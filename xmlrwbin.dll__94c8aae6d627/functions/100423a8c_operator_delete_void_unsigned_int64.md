# operator delete(void *,unsigned __int64)

- ea: `0x100423a8c`
- end: `0x100423a91`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x100407bb0`
- `0x1004195c0`
- `0x1004239d0`

## callees

- `0x100401250`

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
0x100423a8c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
