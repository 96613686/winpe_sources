# __scrt_fastfail

- ea: `0x1400019b4`
- end: `0x1400019b8`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001300`
- `0x1400013f0`
- `0x140001668`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1400019b4  mov     ecx, ecx
0x1400019b6  int     29h; Win8: RtlFailFast(ecx)
```
