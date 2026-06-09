# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000eab4`
- end: `0x18000eabb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180006b48`
- `0x180008288`
- `0x18000a414`
- `0x18000c004`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000eab4  mov     ecx, 7
0x18000eab9  int     29h; Win8: RtlFailFast(ecx)
```
