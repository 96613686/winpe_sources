# std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>>::_Change_array(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,unsigned __int64,unsigned __int64)

- ea: `0x18000dc70`
- end: `0x18000dd3a`
- name: `?_Change_array@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAXQEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@_K1@Z`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d8fc`
- `0x180026a44`

## callees

- `0x18000dc70`
- `0x180021084`
- `0x1800257b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dca7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dca7`

## pseudocode

```c
__int64 __fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  HSTRING *v4; // rbx
  HSTRING *i; // rdi
  void *v10; // rcx
  unsigned __int64 v11; // rax
  __int64 v12; // rdx
  __int64 result; // rax
  unsigned __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  void *v15; // [rsp+58h] [rbp+10h] BYREF

  v4 = *(HSTRING **)a1;
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(HSTRING **)(a1 + 8); v4 != i; v4 += 3 )
    {
      if ( *v4 )
        WindowsDeleteString(*v4);
    }
    v10 = *(void **)a1;
    v11 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3);
    v15 = *(void **)a1;
    v12 = 24 * v11;
    v14 = 24 * v11;
    if ( 24 * v11 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v15, &v14);
      v12 = v14;
      v10 = v15;
    }
    operator delete(v10, v12);
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 24 * a3;
  result = 3 * a4;
  *(_QWORD *)(a1 + 16) = a2 + 24 * a4;
  return result;
}

```

## disassembly

```asm
0x18000dc70  push    rbx
0x18000dc72  push    rsi
0x18000dc73  push    r12
0x18000dc75  push    r14
0x18000dc77  push    r15
0x18000dc79  sub     rsp, 20h
0x18000dc7d  mov     rbx, [rcx]
0x18000dc80  mov     r15, r9
0x18000dc83  mov     r12, r8
0x18000dc86  mov     r14, rdx
0x18000dc89  mov     rsi, rcx
0x18000dc8c  test    rbx, rbx
0x18000dc8f  jz      short loc_18000DCF7
0x18000dc91  mov     [rsp+48h+arg_10], rdi
0x18000dc96  mov     rdi, [rcx+8]
0x18000dc9a  cmp     rbx, rdi
0x18000dc9d  jz      short loc_18000DCB6
0x18000dc9f  mov     rcx, [rbx]; string
0x18000dca2  test    rcx, rcx
0x18000dca5  jz      short loc_18000DCAD
0x18000dca7  call    cs:__imp_WindowsDeleteString
0x18000dcad  add     rbx, 18h
0x18000dcb1  cmp     rbx, rdi
0x18000dcb4  jnz     short loc_18000DC9F
0x18000dcb6  mov     rcx, [rsi]; void *
0x18000dcb9  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000dcc3  mov     rax, [rsi+10h]
0x18000dcc7  mov     rdi, [rsp+48h+arg_10]
0x18000dccc  sub     rax, rcx
0x18000dccf  sar     rax, 3
0x18000dcd3  imul    rax, rdx
0x18000dcd7  mov     [rsp+48h+arg_8], rcx
0x18000dcdc  lea     rdx, [rax+rax*2]
0x18000dce0  shl     rdx, 3; unsigned __int64
0x18000dce4  mov     [rsp+48h+arg_0], rdx
0x18000dce9  cmp     rdx, 1000h
0x18000dcf0  jnb     short loc_18000DD1F
0x18000dcf2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dcf7  lea     rax, [r12+r12*2]
0x18000dcfb  mov     [rsi], r14
0x18000dcfe  lea     rcx, [r14+rax*8]
0x18000dd02  mov     [rsi+8], rcx
0x18000dd06  lea     rax, [r15+r15*2]
0x18000dd0a  lea     rcx, [r14+rax*8]
0x18000dd0e  mov     [rsi+10h], rcx
0x18000dd12  add     rsp, 20h
0x18000dd16  pop     r15
0x18000dd18  pop     r14
0x18000dd1a  pop     r12
0x18000dd1c  pop     rsi
0x18000dd1d  pop     rbx
0x18000dd1e  retn
0x18000dd1f  lea     rdx, [rsp+48h+arg_0]; unsigned __int64 *
0x18000dd24  lea     rcx, [rsp+48h+arg_8]; void **
0x18000dd29  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000dd2e  mov     rdx, [rsp+48h+arg_0]
0x18000dd33  mov     rcx, [rsp+48h+arg_8]
0x18000dd38  jmp     short loc_18000DCF2
```
