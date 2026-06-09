# __imp_load_SspiPrepareForCredWrite

- ea: `0x18002084a`
- end: `0x180020856`
- name: `__imp_load_SspiPrepareForCredWrite`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800207cb`

## import_xrefs

- `SspiCli!SspiPrepareForCredWrite` at `0x18002084a`

## pseudocode

```c
__int64 load_SspiPrepareForCredWrite()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x18002084a  lea     rax, __imp_SspiPrepareForCredWrite
0x180020851  jmp     __tailMerge_sspicli_dll
```
