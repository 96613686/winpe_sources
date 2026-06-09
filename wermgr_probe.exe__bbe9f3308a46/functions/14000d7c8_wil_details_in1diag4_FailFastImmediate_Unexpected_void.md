# wil::details::in1diag4::_FailFastImmediate_Unexpected(void)

- ea: `0x14000d7c8`
- end: `0x14000d7cf`
- name: `?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag4 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140003df4`
- `0x140004090`
- `0x140010778`
- `0x140010b80`
- `0x140010fac`
- `0x140012d44`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag4::_FailFastImmediate_Unexpected(wil::details::in1diag4 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000d7c8  mov     ecx, 7
0x14000d7cd  int     29h; Win8: RtlFailFast(ecx)
```
