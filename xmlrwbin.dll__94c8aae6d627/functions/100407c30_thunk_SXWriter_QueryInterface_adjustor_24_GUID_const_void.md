# [thunk]:SXWriter::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x100407c30`
- end: `0x100407c39`
- name: `?QueryInterface@SXWriter@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100408070`

## pseudocode

```c
__int64 __fastcall SXWriter::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return SXWriter::QueryInterface((SXWriter *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x100407c30  sub     rcx, 18h; this
0x100407c34  jmp     ?QueryInterface@SXWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z; SXWriter::QueryInterface(_GUID const &,void * *)
```
