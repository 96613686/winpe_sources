# operator new[](unsigned __int64)

- ea: `0x1800019b4`
- end: `0x1800019b9`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180002780`
- `0x180003210`
- `0x180004da0`
- `0x180004fe0`
- `0x1800064a0`
- `0x180008680`
- `0x1800089b0`
- `0x18000e690`
- `0x180012e30`
- `0x180013560`

## callees

- `0x180001974`

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
0x1800019b4  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
