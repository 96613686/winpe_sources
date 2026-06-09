# CZoneIdentifier::Load(ushort const *,ulong)

- ea: `0x180031ce0`
- end: `0x180032081`
- name: `?Load@CZoneIdentifier@@UEAAJPEBGK@Z`
- size: `929`
- prototype: `__int64 __fastcall(CZoneIdentifier *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180031600`

## callees

- `0x18002fee0`
- `0x18003142c`
- `0x180031ce0`
- `0x180032088`
- `0x1800830ec`
- `0x1800924d0`
- `0x180097d78`
- `0x1800a11c0`
- `0x1800a5410`
- `0x1800aca08`
- `0x1801285fe`
- `0x180129010`

## import_xrefs

- `msvcrt!wcstok_s` at `0x180031efe`
- `msvcrt!wcstok_s` at `0x180031efe`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180031dce`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180031de7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180031ea6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180032040`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180031dce`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180031de7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180031ea6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180032040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e68`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180031db9`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180031db9`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x180031e4e`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x180031f9b`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x180031e4e`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x180031f9b`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180031d72`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180031d72`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x180031d1f`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x180031d1f`

## pseudocode

```c
__int64 __fastcall CZoneIdentifier::Load(CZoneIdentifier *this, const unsigned __int16 *a2)
{
  HRESULT updated; // ebx
  __int64 v5; // rcx
  wchar_t *v7; // r15
  __int64 v8; // rdx
  WCHAR *v9; // rax
  WCHAR *v10; // rbx
  const WCHAR *v11; // r9
  DWORD v12; // r14d
  WCHAR *v13; // rdi
  DWORD LastError; // eax
  unsigned int v15; // r8d
  wchar_t *v16; // rax
  __int64 v17; // rcx
  wchar_t *v18; // rsi
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rax
  WCHAR *v23; // rsi
  unsigned __int64 v24; // r12
  WCHAR *v25; // rax
  unsigned int v26; // [rsp+20h] [rbp-20h] BYREF
  wchar_t *v27; // [rsp+28h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  WCHAR *v29; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *Context; // [rsp+98h] [rbp+58h] BYREF

  updated = CZoneIdentifier::_UpdateFile((CZoneIdentifier *)((char *)this - 40), a2);
  if ( updated < 0 )
  {
    v8 = 697;
    goto LABEL_8;
  }
  v5 = *((_QWORD *)this + 1);
  LODWORD(v29) = 0;
  if ( !(unsigned int)PathFileExistsAndAttributesW(v5, &v29) || ((unsigned __int8)v29 & 0x10) != 0 )
    return 2147942402LL;
  v7 = (wchar_t *)((char *)this + 16);
  Context = (wchar_t *)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
  {
    CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore((char *)this + 16);
    updated = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, (void **)this + 2);
    if ( updated < 0 )
    {
      v8 = 704;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
        (const char *)(unsigned int)updated,
        v26);
      return (unsigned int)updated;
    }
  }
  if ( (GetPrivateProfileIntW(L"ZoneTransfer", L"ZoneId", -1, *((LPCWSTR *)this + 1)) & 0x80000000) == 0 )
  {
    v9 = (WCHAR *)operator new[](0x1000u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( v9 )
      memset_0(v9, 0, 0x1000u);
    else
      v10 = 0;
    v11 = (const WCHAR *)*((_QWORD *)this + 1);
    v12 = 2048;
    v29 = v10;
    if ( GetPrivateProfileSectionW(L"ZoneTransfer", v10, 0x800u, v11) == 2046 )
    {
      v23 = v10;
      do
      {
        v12 *= 2;
        v24 = 2LL * v12;
        if ( !is_mul_ok(v12, 2u) )
          v24 = -1;
        v25 = (WCHAR *)operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
        v10 = v25;
        if ( v25 )
          memset_0(v25, 0, v24);
        else
          v10 = 0;
        v29 = v10;
        if ( v23 )
          operator delete(v23);
        v23 = v10;
      }
      while ( GetPrivateProfileSectionW(L"ZoneTransfer", v10, v12, *((LPCWSTR *)this + 1)) == v12 - 2 );
      v7 = Context;
    }
    v13 = v10;
    LastError = GetLastError();
    if ( LastError )
    {
      updated = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x2CF, v15, (const char *)LastError, v26);
      if ( v13 )
        operator delete(v13);
      return (unsigned int)updated;
    }
    while ( *v13 )
    {
      Context = 0;
      v16 = wcstok_s(v13, L"=", &Context);
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      v18 = &v16[v17 + 1];
      v19 = *(_QWORD *)v7;
      v27 = v18;
      LOWORD(v26) = 31;
      v20 = (*(__int64 (__fastcall **)(__int64, wchar_t *, unsigned int *))(*(_QWORD *)v19 + 32LL))(v19, v16, &v26);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D7,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
          (const char *)(unsigned int)v20,
          v26);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v29);
        return v21;
      }
      v22 = -1;
      do
        ++v22;
      while ( v18[v22] );
      v13 = &v18[v22 + 1];
    }
    if ( v10 )
      operator delete(v10);
  }
  else
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(268435481) && !(unsigned __int8)IEConfiguration_GetBool(268435482)
      || !(unsigned __int8)IEConfiguration_GetBool(536870915) && !(unsigned __int8)IEConfiguration_GetBool(536870916) )
    {
      updated = -2147024891;
      v8 = 753;
      goto LABEL_8;
    }
    LODWORD(v29) = 0;
    updated = AskBrokerToGetZoneIdentifier(a2, &v29);
    if ( updated < 0 )
    {
      v8 = 745;
      goto LABEL_8;
    }
    updated = CZoneIdentifier::_SetZoneId((CZoneIdentifier *)((char *)this - 40), L"ZoneId", (unsigned int)v29);
    if ( updated < 0 )
    {
      v8 = 747;
      goto LABEL_8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180031ce0  mov     [rsp-38h+arg_8], rbx
0x180031ce5  push    rbp
0x180031ce6  push    rsi
0x180031ce7  push    rdi
0x180031ce8  push    r12
0x180031cea  push    r13
0x180031cec  push    r14
0x180031cee  push    r15
0x180031cf0  mov     rbp, rsp
0x180031cf3  sub     rsp, 40h
0x180031cf7  mov     rdi, rcx
0x180031cfa  mov     rsi, rdx
0x180031cfd  add     rcx, 0FFFFFFFFFFFFFFD8h; this
0x180031d01  call    ?_UpdateFile@CZoneIdentifier@@AEAAJPEBG@Z; CZoneIdentifier::_UpdateFile(ushort const *)
0x180031d06  xor     r13d, r13d
0x180031d09  mov     ebx, eax
0x180031d0b  test    eax, eax
0x180031d0d  js      loc_180031FBC
0x180031d13  mov     rcx, [rdi+8]
0x180031d17  lea     rdx, [rbp+arg_0]
0x180031d1b  mov     dword ptr [rbp+arg_0], r13d
0x180031d1f  call    cs:__imp_PathFileExistsAndAttributesW
0x180031d26  nop     dword ptr [rax+rax+00h]
0x180031d2b  test    eax, eax
0x180031d2d  jnz     short loc_180031D4D
0x180031d2f  mov     eax, 80070002h
0x180031d34  mov     rbx, [rsp+40h+arg_8]
0x180031d3c  add     rsp, 40h
0x180031d40  pop     r15
0x180031d42  pop     r14
0x180031d44  pop     r13
0x180031d46  pop     r12
0x180031d48  pop     rdi
0x180031d49  pop     rsi
0x180031d4a  pop     rbp
0x180031d4b  retn
0x180031d4d  test    byte ptr [rbp+arg_0], 10h
0x180031d51  jnz     short loc_180031D2F
0x180031d53  lea     r15, [rdi+10h]
0x180031d57  mov     [rbp+Context], r15
0x180031d5b  cmp     [r15], r13
0x180031d5e  jz      short loc_180031DA0
0x180031d60  mov     rcx, r15
0x180031d63  call    ?ClearPropertyStore@?$CPropertyStoreHelperBase@UINamedPropertyStore@@@@QEAAXXZ; CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(void)
0x180031d68  mov     rdx, r15; ppv
0x180031d6b  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x180031d72  call    cs:__imp_PSCreateMemoryPropertyStore
0x180031d79  nop     dword ptr [rax+rax+00h]
0x180031d7e  mov     ebx, eax
0x180031d80  test    eax, eax
0x180031d82  jns     short loc_180031DA0
0x180031d84  mov     edx, 2C0h; void *
0x180031d89  mov     rcx, [rbp+38h]; this
0x180031d8d  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180031d94  mov     r9d, ebx; char *
0x180031d97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d9c  mov     eax, ebx
0x180031d9e  jmp     short loc_180031D34
0x180031da0  mov     r9, [rdi+8]; lpFileName
0x180031da4  lea     rdx, KeyName; "ZoneId"
0x180031dab  or      r12, 0FFFFFFFFFFFFFFFFh
0x180031daf  lea     rcx, AppName; "ZoneTransfer"
0x180031db6  mov     r8d, r12d; nDefault
0x180031db9  call    cs:__imp_GetPrivateProfileIntW
0x180031dc0  nop     dword ptr [rax+rax+00h]
0x180031dc5  test    eax, eax
0x180031dc7  jns     short loc_180031E07
0x180031dc9  mov     ecx, 10000019h
0x180031dce  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180031dd5  nop     dword ptr [rax+rax+00h]
0x180031dda  test    al, al
0x180031ddc  jnz     loc_180031EA1
0x180031de2  mov     ecx, 1000001Ah
0x180031de7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180031dee  nop     dword ptr [rax+rax+00h]
0x180031df3  test    al, al
0x180031df5  jnz     loc_180031EA1
0x180031dfb  mov     ebx, 80070005h
0x180031e00  mov     edx, 2F1h
0x180031e05  jmp     short loc_180031D89
0x180031e07  mov     esi, 1000h
0x180031e0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031e13  mov     ecx, esi; unsigned __int64
0x180031e15  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180031e1a  mov     rbx, rax
0x180031e1d  test    rax, rax
0x180031e20  jz      loc_180031EDE
0x180031e26  mov     r8d, esi; Size
0x180031e29  xor     edx, edx; Val
0x180031e2b  mov     rcx, rax; void *
0x180031e2e  call    memset_0
0x180031e33  mov     r9, [rdi+8]; lpFileName
0x180031e37  lea     rcx, AppName; "ZoneTransfer"
0x180031e3e  mov     r14d, 800h
0x180031e44  mov     [rbp+arg_0], rbx
0x180031e48  mov     r8d, r14d; nSize
0x180031e4b  mov     rdx, rbx; lpReturnedString
0x180031e4e  call    cs:__imp_GetPrivateProfileSectionW
0x180031e55  nop     dword ptr [rax+rax+00h]
0x180031e5a  cmp     eax, 7FEh
0x180031e5f  jz      loc_180031FC6
0x180031e65  mov     rdi, rbx
0x180031e68  call    cs:__imp_GetLastError
0x180031e6f  nop     dword ptr [rax+rax+00h]
0x180031e74  test    eax, eax
0x180031e76  jz      short loc_180031EE6
0x180031e78  mov     rcx, [rbp+38h]; this
0x180031e7c  mov     r9d, eax; char *
0x180031e7f  mov     edx, 2CFh; void *
0x180031e84  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031e89  mov     ebx, eax
0x180031e8b  test    rdi, rdi
0x180031e8e  jz      loc_180031D9C
0x180031e94  mov     rcx, rdi; void *
0x180031e97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031e9c  jmp     loc_180031D9C
0x180031ea1  mov     ecx, 20000003h
0x180031ea6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180031ead  nop     dword ptr [rax+rax+00h]
0x180031eb2  test    al, al
0x180031eb4  jz      loc_18003203B
0x180031eba  lea     rdx, [rbp+arg_0]
0x180031ebe  mov     dword ptr [rbp+arg_0], r13d
0x180031ec2  mov     rcx, rsi
0x180031ec5  call    _AskBrokerToGetZoneIdentifier
0x180031eca  mov     ebx, eax
0x180031ecc  test    eax, eax
0x180031ece  jns     loc_180032059
0x180031ed4  mov     edx, 2E9h
0x180031ed9  jmp     loc_180031D89
0x180031ede  mov     rbx, r13
0x180031ee1  jmp     loc_180031E33
0x180031ee6  cmp     [rdi], r13w
0x180031eea  jz      short loc_180031F62
0x180031eec  lea     r8, [rbp+Context]; Context
0x180031ef0  mov     [rbp+Context], r13
0x180031ef4  lea     rdx, asc_18013891C; "="
0x180031efb  mov     rcx, rdi; String
0x180031efe  call    cs:__imp_wcstok_s
0x180031f05  nop     dword ptr [rax+rax+00h]
0x180031f0a  mov     rdx, rax
0x180031f0d  mov     rcx, r12
0x180031f10  inc     rcx
0x180031f13  cmp     [rax+rcx*2], r13w
0x180031f18  jnz     short loc_180031F10
0x180031f1a  inc     rcx
0x180031f1d  lea     r8, [rbp+var_20]
0x180031f21  lea     rsi, [rax+rcx*2]
0x180031f25  mov     rcx, [r15]
0x180031f28  mov     eax, 1Fh
0x180031f2d  mov     [rbp+var_18], rsi
0x180031f31  mov     word ptr [rbp+var_20], ax
0x180031f35  mov     rax, [rcx]
0x180031f38  mov     rax, [rax+20h]
0x180031f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f41  mov     edi, eax
0x180031f43  test    eax, eax
0x180031f45  js      loc_180032013
0x180031f4b  mov     rax, r12
0x180031f4e  inc     rax
0x180031f51  cmp     [rsi+rax*2], r13w
0x180031f56  jnz     short loc_180031F4E
0x180031f58  lea     rdi, [rax+1]
0x180031f5c  lea     rdi, [rsi+rdi*2]
0x180031f60  jmp     short loc_180031EE6
0x180031f62  test    rbx, rbx
0x180031f65  jz      short loc_180031F6F
0x180031f67  mov     rcx, rbx; void *
0x180031f6a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031f6f  xor     eax, eax
0x180031f71  jmp     loc_180031D34
0x180031f76  mov     [rbp+arg_0], rbx
0x180031f7a  test    rsi, rsi
0x180031f7d  jz      short loc_180031F87
0x180031f7f  mov     rcx, rsi; void *
0x180031f82  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031f87  mov     r9, [rdi+8]; lpFileName
0x180031f8b  lea     rcx, AppName; "ZoneTransfer"
0x180031f92  mov     r8d, r14d; nSize
0x180031f95  mov     rdx, rbx; lpReturnedString
0x180031f98  mov     rsi, rbx
0x180031f9b  call    cs:__imp_GetPrivateProfileSectionW
0x180031fa2  nop     dword ptr [rax+rax+00h]
0x180031fa7  lea     ecx, [r14-2]
0x180031fab  cmp     eax, ecx
0x180031fad  jz      short loc_180031FCD
0x180031faf  mov     r15, [rbp+Context]
0x180031fb3  or      r12, 0FFFFFFFFFFFFFFFFh
0x180031fb7  jmp     loc_180031E65
0x180031fbc  mov     edx, 2B9h
0x180031fc1  jmp     loc_180031D89
0x180031fc6  mov     rsi, rbx
0x180031fc9  or      r15, 0FFFFFFFFFFFFFFFFh
0x180031fcd  add     r14d, r14d
0x180031fd0  mov     eax, 2
0x180031fd5  mov     ecx, r14d
0x180031fd8  mul     rcx
0x180031fdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031fe2  mov     r12, rax
0x180031fe5  cmovb   r12, r15
0x180031fe9  mov     rcx, r12; unsigned __int64
0x180031fec  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180031ff1  mov     rbx, rax
0x180031ff4  test    rax, rax
0x180031ff7  jz      short loc_18003200B
0x180031ff9  mov     r8, r12; Size
0x180031ffc  xor     edx, edx; Val
0x180031ffe  mov     rcx, rax; void *
0x180032001  call    memset_0
0x180032006  jmp     loc_180031F76
0x18003200b  mov     rbx, r13
0x18003200e  jmp     loc_180031F76
0x180032013  mov     rcx, [rbp+38h]; this
0x180032017  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x18003201e  mov     r9d, edi; char *
0x180032021  mov     edx, 2D7h; void *
0x180032026  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003202b  lea     rcx, [rbp+arg_0]
0x18003202f  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180032034  mov     eax, edi
0x180032036  jmp     loc_180031D34
0x18003203b  mov     ecx, 20000004h
0x180032040  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180032047  nop     dword ptr [rax+rax+00h]
0x18003204c  test    al, al
0x18003204e  jnz     loc_180031EBA
0x180032054  jmp     loc_180031DFB
0x180032059  mov     r8d, dword ptr [rbp+arg_0]; unsigned int
0x18003205d  lea     rdx, KeyName; "ZoneId"
0x180032064  lea     rcx, [rdi-28h]; this
0x180032068  call    ?_SetZoneId@CZoneIdentifier@@AEAAJPEBGK@Z; CZoneIdentifier::_SetZoneId(ushort const *,ulong)
0x18003206d  mov     ebx, eax
0x18003206f  test    eax, eax
0x180032071  jns     loc_180031F6F
0x180032077  mov     edx, 2EBh
0x18003207c  jmp     loc_180031D89
```
