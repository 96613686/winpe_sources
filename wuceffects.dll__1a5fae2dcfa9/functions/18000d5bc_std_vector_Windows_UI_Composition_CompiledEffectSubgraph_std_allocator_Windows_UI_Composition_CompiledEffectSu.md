# std::vector<Windows::UI::Composition::CompiledEffectSubgraph,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18000d5bc`
- end: `0x18000d708`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@VCompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `332`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000c410`

## callees

- `0x18000a88c`
- `0x18000ad40`
- `0x18000d5bc`
- `0x18000db84`
- `0x18000de60`
- `0x18001e6e0`
- `0x1800257e4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d5e7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d5e7`

## pseudocode

```c
char *__fastcall std::vector<Windows::UI::Composition::CompiledEffectSubgraph>::_Resize_reallocate<std::_Value_init_tag>(
        Windows::UI::Composition::CompiledEffectSubgraph **a1,
        unsigned __int64 a2)
{
  __int64 v2; // r8
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  __int64 v7; // r15
  unsigned __int64 v8; // rbx
  Windows::UI::Composition::CompiledEffectSubgraph *v9; // rbp
  Windows::UI::Composition::CompiledEffectSubgraph *v10; // r14
  Windows::UI::Composition::CompiledEffectSubgraph *v11; // rcx
  Windows::UI::Composition::CompiledEffectSubgraph *v12; // rbx
  char *result; // rax
  Windows::UI::Composition::CompiledEffectSubgraph *v14; // [rsp+20h] [rbp-58h] BYREF
  Windows::UI::Composition::CompiledEffectSubgraph *v15; // [rsp+28h] [rbp-50h]
  Windows::UI::Composition::CompiledEffectSubgraph **v16; // [rsp+30h] [rbp-48h]

  v2 = 0x1E1E1E1E1E1E1E1LL;
  if ( a2 > 0x1E1E1E1E1E1E1E1LL )
    std::_Xlength_error("vector too long");
  v5 = 0xF0F0F0F0F0F0F0F1uLL * ((a1[2] - *a1) >> 3);
  v6 = v5 >> 1;
  if ( v5 <= 0x1E1E1E1E1E1E1E1LL - (v5 >> 1) )
  {
    if ( v5 + v6 >= a2 )
    {
      if ( v5 + v6 > 0x1E1E1E1E1E1E1E1LL )
        std::_Throw_bad_array_new_length();
      v2 = v5 + v6;
    }
    else
    {
      v2 = a2;
    }
  }
  v7 = 136 * v2;
  v8 = 0xF0F0F0F0F0F0F0F1uLL * ((a1[1] - *a1) >> 3);
  v9 = (Windows::UI::Composition::CompiledEffectSubgraph *)std::_Allocate<16,std::_Default_allocate_traits>(136 * v2);
  std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(
    (char *)v9 + 136 * v8,
    a2 - v8,
    a1);
  v10 = a1[1];
  v11 = v9;
  v12 = *a1;
  v15 = v9;
  v14 = v9;
  v16 = a1;
  if ( v12 != v10 )
  {
    do
    {
      std::_Uninitialized_backout_al<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>::_Emplace_back<Windows::UI::Composition::CompiledEffectSubgraph>(
        &v14,
        v12);
      v12 = (Windows::UI::Composition::CompiledEffectSubgraph *)((char *)v12 + 136);
    }
    while ( v12 != v10 );
    v11 = v15;
  }
  std::_Destroy_range<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(v11);
  if ( *a1 )
  {
    std::_Destroy_range<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(*a1);
    std::_Deallocate<16>(*a1, 8 * ((a1[2] - *a1) >> 3));
  }
  *a1 = v9;
  a1[1] = (Windows::UI::Composition::CompiledEffectSubgraph *)((char *)v9 + 136 * a2);
  result = (char *)v9 + v7;
  a1[2] = (Windows::UI::Composition::CompiledEffectSubgraph *)((char *)v9 + v7);
  return result;
}

```

## disassembly

```asm
0x18000d5bc  push    rbx
0x18000d5be  push    rbp
0x18000d5bf  push    rsi
0x18000d5c0  push    rdi
0x18000d5c1  push    r12
0x18000d5c3  push    r14
0x18000d5c5  push    r15
0x18000d5c7  sub     rsp, 40h
0x18000d5cb  mov     r8, 1E1E1E1E1E1E1E1h
0x18000d5d5  mov     rsi, rdx
0x18000d5d8  mov     rdi, rcx
0x18000d5db  cmp     rdx, r8
0x18000d5de  jbe     short loc_18000D5EE
0x18000d5e0  lea     rcx, aVectorTooLong; "vector too long"
0x18000d5e7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000d5ee  mov     rcx, [rcx+10h]
0x18000d5f2  mov     r12, 0F0F0F0F0F0F0F0F1h
0x18000d5fc  sub     rcx, [rdi]
0x18000d5ff  mov     rax, r8
0x18000d602  sar     rcx, 3
0x18000d606  imul    rcx, r12
0x18000d60a  mov     rdx, rcx
0x18000d60d  shr     rdx, 1
0x18000d610  sub     rax, rdx
0x18000d613  cmp     rcx, rax
0x18000d616  ja      short loc_18000D634
0x18000d618  lea     rax, [rcx+rdx]
0x18000d61c  cmp     rax, rsi
0x18000d61f  jnb     short loc_18000D626
0x18000d621  mov     r8, rsi
0x18000d624  jmp     short loc_18000D634
0x18000d626  cmp     rax, r8
0x18000d629  jbe     short loc_18000D631
0x18000d62b  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000d631  mov     r8, rax
0x18000d634  mov     rbx, [rdi+8]
0x18000d638  sub     rbx, [rdi]
0x18000d63b  imul    r15, r8, 88h
0x18000d642  sar     rbx, 3
0x18000d646  mov     rcx, r15; dwBytes
0x18000d649  imul    rbx, r12
0x18000d64d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d652  imul    rcx, rbx, 88h
0x18000d659  mov     rdx, rsi
0x18000d65c  mov     r8, rdi
0x18000d65f  add     rcx, rax
0x18000d662  sub     rdx, rbx
0x18000d665  mov     rbp, rax
0x18000d668  call    ??$_Uninitialized_value_construct_n@V?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAVCompiledEffectSubgraph@Composition@UI@Windows@@PEAV1234@_KAEAV?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(Windows::UI::Composition::CompiledEffectSubgraph *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph> &)
0x18000d66d  mov     r14, [rdi+8]
0x18000d671  mov     rcx, rbp
0x18000d674  mov     rbx, [rdi]
0x18000d677  mov     [rsp+78h+var_50], rcx
0x18000d67c  mov     [rsp+78h+var_58], rbp
0x18000d681  mov     [rsp+78h+var_48], rdi
0x18000d686  cmp     rbx, r14
0x18000d689  jz      short loc_18000D6A9
0x18000d68b  mov     rdx, rbx
0x18000d68e  lea     rcx, [rsp+78h+var_58]
0x18000d693  call    ??$_Emplace_back@VCompiledEffectSubgraph@Composition@UI@Windows@@@?$_Uninitialized_backout_al@V?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@QEAAX$$QEAVCompiledEffectSubgraph@Composition@UI@Windows@@@Z; std::_Uninitialized_backout_al<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>::_Emplace_back<Windows::UI::Composition::CompiledEffectSubgraph>(Windows::UI::Composition::CompiledEffectSubgraph &&)
0x18000d698  add     rbx, 88h
0x18000d69f  cmp     rbx, r14
0x18000d6a2  jnz     short loc_18000D68B
0x18000d6a4  mov     rcx, [rsp+78h+var_50]; this
0x18000d6a9  mov     rdx, rcx
0x18000d6ac  call    ??$_Destroy_range@V?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAXPEAVCompiledEffectSubgraph@Composition@UI@Windows@@QEAV1234@AEAV?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(Windows::UI::Composition::CompiledEffectSubgraph *,Windows::UI::Composition::CompiledEffectSubgraph * const,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph> &)
0x18000d6b1  mov     rcx, [rdi]; this
0x18000d6b4  test    rcx, rcx
0x18000d6b7  jz      short loc_18000D6E0
0x18000d6b9  mov     rdx, [rdi+8]
0x18000d6bd  call    ??$_Destroy_range@V?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAXPEAVCompiledEffectSubgraph@Composition@UI@Windows@@QEAV1234@AEAV?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(Windows::UI::Composition::CompiledEffectSubgraph *,Windows::UI::Composition::CompiledEffectSubgraph * const,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph> &)
0x18000d6c2  mov     rax, [rdi+10h]
0x18000d6c6  sub     rax, [rdi]
0x18000d6c9  mov     rcx, [rdi]
0x18000d6cc  sar     rax, 3
0x18000d6d0  imul    rax, r12
0x18000d6d4  imul    rdx, rax, 88h
0x18000d6db  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d6e0  mov     [rdi], rbp
0x18000d6e3  imul    rax, rsi, 88h
0x18000d6ea  add     rax, rbp
0x18000d6ed  mov     [rdi+8], rax
0x18000d6f1  lea     rax, [r15+rbp]
0x18000d6f5  mov     [rdi+10h], rax
0x18000d6f9  add     rsp, 40h
0x18000d6fd  pop     r15
0x18000d6ff  pop     r14
0x18000d701  pop     r12
0x18000d703  pop     rdi
0x18000d704  pop     rsi
0x18000d705  pop     rbp
0x18000d706  pop     rbx
0x18000d707  retn
```
