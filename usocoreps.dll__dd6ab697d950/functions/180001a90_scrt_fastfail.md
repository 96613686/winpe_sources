# __scrt_fastfail

- ea: `0x180001a90`
- end: `0x180001a94`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011e8`
- `0x1800012e8`
- `0x18000171c`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001a90  mov     ecx, ecx
0x180001a92  int     29h; Win8: RtlFailFast(ecx)
```
