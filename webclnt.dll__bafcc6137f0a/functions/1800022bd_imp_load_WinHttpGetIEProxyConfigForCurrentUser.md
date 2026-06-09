# __imp_load_WinHttpGetIEProxyConfigForCurrentUser

- ea: `0x1800022bd`
- end: `0x1800022c9`
- name: `__imp_load_WinHttpGetIEProxyConfigForCurrentUser`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180001c86`

## import_xrefs

- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800022bd`

## pseudocode

```c
__int64 load_WinHttpGetIEProxyConfigForCurrentUser()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800022bd  lea     rax, __imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800022c4  jmp     __tailMerge_winhttp_dll
```
