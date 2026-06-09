# GetMaxNodeCount

- ea: `0x180043f50`
- end: `0x180044023`
- name: `GetMaxNodeCount`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030d30`

## callees

- `0x180043f50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043fe7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043fe7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043f9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043f9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043ffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043ffa`

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
0x180043f50  mov     rax, rsp
0x180043f53  mov     [rax+20h], rbx
0x180043f57  mov     [rax+8], rcx
0x180043f5b  push    rdi
0x180043f5c  sub     rsp, 30h
0x180043f60  mov     dword ptr [rax+10h], 4
0x180043f67  mov     rdi, rdx
0x180043f6a  mov     dword ptr [rax+8], 0
0x180043f71  mov     r9d, 1; samDesired
0x180043f77  mov     qword ptr [rax+18h], 0
0x180043f7f  lea     rax, [rax+18h]
0x180043f83  mov     dword ptr [rdx], 0
0x180043f89  xor     r8d, r8d; ulOptions
0x180043f8c  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180043f93  mov     [rsp+38h+phkResult], rax; phkResult
0x180043f98  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043f9f  call    cs:__imp_RegOpenKeyExW
0x180043fa6  nop     dword ptr [rax+rax+00h]
0x180043fab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043fb2  mov     ebx, eax
0x180043fb4  call    cs:__imp_RegCloseKey
0x180043fbb  nop     dword ptr [rax+rax+00h]
0x180043fc0  test    ebx, ebx
0x180043fc2  jnz     short loc_180044015
0x180043fc4  mov     rcx, [rsp+38h+hKey]; hKey
0x180043fc9  lea     rax, [rsp+38h+cbData]
0x180043fce  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180043fd3  lea     r9, [rsp+38h+Type]; lpType
0x180043fd8  xor     r8d, r8d; lpReserved
0x180043fdb  mov     [rsp+38h+phkResult], rdi; lpData
0x180043fe0  lea     rdx, ValueName; "MaxLicensedNodes"
0x180043fe7  call    cs:__imp_RegQueryValueExW
0x180043fee  nop     dword ptr [rax+rax+00h]
0x180043ff3  mov     rcx, [rsp+38h+hKey]; hKey
0x180043ff8  mov     ebx, eax
0x180043ffa  call    cs:__imp_RegCloseKey
0x180044001  nop     dword ptr [rax+rax+00h]
0x180044006  test    ebx, ebx
0x180044008  jnz     short loc_180044015
0x18004400a  cmp     [rsp+38h+Type], 4
0x18004400f  lea     eax, [rbx+0Dh]
0x180044012  cmovnz  ebx, eax
0x180044015  mov     eax, ebx
0x180044017  mov     rbx, [rsp+38h+arg_18]
0x18004401c  add     rsp, 30h
0x180044020  pop     rdi
0x180044021  retn
```
