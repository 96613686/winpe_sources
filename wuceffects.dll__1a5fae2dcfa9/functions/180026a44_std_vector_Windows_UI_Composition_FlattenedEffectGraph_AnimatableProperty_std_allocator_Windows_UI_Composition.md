# std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>>::_Emplace_reallocate<>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const)

- ea: `0x180026a44`
- end: `0x180026b70`
- name: `??$_Emplace_reallocate@$$V@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU23456@@Z`
- size: `300`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009730`

## callees

- `0x18000ad40`
- `0x18000afe0`
- `0x18000dbc0`
- `0x18000dc08`
- `0x18000dc70`
- `0x18001f0e8`
- `0x180026a44`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180026a8b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180026a8b`

## pseudocode

```c
__int64 __fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Emplace_reallocate<>(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rbp
  unsigned __int64 v5; // rax
  __int64 v6; // r12
  __int64 v7; // r15
  SIZE_T size_of; // rax
  __int64 v9; // rdi
  _QWORD *v10; // r8
  _QWORD *v11; // r14
  __int64 v12; // rdx
  __int64 v13; // rcx
  _QWORD v15[3]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v16; // [rsp+38h] [rbp-50h]
  _QWORD *v17; // [rsp+40h] [rbp-48h]

  v2 = *a1;
  v5 = 0xAAAAAAAAAAAAAAABuLL * ((a1[1] - *a1) >> 3);
  if ( v5 == 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("vector too long");
  v6 = v5 + 1;
  v7 = std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Calculate_growth(a1, v5 + 1);
  size_of = std::_Get_size_of_n<24>(v7);
  v9 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15[0] = a1;
  v15[2] = v7;
  v10 = (_QWORD *)v9;
  v11 = (_QWORD *)(v9 + 24 * ((a2 - v2) / 24));
  v17 = v11 + 3;
  v11[1] = 0;
  v11[2] = 0;
  *v11 = 0;
  v12 = a1[1];
  v13 = *a1;
  v16 = v11;
  if ( a2 != v12 )
  {
    std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *>(v13, a2, v9);
    v12 = a1[1];
    v10 = v11 + 3;
    v13 = a2;
    v16 = (_QWORD *)v9;
  }
  std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *>(v13, v12, v10);
  v15[1] = 0;
  std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Change_array(
    (__int64)a1,
    v9,
    v6,
    v7);
  std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Reallocation_guard::~_Reallocation_guard(v15);
  return v9 + 24 * ((a2 - v2) / 24);
}

```

## disassembly

```asm
0x180026a44  push    rbx
0x180026a46  push    rbp
0x180026a47  push    rsi
0x180026a48  push    rdi
0x180026a49  push    r12
0x180026a4b  push    r14
0x180026a4d  push    r15
0x180026a4f  sub     rsp, 50h
0x180026a53  mov     rbp, [rcx]
0x180026a56  mov     rbx, rcx
0x180026a59  mov     rax, [rcx+8]
0x180026a5d  mov     rsi, rdx
0x180026a60  sub     rax, rbp
0x180026a63  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180026a6d  sar     rax, 3
0x180026a71  imul    rax, rcx
0x180026a75  mov     rcx, 0AAAAAAAAAAAAAAAh
0x180026a7f  cmp     rax, rcx
0x180026a82  jnz     short loc_180026A92
0x180026a84  lea     rcx, aVectorTooLong; "vector too long"
0x180026a8b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180026a92  lea     r12, [rax+1]
0x180026a96  mov     rcx, rbx
0x180026a99  mov     rdx, r12
0x180026a9c  call    ?_Calculate_growth@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEBA_K_K@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Calculate_growth(unsigned __int64)
0x180026aa1  mov     rcx, rax
0x180026aa4  mov     r15, rax
0x180026aa7  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x180026aac  mov     rcx, rax; dwBytes
0x180026aaf  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180026ab4  mov     rdi, rax
0x180026ab7  mov     [rsp+88h+var_68], rbx
0x180026abc  mov     [rsp+88h+var_58], r15
0x180026ac1  mov     rcx, rsi
0x180026ac4  sub     rcx, rbp
0x180026ac7  mov     rax, 2AAAAAAAAAAAAAABh
0x180026ad1  imul    rcx
0x180026ad4  mov     r8, rdi
0x180026ad7  sar     rdx, 2
0x180026adb  mov     rcx, rdx
0x180026ade  shr     rcx, 3Fh
0x180026ae2  add     rdx, rcx
0x180026ae5  lea     rcx, [rdx+rdx*2]
0x180026ae9  lea     r14, [rdi+rcx*8]
0x180026aed  lea     rbp, [r14+18h]
0x180026af1  mov     [rsp+88h+var_48], rbp
0x180026af6  mov     qword ptr [r14+8], 0
0x180026afe  mov     qword ptr [r14+10h], 0
0x180026b06  mov     qword ptr [r14], 0
0x180026b0d  mov     rdx, [rbx+8]
0x180026b11  mov     rcx, [rbx]
0x180026b14  mov     [rsp+88h+var_50], r14
0x180026b19  cmp     rsi, rdx
0x180026b1c  jz      short loc_180026B35
0x180026b1e  mov     rdx, rsi
0x180026b21  call    ??$_Uninitialized_move@PEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty> &)
0x180026b26  mov     rdx, [rbx+8]
0x180026b2a  mov     r8, rbp
0x180026b2d  mov     rcx, rsi
0x180026b30  mov     [rsp+88h+var_50], rdi
0x180026b35  call    ??$_Uninitialized_move@PEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty> &)
0x180026b3a  mov     r9, r15
0x180026b3d  mov     [rsp+88h+var_60], 0
0x180026b46  mov     r8, r12
0x180026b49  mov     rdx, rdi
0x180026b4c  mov     rcx, rbx
0x180026b4f  call    ?_Change_array@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAXQEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@_K1@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Change_array(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,unsigned __int64,unsigned __int64)
0x180026b54  lea     rcx, [rsp+88h+var_68]
0x180026b59  call    ??1_Reallocation_guard@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Reallocation_guard::~_Reallocation_guard(void)
0x180026b5e  mov     rax, r14
0x180026b61  add     rsp, 50h
0x180026b65  pop     r15
0x180026b67  pop     r14
0x180026b69  pop     r12
0x180026b6b  pop     rdi
0x180026b6c  pop     rsi
0x180026b6d  pop     rbp
0x180026b6e  pop     rbx
0x180026b6f  retn
```
