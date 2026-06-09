# __imp_load_MesDecodeBufferHandleCreate

- ea: `0x18001c92f`
- end: `0x18001c93b`
- name: `__imp_load_MesDecodeBufferHandleCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c856`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001c92f`

## pseudocode

```c
__int64 load_MesDecodeBufferHandleCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001c92f  lea     rax, __imp_MesDecodeBufferHandleCreate
0x18001c936  jmp     __tailMerge_rpcrt4_dll
```
