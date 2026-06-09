# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000ff0c`
- end: `0x18000ff13`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ac9c`
- `0x18000b794`
- `0x18000bb64`
- `0x18000bf5c`
- `0x18000d470`
- `0x18000e75c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000ff0c  mov     ecx, 7
0x18000ff11  int     29h; Win8: RtlFailFast(ecx)
```
