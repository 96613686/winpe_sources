# core::alloc::layout::impl$6::fmt_0

- ea: `0x1400146f0`
- end: `0x140014797`
- name: `core::alloc::layout::impl$6::fmt_0`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140006050`
- `0x1400146f0`
- `0x140017a10`

## string_xrefs

- `0x140014754`: `LayoutsizealignCapacityOverflowAllocErrorlayoutnon_exhaustive()d:\os\out\rust\cargo_home\amd64fre\registry\src\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\fallible_vec-0.1.0\src\lib.rs`

## pseudocode

```c
__int64 __fastcall core::alloc::layout::impl_6::fmt_0(__int64 a1, int a2)
{
  __int64 result; // rax
  __int64 v3; // [rsp+0h] [rbp-68h] BYREF
  _QWORD v4[2]; // [rsp+58h] [rbp-10h] BYREF

  v4[0] = a1;
  result = RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter26debug_struct_field2_finish(
             a2,
             (unsigned int)"LayoutsizealignCapacityOverflowAllocErrorlayoutnon_exhaustive()d:\\os\\out\\rust\\cargo_home\\"
                           "amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\fallible_vec-0.1.0\\src\\lib.rs",
             6,
             (unsigned int)"sizealignCapacityOverflowAllocErrorlayoutnon_exhaustive()d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\fallible_vec-0.1.0\\src\\lib.rs",
             4,
             a1 + 8,
             (__int64)&qword_14001C410,
             (__int64)"alignCapacityOverflowAllocErrorlayoutnon_exhaustive()d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\fallible_vec-0.1.0\\src\\lib.rs",
             5,
             (__int64)v4,
             (__int64)&qword_14001C430);
  if ( _security_cookie != ((unsigned __int64)&v3 ^ v4[1]) )
    JUMPOUT(0x140014796LL);
  return result;
}

```

## disassembly

```asm
0x1400146f0  sub     rsp, 68h
0x1400146f4  mov     rax, rdx
0x1400146f7  mov     rdx, cs:__security_cookie
0x1400146fe  xor     rdx, rsp
0x140014701  mov     [rsp+68h+var_8], rdx
0x140014706  mov     [rsp+68h+var_10], rcx
0x14001470b  add     rcx, 8
0x14001470f  lea     rdx, qword_14001C430
0x140014716  mov     [rsp+68h+var_18], rdx
0x14001471b  lea     rdx, [rsp+68h+var_10]
0x140014720  mov     [rsp+68h+var_20], rdx
0x140014725  lea     rdx, aLayoutsizealig+0Ah; "alignCapacityOverflowAllocErrorlayoutno"...
0x14001472c  mov     [rsp+68h+var_30], rdx
0x140014731  lea     rdx, qword_14001C410
0x140014738  mov     [rsp+68h+var_38], rdx
0x14001473d  mov     [rsp+68h+var_40], rcx
0x140014742  mov     [rsp+68h+var_28], 5
0x14001474b  mov     [rsp+68h+var_48], 4
0x140014754  lea     rdx, aLayoutsizealig; "LayoutsizealignCapacityOverflowAllocErr"...
0x14001475b  lea     r9, aLayoutsizealig+6; "sizealignCapacityOverflowAllocErrorlayo"...
0x140014762  mov     r8d, 6
0x140014768  mov     rcx, rax
0x14001476b  call    _RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter26debug_struct_field2_finish
0x140014770  mov     rcx, [rsp+68h+var_8]
0x140014775  xor     rcx, rsp
0x140014778  mov     rdx, cs:__security_cookie
0x14001477f  cmp     rdx, rcx
0x140014782  jnz     short loc_140014789
0x140014784  add     rsp, 68h
0x140014788  retn
0x140014789  mov     rcx, [rsp+68h+var_8]
0x14001478e  xor     rcx, rsp; StackCookie
0x140014791  call    __security_check_cookie
```
