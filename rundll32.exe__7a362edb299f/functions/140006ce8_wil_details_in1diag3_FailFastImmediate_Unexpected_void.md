# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140006ce8`
- end: `0x140006cef`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140003444`
- `0x140003b94`
- `0x140003ffc`
- `0x140005408`
- `0x14000897c`
- `0x140009d94`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006ce8  mov     ecx, 7
0x140006ced  int     29h; Win8: RtlFailFast(ecx)
```
