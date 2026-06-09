# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800108b4`
- end: `0x1800108bb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a704`
- `0x18000a858`
- `0x18000cdd4`
- `0x18000da54`
- `0x18000e9b8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800108b4  mov     ecx, 7
0x1800108b9  int     29h; Win8: RtlFailFast(ecx)
```
