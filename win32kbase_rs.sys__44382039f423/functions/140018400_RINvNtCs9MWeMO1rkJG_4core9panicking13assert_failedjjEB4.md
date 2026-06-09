# _RINvNtCs9MWeMO1rkJG_4core9panicking13assert_failedjjEB4_

- ea: `0x140018400`
- end: `0x14001843e`
- name: `_RINvNtCs9MWeMO1rkJG_4core9panicking13assert_failedjjEB4_`
- size: `62`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140002000`
- `0x140002150`
- `0x1400022a0`
- `0x1400023c0`
- `0x140002500`
- `0x140002610`
- `0x140003210`
- `0x140008030`
- `0x14000f5b0`
- `0x1400120f0`

## callees

- `0x140018519`

## pseudocode

```c
void __fastcall __noreturn RINvNtCs9MWeMO1rkJG_4core9panicking13assert_failedjjEB4_(
        __int128 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // [rsp+48h] [rbp-10h] BYREF
  __int64 v7; // [rsp+50h] [rbp-8h] BYREF

  v6 = a2;
  v7 = a3;
  RNvNtCs9MWeMO1rkJG_4core9panicking19assert_failed_inner(
    (_DWORD)a1,
    (unsigned int)&v6,
    (unsigned int)&qword_14001B168,
    (unsigned int)&v7,
    (__int64)&qword_14001B168,
    a4,
    a5,
    a6);
}

```

## disassembly

```asm
0x140018400  sub     rsp, 58h
0x140018404  movaps  xmm0, [rsp+58h+arg_20]
0x14001840c  lea     rax, [rsp+58h+var_10]
0x140018411  mov     [rax], rdx
0x140018414  lea     r10, [rsp+58h+var_8]
0x140018419  mov     [r10], r8
0x14001841c  movups  [rsp+58h+var_28], xmm0
0x140018421  mov     [rsp+58h+var_30], r9
0x140018426  lea     r8, qword_14001B168
0x14001842d  mov     [rsp+58h+var_38], r8
0x140018432  mov     rdx, rax
0x140018435  mov     r9, r10
0x140018438  call    _RNvNtCs9MWeMO1rkJG_4core9panicking19assert_failed_inner
```
