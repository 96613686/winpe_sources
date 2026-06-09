# __scrt_fastfail

- ea: `0x180005be4`
- end: `0x180005be8`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005418`
- `0x180005518`
- `0x180005a44`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180005be4  mov     ecx, ecx
0x180005be6  int     29h; Win8: RtlFailFast(ecx)
```
