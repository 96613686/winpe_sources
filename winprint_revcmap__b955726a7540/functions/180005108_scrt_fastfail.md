# __scrt_fastfail

- ea: `0x180005108`
- end: `0x18000510c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004968`
- `0x180004a68`
- `0x180004f68`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180005108  mov     ecx, ecx
0x18000510a  int     29h; Win8: RtlFailFast(ecx)
```
