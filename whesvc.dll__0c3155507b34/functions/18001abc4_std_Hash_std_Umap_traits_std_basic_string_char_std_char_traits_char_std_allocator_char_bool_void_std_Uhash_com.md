# std::_Hash<std::_Umap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool (*)(void),std::_Uhash_compare<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::hash<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::equal_to<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bool (*)(void)>>,0>>::emplace<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bool (*)(void)> const &>(std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bool (*)(void)> const &)

- ea: `0x18001abc4`
- end: `0x18001ae02`
- name: `??$emplace@AEBU?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@1@@Z`
- size: `574`
- prototype: `__int64 __fastcall(__int64, __int64, size_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001f30`

## callees

- `0x180003be4`
- `0x180003d44`
- `0x18001a260`
- `0x18001abc4`
- `0x18001b084`
- `0x180023f78`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001ac56`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001ac56`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::emplace<std::pair<std::string const,bool (*)(void)> const &>(
        __int64 a1,
        __int64 a2,
        size_t *a3)
{
  size_t v5; // rdx
  __int64 v6; // rbp
  unsigned __int64 i; // rcx
  _QWORD *v8; // rdi
  __int64 v9; // r9
  unsigned __int64 v10; // rcx
  float v11; // xmm0_4
  unsigned __int64 v12; // rbx
  float v13; // xmm2_4
  float v14; // xmm0_4
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // r9
  __int128 v25; // [rsp+20h] [rbp-48h] BYREF
  __int64 *v26; // [rsp+30h] [rbp-38h] BYREF
  _QWORD *v27; // [rsp+38h] [rbp-30h]

  if ( a3[3] <= 0xF )
    v5 = (size_t)a3;
  else
    v5 = *a3;
  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < a3[2]; ++i )
    v6 = 0x100000001B3LL * (*(unsigned __int8 *)(v5 + i) ^ (unsigned __int64)v6);
  std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Find_last<std::string>(
    i,
    &v25,
    a3,
    v6);
  if ( !*((_QWORD *)&v25 + 1) )
  {
    if ( qword_180034E10 == 0x492492492492492LL )
      std::_Xlength_error("unordered_map/set too long");
    v26 = &qword_180034E08;
    v27 = 0;
    v8 = operator new(0x38u);
    v27 = v8;
    std::string::string(v8 + 2, a3);
    v8[6] = a3[4];
    v9 = qword_180034E10;
    v10 = qword_180034E10 + 1;
    if ( qword_180034E10 + 1 < 0 )
      v11 = (float)(int)(v10 & 1 | (v10 >> 1)) + (float)(int)(v10 & 1 | (v10 >> 1));
    else
      v11 = (float)(int)v10;
    v12 = qword_180034E38;
    if ( qword_180034E38 < 0 )
      v13 = (float)(qword_180034E38 & 1 | (unsigned int)((unsigned __int64)qword_180034E38 >> 1))
          + (float)(qword_180034E38 & 1 | (unsigned int)((unsigned __int64)qword_180034E38 >> 1));
    else
      v13 = (float)(int)qword_180034E38;
    if ( (float)(v11 / v13) > *(float *)&dword_180034E00 )
    {
      v14 = o_ceilf_0(v11 / *(float *)&dword_180034E00);
      v15 = 0;
      if ( v14 >= 9.223372e18 )
      {
        v14 = v14 - 9.223372e18;
        if ( v14 < 9.223372e18 )
          v15 = 0x8000000000000000uLL;
      }
      v16 = v15 + (unsigned int)(int)v14;
      v17 = 8;
      if ( v16 > 8 )
        v17 = v16;
      if ( v12 < v17 )
      {
        if ( v12 >= 0x200 || (v12 *= 8LL, v12 < v17) )
          v12 = v17;
      }
      std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Forced_rehash(
        v17,
        v12);
      v25 = *(_OWORD *)std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Find_last<std::string>(
                         v18,
                         &v26,
                         v8 + 2,
                         v6);
      v9 = qword_180034E10;
    }
    v19 = v25;
    v20 = *(_QWORD **)(v25 + 8);
    qword_180034E10 = v9 + 1;
    *v8 = v25;
    v8[1] = v20;
    *v20 = v8;
    *(_QWORD *)(v19 + 8) = v8;
    v21 = qword_180034E18;
    v22 = 2 * (v6 & qword_180034E30);
    v23 = *(_QWORD *)(qword_180034E18 + 16 * (v6 & qword_180034E30));
    if ( v23 == qword_180034E08 )
    {
      *(_QWORD *)(qword_180034E18 + 16 * (v6 & qword_180034E30)) = v8;
LABEL_32:
      *(_QWORD *)(v21 + 8 * v22 + 8) = v8;
      goto LABEL_33;
    }
    if ( v23 == v19 )
    {
      *(_QWORD *)(qword_180034E18 + 16 * (v6 & qword_180034E30)) = v8;
    }
    else if ( *(_QWORD **)(qword_180034E18 + 16 * (v6 & qword_180034E30) + 8) == v20 )
    {
      goto LABEL_32;
    }
LABEL_33:
    *(_QWORD *)a2 = v8;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v25 + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18001abc4  push    rbx
0x18001abc6  push    rbp
0x18001abc7  push    rsi
0x18001abc8  push    rdi
0x18001abc9  push    r14
0x18001abcb  sub     rsp, 40h
0x18001abcf  mov     rbx, r8
0x18001abd2  mov     rsi, rdx
0x18001abd5  cmp     qword ptr [r8+18h], 0Fh
0x18001abda  jbe     short loc_18001ABE1
0x18001abdc  mov     rdx, [r8]
0x18001abdf  jmp     short loc_18001ABE4
0x18001abe1  mov     rdx, rbx
0x18001abe4  mov     rbp, 0CBF29CE484222325h
0x18001abee  xor     edi, edi
0x18001abf0  mov     ecx, edi
0x18001abf2  cmp     [r8+10h], rdi
0x18001abf6  jbe     short loc_18001AC16
0x18001abf8  movzx   eax, byte ptr [rdx+rcx]
0x18001abfc  xor     rbp, rax
0x18001abff  mov     r8, 100000001B3h
0x18001ac09  imul    rbp, r8
0x18001ac0d  inc     rcx
0x18001ac10  cmp     rcx, [rbx+10h]
0x18001ac14  jb      short loc_18001ABF8
0x18001ac16  mov     r9, rbp
0x18001ac19  mov     r8, rbx
0x18001ac1c  lea     rdx, [rsp+68h+var_48]
0x18001ac21  call    ??$_Find_last@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Find_last<std::string>(std::string const &,unsigned __int64)
0x18001ac26  mov     rax, qword ptr [rsp+68h+var_48+8]
0x18001ac2b  test    rax, rax
0x18001ac2e  jz      short loc_18001AC3C
0x18001ac30  mov     [rsi], rax
0x18001ac33  mov     [rsi+8], dil
0x18001ac37  jmp     loc_18001ADF4
0x18001ac3c  mov     rax, 492492492492492h
0x18001ac46  cmp     cs:qword_180034E10, rax
0x18001ac4d  jnz     short loc_18001AC5D
0x18001ac4f  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18001ac56  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001ac5d  lea     rax, qword_180034E08
0x18001ac64  mov     [rsp+68h+var_38], rax
0x18001ac69  mov     [rsp+68h+var_30], rdi
0x18001ac6e  mov     ecx, 38h ; '8'; Size
0x18001ac73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ac78  mov     rdi, rax
0x18001ac7b  mov     [rsp+68h+var_30], rax
0x18001ac80  mov     rdx, rbx
0x18001ac83  lea     rcx, [rax+10h]
0x18001ac87  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18001ac8c  mov     rax, [rbx+20h]
0x18001ac90  mov     [rdi+30h], rax
0x18001ac94  mov     r9, cs:qword_180034E10
0x18001ac9b  lea     rcx, [r9+1]
0x18001ac9f  xorps   xmm0, xmm0
0x18001aca2  test    rcx, rcx
0x18001aca5  js      short loc_18001ACAE
0x18001aca7  cvtsi2ss xmm0, rcx
0x18001acac  jmp     short loc_18001ACC3
0x18001acae  mov     rax, rcx
0x18001acb1  shr     rax, 1
0x18001acb4  and     ecx, 1
0x18001acb7  or      rax, rcx
0x18001acba  cvtsi2ss xmm0, rax
0x18001acbf  addss   xmm0, xmm0
0x18001acc3  mov     rbx, cs:qword_180034E38
0x18001acca  xorps   xmm2, xmm2
0x18001accd  test    rbx, rbx
0x18001acd0  js      short loc_18001ACD9
0x18001acd2  cvtsi2ss xmm2, rbx
0x18001acd7  jmp     short loc_18001ACF1
0x18001acd9  mov     rcx, rbx
0x18001acdc  shr     rcx, 1
0x18001acdf  mov     rax, rbx
0x18001ace2  and     eax, 1
0x18001ace5  or      rcx, rax
0x18001ace8  cvtsi2ss xmm2, rcx
0x18001aced  addss   xmm2, xmm2
0x18001acf1  movaps  xmm1, xmm0
0x18001acf4  divss   xmm1, xmm2
0x18001acf8  movss   xmm3, cs:dword_180034E00
0x18001ad00  comiss  xmm1, xmm3
0x18001ad03  jbe     loc_18001AD8E
0x18001ad09  divss   xmm0, xmm3; X
0x18001ad0d  call    _o_ceilf_0
0x18001ad12  xor     ecx, ecx
0x18001ad14  movss   xmm1, cs:__real@5f000000
0x18001ad1c  comiss  xmm0, xmm1
0x18001ad1f  jb      short loc_18001AD37
0x18001ad21  subss   xmm0, xmm1
0x18001ad25  comiss  xmm0, xmm1
0x18001ad28  jnb     short loc_18001AD37
0x18001ad2a  mov     rax, 8000000000000000h
0x18001ad34  mov     rcx, rax
0x18001ad37  cvttss2si rax, xmm0
0x18001ad3c  add     rax, rcx
0x18001ad3f  mov     ecx, 8
0x18001ad44  cmp     rax, rcx
0x18001ad47  cmova   rcx, rax
0x18001ad4b  cmp     rbx, rcx
0x18001ad4e  jnb     short loc_18001AD65
0x18001ad50  cmp     rbx, 200h
0x18001ad57  jnb     short loc_18001AD62
0x18001ad59  shl     rbx, 3
0x18001ad5d  cmp     rbx, rcx
0x18001ad60  jnb     short loc_18001AD65
0x18001ad62  mov     rbx, rcx
0x18001ad65  mov     rdx, rbx
0x18001ad68  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Forced_rehash(unsigned __int64)
0x18001ad6d  mov     r9, rbp
0x18001ad70  lea     r8, [rdi+10h]
0x18001ad74  lea     rdx, [rsp+68h+var_38]
0x18001ad79  call    ??$_Find_last@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Find_last<std::string>(std::string const &,unsigned __int64)
0x18001ad7e  movups  xmm0, xmmword ptr [rax]
0x18001ad81  movdqu  [rsp+68h+var_48], xmm0
0x18001ad87  mov     r9, cs:qword_180034E10
0x18001ad8e  mov     rdx, qword ptr [rsp+68h+var_48]
0x18001ad93  mov     r8, [rdx+8]
0x18001ad97  inc     r9
0x18001ad9a  mov     cs:qword_180034E10, r9
0x18001ada1  mov     [rdi], rdx
0x18001ada4  mov     [rdi+8], r8
0x18001ada8  mov     [r8], rdi
0x18001adab  mov     [rdx+8], rdi
0x18001adaf  mov     rcx, cs:qword_180034E18
0x18001adb6  mov     rax, cs:qword_180034E30
0x18001adbd  and     rax, rbp
0x18001adc0  add     rax, rax
0x18001adc3  mov     r9, [rcx+rax*8]
0x18001adc7  cmp     r9, cs:qword_180034E08
0x18001adce  jnz     short loc_18001ADD6
0x18001add0  mov     [rcx+rax*8], rdi
0x18001add4  jmp     short loc_18001ADE8
0x18001add6  cmp     r9, rdx
0x18001add9  jnz     short loc_18001ADE1
0x18001addb  mov     [rcx+rax*8], rdi
0x18001addf  jmp     short loc_18001ADED
0x18001ade1  cmp     [rcx+rax*8+8], r8
0x18001ade6  jnz     short loc_18001ADED
0x18001ade8  mov     [rcx+rax*8+8], rdi
0x18001aded  mov     [rsi], rdi
0x18001adf0  mov     byte ptr [rsi+8], 1
0x18001adf4  mov     rax, rsi
0x18001adf7  add     rsp, 40h
0x18001adfb  pop     r14
0x18001adfd  pop     rdi
0x18001adfe  pop     rsi
0x18001adff  pop     rbp
0x18001ae00  pop     rbx
0x18001ae01  retn
```
