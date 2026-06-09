# _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt

- ea: `0x140018650`
- end: `0x14001867f`
- name: `_RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt`
- size: `47`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140007c90`
- `0x14000a400`
- `0x14000c640`
- `0x14000ca10`
- `0x14000e9d0`
- `0x140012420`
- `0x140018470`
- `0x1400184d7`
- `0x140018519`
- `0x140018630`
- `0x140018690`
- `0x140018780`
- `0x1400187a0`
- `0x1400187c0`
- `0x1400187f0`
- `0x140018cb7`

## callees

- `0x140013300`

## pseudocode

```c
void __fastcall __noreturn RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD v3[2]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v4[2]; // [rsp+30h] [rbp-18h] BYREF
  __int16 v5; // [rsp+40h] [rbp-8h]

  v3[0] = a1;
  v3[1] = a2;
  v4[0] = v3;
  v4[1] = a3;
  v5 = 1;
  RNvCskrXTfrW5pjd_7___rustc17rust_begin_unwind(v4);
}

```

## disassembly

```asm
0x140018650  sub     rsp, 48h
0x140018654  mov     [rsp+48h+var_28], rcx
0x140018659  mov     [rsp+48h+var_20], rdx
0x14001865e  lea     rax, [rsp+48h+var_28]
0x140018663  mov     [rsp+48h+var_18], rax
0x140018668  mov     [rsp+48h+var_10], r8
0x14001866d  mov     [rsp+48h+var_8], 1
0x140018674  lea     rcx, [rsp+48h+var_18]
0x140018679  call    _RNvCskrXTfrW5pjd_7___rustc17rust_begin_unwind
```
