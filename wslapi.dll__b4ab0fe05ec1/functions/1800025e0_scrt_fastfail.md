# __scrt_fastfail

- ea: `0x1800025e0`
- end: `0x1800025e4`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001aa8`
- `0x180001ba8`
- `0x180001fa0`
- `0x1800021d0`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800025e0  mov     ecx, ecx
0x1800025e2  int     29h; Win8: RtlFailFast(ecx)
```
