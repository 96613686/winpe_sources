# operator new[](unsigned __int64)

- ea: `0x1800011ac`
- end: `0x1800011b1`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180005240`
- `0x180006a9c`
- `0x1800073dc`
- `0x1800079e0`
- `0x18000b370`
- `0x18000bf3c`
- `0x18000d9b0`
- `0x18000e078`
- `0x18000f1e8`

## callees

- `0x1800011b8`

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
0x1800011ac  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
