# __scrt_fastfail

- ea: `0x140004fa8`
- end: `0x140004fac`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140004920`
- `0x140004a10`
- `0x140004c74`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x140004fa8  mov     ecx, ecx
0x140004faa  int     29h; Win8: RtlFailFast(ecx)
```
