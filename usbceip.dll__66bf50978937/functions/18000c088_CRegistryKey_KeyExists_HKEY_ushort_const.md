# CRegistryKey::KeyExists(HKEY__ *,ushort const *)

- ea: `0x18000c088`
- end: `0x18000c0c8`
- name: `?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z`
- size: `64`
- prototype: `unsigned __int8 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005e94`
- `0x1800066a8`
- `0x1800078e0`
- `0x180008b6c`
- `0x180008bf0`
- `0x180008f48`
- `0x1800090d4`
- `0x180009424`
- `0x180009748`
- `0x180009c50`
- `0x180009d50`
- `0x180009e50`

## callees

- `0x18000c088`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c0bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c0bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c0a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c0a8`

## pseudocode

```c
unsigned __int8 __fastcall CRegistryKey::KeyExists(HKEY a1, const unsigned __int16 *a2)
{
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey) )
    return 0;
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x18000c088  sub     rsp, 38h
0x18000c08c  lea     rax, [rsp+38h+hKey]
0x18000c091  mov     [rsp+38h+hKey], 0
0x18000c09a  mov     r9d, 20019h; samDesired
0x18000c0a0  mov     [rsp+38h+phkResult], rax; phkResult
0x18000c0a5  xor     r8d, r8d; ulOptions
0x18000c0a8  call    cs:__imp_RegOpenKeyExW
0x18000c0ae  test    eax, eax
0x18000c0b0  jz      short loc_18000C0B6
0x18000c0b2  xor     al, al
0x18000c0b4  jmp     short loc_18000C0C3
0x18000c0b6  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c0bb  call    cs:__imp_RegCloseKey
0x18000c0c1  mov     al, 1
0x18000c0c3  add     rsp, 38h
0x18000c0c7  retn
```
