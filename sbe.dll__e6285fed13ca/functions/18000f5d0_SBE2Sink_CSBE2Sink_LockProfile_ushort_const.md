# SBE2Sink::CSBE2Sink::LockProfile(ushort const *)

- ea: `0x18000f5d0`
- end: `0x18000f737`
- name: `?LockProfile@CSBE2Sink@SBE2Sink@@UEAAJPEBG@Z`
- size: `359`
- prototype: `int(SBE2Sink::CSBE2Sink *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001c00`
- `0x1800089b8`
- `0x18000f058`
- `0x18000f5d0`
- `0x180057140`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000f704`
- `KERNEL32!LeaveCriticalSection` at `0x18000f70d`
- `KERNEL32!LeaveCriticalSection` at `0x18000f704`
- `KERNEL32!LeaveCriticalSection` at `0x18000f70d`
- `KERNEL32!EnterCriticalSection` at `0x18000f5fe`
- `KERNEL32!EnterCriticalSection` at `0x18000f60f`
- `KERNEL32!EnterCriticalSection` at `0x18000f5fe`
- `KERNEL32!EnterCriticalSection` at `0x18000f60f`
- `KERNEL32!lstrcmpiW` at `0x18000f676`
- `KERNEL32!lstrcmpiW` at `0x18000f676`
- `ole32!CoTaskMemFree` at `0x18000f6a1`
- `ole32!CoTaskMemFree` at `0x18000f6a1`

## pseudocode

```c
__int64 __fastcall SBE2Sink::CSBE2Sink::LockProfile(SBE2Sink::CSBE2Sink *this, WCHAR *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  char *v5; // rsi
  struct _RTL_CRITICAL_SECTION *v6; // r14
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  signed int v8; // ebx
  LPCWSTR lpString2; // [rsp+40h] [rbp-38h] BYREF
  __int64 v11; // [rsp+48h] [rbp-30h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v5 = (char *)this - 128;
  v6 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this - 6);
  EnterCriticalSection(v6);
  lpString2 = 0;
  v11 = 0;
  if ( a2 )
  {
    v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 13);
    if ( v7 )
    {
      v8 = (**v7)(v7, &IID_IPauseBuffer, &v11);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v11 + 24LL))(v11, &lpString2);
        if ( v8 >= 0 )
          v8 = lstrcmpiW(a2, lpString2) != 0 ? 0x8000FFFF : 0;
      }
    }
    else
    {
      v8 = SBE2Sink::CSBE2Sink::InternalInitialize((SBE2Sink::CSBE2Sink *)((char *)this - 128), a2);
    }
  }
  else
  {
    v8 = -2147467261;
  }
  CoTaskMemFree((LPVOID)lpString2);
  EhEtw::TPtr<IEhTraceSpan>::Release(&v11);
  if ( v8 < 0 )
    CSbeFileLog::LogEvent(
      0x10u,
      1u,
      L"ERROR: %s(%u); SBE2Sink::LockProfile(%s) [%p] : returning error %08xh",
      L"multimedia\\dshow\\filters\\sbe\\dvrfilters\\sbesink2\\sbesink2.cpp",
      1410,
      a2,
      v5,
      v8);
  else
    CSbeFileLog::LogEvent(2u, 1u, L"* SUCCEEDED : SBE2Sink::LockProfile(%s) [%p]", a2, v5);
  LeaveCriticalSection(v6);
  LeaveCriticalSection(v2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f5d0  mov     [rsp+arg_10], rbx
0x18000f5d5  mov     [rsp+arg_18], rbp
0x18000f5da  push    rsi
0x18000f5db  push    rdi
0x18000f5dc  push    r14
0x18000f5de  sub     rsp, 60h
0x18000f5e2  mov     rax, cs:__security_cookie
0x18000f5e9  xor     rax, rsp
0x18000f5ec  mov     [rsp+78h+var_28], rax
0x18000f5f1  lea     rbp, [rcx+38h]
0x18000f5f5  mov     rbx, rcx
0x18000f5f8  mov     rcx, rbp; lpCriticalSection
0x18000f5fb  mov     rdi, rdx
0x18000f5fe  call    cs:__imp_EnterCriticalSection
0x18000f604  lea     rsi, [rbx-80h]
0x18000f608  mov     r14, [rsi+50h]
0x18000f60c  mov     rcx, r14; lpCriticalSection
0x18000f60f  call    cs:__imp_EnterCriticalSection
0x18000f615  mov     [rsp+78h+lpString2], 0
0x18000f61e  mov     [rsp+78h+var_30], 0
0x18000f627  test    rdi, rdi
0x18000f62a  jz      short loc_18000F697
0x18000f62c  mov     rcx, [rbx+68h]
0x18000f630  test    rcx, rcx
0x18000f633  jz      short loc_18000F688
0x18000f635  mov     rax, [rcx]
0x18000f638  lea     r8, [rsp+78h+var_30]
0x18000f63d  lea     rdx, IID_IPauseBuffer
0x18000f644  mov     rax, [rax]
0x18000f647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f64c  mov     ebx, eax
0x18000f64e  test    eax, eax
0x18000f650  js      short loc_18000F69C
0x18000f652  mov     rcx, [rsp+78h+var_30]
0x18000f657  lea     rdx, [rsp+78h+lpString2]
0x18000f65c  mov     rax, [rcx]
0x18000f65f  mov     rax, [rax+18h]
0x18000f663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f668  mov     ebx, eax
0x18000f66a  test    eax, eax
0x18000f66c  js      short loc_18000F69C
0x18000f66e  mov     rdx, [rsp+78h+lpString2]; lpString2
0x18000f673  mov     rcx, rdi; lpString1
0x18000f676  call    cs:__imp_lstrcmpiW
0x18000f67c  neg     eax
0x18000f67e  sbb     ebx, ebx
0x18000f680  and     ebx, 8000FFFFh
0x18000f686  jmp     short loc_18000F69C
0x18000f688  mov     rdx, rdi; unsigned __int16 *
0x18000f68b  mov     rcx, rsi; this
0x18000f68e  call    ?InternalInitialize@CSBE2Sink@SBE2Sink@@AEAAJPEBG@Z; SBE2Sink::CSBE2Sink::InternalInitialize(ushort const *)
0x18000f693  mov     ebx, eax
0x18000f695  jmp     short loc_18000F69C
0x18000f697  mov     ebx, 80004003h
0x18000f69c  mov     rcx, [rsp+78h+lpString2]; pv
0x18000f6a1  call    cs:__imp_CoTaskMemFree
0x18000f6a7  lea     rcx, [rsp+78h+var_30]
0x18000f6ac  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x18000f6b1  mov     edx, 1; unsigned __int8
0x18000f6b6  test    ebx, ebx
0x18000f6b8  js      short loc_18000F6D3
0x18000f6ba  mov     r9, rdi
0x18000f6bd  mov     [rsp+78h+var_58], rsi
0x18000f6c2  lea     r8, aSucceededSbe2s_3; "* SUCCEEDED : SBE2Sink::LockProfile(%s)"...
0x18000f6c9  lea     ecx, [rdx+1]; unsigned int
0x18000f6cc  call    ?LogEvent@CSbeFileLog@@SAJKEPEBGZZ; CSbeFileLog::LogEvent(ulong,uchar,ushort const *,...)
0x18000f6d1  jmp     short loc_18000F701
0x18000f6d3  mov     [rsp+78h+var_40], ebx
0x18000f6d7  lea     r9, aMultimediaDsho_4; "multimedia\\dshow\\filters\\sbe\\dvrfil"...
0x18000f6de  mov     [rsp+78h+var_48], rsi
0x18000f6e3  lea     r8, aErrorSUSbe2sin; "ERROR: %s(%u); SBE2Sink::LockProfile(%s"...
0x18000f6ea  mov     [rsp+78h+var_50], rdi
0x18000f6ef  mov     ecx, 10h; unsigned int
0x18000f6f4  mov     dword ptr [rsp+78h+var_58], 582h
0x18000f6fc  call    ?LogEvent@CSbeFileLog@@SAJKEPEBGZZ; CSbeFileLog::LogEvent(ulong,uchar,ushort const *,...)
0x18000f701  mov     rcx, r14; lpCriticalSection
0x18000f704  call    cs:__imp_LeaveCriticalSection
0x18000f70a  mov     rcx, rbp; lpCriticalSection
0x18000f70d  call    cs:__imp_LeaveCriticalSection
0x18000f713  mov     eax, ebx
0x18000f715  mov     rcx, [rsp+78h+var_28]
0x18000f71a  xor     rcx, rsp; StackCookie
0x18000f71d  call    __security_check_cookie
0x18000f722  lea     r11, [rsp+78h+var_18]
0x18000f727  mov     rbx, [r11+30h]
0x18000f72b  mov     rbp, [r11+38h]
0x18000f72f  mov     rsp, r11
0x18000f732  pop     r14
0x18000f734  pop     rdi
0x18000f735  pop     rsi
0x18000f736  retn
```
