# MIDL_user_allocate

- ea: `0x18000f4f0`
- end: `0x18000f4f7`
- name: `MIDL_user_allocate`
- size: `7`
- prototype: `void *__stdcall(size_t size)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000f4f0`

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
0x18000f4f0  jmp     cs:__imp_CoTaskMemAlloc
```
