# RegDeleteKeyRecursive

- ea: `0x18003f764`
- end: `0x18003f914`
- name: `RegDeleteKeyRecursive`
- size: `432`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003f764`
- `0x18003f91c`

## callees

- `0x18003f764`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f8d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f90a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f8d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f90a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003f8e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003f8e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f7ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f7ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f852`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f8be`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f852`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f8be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f7a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f7a2`
- `KERNEL32!GlobalAlloc` at `0x18003f82b`
- `KERNEL32!GlobalAlloc` at `0x18003f82b`
- `KERNEL32!GlobalFree` at `0x18003f8cb`
- `KERNEL32!GlobalFree` at `0x18003f8cb`

## pseudocode

```c
LSTATUS __fastcall RegDeleteKeyRecursive(HKEY a1, const WCHAR *a2)
{
  LSTATUS result; // eax
  LSTATUS v5; // ebx
  unsigned __int64 v6; // rax
  WCHAR *v7; // rbx
  DWORD v8; // edi
  WCHAR *v9; // r8
  DWORD cSubKeys; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-8h] BYREF
  DWORD cchName; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+B8h] [rbp+48h] BYREF

  hKey = 0;
  cSubKeys = 0;
  cchName = 0;
  cbMaxSubKeyLen = 0;
  result = RegOpenKeyExW(a1, a2, 0, 0x2001Fu, &hKey);
  if ( !result )
  {
    v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v5 )
    {
      if ( !cSubKeys )
      {
LABEL_15:
        RegCloseKey(hKey);
        return RegDeleteKeyExW(a1, a2, 0, 0);
      }
      if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
      {
        v6 = 2LL * (cbMaxSubKeyLen + 1);
        if ( v6 <= 0xFFFFFFFF )
        {
          v7 = (WCHAR *)GlobalAlloc(0, (unsigned int)v6);
          if ( v7 )
          {
            v8 = cSubKeys;
            while ( 1 )
            {
              v9 = v7;
              if ( !v8 )
                break;
              cchName = cbMaxSubKeyLen + 1;
              if ( !RegEnumKeyExW(hKey, --v8, v7, &cchName, 0, 0, 0, 0) )
                RegDeleteKeyRecursive(hKey, v7);
            }
            while ( 1 )
            {
              cchName = cbMaxSubKeyLen + 1;
              if ( RegEnumKeyExW(hKey, 0, v9, &cchName, 0, 0, 0, 0) )
                break;
              RegDeleteKeyRecursive(hKey, v7);
              v9 = v7;
            }
            GlobalFree(v7);
          }
          goto LABEL_15;
        }
      }
      v5 = 534;
    }
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18003f764  mov     [rsp-28h+arg_0], rbx
0x18003f769  push    rbp
0x18003f76a  push    rsi
0x18003f76b  push    rdi
0x18003f76c  push    r14
0x18003f76e  push    r15
0x18003f770  mov     rbp, rsp
0x18003f773  sub     rsp, 70h
0x18003f777  xor     r15d, r15d
0x18003f77a  lea     rax, [rbp+hKey]
0x18003f77e  mov     r9d, 2001Fh; samDesired
0x18003f784  mov     [rbp+hKey], r15
0x18003f788  xor     r8d, r8d; ulOptions
0x18003f78b  mov     [rbp+cSubKeys], r15d
0x18003f78f  mov     [rbp+cchName], r15d
0x18003f793  mov     rsi, rdx
0x18003f796  mov     [rbp+cbMaxSubKeyLen], r15d
0x18003f79a  mov     r14, rcx
0x18003f79d  mov     [rsp+70h+phkResult], rax; phkResult
0x18003f7a2  call    cs:__imp_RegOpenKeyExW
0x18003f7a8  test    eax, eax
0x18003f7aa  jnz     loc_18003F8ED
0x18003f7b0  mov     rcx, [rbp+hKey]; hKey
0x18003f7b4  lea     rax, [rbp+cbMaxSubKeyLen]
0x18003f7b8  mov     [rsp+70h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18003f7bd  xor     r9d, r9d; lpReserved
0x18003f7c0  mov     [rsp+70h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18003f7c5  xor     r8d, r8d; lpcchClass
0x18003f7c8  mov     [rsp+70h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18003f7cd  xor     edx, edx; lpClass
0x18003f7cf  mov     [rsp+70h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18003f7d4  mov     [rsp+70h+lpcValues], r15; lpcValues
0x18003f7d9  mov     [rsp+70h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18003f7de  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18003f7e3  lea     rax, [rbp+cSubKeys]
0x18003f7e7  mov     [rsp+70h+phkResult], rax; lpcSubKeys
0x18003f7ec  call    cs:__imp_RegQueryInfoKeyW
0x18003f7f2  mov     ebx, eax
0x18003f7f4  test    eax, eax
0x18003f7f6  jnz     loc_18003F906
0x18003f7fc  cmp     [rbp+cSubKeys], r15d
0x18003f800  jbe     loc_18003F8D1
0x18003f806  mov     eax, [rbp+cbMaxSubKeyLen]
0x18003f809  lea     ecx, [rax+1]
0x18003f80c  cmp     ecx, eax
0x18003f80e  jb      loc_18003F901
0x18003f814  mov     eax, ecx
0x18003f816  mov     ecx, 0FFFFFFFFh
0x18003f81b  add     rax, rax
0x18003f81e  cmp     rax, rcx
0x18003f821  ja      loc_18003F901
0x18003f827  mov     edx, eax; dwBytes
0x18003f829  xor     ecx, ecx; uFlags
0x18003f82b  call    cs:__imp_GlobalAlloc
0x18003f831  mov     rbx, rax
0x18003f834  test    rax, rax
0x18003f837  jz      loc_18003F8D1
0x18003f83d  mov     edi, [rbp+cSubKeys]
0x18003f840  jmp     short loc_18003F868
0x18003f842  mov     ecx, [rbp+cbMaxSubKeyLen]
0x18003f845  inc     ecx
0x18003f847  mov     [rbp+cchName], ecx
0x18003f84a  dec     edi
0x18003f84c  mov     rcx, [rbp+hKey]; hKey
0x18003f850  mov     edx, edi; dwIndex
0x18003f852  call    cs:__imp_RegEnumKeyExW
0x18003f858  test    eax, eax
0x18003f85a  jnz     short loc_18003F868
0x18003f85c  mov     rcx, [rbp+hKey]
0x18003f860  mov     rdx, rbx
0x18003f863  call    RegDeleteKeyRecursive
0x18003f868  mov     [rsp+70h+lpcValues], r15; lpftLastWriteTime
0x18003f86d  lea     r9, [rbp+cchName]; lpcchName
0x18003f871  mov     [rsp+70h+lpcbMaxClassLen], r15; lpcchClass
0x18003f876  mov     r8, rbx; lpName
0x18003f879  mov     [rsp+70h+lpcbMaxSubKeyLen], r15; lpClass
0x18003f87e  mov     [rsp+70h+phkResult], r15; lpReserved
0x18003f883  test    edi, edi
0x18003f885  jnz     short loc_18003F842
0x18003f887  jmp     short loc_18003F8B0
0x18003f889  mov     rcx, [rbp+hKey]
0x18003f88d  mov     rdx, rbx
0x18003f890  call    RegDeleteKeyRecursive
0x18003f895  mov     [rsp+70h+lpcValues], r15; lpftLastWriteTime
0x18003f89a  lea     r9, [rbp+cchName]; lpcchName
0x18003f89e  mov     [rsp+70h+lpcbMaxClassLen], r15; lpcchClass
0x18003f8a3  mov     r8, rbx; lpName
0x18003f8a6  mov     [rsp+70h+lpcbMaxSubKeyLen], r15; lpClass
0x18003f8ab  mov     [rsp+70h+phkResult], r15; lpReserved
0x18003f8b0  mov     eax, [rbp+cbMaxSubKeyLen]
0x18003f8b3  xor     edx, edx; dwIndex
0x18003f8b5  mov     rcx, [rbp+hKey]; hKey
0x18003f8b9  inc     eax
0x18003f8bb  mov     [rbp+cchName], eax
0x18003f8be  call    cs:__imp_RegEnumKeyExW
0x18003f8c4  test    eax, eax
0x18003f8c6  jz      short loc_18003F889
0x18003f8c8  mov     rcx, rbx; hMem
0x18003f8cb  call    cs:__imp_GlobalFree
0x18003f8d1  mov     rcx, [rbp+hKey]; hKey
0x18003f8d5  call    cs:__imp_RegCloseKey
0x18003f8db  xor     r9d, r9d; Reserved
0x18003f8de  xor     r8d, r8d; samDesired
0x18003f8e1  mov     rdx, rsi; lpSubKey
0x18003f8e4  mov     rcx, r14; hKey
0x18003f8e7  call    cs:__imp_RegDeleteKeyExW
0x18003f8ed  mov     rbx, [rsp+70h+arg_0]
0x18003f8f5  add     rsp, 70h
0x18003f8f9  pop     r15
0x18003f8fb  pop     r14
0x18003f8fd  pop     rdi
0x18003f8fe  pop     rsi
0x18003f8ff  pop     rbp
0x18003f900  retn
0x18003f901  mov     ebx, 216h
0x18003f906  mov     rcx, [rbp+hKey]; hKey
0x18003f90a  call    cs:__imp_RegCloseKey
0x18003f910  mov     eax, ebx
0x18003f912  jmp     short loc_18003F8ED
```
