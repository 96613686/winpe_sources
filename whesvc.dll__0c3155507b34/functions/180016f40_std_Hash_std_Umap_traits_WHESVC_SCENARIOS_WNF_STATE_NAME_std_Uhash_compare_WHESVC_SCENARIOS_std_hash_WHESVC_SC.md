# std::_Hash<std::_Umap_traits<_WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<_WHESVC_SCENARIOS,std::hash<_WHESVC_SCENARIOS>,std::equal_to<_WHESVC_SCENARIOS>>,std::allocator<std::pair<_WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::_Rehash_for_1(void)

- ea: `0x180016f40`
- end: `0x18001714f`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@W4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@V?$_Uhash_compare@W4_WHESVC_SCENARIOS@@U?$hash@W4_WHESVC_SCENARIOS@@@std@@U?$equal_to@W4_WHESVC_SCENARIOS@@@3@@std@@V?$allocator@U?$pair@$$CBW4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@@std@@@4@$0A@@std@@@std@@IEAAXXZ`
- size: `527`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800101f4`
- `0x180012194`

## callees

- `0x180003d44`
- `0x180016b28`
- `0x180016f40`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017000`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017000`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<enum _WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<enum _WHESVC_SCENARIOS,std::hash<enum _WHESVC_SCENARIOS>,std::equal_to<enum _WHESVC_SCENARIOS>>,std::allocator<std::pair<enum _WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::_Rehash_for_1(
        __int64 a1)
{
  __int64 v1; // rdx
  bool v3; // sf
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  float v6; // xmm0_4
  float v7; // xmm0_4
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  __int64 v15; // rdi
  _QWORD *result; // rax
  _QWORD *v17; // rcx
  __int64 v18; // r10
  unsigned __int64 i; // r8
  __int64 v20; // rdx
  __int64 v21; // r11
  __int64 v22; // r10
  __int64 *v23; // rdx
  int v24; // r8d
  _QWORD *v25; // rdi
  _QWORD *v26; // r9
  _QWORD *v27; // r8
  _QWORD *v28; // rdx
  __int64 **v29; // rdi
  __int64 v30; // r10
  _QWORD *v31; // r9
  _QWORD *v32; // r8
  _QWORD *v33; // rdx
  _QWORD *v34; // r9
  __int64 **v35; // r8
  __int64 *v36; // rdx

  v1 = *(_QWORD *)(a1 + 16);
  v3 = v1 + 1 < 0;
  v4 = v1 + 1;
  v5 = *(_QWORD *)(a1 + 56);
  if ( v3 )
    v6 = (float)(int)(v4 & 1 | (v4 >> 1)) + (float)(int)(v4 & 1 | (v4 >> 1));
  else
    v6 = (float)(int)v4;
  v7 = o_ceilf_0(v6 / *(float *)a1);
  v8 = 0;
  if ( v7 >= 9.223372e18 )
  {
    v7 = v7 - 9.223372e18;
    if ( v7 < 9.223372e18 )
      v8 = 0x8000000000000000uLL;
  }
  v9 = v8 + (unsigned int)(int)v7;
  v10 = 8;
  if ( v9 > 8 )
    v10 = v9;
  if ( v5 < v10 )
  {
    if ( v5 >= 0x200 || (v5 *= 8LL, v5 < v10) )
      v5 = v10;
  }
  _BitScanReverse64(&v11, 0xFFFFFFFFFFFFFFFuLL);
  if ( v5 > 1LL << v11 )
    std::_Xlength_error("invalid hash bucket count");
  v12 = v5 - 1;
  v13 = *(_QWORD *)(a1 + 8);
  _BitScanReverse64(&v14, v12 | 1);
  v15 = 1LL << ((unsigned __int8)v14 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(
    a1 + 24,
    2 * v15,
    v13);
  *(_QWORD *)(a1 + 56) = v15;
  *(_QWORD *)(a1 + 48) = v15 - 1;
  result = **(_QWORD ***)(a1 + 8);
  v17 = result;
  while ( result != (_QWORD *)v13 )
  {
    v17 = (_QWORD *)*v17;
    v18 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 4; ++i )
    {
      v20 = *((unsigned __int8 *)result + i + 16);
      v18 = 0x100000001B3LL * (v20 ^ v18);
    }
    v21 = *(_QWORD *)(a1 + 24);
    v22 = 2 * (*(_QWORD *)(a1 + 48) & v18);
    if ( *(_QWORD *)(v21 + 8 * v22) == v13 )
    {
      *(_QWORD *)(v21 + 8 * v22) = result;
LABEL_21:
      *(_QWORD *)(v21 + 8 * v22 + 8) = result;
      goto LABEL_29;
    }
    v23 = *(__int64 **)(v21 + 8 * v22 + 8);
    v24 = *((_DWORD *)result + 4);
    if ( v24 == *((_DWORD *)v23 + 4) )
    {
      v25 = (_QWORD *)*v23;
      if ( (_QWORD *)*v23 != result )
      {
        v26 = (_QWORD *)result[1];
        *v26 = v17;
        v27 = (_QWORD *)v17[1];
        *v27 = v25;
        v28 = (_QWORD *)v25[1];
        *v28 = result;
        v25[1] = v27;
        v17[1] = v26;
        result[1] = v28;
      }
      goto LABEL_21;
    }
    while ( 1 )
    {
      v29 = (__int64 **)(v23 + 1);
      if ( *(__int64 **)(v21 + 8 * v22) == v23 )
        break;
      v23 = *v29;
      if ( v24 == *((_DWORD *)*v29 + 4) )
      {
        v30 = *v23;
        v31 = (_QWORD *)result[1];
        *v31 = v17;
        v32 = (_QWORD *)v17[1];
        *v32 = v30;
        v33 = *(_QWORD **)(v30 + 8);
        *v33 = result;
        *(_QWORD *)(v30 + 8) = v32;
        v17[1] = v31;
        result[1] = v33;
        goto LABEL_29;
      }
    }
    v34 = (_QWORD *)result[1];
    *v34 = v17;
    v35 = (__int64 **)v17[1];
    *v35 = v23;
    v36 = *v29;
    *v36 = (__int64)result;
    *v29 = (__int64 *)v35;
    v17[1] = v34;
    result[1] = v36;
    *(_QWORD *)(v21 + 8 * v22) = result;
LABEL_29:
    result = v17;
  }
  return result;
}

```

## disassembly

```asm
0x180016f40  push    rbx
0x180016f42  push    rsi
0x180016f43  push    rdi
0x180016f44  push    r14
0x180016f46  sub     rsp, 28h
0x180016f4a  mov     rdx, [rcx+10h]
0x180016f4e  mov     rsi, rcx
0x180016f51  add     rdx, 1
0x180016f55  mov     rbx, [rcx+38h]
0x180016f59  xorps   xmm0, xmm0
0x180016f5c  js      short loc_180016F65
0x180016f5e  cvtsi2ss xmm0, rdx
0x180016f63  jmp     short loc_180016F7A
0x180016f65  mov     rax, rdx
0x180016f68  and     edx, 1
0x180016f6b  shr     rax, 1
0x180016f6e  or      rax, rdx
0x180016f71  cvtsi2ss xmm0, rax
0x180016f76  addss   xmm0, xmm0
0x180016f7a  divss   xmm0, dword ptr [rcx]; X
0x180016f7e  call    _o_ceilf_0
0x180016f83  movss   xmm1, cs:__real@5f000000
0x180016f8b  xor     ecx, ecx
0x180016f8d  comiss  xmm0, xmm1
0x180016f90  jb      short loc_180016FA8
0x180016f92  subss   xmm0, xmm1
0x180016f96  comiss  xmm0, xmm1
0x180016f99  jnb     short loc_180016FA8
0x180016f9b  mov     rax, 8000000000000000h
0x180016fa5  mov     rcx, rax
0x180016fa8  cvttss2si rax, xmm0
0x180016fad  add     rax, rcx
0x180016fb0  mov     ecx, 8
0x180016fb5  cmp     rax, rcx
0x180016fb8  cmova   rcx, rax
0x180016fbc  cmp     rbx, rcx
0x180016fbf  jnb     short loc_180016FD6
0x180016fc1  cmp     rbx, 200h
0x180016fc8  jnb     short loc_180016FD3
0x180016fca  shl     rbx, 3
0x180016fce  cmp     rbx, rcx
0x180016fd1  jnb     short loc_180016FD6
0x180016fd3  mov     rbx, rcx
0x180016fd6  mov     rax, 0FFFFFFFFFFFFFFFh
0x180016fe0  mov     [rsp+48h+arg_0], 0
0x180016fe8  bsr     rcx, rax
0x180016fec  mov     eax, 1
0x180016ff1  shl     rax, cl
0x180016ff4  cmp     rbx, rax
0x180016ff7  jbe     short loc_180017007
0x180016ff9  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180017000  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017007  lea     rax, [rbx-1]
0x18001700b  mov     [rsp+48h+arg_0], 0
0x180017013  mov     rbx, [rsi+8]
0x180017017  or      rax, 1
0x18001701b  bsr     rcx, rax
0x18001701f  mov     edi, 1
0x180017024  mov     r8, rbx
0x180017027  inc     ecx
0x180017029  shl     rdi, cl
0x18001702c  lea     rcx, [rsi+18h]
0x180017030  lea     rdx, [rdi+rdi]
0x180017034  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>)
0x180017039  lea     rax, [rdi-1]
0x18001703d  mov     [rsi+38h], rdi
0x180017041  mov     [rsi+30h], rax
0x180017045  mov     rax, [rsi+8]
0x180017049  mov     rax, [rax]
0x18001704c  mov     rcx, rax
0x18001704f  cmp     rax, rbx
0x180017052  jz      loc_180017145
0x180017058  mov     rcx, [rcx]
0x18001705b  mov     r10, 0CBF29CE484222325h
0x180017065  xor     r8d, r8d
0x180017068  movzx   edx, byte ptr [rax+r8+10h]
0x18001706e  mov     r9, 100000001B3h
0x180017078  xor     r10, rdx
0x18001707b  inc     r8
0x18001707e  imul    r10, r9
0x180017082  cmp     r8, 4
0x180017086  jb      short loc_180017068
0x180017088  and     r10, [rsi+30h]
0x18001708c  mov     r11, [rsi+18h]
0x180017090  add     r10, r10
0x180017093  cmp     [r11+r10*8], rbx
0x180017097  jnz     short loc_1800170A7
0x180017099  mov     [r11+r10*8], rax
0x18001709d  mov     [r11+r10*8+8], rax
0x1800170a2  jmp     loc_18001713D
0x1800170a7  mov     rdx, [r11+r10*8+8]
0x1800170ac  mov     r8d, [rax+10h]
0x1800170b0  cmp     r8d, [rdx+10h]
0x1800170b4  jnz     short loc_1800170E1
0x1800170b6  mov     rdi, [rdx]
0x1800170b9  cmp     rdi, rax
0x1800170bc  jz      short loc_18001709D
0x1800170be  mov     r9, [rax+8]
0x1800170c2  mov     [r9], rcx
0x1800170c5  mov     r8, [rcx+8]
0x1800170c9  mov     [r8], rdi
0x1800170cc  mov     rdx, [rdi+8]
0x1800170d0  mov     [rdx], rax
0x1800170d3  mov     [rdi+8], r8
0x1800170d7  mov     [rcx+8], r9
0x1800170db  mov     [rax+8], rdx
0x1800170df  jmp     short loc_18001709D
0x1800170e1  lea     rdi, [rdx+8]
0x1800170e5  cmp     [r11+r10*8], rdx
0x1800170e9  jz      short loc_18001711A
0x1800170eb  mov     rdx, [rdi]
0x1800170ee  cmp     r8d, [rdx+10h]
0x1800170f2  jnz     short loc_1800170E1
0x1800170f4  mov     r10, [rdx]
0x1800170f7  mov     r9, [rax+8]
0x1800170fb  mov     [r9], rcx
0x1800170fe  mov     r8, [rcx+8]
0x180017102  mov     [r8], r10
0x180017105  mov     rdx, [r10+8]
0x180017109  mov     [rdx], rax
0x18001710c  mov     [r10+8], r8
0x180017110  mov     [rcx+8], r9
0x180017114  mov     [rax+8], rdx
0x180017118  jmp     short loc_18001713D
0x18001711a  mov     r9, [rax+8]
0x18001711e  mov     [r9], rcx
0x180017121  mov     r8, [rcx+8]
0x180017125  mov     [r8], rdx
0x180017128  mov     rdx, [rdi]
0x18001712b  mov     [rdx], rax
0x18001712e  mov     [rdi], r8
0x180017131  mov     [rcx+8], r9
0x180017135  mov     [rax+8], rdx
0x180017139  mov     [r11+r10*8], rax
0x18001713d  mov     rax, rcx
0x180017140  jmp     loc_18001704F
0x180017145  add     rsp, 28h
0x180017149  pop     r14
0x18001714b  pop     rdi
0x18001714c  pop     rsi
0x18001714d  pop     rbx
0x18001714e  retn
```
