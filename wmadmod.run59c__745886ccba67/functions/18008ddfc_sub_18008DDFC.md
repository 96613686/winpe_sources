# sub_18008DDFC

- ea: `0x18008ddfc`
- end: `0x18008deac`
- name: `sub_18008DDFC`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008c72c`

## callees

- `0x18008ddfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008de39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008de39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008de96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008de96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008de74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008de74`

## pseudocode

```c
__int64 sub_18008DDFC()
{
  unsigned int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  cbData = 4;
  Data = 1;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Scrunch\\wmaspdtxdmo", 0, 1u, &hKey) )
  {
    if ( !hKey )
      return Data;
    if ( RegQueryValueExW(hKey, L"ProPlusMode", 0, 0, (LPBYTE)&Data, &cbData) )
      Data = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x18008ddfc  mov     rax, rsp
0x18008ddff  sub     rsp, 38h
0x18008de03  mov     dword ptr [rax+10h], 4
0x18008de0a  mov     r9d, 1; samDesired
0x18008de10  mov     dword ptr [rax+8], 1
0x18008de17  xor     r8d, r8d; ulOptions
0x18008de1a  mov     qword ptr [rax+18h], 0
0x18008de22  lea     rax, [rax+18h]
0x18008de26  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Scrunch\\wmaspdtxd"...
0x18008de2d  mov     [rsp+38h+phkResult], rax; phkResult
0x18008de32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008de39  call    cs:RegOpenKeyExW
0x18008de40  nop     dword ptr [rax+rax+00h]
0x18008de45  test    eax, eax
0x18008de47  jnz     short loc_18008DE8C
0x18008de49  mov     rcx, [rsp+38h+hKey]; hKey
0x18008de4e  test    rcx, rcx
0x18008de51  jz      short loc_18008DEA2
0x18008de53  lea     rax, [rsp+38h+cbData]
0x18008de58  xor     r9d, r9d; lpType
0x18008de5b  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18008de60  lea     rdx, aProplusmode; "ProPlusMode"
0x18008de67  lea     rax, [rsp+38h+Data]
0x18008de6c  xor     r8d, r8d; lpReserved
0x18008de6f  mov     [rsp+38h+phkResult], rax; lpData
0x18008de74  call    cs:RegQueryValueExW
0x18008de7b  nop     dword ptr [rax+rax+00h]
0x18008de80  test    eax, eax
0x18008de82  jz      short loc_18008DE8C
0x18008de84  mov     [rsp+38h+Data], 1
0x18008de8c  mov     rcx, [rsp+38h+hKey]; hKey
0x18008de91  test    rcx, rcx
0x18008de94  jz      short loc_18008DEA2
0x18008de96  call    cs:RegCloseKey
0x18008de9d  nop     dword ptr [rax+rax+00h]
0x18008dea2  mov     eax, [rsp+38h+Data]
0x18008dea6  add     rsp, 38h
0x18008deaa  retn
```
