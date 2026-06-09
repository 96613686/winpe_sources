# __imp_load_?TpmDeleteOwnerAuth@@YAJXZ

- ea: `0x180002bf5`
- end: `0x180002c01`
- name: `__imp_load_?TpmDeleteOwnerAuth@@YAJXZ`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b76`

## import_xrefs

- `TpmCoreProvisioning!TpmDeleteOwnerAuth` at `0x180002bf5`

## pseudocode

```c
__int64 load__TpmDeleteOwnerAuth__YAJXZ()
{
  return _tailMerge_tpmcoreprovisioning_dll();
}

```

## disassembly

```asm
0x180002bf5  lea     rax, __imp_?TpmDeleteOwnerAuth@@YAJXZ; TpmDeleteOwnerAuth(void)
0x180002bfc  jmp     __tailMerge_tpmcoreprovisioning_dll
```
