# operator delete(void *,std::nothrow_t const &)

- ea: `0x18000213c`
- end: `0x180002141`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `30`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003d58`
- `0x180004544`
- `0x1800045ac`
- `0x180004ed0`
- `0x180004f10`
- `0x180004f50`
- `0x180004fb0`
- `0x180005020`
- `0x180005060`
- `0x1800050c0`
- `0x180005120`
- `0x180005150`
- `0x18000e77c`
- `0x18000fc28`
- `0x18000fc90`
- `0x18000fe38`
- `0x18000ff10`
- `0x18000ff80`
- `0x180010000`
- `0x180010050`
- `0x18001008c`
- `0x1800114a0`
- `0x1800117d0`
- `0x180013010`
- `0x180013170`
- `0x1800141a0`
- `0x180014fab`
- `0x18001501e`
- `0x18001564f`
- `0x180015672`

## callees

- `0x1800020c4`

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
0x18000213c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
