# __imp_load_WinHttpGetIEProxyConfigForCurrentUser

- ea: `0x180001cc9`
- end: `0x180001cd5`
- name: `__imp_load_WinHttpGetIEProxyConfigForCurrentUser`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180001c02`

## import_xrefs

- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180001cc9`

## pseudocode

```c
__int64 load_WinHttpGetIEProxyConfigForCurrentUser()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001cc9  lea     rax, __imp_WinHttpGetIEProxyConfigForCurrentUser
0x180001cd0  jmp     __tailMerge_winhttp_dll
```
