# MIDL_user_free

- ea: `0x18000f500`
- end: `0x18000f507`
- name: `MIDL_user_free`
- size: `7`
- prototype: `void __stdcall(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000f500`

## pseudocode

```c
// attributes: thunk
void __stdcall MIDL_user_free(void *a1)
{
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x18000f500  jmp     cs:__imp_CoTaskMemFree
```
