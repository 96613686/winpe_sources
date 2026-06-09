# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000c558`
- end: `0x18000c55f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180003394`
- `0x180003648`
- `0x180004b78`
- `0x180004f48`
- `0x1800057f0`
- `0x18000776c`
- `0x180008e2c`
- `0x18000f574`
- `0x18000f648`
- `0x18000f708`
- `0x180016768`
- `0x180016c40`
- `0x180016d60`
- `0x1800189d8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000c558  mov     ecx, 7
0x18000c55d  int     29h; Win8: RtlFailFast(ecx)
```
