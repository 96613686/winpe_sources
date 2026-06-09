# CSafeArray::Access(void * *)

- ea: `0x1800119a0`
- end: `0x1800119ab`
- name: `?Access@CSafeArray@@QEAAJPEAPEAX@Z`
- size: `11`
- prototype: `HRESULT __fastcall(SAFEARRAY **this, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800119a4`

## pseudocode

```c
HRESULT __fastcall CSafeArray::Access(SAFEARRAY **this, void **a2)
{
  return SafeArrayAccessData(this[4], a2);
}

```

## disassembly

```asm
0x1800119a0  mov     rcx, [rcx+20h]
0x1800119a4  jmp     cs:__imp_SafeArrayAccessData
```
