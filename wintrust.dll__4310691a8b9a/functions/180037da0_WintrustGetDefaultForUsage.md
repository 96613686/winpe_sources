# WintrustGetDefaultForUsage

- ea: `0x180037da0`
- end: `0x180038062`
- name: `WintrustGetDefaultForUsage`
- size: `706`
- prototype: `BOOL __stdcall(DWORD dwAction, const char *pszUsageOID, CRYPT_PROVIDER_DEFUSAGE *psUsage)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000bdb0`
- `0x18000d1c0`
- `0x180020aac`
- `0x180037da0`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037f67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037f67`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038030`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038030`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038010`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038010`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037e3a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037e3a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180037f03`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180037f03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180037f55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180037f55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037ef1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037fd7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037ef1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037fd7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037ead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037ead`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038022`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038022`

## pseudocode

```c
BOOL __stdcall WintrustGetDefaultForUsage(DWORD dwAction, const char *pszUsageOID, CRYPT_PROVIDER_DEFUSAGE *psUsage)
{
  HMODULE LibraryW; // rdi
  int v7; // eax
  unsigned int (__fastcall *v8)(const char *, CRYPT_PROVIDER_DEFUSAGE *); // r14
  const CHAR *v9; // rdx
  FARPROC ProcAddress; // rax
  BOOL v11; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[64]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v17[80]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR WideCharStr[64]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SubKey[128]; // [rsp+150h] [rbp+50h] BYREF

  LibraryW = 0;
  Type = 0;
  cbData = 0;
  phkResult = 0;
  if ( !pszUsageOID
    || !psUsage
    || psUsage->cbStruct <= 0x20
    || (WideCharStr[0] = 0,
        psUsage->gActionID = 0,
        v7 = MultiByteToWideChar(0, 0, pszUsageOID, -1, WideCharStr, 64),
        v7 <= 0)
    || (unsigned __int64)(v7 + 56LL) > 0x80 )
  {
    SetLastError(0x57u);
    goto LABEL_24;
  }
  StringCchCopyW(SubKey, 0x80u, L"Software\\Microsoft\\Cryptography\\Providers\\Trust\\Usages");
  StringCchCatW(SubKey, 0x80u, L"\\");
  StringCchCatW(SubKey, 0x80u, WideCharStr);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult) )
  {
LABEL_24:
    v11 = 0;
    goto LABEL_25;
  }
  v8 = 0;
  Type = 0;
  cbData = 256;
  if ( RegQueryValueExW(phkResult, L"$DLL", 0, &Type, (LPBYTE)SubKey, &cbData) )
    goto LABEL_17;
  LibraryW = LoadLibraryW(SubKey);
  if ( !LibraryW )
    goto LABEL_17;
  Type = 0;
  v9 = "CallbackFreeFunction";
  cbData = 64;
  if ( dwAction != 2 )
    v9 = "CallbackAllocFunction";
  if ( RegQueryValueExA(phkResult, v9, 0, &Type, Data, &cbData) )
  {
LABEL_17:
    v11 = 1;
    if ( dwAction != 1 )
      goto LABEL_25;
    Type = 0;
    *(_WORD *)v17 = 0;
    cbData = 78;
    if ( !RegQueryValueExW(phkResult, L"DefaultId", 0, &Type, v17, &cbData)
      && (unsigned int)wstr2guid(v17, &psUsage->gActionID)
      && (!v8 || v8(pszUsageOID, psUsage)) )
    {
      goto LABEL_25;
    }
    goto LABEL_24;
  }
  ProcAddress = GetProcAddress(LibraryW, (LPCSTR)Data);
  if ( dwAction != 2 )
  {
    v8 = (unsigned int (__fastcall *)(const char *, CRYPT_PROVIDER_DEFUSAGE *))ProcAddress;
    goto LABEL_17;
  }
  if ( ProcAddress )
    ((void (__fastcall *)(const char *, CRYPT_PROVIDER_DEFUSAGE *))ProcAddress)(pszUsageOID, psUsage);
  v11 = 1;
LABEL_25:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( LibraryW )
    FreeLibrary(LibraryW);
  return v11;
}

```

## disassembly

```asm
0x180037da0  mov     [rsp-8+arg_0], rbx
0x180037da5  push    rbp
0x180037da6  push    rsi
0x180037da7  push    rdi
0x180037da8  push    r12
0x180037daa  push    r13
0x180037dac  push    r14
0x180037dae  push    r15
0x180037db0  lea     rbp, [rsp-160h]
0x180037db8  sub     rsp, 260h
0x180037dbf  mov     rax, cs:__security_cookie
0x180037dc6  xor     rax, rsp
0x180037dc9  mov     [rbp+190h+var_40], rax
0x180037dd0  xor     edi, edi
0x180037dd2  mov     [rsp+290h+Type], 0
0x180037dda  mov     [rsp+290h+cbData], 0
0x180037de2  mov     rsi, r8
0x180037de5  mov     [rsp+290h+phkResult], 0
0x180037dee  mov     r15, rdx
0x180037df1  mov     r12d, ecx
0x180037df4  test    rdx, rdx
0x180037df7  jz      loc_18003800B
0x180037dfd  test    r8, r8
0x180037e00  jz      loc_18003800B
0x180037e06  cmp     dword ptr [r8], 20h ; ' '
0x180037e0a  jbe     loc_18003800B
0x180037e10  xor     eax, eax
0x180037e12  mov     [rsp+290h+cchWideChar], 40h ; '@'; cchWideChar
0x180037e1a  xorps   xmm0, xmm0
0x180037e1d  mov     [rbp+190h+WideCharStr], ax
0x180037e21  movups  xmmword ptr [r8+4], xmm0
0x180037e26  lea     rax, [rbp+190h+WideCharStr]
0x180037e2a  mov     r8, rdx; lpMultiByteStr
0x180037e2d  xor     edx, edx; dwFlags
0x180037e2f  mov     [rsp+290h+lpWideCharStr], rax; lpWideCharStr
0x180037e34  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180037e38  xor     ecx, ecx; CodePage
0x180037e3a  call    cs:__imp_MultiByteToWideChar
0x180037e40  test    eax, eax
0x180037e42  jle     loc_18003800B
0x180037e48  cdqe
0x180037e4a  mov     ebx, 80h
0x180037e4f  add     rax, 38h ; '8'
0x180037e53  cmp     rax, rbx
0x180037e56  ja      loc_18003800B
0x180037e5c  lea     r8, aSoftwareMicros_14; "Software\\Microsoft\\Cryptography\\Prov"...
0x180037e63  mov     edx, ebx; unsigned __int64
0x180037e65  lea     rcx, [rbp+190h+SubKey]; unsigned __int16 *
0x180037e69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037e6e  lea     r8, asc_1800557E4; "\\"
0x180037e75  mov     edx, ebx; unsigned __int64
0x180037e77  lea     rcx, [rbp+190h+SubKey]; unsigned __int16 *
0x180037e7b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037e80  lea     r8, [rbp+190h+WideCharStr]; unsigned __int16 *
0x180037e84  mov     edx, ebx; unsigned __int64
0x180037e86  lea     rcx, [rbp+190h+SubKey]; unsigned __int16 *
0x180037e8a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037e8f  lea     rax, [rsp+290h+phkResult]
0x180037e94  mov     r9d, 20019h; samDesired
0x180037e9a  xor     r8d, r8d; ulOptions
0x180037e9d  mov     [rsp+290h+lpWideCharStr], rax; phkResult
0x180037ea2  lea     rdx, [rbp+190h+SubKey]; lpSubKey
0x180037ea6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037ead  call    cs:__imp_RegOpenKeyExW
0x180037eb3  test    eax, eax
0x180037eb5  jnz     loc_180038016
0x180037ebb  xor     r14d, r14d
0x180037ebe  mov     rcx, [rsp+290h+phkResult]; hKey
0x180037ec3  lea     rax, [rsp+290h+cbData]
0x180037ec8  mov     qword ptr [rsp+290h+cchWideChar], rax; lpcbData
0x180037ecd  lea     r9, [rsp+290h+Type]; lpType
0x180037ed2  lea     rax, [rbp+190h+SubKey]
0x180037ed6  mov     [rsp+290h+Type], edi
0x180037eda  xor     r8d, r8d; lpReserved
0x180037edd  mov     [rsp+290h+lpWideCharStr], rax; lpData
0x180037ee2  lea     rdx, aDll; "$DLL"
0x180037ee9  mov     [rsp+290h+cbData], 100h
0x180037ef1  call    cs:__imp_RegQueryValueExW
0x180037ef7  test    eax, eax
0x180037ef9  jnz     loc_180037F90
0x180037eff  lea     rcx, [rbp+190h+SubKey]; lpLibFileName
0x180037f03  call    cs:__imp_LoadLibraryW
0x180037f09  mov     rdi, rax
0x180037f0c  test    rax, rax
0x180037f0f  jz      short loc_180037F90
0x180037f11  mov     rcx, [rsp+290h+phkResult]; hKey
0x180037f16  lea     rax, aCallbackallocf; "CallbackAllocFunction"
0x180037f1d  cmp     r12d, 2
0x180037f21  mov     [rsp+290h+Type], r14d
0x180037f26  lea     rdx, aCallbackfreefu; "CallbackFreeFunction"
0x180037f2d  mov     [rsp+290h+cbData], 40h ; '@'
0x180037f35  cmovnz  rdx, rax; lpValueName
0x180037f39  lea     r9, [rsp+290h+Type]; lpType
0x180037f3e  lea     rax, [rsp+290h+cbData]
0x180037f43  xor     r8d, r8d; lpReserved
0x180037f46  mov     qword ptr [rsp+290h+cchWideChar], rax; lpcbData
0x180037f4b  lea     rax, [rsp+290h+Data]
0x180037f50  mov     [rsp+290h+lpWideCharStr], rax; lpData
0x180037f55  call    cs:__imp_RegQueryValueExA
0x180037f5b  test    eax, eax
0x180037f5d  jnz     short loc_180037F90
0x180037f5f  lea     rdx, [rsp+290h+Data]; lpProcName
0x180037f64  mov     rcx, rdi; hModule
0x180037f67  call    cs:__imp_GetProcAddress
0x180037f6d  cmp     r12d, 2
0x180037f71  jnz     short loc_180037F8D
0x180037f73  test    rax, rax
0x180037f76  jz      short loc_180037F83
0x180037f78  mov     rdx, rsi
0x180037f7b  mov     rcx, r15
0x180037f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f83  mov     ebx, 1
0x180037f88  jmp     loc_180038018
0x180037f8d  mov     r14, rax
0x180037f90  mov     ebx, 1
0x180037f95  cmp     r12d, ebx
0x180037f98  jnz     short loc_180038018
0x180037f9a  xor     ecx, ecx
0x180037f9c  mov     [rsp+290h+Type], 0
0x180037fa4  lea     rax, [rsp+290h+cbData]
0x180037fa9  mov     word ptr [rbp+190h+var_210], cx
0x180037fad  mov     rcx, [rsp+290h+phkResult]; hKey
0x180037fb2  lea     r9, [rsp+290h+Type]; lpType
0x180037fb7  mov     qword ptr [rsp+290h+cchWideChar], rax; lpcbData
0x180037fbc  lea     rdx, aDefaultid; "DefaultId"
0x180037fc3  lea     rax, [rbp+190h+var_210]
0x180037fc7  mov     [rsp+290h+cbData], 4Eh ; 'N'
0x180037fcf  xor     r8d, r8d; lpReserved
0x180037fd2  mov     [rsp+290h+lpWideCharStr], rax; lpData
0x180037fd7  call    cs:__imp_RegQueryValueExW
0x180037fdd  test    eax, eax
0x180037fdf  jnz     short loc_180038016
0x180037fe1  lea     rdx, [rsi+4]
0x180037fe5  lea     rcx, [rbp+190h+var_210]
0x180037fe9  call    wstr2guid
0x180037fee  test    eax, eax
0x180037ff0  jz      short loc_180038016
0x180037ff2  test    r14, r14
0x180037ff5  jz      short loc_180038018
0x180037ff7  mov     rdx, rsi
0x180037ffa  mov     rcx, r15
0x180037ffd  mov     rax, r14
0x180038000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038005  test    eax, eax
0x180038007  jz      short loc_180038016
0x180038009  jmp     short loc_180038018
0x18003800b  mov     ecx, 57h ; 'W'; dwErrCode
0x180038010  call    cs:__imp_SetLastError
0x180038016  xor     ebx, ebx
0x180038018  mov     rcx, [rsp+290h+phkResult]; hKey
0x18003801d  test    rcx, rcx
0x180038020  jz      short loc_180038028
0x180038022  call    cs:__imp_RegCloseKey
0x180038028  test    rdi, rdi
0x18003802b  jz      short loc_180038036
0x18003802d  mov     rcx, rdi; hLibModule
0x180038030  call    cs:__imp_FreeLibrary
0x180038036  mov     eax, ebx
0x180038038  mov     rcx, [rbp+190h+var_40]
0x18003803f  xor     rcx, rsp; StackCookie
0x180038042  call    __security_check_cookie
0x180038047  mov     rbx, [rsp+290h+arg_0]
0x18003804f  add     rsp, 260h
0x180038056  pop     r15
0x180038058  pop     r14
0x18003805a  pop     r13
0x18003805c  pop     r12
0x18003805e  pop     rdi
0x18003805f  pop     rsi
0x180038060  pop     rbp
0x180038061  retn
```
