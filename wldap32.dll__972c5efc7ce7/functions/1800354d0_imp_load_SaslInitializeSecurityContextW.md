# __imp_load_SaslInitializeSecurityContextW

- ea: `0x1800354d0`
- end: `0x1800354dc`
- name: `__imp_load_SaslInitializeSecurityContextW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003525e`

## import_xrefs

- `SspiCli!SaslInitializeSecurityContextW` at `0x1800354d0`

## pseudocode

```c
__int64 load_SaslInitializeSecurityContextW()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x1800354d0  lea     rax, __imp_SaslInitializeSecurityContextW
0x1800354d7  jmp     __tailMerge_sspicli_dll
```
