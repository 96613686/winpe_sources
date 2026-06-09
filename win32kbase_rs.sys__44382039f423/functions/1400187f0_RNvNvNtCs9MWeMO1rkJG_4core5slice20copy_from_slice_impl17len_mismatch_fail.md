# _RNvNvNtCs9MWeMO1rkJG_4core5slice20copy_from_slice_impl17len_mismatch_fail

- ea: `0x1400187f0`
- end: `0x140018835`
- name: `_RNvNvNtCs9MWeMO1rkJG_4core5slice20copy_from_slice_impl17len_mismatch_fail`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005340`
- `0x1400132c0`

## callees

- `0x140018650`

## pseudocode

```c
void __fastcall __noreturn RNvNvNtCs9MWeMO1rkJG_4core5slice20copy_from_slice_impl17len_mismatch_fail(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // [rsp+28h] [rbp-30h] BYREF
  __int64 v4; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v5[4]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a2;
  v4 = a1;
  v5[0] = &v3;
  v5[1] = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
  v5[2] = &v4;
  v5[3] = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
  RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(byte_14001CBDB, v5, a3);
}

```

## disassembly

```asm
0x1400187f0  sub     rsp, 58h
0x1400187f4  mov     [rsp+58h+var_30], rdx
0x1400187f9  mov     [rsp+58h+var_28], rcx
0x1400187fe  lea     rax, [rsp+58h+var_30]
0x140018803  mov     [rsp+58h+var_20], rax
0x140018808  lea     rax, _RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt
0x14001880f  mov     [rsp+58h+var_18], rax
0x140018814  lea     rcx, [rsp+58h+var_28]
0x140018819  mov     [rsp+58h+var_10], rcx
0x14001881e  mov     [rsp+58h+var_8], rax
0x140018823  lea     rcx, byte_14001CBDB
0x14001882a  lea     rdx, [rsp+58h+var_20]
0x14001882f  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
```
