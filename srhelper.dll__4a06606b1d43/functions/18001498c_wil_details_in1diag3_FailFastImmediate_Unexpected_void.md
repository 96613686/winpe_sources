# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18001498c`
- end: `0x180014993`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fcb8`
- `0x18001078c`
- `0x180010b30`
- `0x180010f00`
- `0x1800122c0`
- `0x180013468`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18001498c  mov     ecx, 7
0x180014991  int     29h; Win8: RtlFailFast(ecx)
```
