# std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>>,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>>>>::_Emplace_reallocate<>(std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>> * const)

- ea: `0x1800177ec`
- end: `0x18001790a`
- name: `??$_Emplace_reallocate@$$V@?$vector@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@1@QEAV21@@Z`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009730`

## callees

- `0x180009fe0`
- `0x18000a760`
- `0x18000ad10`
- `0x18000ad40`
- `0x180016bf0`
- `0x1800177ec`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017825`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017825`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Emplace_reallocate<>(
        __int64 **a1,
        __int64 *a2)
{
  __int64 *v2; // rdi
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 v7; // r12
  SIZE_T size_of; // rax
  __int64 v9; // r14
  _QWORD *v10; // r15
  _QWORD *v11; // rcx
  __int64 *v12; // r8
  __int64 *v13; // rdx
  _QWORD *v14; // rdi
  __int64 v15; // rax
  _QWORD *v16; // rdx
  __int64 v17; // rax
  __int64 *v18; // rcx
  __int64 v19; // rax

  v2 = *a1;
  v5 = a1[1] - *a1;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v6 = v5 + 1;
  v7 = std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(a1, v5 + 1);
  size_of = std::_Get_size_of_n<8>(v7);
  v9 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v10 = (_QWORD *)(v9 + 8 * (a2 - v2));
  v11 = (_QWORD *)v9;
  *v10 = 0;
  v12 = a1[1];
  v13 = *a1;
  if ( a2 == v12 )
  {
    while ( v13 != v12 )
    {
      v15 = *v13;
      *v13 = 0;
      *v11++ = v15;
      ++v13;
    }
    v16 = v11;
  }
  else
  {
    v14 = v10 + 1;
    while ( v13 != a2 )
    {
      v17 = *v13;
      *v13 = 0;
      *v11++ = v17;
      ++v13;
    }
    std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>>(v11, v11);
    v18 = a1[1];
    while ( a2 != v18 )
    {
      v19 = *a2;
      *a2 = 0;
      *v14++ = v19;
      ++a2;
    }
    v16 = v14;
    v11 = v14;
  }
  std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>>(v11, v16);
  std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Change_array(a1, v9, v6, v7);
  return v10;
}

```

## disassembly

```asm
0x1800177ec  push    rbx
0x1800177ee  push    rbp
0x1800177ef  push    rsi
0x1800177f0  push    rdi
0x1800177f1  push    r12
0x1800177f3  push    r14
0x1800177f5  push    r15
0x1800177f7  sub     rsp, 20h
0x1800177fb  mov     rdi, [rcx]
0x1800177fe  mov     rsi, rcx
0x180017801  mov     rax, [rcx+8]
0x180017805  mov     rbx, rdx
0x180017808  sub     rax, rdi
0x18001780b  mov     rcx, 1FFFFFFFFFFFFFFFh
0x180017815  sar     rax, 3
0x180017819  cmp     rax, rcx
0x18001781c  jnz     short loc_18001782C
0x18001781e  lea     rcx, aVectorTooLong; "vector too long"
0x180017825  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001782c  lea     rbp, [rax+1]
0x180017830  mov     rcx, rsi
0x180017833  mov     rdx, rbp
0x180017836  call    ?_Calculate_growth@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEBA_K_K@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(unsigned __int64)
0x18001783b  mov     rcx, rax
0x18001783e  mov     r12, rax
0x180017841  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180017846  mov     rcx, rax; dwBytes
0x180017849  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001784e  mov     rcx, rbx
0x180017851  mov     r14, rax
0x180017854  sub     rcx, rdi
0x180017857  sar     rcx, 3
0x18001785b  lea     r15, [rax+rcx*8]
0x18001785f  mov     rcx, rax
0x180017862  mov     qword ptr [r15], 0
0x180017869  mov     r8, [rsi+8]
0x18001786d  mov     rdx, [rsi]
0x180017870  cmp     rbx, r8
0x180017873  jz      short loc_180017890
0x180017875  lea     rdi, [r15+8]
0x180017879  jmp     short loc_1800178AF
0x18001787b  mov     rax, [rdx]
0x18001787e  mov     qword ptr [rdx], 0
0x180017885  mov     [rcx], rax
0x180017888  add     rcx, 8
0x18001788c  add     rdx, 8
0x180017890  cmp     rdx, r8
0x180017893  jnz     short loc_18001787B
0x180017895  mov     rdx, rcx
0x180017898  jmp     short loc_1800178E2
0x18001789a  mov     rax, [rdx]
0x18001789d  mov     qword ptr [rdx], 0
0x1800178a4  mov     [rcx], rax
0x1800178a7  add     rcx, 8
0x1800178ab  add     rdx, 8
0x1800178af  cmp     rdx, rbx
0x1800178b2  jnz     short loc_18001789A
0x1800178b4  mov     rdx, rcx
0x1800178b7  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>>(std::unique_ptr<Windows::UI::Composition::EffectSubgraph> *,std::unique_ptr<Windows::UI::Composition::EffectSubgraph> * const,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>> &)
0x1800178bc  mov     rcx, [rsi+8]
0x1800178c0  jmp     short loc_1800178D7
0x1800178c2  mov     rax, [rbx]
0x1800178c5  mov     qword ptr [rbx], 0
0x1800178cc  mov     [rdi], rax
0x1800178cf  add     rdi, 8
0x1800178d3  add     rbx, 8
0x1800178d7  cmp     rbx, rcx
0x1800178da  jnz     short loc_1800178C2
0x1800178dc  mov     rdx, rdi
0x1800178df  mov     rcx, rdi
0x1800178e2  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>>(std::unique_ptr<Windows::UI::Composition::EffectSubgraph> *,std::unique_ptr<Windows::UI::Composition::EffectSubgraph> * const,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>> &)
0x1800178e7  mov     r9, r12
0x1800178ea  mov     r8, rbp
0x1800178ed  mov     rdx, r14
0x1800178f0  mov     rcx, rsi
0x1800178f3  call    ?_Change_array@?$vector@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@2@_K1@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Change_array(std::unique_ptr<Windows::UI::Composition::EffectSubgraph> * const,unsigned __int64,unsigned __int64)
0x1800178f8  mov     rax, r15
0x1800178fb  add     rsp, 20h
0x1800178ff  pop     r15
0x180017901  pop     r14
0x180017903  pop     r12
0x180017905  pop     rdi
0x180017906  pop     rsi
0x180017907  pop     rbp
0x180017908  pop     rbx
0x180017909  retn
```
