# operator delete(void *)

- ea: `0x18000bde4`
- end: `0x18000bde9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002e50`
- `0x180007c40`
- `0x18000b920`
- `0x18000bf60`
- `0x18000c030`

## callees

- `0x18000c15c`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x18000bde4  jmp     free
```
