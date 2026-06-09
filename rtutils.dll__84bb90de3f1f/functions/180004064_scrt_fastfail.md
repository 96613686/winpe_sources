# __scrt_fastfail

- ea: `0x180004064`
- end: `0x180004068`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003898`
- `0x180003998`
- `0x180003ec4`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180004064  mov     ecx, ecx
0x180004066  int     29h; Win8: RtlFailFast(ecx)
```
