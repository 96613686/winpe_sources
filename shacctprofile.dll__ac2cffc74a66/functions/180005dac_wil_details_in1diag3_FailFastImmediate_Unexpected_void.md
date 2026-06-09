# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180005dac`
- end: `0x180005db3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800036bc`
- `0x180003bd0`
- `0x180003f74`
- `0x180004e30`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180005dac  mov     ecx, 7
0x180005db1  int     29h; Win8: RtlFailFast(ecx)
```
