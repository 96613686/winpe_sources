# CreateSAXAttributes(_GUID const &,void * *)

- ea: `0x100413e80`
- end: `0x100413e88`
- name: `?CreateSAXAttributes@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `8`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100413e90`

## pseudocode

```c
__int64 __fastcall CreateSAXAttributes(const struct _GUID *a1, void **a2)
{
  return CreateSAXAttributesEx(a1, a2, 0);
}

```

## disassembly

```asm
0x100413e80  xor     r8d, r8d; struct IMalloc *
0x100413e83  jmp     ?CreateSAXAttributesEx@@YAJAEBU_GUID@@PEAPEAXPEAUIMalloc@@@Z; CreateSAXAttributesEx(_GUID const &,void * *,IMalloc *)
```
