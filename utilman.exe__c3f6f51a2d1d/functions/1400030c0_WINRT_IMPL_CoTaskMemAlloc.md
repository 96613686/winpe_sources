# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x1400030c0`
- end: `0x1400030c6`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x14000dc10`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400030c0`

## pseudocode

```c
// attributes: thunk
LPVOID __stdcall WINRT_IMPL_CoTaskMemAlloc(SIZE_T cb)
{
  return CoTaskMemAlloc(cb);
}

```

## disassembly

```asm
0x1400030c0  jmp     cs:__imp_CoTaskMemAlloc
```
