# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18001c710`
- end: `0x18001c717`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180017e5c`
- `0x180018eec`
- `0x18001a0b4`
- `0x18001a1f8`
- `0x18001a624`
- `0x18001a74c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18001c710  mov     ecx, 7
0x18001c715  int     29h; Win8: RtlFailFast(ecx)
```
