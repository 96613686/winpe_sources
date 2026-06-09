# operator delete(void *,unsigned __int64)

- ea: `0x180010334`
- end: `0x180010339`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `30`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003cc0`
- `0x180004080`
- `0x180004670`
- `0x180005670`
- `0x180009a38`
- `0x180009ed0`
- `0x18000a040`
- `0x18000a210`
- `0x18000a430`
- `0x18000ac80`
- `0x18000b090`
- `0x18000b1b4`
- `0x18000b2f4`
- `0x18000ba80`
- `0x18000bac0`
- `0x18000cfc0`
- `0x18000d1cc`
- `0x18000d3b4`
- `0x18000e110`
- `0x18000e144`
- `0x18000e240`
- `0x18000ec40`
- `0x18000f200`
- `0x18000f23c`
- `0x18000f2b0`
- `0x18000f340`
- `0x18000f384`
- `0x18000fb80`
- `0x180015de1`
- `0x180015e07`

## callees

- `0x180010c64`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180010334  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
