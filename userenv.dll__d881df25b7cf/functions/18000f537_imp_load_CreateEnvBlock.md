# __imp_load_CreateEnvBlock

- ea: `0x18000f537`
- end: `0x18000f543`
- name: `__imp_load_CreateEnvBlock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f4a6`

## import_xrefs

- `profapi!__imp_CreateEnvBlock` at `0x18000f537`

## pseudocode

```c
__int64 load_CreateEnvBlock()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18000f537  lea     rax, __imp_CreateEnvBlock
0x18000f53e  jmp     __tailMerge_profapi_dll
```
