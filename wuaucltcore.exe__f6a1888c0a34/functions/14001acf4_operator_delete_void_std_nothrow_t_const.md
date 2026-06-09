# operator delete(void *,std::nothrow_t const &)

- ea: `0x14001acf4`
- end: `0x14001acf9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `48`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002e60`
- `0x140003970`
- `0x140006610`
- `0x140006640`
- `0x140006f90`
- `0x140007460`
- `0x140007e50`
- `0x140008060`
- `0x1400090f0`
- `0x140009214`
- `0x140009400`
- `0x140009650`
- `0x140009790`
- `0x140009dc0`
- `0x14000b070`
- `0x14000b0b0`
- `0x14000be70`
- `0x14000c2f0`
- `0x1400118f0`
- `0x14001192c`
- `0x140011c50`
- `0x140013600`
- `0x1400138f4`
- `0x140013a74`
- `0x140013b78`
- `0x140013bbc`
- `0x140013c24`
- `0x140013c68`
- `0x140013cac`
- `0x140013cf0`
- `0x140013d70`
- `0x140013de4`
- `0x140013e54`
- `0x140015c4c`
- `0x140016318`
- `0x1400164c8`
- `0x14001671c`
- `0x1400168cc`
- `0x140016cd4`
- `0x140016ef8`
- `0x1400174fc`
- `0x140017624`
- `0x1400178a0`
- `0x140017b48`
- `0x140017f58`
- `0x140018da0`
- `0x14001a580`
- `0x14002167b`

## callees

- `0x14001b758`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x14001acf4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
