# QueryRmSoftwareKey

- ea: `0x18000a1d8`
- end: `0x18000a499`
- name: `QueryRmSoftwareKey`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d80`

## callees

- `0x180003bb0`
- `0x180004afc`
- `0x18000a1d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a340`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a340`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a433`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a433`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a441`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a441`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a2fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a2fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a292`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a3b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a292`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a3b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a409`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a453`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a409`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a453`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a390`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a390`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a3ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a3ec`

## string_xrefs

- `0x18000a3e5`: `ProtocolId`

## pseudocode

```c
HRESULT __fastcall QueryRmSoftwareKey(__int64 a1, int a2, HKEY *a3, WCHAR **a4)
{
  HRESULT result; // eax
  LSTATUS v8; // edi
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v13; // rsi
  DWORD i; // ebx
  HKEY v15; // rcx
  LSTATUS v16; // eax
  HANDLE v17; // rax
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  wchar_t pszDest[256]; // [rsp+80h] [rbp-80h] BYREF

  *a4 = 0;
  hKey = 0;
  result = StringCchPrintfW(
             pszDest,
             0x100u,
             L"%s\\%s\\%s\\%s\\%s",
             L"Software",
             L"Microsoft",
             L"Router",
             L"CurrentVersion",
             L"RouterManagers");
  if ( result < 0 )
    return (unsigned __int16)result;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &hKey);
  if ( !result )
  {
    *(_DWORD *)Data = ~a2;
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    cchName = 0;
    Type = 0;
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v8 )
      goto LABEL_24;
    v9 = cbMaxSubKeyLen + 1;
    if ( (unsigned int)v9 < cbMaxSubKeyLen || (v10 = 2 * v9, v10 > 0xFFFFFFFF) )
    {
      v8 = 534;
      goto LABEL_24;
    }
    v11 = v10;
    cchName = v10;
    ProcessHeap = GetProcessHeap();
    v13 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v11);
    if ( !v13 )
    {
      v8 = 8;
      goto LABEL_24;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= cSubKeys )
        goto LABEL_22;
      cchName = cbMaxSubKeyLen + 1;
      v8 = RegEnumKeyExW(hKey, i, v13, &cchName, 0, 0, 0, 0);
      if ( !v8 )
      {
        v8 = RegOpenKeyExW(hKey, v13, 0, 0x20019u, a3);
        if ( !v8 )
        {
          v15 = *a3;
          cchName = 4;
          v16 = RegQueryValueExW(v15, L"ProtocolId", 0, &Type, Data, &cchName);
          v8 = v16;
          if ( Type != 4 )
          {
            RegCloseKey(*a3);
            v8 = 13;
LABEL_19:
            if ( i >= cSubKeys )
            {
LABEL_22:
              v17 = GetProcessHeap();
              HeapFree(v17, 0, v13);
              goto LABEL_24;
            }
            if ( !v8 )
              *a4 = v13;
LABEL_24:
            RegCloseKey(hKey);
            if ( *a4 )
              return 0;
            if ( !v8 )
              return 259;
            return v8;
          }
          if ( !v16 && *(_DWORD *)Data == a2 )
            goto LABEL_19;
          RegCloseKey(*a3);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a1d8  mov     [rsp-8+arg_0], rbx
0x18000a1dd  push    rbp
0x18000a1de  push    rsi
0x18000a1df  push    rdi
0x18000a1e0  push    r12
0x18000a1e2  push    r13
0x18000a1e4  push    r14
0x18000a1e6  push    r15
0x18000a1e8  lea     rbp, [rsp-190h]
0x18000a1f0  sub     rsp, 290h
0x18000a1f7  mov     rax, cs:__security_cookie
0x18000a1fe  xor     rax, rsp
0x18000a201  mov     [rbp+1C0h+var_40], rax
0x18000a208  lea     rax, c_szRouterManagers; "RouterManagers"
0x18000a20f  xor     r13d, r13d
0x18000a212  mov     [rsp+2C0h+lpcValues], rax
0x18000a217  lea     rcx, [rbp+1C0h+pszDest]; pszDest
0x18000a21b  lea     rax, c_szCurrentVersion; "CurrentVersion"
0x18000a222  mov     [r9], r13
0x18000a225  mov     [rsp+2C0h+lpcbMaxClassLen], rax
0x18000a22a  mov     r15, r9
0x18000a22d  lea     rax, c_szRouter; "Router"
0x18000a234  mov     [rsp+2C0h+hKey], r13
0x18000a239  mov     [rsp+2C0h+lpcbMaxSubKeyLen], rax
0x18000a23e  lea     r9, c_szSoftware; "Software"
0x18000a245  lea     rax, c_szMicrosoft; "Microsoft"
0x18000a24c  mov     r14, r8
0x18000a24f  mov     r12d, edx
0x18000a252  mov     [rsp+2C0h+phkResult], rax
0x18000a257  lea     r8, aSSSSS; "%s\\%s\\%s\\%s\\%s"
0x18000a25e  mov     edx, 100h; cchDest
0x18000a263  call    StringCchPrintfW
0x18000a268  test    eax, eax
0x18000a26a  jns     short loc_18000A274
0x18000a26c  movzx   eax, ax
0x18000a26f  jmp     loc_18000A46F
0x18000a274  lea     rax, [rsp+2C0h+hKey]
0x18000a279  mov     r9d, 20019h; samDesired
0x18000a27f  xor     r8d, r8d; ulOptions
0x18000a282  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18000a287  lea     rdx, [rbp+1C0h+pszDest]; lpSubKey
0x18000a28b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a292  call    cs:__imp_RegOpenKeyExW
0x18000a298  test    eax, eax
0x18000a29a  jnz     loc_18000A46F
0x18000a2a0  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000a2a5  mov     eax, r12d
0x18000a2a8  mov     [rsp+2C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000a2ad  not     eax
0x18000a2af  mov     [rsp+2C0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000a2b4  xor     r9d, r9d; lpReserved
0x18000a2b7  mov     [rsp+2C0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000a2bc  xor     r8d, r8d; lpcchClass
0x18000a2bf  mov     [rsp+2C0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000a2c4  xor     edx, edx; lpClass
0x18000a2c6  mov     dword ptr [rsp+2C0h+Data], eax
0x18000a2ca  lea     rax, [rsp+2C0h+cbMaxSubKeyLen]
0x18000a2cf  mov     [rsp+2C0h+lpcValues], r13; lpcValues
0x18000a2d4  mov     [rsp+2C0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000a2d9  mov     [rsp+2C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000a2de  lea     rax, [rsp+2C0h+cSubKeys]
0x18000a2e3  mov     [rsp+2C0h+phkResult], rax; lpcSubKeys
0x18000a2e8  mov     [rsp+2C0h+cSubKeys], r13d
0x18000a2ed  mov     [rsp+2C0h+cbMaxSubKeyLen], r13d
0x18000a2f2  mov     [rsp+2C0h+cchName], r13d
0x18000a2f7  mov     [rsp+2C0h+Type], r13d
0x18000a2fc  call    cs:__imp_RegQueryInfoKeyW
0x18000a302  mov     edi, eax
0x18000a304  test    eax, eax
0x18000a306  jnz     loc_18000A44E
0x18000a30c  mov     ecx, [rsp+2C0h+cbMaxSubKeyLen]
0x18000a310  lea     eax, [rcx+1]
0x18000a313  cmp     eax, ecx
0x18000a315  jb      loc_18000A449
0x18000a31b  add     rax, rax
0x18000a31e  mov     ecx, 0FFFFFFFFh
0x18000a323  cmp     rax, rcx
0x18000a326  ja      loc_18000A449
0x18000a32c  mov     ebx, eax
0x18000a32e  mov     [rsp+2C0h+cchName], ebx
0x18000a332  call    cs:__imp_GetProcessHeap
0x18000a338  mov     r8d, ebx; dwBytes
0x18000a33b  xor     edx, edx; dwFlags
0x18000a33d  mov     rcx, rax; hHeap
0x18000a340  call    cs:__imp_HeapAlloc
0x18000a346  mov     rsi, rax
0x18000a349  test    rax, rax
0x18000a34c  jnz     short loc_18000A356
0x18000a34e  lea     edi, [rax+8]
0x18000a351  jmp     loc_18000A44E
0x18000a356  mov     ebx, r13d
0x18000a359  cmp     ebx, [rsp+2C0h+cSubKeys]
0x18000a35d  jnb     loc_18000A433
0x18000a363  mov     eax, [rsp+2C0h+cbMaxSubKeyLen]
0x18000a367  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x18000a36c  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000a371  inc     eax
0x18000a373  mov     [rsp+2C0h+lpcValues], r13; lpftLastWriteTime
0x18000a378  mov     r8, rsi; lpName
0x18000a37b  mov     [rsp+2C0h+lpcbMaxClassLen], r13; lpcchClass
0x18000a380  mov     edx, ebx; dwIndex
0x18000a382  mov     [rsp+2C0h+lpcbMaxSubKeyLen], r13; lpClass
0x18000a387  mov     [rsp+2C0h+cchName], eax
0x18000a38b  mov     [rsp+2C0h+phkResult], r13; lpReserved
0x18000a390  call    cs:__imp_RegEnumKeyExW
0x18000a396  mov     edi, eax
0x18000a398  test    eax, eax
0x18000a39a  jnz     short loc_18000A40F
0x18000a39c  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000a3a1  mov     r9d, 20019h; samDesired
0x18000a3a7  xor     r8d, r8d; ulOptions
0x18000a3aa  mov     [rsp+2C0h+phkResult], r14; phkResult
0x18000a3af  mov     rdx, rsi; lpSubKey
0x18000a3b2  call    cs:__imp_RegOpenKeyExW
0x18000a3b8  mov     edi, eax
0x18000a3ba  test    eax, eax
0x18000a3bc  jnz     short loc_18000A40F
0x18000a3be  mov     rcx, [r14]; hKey
0x18000a3c1  lea     rax, [rsp+2C0h+cchName]
0x18000a3c6  mov     [rsp+2C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000a3cb  lea     r9, [rsp+2C0h+Type]; lpType
0x18000a3d0  lea     rax, [rsp+2C0h+Data]
0x18000a3d5  mov     [rsp+2C0h+cchName], 4
0x18000a3dd  xor     r8d, r8d; lpReserved
0x18000a3e0  mov     [rsp+2C0h+phkResult], rax; lpData
0x18000a3e5  lea     rdx, c_szProtocolId; "ProtocolId"
0x18000a3ec  call    cs:__imp_RegQueryValueExW
0x18000a3f2  cmp     [rsp+2C0h+Type], 4
0x18000a3f7  mov     edi, eax
0x18000a3f9  jnz     short loc_18000A416
0x18000a3fb  test    eax, eax
0x18000a3fd  jnz     short loc_18000A406
0x18000a3ff  cmp     dword ptr [rsp+2C0h+Data], r12d
0x18000a404  jz      short loc_18000A424
0x18000a406  mov     rcx, [r14]; hKey
0x18000a409  call    cs:__imp_RegCloseKey
0x18000a40f  inc     ebx
0x18000a411  jmp     loc_18000A359
0x18000a416  mov     rcx, [r14]; hKey
0x18000a419  call    cs:__imp_RegCloseKey
0x18000a41f  mov     edi, 0Dh
0x18000a424  cmp     ebx, [rsp+2C0h+cSubKeys]
0x18000a428  jnb     short loc_18000A433
0x18000a42a  test    edi, edi
0x18000a42c  jnz     short loc_18000A44E
0x18000a42e  mov     [r15], rsi
0x18000a431  jmp     short loc_18000A44E
0x18000a433  call    cs:__imp_GetProcessHeap
0x18000a439  mov     r8, rsi; lpMem
0x18000a43c  xor     edx, edx; dwFlags
0x18000a43e  mov     rcx, rax; hHeap
0x18000a441  call    cs:__imp_HeapFree
0x18000a447  jmp     short loc_18000A44E
0x18000a449  mov     edi, 216h
0x18000a44e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000a453  call    cs:__imp_RegCloseKey
0x18000a459  cmp     [r15], r13
0x18000a45c  jz      short loc_18000A463
0x18000a45e  mov     edi, r13d
0x18000a461  jmp     short loc_18000A46D
0x18000a463  test    edi, edi
0x18000a465  mov     eax, 103h
0x18000a46a  cmovz   edi, eax
0x18000a46d  mov     eax, edi
0x18000a46f  mov     rcx, [rbp+1C0h+var_40]
0x18000a476  xor     rcx, rsp; StackCookie
0x18000a479  call    __security_check_cookie
0x18000a47e  mov     rbx, [rsp+2C0h+arg_0]
0x18000a486  add     rsp, 290h
0x18000a48d  pop     r15
0x18000a48f  pop     r14
0x18000a491  pop     r13
0x18000a493  pop     r12
0x18000a495  pop     rdi
0x18000a496  pop     rsi
0x18000a497  pop     rbp
0x18000a498  retn
```
