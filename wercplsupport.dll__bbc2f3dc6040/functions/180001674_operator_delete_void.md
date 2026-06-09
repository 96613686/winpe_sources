# operator delete(void *)

- ea: `0x180001674`
- end: `0x180001679`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001680`
- `0x180002200`
- `0x180002b80`
- `0x180007450`
- `0x1800076c8`
- `0x180009810`
- `0x180009890`
- `0x180009910`
- `0x180009990`
- `0x180009a10`
- `0x180009a90`
- `0x180009ac0`
- `0x180009b00`
- `0x180009b40`

## callees

- `0x180001c74`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001674  jmp     free_0
```
