# __lambda_3d5f3bee0032f150f7b5c906833347cc_$_ResumeCoro$1::operator()_::_1_::catch$13

- ea: `0x18002fcd9`
- end: `0x18002fd34`
- name: `__lambda_3d5f3bee0032f150f7b5c906833347cc_$_ResumeCoro$1::operator()_::_1_::catch$13`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800167c0`
- `0x18002fcd9`

## string_xrefs

- `0x18002fced`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_3d5f3bee0032f150f7b5c906833347cc___ResumeCoro_1::operator()_::_1_::catch_13(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 232),
    (void *)0x521,
    (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
    a4);
  v5 = *(_QWORD *)(a2 + 32);
  v6 = *(_QWORD *)(v5 + 16);
  *(_QWORD *)(a2 + 80) = v6;
  v7 = *(_QWORD *)(v5 + 24);
  *(_QWORD *)(a2 + 88) = v7;
  if ( v6 != v7 )
  {
    v8 = *(_QWORD *)(v5 + 16);
    *(_QWORD *)(a2 + 80) = v8;
    *(_QWORD *)(v5 + 24) = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x18002fcd9  mov     [rsp+arg_8], rdx
0x18002fcde  push    rbp
0x18002fcdf  sub     rsp, 20h
0x18002fce3  mov     rbp, rdx
0x18002fce6  mov     rcx, [rbp+0E8h]; this
0x18002fced  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18002fcf4  mov     edx, 521h; void *
0x18002fcf9  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18002fcfe  mov     rdx, [rbp+20h]
0x18002fd02  mov     rcx, [rdx+10h]
0x18002fd06  mov     [rbp+50h], rcx
0x18002fd0a  mov     rax, [rdx+18h]
0x18002fd0e  mov     [rbp+58h], rax
0x18002fd12  cmp     rcx, rax
0x18002fd15  jz      short loc_18002FD23
0x18002fd17  mov     rax, [rdx+10h]
0x18002fd1b  mov     [rbp+50h], rax
0x18002fd1f  mov     [rdx+18h], rax
0x18002fd23  mov     rax, 0
0x18002fd2d  add     rsp, 20h
0x18002fd31  pop     rbp
0x18002fd32  retn
```
