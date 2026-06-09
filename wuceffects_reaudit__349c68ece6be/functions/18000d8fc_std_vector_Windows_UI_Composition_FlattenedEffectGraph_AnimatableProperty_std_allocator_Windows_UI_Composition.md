# std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>>::_Emplace_reallocate<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty &&)

- ea: `0x18000d8fc`
- end: `0x18000da16`
- name: `??$_Emplace_reallocate@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU23456@$$QEAU23456@@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c9b8`

## callees

- `0x18000ad40`
- `0x18000afe0`
- `0x18000d8fc`
- `0x18000dbc0`
- `0x18000dc08`
- `0x18000dc70`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d948`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d948`

## pseudocode

```c
__int64 __fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Emplace_reallocate<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbp
  unsigned __int64 v7; // rax
  __int64 v8; // r12
  __int64 v9; // r13
  SIZE_T size_of; // rax
  __int64 v11; // rdi
  __int64 v12; // r8
  __int64 v13; // r14
  __int64 v14; // rdx
  __int64 v15; // rcx

  v3 = *a1;
  v7 = 0xAAAAAAAAAAAAAAABuLL * ((a1[1] - *a1) >> 3);
  if ( v7 == 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("vector too long");
  v8 = v7 + 1;
  v9 = std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Calculate_growth(a1, v7 + 1);
  size_of = std::_Get_size_of_n<24>(v9);
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = v11;
  v13 = v11 + 24 * ((a2 - v3) / 24);
  *(_QWORD *)v13 = *(_QWORD *)a3;
  *(_QWORD *)a3 = 0;
  *(_DWORD *)(v13 + 8) = *(_DWORD *)(a3 + 8);
  *(_DWORD *)(v13 + 12) = *(_DWORD *)(a3 + 12);
  *(_DWORD *)(v13 + 16) = *(_DWORD *)(a3 + 16);
  *(_DWORD *)(v13 + 20) = *(_DWORD *)(a3 + 20);
  v14 = a1[1];
  v15 = *a1;
  if ( a2 != v14 )
  {
    std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *>(v15, a2, v11);
    v14 = a1[1];
    v12 = v13 + 24;
    v15 = a2;
  }
  std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *>(v15, v14, v12);
  std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Change_array(
    (__int64)a1,
    v11,
    v8,
    v9);
  return v11 + 24 * ((a2 - v3) / 24);
}

```

## disassembly

```asm
0x18000d8fc  push    rbx
0x18000d8fe  push    rbp
0x18000d8ff  push    rsi
0x18000d900  push    rdi
0x18000d901  push    r12
0x18000d903  push    r13
0x18000d905  push    r14
0x18000d907  push    r15
0x18000d909  sub     rsp, 28h
0x18000d90d  mov     rbp, [rcx]
0x18000d910  mov     rbx, rcx
0x18000d913  mov     rax, [rcx+8]
0x18000d917  mov     r15, r8
0x18000d91a  sub     rax, rbp
0x18000d91d  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18000d927  sar     rax, 3
0x18000d92b  mov     rsi, rdx
0x18000d92e  imul    rax, rcx
0x18000d932  mov     rcx, 0AAAAAAAAAAAAAAAh
0x18000d93c  cmp     rax, rcx
0x18000d93f  jnz     short loc_18000D94F
0x18000d941  lea     rcx, aVectorTooLong; "vector too long"
0x18000d948  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000d94f  lea     r12, [rax+1]
0x18000d953  mov     rcx, rbx
0x18000d956  mov     rdx, r12
0x18000d959  call    ?_Calculate_growth@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEBA_K_K@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Calculate_growth(unsigned __int64)
0x18000d95e  mov     rcx, rax
0x18000d961  mov     r13, rax
0x18000d964  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x18000d969  mov     rcx, rax; dwBytes
0x18000d96c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d971  mov     rdi, rax
0x18000d974  mov     rcx, rsi
0x18000d977  sub     rcx, rbp
0x18000d97a  mov     rax, 2AAAAAAAAAAAAAABh
0x18000d984  imul    rcx
0x18000d987  mov     rax, [r15]
0x18000d98a  mov     r8, rdi
0x18000d98d  sar     rdx, 2
0x18000d991  mov     rcx, rdx
0x18000d994  shr     rcx, 3Fh
0x18000d998  add     rdx, rcx
0x18000d99b  lea     rcx, [rdx+rdx*2]
0x18000d99f  lea     r14, [rdi+rcx*8]
0x18000d9a3  mov     [r14], rax
0x18000d9a6  mov     qword ptr [r15], 0
0x18000d9ad  mov     eax, [r15+8]
0x18000d9b1  mov     [r14+8], eax
0x18000d9b5  mov     eax, [r15+0Ch]
0x18000d9b9  mov     [r14+0Ch], eax
0x18000d9bd  mov     eax, [r15+10h]
0x18000d9c1  mov     [r14+10h], eax
0x18000d9c5  mov     eax, [r15+14h]
0x18000d9c9  mov     [r14+14h], eax
0x18000d9cd  mov     rdx, [rbx+8]
0x18000d9d1  mov     rcx, [rbx]
0x18000d9d4  cmp     rsi, rdx
0x18000d9d7  jz      short loc_18000D9EC
0x18000d9d9  mov     rdx, rsi
0x18000d9dc  call    ??$_Uninitialized_move@PEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty> &)
0x18000d9e1  mov     rdx, [rbx+8]
0x18000d9e5  lea     r8, [r14+18h]
0x18000d9e9  mov     rcx, rsi
0x18000d9ec  call    ??$_Uninitialized_move@PEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty> &)
0x18000d9f1  mov     r9, r13
0x18000d9f4  mov     r8, r12
0x18000d9f7  mov     rdx, rdi
0x18000d9fa  mov     rcx, rbx
0x18000d9fd  call    ?_Change_array@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAXQEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@_K1@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Change_array(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,unsigned __int64,unsigned __int64)
0x18000da02  mov     rax, r14
0x18000da05  add     rsp, 28h
0x18000da09  pop     r15
0x18000da0b  pop     r14
0x18000da0d  pop     r13
0x18000da0f  pop     r12
0x18000da11  pop     rdi
0x18000da12  pop     rsi
0x18000da13  pop     rbp
0x18000da14  pop     rbx
0x18000da15  retn
```
