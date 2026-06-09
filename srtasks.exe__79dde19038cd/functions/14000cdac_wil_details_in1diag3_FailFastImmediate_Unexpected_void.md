# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000cdac`
- end: `0x14000cdb3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140008188`
- `0x140008c5c`
- `0x140009000`
- `0x1400093d0`
- `0x14000a790`
- `0x14000b888`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000cdac  mov     ecx, 7
0x14000cdb1  int     29h; Win8: RtlFailFast(ecx)
```
