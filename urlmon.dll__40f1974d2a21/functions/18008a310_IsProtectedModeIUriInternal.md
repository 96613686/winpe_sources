# IsProtectedModeIUriInternal

- ea: `0x18008a310`
- end: `0x18008a5a8`
- name: `IsProtectedModeIUriInternal`
- size: `664`
- prototype: `__int64 __fastcall(struct IUri *, int, int, _DWORD *)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180089c9c`
- `0x1800f4940`
- `0x1800f4ad0`

## callees

- `0x1800123e0`
- `0x18002d5dc`
- `0x18003b010`
- `0x180047740`
- `0x18006bd0c`
- `0x18008a310`
- `0x1800a856c`
- `0x1800f4198`
- `0x1800f4350`
- `0x1800f4498`
- `0x1800f4610`
- `0x1800f4a00`
- `0x1800f4c20`
- `0x18011baa0`
- `0x18011bb60`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x18008a408`
- `iertutil!CreateUri` at `0x18008a408`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18008a471`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18008a471`
- `iertutil!__imp_?IsProtectedModeEnabled@@YAHXZ` at `0x18008a467`
- `iertutil!__imp_?IsProtectedModeEnabled@@YAHXZ` at `0x18008a467`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x18008a4b8`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x18008a4b8`
- `iertutil!__imp_?IsBrowserProcess@@YAHXZ` at `0x18008a505`
- `iertutil!__imp_?IsBrowserProcess@@YAHXZ` at `0x18008a505`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a4ed`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a4ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a54a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a54a`
- `WININET!InternetInitializeAutoProxyDll` at `0x18008a4de`
- `WININET!InternetInitializeAutoProxyDll` at `0x18008a51e`
- `WININET!InternetInitializeAutoProxyDll` at `0x18008a4de`
- `WININET!InternetInitializeAutoProxyDll` at `0x18008a51e`

## string_xrefs

- `0x18008a361`: `onecoreuap\inetcore\urlmon\utils\extension.cxx`

## pseudocode

```c
__int64 __fastcall IsProtectedModeIUriInternal(struct IUri *a1, int a2, int a3, _DWORD *a4)
{
  int v9; // r12d
  int v10; // ebx
  BOOL v11; // edi
  DWORD v12; // eax
  struct IUri *v13; // rcx
  int v14; // eax
  int v15; // edx
  int v16; // edx
  int v17; // eax
  int v18; // edx
  signed int LastError; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  IUri *ppURI; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pwzURI[2088]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10E8h] [rbp+FE8h]

  if ( (unsigned int)IsSpartanApp() )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x380,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\utils\\extension.cxx",
      (const char *)0x80004001LL,
      v20);
  ppURI = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a1 )
    return 2147500037LL;
  v9 = 0;
  v10 = -2147467259;
  v11 = 1;
  if ( IsAboutIUri(a1) )
  {
    v22 = 0;
    if ( !(unsigned int)CoInternetParseIUriInternal((_DWORD)a1, 1, 0, (unsigned int)pwzURI, 2084, (__int64)&v22, 0, 0) )
    {
      v12 = HelperAddUriDefaultFlags(0x3002B80u, 0);
      v9 = 1;
      v10 = CreateUri(pwzURI, v12, 0, &ppURI);
      if ( !(unsigned int)StrCmpIIW(pwzURI, L"about:protectedmodeoff") )
        a2 = 0;
    }
  }
  else if ( IsResIUri(a1) )
  {
    a2 = 0;
  }
  v13 = ppURI;
  if ( !ppURI )
  {
    v13 = a1;
    ppURI = a1;
  }
  if ( !v9 || v10 >= 0 )
  {
    if ( !a2 && (unsigned int)IsProtectedModeNeutralIUri(v13) )
    {
      if ( IsProtectedModeEnabled() )
      {
        v14 = IsProtectedModeProcess();
        if ( v14 < 0 )
          v11 = v14;
        else
          v11 = v14 == 0;
      }
      v10 = !v11;
      goto LABEL_41;
    }
    if ( (int)EnsureSecurityManager() >= 0 )
      v10 = IsLRIEnabledforUri((_DWORD)ppURI, v15, 1, a3, (__int64)a4) == 0;
    if ( IsElevatedProcess() )
      goto LABEL_41;
    if ( !v10 )
    {
      if ( !(unsigned int)SkipBrokerCheckForURL() || InternetInitializeAutoProxyDll(0xCu) )
      {
LABEL_41:
        if ( v9 )
          ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
        return (unsigned int)v10;
      }
      if ( (unsigned __int8)IEConfiguration_GetBool(536870914) )
      {
        v10 = AskBrokerProtectedModeUrl(ppURI);
      }
      else
      {
        if ( IsBrowserProcess() )
        {
          v17 = IsLRIEnabledforUri((_DWORD)ppURI, v16, 0, a3, (__int64)a4);
        }
        else
        {
          if ( !InternetInitializeAutoProxyDll(2u) )
          {
            LastError = GetLastError();
            v10 = LastError;
            if ( LastError > 0 )
              v10 = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_39;
          }
          v17 = IsLRIEnabledforUri((_DWORD)ppURI, v18, 0, 1, 0);
        }
        v10 = v17 == 0;
      }
    }
LABEL_39:
    if ( v10 < 0 )
      v10 = 0;
    goto LABEL_41;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008a310  mov     [rsp-8+arg_8], rbx
0x18008a315  push    rbp
0x18008a316  push    rsi
0x18008a317  push    rdi
0x18008a318  push    r12
0x18008a31a  push    r13
0x18008a31c  push    r14
0x18008a31e  push    r15
0x18008a320  lea     rbp, [rsp-0FB0h]
0x18008a328  mov     eax, 10B0h
0x18008a32d  call    _alloca_probe
0x18008a332  sub     rsp, rax
0x18008a335  mov     rax, cs:__security_cookie
0x18008a33c  xor     rax, rsp
0x18008a33f  mov     [rbp+0FE0h+var_40], rax
0x18008a346  mov     r15, r9
0x18008a349  mov     r13d, r8d
0x18008a34c  mov     esi, edx
0x18008a34e  mov     r14, rcx
0x18008a351  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x18008a356  test    eax, eax
0x18008a358  jz      short loc_18008A379
0x18008a35a  mov     rcx, [rbp+0FE8h]; this
0x18008a361  lea     r8, aOnecoreuapInet_18; "onecoreuap\\inetcore\\urlmon\\utils\\ex"...
0x18008a368  mov     r9d, 80004001h; char *
0x18008a36e  mov     edx, 380h; void *
0x18008a373  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18008a379  mov     [rsp+10E0h+ppURI], 0
0x18008a382  test    r15, r15
0x18008a385  jz      short loc_18008A38E
0x18008a387  mov     dword ptr [r15], 0
0x18008a38e  test    r14, r14
0x18008a391  jnz     short loc_18008A39D
0x18008a393  mov     eax, 80004005h
0x18008a398  jmp     loc_18008A57E
0x18008a39d  mov     rcx, r14; struct IUri *
0x18008a3a0  xor     r12d, r12d
0x18008a3a3  mov     ebx, 80004005h
0x18008a3a8  call    ?IsAboutIUri@@YAHPEAUIUri@@@Z; IsAboutIUri(IUri *)
0x18008a3ad  xor     ecx, ecx
0x18008a3af  lea     edi, [r12+1]
0x18008a3b4  test    eax, eax
0x18008a3b6  jz      short loc_18008A42C
0x18008a3b8  mov     [rsp+10E0h+var_10A8], ecx
0x18008a3bc  lea     rax, [rsp+10E0h+var_1098]
0x18008a3c1  mov     [rsp+10E0h+var_10B0], rcx
0x18008a3c6  lea     r9, [rsp+10E0h+pwzURI]
0x18008a3cb  mov     [rsp+10E0h+var_1098], ecx
0x18008a3cf  xor     r8d, r8d
0x18008a3d2  mov     [rsp+10E0h+var_10B8], rax
0x18008a3d7  mov     rcx, r14
0x18008a3da  mov     edx, edi
0x18008a3dc  mov     dword ptr [rsp+10E0h+var_10C0], 824h
0x18008a3e4  call    CoInternetParseIUriInternal
0x18008a3e9  test    eax, eax
0x18008a3eb  jnz     short loc_18008A43B
0x18008a3ed  xor     edx, edx; unsigned int
0x18008a3ef  mov     ecx, 3002B80h; unsigned int
0x18008a3f4  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18008a3f9  mov     edx, eax; dwFlags
0x18008a3fb  lea     rcx, [rsp+10E0h+pwzURI]; pwzURI
0x18008a400  lea     r9, [rsp+10E0h+ppURI]; ppURI
0x18008a405  xor     r8d, r8d; dwReserved
0x18008a408  call    cs:__imp_CreateUri
0x18008a40e  lea     rdx, aAboutProtected; "about:protectedmodeoff"
0x18008a415  mov     r12d, edi
0x18008a418  lea     rcx, [rsp+10E0h+pwzURI]; lpString1
0x18008a41d  mov     ebx, eax
0x18008a41f  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x18008a424  test    eax, eax
0x18008a426  jnz     short loc_18008A43B
0x18008a428  xor     esi, esi
0x18008a42a  jmp     short loc_18008A43B
0x18008a42c  mov     rcx, r14; struct IUri *
0x18008a42f  call    ?IsResIUri@@YAHPEAUIUri@@@Z; IsResIUri(IUri *)
0x18008a434  xor     ecx, ecx
0x18008a436  test    eax, eax
0x18008a438  cmovnz  esi, ecx
0x18008a43b  mov     rcx, [rsp+10E0h+ppURI]
0x18008a440  test    rcx, rcx
0x18008a443  jnz     short loc_18008A44D
0x18008a445  mov     rcx, r14; struct IUri *
0x18008a448  mov     [rsp+10E0h+ppURI], rcx
0x18008a44d  test    r12d, r12d
0x18008a450  jz      short loc_18008A45A
0x18008a452  test    ebx, ebx
0x18008a454  js      loc_18008A57C
0x18008a45a  test    esi, esi
0x18008a45c  jnz     short loc_18008A493
0x18008a45e  call    ?IsProtectedModeNeutralIUri@@YAHPEAUIUri@@@Z; IsProtectedModeNeutralIUri(IUri *)
0x18008a463  test    eax, eax
0x18008a465  jz      short loc_18008A493
0x18008a467  call    cs:__imp_?IsProtectedModeEnabled@@YAHXZ; IsProtectedModeEnabled(void)
0x18008a46d  test    eax, eax
0x18008a46f  jz      short loc_18008A487
0x18008a471  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x18008a477  test    eax, eax
0x18008a479  js      short loc_18008A485
0x18008a47b  xor     edi, edi
0x18008a47d  test    eax, eax
0x18008a47f  setz    dil
0x18008a483  jmp     short loc_18008A487
0x18008a485  mov     edi, eax
0x18008a487  xor     ebx, ebx
0x18008a489  test    edi, edi
0x18008a48b  setz    bl
0x18008a48e  jmp     loc_18008A566
0x18008a493  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x18008a498  test    eax, eax
0x18008a49a  js      short loc_18008A4B8
0x18008a49c  mov     rcx, [rsp+10E0h+ppURI]
0x18008a4a1  mov     r9d, r13d
0x18008a4a4  mov     r8d, edi
0x18008a4a7  mov     [rsp+10E0h+var_10C0], r15
0x18008a4ac  call    IsLRIEnabledforUri
0x18008a4b1  xor     ebx, ebx
0x18008a4b3  test    eax, eax
0x18008a4b5  setz    bl
0x18008a4b8  call    cs:__imp_?IsElevatedProcess@@YAHXZ; IsElevatedProcess(void)
0x18008a4be  test    eax, eax
0x18008a4c0  jnz     loc_18008A566
0x18008a4c6  test    ebx, ebx
0x18008a4c8  jnz     loc_18008A55F
0x18008a4ce  call    SkipBrokerCheckForURL
0x18008a4d3  test    eax, eax
0x18008a4d5  jz      loc_18008A566
0x18008a4db  lea     ecx, [rbx+0Ch]; dwReserved
0x18008a4de  call    cs:__imp_InternetInitializeAutoProxyDll
0x18008a4e4  test    eax, eax
0x18008a4e6  jnz     short loc_18008A566
0x18008a4e8  mov     ecx, 20000002h
0x18008a4ed  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008a4f3  test    al, al
0x18008a4f5  jz      short loc_18008A505
0x18008a4f7  mov     rcx, [rsp+10E0h+ppURI]; struct IUri *
0x18008a4fc  call    ?AskBrokerProtectedModeUrl@@YAJPEAUIUri@@@Z; AskBrokerProtectedModeUrl(IUri *)
0x18008a501  mov     ebx, eax
0x18008a503  jmp     short loc_18008A55F
0x18008a505  call    cs:__imp_?IsBrowserProcess@@YAHXZ; IsBrowserProcess(void)
0x18008a50b  test    eax, eax
0x18008a50d  jz      short loc_18008A519
0x18008a50f  mov     [rsp+10E0h+var_10C0], r15
0x18008a514  mov     r9d, r13d
0x18008a517  jmp     short loc_18008A534
0x18008a519  mov     ecx, 2; dwReserved
0x18008a51e  call    cs:__imp_InternetInitializeAutoProxyDll
0x18008a524  test    eax, eax
0x18008a526  jz      short loc_18008A54A
0x18008a528  mov     [rsp+10E0h+var_10C0], 0
0x18008a531  mov     r9d, edi
0x18008a534  mov     rcx, [rsp+10E0h+ppURI]
0x18008a539  xor     r8d, r8d
0x18008a53c  call    IsLRIEnabledforUri
0x18008a541  xor     ebx, ebx
0x18008a543  test    eax, eax
0x18008a545  setz    bl
0x18008a548  jmp     short loc_18008A55F
0x18008a54a  call    cs:__imp_GetLastError
0x18008a550  mov     ebx, eax
0x18008a552  test    eax, eax
0x18008a554  jle     short loc_18008A55F
0x18008a556  movzx   ebx, ax
0x18008a559  or      ebx, 80070000h
0x18008a55f  xor     eax, eax
0x18008a561  test    ebx, ebx
0x18008a563  cmovs   ebx, eax
0x18008a566  test    r12d, r12d
0x18008a569  jz      short loc_18008A57C
0x18008a56b  mov     rcx, [rsp+10E0h+ppURI]
0x18008a570  mov     rax, [rcx]
0x18008a573  mov     rax, [rax+10h]
0x18008a577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a57c  mov     eax, ebx
0x18008a57e  mov     rcx, [rbp+0FE0h+var_40]
0x18008a585  xor     rcx, rsp; StackCookie
0x18008a588  call    __security_check_cookie
0x18008a58d  mov     rbx, [rsp+10E0h+arg_8]
0x18008a595  add     rsp, 10B0h
0x18008a59c  pop     r15
0x18008a59e  pop     r14
0x18008a5a0  pop     r13
0x18008a5a2  pop     r12
0x18008a5a4  pop     rdi
0x18008a5a5  pop     rsi
0x18008a5a6  pop     rbp
0x18008a5a7  retn
```
