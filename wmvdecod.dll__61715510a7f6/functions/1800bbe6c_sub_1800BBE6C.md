# sub_1800BBE6C

- ea: `0x1800bbe6c`
- end: `0x1800bbf09`
- name: `sub_1800BBE6C`
- size: `157`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b0d68`

## callees

- `0x1800bbe6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbeee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbeee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbedd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbedd`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800bbea7`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800bbea7`

## pseudocode

```c
_BOOL8 __fastcall sub_1800BBE6C(__int64 a1, __int64 a2, __int64 a3)
{
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int v6; // [rsp+4Ch] [rbp+14h]
  int Data; // [rsp+50h] [rbp+18h] BYREF
  int v8; // [rsp+54h] [rbp+1Ch]

  v8 = HIDWORD(a3);
  v6 = HIDWORD(a2);
  hKey = 0;
  cbData = 4;
  Data = 1;
  if ( !RegOpenKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Scrunch\\WMVideo", &hKey) )
  {
    RegQueryValueExW(hKey, L"DXVA", 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  return Data == 0;
}

```

## disassembly

```asm
0x1800bbe6c  mov     rax, rsp
0x1800bbe6f  mov     [rax+18h], r8
0x1800bbe73  mov     [rax+10h], rdx
0x1800bbe77  mov     [rax+8], rcx
0x1800bbe7b  sub     rsp, 38h
0x1800bbe7f  lea     r8, [rax+8]; phkResult
0x1800bbe83  mov     qword ptr [rax+8], 0
0x1800bbe8b  lea     rdx, SubKey; "Software\\Microsoft\\Scrunch\\WMVideo"
0x1800bbe92  mov     dword ptr [rax+10h], 4
0x1800bbe99  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800bbea0  mov     dword ptr [rax+18h], 1
0x1800bbea7  call    cs:RegOpenKeyW
0x1800bbeae  nop     dword ptr [rax+rax+00h]
0x1800bbeb3  test    eax, eax
0x1800bbeb5  jnz     short loc_1800BBEFA
0x1800bbeb7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bbebc  lea     rax, [rsp+38h+cbData]
0x1800bbec1  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800bbec6  lea     rdx, aDxva; "DXVA"
0x1800bbecd  lea     rax, [rsp+38h+Data]
0x1800bbed2  xor     r9d, r9d; lpType
0x1800bbed5  xor     r8d, r8d; lpReserved
0x1800bbed8  mov     [rsp+38h+lpData], rax; lpData
0x1800bbedd  call    cs:RegQueryValueExW
0x1800bbee4  nop     dword ptr [rax+rax+00h]
0x1800bbee9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bbeee  call    cs:RegCloseKey
0x1800bbef5  nop     dword ptr [rax+rax+00h]
0x1800bbefa  xor     eax, eax
0x1800bbefc  cmp     [rsp+38h+Data], eax
0x1800bbf00  setz    al
0x1800bbf03  add     rsp, 38h
0x1800bbf07  retn
```
