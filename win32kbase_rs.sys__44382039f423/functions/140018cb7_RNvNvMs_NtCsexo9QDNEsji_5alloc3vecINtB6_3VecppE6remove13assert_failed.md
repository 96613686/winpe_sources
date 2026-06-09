# _RNvNvMs_NtCsexo9QDNEsji_5alloc3vecINtB6_3VecppE6remove13assert_failed

- ea: `0x140018cb7`
- end: `0x140018cf3`
- name: `_RNvNvMs_NtCsexo9QDNEsji_5alloc3vecINtB6_3VecppE6remove13assert_failed`
- size: `60`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400101f0`

## callees

- `0x140018650`

## pseudocode

```c
void __fastcall __noreturn RNvNvMs_NtCsexo9QDNEsji_5alloc3vecINtB6_3VecppE6remove13assert_failed(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // [rsp+28h] [rbp-30h] BYREF
  __int64 v4; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v5[4]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a1;
  v4 = a2;
  v5[0] = &v3;
  v5[1] = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
  v5[2] = &v4;
  v5[3] = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
  RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(byte_14001D045, v5, a3);
}

```

## disassembly

```asm
0x140018cb7  sub     rsp, 58h
0x140018cbb  lea     rax, [rsp+58h+var_30]
0x140018cc0  mov     [rax], rcx
0x140018cc3  lea     rcx, [rsp+58h+var_28]
0x140018cc8  mov     [rcx], rdx
0x140018ccb  lea     rdx, [rsp+58h+var_20]
0x140018cd0  mov     [rdx], rax
0x140018cd3  lea     rax, _RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt
0x140018cda  mov     [rdx+8], rax
0x140018cde  mov     [rdx+10h], rcx
0x140018ce2  mov     [rdx+18h], rax
0x140018ce6  lea     rcx, byte_14001D045
0x140018ced  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
```
