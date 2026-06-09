# QueryRmSoftwareKey(x,x,x,x)

- ea: `0x1000a2ae`
- end: `0x1000a512`
- name: `_QueryRmSoftwareKey@16`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10009f60`

## callees

- `0x10003c20`
- `0x10006636`
- `0x1000a2ae`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000a4c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000a4c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1000a3b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1000a3b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000a3b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000a4bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000a3b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000a4bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000a47d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000a49a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000a4e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000a47d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000a49a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000a4e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1000a452`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1000a452`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1000a3fa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1000a3fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1000a370`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1000a370`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000a33a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000a419`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000a33a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000a419`

## string_xrefs

- `0x1000a44b`: `ProtocolId`

## pseudocode

```c
HRESULT __fastcall QueryRmSoftwareKey(int a1, int a2, HKEY *a3, WCHAR **a4)
{
  DWORD v4; // edi
  HRESULT result; // eax
  LSTATUS v7; // esi
  HANDLE ProcessHeap; // eax
  WCHAR *v9; // ebx
  LSTATUS v10; // eax
  WCHAR **v11; // edi
  HANDLE v12; // eax
  DWORD v13; // [esp-8h] [ebp-238h]
  DWORD Type; // [esp+Ch] [ebp-224h] BYREF
  BYTE Data[4]; // [esp+10h] [ebp-220h] BYREF
  DWORD cbMaxSubKeyLen; // [esp+14h] [ebp-21Ch] BYREF
  DWORD cSubKeys; // [esp+18h] [ebp-218h] BYREF
  HKEY phkResult; // [esp+1Ch] [ebp-214h] BYREF
  PHKEY v20; // [esp+20h] [ebp-210h]
  DWORD cchName; // [esp+24h] [ebp-20Ch] BYREF
  WCHAR **v22; // [esp+28h] [ebp-208h]
  wchar_t pszDest[256]; // [esp+2Ch] [ebp-204h] BYREF

  v20 = a3;
  v4 = 0;
  v22 = a4;
  *a4 = 0;
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
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &phkResult);
  if ( !result )
  {
    *(_DWORD *)Data = ~a2;
    v7 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v7 )
      goto LABEL_25;
    if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
    {
      if ( is_mul_ok(2u, cbMaxSubKeyLen + 1) )
      {
        v13 = 2 * (cbMaxSubKeyLen + 1);
        cchName = v13;
        ProcessHeap = GetProcessHeap();
        v9 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v13);
        if ( !v9 )
        {
          v7 = 8;
          goto LABEL_25;
        }
        if ( !cSubKeys )
          goto LABEL_22;
        while ( 1 )
        {
          cchName = cbMaxSubKeyLen + 1;
          v7 = RegEnumKeyExW(phkResult, v4, v9, &cchName, 0, 0, 0, 0);
          if ( !v7 )
          {
            v7 = RegOpenKeyExW(phkResult, v9, 0, 0x20019u, v20);
            if ( !v7 )
            {
              cchName = 4;
              v10 = RegQueryValueExW(*v20, L"ProtocolId", 0, &Type, Data, &cchName);
              v7 = v10;
              if ( Type != 4 )
              {
                RegCloseKey(*v20);
                v7 = 13;
LABEL_19:
                if ( v4 < cSubKeys )
                {
                  v11 = v22;
                  if ( !v7 )
                    *v22 = v9;
LABEL_26:
                  RegCloseKey(phkResult);
                  if ( *v11 )
                    return 0;
                  if ( !v7 )
                    return 259;
                  return v7;
                }
LABEL_22:
                v12 = GetProcessHeap();
                HeapFree(v12, 0, v9);
LABEL_25:
                v11 = v22;
                goto LABEL_26;
              }
              if ( !v10 && *(_DWORD *)Data == a2 )
                goto LABEL_19;
              RegCloseKey(*v20);
            }
          }
          if ( ++v4 >= cSubKeys )
            goto LABEL_19;
        }
      }
      cchName = -1;
    }
    v7 = 534;
    goto LABEL_25;
  }
  return result;
}

```

## disassembly

```asm
0x1000a2ae  mov     edi, edi
0x1000a2b0  push    ebp
0x1000a2b1  mov     ebp, esp
0x1000a2b3  sub     esp, 228h
0x1000a2b9  mov     eax, ___security_cookie
0x1000a2be  xor     eax, ebp
0x1000a2c0  mov     [ebp+var_4], eax
0x1000a2c3  mov     eax, [ebp+arg_0]
0x1000a2c6  push    ebx
0x1000a2c7  push    edi
0x1000a2c8  push    offset _c_szRouterManagers; "RouterManagers"
0x1000a2cd  push    offset _c_szCurrentVersion; "CurrentVersion"
0x1000a2d2  push    offset _c_szRouter; "Router"
0x1000a2d7  mov     [ebp+var_210], eax
0x1000a2dd  xor     edi, edi
0x1000a2df  mov     eax, [ebp+arg_4]
0x1000a2e2  mov     ebx, edx
0x1000a2e4  push    offset _c_szMicrosoft; "Microsoft"
0x1000a2e9  push    offset _c_szSoftware; "Software"
0x1000a2ee  push    offset aSSSSS; "%s\\%s\\%s\\%s\\%s"
0x1000a2f3  mov     [ebp+var_208], eax
0x1000a2f9  mov     [eax], edi
0x1000a2fb  lea     eax, [ebp+pszDest]
0x1000a301  push    100h; cchDest
0x1000a306  push    eax; pszDest
0x1000a307  mov     [ebp+var_228], ebx
0x1000a30d  call    _StringCchPrintfW
0x1000a312  add     esp, 20h
0x1000a315  test    eax, eax
0x1000a317  jns     short loc_1000A321
0x1000a319  movzx   eax, ax
0x1000a31c  jmp     loc_1000A502
0x1000a321  lea     eax, [ebp+phkResult]
0x1000a327  push    eax; phkResult
0x1000a328  push    20019h; samDesired
0x1000a32d  push    edi; ulOptions
0x1000a32e  lea     eax, [ebp+pszDest]
0x1000a334  push    eax; lpSubKey
0x1000a335  push    80000002h; hKey
0x1000a33a  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x1000a340  test    eax, eax
0x1000a342  jnz     loc_1000A502
0x1000a348  push    esi
0x1000a349  push    edi; lpftLastWriteTime
0x1000a34a  push    edi; lpcbSecurityDescriptor
0x1000a34b  push    edi; lpcbMaxValueLen
0x1000a34c  push    edi; lpcbMaxValueNameLen
0x1000a34d  push    edi; lpcValues
0x1000a34e  push    edi; lpcbMaxClassLen
0x1000a34f  mov     eax, ebx
0x1000a351  not     eax
0x1000a353  mov     dword ptr [ebp+Data], eax
0x1000a359  lea     eax, [ebp+cbMaxSubKeyLen]
0x1000a35f  push    eax; lpcbMaxSubKeyLen
0x1000a360  lea     eax, [ebp+cSubKeys]
0x1000a366  push    eax; lpcSubKeys
0x1000a367  push    edi; lpReserved
0x1000a368  push    edi; lpcchClass
0x1000a369  push    edi; lpClass
0x1000a36a  push    [ebp+phkResult]; hKey
0x1000a370  call    ds:__imp__RegQueryInfoKeyW@48; RegQueryInfoKeyW(x,x,x,x,x,x,x,x,x,x,x,x)
0x1000a376  mov     esi, eax
0x1000a378  test    esi, esi
0x1000a37a  jnz     loc_1000A4DA
0x1000a380  mov     ecx, [ebp+cbMaxSubKeyLen]
0x1000a386  lea     eax, [ecx+1]
0x1000a389  cmp     eax, ecx
0x1000a38b  jb      loc_1000A4D5
0x1000a391  push    2
0x1000a393  pop     ecx
0x1000a394  mul     ecx
0x1000a396  cmp     edx, edi
0x1000a398  ja      loc_1000A4CB
0x1000a39e  jb      short loc_1000A3A9
0x1000a3a0  cmp     eax, 0FFFFFFFFh
0x1000a3a3  ja      loc_1000A4CB
0x1000a3a9  push    eax; dwBytes
0x1000a3aa  push    edi; dwFlags
0x1000a3ab  mov     [ebp+cchName], eax
0x1000a3b1  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000a3b7  push    eax; hHeap
0x1000a3b8  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x1000a3be  mov     ebx, eax
0x1000a3c0  test    ebx, ebx
0x1000a3c2  jnz     short loc_1000A3CC
0x1000a3c4  push    8
0x1000a3c6  pop     esi
0x1000a3c7  jmp     loc_1000A4DA
0x1000a3cc  cmp     [ebp+cSubKeys], edi
0x1000a3d2  jbe     loc_1000A4B9
0x1000a3d8  mov     eax, [ebp+cbMaxSubKeyLen]
0x1000a3de  inc     eax
0x1000a3df  mov     [ebp+cchName], eax
0x1000a3e5  xor     eax, eax
0x1000a3e7  push    eax; lpftLastWriteTime
0x1000a3e8  push    eax; lpcchClass
0x1000a3e9  push    eax; lpClass
0x1000a3ea  push    eax; lpReserved
0x1000a3eb  lea     eax, [ebp+cchName]
0x1000a3f1  push    eax; lpcchName
0x1000a3f2  push    ebx; lpName
0x1000a3f3  push    edi; dwIndex
0x1000a3f4  push    [ebp+phkResult]; hKey
0x1000a3fa  call    ds:__imp__RegEnumKeyExW@32; RegEnumKeyExW(x,x,x,x,x,x,x,x)
0x1000a400  mov     esi, eax
0x1000a402  test    esi, esi
0x1000a404  jnz     short loc_1000A483
0x1000a406  push    [ebp+var_210]; phkResult
0x1000a40c  push    20019h; samDesired
0x1000a411  push    eax; ulOptions
0x1000a412  push    ebx; lpSubKey
0x1000a413  push    [ebp+phkResult]; hKey
0x1000a419  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x1000a41f  mov     esi, eax
0x1000a421  test    esi, esi
0x1000a423  jnz     short loc_1000A483
0x1000a425  lea     eax, [ebp+cchName]
0x1000a42b  mov     [ebp+cchName], 4
0x1000a435  push    eax; lpcbData
0x1000a436  lea     eax, [ebp+Data]
0x1000a43c  push    eax; lpData
0x1000a43d  lea     eax, [ebp+Type]
0x1000a443  push    eax; lpType
0x1000a444  mov     eax, [ebp+var_210]
0x1000a44a  push    esi; lpReserved
0x1000a44b  push    offset _c_szProtocolId; "ProtocolId"
0x1000a450  push    dword ptr [eax]; hKey
0x1000a452  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x1000a458  cmp     [ebp+Type], 4
0x1000a45f  mov     esi, eax
0x1000a461  jnz     short loc_1000A492
0x1000a463  test    esi, esi
0x1000a465  jnz     short loc_1000A475
0x1000a467  mov     eax, [ebp+var_228]
0x1000a46d  cmp     dword ptr [ebp+Data], eax
0x1000a473  jz      short loc_1000A4A3
0x1000a475  mov     eax, [ebp+var_210]
0x1000a47b  push    dword ptr [eax]; hKey
0x1000a47d  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1000a483  inc     edi
0x1000a484  cmp     edi, [ebp+cSubKeys]
0x1000a48a  jb      loc_1000A3D8
0x1000a490  jmp     short loc_1000A4A3
0x1000a492  mov     eax, [ebp+var_210]
0x1000a498  push    dword ptr [eax]; hKey
0x1000a49a  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1000a4a0  push    0Dh
0x1000a4a2  pop     esi
0x1000a4a3  cmp     edi, [ebp+cSubKeys]
0x1000a4a9  jnb     short loc_1000A4B9
0x1000a4ab  mov     edi, [ebp+var_208]
0x1000a4b1  test    esi, esi
0x1000a4b3  jnz     short loc_1000A4E0
0x1000a4b5  mov     [edi], ebx
0x1000a4b7  jmp     short loc_1000A4E0
0x1000a4b9  push    ebx; lpMem
0x1000a4ba  push    0; dwFlags
0x1000a4bc  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000a4c2  push    eax; hHeap
0x1000a4c3  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000a4c9  jmp     short loc_1000A4DA
0x1000a4cb  mov     [ebp+cchName], 0FFFFFFFFh
0x1000a4d5  mov     esi, 216h
0x1000a4da  mov     edi, [ebp+var_208]
0x1000a4e0  push    [ebp+phkResult]; hKey
0x1000a4e6  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1000a4ec  cmp     dword ptr [edi], 0
0x1000a4ef  jz      short loc_1000A4F5
0x1000a4f1  xor     esi, esi
0x1000a4f3  jmp     short loc_1000A4FF
0x1000a4f5  test    esi, esi
0x1000a4f7  mov     eax, 103h
0x1000a4fc  cmovz   esi, eax
0x1000a4ff  mov     eax, esi
0x1000a501  pop     esi
0x1000a502  mov     ecx, [ebp+var_4]
0x1000a505  pop     edi
0x1000a506  xor     ecx, ebp; StackCookie
0x1000a508  pop     ebx
0x1000a509  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000a50e  leave
0x1000a50f  retn    8
```
