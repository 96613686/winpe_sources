# operator delete(void *,std::nothrow_t const &)

- ea: `0x180002814`
- end: `0x180002819`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003750`
- `0x1800043bc`
- `0x180005870`
- `0x1800058b0`
- `0x1800058f0`
- `0x18000592c`
- `0x180005960`
- `0x1800059a0`
- `0x18000a040`
- `0x18000a080`
- `0x18000a0c0`
- `0x18000a100`
- `0x18000a838`
- `0x18000aae4`
- `0x18000b1c0`
- `0x18000b388`
- `0x18000b9e0`
- `0x18000f030`
- `0x18000fd90`
- `0x18001082a`
- `0x180010871`
- `0x180010b2b`
- `0x180011154`

## callees

- `0x1800027d4`

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
0x180002814  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
