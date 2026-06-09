# WINRT_IMPL_CoCreateFreeThreadedMarshaler

- ea: `0x140003545`
- end: `0x14000354b`
- name: `WINRT_IMPL_CoCreateFreeThreadedMarshaler`
- size: `6`
- prototype: `HRESULT __stdcall(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14001080c`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x140003545`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall WINRT_IMPL_CoCreateFreeThreadedMarshaler(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)
{
  return CoCreateFreeThreadedMarshaler(punkOuter, ppunkMarshal);
}

```

## disassembly

```asm
0x140003545  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
