# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000b818`
- end: `0x18000b81f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002dc0`
- `0x180004e8c`
- `0x18000796c`
- `0x1800091fc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000b818  mov     ecx, 7
0x18000b81d  int     29h; Win8: RtlFailFast(ecx)
```
