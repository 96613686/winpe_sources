# IsCompatibleHostingModelEnabled(ushort const *,int &)

- ea: `0x1800c4d04`
- end: `0x1800c4faa`
- name: `?IsCompatibleHostingModelEnabled@@YAJPEBGAEAH@Z`
- size: `678`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c4a3c`
- `0x1800c6954`

## callees

- `0x1800c4d04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4df9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4e69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4ecf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4f51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4df9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4e69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4ecf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4f51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4d87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4ded`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4e5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4ec3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4f45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4d87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4ded`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4e5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4ec3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4f45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4d53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4dc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4e33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4e99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4f07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4d53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4dc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4e33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4e99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4f07`

## string_xrefs

- `0x1800c4e29`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`
- `0x1800c4e8f`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`

## pseudocode

```c
__int64 __fastcall IsCompatibleHostingModelEnabled(LPCWSTR lpValueName, int *a2)
{
  BOOL v4; // edi
  LSTATUS v5; // ebx
  LSTATUS v6; // ebx
  LSTATUS v8; // ebx
  LSTATUS v9; // ebx
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  LSTATUS v12; // esi
  int v13; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+50h] BYREF
  DWORD Type; // [rsp+98h] [rbp+58h] BYREF

  Type = 0;
  hKey = 0;
  cbData = 0;
  v4 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20019u, &hKey)
    && ((cbData = 0, v5 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v5) || v5 == 234)
    && Type == 1
    || !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20219u, &hKey)
    && ((cbData = 0, v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v6) || v6 == 234)
    && Type == 1 )
  {
    *a2 = 0;
    return 0;
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20019u,
          &hKey)
    && ((cbData = 0, v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v8) || v8 == 234)
    && Type == 1
    || !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20219u,
          &hKey)
    && ((cbData = 0, v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v9) || v9 == 234)
    && Type == 1 )
  {
    *a2 = 1;
    return 0;
  }
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, &hKey);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 <= 0 )
      return v11;
    v13 = (unsigned __int16)v10;
    return v13 | 0x80070000;
  }
  *(_DWORD *)Data = 0;
  cbData = 4;
  v11 = 0;
  v12 = RegQueryValueExW(hKey, L"DefaultSecuredHost", 0, &Type, Data, &cbData);
  RegCloseKey(hKey);
  if ( !v12 )
  {
    if ( Type == 4 )
      v4 = *(_DWORD *)Data == 0;
    goto LABEL_25;
  }
  if ( v12 != 2 )
  {
    if ( v12 <= 0 )
      return (unsigned int)v12;
    v13 = (unsigned __int16)v12;
    return v13 | 0x80070000;
  }
LABEL_25:
  *a2 = v4;
  return v11;
}

```

## disassembly

```asm
0x1800c4d04  mov     [rsp-38h+arg_0], rbx
0x1800c4d09  push    rbp
0x1800c4d0a  push    rsi
0x1800c4d0b  push    rdi
0x1800c4d0c  push    r12
0x1800c4d0e  push    r13
0x1800c4d10  push    r14
0x1800c4d12  push    r15
0x1800c4d14  mov     rbp, rsp
0x1800c4d17  sub     rsp, 40h
0x1800c4d1b  xor     r15d, r15d
0x1800c4d1e  lea     rax, [rbp+hKey]
0x1800c4d22  mov     r14, rdx
0x1800c4d25  mov     [rbp+Type], r15d
0x1800c4d29  mov     rsi, rcx
0x1800c4d2c  mov     [rbp+hKey], r15
0x1800c4d30  mov     r13, 0FFFFFFFF80000002h
0x1800c4d37  mov     [rbp+cbData], r15d
0x1800c4d3b  mov     rcx, r13; hKey
0x1800c4d3e  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c4d43  mov     r9d, 20019h; samDesired
0x1800c4d49  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x1800c4d50  xor     r8d, r8d; ulOptions
0x1800c4d53  call    cs:__imp_RegOpenKeyExW
0x1800c4d59  lea     edi, [r15+1]
0x1800c4d5d  mov     r12d, 0EAh
0x1800c4d63  test    eax, eax
0x1800c4d65  jnz     short loc_1800C4DA7
0x1800c4d67  mov     rcx, [rbp+hKey]; hKey
0x1800c4d6b  lea     rax, [rbp+cbData]
0x1800c4d6f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c4d74  lea     r9, [rbp+Type]; lpType
0x1800c4d78  xor     r8d, r8d; lpReserved
0x1800c4d7b  mov     [rsp+40h+phkResult], r15; lpData
0x1800c4d80  mov     rdx, rsi; lpValueName
0x1800c4d83  mov     [rbp+cbData], r15d
0x1800c4d87  call    cs:__imp_RegQueryValueExW
0x1800c4d8d  mov     rcx, [rbp+hKey]; hKey
0x1800c4d91  mov     ebx, eax
0x1800c4d93  call    cs:__imp_RegCloseKey
0x1800c4d99  test    ebx, ebx
0x1800c4d9b  jz      short loc_1800C4DA2
0x1800c4d9d  cmp     ebx, r12d
0x1800c4da0  jnz     short loc_1800C4DA7
0x1800c4da2  cmp     [rbp+Type], edi
0x1800c4da5  jz      short loc_1800C4E0D
0x1800c4da7  lea     rax, [rbp+hKey]
0x1800c4dab  mov     r9d, 20219h; samDesired
0x1800c4db1  xor     r8d, r8d; ulOptions
0x1800c4db4  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c4db9  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x1800c4dc0  mov     rcx, r13; hKey
0x1800c4dc3  call    cs:__imp_RegOpenKeyExW
0x1800c4dc9  test    eax, eax
0x1800c4dcb  jnz     short loc_1800C4E17
0x1800c4dcd  mov     rcx, [rbp+hKey]; hKey
0x1800c4dd1  lea     rax, [rbp+cbData]
0x1800c4dd5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c4dda  lea     r9, [rbp+Type]; lpType
0x1800c4dde  xor     r8d, r8d; lpReserved
0x1800c4de1  mov     [rsp+40h+phkResult], r15; lpData
0x1800c4de6  mov     rdx, rsi; lpValueName
0x1800c4de9  mov     [rbp+cbData], r15d
0x1800c4ded  call    cs:__imp_RegQueryValueExW
0x1800c4df3  mov     rcx, [rbp+hKey]; hKey
0x1800c4df7  mov     ebx, eax
0x1800c4df9  call    cs:__imp_RegCloseKey
0x1800c4dff  test    ebx, ebx
0x1800c4e01  jz      short loc_1800C4E08
0x1800c4e03  cmp     ebx, r12d
0x1800c4e06  jnz     short loc_1800C4E17
0x1800c4e08  cmp     [rbp+Type], edi
0x1800c4e0b  jnz     short loc_1800C4E17
0x1800c4e0d  mov     [r14], r15d
0x1800c4e10  xor     eax, eax
0x1800c4e12  jmp     loc_1800C4F92
0x1800c4e17  lea     rax, [rbp+hKey]
0x1800c4e1b  mov     r9d, 20019h; samDesired
0x1800c4e21  xor     r8d, r8d; ulOptions
0x1800c4e24  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c4e29  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x1800c4e30  mov     rcx, r13; hKey
0x1800c4e33  call    cs:__imp_RegOpenKeyExW
0x1800c4e39  test    eax, eax
0x1800c4e3b  jnz     short loc_1800C4E7D
0x1800c4e3d  mov     rcx, [rbp+hKey]; hKey
0x1800c4e41  lea     rax, [rbp+cbData]
0x1800c4e45  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c4e4a  lea     r9, [rbp+Type]; lpType
0x1800c4e4e  xor     r8d, r8d; lpReserved
0x1800c4e51  mov     [rsp+40h+phkResult], r15; lpData
0x1800c4e56  mov     rdx, rsi; lpValueName
0x1800c4e59  mov     [rbp+cbData], r15d
0x1800c4e5d  call    cs:__imp_RegQueryValueExW
0x1800c4e63  mov     rcx, [rbp+hKey]; hKey
0x1800c4e67  mov     ebx, eax
0x1800c4e69  call    cs:__imp_RegCloseKey
0x1800c4e6f  test    ebx, ebx
0x1800c4e71  jz      short loc_1800C4E78
0x1800c4e73  cmp     ebx, r12d
0x1800c4e76  jnz     short loc_1800C4E7D
0x1800c4e78  cmp     [rbp+Type], edi
0x1800c4e7b  jz      short loc_1800C4EE3
0x1800c4e7d  lea     rax, [rbp+hKey]
0x1800c4e81  mov     r9d, 20219h; samDesired
0x1800c4e87  xor     r8d, r8d; ulOptions
0x1800c4e8a  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c4e8f  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x1800c4e96  mov     rcx, r13; hKey
0x1800c4e99  call    cs:__imp_RegOpenKeyExW
0x1800c4e9f  test    eax, eax
0x1800c4ea1  jnz     short loc_1800C4EEB
0x1800c4ea3  mov     rcx, [rbp+hKey]; hKey
0x1800c4ea7  lea     rax, [rbp+cbData]
0x1800c4eab  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c4eb0  lea     r9, [rbp+Type]; lpType
0x1800c4eb4  xor     r8d, r8d; lpReserved
0x1800c4eb7  mov     [rsp+40h+phkResult], r15; lpData
0x1800c4ebc  mov     rdx, rsi; lpValueName
0x1800c4ebf  mov     [rbp+cbData], r15d
0x1800c4ec3  call    cs:__imp_RegQueryValueExW
0x1800c4ec9  mov     rcx, [rbp+hKey]; hKey
0x1800c4ecd  mov     ebx, eax
0x1800c4ecf  call    cs:__imp_RegCloseKey
0x1800c4ed5  test    ebx, ebx
0x1800c4ed7  jz      short loc_1800C4EDE
0x1800c4ed9  cmp     ebx, r12d
0x1800c4edc  jnz     short loc_1800C4EEB
0x1800c4ede  cmp     [rbp+Type], edi
0x1800c4ee1  jnz     short loc_1800C4EEB
0x1800c4ee3  mov     [r14], edi
0x1800c4ee6  jmp     loc_1800C4E10
0x1800c4eeb  lea     rax, [rbp+hKey]
0x1800c4eef  mov     r9d, 20019h; samDesired
0x1800c4ef5  xor     r8d, r8d; ulOptions
0x1800c4ef8  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c4efd  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\WBEM\\CIMOM"
0x1800c4f04  mov     rcx, r13; hKey
0x1800c4f07  call    cs:__imp_RegOpenKeyExW
0x1800c4f0d  mov     ebx, eax
0x1800c4f0f  test    eax, eax
0x1800c4f11  jnz     short loc_1800C4F85
0x1800c4f13  mov     rcx, [rbp+hKey]; hKey
0x1800c4f17  lea     rax, [rbp+cbData]
0x1800c4f1b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c4f20  lea     r9, [rbp+Type]; lpType
0x1800c4f24  lea     rax, [rbp+Data]
0x1800c4f28  mov     dword ptr [rbp+Data], r15d
0x1800c4f2c  xor     r8d, r8d; lpReserved
0x1800c4f2f  mov     [rsp+40h+phkResult], rax; lpData
0x1800c4f34  lea     rdx, aDefaultsecured; "DefaultSecuredHost"
0x1800c4f3b  mov     [rbp+cbData], 4
0x1800c4f42  mov     ebx, r15d
0x1800c4f45  call    cs:__imp_RegQueryValueExW
0x1800c4f4b  mov     rcx, [rbp+hKey]; hKey
0x1800c4f4f  mov     esi, eax
0x1800c4f51  call    cs:__imp_RegCloseKey
0x1800c4f57  test    esi, esi
0x1800c4f59  jnz     short loc_1800C4F6E
0x1800c4f5b  cmp     [rbp+Type], 4
0x1800c4f5f  jnz     short loc_1800C4F73
0x1800c4f61  cmp     dword ptr [rbp+Data], r15d
0x1800c4f65  mov     edi, r15d
0x1800c4f68  setz    dil
0x1800c4f6c  jmp     short loc_1800C4F73
0x1800c4f6e  cmp     esi, 2
0x1800c4f71  jnz     short loc_1800C4F78
0x1800c4f73  mov     [r14], edi
0x1800c4f76  jmp     short loc_1800C4F90
0x1800c4f78  test    esi, esi
0x1800c4f7a  jg      short loc_1800C4F80
0x1800c4f7c  mov     ebx, esi
0x1800c4f7e  jmp     short loc_1800C4F90
0x1800c4f80  movzx   ebx, si
0x1800c4f83  jmp     short loc_1800C4F8A
0x1800c4f85  jle     short loc_1800C4F90
0x1800c4f87  movzx   ebx, ax
0x1800c4f8a  or      ebx, 80070000h
0x1800c4f90  mov     eax, ebx
0x1800c4f92  mov     rbx, [rsp+40h+arg_0]
0x1800c4f9a  add     rsp, 40h
0x1800c4f9e  pop     r15
0x1800c4fa0  pop     r14
0x1800c4fa2  pop     r13
0x1800c4fa4  pop     r12
0x1800c4fa6  pop     rdi
0x1800c4fa7  pop     rsi
0x1800c4fa8  pop     rbp
0x1800c4fa9  retn
```
