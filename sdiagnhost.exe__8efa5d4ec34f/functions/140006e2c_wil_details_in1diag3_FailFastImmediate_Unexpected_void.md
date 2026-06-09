# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140006e2c`
- end: `0x140006e33`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140003368`
- `0x140003bd0`
- `0x140003f74`
- `0x140004da4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006e2c  mov     ecx, 7
0x140006e31  int     29h; Win8: RtlFailFast(ecx)
```
