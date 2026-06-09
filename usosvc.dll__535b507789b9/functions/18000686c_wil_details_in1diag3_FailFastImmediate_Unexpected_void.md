# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000686c`
- end: `0x180006873`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180003744`
- `0x180003f78`
- `0x180004348`
- `0x1800052d0`
- `0x180007078`
- `0x180008e70`
- `0x18000b35c`
- `0x18000cf7c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000686c  mov     ecx, 7
0x180006871  int     29h; Win8: RtlFailFast(ecx)
```
