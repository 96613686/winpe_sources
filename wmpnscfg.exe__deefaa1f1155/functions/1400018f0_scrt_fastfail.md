# __scrt_fastfail

- ea: `0x1400018f0`
- end: `0x1400018f4`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001250`
- `0x140001340`
- `0x140001594`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1400018f0  mov     ecx, ecx
0x1400018f2  int     29h; Win8: RtlFailFast(ecx)
```
