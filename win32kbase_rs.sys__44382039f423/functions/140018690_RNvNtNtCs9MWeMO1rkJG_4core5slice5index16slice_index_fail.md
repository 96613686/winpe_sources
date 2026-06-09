# _RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail

- ea: `0x140018690`
- end: `0x14001876d`
- name: `_RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail`
- size: `221`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a990`
- `0x14000b0e0`
- `0x14000be40`
- `0x14000c440`
- `0x14000cc10`
- `0x14000e9d0`
- `0x14000f800`
- `0x1400101f0`
- `0x140012320`
- `0x140012420`
- `0x140012690`
- `0x140012770`
- `0x140013320`
- `0x140014dd0`
- `0x1400153c0`
- `0x140015ac0`

## callees

- `0x140018650`
- `0x140018690`

## pseudocode

```c
void __fastcall __noreturn RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        __int64 a4)
{
  unsigned __int64 v4; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int64 v5; // [rsp+30h] [rbp-28h] BYREF
  __int64 *v6; // [rsp+38h] [rbp-20h] BYREF
  __int64 (__fastcall *v7)(); // [rsp+40h] [rbp-18h]
  __int64 *v8; // [rsp+48h] [rbp-10h]
  __int64 (__fastcall *v9)(); // [rsp+50h] [rbp-8h]

  if ( a1 > a3 )
  {
    v4 = a1;
    v5 = a3;
    v6 = (__int64 *)&v4;
    v7 = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
    v8 = (__int64 *)&v5;
    v9 = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
    RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(&dword_14001CA74, &v6, a4);
  }
  if ( a2 <= a3 && a1 > a2 )
  {
    v4 = a1;
    v5 = a2;
    v6 = (__int64 *)&v4;
    v7 = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
    v8 = (__int64 *)&v5;
    v9 = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
    RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(&dword_14001CAE4, &v6, a4);
  }
  v4 = a2;
  v5 = a3;
  v6 = (__int64 *)&v4;
  v7 = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
  v8 = (__int64 *)&v5;
  v9 = RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt;
  RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(byte_14001CAAD, &v6, a4);
}

```

## disassembly

```asm
0x140018690  sub     rsp, 58h
0x140018694  cmp     rcx, r8
0x140018697  jbe     short loc_1400186DC
0x140018699  mov     [rsp+58h+var_30], rcx
0x14001869e  mov     [rsp+58h+var_28], r8
0x1400186a3  lea     rax, [rsp+58h+var_30]
0x1400186a8  mov     [rsp+58h+var_20], rax
0x1400186ad  lea     rax, _RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt
0x1400186b4  mov     [rsp+58h+var_18], rax
0x1400186b9  lea     rcx, [rsp+58h+var_28]
0x1400186be  mov     [rsp+58h+var_10], rcx
0x1400186c3  mov     [rsp+58h+var_8], rax
0x1400186c8  lea     rcx, dword_14001CA74
0x1400186cf  lea     rdx, [rsp+58h+var_20]
0x1400186d4  mov     r8, r9
0x1400186d7  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x1400186dc  cmp     rdx, r8
0x1400186df  ja      short loc_140018729
0x1400186e1  cmp     rcx, rdx
0x1400186e4  jbe     short loc_140018729
0x1400186e6  mov     [rsp+58h+var_30], rcx
0x1400186eb  mov     [rsp+58h+var_28], rdx
0x1400186f0  lea     rax, [rsp+58h+var_30]
0x1400186f5  mov     [rsp+58h+var_20], rax
0x1400186fa  lea     rax, _RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt
0x140018701  mov     [rsp+58h+var_18], rax
0x140018706  lea     rcx, [rsp+58h+var_28]
0x14001870b  mov     [rsp+58h+var_10], rcx
0x140018710  mov     [rsp+58h+var_8], rax
0x140018715  lea     rcx, dword_14001CAE4
0x14001871c  lea     rdx, [rsp+58h+var_20]
0x140018721  mov     r8, r9
0x140018724  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x140018729  mov     [rsp+58h+var_30], rdx
0x14001872e  mov     [rsp+58h+var_28], r8
0x140018733  lea     rax, [rsp+58h+var_30]
0x140018738  mov     [rsp+58h+var_20], rax
0x14001873d  lea     rax, _RNvXsd_NtNtNtCs9MWeMO1rkJG_4core3fmt3num3impyNtB9_7Display3fmt
0x140018744  mov     [rsp+58h+var_18], rax
0x140018749  lea     rcx, [rsp+58h+var_28]
0x14001874e  mov     [rsp+58h+var_10], rcx
0x140018753  mov     [rsp+58h+var_8], rax
0x140018758  lea     rcx, byte_14001CAAD
0x14001875f  lea     rdx, [rsp+58h+var_20]
0x140018764  mov     r8, r9
0x140018767  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
```
