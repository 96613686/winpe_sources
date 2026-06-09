# operator delete(void *)

- ea: `0x140001048`
- end: `0x14000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `30`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001920`
- `0x140001da0`
- `0x140001dd8`
- `0x140002310`
- `0x140002b30`
- `0x140006004`
- `0x1400067c4`
- `0x140006c88`
- `0x140008c70`
- `0x14000a568`
- `0x14000a880`
- `0x14000b184`
- `0x14000b4c8`
- `0x14000c690`
- `0x14000c6d0`
- `0x14000d0e0`
- `0x14000e384`
- `0x140010710`
- `0x140010b40`
- `0x140010bf0`
- `0x14001108c`
- `0x1400110dc`
- `0x140011cc0`
- `0x140011cf8`
- `0x140011d30`
- `0x140014190`
- `0x140014260`
- `0x140015fa0`
- `0x140016100`
- `0x140016840`

## callees

- `0x14000147c`

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
0x140001048  jmp     free_0
```
