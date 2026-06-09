# GetMaxNodeCount

- ea: `0x18007f220`
- end: `0x18007f2da`
- name: `GetMaxNodeCount`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033a90`

## callees

- `0x18007f220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f27e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f2b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f27e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f2b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007f2ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007f2ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f26f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f26f`

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
0x18007f220  mov     rax, rsp
0x18007f223  mov     [rax+20h], rbx
0x18007f227  mov     [rax+8], rcx
0x18007f22b  push    rdi
0x18007f22c  sub     rsp, 30h
0x18007f230  mov     dword ptr [rax+10h], 4
0x18007f237  mov     rdi, rdx
0x18007f23a  mov     dword ptr [rax+8], 0
0x18007f241  mov     r9d, 1; samDesired
0x18007f247  mov     qword ptr [rax+18h], 0
0x18007f24f  lea     rax, [rax+18h]
0x18007f253  mov     dword ptr [rdx], 0
0x18007f259  xor     r8d, r8d; ulOptions
0x18007f25c  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18007f263  mov     [rsp+38h+phkResult], rax; phkResult
0x18007f268  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007f26f  call    cs:__imp_RegOpenKeyExW
0x18007f275  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007f27c  mov     ebx, eax
0x18007f27e  call    cs:__imp_RegCloseKey
0x18007f284  test    ebx, ebx
0x18007f286  jnz     short loc_18007F2CD
0x18007f288  mov     rcx, [rsp+38h+hKey]; hKey
0x18007f28d  lea     rax, [rsp+38h+cbData]
0x18007f292  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18007f297  lea     r9, [rsp+38h+Type]; lpType
0x18007f29c  xor     r8d, r8d; lpReserved
0x18007f29f  mov     [rsp+38h+phkResult], rdi; lpData
0x18007f2a4  lea     rdx, ValueName; "MaxLicensedNodes"
0x18007f2ab  call    cs:__imp_RegQueryValueExW
0x18007f2b1  mov     rcx, [rsp+38h+hKey]; hKey
0x18007f2b6  mov     ebx, eax
0x18007f2b8  call    cs:__imp_RegCloseKey
0x18007f2be  test    ebx, ebx
0x18007f2c0  jnz     short loc_18007F2CD
0x18007f2c2  cmp     [rsp+38h+Type], 4
0x18007f2c7  lea     eax, [rbx+0Dh]
0x18007f2ca  cmovnz  ebx, eax
0x18007f2cd  mov     eax, ebx
0x18007f2cf  mov     rbx, [rsp+38h+arg_18]
0x18007f2d4  add     rsp, 30h
0x18007f2d8  pop     rdi
0x18007f2d9  retn
```
