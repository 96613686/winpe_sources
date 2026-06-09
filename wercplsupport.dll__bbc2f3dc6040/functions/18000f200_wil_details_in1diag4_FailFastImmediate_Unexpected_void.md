# wil::details::in1diag4::_FailFastImmediate_Unexpected(void)

- ea: `0x18000f200`
- end: `0x18000f207`
- name: `?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag4 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180008b5c`
- `0x180009b78`
- `0x180009f58`
- `0x18000a410`
- `0x18000bdfc`
- `0x18000d28c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag4::_FailFastImmediate_Unexpected(wil::details::in1diag4 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000f200  mov     ecx, 7
0x18000f205  int     29h; Win8: RtlFailFast(ecx)
```
