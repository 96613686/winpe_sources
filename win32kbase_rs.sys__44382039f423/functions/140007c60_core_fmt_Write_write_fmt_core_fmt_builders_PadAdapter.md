# core::fmt::Write::write_fmt_core::fmt::builders::PadAdapter_

- ea: `0x140007c60`
- end: `0x140007c86`
- name: `core::fmt::Write::write_fmt_core::fmt::builders::PadAdapter_`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140006620`
- `0x140006f30`
- `0x140007c60`

## pseudocode

```c
char __fastcall core::fmt::Write::write_fmt_core::fmt::builders::PadAdapter_(
        __int64 *a1,
        unsigned __int8 *a2,
        unsigned __int64 a3)
{
  if ( (a3 & 1) != 0 )
    return RNvXs0_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_10PadAdapterNtB7_5Write9write_str(a1, (__int64)a2, a3 >> 1);
  else
    return RNvNtCs9MWeMO1rkJG_4core3fmt5write((__int64)a1, (__int64)&qword_14001B188, a2, a3);
}

```

## disassembly

```asm
0x140007c60  mov     r9, r8
0x140007c63  mov     r8, rdx
0x140007c66  test    r9b, 1
0x140007c6a  jnz     short loc_140007C78
0x140007c6c  lea     rdx, qword_14001B188
0x140007c73  jmp     _RNvNtCs9MWeMO1rkJG_4core3fmt5write
0x140007c78  shr     r9, 1
0x140007c7b  mov     rdx, r8
0x140007c7e  mov     r8, r9
0x140007c81  jmp     _RNvXs0_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_10PadAdapterNtB7_5Write9write_str
```
