# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180010a38`
- end: `0x180010a3f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180009680`
- `0x18000aa10`
- `0x18000c7f4`
- `0x18000dcdc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180010a38  mov     ecx, 7
0x180010a3d  int     29h; Win8: RtlFailFast(ecx)
```
