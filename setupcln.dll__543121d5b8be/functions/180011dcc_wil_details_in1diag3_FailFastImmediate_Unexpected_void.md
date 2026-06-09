# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180011dcc`
- end: `0x180011dd3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ce94`
- `0x18000e1a8`
- `0x18000f514`
- `0x18000f650`
- `0x18000fa94`
- `0x18000fbbc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180011dcc  mov     ecx, 7
0x180011dd1  int     29h; Win8: RtlFailFast(ecx)
```
