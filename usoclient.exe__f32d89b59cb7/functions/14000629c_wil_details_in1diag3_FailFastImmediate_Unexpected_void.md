# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000629c`
- end: `0x1400062a3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140003208`
- `0x140003a38`
- `0x140003e08`
- `0x140004ce0`
- `0x140006b0c`
- `0x140008c00`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000629c  mov     ecx, 7
0x1400062a1  int     29h; Win8: RtlFailFast(ecx)
```
