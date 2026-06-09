# __scrt_fastfail

- ea: `0x180036c48`
- end: `0x180036c4c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180036108`
- `0x180036208`
- `0x180036644`
- `0x180036870`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180036c48  mov     ecx, ecx
0x180036c4a  int     29h; Win8: RtlFailFast(ecx)
```
