# CWinInetHelperClass::LowHealthGetUserAutoProxyConfig(_WINHTTP_PROXY_INFO *,tagDIAGNOSIS_STATUS *,int *,int *)

- ea: `0x180009ae4`
- end: `0x180009dfd`
- name: `?LowHealthGetUserAutoProxyConfig@CWinInetHelperClass@@AEAAJPEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@PEAH2@Z`
- size: `793`
- prototype: `__int64 __usercall@<rax>(CWinInetHelperClass *__hidden this@<rcx>, struct _WINHTTP_PROXY_INFO *@<rdx>, enum tagDIAGNOSIS_STATUS *@<r8>, int *@<r9>, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009e04`

## callees

- `0x1800048cc`
- `0x180009858`
- `0x180009ae4`
- `0x18000fce8`
- `0x180014010`

## string_xrefs

- `0x180009c1c`: `The proxy auto-detection thread timed out. Will try direct connection.`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::LowHealthGetUserAutoProxyConfig(
        CWinInetHelperClass *this,
        struct _WINHTTP_PROXY_INFO *a2,
        enum tagDIAGNOSIS_STATUS *a3,
        int *a4,
        int *a5)
{
  unsigned int PacFileServerInfo; // esi
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rcx
  const wchar_t *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rbx
  int v20; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v21[8]; // [rsp+38h] [rbp-40h] BYREF

  v20 = 0;
  PacFileServerInfo = CWinInetHelperClass::ExecuteProxyAutodetectionThread(
                        this,
                        1,
                        &v20,
                        a4,
                        (enum ThreadExternalHostResolveResult *)v21);
  if ( (PacFileServerInfo & 0x80000000) != 0 )
    return PacFileServerInfo;
  v9 = v20;
  if ( v20 >= 0 )
  {
    *(_OWORD *)a2 = *((_OWORD *)this + 306);
    *((_QWORD *)a2 + 2) = *((_QWORD *)this + 614);
    if ( *((_QWORD *)this + 602) )
    {
      v10 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
      v11 = *((_QWORD *)this + 613);
      v21[0] = v10 + 24;
      if ( v11 )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          v21,
          L"Auto proxy detection success, proxy string: '%s'.");
      else
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          v21,
          L"Auto proxy detection success, no proxy auto-detected.");
      v12 = v21[0];
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 602) + 24LL))(
        *((_QWORD *)this + 602),
        2,
        0,
        L"WinInetHelperClass",
        v21[0]);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v12 - 24) + 8LL))(*(_QWORD *)(v12 - 24));
    }
    return PacFileServerInfo;
  }
  *a3 = DS_CONFIRMED;
  if ( v9 == -2147024638 )
  {
    v13 = *((_QWORD *)this + 602);
    *((_DWORD *)this + 1238) = 1;
    if ( !v13 )
      return PacFileServerInfo;
    v14 = L"The proxy auto-detection thread timed out. Will try direct connection.";
LABEL_12:
    (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v13 + 24LL))(
      v13,
      2,
      0,
      L"WinInetHelperClass",
      v14);
    return PacFileServerInfo;
  }
  if ( v9 == -2147012716 )
  {
    v15 = *((_QWORD *)this + 602);
    if ( v15 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v15 + 24LL))(
        v15,
        2,
        0,
        L"WinInetHelperClass",
        L"Got ERROR_WINHTTP_AUTODETECTION_FAILED while detecting proxy. Assuming no proxy on the network.");
    *((_DWORD *)this + 793) = 0;
    return PacFileServerInfo;
  }
  if ( v9 != -2147012729 )
  {
    if ( *((_QWORD *)this + 602) )
    {
      v21[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        v21,
        L"Auto proxy detection failed with error hr=0x%x.",
        v9);
      v18 = v21[0];
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 602) + 24LL))(
        *((_QWORD *)this + 602),
        2,
        0,
        L"WinInetHelperClass",
        v21[0]);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 - 24) + 8LL))(*(_QWORD *)(v18 - 24));
    }
    goto LABEL_31;
  }
  PacFileServerInfo = CWinInetHelperClass::LowHealthGetPacFileServerInfo(this);
  *a5 = 1;
  if ( !PacFileServerInfo )
  {
    v13 = *((_QWORD *)this + 602);
    if ( !v13 )
      return PacFileServerInfo;
    v14 = L"PAC script server info retrieved successfully, but cannot download script";
    goto LABEL_12;
  }
  if ( PacFileServerInfo != -2147013892 && PacFileServerInfo != -2147013895 )
  {
    v16 = *((_QWORD *)this + 602);
    PacFileServerInfo = 0;
    if ( v16 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v16 + 24LL))(
        v16,
        2,
        0,
        L"WinInetHelperClass",
        L"Unexpected error encountered when retreiving PAC server info.");
LABEL_31:
    *((_DWORD *)this + 1275) = 1;
    return PacFileServerInfo;
  }
  v17 = *((_QWORD *)this + 602);
  if ( v17 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v17 + 24LL))(
      v17,
      2,
      0,
      L"WinInetHelperClass",
      L"The PAC script server name cannot be resolved.");
  *((_DWORD *)this + 1276) = 1;
  return 0;
}

```

## disassembly

```asm
0x180009ae4  push    rbx
0x180009ae6  push    rbp
0x180009ae7  push    rsi
0x180009ae8  push    rdi
0x180009ae9  push    r12
0x180009aeb  push    r14
0x180009aed  sub     rsp, 48h
0x180009af1  mov     r14, r8
0x180009af4  mov     [rsp+78h+var_48], 0
0x180009afc  mov     rbp, rdx
0x180009aff  lea     rax, [rsp+78h+var_40]
0x180009b04  mov     r12d, 1
0x180009b0a  mov     [rsp+78h+var_58], rax; enum ThreadExternalHostResolveResult *
0x180009b0f  mov     edx, r12d; int
0x180009b12  lea     r8, [rsp+78h+var_48]; int *
0x180009b17  mov     rdi, rcx
0x180009b1a  call    ?ExecuteProxyAutodetectionThread@CWinInetHelperClass@@AEAAJHPEAJPEAHPEAW4ThreadExternalHostResolveResult@@@Z; CWinInetHelperClass::ExecuteProxyAutodetectionThread(int,long *,int *,ThreadExternalHostResolveResult *)
0x180009b1f  mov     esi, eax
0x180009b21  test    eax, eax
0x180009b23  js      loc_180009DED
0x180009b29  mov     ebx, [rsp+78h+var_48]
0x180009b2d  test    ebx, ebx
0x180009b2f  js      loc_180009BFA
0x180009b35  movups  xmm0, xmmword ptr [rdi+1320h]
0x180009b3c  movups  xmmword ptr [rbp+0], xmm0
0x180009b40  movsd   xmm1, qword ptr [rdi+1330h]
0x180009b48  movsd   qword ptr [rbp+10h], xmm1
0x180009b4d  cmp     qword ptr [rdi+12D0h], 0
0x180009b55  jz      loc_180009DED
0x180009b5b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009b62  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009b69  mov     rax, [rax+18h]
0x180009b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b72  mov     r8, [rdi+1328h]
0x180009b79  lea     rcx, [rsp+78h+var_40]
0x180009b7e  add     rax, 18h
0x180009b82  mov     [rsp+78h+var_40], rax
0x180009b87  test    r8, r8
0x180009b8a  jz      short loc_180009B9A
0x180009b8c  lea     rdx, aAutoProxyDetec_0; "Auto proxy detection success, proxy str"...
0x180009b93  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009b98  jmp     short loc_180009BA6
0x180009b9a  lea     rdx, aAutoProxyDetec; "Auto proxy detection success, no proxy "...
0x180009ba1  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009ba6  mov     rcx, [rdi+12D0h]
0x180009bad  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009bb4  mov     rbx, [rsp+78h+var_40]
0x180009bb9  xor     r8d, r8d
0x180009bbc  mov     [rsp+78h+var_58], rbx
0x180009bc1  mov     rax, [rcx]
0x180009bc4  lea     edx, [r8+2]
0x180009bc8  mov     rax, [rax+18h]
0x180009bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd1  lea     rdx, [rbx-18h]
0x180009bd5  or      eax, 0FFFFFFFFh
0x180009bd8  lock xadd [rdx+10h], eax
0x180009bdd  sub     eax, r12d
0x180009be0  jg      loc_180009DED
0x180009be6  mov     rcx, [rdx]
0x180009be9  mov     rax, [rcx]
0x180009bec  mov     rax, [rax+8]
0x180009bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bf5  jmp     loc_180009DED
0x180009bfa  mov     [r14], r12d
0x180009bfd  cmp     ebx, 80070102h
0x180009c03  jnz     short loc_180009C47
0x180009c05  mov     rcx, [rdi+12D0h]
0x180009c0c  mov     [rdi+1358h], r12d
0x180009c13  test    rcx, rcx
0x180009c16  jz      loc_180009DED
0x180009c1c  lea     rdx, aTheProxyAutoDe; "The proxy auto-detection thread timed o"...
0x180009c23  mov     rax, [rcx]
0x180009c26  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009c2d  xor     r8d, r8d
0x180009c30  mov     [rsp+78h+var_58], rdx
0x180009c35  mov     rax, [rax+18h]
0x180009c39  lea     edx, [r8+2]
0x180009c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c42  jmp     loc_180009DED
0x180009c47  cmp     ebx, 80072F94h
0x180009c4d  jnz     short loc_180009C90
0x180009c4f  mov     rcx, [rdi+12D0h]
0x180009c56  test    rcx, rcx
0x180009c59  jz      short loc_180009C81
0x180009c5b  mov     rax, [rcx]
0x180009c5e  lea     rdx, aGotErrorWinhtt; "Got ERROR_WINHTTP_AUTODETECTION_FAILED "...
0x180009c65  xor     r8d, r8d
0x180009c68  mov     [rsp+78h+var_58], rdx
0x180009c6d  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009c74  mov     rax, [rax+18h]
0x180009c78  lea     edx, [r8+2]
0x180009c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c81  mov     dword ptr [rdi+0C64h], 0
0x180009c8b  jmp     loc_180009DED
0x180009c90  cmp     ebx, 80072F87h
0x180009c96  jnz     loc_180009D5D
0x180009c9c  mov     rcx, rdi; this
0x180009c9f  call    ?LowHealthGetPacFileServerInfo@CWinInetHelperClass@@AEAAJXZ; CWinInetHelperClass::LowHealthGetPacFileServerInfo(void)
0x180009ca4  mov     esi, eax
0x180009ca6  mov     rax, [rsp+78h+arg_20]
0x180009cae  mov     [rax], r12d
0x180009cb1  test    esi, esi
0x180009cb3  jnz     short loc_180009CD1
0x180009cb5  mov     rcx, [rdi+12D0h]
0x180009cbc  test    rcx, rcx
0x180009cbf  jz      loc_180009DED
0x180009cc5  lea     rdx, aPacScriptServe; "PAC script server info retrieved succes"...
0x180009ccc  jmp     loc_180009C23
0x180009cd1  cmp     esi, 80072AFCh
0x180009cd7  jz      short loc_180009D1D
0x180009cd9  cmp     esi, 80072AF9h
0x180009cdf  jz      short loc_180009D1D
0x180009ce1  mov     rcx, [rdi+12D0h]
0x180009ce8  xor     esi, esi
0x180009cea  test    rcx, rcx
0x180009ced  jz      loc_180009DE6
0x180009cf3  mov     rax, [rcx]
0x180009cf6  lea     rdx, aUnexpectedErro; "Unexpected error encountered when retre"...
0x180009cfd  mov     [rsp+78h+var_58], rdx
0x180009d02  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009d09  xor     r8d, r8d
0x180009d0c  lea     edx, [rsi+2]
0x180009d0f  mov     rax, [rax+18h]
0x180009d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d18  jmp     loc_180009DE6
0x180009d1d  mov     rcx, [rdi+12D0h]
0x180009d24  test    rcx, rcx
0x180009d27  jz      short loc_180009D4F
0x180009d29  mov     rax, [rcx]
0x180009d2c  lea     rdx, aThePacScriptSe; "The PAC script server name cannot be re"...
0x180009d33  xor     r8d, r8d
0x180009d36  mov     [rsp+78h+var_58], rdx
0x180009d3b  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009d42  mov     rax, [rax+18h]
0x180009d46  lea     edx, [r8+2]
0x180009d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d4f  mov     [rdi+13F0h], r12d
0x180009d56  xor     esi, esi
0x180009d58  jmp     loc_180009DED
0x180009d5d  cmp     qword ptr [rdi+12D0h], 0
0x180009d65  jz      short loc_180009DE6
0x180009d67  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009d6e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009d75  mov     rax, [rax+18h]
0x180009d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d7e  add     rax, 18h
0x180009d82  lea     rdx, aAutoProxyDetec_1; "Auto proxy detection failed with error "...
0x180009d89  mov     r8d, ebx
0x180009d8c  mov     [rsp+78h+var_40], rax
0x180009d91  lea     rcx, [rsp+78h+var_40]
0x180009d96  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009d9b  mov     rcx, [rdi+12D0h]
0x180009da2  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009da9  mov     rbx, [rsp+78h+var_40]
0x180009dae  xor     r8d, r8d
0x180009db1  mov     [rsp+78h+var_58], rbx
0x180009db6  mov     rax, [rcx]
0x180009db9  lea     edx, [r8+2]
0x180009dbd  mov     rax, [rax+18h]
0x180009dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc6  lea     rdx, [rbx-18h]
0x180009dca  or      eax, 0FFFFFFFFh
0x180009dcd  lock xadd [rdx+10h], eax
0x180009dd2  sub     eax, r12d
0x180009dd5  jg      short loc_180009DE6
0x180009dd7  mov     rcx, [rdx]
0x180009dda  mov     rax, [rcx]
0x180009ddd  mov     rax, [rax+8]
0x180009de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009de6  mov     [rdi+13ECh], r12d
0x180009ded  mov     eax, esi
0x180009def  add     rsp, 48h
0x180009df3  pop     r14
0x180009df5  pop     r12
0x180009df7  pop     rdi
0x180009df8  pop     rsi
0x180009df9  pop     rbp
0x180009dfa  pop     rbx
0x180009dfb  retn
```
