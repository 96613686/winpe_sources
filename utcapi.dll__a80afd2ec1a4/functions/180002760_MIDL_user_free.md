# MIDL_user_free

- ea: `0x180002760`
- end: `0x180002767`
- name: `MIDL_user_free`
- size: `7`
- prototype: `void __stdcall(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002760`

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
0x180002760  jmp     cs:__imp_CoTaskMemFree
```
