# operator delete(void *,unsigned __int64)

- ea: `0x18000937c`
- end: `0x180009381`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003cd0`
- `0x18000b910`
- `0x18000b950`
- `0x18000ea58`
- `0x18000ea84`
- `0x180011008`

## callees

- `0x180009370`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18000937c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
