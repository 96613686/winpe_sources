# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000635c`
- end: `0x140006363`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400030bc`
- `0x1400036fc`
- `0x140003ad0`
- `0x140004f10`
- `0x140009214`
- `0x14000b058`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000635c  mov     ecx, 7
0x140006361  int     29h; Win8: RtlFailFast(ecx)
```
