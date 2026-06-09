# CreateSXFormatReader(_GUID const &,void * *)

- ea: `0x1004040a0`
- end: `0x1004040a8`
- name: `?CreateSXFormatReader@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `8`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1004040b0`

## pseudocode

```c
__int64 __fastcall CreateSXFormatReader(const struct _GUID *a1, void **a2)
{
  return CreateSXFormatReaderEx(a1, a2, 0);
}

```

## disassembly

```asm
0x1004040a0  xor     r8d, r8d; struct IMalloc *
0x1004040a3  jmp     ?CreateSXFormatReaderEx@@YAJAEBU_GUID@@PEAPEAXPEAUIMalloc@@@Z; CreateSXFormatReaderEx(_GUID const &,void * *,IMalloc *)
```
