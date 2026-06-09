# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18001b1ec`
- end: `0x18001b1f3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180016c04`
- `0x180017b40`
- `0x180018c54`
- `0x180018d94`
- `0x1800191a8`
- `0x1800192d0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18001b1ec  mov     ecx, 7
0x18001b1f1  int     29h; Win8: RtlFailFast(ecx)
```
