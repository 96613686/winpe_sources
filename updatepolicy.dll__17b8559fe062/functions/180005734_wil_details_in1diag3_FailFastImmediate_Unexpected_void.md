# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180005734`
- end: `0x18000573b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180005320`
- `0x1800061d0`
- `0x180006560`
- `0x180006ea8`
- `0x180009e48`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180005734  mov     ecx, 7
0x180005739  int     29h; Win8: RtlFailFast(ecx)
```
