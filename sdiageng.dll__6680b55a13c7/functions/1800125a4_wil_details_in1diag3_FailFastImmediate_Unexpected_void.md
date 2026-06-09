# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800125a4`
- end: `0x1800125ab`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800089b8`
- `0x18000988c`
- `0x180009c30`
- `0x18000aa8c`
- `0x18000dee8`
- `0x18000f534`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800125a4  mov     ecx, 7
0x1800125a9  int     29h; Win8: RtlFailFast(ecx)
```
