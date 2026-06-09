# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180026694`
- end: `0x180026699`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `32`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029f4`
- `0x18000480c`
- `0x180006bc4`
- `0x180007a24`
- `0x18000881c`
- `0x18000c024`
- `0x18000d6d0`
- `0x18000de34`
- `0x1800191c0`
- `0x18001b118`
- `0x180022210`
- `0x180022328`
- `0x180022590`
- `0x180022a34`
- `0x180022f20`
- `0x180023404`
- `0x180023e54`
- `0x180023ffc`
- `0x180024168`
- `0x1800242a4`
- `0x180024320`
- `0x1800243f4`
- `0x1800244bc`
- `0x1800245a4`
- `0x1800248d4`
- `0x180024e10`
- `0x1800253a8`
- `0x180025450`
- `0x1800255f4`
- `0x180025c98`
- `0x180025d8c`
- `0x180025f94`

## callees

- `0x1800266a0`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  return operator new(a1, a2);
}

```

## disassembly

```asm
0x180026694  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
