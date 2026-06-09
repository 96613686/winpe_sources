# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000bc9c`
- end: `0x18000bca3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180007284`
- `0x180008260`
- `0x180009514`
- `0x180009654`
- `0x180009a80`
- `0x180009ba8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000bc9c  mov     ecx, 7
0x18000bca1  int     29h; Win8: RtlFailFast(ecx)
```
