# operator delete(void *)

- ea: `0x180024ea4`
- end: `0x180024eab`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `83`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800016f0`
- `0x180001e8c`
- `0x1800023a0`
- `0x180002534`
- `0x180002ff0`
- `0x180003bec`
- `0x180005550`
- `0x180005cc8`
- `0x180005d48`
- `0x180005e40`
- `0x1800063b4`
- `0x180006580`
- `0x180008b9c`
- `0x180008cc0`
- `0x180008d30`
- `0x180008da0`
- `0x180008df0`
- `0x180008e40`
- `0x180008ea0`
- `0x180008f00`
- `0x180008f60`
- `0x180008fc0`
- `0x180009020`
- `0x1800090e0`
- `0x1800092a4`
- `0x180009744`
- `0x180009cc4`
- `0x180009de0`
- `0x18000aeec`
- `0x18000b5f4`
- `0x18000bcfc`
- `0x18000c48c`
- `0x18000cfcc`
- `0x18000d408`
- `0x18000da10`
- `0x18000e630`
- `0x18000fa74`
- `0x18000fe28`
- `0x180011bdc`
- `0x180012458`
- `0x180012e04`
- `0x180012e3c`
- `0x180012ea0`
- `0x180012ed0`
- `0x180013780`
- `0x180013890`
- `0x1800139f0`
- `0x180013b00`
- `0x1800147f0`
- `0x180015600`

## import_xrefs

- `msvcrt!free` at `0x180024ea4`

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
0x180024ea4  jmp     cs:__imp_free
```
