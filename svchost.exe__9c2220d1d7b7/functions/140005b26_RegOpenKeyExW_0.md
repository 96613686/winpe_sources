# RegOpenKeyExW_0

- ea: `0x140005b26`
- end: `0x140005b2c`
- name: `RegOpenKeyExW_0`
- size: `6`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140002830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005b26`

## pseudocode

```c
// attributes: thunk
LSTATUS __stdcall RegOpenKeyExW_0(HKEY hKey, LPCWSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult)
{
  return RegOpenKeyExW(hKey, lpSubKey, ulOptions, samDesired, phkResult);
}

```

## disassembly

```asm
0x140005b26  jmp     cs:__imp_RegOpenKeyExW
```
