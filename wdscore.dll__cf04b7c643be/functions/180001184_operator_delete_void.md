# operator delete(void *)

- ea: `0x180001184`
- end: `0x180001189`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `33`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001a70`
- `0x180009a48`
- `0x18000f568`
- `0x18000f590`
- `0x18000f5d0`
- `0x18000f600`
- `0x18000f638`
- `0x18000f664`
- `0x18001220c`
- `0x180018994`
- `0x180019e40`
- `0x180019e68`
- `0x180019e90`
- `0x18001e2ec`
- `0x18001e314`
- `0x18001eaa0`
- `0x180020590`
- `0x1800205c0`
- `0x1800205f0`
- `0x180020da0`
- `0x180020de0`
- `0x180021dec`
- `0x180021ff0`
- `0x180023650`
- `0x180025978`
- `0x1800259b0`
- `0x1800259d8`
- `0x1800265a0`
- `0x1800265d0`
- `0x180026b50`
- `0x1800287f6`
- `0x180029345`
- `0x18002942b`

## callees

- `0x180001c02`

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
0x180001184  jmp     free_0
```
