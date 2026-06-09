# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000627c`
- end: `0x140006283`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400031e8`
- `0x140003a18`
- `0x140003de8`
- `0x140004cc0`
- `0x140006aec`
- `0x140008c30`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000627c  mov     ecx, 7
0x140006281  int     29h; Win8: RtlFailFast(ecx)
```
