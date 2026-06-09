# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800026fc`
- end: `0x180002703`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d94`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800026fc  mov     ecx, 7
0x180002701  int     29h; Win8: RtlFailFast(ecx)
```
