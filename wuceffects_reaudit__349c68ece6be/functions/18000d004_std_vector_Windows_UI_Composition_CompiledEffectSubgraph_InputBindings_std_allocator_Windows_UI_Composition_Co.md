# std::vector<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18000d004`
- end: `0x18000d0ce`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c410`

## callees

- `0x18000a88c`
- `0x18000ad10`
- `0x18000ad40`
- `0x18000c75c`
- `0x18000d004`
- `0x180021ce0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d02b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d02b`

## pseudocode

```c
char *__fastcall std::vector<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>::_Resize_reallocate<std::_Value_init_tag>(
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

  v2 = 0x1FFFFFFFFFFFFFFFLL;
  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v5 = a1[1] - *a1;
  v6 = (__int64)(a1[2] - *a1) >> 3;
  v7 = v5 >> 3;
  v8 = v6 >> 1;
  if ( v6 <= 0x1FFFFFFFFFFFFFFFLL - (v6 >> 1) )
  {
    v2 = v6 + v8;
    if ( v6 + v8 < a2 )
      v2 = a2;
  }
  size_of = std::_Get_size_of_n<8>(v2);
  v10 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>>(
    &v10[8 * v7],
    a2 - v7);
  memmove_0(v10, (const void *)*a1, a1[1] - *a1);
  if ( *a1 )
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  *a1 = v10;
  a1[1] = &v10[8 * a2];
  result = &v10[8 * v2];
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x18000d004  push    rbx
0x18000d006  push    rbp
0x18000d007  push    rsi
0x18000d008  push    rdi
0x18000d009  push    r14
0x18000d00b  sub     rsp, 20h
0x18000d00f  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18000d019  mov     rsi, rdx
0x18000d01c  mov     rbx, rcx
0x18000d01f  cmp     rdx, rdi
0x18000d022  jbe     short loc_18000D032
0x18000d024  lea     rcx, aVectorTooLong; "vector too long"
0x18000d02b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000d032  mov     rbp, [rcx+8]
0x18000d036  mov     rax, rdi
0x18000d039  sub     rbp, [rcx]
0x18000d03c  mov     rcx, [rcx+10h]
0x18000d040  sub     rcx, [rbx]
0x18000d043  sar     rcx, 3
0x18000d047  mov     rdx, rcx
0x18000d04a  sar     rbp, 3
0x18000d04e  shr     rdx, 1
0x18000d051  sub     rax, rdx
0x18000d054  cmp     rcx, rax
0x18000d057  ja      short loc_18000D064
0x18000d059  lea     rdi, [rcx+rdx]
0x18000d05d  cmp     rdi, rsi
0x18000d060  cmovb   rdi, rsi
0x18000d064  mov     rcx, rdi
0x18000d067  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000d06c  mov     rcx, rax; dwBytes
0x18000d06f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d074  mov     rdx, rsi
0x18000d077  mov     r14, rax
0x18000d07a  sub     rdx, rbp
0x18000d07d  lea     rcx, [rax+rbp*8]
0x18000d081  call    ??$_Uninitialized_value_construct_n@V?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>>(Windows::UI::Composition::CompiledEffectSubgraph::InputBindings *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings> &)
0x18000d086  mov     r8, [rbx+8]
0x18000d08a  mov     rcx, r14; void *
0x18000d08d  sub     r8, [rbx]; Size
0x18000d090  mov     rdx, [rbx]; Src
0x18000d093  call    memmove_0
0x18000d098  mov     rcx, [rbx]
0x18000d09b  test    rcx, rcx
0x18000d09e  jz      short loc_18000D0B0
0x18000d0a0  mov     rdx, [rbx+10h]
0x18000d0a4  sub     rdx, rcx
0x18000d0a7  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000d0ab  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d0b0  lea     rax, [r14+rsi*8]
0x18000d0b4  mov     [rbx], r14
0x18000d0b7  mov     [rbx+8], rax
0x18000d0bb  lea     rax, [r14+rdi*8]
0x18000d0bf  mov     [rbx+10h], rax
0x18000d0c3  add     rsp, 20h
0x18000d0c7  pop     r14
0x18000d0c9  pop     rdi
0x18000d0ca  pop     rsi
0x18000d0cb  pop     rbp
0x18000d0cc  pop     rbx
0x18000d0cd  retn
```
