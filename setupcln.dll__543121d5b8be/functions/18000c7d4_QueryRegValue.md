# QueryRegValue

- ea: `0x18000c7d4`
- end: `0x18000c876`
- name: `QueryRegValue`
- size: `162`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180004c30`

## callees

- `0x18000c7d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c80e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c80e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c867`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c867`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c850`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c850`

## pseudocode

```c
_BOOL8 __fastcall QueryRegValue(__int64 a1, __int64 a2, __int64 a3)
{
  BOOL v3; // ebx
  __int64 Data; // [rsp+50h] [rbp+8h] BYREF
  __int64 cbData; // [rsp+58h] [rbp+10h] BYREF
  __int64 Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Type = a3;
  cbData = a2;
  Data = a1;
  v3 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 1u, &hKey) )
  {
    LODWORD(Data) = 0;
    LODWORD(cbData) = 4;
    LODWORD(Type) = 0;
    if ( !RegQueryValueExW(hKey, L"Upgrade", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
      v3 = Type == 4;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18000c7d4  mov     r11, rsp
0x18000c7d7  mov     [r11+18h], r8
0x18000c7db  mov     [r11+10h], rdx
0x18000c7df  mov     [r11+8], rcx
0x18000c7e3  push    rbx
0x18000c7e4  push    rsi
0x18000c7e5  sub     rsp, 38h
0x18000c7e9  xor     ebx, ebx
0x18000c7eb  lea     rax, [r11+20h]
0x18000c7ef  xor     r8d, r8d; ulOptions
0x18000c7f2  mov     [r11+20h], rbx
0x18000c7f6  lea     rdx, SubKey; "SYSTEM\\Setup"
0x18000c7fd  mov     [r11-28h], rax
0x18000c801  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c808  lea     esi, [rbx+1]
0x18000c80b  mov     r9d, esi; samDesired
0x18000c80e  call    cs:__imp_RegOpenKeyExW
0x18000c814  test    eax, eax
0x18000c816  jnz     short loc_18000C86D
0x18000c818  mov     rcx, [rsp+48h+hKey]; hKey
0x18000c81d  lea     rax, [rsp+48h+cbData]
0x18000c822  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000c827  lea     r9, [rsp+48h+Type]; lpType
0x18000c82c  lea     rax, [rsp+48h+Data]
0x18000c831  mov     dword ptr [rsp+48h+Data], ebx
0x18000c835  xor     r8d, r8d; lpReserved
0x18000c838  mov     [rsp+48h+lpData], rax; lpData
0x18000c83d  lea     rdx, ValueName; "Upgrade"
0x18000c844  mov     dword ptr [rsp+48h+cbData], 4
0x18000c84c  mov     dword ptr [rsp+48h+Type], ebx
0x18000c850  call    cs:__imp_RegQueryValueExW
0x18000c856  test    eax, eax
0x18000c858  jnz     short loc_18000C862
0x18000c85a  cmp     dword ptr [rsp+48h+Type], 4
0x18000c85f  cmovz   ebx, esi
0x18000c862  mov     rcx, [rsp+48h+hKey]; hKey
0x18000c867  call    cs:__imp_RegCloseKey
0x18000c86d  mov     eax, ebx
0x18000c86f  add     rsp, 38h
0x18000c873  pop     rsi
0x18000c874  pop     rbx
0x18000c875  retn
```
