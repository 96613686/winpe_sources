# _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check

- ea: `0x1400184d7`
- end: `0x140018513`
- name: `_RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check`
- size: `60`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD, _QWORD)`
- caller_count: `51`
- callee_count: `1`
- tags: ``

## callers

- `0x140003860`
- `0x140004820`
- `0x140004af0`
- `0x140009150`
- `0x140009270`
- `0x140009390`
- `0x140009530`
- `0x1400096c0`
- `0x1400099d0`
- `0x140009b50`
- `0x140009c50`
- `0x140009e00`
- `0x14000a0d0`
- `0x14000a250`
- `0x14000a990`
- `0x14000ab50`
- `0x14000b0e0`
- `0x14000b240`
- `0x14000b860`
- `0x14000be40`
- `0x14000c440`
- `0x14000c640`
- `0x14000cc10`
- `0x14000e720`
- `0x14000e9d0`
- `0x14000f5b0`
- `0x14000f6b0`
- `0x14000f720`
- `0x14000f800`
- `0x14000fab0`
- `0x1400101f0`
- `0x140011120`
- `0x1400120f0`
- `0x1400121f0`
- `0x140012320`
- `0x1400123c0`
- `0x140012420`
- `0x140012690`
- `0x140012770`
- `0x140012a30`
- `0x140013460`
- `0x140013570`
- `0x140013670`
- `0x140013890`
- `0x1400139c0`
- `0x140013a70`
- `0x140013c70`
- `0x1400142f0`
- `0x140014dd0`
- `0x1400153c0`

## callees

- `0x140018650`

## pseudocode

```c
void __fastcall __noreturn RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // [rsp+28h] [rbp-30h] BYREF
  __int64 v4; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v5[4]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a1;
  v4 = a2;
  v5[0] = &v4;
  v5[1] = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
  v5[2] = &v3;
  v5[3] = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
  RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(byte_14001C8D9, v5, a3);
}

```

## disassembly

```asm
0x1400184d7  sub     rsp, 58h
0x1400184db  lea     rax, [rsp+58h+var_30]
0x1400184e0  mov     [rax], rcx
0x1400184e3  lea     rcx, [rsp+58h+var_28]
0x1400184e8  mov     [rcx], rdx
0x1400184eb  lea     rdx, [rsp+58h+var_20]
0x1400184f0  mov     [rdx], rcx
0x1400184f3  lea     rcx, _RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt
0x1400184fa  mov     [rdx+8], rcx
0x1400184fe  mov     [rdx+10h], rax
0x140018502  mov     [rdx+18h], rcx
0x140018506  lea     rcx, byte_14001C8D9
0x14001850d  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
```
