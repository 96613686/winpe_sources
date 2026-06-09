# _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed

- ea: `0x140018470`
- end: `0x1400184d1`
- name: `_RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed`
- size: `97`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x140003860`
- `0x14000abf0`
- `0x14000b240`
- `0x14000b710`
- `0x14000b860`
- `0x14000bc20`
- `0x14000be40`
- `0x14000c2a0`
- `0x14000cc10`
- `0x14000e9d0`
- `0x14000f5b0`
- `0x14000f800`
- `0x1400120f0`
- `0x140012260`
- `0x140012770`
- `0x140013e50`
- `0x140018840`
- `0x140019140`

## callees

- `0x140018650`

## pseudocode

```c
void __fastcall __noreturn RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD v5[2]; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v6[2]; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v7[4]; // [rsp+48h] [rbp-20h] BYREF

  v5[0] = a1;
  v5[1] = a2;
  v6[0] = a3;
  v6[1] = a4;
  v7[0] = v5;
  v7[1] = core::fmt::impl_82::fmt_str__;
  v7[2] = v6;
  v7[3] = core::fmt::impl_80::fmt_dyn__core::fmt::Debug___;
  RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(byte_14001C8D3, v7, a5);
}

```

## disassembly

```asm
0x140018470  sub     rsp, 68h
0x140018474  mov     rax, [rsp+68h+arg_20]
0x14001847c  mov     [rsp+68h+var_40], rcx
0x140018481  mov     [rsp+68h+var_38], rdx
0x140018486  mov     [rsp+68h+var_30], r8
0x14001848b  mov     [rsp+68h+var_28], r9
0x140018490  lea     rcx, [rsp+68h+var_40]
0x140018495  mov     [rsp+68h+var_20], rcx
0x14001849a  lea     rcx, core__fmt__impl$82__fmt_str$_
0x1400184a1  mov     [rsp+68h+var_18], rcx
0x1400184a6  lea     rcx, [rsp+68h+var_30]
0x1400184ab  mov     [rsp+68h+var_10], rcx
0x1400184b0  lea     rcx, core__fmt__impl$80__fmt_dyn$_core__fmt__Debug___
0x1400184b7  mov     [rsp+68h+var_8], rcx
0x1400184bc  lea     rcx, byte_14001C8D3
0x1400184c3  lea     rdx, [rsp+68h+var_20]
0x1400184c8  mov     r8, rax
0x1400184cb  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
```
