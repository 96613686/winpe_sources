# CWinInetHelperClass::~CWinInetHelperClass(void)

- ea: `0x180002f7c`
- end: `0x1800031e2`
- name: `??1CWinInetHelperClass@@QEAA@XZ`
- size: `614`
- prototype: `void __fastcall(CWinInetHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180003490`

## callees

- `0x1800012c0`
- `0x180002e38`
- `0x180002f7c`
- `0x1800048cc`
- `0x18000dd54`
- `0x18000ddac`
- `0x180014010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180002fe5`
- `KERNEL32!CloseHandle` at `0x180002fe5`
- `KERNEL32!WaitForSingleObjectEx` at `0x180002fd1`
- `KERNEL32!WaitForSingleObjectEx` at `0x180002fd1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002fb7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000301e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002fb7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000301e`
- `DNSAPI!DnsFreeProxyName` at `0x18000312a`
- `DNSAPI!DnsFreeProxyName` at `0x180003143`
- `DNSAPI!DnsFreeProxyName` at `0x18000312a`
- `DNSAPI!DnsFreeProxyName` at `0x180003143`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003191`

## string_xrefs

- `0x1800030a0`: `Waited for %dms for WinInet %s thread to finish.`

## pseudocode

```c
void __fastcall CWinInetHelperClass::~CWinInetHelperClass(CWinInetHelperClass *this)
{
  __int64 v1; // r14
  unsigned int i; // esi
  unsigned __int64 v4; // rbx
  const wchar_t *v5; // r9
  __int64 v6; // rbx
  _QWORD *v7; // rbx
  WCHAR *v8; // rcx
  WCHAR *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+30h] BYREF
  struct _FILETIME v13; // [rsp+68h] [rbp+38h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF

  v1 = *((_QWORD *)this + 602);
  for ( i = 0; i < 4; ++i )
  {
    if ( *((_QWORD *)this + i + 553) )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      WaitForSingleObjectEx(*((HANDLE *)this + i + 553), 0xFFFFFFFF, 0);
      CloseHandle(*((HANDLE *)this + i + 553));
      *((_QWORD *)this + i + 553) = 0;
      if ( *((int *)qword_18001BDC8 + (int)i) >= 0 )
        _InterlockedDecrement((volatile signed __int32 *)qword_18001BDC8 + (int)i);
      if ( v1 )
      {
        v13 = 0;
        GetSystemTimeAsFileTime(&v13);
        v4 = *(_QWORD *)&v13 - *(_QWORD *)&SystemTimeAsFileTime;
        v14 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
        if ( i )
        {
          v5 = L"validation";
          if ( i != 1 )
            v5 = L"proxy detection";
        }
        else
        {
          v5 = L"diagnosis";
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v14,
          L"Waited for %dms for WinInet %s thread to finish.",
          (unsigned int)(v4 / 0x2710),
          v5);
        v6 = v14;
        (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v1 + 24LL))(
          v1,
          2,
          0,
          L"WinInetHelperClass",
          v14);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 - 24) + 8LL))(*(_QWORD *)(v6 - 24));
      }
    }
  }
  FreeProxyInfo((CWinInetHelperClass *)((char *)this + 4896));
  FreeUserProxyConfig((CWinInetHelperClass *)((char *)this + 4856));
  v7 = (_QWORD *)*((_QWORD *)this + 639);
  if ( v7 )
  {
    v8 = (WCHAR *)v7[1];
    if ( v8 )
    {
      DnsFreeProxyName(v8);
      v7[1] = 0;
    }
    v9 = (WCHAR *)v7[3];
    if ( v9 )
    {
      DnsFreeProxyName(v9);
      v7[3] = 0;
    }
    operator delete(v7);
    *((_QWORD *)this + 639) = 0;
  }
  v10 = *((_QWORD *)this + 602);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 602) = 0;
  }
  if ( *((_DWORD *)this + 718) )
  {
    CoTaskMemFree(*((LPVOID *)this + 360));
    *((_QWORD *)this + 360) = 0;
    *((_DWORD *)this + 718) = 0;
  }
  v11 = *((_QWORD *)this + 603);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)this + 603) = 0;
  }
  CNetDiagHelperEx::~CNetDiagHelperEx(this);
}

```

## disassembly

```asm
0x180002f7c  mov     [rsp-28h+arg_18], rbx
0x180002f81  push    rbp
0x180002f82  push    rsi
0x180002f83  push    rdi
0x180002f84  push    r14
0x180002f86  push    r15
0x180002f88  mov     rbp, rsp
0x180002f8b  sub     rsp, 30h
0x180002f8f  mov     r14, [rcx+12D0h]
0x180002f96  xor     r15d, r15d
0x180002f99  mov     esi, r15d
0x180002f9c  mov     rdi, rcx
0x180002f9f  mov     ebx, esi
0x180002fa1  cmp     [rdi+rbx*8+1148h], r15
0x180002fa9  jz      loc_1800030F2
0x180002faf  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002fb3  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r15
0x180002fb7  call    cs:__imp_GetSystemTimeAsFileTime
0x180002fbe  nop     dword ptr [rax+rax+00h]
0x180002fc3  mov     rcx, [rdi+rbx*8+1148h]; hHandle
0x180002fcb  xor     r8d, r8d; bAlertable
0x180002fce  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002fd1  call    cs:__imp_WaitForSingleObjectEx
0x180002fd8  nop     dword ptr [rax+rax+00h]
0x180002fdd  mov     rcx, [rdi+rbx*8+1148h]; hObject
0x180002fe5  call    cs:__imp_CloseHandle
0x180002fec  nop     dword ptr [rax+rax+00h]
0x180002ff1  movsxd  rax, esi
0x180002ff4  lea     rcx, qword_18001BDC8
0x180002ffb  mov     [rdi+rbx*8+1148h], r15
0x180003003  cmp     [rcx+rax*4], r15d
0x180003007  jl      short loc_18000300D
0x180003009  lock dec dword ptr [rcx+rax*4]
0x18000300d  test    r14, r14
0x180003010  jz      loc_1800030F2
0x180003016  lea     rcx, [rbp+arg_8]; lpSystemTimeAsFileTime
0x18000301a  mov     qword ptr [rbp+arg_8.dwLowDateTime], r15
0x18000301e  call    cs:__imp_GetSystemTimeAsFileTime
0x180003025  nop     dword ptr [rax+rax+00h]
0x18000302a  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000302d  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x180003030  mov     ebx, [rbp+arg_8.dwHighDateTime]
0x180003033  shl     rcx, 20h
0x180003037  or      rcx, rax
0x18000303a  shl     rbx, 20h
0x18000303e  mov     eax, [rbp+arg_8.dwLowDateTime]
0x180003041  or      rbx, rax
0x180003044  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000304b  sub     rbx, rcx
0x18000304e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180003055  mov     rax, [rax+18h]
0x180003059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000305e  add     rax, 18h
0x180003062  mov     [rbp+arg_10], rax
0x180003066  test    esi, esi
0x180003068  jnz     short loc_180003073
0x18000306a  lea     r9, aDiagnosis; "diagnosis"
0x180003071  jmp     short loc_180003088
0x180003073  cmp     esi, 1
0x180003076  lea     r9, aValidation; "validation"
0x18000307d  lea     rax, aProxyDetection; "proxy detection"
0x180003084  cmovnz  r9, rax
0x180003088  mov     rax, 346DC5D63886594Bh
0x180003092  lea     rcx, [rbp+arg_10]
0x180003096  mul     rbx
0x180003099  shr     rdx, 0Bh
0x18000309d  mov     r8d, edx
0x1800030a0  lea     rdx, aWaitedForDmsFo; "Waited for %dms for WinInet %s thread t"...
0x1800030a7  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800030ac  mov     rax, [r14]
0x1800030af  lea     r9, aWininethelperc; "WinInetHelperClass"
0x1800030b6  mov     rbx, [rbp+arg_10]
0x1800030ba  xor     r8d, r8d
0x1800030bd  mov     rcx, r14
0x1800030c0  mov     [rsp+30h+var_10], rbx
0x1800030c5  mov     rax, [rax+18h]
0x1800030c9  lea     edx, [r8+2]
0x1800030cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d2  lea     rdx, [rbx-18h]
0x1800030d6  or      eax, 0FFFFFFFFh
0x1800030d9  lock xadd [rdx+10h], eax
0x1800030de  sub     eax, 1
0x1800030e1  jg      short loc_1800030F2
0x1800030e3  mov     rcx, [rdx]
0x1800030e6  mov     rax, [rcx]
0x1800030e9  mov     rax, [rax+8]
0x1800030ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f2  inc     esi
0x1800030f4  cmp     esi, 4
0x1800030f7  jb      loc_180002F9F
0x1800030fd  lea     rcx, [rdi+1320h]; struct _WINHTTP_PROXY_INFO *
0x180003104  call    ?FreeProxyInfo@@YAXPEAU_WINHTTP_PROXY_INFO@@@Z; FreeProxyInfo(_WINHTTP_PROXY_INFO *)
0x180003109  lea     rcx, [rdi+12F8h]; struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *
0x180003110  call    ?FreeUserProxyConfig@@YAXPEAU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z; FreeUserProxyConfig(_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)
0x180003115  mov     rbx, [rdi+13F8h]
0x18000311c  test    rbx, rbx
0x18000311f  jz      short loc_180003162
0x180003121  mov     rcx, [rbx+8]; proxyName
0x180003125  test    rcx, rcx
0x180003128  jz      short loc_18000313A
0x18000312a  call    cs:__imp_DnsFreeProxyName
0x180003131  nop     dword ptr [rax+rax+00h]
0x180003136  mov     [rbx+8], r15
0x18000313a  mov     rcx, [rbx+18h]; proxyName
0x18000313e  test    rcx, rcx
0x180003141  jz      short loc_180003153
0x180003143  call    cs:__imp_DnsFreeProxyName
0x18000314a  nop     dword ptr [rax+rax+00h]
0x18000314f  mov     [rbx+18h], r15
0x180003153  mov     rcx, rbx; Block
0x180003156  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000315b  mov     [rdi+13F8h], r15
0x180003162  mov     rcx, [rdi+12D0h]
0x180003169  test    rcx, rcx
0x18000316c  jz      short loc_180003181
0x18000316e  mov     rax, [rcx]
0x180003171  mov     rax, [rax+10h]
0x180003175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000317a  mov     [rdi+12D0h], r15
0x180003181  cmp     [rdi+0B38h], r15d
0x180003188  jz      short loc_1800031AB
0x18000318a  mov     rcx, [rdi+0B40h]; pv
0x180003191  call    cs:__imp_CoTaskMemFree
0x180003198  nop     dword ptr [rax+rax+00h]
0x18000319d  mov     [rdi+0B40h], r15
0x1800031a4  mov     [rdi+0B38h], r15d
0x1800031ab  mov     rcx, [rdi+12D8h]
0x1800031b2  test    rcx, rcx
0x1800031b5  jz      short loc_1800031CA
0x1800031b7  mov     rax, [rcx]
0x1800031ba  mov     rax, [rax+10h]
0x1800031be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c3  mov     [rdi+12D8h], r15
0x1800031ca  mov     rcx, rdi; this
0x1800031cd  mov     rbx, [rsp+30h+arg_18]
0x1800031d2  add     rsp, 30h
0x1800031d6  pop     r15
0x1800031d8  pop     r14
0x1800031da  pop     rdi
0x1800031db  pop     rsi
0x1800031dc  pop     rbp
0x1800031dd  jmp     ??1CNetDiagHelperEx@@QEAA@XZ; CNetDiagHelperEx::~CNetDiagHelperEx(void)
```
