# __imp_load_CryptMsgUpdate

- ea: `0x18002368e`
- end: `0x18002369a`
- name: `__imp_load_CryptMsgUpdate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180022aca`

## import_xrefs

- `CRYPT32!CryptMsgUpdate` at `0x18002368e`

## pseudocode

```c
__int64 load_CryptMsgUpdate()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x18002368e  lea     rax, __imp_CryptMsgUpdate
0x180023695  jmp     __tailMerge_crypt32_dll
```
