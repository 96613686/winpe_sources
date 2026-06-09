# __imp_load_SspiPrepareForCredWrite

- ea: `0x18001f09a`
- end: `0x18001f0a6`
- name: `__imp_load_SspiPrepareForCredWrite`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f01b`

## import_xrefs

- `SspiCli!SspiPrepareForCredWrite` at `0x18001f09a`

## pseudocode

```c
__int64 load_SspiPrepareForCredWrite()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x18001f09a  lea     rax, __imp_SspiPrepareForCredWrite
0x18001f0a1  jmp     __tailMerge_sspicli_dll
```
