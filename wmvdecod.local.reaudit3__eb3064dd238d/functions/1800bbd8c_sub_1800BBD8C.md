# sub_1800BBD8C

- ea: `0x1800bbd8c`
- end: `0x1800bbe24`
- name: `sub_1800BBD8C`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b0d68`

## callees

- `0x1800bbd8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbdfd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbdfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbe0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbe0e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800bbdc7`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800bbdc7`

## pseudocode

```c
__int64 __fastcall sub_1800BBD8C(__int64 a1, __int64 a2, __int64 a3)
{
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int v6; // [rsp+4Ch] [rbp+14h]
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  int v8; // [rsp+54h] [rbp+1Ch]

  v8 = HIDWORD(a3);
  v6 = HIDWORD(a2);
  hKey = 0;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Scrunch\\WMVideo", &hKey) )
  {
    RegQueryValueExW(hKey, L"DXVA1", 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  return Data;
}

```

## disassembly

```asm
0x1800bbd8c  mov     rax, rsp
0x1800bbd8f  mov     [rax+18h], r8
0x1800bbd93  mov     [rax+10h], rdx
0x1800bbd97  mov     [rax+8], rcx
0x1800bbd9b  sub     rsp, 38h
0x1800bbd9f  lea     r8, [rax+8]; phkResult
0x1800bbda3  mov     qword ptr [rax+8], 0
0x1800bbdab  lea     rdx, SubKey; "Software\\Microsoft\\Scrunch\\WMVideo"
0x1800bbdb2  mov     dword ptr [rax+10h], 4
0x1800bbdb9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800bbdc0  mov     dword ptr [rax+18h], 0
0x1800bbdc7  call    cs:RegOpenKeyW
0x1800bbdce  nop     dword ptr [rax+rax+00h]
0x1800bbdd3  test    eax, eax
0x1800bbdd5  jnz     short loc_1800BBE1A
0x1800bbdd7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bbddc  lea     rax, [rsp+38h+cbData]
0x1800bbde1  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800bbde6  lea     rdx, ValueName; "DXVA1"
0x1800bbded  lea     rax, [rsp+38h+Data]
0x1800bbdf2  xor     r9d, r9d; lpType
0x1800bbdf5  xor     r8d, r8d; lpReserved
0x1800bbdf8  mov     [rsp+38h+lpData], rax; lpData
0x1800bbdfd  call    cs:RegQueryValueExW
0x1800bbe04  nop     dword ptr [rax+rax+00h]
0x1800bbe09  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bbe0e  call    cs:RegCloseKey
0x1800bbe15  nop     dword ptr [rax+rax+00h]
0x1800bbe1a  mov     eax, [rsp+38h+Data]
0x1800bbe1e  add     rsp, 38h
0x1800bbe22  retn
```
