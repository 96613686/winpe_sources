# WsQueryGlobalMappingFromRegistry

- ea: `0x180031538`
- end: `0x1800315f0`
- name: `WsQueryGlobalMappingFromRegistry`
- size: `184`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800012a0`

## callees

- `0x18003097c`
- `0x180030d6c`
- `0x180031538`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003157d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003157d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800315c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800315d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800315c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800315d1`

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
0x180031538  mov     r11, rsp
0x18003153b  mov     [r11+8], rbx
0x18003153f  mov     [r11+10h], rsi
0x180031543  push    rdi
0x180031544  sub     rsp, 30h
0x180031548  mov     rdi, rdx
0x18003154b  mov     qword ptr [r11+20h], 0
0x180031553  mov     rsi, rcx
0x180031556  mov     qword ptr [r11+18h], 0
0x18003155e  lea     rax, [r11+20h]
0x180031562  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031569  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Net"...
0x180031570  mov     [r11-18h], rax
0x180031574  mov     r9d, 20019h; samDesired
0x18003157a  xor     r8d, r8d; ulOptions
0x18003157d  call    cs:__imp_RegOpenKeyExW
0x180031584  nop     dword ptr [rax+rax+00h]
0x180031589  mov     ebx, eax
0x18003158b  test    eax, eax
0x18003158d  jnz     short loc_1800315DD
0x18003158f  mov     rcx, [rsp+38h+arg_18]; hKey
0x180031594  lea     r9, [rsp+38h+hKey]
0x180031599  xor     r8d, r8d
0x18003159c  mov     rdx, rsi; SourceString
0x18003159f  call    FindCreateOrDeleteConnectionKey
0x1800315a4  mov     ebx, eax
0x1800315a6  test    eax, eax
0x1800315a8  jnz     short loc_1800315CC
0x1800315aa  mov     rcx, [rsp+38h+hKey]; hKey
0x1800315af  mov     r8, rdi
0x1800315b2  xor     edx, edx; pszSrc
0x1800315b4  call    ReadConnectionInfoFromRegistry
0x1800315b9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800315be  mov     ebx, eax
0x1800315c0  call    cs:__imp_RegCloseKey
0x1800315c7  nop     dword ptr [rax+rax+00h]
0x1800315cc  mov     rcx, [rsp+38h+arg_18]; hKey
0x1800315d1  call    cs:__imp_RegCloseKey
0x1800315d8  nop     dword ptr [rax+rax+00h]
0x1800315dd  mov     rsi, [rsp+38h+arg_8]
0x1800315e2  mov     eax, ebx
0x1800315e4  mov     rbx, [rsp+38h+arg_0]
0x1800315e9  add     rsp, 30h
0x1800315ed  pop     rdi
0x1800315ee  retn
```
