# std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>>,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>>>>::_Emplace_reallocate<std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>>>(std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>> * const,std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>> &&)

- ea: `0x180017910`
- end: `0x180017a33`
- name: `??$_Emplace_reallocate@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@?$vector@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b520`

## callees

- `0x180009fe0`
- `0x18000a760`
- `0x18000ad10`
- `0x18000ad40`
- `0x180016bf0`
- `0x180017910`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001794e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001794e`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Emplace_reallocate<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v3; // rdi
  __int64 v6; // rax
  __int64 v8; // r12
  __int64 v9; // r13
  SIZE_T size_of; // rax
  __int64 v11; // r14
  _QWORD *v12; // rbp
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 *v15; // r8
  __int64 *v16; // rdx
  _QWORD *v17; // rdi
  __int64 v18; // rax
  _QWORD *v19; // rdx
  __int64 v20; // rax
  __int64 *v21; // rcx
  __int64 v22; // rax

  v3 = *a1;
  v6 = a1[1] - *a1;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v6 + 1;
  v9 = std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(a1, v6 + 1);
  size_of = std::_Get_size_of_n<8>(v9);
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = (_QWORD *)(v11 + 8 * (a2 - v3));
  v13 = *a3;
  *a3 = 0;
  *v12 = v13;
  v14 = (_QWORD *)v11;
  v15 = a1[1];
  v16 = *a1;
  if ( a2 == v15 )
  {
    while ( v16 != v15 )
    {
      v18 = *v16;
      *v16 = 0;
      *v14++ = v18;
      ++v16;
    }
    v19 = v14;
  }
  else
  {
    v17 = v12 + 1;
    while ( v16 != a2 )
    {
      v20 = *v16;
      *v16 = 0;
      *v14++ = v20;
      ++v16;
    }
    std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>>(v14, v14);
    v21 = a1[1];
    while ( a2 != v21 )
    {
      v22 = *a2;
      *a2 = 0;
      *v17++ = v22;
      ++a2;
    }
    v19 = v17;
    v14 = v17;
  }
  std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>>(v14, v19);
  std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Change_array(a1, v11, v8, v9);
  return v12;
}

```

## disassembly

```asm
0x180017910  push    rbx
0x180017912  push    rbp
0x180017913  push    rsi
0x180017914  push    rdi
0x180017915  push    r12
0x180017917  push    r13
0x180017919  push    r14
0x18001791b  push    r15
0x18001791d  sub     rsp, 28h
0x180017921  mov     rdi, [rcx]
0x180017924  mov     rsi, rcx
0x180017927  mov     rax, [rcx+8]
0x18001792b  mov     r15, r8
0x18001792e  sub     rax, rdi
0x180017931  mov     rcx, 1FFFFFFFFFFFFFFFh
0x18001793b  sar     rax, 3
0x18001793f  mov     rbx, rdx
0x180017942  cmp     rax, rcx
0x180017945  jnz     short loc_180017955
0x180017947  lea     rcx, aVectorTooLong; "vector too long"
0x18001794e  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017955  lea     r12, [rax+1]
0x180017959  mov     rcx, rsi
0x18001795c  mov     rdx, r12
0x18001795f  call    ?_Calculate_growth@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEBA_K_K@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(unsigned __int64)
0x180017964  mov     rcx, rax
0x180017967  mov     r13, rax
0x18001796a  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18001796f  mov     rcx, rax; dwBytes
0x180017972  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180017977  xor     r9d, r9d
0x18001797a  mov     rcx, rbx
0x18001797d  sub     rcx, rdi
0x180017980  mov     r14, rax
0x180017983  sar     rcx, 3
0x180017987  lea     rbp, [rax+rcx*8]
0x18001798b  mov     rcx, [r15]
0x18001798e  mov     [r15], r9
0x180017991  mov     [rbp+0], rcx
0x180017995  mov     rcx, rax
0x180017998  mov     r8, [rsi+8]
0x18001799c  mov     rdx, [rsi]
0x18001799f  cmp     rbx, r8
0x1800179a2  jz      short loc_1800179BB
0x1800179a4  lea     rdi, [rbp+8]
0x1800179a8  jmp     short loc_1800179D6
0x1800179aa  mov     rax, [rdx]
0x1800179ad  mov     [rdx], r9
0x1800179b0  mov     [rcx], rax
0x1800179b3  add     rcx, 8
0x1800179b7  add     rdx, 8
0x1800179bb  cmp     rdx, r8
0x1800179be  jnz     short loc_1800179AA
0x1800179c0  mov     rdx, rcx
0x1800179c3  jmp     short loc_180017A09
0x1800179c5  mov     rax, [rdx]
0x1800179c8  mov     [rdx], r9
0x1800179cb  mov     [rcx], rax
0x1800179ce  add     rcx, 8
0x1800179d2  add     rdx, 8
0x1800179d6  cmp     rdx, rbx
0x1800179d9  jnz     short loc_1800179C5
0x1800179db  mov     rdx, rcx
0x1800179de  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>>(std::unique_ptr<Windows::UI::Composition::EffectSubgraph> *,std::unique_ptr<Windows::UI::Composition::EffectSubgraph> * const,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>> &)
0x1800179e3  mov     rcx, [rsi+8]
0x1800179e7  jmp     short loc_1800179FE
0x1800179e9  mov     rax, [rbx]
0x1800179ec  mov     qword ptr [rbx], 0
0x1800179f3  mov     [rdi], rax
0x1800179f6  add     rdi, 8
0x1800179fa  add     rbx, 8
0x1800179fe  cmp     rbx, rcx
0x180017a01  jnz     short loc_1800179E9
0x180017a03  mov     rdx, rdi
0x180017a06  mov     rcx, rdi
0x180017a09  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>>(std::unique_ptr<Windows::UI::Composition::EffectSubgraph> *,std::unique_ptr<Windows::UI::Composition::EffectSubgraph> * const,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>> &)
0x180017a0e  mov     r9, r13
0x180017a11  mov     r8, r12
0x180017a14  mov     rdx, r14
0x180017a17  mov     rcx, rsi
0x180017a1a  call    ?_Change_array@?$vector@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@2@_K1@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Change_array(std::unique_ptr<Windows::UI::Composition::EffectSubgraph> * const,unsigned __int64,unsigned __int64)
0x180017a1f  mov     rax, rbp
0x180017a22  add     rsp, 28h
0x180017a26  pop     r15
0x180017a28  pop     r14
0x180017a2a  pop     r13
0x180017a2c  pop     r12
0x180017a2e  pop     rdi
0x180017a2f  pop     rsi
0x180017a30  pop     rbp
0x180017a31  pop     rbx
0x180017a32  retn
```
