# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000c468`
- end: `0x18000c46f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180008bb0`
- `0x18000a570`
- `0x18000a904`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000c468  mov     ecx, 7
0x18000c46d  int     29h; Win8: RtlFailFast(ecx)
```
