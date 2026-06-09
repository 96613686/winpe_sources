# _lambda_d1e543e32deb761d4b0a6b2d9b3a008a_::operator()

- ea: `0x140008e50`
- end: `0x140008fee`
- name: `_lambda_d1e543e32deb761d4b0a6b2d9b3a008a_::operator()`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140008dc0`

## callees

- `0x140008e50`
- `0x140009300`
- `0x140009510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008f66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008f79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008f79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008ed7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008f3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008ed7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008f3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008f01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008f5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008f98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008fd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008f01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008f5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008f98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008fd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008ef1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008ef1`

## string_xrefs

- `0x140008e5b`: `Configs`

## pseudocode

```c
__int64 __fastcall lambda_d1e543e32deb761d4b0a6b2d9b3a008a_::operator()(__int64 *a1)
{
  __int64 v1; // r8
  int v3; // ebx
  HKEY v4; // rbx
  WCHAR *v5; // rbx
  LSTATUS v6; // eax
  unsigned int v7; // edi
  LPCWSTR *v9; // rdx
  LSTATUS v10; // eax
  DWORD LastError; // edi
  LPCWSTR lpSubKey[7]; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+10h] BYREF

  v1 = *a1;
  hKey = 0;
  memset(lpSubKey, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *(_QWORD *)(v1 + 8),
         L"Configs");
  if ( v3 < 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v3;
  }
  else
  {
    v4 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v4);
      SetLastError(LastError);
    }
    v5 = (WCHAR *)lpSubKey[0];
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
LABEL_7:
      if ( v5 )
        CoTaskMemFree(v5);
      if ( hKey )
        RegCloseKey(hKey);
      return v7;
    }
    v9 = (LPCWSTR *)a1[1];
    phkResult = 0;
    v10 = RegOpenKeyExW(hKey, *v9, 0, 0x20019u, &phkResult);
    v7 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_7;
    }
    *(_BYTE *)a1[2] = 1;
    if ( phkResult )
      RegCloseKey(phkResult);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x140008e50  push    rbx
0x140008e52  push    rbp
0x140008e53  push    rsi
0x140008e54  sub     rsp, 50h
0x140008e58  mov     r8, [rcx]
0x140008e5b  lea     r9, aConfigs; "Configs"
0x140008e62  xor     ebp, ebp
0x140008e64  lea     rdx, aSS; "%s\\%s"
0x140008e6b  mov     rsi, rcx
0x140008e6e  mov     [rsp+68h+hKey], rbp
0x140008e73  lea     rcx, [rsp+68h+lpSubKey]
0x140008e78  mov     [rsp+68h+lpSubKey], rbp
0x140008e7d  mov     r8, [r8+8]
0x140008e81  mov     [rsp+68h+var_30], rbp
0x140008e86  mov     [rsp+68h+var_28], rbp
0x140008e8b  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x140008e90  mov     ebx, eax
0x140008e92  test    eax, eax
0x140008e94  js      loc_140008F84
0x140008e9a  mov     rbx, [rsp+68h+hKey]
0x140008e9f  mov     [rsp+68h+arg_10], rdi
0x140008ea7  test    rbx, rbx
0x140008eaa  jnz     loc_140008F66
0x140008eb0  mov     rbx, [rsp+68h+lpSubKey]
0x140008eb5  lea     rax, [rsp+68h+hKey]
0x140008eba  mov     rdx, rbx; lpSubKey
0x140008ebd  mov     [rsp+68h+hKey], rbp
0x140008ec2  mov     r9d, 20019h; samDesired
0x140008ec8  mov     [rsp+68h+phkResult], rax; phkResult
0x140008ecd  xor     r8d, r8d; ulOptions
0x140008ed0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140008ed7  call    cs:__imp_RegOpenKeyExW
0x140008edd  mov     edi, eax
0x140008edf  test    eax, eax
0x140008ee1  jz      short loc_140008F19
0x140008ee3  jg      loc_140008FE0
0x140008ee9  test    rbx, rbx
0x140008eec  jz      short loc_140008EF7
0x140008eee  mov     rcx, rbx; pv
0x140008ef1  call    cs:__imp_CoTaskMemFree
0x140008ef7  mov     rcx, [rsp+68h+hKey]; hKey
0x140008efc  test    rcx, rcx
0x140008eff  jz      short loc_140008F07
0x140008f01  call    cs:__imp_RegCloseKey
0x140008f07  mov     eax, edi
0x140008f09  mov     rdi, [rsp+68h+arg_10]
0x140008f11  add     rsp, 50h
0x140008f15  pop     rsi
0x140008f16  pop     rbp
0x140008f17  pop     rbx
0x140008f18  retn
0x140008f19  mov     rdx, [rsi+8]
0x140008f1d  lea     rax, [rsp+68h+arg_8]
0x140008f22  mov     rcx, [rsp+68h+hKey]; hKey
0x140008f27  mov     r9d, 20019h; samDesired
0x140008f2d  mov     [rsp+68h+arg_8], rbp
0x140008f32  xor     r8d, r8d; ulOptions
0x140008f35  mov     [rsp+68h+phkResult], rax; phkResult
0x140008f3a  mov     rdx, [rdx]; lpSubKey
0x140008f3d  call    cs:__imp_RegOpenKeyExW
0x140008f43  mov     edi, eax
0x140008f45  test    eax, eax
0x140008f47  jz      short loc_140008FA8
0x140008f49  jle     short loc_140008F54
0x140008f4b  movzx   edi, ax
0x140008f4e  or      edi, 80070000h
0x140008f54  mov     rcx, [rsp+68h+arg_8]; hKey
0x140008f59  test    rcx, rcx
0x140008f5c  jz      short loc_140008EE9
0x140008f5e  call    cs:__imp_RegCloseKey
0x140008f64  jmp     short loc_140008EE9
0x140008f66  call    cs:__imp_GetLastError
0x140008f6c  mov     rcx, rbx; hKey
0x140008f6f  mov     edi, eax
0x140008f71  call    cs:__imp_RegCloseKey
0x140008f77  mov     ecx, edi; dwErrCode
0x140008f79  call    cs:__imp_SetLastError
0x140008f7f  jmp     loc_140008EB0
0x140008f84  lea     rcx, [rsp+68h+lpSubKey]
0x140008f89  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x140008f8e  mov     rcx, [rsp+68h+hKey]; hKey
0x140008f93  test    rcx, rcx
0x140008f96  jz      short loc_140008F9E
0x140008f98  call    cs:__imp_RegCloseKey
0x140008f9e  mov     eax, ebx
0x140008fa0  add     rsp, 50h
0x140008fa4  pop     rsi
0x140008fa5  pop     rbp
0x140008fa6  pop     rbx
0x140008fa7  retn
0x140008fa8  mov     rax, [rsi+10h]
0x140008fac  mov     byte ptr [rax], 1
0x140008faf  mov     rcx, [rsp+68h+arg_8]; hKey
0x140008fb4  test    rcx, rcx
0x140008fb7  jz      short loc_140008FBF
0x140008fb9  call    cs:__imp_RegCloseKey
0x140008fbf  lea     rcx, [rsp+68h+lpSubKey]
0x140008fc4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x140008fc9  mov     rcx, [rsp+68h+hKey]; hKey
0x140008fce  test    rcx, rcx
0x140008fd1  jz      short loc_140008FD9
0x140008fd3  call    cs:__imp_RegCloseKey
0x140008fd9  xor     eax, eax
0x140008fdb  jmp     loc_140008F09
0x140008fe0  movzx   edi, ax
0x140008fe3  or      edi, 80070000h
0x140008fe9  jmp     loc_140008EE9
```
