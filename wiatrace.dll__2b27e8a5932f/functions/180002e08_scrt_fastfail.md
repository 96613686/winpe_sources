# __scrt_fastfail

- ea: `0x180002e08`
- end: `0x180002e0c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002668`
- `0x180002768`
- `0x180002c68`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180002e08  mov     ecx, ecx
0x180002e0a  int     29h; Win8: RtlFailFast(ecx)
```
