# _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed

- ea: `0x140018450`
- end: `0x140018469`
- name: `_RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed`
- size: `25`
- prototype: `void __fastcall __noreturn(_QWORD)`
- caller_count: `69`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010d0`
- `0x140001110`
- `0x140001160`
- `0x1400011f0`
- `0x140001260`
- `0x1400012a0`
- `0x1400012e0`
- `0x140001390`
- `0x1400013c0`
- `0x1400013f0`
- `0x140001420`
- `0x140001490`
- `0x140001500`
- `0x1400016b0`
- `0x1400016f0`
- `0x140001730`
- `0x140001810`
- `0x140001980`
- `0x1400019e0`
- `0x140001ae0`
- `0x140001b20`
- `0x140001b60`
- `0x140001c40`
- `0x140001cf0`
- `0x140001f50`
- `0x140002000`
- `0x140002150`
- `0x1400022a0`
- `0x1400023c0`
- `0x140002500`
- `0x140002610`
- `0x1400029e0`
- `0x140002b00`
- `0x140002c60`
- `0x140002ea0`
- `0x140003210`
- `0x140003410`
- `0x140004890`
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
- `0x14000abf0`

## callees

- `0x140018630`

## pseudocode

```c
void __fastcall __noreturn RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(__int64 a1)
{
  RNvNtCs9MWeMO1rkJG_4core9panicking5panic(qword_14001C8A8, 43, a1);
}

```

## disassembly

```asm
0x140018450  sub     rsp, 28h
0x140018454  mov     r8, rcx
0x140018457  lea     rcx, qword_14001C8A8
0x14001845e  mov     edx, 2Bh ; '+'
0x140018463  call    _RNvNtCs9MWeMO1rkJG_4core9panicking5panic
```
