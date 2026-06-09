# IsProtectedModeIUriInternal

- ea: `0x180090068`
- end: `0x18009033b`
- name: `IsProtectedModeIUriInternal`
- size: `723`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008f954`
- `0x1800feea0`
- `0x1800ff040`

## callees

- `0x1800124b0`
- `0x18001a6e0`
- `0x180033858`
- `0x18003e100`
- `0x180070adc`
- `0x180090068`
- `0x1800af5b0`
- `0x1800fe6b8`
- `0x1800fe884`
- `0x1800fe9d0`
- `0x1800feb60`
- `0x1800fef70`
- `0x1800ff1b0`
- `0x180128660`
- `0x180128720`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x180090160`
- `iertutil!CreateUri` at `0x180090160`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800901d5`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800901d5`
- `iertutil!__imp_?IsProtectedModeEnabled@@YAHXZ` at `0x1800901c5`
- `iertutil!__imp_?IsProtectedModeEnabled@@YAHXZ` at `0x1800901c5`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x180090222`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x180090222`
- `iertutil!__imp_?IsBrowserProcess@@YAHXZ` at `0x180090285`
- `iertutil!__imp_?IsBrowserProcess@@YAHXZ` at `0x180090285`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180090267`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180090267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800902d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800902d6`
- `WININET!InternetInitializeAutoProxyDll` at `0x18009024e`
- `WININET!InternetInitializeAutoProxyDll` at `0x1800902a4`
- `WININET!InternetInitializeAutoProxyDll` at `0x18009024e`
- `WININET!InternetInitializeAutoProxyDll` at `0x1800902a4`

## string_xrefs

- `0x1800900b9`: `onecoreuap\inetcore\urlmon\utils\extension.cxx`

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
0x180090068  mov     [rsp-8+arg_8], rbx
0x18009006d  push    rbp
0x18009006e  push    rsi
0x18009006f  push    rdi
0x180090070  push    r12
0x180090072  push    r13
0x180090074  push    r14
0x180090076  push    r15
0x180090078  lea     rbp, [rsp-0FB0h]
0x180090080  mov     eax, 10B0h
0x180090085  call    _alloca_probe
0x18009008a  sub     rsp, rax
0x18009008d  mov     rax, cs:__security_cookie
0x180090094  xor     rax, rsp
0x180090097  mov     [rbp+0FE0h+var_40], rax
0x18009009e  mov     r15, r9
0x1800900a1  mov     r13d, r8d
0x1800900a4  mov     esi, edx
0x1800900a6  mov     r14, rcx
0x1800900a9  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x1800900ae  test    eax, eax
0x1800900b0  jz      short loc_1800900D1
0x1800900b2  mov     rcx, [rbp+0FE8h]; this
0x1800900b9  lea     r8, aOnecoreuapInet_18; "onecoreuap\\inetcore\\urlmon\\utils\\ex"...
0x1800900c0  mov     r9d, 80004001h; char *
0x1800900c6  mov     edx, 380h; void *
0x1800900cb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800900d1  mov     [rsp+10E0h+ppURI], 0
0x1800900da  test    r15, r15
0x1800900dd  jz      short loc_1800900E6
0x1800900df  mov     dword ptr [r15], 0
0x1800900e6  test    r14, r14
0x1800900e9  jnz     short loc_1800900F5
0x1800900eb  mov     eax, 80004005h
0x1800900f0  jmp     loc_180090310
0x1800900f5  mov     rcx, r14; struct IUri *
0x1800900f8  xor     r12d, r12d
0x1800900fb  mov     ebx, 80004005h
0x180090100  call    ?IsAboutIUri@@YAHPEAUIUri@@@Z; IsAboutIUri(IUri *)
0x180090105  xor     ecx, ecx
0x180090107  lea     edi, [r12+1]
0x18009010c  test    eax, eax
0x18009010e  jz      short loc_18009018A
0x180090110  mov     [rsp+10E0h+var_10A8], ecx
0x180090114  lea     rax, [rsp+10E0h+var_1098]
0x180090119  mov     [rsp+10E0h+var_10B0], rcx
0x18009011e  lea     r9, [rsp+10E0h+pwzURI]
0x180090123  mov     [rsp+10E0h+var_1098], ecx
0x180090127  xor     r8d, r8d
0x18009012a  mov     [rsp+10E0h+var_10B8], rax
0x18009012f  mov     rcx, r14
0x180090132  mov     edx, edi
0x180090134  mov     dword ptr [rsp+10E0h+var_10C0], 824h
0x18009013c  call    CoInternetParseIUriInternal
0x180090141  test    eax, eax
0x180090143  jnz     short loc_180090199
0x180090145  xor     edx, edx; unsigned int
0x180090147  mov     ecx, 3002B80h; unsigned int
0x18009014c  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x180090151  mov     edx, eax; dwFlags
0x180090153  lea     rcx, [rsp+10E0h+pwzURI]; pwzURI
0x180090158  lea     r9, [rsp+10E0h+ppURI]; ppURI
0x18009015d  xor     r8d, r8d; dwReserved
0x180090160  call    cs:__imp_CreateUri
0x180090167  nop     dword ptr [rax+rax+00h]
0x18009016c  lea     rdx, aAboutProtected; "about:protectedmodeoff"
0x180090173  mov     r12d, edi
0x180090176  lea     rcx, [rsp+10E0h+pwzURI]; lpString1
0x18009017b  mov     ebx, eax
0x18009017d  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x180090182  test    eax, eax
0x180090184  jnz     short loc_180090199
0x180090186  xor     esi, esi
0x180090188  jmp     short loc_180090199
0x18009018a  mov     rcx, r14; struct IUri *
0x18009018d  call    ?IsResIUri@@YAHPEAUIUri@@@Z; IsResIUri(IUri *)
0x180090192  xor     ecx, ecx
0x180090194  test    eax, eax
0x180090196  cmovnz  esi, ecx
0x180090199  mov     rcx, [rsp+10E0h+ppURI]
0x18009019e  test    rcx, rcx
0x1800901a1  jnz     short loc_1800901AB
0x1800901a3  mov     rcx, r14; struct IUri *
0x1800901a6  mov     [rsp+10E0h+ppURI], rcx
0x1800901ab  test    r12d, r12d
0x1800901ae  jz      short loc_1800901B8
0x1800901b0  test    ebx, ebx
0x1800901b2  js      loc_18009030E
0x1800901b8  test    esi, esi
0x1800901ba  jnz     short loc_1800901FD
0x1800901bc  call    ?IsProtectedModeNeutralIUri@@YAHPEAUIUri@@@Z; IsProtectedModeNeutralIUri(IUri *)
0x1800901c1  test    eax, eax
0x1800901c3  jz      short loc_1800901FD
0x1800901c5  call    cs:__imp_?IsProtectedModeEnabled@@YAHXZ; IsProtectedModeEnabled(void)
0x1800901cc  nop     dword ptr [rax+rax+00h]
0x1800901d1  test    eax, eax
0x1800901d3  jz      short loc_1800901F1
0x1800901d5  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1800901dc  nop     dword ptr [rax+rax+00h]
0x1800901e1  test    eax, eax
0x1800901e3  js      short loc_1800901EF
0x1800901e5  xor     edi, edi
0x1800901e7  test    eax, eax
0x1800901e9  setz    dil
0x1800901ed  jmp     short loc_1800901F1
0x1800901ef  mov     edi, eax
0x1800901f1  xor     ebx, ebx
0x1800901f3  test    edi, edi
0x1800901f5  setz    bl
0x1800901f8  jmp     loc_1800902F8
0x1800901fd  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x180090202  test    eax, eax
0x180090204  js      short loc_180090222
0x180090206  mov     rcx, [rsp+10E0h+ppURI]
0x18009020b  mov     r9d, r13d
0x18009020e  mov     r8d, edi
0x180090211  mov     [rsp+10E0h+var_10C0], r15
0x180090216  call    IsLRIEnabledforUri
0x18009021b  xor     ebx, ebx
0x18009021d  test    eax, eax
0x18009021f  setz    bl
0x180090222  call    cs:__imp_?IsElevatedProcess@@YAHXZ; IsElevatedProcess(void)
0x180090229  nop     dword ptr [rax+rax+00h]
0x18009022e  test    eax, eax
0x180090230  jnz     loc_1800902F8
0x180090236  test    ebx, ebx
0x180090238  jnz     loc_1800902F1
0x18009023e  call    SkipBrokerCheckForURL
0x180090243  test    eax, eax
0x180090245  jz      loc_1800902F8
0x18009024b  lea     ecx, [rbx+0Ch]; dwReserved
0x18009024e  call    cs:__imp_InternetInitializeAutoProxyDll
0x180090255  nop     dword ptr [rax+rax+00h]
0x18009025a  test    eax, eax
0x18009025c  jnz     loc_1800902F8
0x180090262  mov     ecx, 20000002h
0x180090267  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18009026e  nop     dword ptr [rax+rax+00h]
0x180090273  test    al, al
0x180090275  jz      short loc_180090285
0x180090277  mov     rcx, [rsp+10E0h+ppURI]; struct IUri *
0x18009027c  call    ?AskBrokerProtectedModeUrl@@YAJPEAUIUri@@@Z; AskBrokerProtectedModeUrl(IUri *)
0x180090281  mov     ebx, eax
0x180090283  jmp     short loc_1800902F1
0x180090285  call    cs:__imp_?IsBrowserProcess@@YAHXZ; IsBrowserProcess(void)
0x18009028c  nop     dword ptr [rax+rax+00h]
0x180090291  test    eax, eax
0x180090293  jz      short loc_18009029F
0x180090295  mov     [rsp+10E0h+var_10C0], r15
0x18009029a  mov     r9d, r13d
0x18009029d  jmp     short loc_1800902C0
0x18009029f  mov     ecx, 2; dwReserved
0x1800902a4  call    cs:__imp_InternetInitializeAutoProxyDll
0x1800902ab  nop     dword ptr [rax+rax+00h]
0x1800902b0  test    eax, eax
0x1800902b2  jz      short loc_1800902D6
0x1800902b4  mov     [rsp+10E0h+var_10C0], 0
0x1800902bd  mov     r9d, edi
0x1800902c0  mov     rcx, [rsp+10E0h+ppURI]
0x1800902c5  xor     r8d, r8d
0x1800902c8  call    IsLRIEnabledforUri
0x1800902cd  xor     ebx, ebx
0x1800902cf  test    eax, eax
0x1800902d1  setz    bl
0x1800902d4  jmp     short loc_1800902F1
0x1800902d6  call    cs:__imp_GetLastError
0x1800902dd  nop     dword ptr [rax+rax+00h]
0x1800902e2  mov     ebx, eax
0x1800902e4  test    eax, eax
0x1800902e6  jle     short loc_1800902F1
0x1800902e8  movzx   ebx, ax
0x1800902eb  or      ebx, 80070000h
0x1800902f1  xor     eax, eax
0x1800902f3  test    ebx, ebx
0x1800902f5  cmovs   ebx, eax
0x1800902f8  test    r12d, r12d
0x1800902fb  jz      short loc_18009030E
0x1800902fd  mov     rcx, [rsp+10E0h+ppURI]
0x180090302  mov     rax, [rcx]
0x180090305  mov     rax, [rax+10h]
0x180090309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009030e  mov     eax, ebx
0x180090310  mov     rcx, [rbp+0FE0h+var_40]
0x180090317  xor     rcx, rsp; StackCookie
0x18009031a  call    __security_check_cookie
0x18009031f  mov     rbx, [rsp+10E0h+arg_8]
0x180090327  add     rsp, 10B0h
0x18009032e  pop     r15
0x180090330  pop     r14
0x180090332  pop     r13
0x180090334  pop     r12
0x180090336  pop     rdi
0x180090337  pop     rsi
0x180090338  pop     rbp
0x180090339  retn
```
