# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180008d08`
- end: `0x180008d0f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000317c`
- `0x180003e4c`
- `0x1800041f0`
- `0x180004830`
- `0x1800060c4`
- `0x1800074e8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180008d08  mov     ecx, 7
0x180008d0d  int     29h; Win8: RtlFailFast(ecx)
```
