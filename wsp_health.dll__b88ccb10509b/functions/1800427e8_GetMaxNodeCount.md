# GetMaxNodeCount

- ea: `0x1800427e8`
- end: `0x1800428a2`
- name: `GetMaxNodeCount`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fd20`

## callees

- `0x1800427e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042873`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042873`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042837`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042837`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042846`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042880`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042846`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042880`

## pseudocode

```c
__int64 __fastcall GetMaxNodeCount(__int64 a1, BYTE *a2)
{
  unsigned int v3; // ebx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+44h] [rbp+Ch]
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v6 = HIDWORD(a1);
  cbData = 4;
  Type = 0;
  hKey = 0;
  *(_DWORD *)a2 = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Failover Clusters",
         0,
         1u,
         &hKey);
  RegCloseKey(HKEY_LOCAL_MACHINE);
  if ( !v3 )
  {
    v3 = RegQueryValueExW(hKey, L"MaxLicensedNodes", 0, &Type, a2, &cbData);
    RegCloseKey(hKey);
    if ( !v3 && Type != 4 )
      return 13;
  }
  return v3;
}

```

## disassembly

```asm
0x1800427e8  mov     rax, rsp
0x1800427eb  mov     [rax+20h], rbx
0x1800427ef  mov     [rax+8], rcx
0x1800427f3  push    rdi
0x1800427f4  sub     rsp, 30h
0x1800427f8  mov     dword ptr [rax+10h], 4
0x1800427ff  mov     rdi, rdx
0x180042802  mov     dword ptr [rax+8], 0
0x180042809  mov     r9d, 1; samDesired
0x18004280f  mov     qword ptr [rax+18h], 0
0x180042817  lea     rax, [rax+18h]
0x18004281b  mov     dword ptr [rdx], 0
0x180042821  xor     r8d, r8d; ulOptions
0x180042824  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18004282b  mov     [rsp+38h+phkResult], rax; phkResult
0x180042830  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042837  call    cs:__imp_RegOpenKeyExW
0x18004283d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042844  mov     ebx, eax
0x180042846  call    cs:__imp_RegCloseKey
0x18004284c  test    ebx, ebx
0x18004284e  jnz     short loc_180042895
0x180042850  mov     rcx, [rsp+38h+hKey]; hKey
0x180042855  lea     rax, [rsp+38h+cbData]
0x18004285a  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004285f  lea     r9, [rsp+38h+Type]; lpType
0x180042864  xor     r8d, r8d; lpReserved
0x180042867  mov     [rsp+38h+phkResult], rdi; lpData
0x18004286c  lea     rdx, ValueName; "MaxLicensedNodes"
0x180042873  call    cs:__imp_RegQueryValueExW
0x180042879  mov     rcx, [rsp+38h+hKey]; hKey
0x18004287e  mov     ebx, eax
0x180042880  call    cs:__imp_RegCloseKey
0x180042886  test    ebx, ebx
0x180042888  jnz     short loc_180042895
0x18004288a  cmp     [rsp+38h+Type], 4
0x18004288f  lea     eax, [rbx+0Dh]
0x180042892  cmovnz  ebx, eax
0x180042895  mov     eax, ebx
0x180042897  mov     rbx, [rsp+38h+arg_18]
0x18004289c  add     rsp, 30h
0x1800428a0  pop     rdi
0x1800428a1  retn
```
