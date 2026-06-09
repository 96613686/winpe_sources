# [thunk]:SXReader::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x100406470`
- end: `0x100406479`
- name: `?QueryInterface@SXReader@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1004047b0`

## pseudocode

```c
__int64 __fastcall SXReader::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return SXReader::QueryInterface((SXReader *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x100406470  sub     rcx, 8; this
0x100406474  jmp     ?QueryInterface@SXReader@@UEAAJAEBU_GUID@@PEAPEAX@Z; SXReader::QueryInterface(_GUID const &,void * *)
```
