# __scrt_fastfail

- ea: `0x14000177c`
- end: `0x140001780`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010f0`
- `0x1400011e0`
- `0x140001460`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x14000177c  mov     ecx, ecx
0x14000177e  int     29h; Win8: RtlFailFast(ecx)
```
