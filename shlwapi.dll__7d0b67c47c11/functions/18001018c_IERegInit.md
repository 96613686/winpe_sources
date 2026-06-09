# IERegInit

- ea: `0x18001018c`
- end: `0x1800102c4`
- name: `IERegInit`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c570`
- `0x1800363e4`

## callees

- `0x18001018c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010209`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001023e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010272`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800102a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010209`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001023e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010272`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800102a7`

## pseudocode

```c
LSTATUS IERegInit()
{
  LSTATUS result; // eax
  LSTATUS v1; // eax
  HKEY v2; // rcx
  LSTATUS v3; // eax
  HKEY v4; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  LSTATUS v7; // eax
  HKEY v8; // r8
  HKEY v9; // rcx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  result = _InterlockedCompareExchange(&dword_180059B88, 1, 0);
  if ( !result )
  {
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies", 0, 0x20019u, &phkResult);
    v2 = 0;
    if ( !v1 )
      v2 = phkResult;
    qword_180059B60 = (__int64)v2;
    v3 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Policies", 0, 0x20019u, &phkResult);
    v4 = 0;
    if ( !v3 )
      v4 = phkResult;
    qword_180059B68 = (__int64)v4;
    v5 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software", 0, 0x20019u, &phkResult);
    v6 = 0;
    if ( !v5 )
      v6 = phkResult;
    qword_180059B70 = (__int64)v6;
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &phkResult);
    v8 = 0;
    if ( !v7 )
      v8 = phkResult;
    qword_180059B78 = (__int64)v8;
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20219u, &phkResult);
    v9 = 0;
    if ( !result )
      v9 = phkResult;
    qword_180059B80 = (__int64)v9;
  }
  return result;
}

```

## disassembly

```asm
0x18001018c  push    rbp
0x18001018e  sub     rsp, 30h
0x180010192  mov     [rsp+38h+arg_0], 0
0x18001019b  mov     ecx, 1
0x1800101a0  xor     eax, eax
0x1800101a2  lock cmpxchg cs:dword_180059B88, ecx
0x1800101aa  jnz     loc_1800102BE
0x1800101b0  lea     rax, [rsp+38h+arg_0]
0x1800101b5  mov     rbp, 0FFFFFFFF80000002h
0x1800101bc  mov     rcx, rbp; hKey
0x1800101bf  mov     [rsp+38h+phkResult], rax; phkResult
0x1800101c4  mov     r9d, 20019h; samDesired
0x1800101ca  lea     rdx, SubKey; "Software\\Policies"
0x1800101d1  xor     r8d, r8d; ulOptions
0x1800101d4  call    cs:__imp_RegOpenKeyExW
0x1800101da  xor     ecx, ecx
0x1800101dc  lea     rdx, SubKey; "Software\\Policies"
0x1800101e3  test    eax, eax
0x1800101e5  mov     r9d, 20019h; samDesired
0x1800101eb  lea     rax, [rsp+38h+arg_0]
0x1800101f0  cmovz   rcx, [rsp+38h+arg_0]
0x1800101f6  xor     r8d, r8d; ulOptions
0x1800101f9  mov     cs:qword_180059B60, rcx
0x180010200  lea     rcx, [rbp-1]; hKey
0x180010204  mov     [rsp+38h+phkResult], rax; phkResult
0x180010209  call    cs:__imp_RegOpenKeyExW
0x18001020f  xor     ecx, ecx
0x180010211  lea     rdx, aSoftware; "Software"
0x180010218  test    eax, eax
0x18001021a  mov     r9d, 20019h; samDesired
0x180010220  lea     rax, [rsp+38h+arg_0]
0x180010225  cmovz   rcx, [rsp+38h+arg_0]
0x18001022b  xor     r8d, r8d; ulOptions
0x18001022e  mov     cs:qword_180059B68, rcx
0x180010235  lea     rcx, [rbp-1]; hKey
0x180010239  mov     [rsp+38h+phkResult], rax; phkResult
0x18001023e  call    cs:__imp_RegOpenKeyExW
0x180010244  xor     ecx, ecx
0x180010246  lea     rdx, aSoftware; "Software"
0x18001024d  test    eax, eax
0x18001024f  mov     r9d, 20019h; samDesired
0x180010255  lea     rax, [rsp+38h+arg_0]
0x18001025a  cmovz   rcx, [rsp+38h+arg_0]
0x180010260  xor     r8d, r8d; ulOptions
0x180010263  mov     cs:qword_180059B70, rcx
0x18001026a  mov     rcx, rbp; hKey
0x18001026d  mov     [rsp+38h+phkResult], rax; phkResult
0x180010272  call    cs:__imp_RegOpenKeyExW
0x180010278  xor     r8d, r8d
0x18001027b  lea     rdx, aSoftware; "Software"
0x180010282  test    eax, eax
0x180010284  mov     r9d, 20219h; samDesired
0x18001028a  lea     rax, [rsp+38h+arg_0]
0x18001028f  mov     rcx, rbp; hKey
0x180010292  cmovz   r8, [rsp+38h+arg_0]
0x180010298  mov     cs:qword_180059B78, r8
0x18001029f  xor     r8d, r8d; ulOptions
0x1800102a2  mov     [rsp+38h+phkResult], rax; phkResult
0x1800102a7  call    cs:__imp_RegOpenKeyExW
0x1800102ad  xor     ecx, ecx
0x1800102af  test    eax, eax
0x1800102b1  cmovz   rcx, [rsp+38h+arg_0]
0x1800102b7  mov     cs:qword_180059B80, rcx
0x1800102be  add     rsp, 30h
0x1800102c2  pop     rbp
0x1800102c3  retn
```
