# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180002730`
- end: `0x180002737`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d9c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180002730  mov     ecx, 7
0x180002735  int     29h; Win8: RtlFailFast(ecx)
```
