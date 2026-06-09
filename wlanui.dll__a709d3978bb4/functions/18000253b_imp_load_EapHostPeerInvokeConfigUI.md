# __imp_load_EapHostPeerInvokeConfigUI

- ea: `0x18000253b`
- end: `0x180002547`
- name: `__imp_load_EapHostPeerInvokeConfigUI`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002498`

## import_xrefs

- `eappcfg!EapHostPeerInvokeConfigUI` at `0x18000253b`

## pseudocode

```c
__int64 load_EapHostPeerInvokeConfigUI()
{
  return _tailMerge_eappcfg_dll();
}

```

## disassembly

```asm
0x18000253b  lea     rax, __imp_EapHostPeerInvokeConfigUI
0x180002542  jmp     __tailMerge_eappcfg_dll
```
