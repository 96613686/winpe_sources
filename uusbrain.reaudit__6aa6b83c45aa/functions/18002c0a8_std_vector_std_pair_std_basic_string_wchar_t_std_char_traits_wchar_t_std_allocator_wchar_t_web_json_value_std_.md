# std::vector<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value>>>::_Emplace_reallocate<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value>>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> * const,std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> &&)

- ea: `0x18002c0a8`
- end: `0x18002c31b`
- name: `??$_Emplace_reallocate@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAU21@@Z`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002c324`

## callees

- `0x18001dc18`
- `0x1800293d4`
- `0x1800294f0`
- `0x18002be9c`
- `0x18002bfa8`
- `0x18002c0a8`

## pseudocode

```c
__int64 __fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(
        _QWORD *a1,
        _QWORD *a2,
        __int128 *a3)
{
  __int64 v6; // r14
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  __int64 v11; // r11
  __int64 v12; // r14
  __int64 v13; // r8
  __int128 v14; // xmm0
  __int64 v15; // rax
  _QWORD *v16; // r9
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  __int64 v19; // rax
  _QWORD *v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rcx
  _QWORD *v23; // r10
  __int64 v24; // rax
  _QWORD *v26; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 v27; // [rsp+30h] [rbp-58h]
  __int64 v28; // [rsp+38h] [rbp-50h]
  __int64 v29; // [rsp+40h] [rbp-48h]

  v6 = ((__int64)a2 - *a1) / 40;
  v7 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[1] - *a1) >> 3);
  if ( v7 == 0x666666666666666LL )
    std::vector<enum UusCapability>::_Xlength();
  v8 = v7 + 1;
  v9 = (0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[2] - *a1) >> 3)) >> 1;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[2] - *a1) >> 3) <= 0x666666666666666LL - v9 )
  {
    v10 = v7 + 1;
    if ( v9 - 0x3333333333333333LL * ((__int64)(a1[2] - *a1) >> 3) >= v8 )
      v10 = v9 - 0x3333333333333333LL * ((__int64)(a1[2] - *a1) >> 3);
    if ( v10 > 0x666666666666666LL )
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v10 = 0x666666666666666LL;
  }
  v26 = a1;
  v27 = v10;
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(40 * v10);
  v12 = v11 + 40 * v6;
  *(_OWORD *)v12 = 0;
  *(_QWORD *)(v12 + 16) = 0;
  *(_QWORD *)(v12 + 24) = 0;
  v13 = v12 + 40;
  v14 = *a3;
  v29 = v12 + 40;
  v28 = v12;
  *(_OWORD *)v12 = v14;
  *(_OWORD *)(v12 + 16) = a3[1];
  *((_QWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 3) = 7;
  *(_WORD *)a3 = 0;
  v15 = *((_QWORD *)a3 + 4);
  *((_QWORD *)a3 + 4) = 0;
  *(_QWORD *)(v12 + 32) = v15;
  v16 = (_QWORD *)a1[1];
  v17 = *a1;
  if ( a2 == v16 )
  {
    if ( (_QWORD *)v17 != v16 )
    {
      v18 = (_QWORD *)(v11 + 24);
      do
      {
        *(_OWORD *)(v18 - 3) = 0;
        *(v18 - 1) = 0;
        *v18 = 0;
        v18 += 5;
        *((_OWORD *)v18 - 4) = *(_OWORD *)v17;
        *((_OWORD *)v18 - 3) = *(_OWORD *)(v17 + 16);
        *(_QWORD *)(v17 + 16) = 0;
        *(_QWORD *)(v17 + 24) = 7;
        *(_WORD *)v17 = 0;
        v19 = *(_QWORD *)(v17 + 32);
        *(_QWORD *)(v17 + 32) = 0;
        v17 += 40;
        *(v18 - 4) = v19;
      }
      while ( (_QWORD *)v17 != v16 );
    }
  }
  else
  {
    if ( (_QWORD *)v17 != a2 )
    {
      v20 = (_QWORD *)(v11 + 24);
      do
      {
        *(_OWORD *)(v20 - 3) = 0;
        *(v20 - 1) = 0;
        *v20 = 0;
        v20 += 5;
        *((_OWORD *)v20 - 4) = *(_OWORD *)v17;
        *((_OWORD *)v20 - 3) = *(_OWORD *)(v17 + 16);
        *(_QWORD *)(v17 + 16) = 0;
        *(_QWORD *)(v17 + 24) = 7;
        *(_WORD *)v17 = 0;
        v21 = *(_QWORD *)(v17 + 32);
        *(_QWORD *)(v17 + 32) = 0;
        v17 += 40;
        *(v20 - 4) = v21;
      }
      while ( (_QWORD *)v17 != a2 );
    }
    v22 = (_QWORD *)a1[1];
    v28 = v11;
    if ( a2 != v22 )
    {
      v23 = a2 + 4;
      do
      {
        *(_OWORD *)v13 = 0;
        *(_QWORD *)(v13 + 16) = 0;
        *(_QWORD *)(v13 + 24) = 0;
        *(_OWORD *)v13 = *((_OWORD *)v23 - 2);
        v13 += 40;
        *(_OWORD *)(v13 - 24) = *((_OWORD *)v23 - 1);
        *(v23 - 2) = 0;
        *(v23 - 1) = 7;
        *((_WORD *)v23 - 16) = 0;
        v24 = *v23;
        *v23 = 0;
        v23 += 5;
        *(_QWORD *)(v13 - 8) = v24;
      }
      while ( v23 - 4 != v22 );
    }
  }
  std::vector<std::pair<std::wstring,web::json::value>>::_Change_array(a1, v11, v8, v10, v26, 0, v27, v28, v29);
  std::vector<std::pair<std::wstring,web::json::value>>::_Reallocation_guard::~_Reallocation_guard(&v26);
  return v12;
}

```

## disassembly

```asm
0x18002c0a8  mov     [rsp+arg_18], rbx
0x18002c0ad  push    rbp
0x18002c0ae  push    rsi
0x18002c0af  push    rdi
0x18002c0b0  push    r12
0x18002c0b2  push    r13
0x18002c0b4  push    r14
0x18002c0b6  push    r15
0x18002c0b8  sub     rsp, 50h
0x18002c0bc  mov     rsi, rcx
0x18002c0bf  mov     rdi, rdx
0x18002c0c2  mov     rcx, rdx
0x18002c0c5  mov     rax, 6666666666666667h
0x18002c0cf  mov     r15, r8
0x18002c0d2  mov     r8, 666666666666666h
0x18002c0dc  sub     rcx, [rsi]
0x18002c0df  imul    rcx
0x18002c0e2  mov     r14, rdx
0x18002c0e5  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18002c0ef  sar     r14, 4
0x18002c0f3  mov     rax, r14
0x18002c0f6  shr     rax, 3Fh
0x18002c0fa  add     r14, rax
0x18002c0fd  mov     rax, [rsi+8]
0x18002c101  sub     rax, [rsi]
0x18002c104  sar     rax, 3
0x18002c108  imul    rax, rdx
0x18002c10c  cmp     rax, r8
0x18002c10f  jz      loc_18002C30F
0x18002c115  mov     rcx, [rsi+10h]
0x18002c119  lea     rbp, [rax+1]
0x18002c11d  sub     rcx, [rsi]
0x18002c120  mov     rax, r8
0x18002c123  sar     rcx, 3
0x18002c127  imul    rcx, rdx
0x18002c12b  mov     rdx, rcx
0x18002c12e  shr     rdx, 1
0x18002c131  sub     rax, rdx
0x18002c134  cmp     rcx, rax
0x18002c137  jbe     loc_18002C211
0x18002c13d  mov     rbx, r8
0x18002c140  lea     rcx, [rbx+rbx*4]
0x18002c144  shl     rcx, 3
0x18002c148  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002c14d  xor     r12d, r12d
0x18002c150  mov     [rsp+88h+var_68], rsi
0x18002c155  lea     rcx, [r14+r14*4]
0x18002c159  mov     [rsp+88h+var_58], rbx
0x18002c15e  xorps   xmm0, xmm0
0x18002c161  mov     r11, rax
0x18002c164  lea     r14, [rax+rcx*8]
0x18002c168  movups  xmmword ptr [r14], xmm0
0x18002c16c  mov     [r14+10h], r12
0x18002c170  lea     r13d, [r12+7]
0x18002c175  mov     [r14+18h], r12
0x18002c179  lea     r8, [r14+28h]
0x18002c17d  movups  xmm0, xmmword ptr [r15]
0x18002c181  mov     [rsp+88h+var_48], r8
0x18002c186  mov     [rsp+88h+var_50], r14
0x18002c18b  movups  xmmword ptr [r14], xmm0
0x18002c18f  movups  xmm1, xmmword ptr [r15+10h]
0x18002c194  movups  xmmword ptr [r14+10h], xmm1
0x18002c199  mov     [r15+10h], r12
0x18002c19d  mov     [r15+18h], r13
0x18002c1a1  mov     [r15], r12w
0x18002c1a5  mov     rax, [r15+20h]
0x18002c1a9  mov     [r15+20h], r12
0x18002c1ad  mov     [r14+20h], rax
0x18002c1b1  mov     r9, [rsi+8]
0x18002c1b5  mov     rcx, [rsi]
0x18002c1b8  cmp     rdi, r9
0x18002c1bb  jnz     short loc_18002C22D
0x18002c1bd  cmp     rcx, r9
0x18002c1c0  jz      loc_18002C2D4
0x18002c1c6  lea     rdx, [r11+18h]
0x18002c1ca  xorps   xmm0, xmm0
0x18002c1cd  movups  xmmword ptr [rdx-18h], xmm0
0x18002c1d1  mov     [rdx-8], r12
0x18002c1d5  mov     [rdx], r12
0x18002c1d8  lea     rdx, [rdx+28h]
0x18002c1dc  movups  xmm0, xmmword ptr [rcx]
0x18002c1df  movups  xmmword ptr [rdx-40h], xmm0
0x18002c1e3  movups  xmm1, xmmword ptr [rcx+10h]
0x18002c1e7  movups  xmmword ptr [rdx-30h], xmm1
0x18002c1eb  mov     [rcx+10h], r12
0x18002c1ef  mov     [rcx+18h], r13
0x18002c1f3  mov     [rcx], r12w
0x18002c1f7  mov     rax, [rcx+20h]
0x18002c1fb  mov     [rcx+20h], r12
0x18002c1ff  add     rcx, 28h ; '('
0x18002c203  mov     [rdx-20h], rax
0x18002c207  cmp     rcx, r9
0x18002c20a  jnz     short loc_18002C1CA
0x18002c20c  jmp     loc_18002C2D4
0x18002c211  lea     rax, [rdx+rcx]
0x18002c215  mov     rbx, rbp
0x18002c218  cmp     rax, rbp
0x18002c21b  cmovnb  rbx, rax
0x18002c21f  cmp     rbx, r8
0x18002c222  ja      loc_18002C315
0x18002c228  jmp     loc_18002C140
0x18002c22d  cmp     rcx, rdi
0x18002c230  jz      short loc_18002C278
0x18002c232  lea     rdx, [r11+18h]
0x18002c236  xorps   xmm0, xmm0
0x18002c239  movups  xmmword ptr [rdx-18h], xmm0
0x18002c23d  mov     [rdx-8], r12
0x18002c241  mov     [rdx], r12
0x18002c244  lea     rdx, [rdx+28h]
0x18002c248  movups  xmm0, xmmword ptr [rcx]
0x18002c24b  movups  xmmword ptr [rdx-40h], xmm0
0x18002c24f  movups  xmm1, xmmword ptr [rcx+10h]
0x18002c253  movups  xmmword ptr [rdx-30h], xmm1
0x18002c257  mov     [rcx+10h], r12
0x18002c25b  mov     [rcx+18h], r13
0x18002c25f  mov     [rcx], r12w
0x18002c263  mov     rax, [rcx+20h]
0x18002c267  mov     [rcx+20h], r12
0x18002c26b  add     rcx, 28h ; '('
0x18002c26f  mov     [rdx-20h], rax
0x18002c273  cmp     rcx, rdi
0x18002c276  jnz     short loc_18002C236
0x18002c278  mov     rcx, [rsi+8]
0x18002c27c  mov     [rsp+88h+var_50], r11
0x18002c281  cmp     rdi, rcx
0x18002c284  jz      short loc_18002C2D4
0x18002c286  lea     r10, [rdi+20h]
0x18002c28a  xorps   xmm0, xmm0
0x18002c28d  movups  xmmword ptr [r8], xmm0
0x18002c291  mov     [r8+10h], r12
0x18002c295  mov     [r8+18h], r12
0x18002c299  movups  xmm0, xmmword ptr [r10-20h]
0x18002c29e  movups  xmmword ptr [r8], xmm0
0x18002c2a2  lea     r8, [r8+28h]
0x18002c2a6  movups  xmm1, xmmword ptr [r10-10h]
0x18002c2ab  movups  xmmword ptr [r8-18h], xmm1
0x18002c2b0  mov     [r10-10h], r12
0x18002c2b4  mov     [r10-8], r13
0x18002c2b8  mov     [r10-20h], r12w
0x18002c2bd  mov     rax, [r10]
0x18002c2c0  mov     [r10], r12
0x18002c2c3  lea     r10, [r10+28h]
0x18002c2c7  lea     rdx, [r10-20h]
0x18002c2cb  mov     [r8-8], rax
0x18002c2cf  cmp     rdx, rcx
0x18002c2d2  jnz     short loc_18002C28A
0x18002c2d4  mov     r9, rbx
0x18002c2d7  mov     [rsp+88h+var_60], r12
0x18002c2dc  mov     r8, rbp
0x18002c2df  mov     rdx, r11
0x18002c2e2  mov     rcx, rsi
0x18002c2e5  call    ?_Change_array@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAXQEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@2@_K1@Z; std::vector<std::pair<std::wstring,web::json::value>>::_Change_array(std::pair<std::wstring,web::json::value> * const,unsigned __int64,unsigned __int64)
0x18002c2ea  lea     rcx, [rsp+88h+var_68]
0x18002c2ef  call    ??1_Reallocation_guard@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,web::json::value>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002c2f4  mov     rbx, [rsp+88h+arg_18]
0x18002c2fc  mov     rax, r14
0x18002c2ff  add     rsp, 50h
0x18002c303  pop     r15
0x18002c305  pop     r14
0x18002c307  pop     r13
0x18002c309  pop     r12
0x18002c30b  pop     rdi
0x18002c30c  pop     rsi
0x18002c30d  pop     rbp
0x18002c30e  retn
0x18002c30f  call    ?_Xlength@?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@CAXXZ; std::vector<UusCapability>::_Xlength(void)
0x18002c315  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
