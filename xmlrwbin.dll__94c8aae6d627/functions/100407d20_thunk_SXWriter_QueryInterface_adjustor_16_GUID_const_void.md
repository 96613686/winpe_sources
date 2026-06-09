# [thunk]:SXWriter::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x100407d20`
- end: `0x100407d29`
- name: `?QueryInterface@SXWriter@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return SXWriter::QueryInterface((SXWriter *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x100407d20  sub     rcx, 10h; this
0x100407d24  jmp     ?QueryInterface@SXWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z; SXWriter::QueryInterface(_GUID const &,void * *)
```
