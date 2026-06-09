# operator delete(void *)

- ea: `0x180001ce0`
- end: `0x180001ce5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001cd4`
- `0x180001eb0`
- `0x180001f70`
- `0x1800040b4`
- `0x180004a70`
- `0x180005990`
- `0x180005a9c`

## callees

- `0x180001ca2`

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
0x180001ce0  jmp     free
```
