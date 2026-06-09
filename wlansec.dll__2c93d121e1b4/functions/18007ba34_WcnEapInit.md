# WcnEapInit

- ea: `0x18007ba34`
- end: `0x18007bd70`
- name: `WcnEapInit`
- size: `828`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18007a2e4`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180043a30`
- `0x18004456c`
- `0x18007ba34`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007bc26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007bc26`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007bcfe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007bcfe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007bbdd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007bbdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bb90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bbf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bc3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bb90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bbf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bc3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007bb48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007bb48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007bd1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007bd1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007bae4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007bae4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007bb80`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007bb80`

## string_xrefs

- `0x18007bad6`: `SYSTEM\CurrentControlSet\Services\Wlansvc\Parameters\OneXAuthenticator`
- `0x18007bc1c`: `WcnEapPluginGetInfo`
- `0x18007bbc8`: `WcnEapAuthProxy.dll`

## pseudocode

```c
__int64 WcnEapInit()
{
  unsigned int v0; // eax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  DWORD LastError; // eax
  DWORD v4; // ebx
  WCHAR *v5; // rcx
  HMODULE Library; // rax
  int v7; // edi
  DWORD v8; // eax
  DWORD v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  FARPROC ProcAddress; // rax
  DWORD v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp+150h] BYREF

  hKey = 0;
  cbData = 260;
  memset_0(Data, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b54c9f5e9d683c400514a20e8b347731_Traceguids);
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\Wlansvc\\Parameters\\OneXAuthenticator",
         0,
         1u,
         &hKey);
  if ( v0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v2 = 11;
LABEL_8:
    WPP_SF_d(v1[2], v2, WPP_b54c9f5e9d683c400514a20e8b347731_Traceguids, v0);
LABEL_18:
    v5 = L"WcnEapAuthProxy.dll";
    goto LABEL_20;
  }
  v0 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData);
  if ( v0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v2 = 12;
    goto LABEL_8;
  }
  if ( !ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b54c9f5e9d683c400514a20e8b347731_Traceguids, LastError);
    if ( v4 )
      goto LABEL_18;
  }
  v5 = Dst;
LABEL_20:
  Library = LoadLibraryExW(v5, 0, 0);
  hLibModule = Library;
  if ( !Library )
  {
    v7 = 0;
    v8 = GetLastError();
    v9 = v8;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 14;
LABEL_28:
      WPP_SF_d(v10[2], v11, WPP_b54c9f5e9d683c400514a20e8b347731_Traceguids, v8);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_29;
    }
    goto LABEL_29;
  }
  ProcAddress = GetProcAddress(Library, "WcnEapPluginGetInfo");
  if ( ProcAddress )
  {
    v13 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(1, &qword_1800BB5A8);
    v9 = v13;
    if ( v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_41;
      v15 = 16;
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(__int64 *))qword_1800BB5A8)(&qword_1800BB5B0);
      v9 = v13;
      if ( !v13 )
      {
LABEL_42:
        v10 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_43;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_41:
        FreeLibrary(hLibModule);
        goto LABEL_42;
      }
      v15 = 17;
    }
    WPP_SF_d(v14[2], v15, WPP_b54c9f5e9d683c400514a20e8b347731_Traceguids, v13);
    goto LABEL_41;
  }
  v7 = 1;
  v8 = GetLastError();
  v9 = v8;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v11 = 15;
    goto LABEL_28;
  }
LABEL_29:
  if ( v9 && v7 )
    goto LABEL_41;
LABEL_43:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    WPP_SF_d(v10[2], 18, WPP_b54c9f5e9d683c400514a20e8b347731_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18007ba34  push    rbp
0x18007ba36  push    rbx
0x18007ba37  push    rsi
0x18007ba38  push    rdi
0x18007ba39  push    r15
0x18007ba3b  lea     rbp, [rsp-370h]
0x18007ba43  sub     rsp, 470h
0x18007ba4a  mov     rax, cs:__security_cookie
0x18007ba51  xor     rax, rsp
0x18007ba54  mov     [rbp+390h+var_30], rax
0x18007ba5b  mov     ebx, 208h
0x18007ba60  mov     [rsp+490h+hKey], 0
0x18007ba69  mov     edi, 104h
0x18007ba6e  lea     rcx, [rsp+490h+Data]; void *
0x18007ba73  mov     r8d, ebx; Size
0x18007ba76  mov     [rsp+490h+cbData], edi
0x18007ba7a  xor     edx, edx; Val
0x18007ba7c  call    memset_0
0x18007ba81  mov     r8d, ebx; Size
0x18007ba84  lea     rcx, [rbp+390h+Dst]; void *
0x18007ba8b  xor     edx, edx; Val
0x18007ba8d  call    memset_0
0x18007ba92  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ba99  lea     rsi, WPP_GLOBAL_Control
0x18007baa0  lea     r15, WPP_b54c9f5e9d683c400514a20e8b347731_Traceguids
0x18007baa7  cmp     rcx, rsi
0x18007baaa  jz      short loc_18007BAC3
0x18007baac  test    byte ptr [rcx+1Ch], 1
0x18007bab0  jz      short loc_18007BAC3
0x18007bab2  mov     rcx, [rcx+10h]
0x18007bab6  mov     edx, 0Ah
0x18007babb  mov     r8, r15
0x18007babe  call    WPP_SF_
0x18007bac3  lea     rax, [rsp+490h+hKey]
0x18007bac8  mov     r9d, 1; samDesired
0x18007bace  xor     r8d, r8d; ulOptions
0x18007bad1  mov     [rsp+490h+phkResult], rax; phkResult
0x18007bad6  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Wl"...
0x18007badd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007bae4  call    cs:__imp_RegOpenKeyExW
0x18007baeb  nop     dword ptr [rax+rax+00h]
0x18007baf0  test    eax, eax
0x18007baf2  jz      short loc_18007BB27
0x18007baf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bafb  cmp     rcx, rsi
0x18007bafe  jz      loc_18007BBC8
0x18007bb04  test    byte ptr [rcx+1Ch], 1
0x18007bb08  jz      loc_18007BBC8
0x18007bb0e  mov     edx, 0Bh
0x18007bb13  mov     rcx, [rcx+10h]
0x18007bb17  mov     r9d, eax
0x18007bb1a  mov     r8, r15
0x18007bb1d  call    WPP_SF_d
0x18007bb22  jmp     loc_18007BBC8
0x18007bb27  mov     rcx, [rsp+490h+hKey]; hKey
0x18007bb2c  lea     rax, [rsp+490h+cbData]
0x18007bb31  mov     [rsp+490h+lpcbData], rax; lpcbData
0x18007bb36  xor     r9d, r9d; lpType
0x18007bb39  lea     rax, [rsp+490h+Data]
0x18007bb3e  xor     r8d, r8d; lpReserved
0x18007bb41  xor     edx, edx; lpValueName
0x18007bb43  mov     [rsp+490h+phkResult], rax; lpData
0x18007bb48  call    cs:__imp_RegQueryValueExW
0x18007bb4f  nop     dword ptr [rax+rax+00h]
0x18007bb54  test    eax, eax
0x18007bb56  jz      short loc_18007BB71
0x18007bb58  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bb5f  cmp     rcx, rsi
0x18007bb62  jz      short loc_18007BBC8
0x18007bb64  test    byte ptr [rcx+1Ch], 1
0x18007bb68  jz      short loc_18007BBC8
0x18007bb6a  mov     edx, 0Ch
0x18007bb6f  jmp     short loc_18007BB13
0x18007bb71  mov     r8d, edi; nSize
0x18007bb74  lea     rdx, [rbp+390h+Dst]; lpDst
0x18007bb7b  lea     rcx, [rsp+490h+Data]; lpSrc
0x18007bb80  call    cs:__imp_ExpandEnvironmentStringsW
0x18007bb87  nop     dword ptr [rax+rax+00h]
0x18007bb8c  test    eax, eax
0x18007bb8e  jnz     short loc_18007BBD1
0x18007bb90  call    cs:__imp_GetLastError
0x18007bb97  nop     dword ptr [rax+rax+00h]
0x18007bb9c  mov     ebx, eax
0x18007bb9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bba5  cmp     rcx, rsi
0x18007bba8  jz      short loc_18007BBC4
0x18007bbaa  test    byte ptr [rcx+1Ch], 1
0x18007bbae  jz      short loc_18007BBC4
0x18007bbb0  mov     rcx, [rcx+10h]
0x18007bbb4  mov     edx, 0Dh
0x18007bbb9  mov     r9d, eax
0x18007bbbc  mov     r8, r15
0x18007bbbf  call    WPP_SF_d
0x18007bbc4  test    ebx, ebx
0x18007bbc6  jz      short loc_18007BBD1
0x18007bbc8  lea     rcx, aWcneapauthprox; "WcnEapAuthProxy.dll"
0x18007bbcf  jmp     short loc_18007BBD8
0x18007bbd1  lea     rcx, [rbp+390h+Dst]; lpLibFileName
0x18007bbd8  xor     r8d, r8d; dwFlags
0x18007bbdb  xor     edx, edx; hFile
0x18007bbdd  call    cs:__imp_LoadLibraryExW
0x18007bbe4  nop     dword ptr [rax+rax+00h]
0x18007bbe9  mov     cs:hLibModule, rax
0x18007bbf0  test    rax, rax
0x18007bbf3  jnz     short loc_18007BC1C
0x18007bbf5  xor     edi, edi
0x18007bbf7  call    cs:__imp_GetLastError
0x18007bbfe  nop     dword ptr [rax+rax+00h]
0x18007bc03  mov     ebx, eax
0x18007bc05  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bc0c  cmp     rcx, rsi
0x18007bc0f  jz      short loc_18007BC73
0x18007bc11  test    byte ptr [rcx+1Ch], 2
0x18007bc15  jz      short loc_18007BC73
0x18007bc17  lea     edx, [rdi+0Eh]
0x18007bc1a  jmp     short loc_18007BC5D
0x18007bc1c  lea     rdx, aWcneappluginge; "WcnEapPluginGetInfo"
0x18007bc23  mov     rcx, rax; hModule
0x18007bc26  call    cs:__imp_GetProcAddress
0x18007bc2d  nop     dword ptr [rax+rax+00h]
0x18007bc32  test    rax, rax
0x18007bc35  jnz     short loc_18007BC85
0x18007bc37  lea     edi, [rax+1]
0x18007bc3a  call    cs:__imp_GetLastError
0x18007bc41  nop     dword ptr [rax+rax+00h]
0x18007bc46  mov     ebx, eax
0x18007bc48  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bc4f  cmp     rcx, rsi
0x18007bc52  jz      short loc_18007BC73
0x18007bc54  test    byte ptr [rcx+1Ch], 2
0x18007bc58  jz      short loc_18007BC73
0x18007bc5a  lea     edx, [rdi+0Eh]
0x18007bc5d  mov     rcx, [rcx+10h]
0x18007bc61  mov     r9d, eax
0x18007bc64  mov     r8, r15
0x18007bc67  call    WPP_SF_d
0x18007bc6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bc73  test    ebx, ebx
0x18007bc75  jz      loc_18007BD11
0x18007bc7b  test    edi, edi
0x18007bc7d  jz      loc_18007BD11
0x18007bc83  jmp     short loc_18007BCF7
0x18007bc85  lea     rdx, qword_1800BB5A8
0x18007bc8c  mov     ecx, 1
0x18007bc91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc96  mov     ebx, eax
0x18007bc98  test    eax, eax
0x18007bc9a  jz      short loc_18007BCB5
0x18007bc9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bca3  cmp     rcx, rsi
0x18007bca6  jz      short loc_18007BCF7
0x18007bca8  test    byte ptr [rcx+1Ch], 2
0x18007bcac  jz      short loc_18007BCF7
0x18007bcae  mov     edx, 10h
0x18007bcb3  jmp     short loc_18007BCE8
0x18007bcb5  mov     rax, cs:qword_1800BB5A8
0x18007bcbc  lea     rcx, qword_1800BB5B0
0x18007bcc3  mov     rax, [rax]
0x18007bcc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bccb  mov     ebx, eax
0x18007bccd  test    eax, eax
0x18007bccf  jz      short loc_18007BD0A
0x18007bcd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bcd8  cmp     rcx, rsi
0x18007bcdb  jz      short loc_18007BCF7
0x18007bcdd  test    byte ptr [rcx+1Ch], 2
0x18007bce1  jz      short loc_18007BCF7
0x18007bce3  mov     edx, 11h
0x18007bce8  mov     rcx, [rcx+10h]
0x18007bcec  mov     r9d, eax
0x18007bcef  mov     r8, r15
0x18007bcf2  call    WPP_SF_d
0x18007bcf7  mov     rcx, cs:hLibModule; hLibModule
0x18007bcfe  call    cs:__imp_FreeLibrary
0x18007bd05  nop     dword ptr [rax+rax+00h]
0x18007bd0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bd11  mov     rax, [rsp+490h+hKey]
0x18007bd16  test    rax, rax
0x18007bd19  jz      short loc_18007BD31
0x18007bd1b  mov     rcx, rax; hKey
0x18007bd1e  call    cs:__imp_RegCloseKey
0x18007bd25  nop     dword ptr [rax+rax+00h]
0x18007bd2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bd31  cmp     rcx, rsi
0x18007bd34  jz      short loc_18007BD50
0x18007bd36  test    byte ptr [rcx+1Ch], 1
0x18007bd3a  jz      short loc_18007BD50
0x18007bd3c  mov     rcx, [rcx+10h]
0x18007bd40  mov     edx, 12h
0x18007bd45  mov     r9d, ebx
0x18007bd48  mov     r8, r15
0x18007bd4b  call    WPP_SF_d
0x18007bd50  mov     eax, ebx
0x18007bd52  mov     rcx, [rbp+390h+var_30]
0x18007bd59  xor     rcx, rsp; StackCookie
0x18007bd5c  call    __security_check_cookie
0x18007bd61  add     rsp, 470h
0x18007bd68  pop     r15
0x18007bd6a  pop     rdi
0x18007bd6b  pop     rsi
0x18007bd6c  pop     rbx
0x18007bd6d  pop     rbp
0x18007bd6e  retn
```
