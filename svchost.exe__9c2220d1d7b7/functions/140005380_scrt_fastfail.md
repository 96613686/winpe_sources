# __scrt_fastfail

- ea: `0x140005380`
- end: `0x140005384`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140004ce0`
- `0x140004dd0`
- `0x140005034`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x140005380  mov     ecx, ecx
0x140005382  int     29h; Win8: RtlFailFast(ecx)
```
