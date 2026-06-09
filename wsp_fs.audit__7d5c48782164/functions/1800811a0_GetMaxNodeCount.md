# GetMaxNodeCount

- ea: `0x1800811a0`
- end: `0x180081273`
- name: `GetMaxNodeCount`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034bb0`

## callees

- `0x1800811a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081204`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008124a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081204`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008124a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081237`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081237`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800811ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800811ef`

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
0x1800811a0  mov     rax, rsp
0x1800811a3  mov     [rax+20h], rbx
0x1800811a7  mov     [rax+8], rcx
0x1800811ab  push    rdi
0x1800811ac  sub     rsp, 30h
0x1800811b0  mov     dword ptr [rax+10h], 4
0x1800811b7  mov     rdi, rdx
0x1800811ba  mov     dword ptr [rax+8], 0
0x1800811c1  mov     r9d, 1; samDesired
0x1800811c7  mov     qword ptr [rax+18h], 0
0x1800811cf  lea     rax, [rax+18h]
0x1800811d3  mov     dword ptr [rdx], 0
0x1800811d9  xor     r8d, r8d; ulOptions
0x1800811dc  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800811e3  mov     [rsp+38h+phkResult], rax; phkResult
0x1800811e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800811ef  call    cs:__imp_RegOpenKeyExW
0x1800811f6  nop     dword ptr [rax+rax+00h]
0x1800811fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081202  mov     ebx, eax
0x180081204  call    cs:__imp_RegCloseKey
0x18008120b  nop     dword ptr [rax+rax+00h]
0x180081210  test    ebx, ebx
0x180081212  jnz     short loc_180081265
0x180081214  mov     rcx, [rsp+38h+hKey]; hKey
0x180081219  lea     rax, [rsp+38h+cbData]
0x18008121e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180081223  lea     r9, [rsp+38h+Type]; lpType
0x180081228  xor     r8d, r8d; lpReserved
0x18008122b  mov     [rsp+38h+phkResult], rdi; lpData
0x180081230  lea     rdx, ValueName; "MaxLicensedNodes"
0x180081237  call    cs:__imp_RegQueryValueExW
0x18008123e  nop     dword ptr [rax+rax+00h]
0x180081243  mov     rcx, [rsp+38h+hKey]; hKey
0x180081248  mov     ebx, eax
0x18008124a  call    cs:__imp_RegCloseKey
0x180081251  nop     dword ptr [rax+rax+00h]
0x180081256  test    ebx, ebx
0x180081258  jnz     short loc_180081265
0x18008125a  cmp     [rsp+38h+Type], 4
0x18008125f  lea     eax, [rbx+0Dh]
0x180081262  cmovnz  ebx, eax
0x180081265  mov     eax, ebx
0x180081267  mov     rbx, [rsp+38h+arg_18]
0x18008126c  add     rsp, 30h
0x180081270  pop     rdi
0x180081271  retn
```
