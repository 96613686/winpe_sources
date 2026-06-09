# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000493c`
- end: `0x140004943`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400021b0`
- `0x1400026bc`
- `0x140002a8c`
- `0x140003a14`
- `0x14000539c`
- `0x140009cd8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000493c  mov     ecx, 7
0x140004941  int     29h; Win8: RtlFailFast(ecx)
```
