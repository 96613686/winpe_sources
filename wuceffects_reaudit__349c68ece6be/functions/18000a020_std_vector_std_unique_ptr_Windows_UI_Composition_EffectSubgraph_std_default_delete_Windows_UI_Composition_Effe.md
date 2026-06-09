# std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>>,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectSubgraph,std::default_delete<Windows::UI::Composition::EffectSubgraph>>>>::reserve(unsigned __int64)

- ea: `0x18000a020`
- end: `0x18000a152`
- name: `?reserve@?$vector@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@2@@std@@QEAAX_K@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009730`

## callees

- `0x18000a020`
- `0x18000a810`
- `0x18000ad10`
- `0x18000ad40`
- `0x180021084`
- `0x1800257b8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a130`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a130`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::reserve(
        __int64 a1,
        unsigned __int64 a2)
{
  __int64 *v4; // rcx
  unsigned __int64 result; // rax
  __int64 v6; // r15
  SIZE_T size_of; // rax
  __int64 v8; // rax
  __int64 *v9; // r8
  __int64 v10; // r14
  __int64 v11; // rdx
  __int64 *i; // rax
  __int64 v13; // rcx
  __int64 *v14; // rbx
  __int64 *j; // rsi
  _QWORD *v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // [rsp+50h] [rbp+8h] BYREF
  void *v19; // [rsp+58h] [rbp+10h] BYREF

  v4 = *(__int64 **)a1;
  result = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)v4) >> 3;
  if ( a2 > result )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    v6 = (__int64)(*(_QWORD *)(a1 + 8) - (_QWORD)v4) >> 3;
    size_of = std::_Get_size_of_n<8>(a2);
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v9 = *(__int64 **)(a1 + 8);
    v10 = v8;
    v11 = v8;
    for ( i = *(__int64 **)a1; i != v9; *(_QWORD *)(v11 - 8) = v13 )
    {
      v13 = *i;
      v11 += 8;
      *i++ = 0;
    }
    v14 = *(__int64 **)a1;
    if ( *(_QWORD *)a1 )
    {
      for ( j = *(__int64 **)(a1 + 8); v14 != j; ++v14 )
        std::unique_ptr<Windows::UI::Composition::EffectSubgraph>::~unique_ptr<Windows::UI::Composition::EffectSubgraph>((_QWORD **)v14);
      v16 = *(_QWORD **)a1;
      v17 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL;
      v19 = *(void **)a1;
      v18 = v17;
      if ( v17 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v19, &v18);
        v16 = v19;
      }
      operator delete(v16);
    }
    *(_QWORD *)a1 = v10;
    *(_QWORD *)(a1 + 8) = v10 + 8 * v6;
    result = v10 + 8 * a2;
    *(_QWORD *)(a1 + 16) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000a020  push    rbp
0x18000a022  push    rdi
0x18000a023  sub     rsp, 38h
0x18000a027  mov     rdi, rcx
0x18000a02a  mov     rbp, rdx
0x18000a02d  mov     rcx, [rcx]
0x18000a030  mov     rax, [rdi+10h]
0x18000a034  sub     rax, rcx
0x18000a037  sar     rax, 3
0x18000a03b  cmp     rdx, rax
0x18000a03e  jbe     loc_18000A122
0x18000a044  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000a04e  cmp     rdx, rax
0x18000a051  ja      loc_18000A129
0x18000a057  mov     [rsp+48h+arg_10], rbx
0x18000a05c  mov     [rsp+48h+var_20], r14
0x18000a061  mov     [rsp+48h+var_28], r15
0x18000a066  mov     r15, [rdi+8]
0x18000a06a  sub     r15, rcx
0x18000a06d  mov     rcx, rdx
0x18000a070  sar     r15, 3
0x18000a074  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000a079  mov     rcx, rax; dwBytes
0x18000a07c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a081  mov     r8, [rdi+8]
0x18000a085  mov     r14, rax
0x18000a088  mov     rdx, rax
0x18000a08b  mov     rax, [rdi]
0x18000a08e  cmp     rax, r8
0x18000a091  jz      short loc_18000A0AE
0x18000a093  mov     rcx, [rax]
0x18000a096  lea     rdx, [rdx+8]
0x18000a09a  mov     qword ptr [rax], 0
0x18000a0a1  add     rax, 8
0x18000a0a5  mov     [rdx-8], rcx
0x18000a0a9  cmp     rax, r8
0x18000a0ac  jnz     short loc_18000A093
0x18000a0ae  mov     rbx, [rdi]
0x18000a0b1  test    rbx, rbx
0x18000a0b4  jz      short loc_18000A100
0x18000a0b6  mov     [rsp+48h+var_18], rsi
0x18000a0bb  mov     rsi, [rdi+8]
0x18000a0bf  cmp     rbx, rsi
0x18000a0c2  jz      short loc_18000A0D5
0x18000a0c4  mov     rcx, rbx
0x18000a0c7  call    ??1?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::UI::Composition::EffectSubgraph>::~unique_ptr<Windows::UI::Composition::EffectSubgraph>(void)
0x18000a0cc  add     rbx, 8
0x18000a0d0  cmp     rbx, rsi
0x18000a0d3  jnz     short loc_18000A0C4
0x18000a0d5  mov     rcx, [rdi]; void *
0x18000a0d8  mov     rdx, [rdi+10h]
0x18000a0dc  mov     rsi, [rsp+48h+var_18]
0x18000a0e1  sub     rdx, rcx
0x18000a0e4  and     rdx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x18000a0e8  mov     [rsp+48h+arg_8], rcx
0x18000a0ed  mov     [rsp+48h+arg_0], rdx
0x18000a0f2  cmp     rdx, 1000h
0x18000a0f9  jnb     short loc_18000A137
0x18000a0fb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a100  mov     rbx, [rsp+48h+arg_10]
0x18000a105  lea     rax, [r14+r15*8]
0x18000a109  mov     r15, [rsp+48h+var_28]
0x18000a10e  mov     [rdi], r14
0x18000a111  mov     [rdi+8], rax
0x18000a115  lea     rax, [r14+rbp*8]
0x18000a119  mov     r14, [rsp+48h+var_20]
0x18000a11e  mov     [rdi+10h], rax
0x18000a122  add     rsp, 38h
0x18000a126  pop     rdi
0x18000a127  pop     rbp
0x18000a128  retn
0x18000a129  lea     rcx, aVectorTooLong; "vector too long"
0x18000a130  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a137  lea     rdx, [rsp+48h+arg_0]; unsigned __int64 *
0x18000a13c  lea     rcx, [rsp+48h+arg_8]; void **
0x18000a141  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000a146  mov     rdx, [rsp+48h+arg_0]
0x18000a14b  mov     rcx, [rsp+48h+arg_8]
0x18000a150  jmp     short loc_18000A0FB
```
