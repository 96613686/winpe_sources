# SHCopyKeyW

- ea: `0x18004f280`
- end: `0x18004f515`
- name: `SHCopyKeyW`
- size: `661`
- prototype: `LSTATUS __stdcall(HKEY hkeySrc, LPCWSTR pszSrcSubKey, HKEY hkeyDest, DWORD fReserved)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004f200`
- `0x18004f280`

## callees

- `0x18004f280`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f437`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f437`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4c7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004f341`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004f341`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004f487`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004f487`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004f420`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004f420`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f392`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f392`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f3bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f4ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f3bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f4ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f2d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f2d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f4af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f4af`

## pseudocode

```c
LSTATUS __stdcall SHCopyKeyW(HKEY hkeySrc, LPCWSTR pszSrcSubKey, HKEY hkeyDest, DWORD fReserved)
{
  LSTATUS v7; // ebx
  DWORD v8; // ebx
  LSTATUS v9; // edi
  BYTE *v10; // rbx
  DWORD v11; // r14d
  DWORD i; // esi
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchClass; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hkeyDesta; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Class[264]; // [rsp+290h] [rbp+190h] BYREF

  hKey = 0;
  if ( pszSrcSubKey )
  {
    v7 = RegOpenKeyExW(hkeySrc, pszSrcSubKey, 0, 0x20019u, &hKey);
    goto LABEL_6;
  }
  if ( !hkeySrc )
  {
    v7 = 87;
LABEL_6:
    if ( v7 )
      return v7;
    goto LABEL_7;
  }
  hKey = hkeySrc;
LABEL_7:
  Type = 0;
  cchName = 260;
  v8 = 0;
  cchClass = 260;
  do
  {
    v9 = RegEnumKeyExW(hKey, v8, Name, &cchName, 0, Class, &cchClass, 0);
    if ( v9 )
      break;
    hkeyDesta = 0;
    dwDisposition = 0;
    v9 = RegCreateKeyExW(hkeyDest, Name, 0, Class, 0, 0x20006u, 0, &hkeyDesta, &dwDisposition);
    if ( v9 )
      break;
    v9 = SHCopyKeyW(hKey, Name, hkeyDesta, fReserved);
    RegCloseKey(hkeyDesta);
    ++v8;
    cchName = 260;
    cchClass = 260;
  }
  while ( !v9 );
  if ( v9 == 259 )
  {
    dwDisposition = 0;
    v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, &dwDisposition, 0, 0);
    if ( !v9 )
    {
      v10 = (BYTE *)LocalAlloc(0x40u, dwDisposition);
      if ( v10 )
      {
        v11 = dwDisposition;
        for ( i = 0; ; ++i )
        {
          cchName = 260;
          v9 = RegEnumValueW(hKey, i, Name, &cchName, 0, &Type, v10, &dwDisposition);
          if ( v9 )
            break;
          v9 = RegSetValueExW(hkeyDest, Name, 0, Type, v10, dwDisposition);
          if ( v9 )
            break;
          dwDisposition = v11;
        }
        LocalFree(v10);
      }
      else
      {
        v9 = 14;
      }
    }
  }
  v7 = 0;
  if ( v9 != 259 )
    v7 = v9;
  if ( pszSrcSubKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18004f280  push    rbp
0x18004f282  push    rbx
0x18004f283  push    rsi
0x18004f284  push    rdi
0x18004f285  push    r12
0x18004f287  push    r13
0x18004f289  push    r14
0x18004f28b  push    r15
0x18004f28d  lea     rbp, [rsp-3B8h]
0x18004f295  sub     rsp, 4B8h
0x18004f29c  mov     rax, cs:__security_cookie
0x18004f2a3  xor     rax, rsp
0x18004f2a6  mov     [rbp+3F0h+var_50], rax
0x18004f2ad  xor     r13d, r13d
0x18004f2b0  mov     esi, r9d
0x18004f2b3  mov     [rsp+4F0h+hKey], r13
0x18004f2b8  mov     r12, r8
0x18004f2bb  mov     r15, rdx
0x18004f2be  test    rdx, rdx
0x18004f2c1  jz      short loc_18004F2E0
0x18004f2c3  lea     rax, [rsp+4F0h+hKey]
0x18004f2c8  mov     r9d, 20019h; samDesired
0x18004f2ce  xor     r8d, r8d; ulOptions
0x18004f2d1  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18004f2d6  call    cs:__imp_RegOpenKeyExW
0x18004f2dc  mov     ebx, eax
0x18004f2de  jmp     short loc_18004F2F1
0x18004f2e0  test    rcx, rcx
0x18004f2e3  jz      short loc_18004F2EC
0x18004f2e5  mov     [rsp+4F0h+hKey], rcx
0x18004f2ea  jmp     short loc_18004F2F9
0x18004f2ec  mov     ebx, 57h ; 'W'
0x18004f2f1  test    ebx, ebx
0x18004f2f3  jnz     loc_18004F4F0
0x18004f2f9  mov     r14d, 104h
0x18004f2ff  mov     [rsp+4F0h+Type], r13d
0x18004f304  mov     [rsp+4F0h+cchName], r14d
0x18004f309  mov     ebx, r13d
0x18004f30c  mov     [rsp+4F0h+cchClass], r14d
0x18004f311  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18004f316  lea     rax, [rsp+4F0h+cchClass]
0x18004f31b  mov     [rsp+4F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18004f320  lea     r9, [rsp+4F0h+cchName]; lpcchName
0x18004f325  mov     [rsp+4F0h+lpcchClass], rax; lpcchClass
0x18004f32a  lea     r8, [rbp+3F0h+Name]; lpName
0x18004f32e  lea     rax, [rbp+3F0h+Class]
0x18004f335  mov     edx, ebx; dwIndex
0x18004f337  mov     [rsp+4F0h+lpClass], rax; lpClass
0x18004f33c  mov     [rsp+4F0h+phkResult], r13; lpReserved
0x18004f341  call    cs:__imp_RegEnumKeyExW
0x18004f347  mov     edi, eax
0x18004f349  test    eax, eax
0x18004f34b  jnz     loc_18004F3D5
0x18004f351  lea     rax, [rsp+4F0h+dwDisposition]
0x18004f356  mov     [rsp+4F0h+hkeyDest], r13
0x18004f35b  mov     [rsp+4F0h+lpdwDisposition], rax; lpdwDisposition
0x18004f360  lea     r9, [rbp+3F0h+Class]; lpClass
0x18004f367  lea     rax, [rsp+4F0h+hkeyDest]
0x18004f36c  mov     [rsp+4F0h+dwDisposition], r13d
0x18004f371  mov     [rsp+4F0h+lpftLastWriteTime], rax; phkResult
0x18004f376  lea     rdx, [rbp+3F0h+Name]; lpSubKey
0x18004f37a  mov     [rsp+4F0h+lpcchClass], r13; lpSecurityAttributes
0x18004f37f  xor     r8d, r8d; Reserved
0x18004f382  mov     dword ptr [rsp+4F0h+lpClass], 20006h; samDesired
0x18004f38a  mov     rcx, r12; hKey
0x18004f38d  mov     dword ptr [rsp+4F0h+phkResult], r13d; dwOptions
0x18004f392  call    cs:__imp_RegCreateKeyExW
0x18004f398  mov     edi, eax
0x18004f39a  test    eax, eax
0x18004f39c  jnz     short loc_18004F3D5
0x18004f39e  mov     r8, [rsp+4F0h+hkeyDest]; hkeyDest
0x18004f3a3  lea     rdx, [rbp+3F0h+Name]; pszSrcSubKey
0x18004f3a7  mov     rcx, [rsp+4F0h+hKey]; hkeySrc
0x18004f3ac  mov     r9d, esi; fReserved
0x18004f3af  call    SHCopyKeyW
0x18004f3b4  mov     rcx, [rsp+4F0h+hkeyDest]; hKey
0x18004f3b9  mov     edi, eax
0x18004f3bb  call    cs:__imp_RegCloseKey
0x18004f3c1  inc     ebx
0x18004f3c3  mov     [rsp+4F0h+cchName], r14d
0x18004f3c8  mov     [rsp+4F0h+cchClass], r14d
0x18004f3cd  test    edi, edi
0x18004f3cf  jz      loc_18004F311
0x18004f3d5  cmp     edi, 103h
0x18004f3db  jnz     loc_18004F4D4
0x18004f3e1  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18004f3e6  lea     rax, [rsp+4F0h+dwDisposition]
0x18004f3eb  mov     [rsp+4F0h+var_498], r13; lpftLastWriteTime
0x18004f3f0  xor     r9d, r9d; lpReserved
0x18004f3f3  mov     [rsp+4F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18004f3f8  xor     r8d, r8d; lpcchClass
0x18004f3fb  mov     [rsp+4F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18004f400  xor     edx, edx; lpClass
0x18004f402  mov     [rsp+4F0h+lpdwDisposition], r13; lpcbMaxValueNameLen
0x18004f407  mov     [rsp+4F0h+lpftLastWriteTime], r13; lpcValues
0x18004f40c  mov     [rsp+4F0h+lpcchClass], r13; lpcbMaxClassLen
0x18004f411  mov     [rsp+4F0h+lpClass], r13; lpcbMaxSubKeyLen
0x18004f416  mov     [rsp+4F0h+phkResult], r13; lpcSubKeys
0x18004f41b  mov     [rsp+4F0h+dwDisposition], r13d
0x18004f420  call    cs:__imp_RegQueryInfoKeyW
0x18004f426  mov     edi, eax
0x18004f428  test    eax, eax
0x18004f42a  jnz     loc_18004F4D4
0x18004f430  mov     edx, [rsp+4F0h+dwDisposition]; uBytes
0x18004f434  lea     ecx, [rax+40h]; uFlags
0x18004f437  call    cs:__imp_LocalAlloc
0x18004f43d  mov     rbx, rax
0x18004f440  test    rax, rax
0x18004f443  jz      loc_18004F4CF
0x18004f449  mov     r14d, [rsp+4F0h+dwDisposition]
0x18004f44e  mov     esi, r13d
0x18004f451  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18004f456  lea     rax, [rsp+4F0h+dwDisposition]
0x18004f45b  mov     [rsp+4F0h+lpftLastWriteTime], rax; lpcbData
0x18004f460  lea     r9, [rsp+4F0h+cchName]; lpcchValueName
0x18004f465  lea     rax, [rsp+4F0h+Type]
0x18004f46a  mov     [rsp+4F0h+lpcchClass], rbx; lpData
0x18004f46f  mov     [rsp+4F0h+lpClass], rax; lpType
0x18004f474  lea     r8, [rbp+3F0h+Name]; lpValueName
0x18004f478  mov     edx, esi; dwIndex
0x18004f47a  mov     [rsp+4F0h+phkResult], r13; lpReserved
0x18004f47f  mov     [rsp+4F0h+cchName], 104h
0x18004f487  call    cs:__imp_RegEnumValueW
0x18004f48d  mov     edi, eax
0x18004f48f  test    eax, eax
0x18004f491  jnz     short loc_18004F4C4
0x18004f493  mov     eax, [rsp+4F0h+dwDisposition]
0x18004f497  lea     rdx, [rbp+3F0h+Name]; lpValueName
0x18004f49b  mov     r9d, [rsp+4F0h+Type]; dwType
0x18004f4a0  xor     r8d, r8d; Reserved
0x18004f4a3  mov     dword ptr [rsp+4F0h+lpClass], eax; cbData
0x18004f4a7  mov     rcx, r12; hKey
0x18004f4aa  mov     [rsp+4F0h+phkResult], rbx; lpData
0x18004f4af  call    cs:__imp_RegSetValueExW
0x18004f4b5  mov     edi, eax
0x18004f4b7  test    eax, eax
0x18004f4b9  jnz     short loc_18004F4C4
0x18004f4bb  inc     esi
0x18004f4bd  mov     [rsp+4F0h+dwDisposition], r14d
0x18004f4c2  jmp     short loc_18004F451
0x18004f4c4  mov     rcx, rbx; hMem
0x18004f4c7  call    cs:__imp_LocalFree
0x18004f4cd  jmp     short loc_18004F4D4
0x18004f4cf  mov     edi, 0Eh
0x18004f4d4  cmp     edi, 103h
0x18004f4da  mov     ebx, r13d
0x18004f4dd  cmovnz  ebx, edi
0x18004f4e0  test    r15, r15
0x18004f4e3  jz      short loc_18004F4F0
0x18004f4e5  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18004f4ea  call    cs:__imp_RegCloseKey
0x18004f4f0  mov     eax, ebx
0x18004f4f2  mov     rcx, [rbp+3F0h+var_50]
0x18004f4f9  xor     rcx, rsp; StackCookie
0x18004f4fc  call    __security_check_cookie
0x18004f501  add     rsp, 4B8h
0x18004f508  pop     r15
0x18004f50a  pop     r14
0x18004f50c  pop     r13
0x18004f50e  pop     r12
0x18004f510  pop     rdi
0x18004f511  pop     rsi
0x18004f512  pop     rbx
0x18004f513  pop     rbp
0x18004f514  retn
```
