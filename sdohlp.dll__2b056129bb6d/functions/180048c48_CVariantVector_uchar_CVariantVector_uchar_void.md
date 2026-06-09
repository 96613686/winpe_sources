# CVariantVector<uchar>::~CVariantVector<uchar>(void)

- ea: `0x180048c48`
- end: `0x180048c52`
- name: `??1?$CVariantVector@E@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180056c7e`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180048c4b`

## pseudocode

```c
HRESULT __fastcall CVariantVector<unsigned char>::~CVariantVector<unsigned char>(SAFEARRAY **a1)
{
  return SafeArrayUnaccessData(*a1);
}

```

## disassembly

```asm
0x180048c48  mov     rcx, [rcx]
0x180048c4b  jmp     cs:__imp_SafeArrayUnaccessData
```
