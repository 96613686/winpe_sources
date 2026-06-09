# operator delete(void *,std::nothrow_t const &)

- ea: `0x180003038`
- end: `0x18000303d`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009580`
- `0x18000ae78`
- `0x18000f44c`
- `0x18000f630`
- `0x18000f6b0`
- `0x18000f800`
- `0x180010938`

## callees

- `0x18000302c`

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
0x180003038  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
