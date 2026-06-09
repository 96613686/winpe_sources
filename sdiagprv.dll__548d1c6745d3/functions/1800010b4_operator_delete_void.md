# operator delete(void *)

- ea: `0x1800010b4`
- end: `0x1800010b9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `28`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001590`
- `0x180002450`
- `0x180003720`
- `0x180003760`
- `0x180004630`
- `0x180004670`
- `0x180005a80`
- `0x180005ac0`
- `0x1800066e0`
- `0x180006720`
- `0x180007e00`
- `0x1800084d0`
- `0x180008508`
- `0x180008530`
- `0x1800096f0`
- `0x180009b10`
- `0x180009b48`
- `0x180009b70`
- `0x180009b98`
- `0x18000d21c`
- `0x18000fa90`
- `0x1800108c0`
- `0x180010900`
- `0x1800125b0`
- `0x180013530`
- `0x180013570`
- `0x180016c40`
- `0x180018492`

## callees

- `0x180001604`

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
0x1800010b4  jmp     free_0
```
