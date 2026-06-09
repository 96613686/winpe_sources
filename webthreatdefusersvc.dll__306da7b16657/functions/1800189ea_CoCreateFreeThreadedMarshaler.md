# CoCreateFreeThreadedMarshaler

- ea: `0x1800189ea`
- end: `0x1800189f0`
- name: `CoCreateFreeThreadedMarshaler`
- size: `6`
- prototype: `HRESULT __stdcall(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180015a8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800189ea`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall CoCreateFreeThreadedMarshaler(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)
{
  return __imp_CoCreateFreeThreadedMarshaler(punkOuter, ppunkMarshal);
}

```

## disassembly

```asm
0x1800189ea  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
