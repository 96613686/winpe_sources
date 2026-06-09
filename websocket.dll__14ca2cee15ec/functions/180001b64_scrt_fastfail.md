# __scrt_fastfail

- ea: `0x180001b64`
- end: `0x180001b68`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001358`
- `0x180001458`
- `0x180001918`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001b64  mov     ecx, ecx
0x180001b66  int     29h; Win8: RtlFailFast(ecx)
```
