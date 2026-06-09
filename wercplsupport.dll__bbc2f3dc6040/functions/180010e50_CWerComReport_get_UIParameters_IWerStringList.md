# CWerComReport::_get_UIParameters(IWerStringList * *)

- ea: `0x180010e50`
- end: `0x180010f4f`
- name: `?_get_UIParameters@CWerComReport@@QEAAJPEAPEAUIWerStringList@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, struct IWerStringList **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011b60`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800073d4`
- `0x180010e50`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_UIParameters(CWerComReport *this, struct IWerStringList **a2)
{
  CManagedObj *v4; // rax
  CManagedObj *v5; // rdi
  __int64 v6; // rbx
  int v7; // eax
  unsigned int v8; // ebx

  v4 = (CManagedObj *)operator new(0x30u);
  v5 = v4;
  if ( v4 )
  {
    v6 = *((_QWORD *)this + 4);
    CManagedObj::CManagedObj(v4);
    *(_QWORD *)v5 = &CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `CManagedObj'};
    *((_QWORD *)v5 + 3) = &CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `IWerStringList'};
    _InterlockedIncrement((volatile signed __int32 *)v5 + 2);
    *((_QWORD *)v5 + 4) = v6;
    *((_QWORD *)v5 + 5) = this;
    (*(void (__fastcall **)(CWerComReport *))(*(_QWORD *)this + 8LL))(this);
    v7 = (**(__int64 (__fastcall ***)(CManagedObj *, GUID *, struct IWerStringList **))v5)(v5, &IID_IWerStringList, a2);
    v8 = v7;
    if ( v7 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)v7);
    }
    (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v5 + 16LL))(v5);
    return v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180010e50  push    rbx
0x180010e52  push    rbp
0x180010e53  push    rsi
0x180010e54  push    rdi
0x180010e55  sub     rsp, 28h
0x180010e59  mov     rsi, rcx
0x180010e5c  mov     rbp, rdx
0x180010e5f  mov     ecx, 30h ; '0'; Size
0x180010e64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010e69  mov     rdi, rax
0x180010e6c  test    rax, rax
0x180010e6f  jz      loc_180010F13
0x180010e75  mov     rbx, [rsi+20h]
0x180010e79  mov     rcx, rax; this
0x180010e7c  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x180010e81  lea     rax, ??_7?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@6BCManagedObj@@@; const CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::`vftable'{for `CManagedObj'}
0x180010e88  mov     [rdi], rax
0x180010e8b  lea     rax, ??_7?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@6BIWerStringList@@@; const CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::`vftable'{for `IWerStringList'}
0x180010e92  mov     [rdi+18h], rax
0x180010e96  lock inc dword ptr [rdi+8]
0x180010e9a  mov     [rdi+20h], rbx
0x180010e9e  mov     rcx, rsi
0x180010ea1  mov     [rdi+28h], rsi
0x180010ea5  mov     rax, [rsi]
0x180010ea8  mov     rax, [rax+8]
0x180010eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eb1  mov     rax, [rdi]
0x180010eb4  lea     rdx, IID_IWerStringList
0x180010ebb  mov     r8, rbp
0x180010ebe  mov     rcx, rdi
0x180010ec1  mov     rax, [rax]
0x180010ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ec9  mov     ebx, eax
0x180010ecb  test    eax, eax
0x180010ecd  jns     short loc_180010F00
0x180010ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ed6  lea     rdx, WPP_GLOBAL_Control
0x180010edd  cmp     rcx, rdx
0x180010ee0  jz      short loc_180010F00
0x180010ee2  test    byte ptr [rcx+1Ch], 1
0x180010ee6  jz      short loc_180010F00
0x180010ee8  mov     rcx, [rcx+10h]
0x180010eec  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010ef3  mov     edx, 26h ; '&'
0x180010ef8  mov     r9d, eax
0x180010efb  call    WPP_SF_d
0x180010f00  mov     rax, [rdi]
0x180010f03  mov     rcx, rdi
0x180010f06  mov     rax, [rax+10h]
0x180010f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f0f  mov     eax, ebx
0x180010f11  jmp     short loc_180010F46
0x180010f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f1a  lea     rdx, WPP_GLOBAL_Control
0x180010f21  cmp     rcx, rdx
0x180010f24  jz      short loc_180010F41
0x180010f26  test    byte ptr [rcx+1Ch], 1
0x180010f2a  jz      short loc_180010F41
0x180010f2c  mov     rcx, [rcx+10h]
0x180010f30  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010f37  mov     edx, 25h ; '%'
0x180010f3c  call    WPP_SF_
0x180010f41  mov     eax, 8007000Eh
0x180010f46  add     rsp, 28h
0x180010f4a  pop     rdi
0x180010f4b  pop     rsi
0x180010f4c  pop     rbp
0x180010f4d  pop     rbx
0x180010f4e  retn
```
