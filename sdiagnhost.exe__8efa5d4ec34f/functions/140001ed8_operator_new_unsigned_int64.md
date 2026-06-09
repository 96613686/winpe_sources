# operator new[](unsigned __int64)

- ea: `0x140001ed8`
- end: `0x140001edd`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400055d8`
- `0x140005ca4`
- `0x140006050`

## callees

- `0x140001174`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](size_t a1)
{
  return operator new(a1);
}

```

## disassembly

```asm
0x140001ed8  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
