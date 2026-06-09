# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000b494`
- end: `0x18000b49b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004638`
- `0x18000558c`
- `0x18000595c`
- `0x180005e08`
- `0x180007a28`
- `0x180009a0c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000b494  mov     ecx, 7
0x18000b499  int     29h; Win8: RtlFailFast(ecx)
```
