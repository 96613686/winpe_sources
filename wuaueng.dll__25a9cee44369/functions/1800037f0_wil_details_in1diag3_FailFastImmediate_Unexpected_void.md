# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800037f0`
- end: `0x1800037f7`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003280`
- `0x180004b60`
- `0x18000521c`
- `0x180009af8`
- `0x18000a00c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800037f0  mov     ecx, 7
0x1800037f5  int     29h; Win8: RtlFailFast(ecx)
```
