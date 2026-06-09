# __imp_load_WinHttpGetIEProxyConfigForCurrentUser

- ea: `0x18000173b`
- end: `0x180001747`
- name: `__imp_load_WinHttpGetIEProxyConfigForCurrentUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000159c`

## import_xrefs

- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000173b`

## pseudocode

```c
__int64 load_WinHttpGetIEProxyConfigForCurrentUser()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x18000173b  lea     rax, __imp_WinHttpGetIEProxyConfigForCurrentUser
0x180001742  jmp     __tailMerge_winhttp_dll
```
