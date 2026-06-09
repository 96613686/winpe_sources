# __scrt_fastfail

- ea: `0x14000187c`
- end: `0x140001880`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011f0`
- `0x1400012e0`
- `0x140001560`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x14000187c  mov     ecx, ecx
0x14000187e  int     29h; Win8: RtlFailFast(ecx)
```
