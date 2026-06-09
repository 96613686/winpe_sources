# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000a00c`
- end: `0x14000a013`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140004958`
- `0x1400054ac`
- `0x140005850`
- `0x140005dd0`
- `0x140007190`
- `0x140008338`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000a00c  mov     ecx, 7
0x14000a011  int     29h; Win8: RtlFailFast(ecx)
```
