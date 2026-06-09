# RegCopyKeyRecursive

- ea: `0x18003f400`
- end: `0x18003f75c`
- name: `RegCopyKeyRecursive`
- size: `860`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003f400`
- `0x18003f91c`

## callees

- `0x18003f400`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003f666`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003f666`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f707`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f707`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f716`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f505`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f505`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f4ad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f4ad`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f6d2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f6d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f690`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f690`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f46d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f46d`
- `KERNEL32!GlobalAlloc` at `0x18003f585`
- `KERNEL32!GlobalAlloc` at `0x18003f602`
- `KERNEL32!GlobalAlloc` at `0x18003f615`
- `KERNEL32!GlobalAlloc` at `0x18003f585`
- `KERNEL32!GlobalAlloc` at `0x18003f602`
- `KERNEL32!GlobalAlloc` at `0x18003f615`
- `KERNEL32!GlobalFree` at `0x18003f724`
- `KERNEL32!GlobalFree` at `0x18003f732`
- `KERNEL32!GlobalFree` at `0x18003f740`
- `KERNEL32!GlobalFree` at `0x18003f724`
- `KERNEL32!GlobalFree` at `0x18003f732`
- `KERNEL32!GlobalFree` at `0x18003f740`

## pseudocode

```c
__int64 __fastcall RegCopyKeyRecursive(HKEY a1, const WCHAR *a2, HKEY a3, const WCHAR *a4)
{
  WCHAR *v6; // rsi
  WCHAR *v7; // r15
  BYTE *v8; // r14
  unsigned int v9; // ebx
  DWORD v10; // ecx
  int v11; // edx
  unsigned __int64 v12; // rax
  unsigned int v13; // ecx
  DWORD v14; // edx
  int v15; // ecx
  unsigned __int64 v16; // rax
  unsigned int v17; // ecx
  DWORD i; // edi
  DWORD j; // edi
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-25h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-21h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-11h] BYREF
  DWORD cValues; // [rsp+80h] [rbp-9h] BYREF
  DWORD cchValueName; // [rsp+84h] [rbp-5h] BYREF
  DWORD Type; // [rsp+88h] [rbp-1h] BYREF
  DWORD cchName; // [rsp+8Ch] [rbp+3h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+7h] BYREF
  DWORD dwDisposition[18]; // [rsp+98h] [rbp+Fh] BYREF

  phkResult = 0;
  hKey = 0;
  dwDisposition[0] = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  v6 = 0;
  cbMaxValueLen = 0;
  v7 = 0;
  cValues = 0;
  v8 = 0;
  cSubKeys = 0;
  Type = 0;
  cbData = 0;
  cchValueName = 0;
  cchName = 0;
  v9 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &phkResult);
  if ( !v9 )
  {
    v9 = RegCreateKeyExW(a3, a4, 0, 0, 0, 0x2001Fu, 0, &hKey, dwDisposition);
    if ( !v9 )
    {
      v9 = RegQueryInfoKeyW(
             phkResult,
             0,
             0,
             0,
             &cSubKeys,
             &cbMaxSubKeyLen,
             0,
             &cValues,
             &cbMaxValueNameLen,
             &cbMaxValueLen,
             0,
             0);
      if ( !v9 )
      {
        v10 = cbMaxSubKeyLen + 1;
        if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
        {
          v10 = -1;
          v11 = -2147024362;
        }
        else
        {
          v11 = 0;
        }
        v9 = (unsigned __int16)v11;
        if ( (v11 & 0x1FFF0000) != 0x70000 )
          v9 = v11;
        if ( !v9 )
        {
          v12 = 2LL * v10;
          v13 = 2 * v10;
          if ( v12 > 0xFFFFFFFF )
            v13 = -1;
          v9 = v12 > 0xFFFFFFFF ? 0x80070216 : 0;
          if ( (v12 > 0xFFFFFFFF ? 0x70000 : 0) == 0x70000 )
            v9 = (unsigned __int16)v9;
          if ( !v9 )
          {
            v6 = (WCHAR *)GlobalAlloc(0, v13);
            if ( !v6 )
            {
LABEL_16:
              v9 = 14;
              goto LABEL_39;
            }
            v14 = cbMaxValueNameLen + 1;
            if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen )
            {
              v14 = -1;
              v15 = -2147024362;
            }
            else
            {
              v15 = 0;
            }
            v9 = (unsigned __int16)v15;
            if ( (v15 & 0x1FFF0000) != 0x70000 )
              v9 = v15;
            if ( !v9 )
            {
              v16 = 2LL * v14;
              v17 = 2 * v14;
              if ( v16 > 0xFFFFFFFF )
                v17 = -1;
              v9 = v16 > 0xFFFFFFFF ? 0x80070216 : 0;
              if ( (v16 > 0xFFFFFFFF ? 0x70000 : 0) == 0x70000 )
                v9 = (unsigned __int16)v9;
              if ( !v9 )
              {
                v7 = (WCHAR *)GlobalAlloc(0, v17);
                if ( !v7 )
                  goto LABEL_16;
                v8 = (BYTE *)GlobalAlloc(0, cbMaxValueLen);
                if ( !v8 )
                  goto LABEL_16;
                for ( i = 0; i < cValues; ++i )
                {
                  cchValueName = cbMaxValueNameLen + 1;
                  cbData = cbMaxValueLen;
                  v9 = RegEnumValueW(phkResult, i, v7, &cchValueName, 0, &Type, v8, &cbData);
                  if ( v9 )
                    goto LABEL_39;
                  v9 = RegSetValueExW(hKey, v7, 0, Type, v8, cbData);
                  if ( v9 )
                    goto LABEL_39;
                }
                for ( j = 0; j < cSubKeys; ++j )
                {
                  cchName = cbMaxSubKeyLen + 1;
                  v9 = RegEnumKeyExW(phkResult, j, v6, &cchName, 0, 0, 0, 0);
                  if ( v9 )
                    break;
                  v9 = RegCopyKeyRecursive(phkResult, v6, hKey, v6);
                  if ( v9 )
                    break;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_39:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    GlobalFree(v6);
  if ( v7 )
    GlobalFree(v7);
  if ( v8 )
    GlobalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x18003f400  push    rbp
0x18003f402  push    rbx
0x18003f403  push    rsi
0x18003f404  push    rdi
0x18003f405  push    r12
0x18003f407  push    r13
0x18003f409  push    r14
0x18003f40b  push    r15
0x18003f40d  lea     rbp, [rsp-1Fh]
0x18003f412  sub     rsp, 0A8h
0x18003f419  xor     r13d, r13d
0x18003f41c  lea     rax, [rbp+57h+var_68]
0x18003f420  mov     rdi, r9
0x18003f423  mov     [rbp+57h+var_68], r13
0x18003f427  mov     r12, r8
0x18003f42a  mov     [rbp+57h+hKey], r13
0x18003f42e  mov     r9d, 20019h; samDesired
0x18003f434  mov     [rbp+57h+dwDisposition], r13d
0x18003f438  xor     r8d, r8d; ulOptions
0x18003f43b  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18003f43f  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x18003f443  mov     esi, r13d
0x18003f446  mov     [rbp+57h+cbMaxValueLen], r13d
0x18003f44a  mov     r15d, r13d
0x18003f44d  mov     [rbp+57h+cValues], r13d
0x18003f451  mov     r14d, r13d
0x18003f454  mov     [rbp+57h+cSubKeys], r13d
0x18003f458  mov     [rbp+57h+Type], r13d
0x18003f45c  mov     [rbp+57h+cbData], r13d
0x18003f460  mov     [rbp+57h+cchValueName], r13d
0x18003f464  mov     [rbp+57h+cchName], r13d
0x18003f468  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003f46d  call    cs:__imp_RegOpenKeyExW
0x18003f473  mov     ebx, eax
0x18003f475  test    eax, eax
0x18003f477  jnz     loc_18003F6FE
0x18003f47d  lea     rax, [rbp+57h+dwDisposition]
0x18003f481  xor     r9d, r9d; lpClass
0x18003f484  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x18003f489  xor     r8d, r8d; Reserved
0x18003f48c  lea     rax, [rbp+57h+hKey]
0x18003f490  mov     rdx, rdi; lpSubKey
0x18003f493  mov     [rsp+0E0h+var_A8], rax; phkResult
0x18003f498  mov     rcx, r12; hKey
0x18003f49b  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18003f4a0  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x18003f4a8  mov     dword ptr [rsp+0E0h+phkResult], r13d; dwOptions
0x18003f4ad  call    cs:__imp_RegCreateKeyExW
0x18003f4b3  mov     ebx, eax
0x18003f4b5  test    eax, eax
0x18003f4b7  jnz     loc_18003F6FE
0x18003f4bd  mov     rcx, [rbp+57h+var_68]; hKey
0x18003f4c1  lea     rax, [rbp+57h+cbMaxValueLen]
0x18003f4c5  mov     [rsp+0E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18003f4ca  xor     r9d, r9d; lpReserved
0x18003f4cd  mov     [rsp+0E0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18003f4d2  xor     r8d, r8d; lpcchClass
0x18003f4d5  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18003f4da  xor     edx, edx; lpClass
0x18003f4dc  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18003f4e0  mov     [rsp+0E0h+lpdwDisposition], rax; lpcbMaxValueNameLen
0x18003f4e5  lea     rax, [rbp+57h+cValues]
0x18003f4e9  mov     [rsp+0E0h+var_A8], rax; lpcValues
0x18003f4ee  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18003f4f2  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpcbMaxClassLen
0x18003f4f7  mov     qword ptr [rsp+0E0h+samDesired], rax; lpcbMaxSubKeyLen
0x18003f4fc  lea     rax, [rbp+57h+cSubKeys]
0x18003f500  mov     [rsp+0E0h+phkResult], rax; lpcSubKeys
0x18003f505  call    cs:__imp_RegQueryInfoKeyW
0x18003f50b  mov     ebx, eax
0x18003f50d  test    eax, eax
0x18003f50f  jnz     loc_18003F6FE
0x18003f515  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18003f518  mov     edi, 0FFFFFFFFh
0x18003f51d  mov     r12d, 80070216h
0x18003f523  lea     ecx, [rax+1]
0x18003f526  cmp     ecx, eax
0x18003f528  jb      short loc_18003F52F
0x18003f52a  mov     edx, r13d
0x18003f52d  jmp     short loc_18003F534
0x18003f52f  mov     ecx, edi
0x18003f531  mov     edx, r12d
0x18003f534  mov     eax, edx
0x18003f536  movzx   ebx, dx
0x18003f539  mov     r8d, 1FFF0000h
0x18003f53f  mov     r9d, 70000h
0x18003f545  and     eax, r8d
0x18003f548  cmp     eax, r9d
0x18003f54b  cmovnz  ebx, edx
0x18003f54e  test    ebx, ebx
0x18003f550  jnz     loc_18003F6FE
0x18003f556  mov     eax, ecx
0x18003f558  add     rax, rax
0x18003f55b  mov     ecx, eax
0x18003f55d  cmp     rax, rdi
0x18003f560  jbe     short loc_18003F564
0x18003f562  mov     ecx, edi
0x18003f564  cmp     rdi, rax
0x18003f567  sbb     ebx, ebx
0x18003f569  and     ebx, r12d
0x18003f56c  mov     eax, ebx
0x18003f56e  and     eax, r8d
0x18003f571  cmp     eax, r9d
0x18003f574  jnz     short loc_18003F579
0x18003f576  movzx   ebx, bx
0x18003f579  test    ebx, ebx
0x18003f57b  jnz     loc_18003F6FE
0x18003f581  mov     edx, ecx; dwBytes
0x18003f583  xor     ecx, ecx; uFlags
0x18003f585  call    cs:__imp_GlobalAlloc
0x18003f58b  mov     rsi, rax
0x18003f58e  test    rax, rax
0x18003f591  jnz     short loc_18003F59D
0x18003f593  mov     ebx, 0Eh
0x18003f598  jmp     loc_18003F6FE
0x18003f59d  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18003f5a0  lea     edx, [rax+1]
0x18003f5a3  cmp     edx, eax
0x18003f5a5  jb      short loc_18003F5AC
0x18003f5a7  mov     ecx, r13d
0x18003f5aa  jmp     short loc_18003F5B1
0x18003f5ac  mov     edx, edi
0x18003f5ae  mov     ecx, r12d
0x18003f5b1  mov     eax, ecx
0x18003f5b3  movzx   ebx, cx
0x18003f5b6  mov     r8d, 1FFF0000h
0x18003f5bc  mov     r9d, 70000h
0x18003f5c2  and     eax, r8d
0x18003f5c5  cmp     eax, r9d
0x18003f5c8  cmovnz  ebx, ecx
0x18003f5cb  test    ebx, ebx
0x18003f5cd  jnz     loc_18003F6FE
0x18003f5d3  mov     eax, edx
0x18003f5d5  add     rax, rax
0x18003f5d8  mov     ecx, eax
0x18003f5da  cmp     rax, rdi
0x18003f5dd  jbe     short loc_18003F5E1
0x18003f5df  mov     ecx, edi
0x18003f5e1  cmp     rdi, rax
0x18003f5e4  sbb     ebx, ebx
0x18003f5e6  and     ebx, r12d
0x18003f5e9  mov     eax, ebx
0x18003f5eb  and     eax, r8d
0x18003f5ee  cmp     eax, r9d
0x18003f5f1  jnz     short loc_18003F5F6
0x18003f5f3  movzx   ebx, bx
0x18003f5f6  test    ebx, ebx
0x18003f5f8  jnz     loc_18003F6FE
0x18003f5fe  mov     edx, ecx; dwBytes
0x18003f600  xor     ecx, ecx; uFlags
0x18003f602  call    cs:__imp_GlobalAlloc
0x18003f608  mov     r15, rax
0x18003f60b  test    rax, rax
0x18003f60e  jz      short loc_18003F593
0x18003f610  mov     edx, [rbp+57h+cbMaxValueLen]; dwBytes
0x18003f613  xor     ecx, ecx; uFlags
0x18003f615  call    cs:__imp_GlobalAlloc
0x18003f61b  mov     r14, rax
0x18003f61e  test    rax, rax
0x18003f621  jz      loc_18003F593
0x18003f627  mov     edi, r13d
0x18003f62a  cmp     edi, [rbp+57h+cValues]
0x18003f62d  jnb     short loc_18003F6A0
0x18003f62f  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18003f632  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18003f636  mov     rcx, [rbp+57h+var_68]; hKey
0x18003f63a  inc     eax
0x18003f63c  mov     [rbp+57h+cchValueName], eax
0x18003f63f  mov     r8, r15; lpValueName
0x18003f642  mov     eax, [rbp+57h+cbMaxValueLen]
0x18003f645  mov     edx, edi; dwIndex
0x18003f647  mov     [rbp+57h+cbData], eax
0x18003f64a  lea     rax, [rbp+57h+cbData]
0x18003f64e  mov     [rsp+0E0h+var_A8], rax; lpcbData
0x18003f653  lea     rax, [rbp+57h+Type]
0x18003f657  mov     [rsp+0E0h+lpSecurityAttributes], r14; lpData
0x18003f65c  mov     qword ptr [rsp+0E0h+samDesired], rax; lpType
0x18003f661  mov     [rsp+0E0h+phkResult], r13; lpReserved
0x18003f666  call    cs:__imp_RegEnumValueW
0x18003f66c  mov     ebx, eax
0x18003f66e  test    eax, eax
0x18003f670  jnz     loc_18003F6FE
0x18003f676  mov     eax, [rbp+57h+cbData]
0x18003f679  xor     r8d, r8d; Reserved
0x18003f67c  mov     r9d, [rbp+57h+Type]; dwType
0x18003f680  mov     rdx, r15; lpValueName
0x18003f683  mov     rcx, [rbp+57h+hKey]; hKey
0x18003f687  mov     [rsp+0E0h+samDesired], eax; cbData
0x18003f68b  mov     [rsp+0E0h+phkResult], r14; lpData
0x18003f690  call    cs:__imp_RegSetValueExW
0x18003f696  mov     ebx, eax
0x18003f698  test    eax, eax
0x18003f69a  jnz     short loc_18003F6FE
0x18003f69c  inc     edi
0x18003f69e  jmp     short loc_18003F62A
0x18003f6a0  mov     edi, r13d
0x18003f6a3  cmp     [rbp+57h+cSubKeys], r13d
0x18003f6a7  jbe     short loc_18003F6FE
0x18003f6a9  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18003f6ac  lea     r9, [rbp+57h+cchName]; lpcchName
0x18003f6b0  mov     rcx, [rbp+57h+var_68]; hKey
0x18003f6b4  inc     eax
0x18003f6b6  mov     [rsp+0E0h+var_A8], r13; lpftLastWriteTime
0x18003f6bb  mov     r8, rsi; lpName
0x18003f6be  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpcchClass
0x18003f6c3  mov     edx, edi; dwIndex
0x18003f6c5  mov     qword ptr [rsp+0E0h+samDesired], r13; lpClass
0x18003f6ca  mov     [rbp+57h+cchName], eax
0x18003f6cd  mov     [rsp+0E0h+phkResult], r13; lpReserved
0x18003f6d2  call    cs:__imp_RegEnumKeyExW
0x18003f6d8  mov     ebx, eax
0x18003f6da  test    eax, eax
0x18003f6dc  jnz     short loc_18003F6FE
0x18003f6de  mov     r8, [rbp+57h+hKey]
0x18003f6e2  mov     r9, rsi
0x18003f6e5  mov     rcx, [rbp+57h+var_68]
0x18003f6e9  mov     rdx, rsi
0x18003f6ec  call    RegCopyKeyRecursive
0x18003f6f1  mov     ebx, eax
0x18003f6f3  test    eax, eax
0x18003f6f5  jnz     short loc_18003F6FE
0x18003f6f7  inc     edi
0x18003f6f9  cmp     edi, [rbp+57h+cSubKeys]
0x18003f6fc  jb      short loc_18003F6A9
0x18003f6fe  mov     rcx, [rbp+57h+var_68]; hKey
0x18003f702  test    rcx, rcx
0x18003f705  jz      short loc_18003F70D
0x18003f707  call    cs:__imp_RegCloseKey
0x18003f70d  mov     rcx, [rbp+57h+hKey]; hKey
0x18003f711  test    rcx, rcx
0x18003f714  jz      short loc_18003F71C
0x18003f716  call    cs:__imp_RegCloseKey
0x18003f71c  test    rsi, rsi
0x18003f71f  jz      short loc_18003F72A
0x18003f721  mov     rcx, rsi; hMem
0x18003f724  call    cs:__imp_GlobalFree
0x18003f72a  test    r15, r15
0x18003f72d  jz      short loc_18003F738
0x18003f72f  mov     rcx, r15; hMem
0x18003f732  call    cs:__imp_GlobalFree
0x18003f738  test    r14, r14
0x18003f73b  jz      short loc_18003F746
0x18003f73d  mov     rcx, r14; hMem
0x18003f740  call    cs:__imp_GlobalFree
0x18003f746  mov     eax, ebx
0x18003f748  add     rsp, 0A8h
0x18003f74f  pop     r15
0x18003f751  pop     r14
0x18003f753  pop     r13
0x18003f755  pop     r12
0x18003f757  pop     rdi
0x18003f758  pop     rsi
0x18003f759  pop     rbx
0x18003f75a  pop     rbp
0x18003f75b  retn
```
