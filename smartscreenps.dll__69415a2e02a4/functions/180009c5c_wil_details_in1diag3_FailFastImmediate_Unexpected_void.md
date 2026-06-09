# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180009c5c`
- end: `0x180009c63`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180006f7c`
- `0x180007aa8`
- `0x180008858`
- `0x180008bf0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009c5c  mov     ecx, 7
0x180009c61  int     29h; Win8: RtlFailFast(ecx)
```
