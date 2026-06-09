# MIDL_user_allocate

- ea: `0x180002740`
- end: `0x180002747`
- name: `MIDL_user_allocate`
- size: `7`
- prototype: `void *__stdcall(size_t size)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002740`

## pseudocode

```c
// attributes: thunk
void *__stdcall MIDL_user_allocate(size_t size)
{
  return CoTaskMemAlloc(size);
}

```

## disassembly

```asm
0x180002740  jmp     cs:__imp_CoTaskMemAlloc
```
