# operator delete(void *)

- ea: `0x1800012a4`
- end: `0x1800012a9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `114`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001410`
- `0x180001450`
- `0x180001a10`
- `0x1800020f8`
- `0x180002280`
- `0x180002338`
- `0x1800025c8`
- `0x1800026a0`
- `0x180002d20`
- `0x1800034c4`
- `0x180004518`
- `0x180004d58`
- `0x18000533c`
- `0x18000571c`
- `0x180005d60`
- `0x180005ffc`
- `0x18000615c`
- `0x1800066f8`
- `0x18000680c`
- `0x18000698c`
- `0x180006a90`
- `0x180007000`
- `0x180007184`
- `0x1800076a4`
- `0x18000787c`
- `0x180007bc0`
- `0x180007f0c`
- `0x180008184`
- `0x1800097f0`
- `0x180009820`
- `0x180009860`
- `0x18000a86c`
- `0x18000ad80`
- `0x18000bef0`
- `0x18000c144`
- `0x18000c31c`
- `0x18000c3fc`
- `0x18000c910`
- `0x18000cf00`
- `0x18000d63c`
- `0x18000e4a8`
- `0x18000fbd0`
- `0x18000fc10`
- `0x18000fcf0`
- `0x1800100b0`
- `0x1800101cc`
- `0x1800114dc`
- `0x180011630`
- `0x180011888`
- `0x180011ba4`

## callees

- `0x180001c62`

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
0x1800012a4  jmp     free_0
```
