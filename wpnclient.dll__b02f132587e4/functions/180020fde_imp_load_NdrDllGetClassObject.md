# __imp_load_NdrDllGetClassObject

- ea: `0x180020fde`
- end: `0x180020fea`
- name: `__imp_load_NdrDllGetClassObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020e25`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180020fde`

## pseudocode

```c
__int64 load_NdrDllGetClassObject()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180020fde  lea     rax, __imp_NdrDllGetClassObject
0x180020fe5  jmp     __tailMerge_rpcrt4_dll
```
