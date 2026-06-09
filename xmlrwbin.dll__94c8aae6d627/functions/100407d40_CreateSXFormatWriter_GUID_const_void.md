# CreateSXFormatWriter(_GUID const &,void * *)

- ea: `0x100407d40`
- end: `0x100407d48`
- name: `?CreateSXFormatWriter@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `8`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100407d50`

## pseudocode

```c
__int64 __fastcall CreateSXFormatWriter(const struct _GUID *a1, void **a2)
{
  return CreateSXFormatWriterEx(a1, a2, 0);
}

```

## disassembly

```asm
0x100407d40  xor     r8d, r8d; struct IMalloc *
0x100407d43  jmp     ?CreateSXFormatWriterEx@@YAJAEBU_GUID@@PEAPEAXPEAUIMalloc@@@Z; CreateSXFormatWriterEx(_GUID const &,void * *,IMalloc *)
```
