# std::vector<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18000d0d4`
- end: `0x18000d19e`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c410`

## callees

- `0x18000a88c`
- `0x18000ad40`
- `0x18000c330`
- `0x18000c7a0`
- `0x18000d0d4`
- `0x180021ce0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d0fb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d0fb`

## pseudocode

```c
char *__fastcall std::vector<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>::_Resize_reallocate<std::_Value_init_tag>(
        _QWORD *a1,
        unsigned __int64 a2)
{
  __int64 v2; // rdi
  __int64 v5; // rbp
  unsigned __int64 v6; // rcx
  __int64 v7; // rbp
  unsigned __int64 v8; // rdx
  SIZE_T size_of; // rax
  char *v10; // r14
  char *result; // rax

  v2 = 0x3FFFFFFFFFFFFFFFLL;
  if ( a2 > 0x3FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v5 = a1[1] - *a1;
  v6 = (__int64)(a1[2] - *a1) >> 2;
  v7 = v5 >> 2;
  v8 = v6 >> 1;
  if ( v6 <= 0x3FFFFFFFFFFFFFFFLL - (v6 >> 1) )
  {
    v2 = v6 + v8;
    if ( v6 + v8 < a2 )
      v2 = a2;
  }
  size_of = std::_Get_size_of_n<4>(v2);
  v10 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>>(
    &v10[4 * v7],
    a2 - v7);
  memmove_0(v10, (const void *)*a1, a1[1] - *a1);
  if ( *a1 )
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFFCuLL);
  *a1 = v10;
  a1[1] = &v10[4 * a2];
  result = &v10[4 * v2];
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x18000d0d4  push    rbx
0x18000d0d6  push    rbp
0x18000d0d7  push    rsi
0x18000d0d8  push    rdi
0x18000d0d9  push    r14
0x18000d0db  sub     rsp, 20h
0x18000d0df  mov     rdi, 3FFFFFFFFFFFFFFFh
0x18000d0e9  mov     rsi, rdx
0x18000d0ec  mov     rbx, rcx
0x18000d0ef  cmp     rdx, rdi
0x18000d0f2  jbe     short loc_18000D102
0x18000d0f4  lea     rcx, aVectorTooLong; "vector too long"
0x18000d0fb  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000d102  mov     rbp, [rcx+8]
0x18000d106  mov     rax, rdi
0x18000d109  sub     rbp, [rcx]
0x18000d10c  mov     rcx, [rcx+10h]
0x18000d110  sub     rcx, [rbx]
0x18000d113  sar     rcx, 2
0x18000d117  mov     rdx, rcx
0x18000d11a  sar     rbp, 2
0x18000d11e  shr     rdx, 1
0x18000d121  sub     rax, rdx
0x18000d124  cmp     rcx, rax
0x18000d127  ja      short loc_18000D134
0x18000d129  lea     rdi, [rcx+rdx]
0x18000d12d  cmp     rdi, rsi
0x18000d130  cmovb   rdi, rsi
0x18000d134  mov     rcx, rdi
0x18000d137  call    ??$_Get_size_of_n@$03@std@@YA_K_K@Z; std::_Get_size_of_n<4>(unsigned __int64)
0x18000d13c  mov     rcx, rax; dwBytes
0x18000d13f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d144  mov     rdx, rsi
0x18000d147  mov     r14, rax
0x18000d14a  sub     rdx, rbp
0x18000d14d  lea     rcx, [rax+rbp*4]
0x18000d151  call    ??$_Uninitialized_value_construct_n@V?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUSurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>>(Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData> &)
0x18000d156  mov     r8, [rbx+8]
0x18000d15a  mov     rcx, r14; void *
0x18000d15d  sub     r8, [rbx]; Size
0x18000d160  mov     rdx, [rbx]; Src
0x18000d163  call    memmove_0
0x18000d168  mov     rcx, [rbx]
0x18000d16b  test    rcx, rcx
0x18000d16e  jz      short loc_18000D180
0x18000d170  mov     rdx, [rbx+10h]
0x18000d174  sub     rdx, rcx
0x18000d177  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18000d17b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d180  lea     rax, [r14+rsi*4]
0x18000d184  mov     [rbx], r14
0x18000d187  mov     [rbx+8], rax
0x18000d18b  lea     rax, [r14+rdi*4]
0x18000d18f  mov     [rbx+10h], rax
0x18000d193  add     rsp, 20h
0x18000d197  pop     r14
0x18000d199  pop     rdi
0x18000d19a  pop     rsi
0x18000d19b  pop     rbp
0x18000d19c  pop     rbx
0x18000d19d  retn
```
