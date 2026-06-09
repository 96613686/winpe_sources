# __scrt_fastfail

- ea: `0x180036684`
- end: `0x180036688`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180035b38`
- `0x180035c38`
- `0x180036074`
- `0x1800362a0`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180036684  mov     ecx, ecx
0x180036686  int     29h; Win8: RtlFailFast(ecx)
```
