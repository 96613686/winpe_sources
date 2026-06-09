# __scrt_fastfail

- ea: `0x180002248`
- end: `0x18000224c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001aa8`
- `0x180001ba8`
- `0x1800020a8`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180002248  mov     ecx, ecx
0x18000224a  int     29h; Win8: RtlFailFast(ecx)
```
