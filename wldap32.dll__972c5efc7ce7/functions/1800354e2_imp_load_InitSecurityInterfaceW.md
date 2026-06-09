# __imp_load_InitSecurityInterfaceW

- ea: `0x1800354e2`
- end: `0x1800354ee`
- name: `__imp_load_InitSecurityInterfaceW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003525e`

## import_xrefs

- `SspiCli!InitSecurityInterfaceW` at `0x1800354e2`

## pseudocode

```c
__int64 load_InitSecurityInterfaceW()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x1800354e2  lea     rax, __imp_InitSecurityInterfaceW
0x1800354e9  jmp     __tailMerge_sspicli_dll
```
