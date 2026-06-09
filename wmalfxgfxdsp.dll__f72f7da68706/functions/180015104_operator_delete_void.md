# operator delete(void *)

- ea: `0x180015104`
- end: `0x180015109`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `25`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007030`
- `0x180008c60`
- `0x180009794`
- `0x1800099bc`
- `0x180009a94`
- `0x180009b08`
- `0x18000a010`
- `0x18000a030`
- `0x18000a058`
- `0x18000a4f0`
- `0x18000fb40`
- `0x18000fdb4`
- `0x180010200`
- `0x1800123d0`
- `0x1800124f8`
- `0x180012530`
- `0x1800160c0`
- `0x180016114`
- `0x1800166d0`
- `0x180016a1c`
- `0x18001f8f0`
- `0x180075c60`
- `0x180077050`
- `0x180077090`
- `0x18007a7f0`

## callees

- `0x180015e30`

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
0x180015104  jmp     free
```
