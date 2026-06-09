# ___scrt_fastfail

- ea: `0x100040b6`
- end: `0x100040c0`
- name: `___scrt_fastfail`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x100038db`
- `0x100039eb`
- `0x10003f29`

## pseudocode

```c
void __cdecl __noreturn __scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x100040b6  mov     edi, edi
0x100040b8  push    ebp
0x100040b9  mov     ebp, esp
0x100040bb  mov     ecx, [ebp+arg_0]
0x100040be  int     29h; Win8: RtlFailFast(ecx)
```
