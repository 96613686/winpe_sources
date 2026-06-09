# WINHTTP_DLL::Startup(void)

- ea: `0x180072cac`
- end: `0x180072eeb`
- name: `?Startup@WINHTTP_DLL@@QEAAKXZ`
- size: `575`
- prototype: `unsigned int __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180072a78`

## callees

- `0x18000f064`
- `0x180032c78`
- `0x18006e610`
- `0x180072cac`
- `0x18008da14`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800db6b0`
- `0x1800dbae4`
- `0x1800dc054`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180072cdb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180072cdb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180072e7e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180072e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e35`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180072e2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180072e2a`
- `WS2_32!__imp_WSAStartup` at `0x180072da2`
- `WS2_32!__imp_WSAStartup` at `0x180072da2`
- `WS2_32!__imp_WSACleanup` at `0x180072e75`
- `WS2_32!__imp_WSACleanup` at `0x180072e75`

## string_xrefs

- `0x180072cd2`: `winhttp.dll`
- `0x180072d6e`: `winhttp.dll`

## pseudocode

```c
__int64 __fastcall WINHTTP_DLL::Startup(char *pv)
{
  HMODULE Library; // rbp
  DWORD LastError; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  DWORD v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // r15d
  __int64 v14; // [rsp+20h] [rbp-1E8h]
  struct WSAData WSAData; // [rsp+30h] [rbp-1D8h] BYREF

  Library = LoadLibraryExA("winhttp.dll", 0, 0);
  if ( !Library )
  {
    LastError = GetLastError();
    v4 = SET_WINHTTP_ERROR_FROM_WIN32(LastError);
    v5 = v4;
    if ( g_fKirHttpBugFix2605 )
    {
      if ( (xmmword_180107A50 & 2) != 0 )
        WPP_SF_d(513, 19, WPP_458ceff5451f34372a71d1f745885a37_Traceguids, v4, v14);
    }
    else if ( (xmmword_180107A50 & 2) != 0 )
    {
      v6 = (unsigned int)InternetMapError(v4);
      WPP_SF_sd(513, 20, (unsigned int)WPP_458ceff5451f34372a71d1f745885a37_Traceguids, v6, v5);
    }
    return v5;
  }
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_s(1025, 21, WPP_458ceff5451f34372a71d1f745885a37_Traceguids, "winhttp.dll");
  memset_0(&WSAData, 0, sizeof(WSAData));
  v7 = WSAStartup(0x101u, &WSAData);
  v5 = v7;
  if ( v7 )
  {
    if ( g_fKirHttpBugFix2605 )
    {
      if ( (xmmword_180107A50 & 2) != 0 )
        WPP_SF_d(513, 22, WPP_458ceff5451f34372a71d1f745885a37_Traceguids, v7, v14);
    }
    else if ( (xmmword_180107A50 & 2) != 0 )
    {
      v8 = (unsigned int)InternetMapError(v7);
      WPP_SF_sd(513, 23, (unsigned int)WPP_458ceff5451f34372a71d1f745885a37_Traceguids, v8, v5);
    }
    v5 = 12004;
LABEL_20:
    FreeLibrary(Library);
    return v5;
  }
  (**(void (__fastcall ***)(char *))pv)(pv);
  ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)WINHTTP_DLL::_SafeTerminateDll, pv, 0);
  if ( !ThreadpoolTimer )
  {
    v10 = GetLastError();
    v11 = SET_WINHTTP_ERROR_FROM_WIN32(v10);
    v5 = v11;
    if ( (xmmword_180107A50 & 2) != 0 )
      WPP_SF_d(513, 24, WPP_458ceff5451f34372a71d1f745885a37_Traceguids, v11, v14);
    (*(void (__fastcall **)(char *))(*(_QWORD *)pv + 8LL))(pv);
    WSACleanup();
    goto LABEL_20;
  }
  v12 = 0;
  *((_QWORD *)pv + 4) = Library;
  *((_QWORD *)pv + 7) = ThreadpoolTimer;
  if ( !(unsigned int)WxIsPlatformXBox() )
  {
    CHttpPolicyExtensionLoader::Load(pv + 64);
    v12 = 1;
  }
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_d(1025, 25, WPP_458ceff5451f34372a71d1f745885a37_Traceguids, v12, v14);
  return v5;
}

```

## disassembly

```asm
0x180072cac  push    rbx
0x180072cae  push    rbp
0x180072caf  push    r14
0x180072cb1  push    r15
0x180072cb3  sub     rsp, 1E8h
0x180072cba  mov     rax, cs:__security_cookie
0x180072cc1  xor     rax, rsp
0x180072cc4  mov     [rsp+208h+var_38], rax
0x180072ccc  mov     r14, rcx
0x180072ccf  xor     r8d, r8d; dwFlags
0x180072cd2  lea     rcx, LibFileName; "winhttp.dll"
0x180072cd9  xor     edx, edx; hFile
0x180072cdb  call    cs:__imp_LoadLibraryExA
0x180072ce1  mov     rbp, rax
0x180072ce4  test    rax, rax
0x180072ce7  jnz     short loc_180072D60
0x180072ce9  call    cs:__imp_GetLastError
0x180072cef  mov     ecx, eax; unsigned int
0x180072cf1  call    ?SET_WINHTTP_ERROR_FROM_WIN32@@YAKK@Z; SET_WINHTTP_ERROR_FROM_WIN32(ulong)
0x180072cf6  cmp     cs:g_fKirHttpBugFix2605, bpl
0x180072cfd  mov     ebx, eax
0x180072cff  jz      short loc_180072D2A
0x180072d01  test    byte ptr cs:xmmword_180107A50, 2
0x180072d08  jz      loc_180072ECB
0x180072d0e  lea     edx, [rbp+13h]
0x180072d11  mov     ecx, 201h
0x180072d16  mov     r9d, eax
0x180072d19  lea     r8, WPP_458ceff5451f34372a71d1f745885a37_Traceguids
0x180072d20  call    WPP_SF_d
0x180072d25  jmp     loc_180072ECB
0x180072d2a  test    byte ptr cs:xmmword_180107A50, 2
0x180072d31  jz      loc_180072ECB
0x180072d37  mov     ecx, ebx; unsigned int
0x180072d39  call    ?InternetMapError@@YAPEADK@Z; InternetMapError(ulong)
0x180072d3e  mov     r9, rax
0x180072d41  mov     [rsp+208h+var_1E8], ebx
0x180072d45  mov     edx, 14h
0x180072d4a  lea     r8, WPP_458ceff5451f34372a71d1f745885a37_Traceguids
0x180072d51  mov     ecx, 201h
0x180072d56  call    WPP_SF_sd
0x180072d5b  jmp     loc_180072ECB
0x180072d60  test    byte ptr cs:xmmword_180107A60, 2
0x180072d67  jz      short loc_180072D86
0x180072d69  mov     edx, 15h
0x180072d6e  lea     r9, LibFileName; "winhttp.dll"
0x180072d75  mov     ecx, 401h
0x180072d7a  lea     r8, WPP_458ceff5451f34372a71d1f745885a37_Traceguids
0x180072d81  call    WPP_SF_s
0x180072d86  xor     edx, edx; Val
0x180072d88  lea     rcx, [rsp+208h+WSAData]; void *
0x180072d8d  mov     r8d, 198h; Size
0x180072d93  call    memset_0
0x180072d98  mov     ecx, 101h; wVersionRequested
0x180072d9d  lea     rdx, [rsp+208h+WSAData]; lpWSAData
0x180072da2  call    cs:__imp_WSAStartup
0x180072da8  mov     ebx, eax
0x180072daa  test    eax, eax
0x180072dac  jz      short loc_180072E0F
0x180072dae  cmp     cs:g_fKirHttpBugFix2605, 0
0x180072db5  jz      short loc_180072DDB
0x180072db7  test    byte ptr cs:xmmword_180107A50, 2
0x180072dbe  jz      short loc_180072E08
0x180072dc0  mov     edx, 16h
0x180072dc5  lea     r8, WPP_458ceff5451f34372a71d1f745885a37_Traceguids
0x180072dcc  mov     ecx, 201h
0x180072dd1  mov     r9d, eax
0x180072dd4  call    WPP_SF_d
0x180072dd9  jmp     short loc_180072E08
0x180072ddb  test    byte ptr cs:xmmword_180107A50, 2
0x180072de2  jz      short loc_180072E08
0x180072de4  mov     ecx, ebx; unsigned int
0x180072de6  call    ?InternetMapError@@YAPEADK@Z; InternetMapError(ulong)
0x180072deb  mov     r9, rax
0x180072dee  mov     [rsp+208h+var_1E8], ebx
0x180072df2  mov     edx, 17h
0x180072df7  lea     r8, WPP_458ceff5451f34372a71d1f745885a37_Traceguids
0x180072dfe  mov     ecx, 201h
0x180072e03  call    WPP_SF_sd
0x180072e08  mov     ebx, 2EE4h
0x180072e0d  jmp     short loc_180072E7B
0x180072e0f  mov     rax, [r14]
0x180072e12  mov     rcx, r14
0x180072e15  mov     rax, [rax]
0x180072e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e1d  xor     r8d, r8d; pcbe
0x180072e20  lea     rcx, ?_SafeTerminateDll@WINHTTP_DLL@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180072e27  mov     rdx, r14; pv
0x180072e2a  call    cs:__imp_CreateThreadpoolTimer
0x180072e30  test    rax, rax
0x180072e33  jnz     short loc_180072E86
0x180072e35  call    cs:__imp_GetLastError
0x180072e3b  mov     ecx, eax; unsigned int
0x180072e3d  call    ?SET_WINHTTP_ERROR_FROM_WIN32@@YAKK@Z; SET_WINHTTP_ERROR_FROM_WIN32(ulong)
0x180072e42  mov     ebx, eax
0x180072e44  test    byte ptr cs:xmmword_180107A50, 2
0x180072e4b  jz      short loc_180072E66
0x180072e4d  mov     edx, 18h
0x180072e52  lea     r8, WPP_458ceff5451f34372a71d1f745885a37_Traceguids
0x180072e59  mov     ecx, 201h
0x180072e5e  mov     r9d, eax
0x180072e61  call    WPP_SF_d
0x180072e66  mov     rax, [r14]
0x180072e69  mov     rcx, r14
0x180072e6c  mov     rax, [rax+8]
0x180072e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e75  call    cs:__imp_WSACleanup
0x180072e7b  mov     rcx, rbp; hLibModule
0x180072e7e  call    cs:__imp_FreeLibrary
0x180072e84  jmp     short loc_180072ECB
0x180072e86  xor     r15d, r15d
0x180072e89  mov     [r14+20h], rbp
0x180072e8d  mov     [r14+38h], rax
0x180072e91  call    WxIsPlatformXBox
0x180072e96  test    eax, eax
0x180072e98  jnz     short loc_180072EA9
0x180072e9a  lea     rcx, [r14+40h]
0x180072e9e  call    ?Load@CHttpPolicyExtensionLoader@@QEAAXW4_HTTP_POLICY_EXTENSION_LOADER_TYPE@@H@Z; CHttpPolicyExtensionLoader::Load(_HTTP_POLICY_EXTENSION_LOADER_TYPE,int)
0x180072ea3  mov     r15d, 1
0x180072ea9  test    byte ptr cs:xmmword_180107A60, 2
0x180072eb0  jz      short loc_180072ECB
0x180072eb2  mov     edx, 19h
0x180072eb7  lea     r8, WPP_458ceff5451f34372a71d1f745885a37_Traceguids
0x180072ebe  mov     ecx, 401h
0x180072ec3  mov     r9d, r15d
0x180072ec6  call    WPP_SF_d
0x180072ecb  mov     eax, ebx
0x180072ecd  mov     rcx, [rsp+208h+var_38]
0x180072ed5  xor     rcx, rsp; StackCookie
0x180072ed8  call    __security_check_cookie
0x180072edd  add     rsp, 1E8h
0x180072ee4  pop     r15
0x180072ee6  pop     r14
0x180072ee8  pop     rbp
0x180072ee9  pop     rbx
0x180072eea  retn
```
