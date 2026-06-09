# operator delete(void *)

- ea: `0x180021268`
- end: `0x18002126d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `21`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012aa4`
- `0x180013c60`
- `0x180016b14`
- `0x180017fd0`
- `0x18001ca4c`
- `0x18001cac4`
- `0x18001cb28`
- `0x18001cce0`
- `0x18001e454`
- `0x18001e47c`
- `0x18001e6c0`
- `0x180020828`
- `0x180020860`
- `0x18003cf0c`
- `0x18003cff4`
- `0x18003d0bc`
- `0x18003d184`
- `0x18003d380`
- `0x18003dc74`
- `0x18003dedc`
- `0x18003f5e4`

## callees

- `0x18002140c`

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
0x180021268  jmp     free
```
