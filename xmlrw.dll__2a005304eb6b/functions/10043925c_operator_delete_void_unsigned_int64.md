# operator delete(void *,unsigned __int64)

- ea: `0x10043925c`
- end: `0x100439261`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x100429550`
- `0x1004391a0`

## callees

- `0x100401370`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x10043925c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
