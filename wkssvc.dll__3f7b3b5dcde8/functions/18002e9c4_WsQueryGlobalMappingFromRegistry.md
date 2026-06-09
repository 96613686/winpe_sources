# WsQueryGlobalMappingFromRegistry

- ea: `0x18002e9c4`
- end: `0x18002ea69`
- name: `WsQueryGlobalMappingFromRegistry`
- size: `165`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800012a0`

## callees

- `0x18002df2c`
- `0x18002e2b8`
- `0x18002e9c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ea09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ea09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea51`

## pseudocode

```c
__int64 __fastcall WsQueryGlobalMappingFromRegistry(wint_t *SourceString, _QWORD *a2)
{
  unsigned int ConnectionInfoFromRegistry; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  HKEY v7; // [rsp+58h] [rbp+20h] BYREF

  v7 = 0;
  hKey = 0;
  ConnectionInfoFromRegistry = RegOpenKeyExW(
                                 HKEY_LOCAL_MACHINE,
                                 L"System\\CurrentControlSet\\Control\\NetworkProvider\\GlobalMappings",
                                 0,
                                 0x20019u,
                                 &v7);
  if ( !ConnectionInfoFromRegistry )
  {
    ConnectionInfoFromRegistry = FindCreateOrDeleteConnectionKey(v7, SourceString, 0, &hKey);
    if ( !ConnectionInfoFromRegistry )
    {
      ConnectionInfoFromRegistry = ReadConnectionInfoFromRegistry(hKey, 0, a2);
      RegCloseKey(hKey);
    }
    RegCloseKey(v7);
  }
  return ConnectionInfoFromRegistry;
}

```

## disassembly

```asm
0x18002e9c4  mov     r11, rsp
0x18002e9c7  mov     [r11+8], rbx
0x18002e9cb  mov     [r11+10h], rsi
0x18002e9cf  push    rdi
0x18002e9d0  sub     rsp, 30h
0x18002e9d4  mov     rdi, rdx
0x18002e9d7  mov     qword ptr [r11+20h], 0
0x18002e9df  mov     rsi, rcx
0x18002e9e2  mov     qword ptr [r11+18h], 0
0x18002e9ea  lea     rax, [r11+20h]
0x18002e9ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e9f5  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Net"...
0x18002e9fc  mov     [r11-18h], rax
0x18002ea00  mov     r9d, 20019h; samDesired
0x18002ea06  xor     r8d, r8d; ulOptions
0x18002ea09  call    cs:__imp_RegOpenKeyExW
0x18002ea0f  mov     ebx, eax
0x18002ea11  test    eax, eax
0x18002ea13  jnz     short loc_18002EA57
0x18002ea15  mov     rcx, [rsp+38h+arg_18]; hKey
0x18002ea1a  lea     r9, [rsp+38h+hKey]
0x18002ea1f  xor     r8d, r8d
0x18002ea22  mov     rdx, rsi; SourceString
0x18002ea25  call    FindCreateOrDeleteConnectionKey
0x18002ea2a  mov     ebx, eax
0x18002ea2c  test    eax, eax
0x18002ea2e  jnz     short loc_18002EA4C
0x18002ea30  mov     rcx, [rsp+38h+hKey]; hKey
0x18002ea35  mov     r8, rdi
0x18002ea38  xor     edx, edx; pszSrc
0x18002ea3a  call    ReadConnectionInfoFromRegistry
0x18002ea3f  mov     rcx, [rsp+38h+hKey]; hKey
0x18002ea44  mov     ebx, eax
0x18002ea46  call    cs:__imp_RegCloseKey
0x18002ea4c  mov     rcx, [rsp+38h+arg_18]; hKey
0x18002ea51  call    cs:__imp_RegCloseKey
0x18002ea57  mov     rsi, [rsp+38h+arg_8]
0x18002ea5c  mov     eax, ebx
0x18002ea5e  mov     rbx, [rsp+38h+arg_0]
0x18002ea63  add     rsp, 30h
0x18002ea67  pop     rdi
0x18002ea68  retn
```
