# CLI::detail::checkParentSegments(std::vector<CLI::ConfigItem,std::allocator<CLI::ConfigItem>> &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,char)

- ea: `0x140029950`
- end: `0x140029eb1`
- name: `?checkParentSegments@detail@CLI@@YAXAEAV?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@D@Z`
- size: `1377`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x14002df60`

## callees

- `0x1400083f0`
- `0x140008a50`
- `0x14000b0a0`
- `0x14000f7e0`
- `0x14000fab8`
- `0x140010608`
- `0x140010e40`
- `0x1400112e0`
- `0x140011f20`
- `0x14001ad90`
- `0x140029950`
- `0x140030720`
- `0x1400455d0`
- `0x140052264`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CLI::detail::checkParentSegments(_QWORD *a1, __int64 a2, unsigned __int8 a3)
{
  __int64 v4; // rdi
  const void *v5; // rcx
  __int64 v6; // rcx
  char *v7; // r14
  unsigned __int64 v8; // r15
  __int64 v9; // rdi
  __int64 v10; // rdi
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rax
  __int64 v14; // r13
  __int64 v15; // r15
  unsigned __int64 v16; // r12
  unsigned __int64 v17; // rdi
  char *v18; // rdx
  _QWORD *v19; // rcx
  char *v20; // r9
  const void *v21; // rax
  size_t v22; // r8
  __int64 v23; // rdi
  __int64 v24; // rdi
  __int64 v25; // rdx
  unsigned __int64 v26; // rdi
  __int64 v27; // rdx
  __int64 v28; // rdx
  char *v29; // rbx
  char *v30; // rdi
  _BYTE *v31; // rcx
  void *v32; // rcx
  void *v33[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v34; // [rsp+30h] [rbp-40h]
  __int64 v35; // [rsp+38h] [rbp-38h]
  void *v36[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v37; // [rsp+50h] [rbp-20h]
  unsigned __int64 v38; // [rsp+58h] [rbp-18h]

  *(_OWORD *)v36 = 0;
  v37 = 0;
  v38 = 15;
  LOBYTE(v36[0]) = 0;
  CLI::detail::generate_parents(v33, a2, v36, a3);
  v4 = a1[1];
  if ( *a1 != v4
    && (*(_QWORD *)(v4 - 32) <= 0xFu ? (v5 = (const void *)(v4 - 56)) : (v5 = *(const void **)(v4 - 56)),
        *(_QWORD *)(v4 - 40) == 2 && !memcmp_0(v5, "--", 2u)) )
  {
    v6 = v4;
    v7 = (char *)v33[0];
    v8 = 2;
    if ( (unsigned __int64)(((char *)v33[1] - (char *)v33[0]) >> 5) > 1 )
      v8 = ((char *)v33[1] - (char *)v33[0]) >> 5;
    if ( (__int64)(*(_QWORD *)(v4 - 72) - *(_QWORD *)(v4 - 80)) >> 5 >= v8 )
    {
      do
      {
        v9 = a1[1];
        if ( v9 == a1[2] )
        {
          std::vector<CLI::ConfigItem>::_Emplace_reallocate<CLI::ConfigItem const &>(a1, a1[1], v9 - 80);
        }
        else
        {
          v35 = a1[1];
          std::vector<std::string>::vector<std::string>(v9, v9 - 80);
          std::string::string(v9 + 24, v9 - 56);
          std::vector<std::string>::vector<std::string>(v9 + 56, v9 - 24);
          a1[1] += 80LL;
        }
        v10 = a1[1];
        std::string::_Tidy_deallocate((void *)(*(_QWORD *)(v10 - 72) - 32LL));
        *(_QWORD *)(v10 - 72) -= 32LL;
        v6 = a1[1];
      }
      while ( (__int64)(*(_QWORD *)(v6 - 72) - *(_QWORD *)(v6 - 80)) >> 5 >= v8 );
      v7 = (char *)v33[0];
    }
    v11 = ((char *)v33[1] - (char *)v7) >> 5;
    if ( v11 > 1 )
    {
      v12 = 0;
      v13 = v11 - 1;
      v14 = v6 - 80;
      v15 = *(_QWORD *)(v6 - 80);
      v16 = (*(_QWORD *)(v6 - 80 + 8) - v15) >> 5;
      v17 = v16;
      if ( v13 < v16 )
        v17 = v13;
      if ( v17 )
      {
        while ( 1 )
        {
          v18 = &v7[32 * v12];
          v19 = (_QWORD *)(32 * v12 + v15);
          v20 = *((_QWORD *)v18 + 3) <= 0xFu ? &v7[32 * v12] : *(char **)v18;
          v21 = (const void *)(v19[3] <= 0xFu ? 32 * v12 + v15 : *v19);
          v22 = v19[2];
          if ( v22 != *((_QWORD *)v18 + 2) || v22 && memcmp_0(v21, v20, v22) )
            break;
          if ( ++v12 >= v17 )
            goto LABEL_29;
        }
      }
      else
      {
LABEL_29:
        if ( v12 == v17 )
        {
          std::vector<std::string>::_Tidy(v14 + 56);
          std::string::_Tidy_deallocate((void *)(v14 + 24));
          std::vector<std::string>::_Tidy(v14);
          a1[1] -= 80LL;
          goto LABEL_36;
        }
      }
      v23 = a1[1];
      if ( v16 <= v12 + 1 )
        goto LABEL_37;
      do
      {
        if ( v23 == a1[2] )
        {
          std::vector<CLI::ConfigItem>::_Emplace_reallocate<CLI::ConfigItem const &>(a1, v23, v23 - 80);
        }
        else
        {
          v35 = v23;
          std::vector<std::string>::vector<std::string>(v23, v23 - 80);
          std::string::string(v23 + 24, v23 - 56);
          std::vector<std::string>::vector<std::string>(v23 + 56, v23 - 24);
          a1[1] += 80LL;
        }
        v24 = a1[1];
        std::string::_Tidy_deallocate((void *)(*(_QWORD *)(v24 - 72) - 32LL));
        *(_QWORD *)(v24 - 72) -= 32LL;
        v23 = a1[1];
      }
      while ( (__int64)(*(_QWORD *)(v23 - 72) - *(_QWORD *)(v23 - 80)) >> 5 > v12 + 1 );
LABEL_36:
      v7 = (char *)v33[0];
LABEL_37:
      if ( v12 < (((char *)v33[1] - (char *)v7) >> 5) - 1 )
      {
        do
        {
          v25 = a1[1];
          if ( v25 == a1[2] )
          {
            std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(a1);
          }
          else
          {
            *(_QWORD *)v25 = 0;
            *(_QWORD *)(v25 + 8) = 0;
            *(_QWORD *)(v25 + 16) = 0;
            *(_OWORD *)(v25 + 24) = 0;
            *(_QWORD *)(v25 + 40) = 0;
            *(_QWORD *)(v25 + 48) = 15;
            *(_BYTE *)(v25 + 24) = 0;
            *(_QWORD *)(v25 + 56) = 0;
            *(_QWORD *)(v25 + 64) = 0;
            *(_QWORD *)(v25 + 72) = 0;
            a1[1] += 80LL;
          }
          std::vector<std::string>::_Assign_counted_range<std::string const *>(
            a1[1] - 80LL,
            v33[0],
            (__int64)(32 * v12 + 32) >> 5);
          std::string::_Assign<char>(a1[1] - 56LL, "++", 2);
          ++v12;
        }
        while ( v12 < (((char *)v33[1] - (char *)v33[0]) >> 5) - 1 );
      }
    }
  }
  else if ( (unsigned __int64)(((char *)v33[1] - (char *)v33[0]) >> 5) > 1 )
  {
    v26 = 0;
    do
    {
      v27 = a1[1];
      if ( v27 == a1[2] )
      {
        std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(a1);
      }
      else
      {
        *(_QWORD *)v27 = 0;
        *(_QWORD *)(v27 + 8) = 0;
        *(_QWORD *)(v27 + 16) = 0;
        *(_OWORD *)(v27 + 24) = 0;
        *(_QWORD *)(v27 + 40) = 0;
        *(_QWORD *)(v27 + 48) = 15;
        *(_BYTE *)(v27 + 24) = 0;
        *(_QWORD *)(v27 + 56) = 0;
        *(_QWORD *)(v27 + 64) = 0;
        *(_QWORD *)(v27 + 72) = 0;
        a1[1] += 80LL;
      }
      std::vector<std::string>::_Assign_counted_range<std::string const *>(
        a1[1] - 80LL,
        v33[0],
        (__int64)(32 * v26 + 32) >> 5);
      std::string::_Assign<char>(a1[1] - 56LL, "++", 2);
      ++v26;
    }
    while ( v26 < (((char *)v33[1] - (char *)v33[0]) >> 5) - 1 );
  }
  v28 = a1[1];
  if ( v28 == a1[2] )
  {
    std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(a1);
  }
  else
  {
    *(_QWORD *)v28 = 0;
    *(_QWORD *)(v28 + 8) = 0;
    *(_QWORD *)(v28 + 16) = 0;
    *(_OWORD *)(v28 + 24) = 0;
    *(_QWORD *)(v28 + 40) = 0;
    *(_QWORD *)(v28 + 48) = 15;
    *(_BYTE *)(v28 + 24) = 0;
    *(_QWORD *)(v28 + 56) = 0;
    *(_QWORD *)(v28 + 64) = 0;
    *(_QWORD *)(v28 + 72) = 0;
    a1[1] += 80LL;
  }
  std::vector<std::string>::operator=(a1[1] - 80LL, v33);
  std::string::_Assign<char>(a1[1] - 56LL, "++", 2);
  v29 = (char *)v33[0];
  if ( v33[0] )
  {
    v30 = (char *)v33[1];
    if ( v33[0] != v33[1] )
    {
      do
      {
        std::string::_Tidy_deallocate(v29);
        v29 += 32;
      }
      while ( v29 != v30 );
      v29 = (char *)v33[0];
    }
    if ( ((v34 - (_QWORD)v29) & 0xFFFFFFFFFFFFFFE0uLL) < 0x1000 )
    {
      v31 = v29;
    }
    else
    {
      v31 = (_BYTE *)*((_QWORD *)v29 - 1);
      if ( (unsigned __int64)(v29 - v31 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v31);
    *(_OWORD *)v33 = 0;
    v34 = 0;
  }
  if ( v38 > 0xF )
  {
    if ( v38 + 1 < 0x1000 )
    {
      v32 = v36[0];
    }
    else
    {
      v32 = (void *)*((_QWORD *)v36[0] - 1);
      if ( (unsigned __int64)((char *)v36[0] - (char *)v32 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v32);
  }
}

```

## disassembly

```asm
0x140029950  mov     [rsp-38h+arg_18], rbx
0x140029955  push    rbp
0x140029956  push    rsi
0x140029957  push    rdi
0x140029958  push    r12
0x14002995a  push    r13
0x14002995c  push    r14
0x14002995e  push    r15
0x140029960  mov     rbp, rsp
0x140029963  sub     rsp, 70h
0x140029967  mov     rax, cs:__security_cookie
0x14002996e  xor     rax, rsp
0x140029971  mov     [rbp+var_10], rax
0x140029975  mov     rbx, rcx
0x140029978  xorps   xmm0, xmm0
0x14002997b  movups  xmmword ptr [rbp+var_30], xmm0
0x14002997f  xor     r12d, r12d
0x140029982  mov     [rbp+var_20], r12
0x140029986  mov     [rbp+var_18], 0Fh
0x14002998e  mov     byte ptr [rbp+var_30], r12b
0x140029992  movzx   r9d, r8b
0x140029996  lea     r8, [rbp+var_30]
0x14002999a  lea     rcx, [rbp+var_50]
0x14002999e  call    ?generate_parents@detail@CLI@@YA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@AEAV54@D@Z; CLI::detail::generate_parents(std::string const &,std::string &,char)
0x1400299a3  nop
0x1400299a4  mov     rdi, [rbx+8]
0x1400299a8  cmp     [rbx], rdi
0x1400299ab  jz      loc_140029CAD
0x1400299b1  cmp     qword ptr [rdi-20h], 0Fh
0x1400299b6  jbe     short loc_1400299BE
0x1400299b8  mov     rcx, [rdi-38h]
0x1400299bc  jmp     short loc_1400299C2
0x1400299be  lea     rcx, [rdi-38h]; Buf1
0x1400299c2  mov     r8, [rdi-28h]; Size
0x1400299c6  cmp     r8, 2
0x1400299ca  jnz     loc_140029CAD
0x1400299d0  lea     rdx, asc_14006CCD4; "--"
0x1400299d7  call    memcmp_0
0x1400299dc  test    eax, eax
0x1400299de  jnz     loc_140029CAD
0x1400299e4  mov     rcx, rdi
0x1400299e7  mov     rax, [rbp+var_50+8]
0x1400299eb  mov     r14, [rbp+var_50]
0x1400299ef  sub     rax, r14
0x1400299f2  sar     rax, 5
0x1400299f6  mov     r15d, 2
0x1400299fc  cmp     rax, 1
0x140029a00  cmova   r15, rax
0x140029a04  mov     rax, [rdi-48h]
0x140029a08  sub     rax, [rdi-50h]
0x140029a0c  sar     rax, 5
0x140029a10  cmp     rax, r15
0x140029a13  jb      loc_140029A9C
0x140029a19  nop     dword ptr [rax+00000000h]
0x140029a20  mov     rdi, [rbx+8]
0x140029a24  cmp     rdi, [rbx+10h]
0x140029a28  jz      short loc_140029A5E
0x140029a2a  mov     [rbp+var_38], rdi
0x140029a2e  lea     rdx, [rdi-50h]
0x140029a32  mov     rcx, rdi
0x140029a35  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::string>::vector<std::string>(std::vector<std::string> const &)
0x140029a3a  nop
0x140029a3b  lea     rdx, [rdi-38h]
0x140029a3f  lea     rcx, [rdi+18h]
0x140029a43  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140029a48  nop
0x140029a49  lea     rdx, [rdi-18h]
0x140029a4d  lea     rcx, [rdi+38h]
0x140029a51  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::string>::vector<std::string>(std::vector<std::string> const &)
0x140029a56  nop
0x140029a57  add     qword ptr [rbx+8], 50h ; 'P'
0x140029a5c  jmp     short loc_140029A6D
0x140029a5e  lea     r8, [rdi-50h]
0x140029a62  mov     rdx, rdi
0x140029a65  mov     rcx, rbx
0x140029a68  call    ??$_Emplace_reallocate@AEBUConfigItem@CLI@@@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAPEAUConfigItem@CLI@@QEAU23@AEBU23@@Z; std::vector<CLI::ConfigItem>::_Emplace_reallocate<CLI::ConfigItem const &>(CLI::ConfigItem * const,CLI::ConfigItem const &)
0x140029a6d  mov     rdi, [rbx+8]
0x140029a71  mov     rcx, [rdi-48h]
0x140029a75  sub     rcx, 20h ; ' '; void *
0x140029a79  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140029a7e  add     qword ptr [rdi-48h], 0FFFFFFFFFFFFFFE0h
0x140029a83  mov     rcx, [rbx+8]
0x140029a87  mov     rax, [rcx-48h]
0x140029a8b  sub     rax, [rcx-50h]
0x140029a8f  sar     rax, 5
0x140029a93  cmp     rax, r15
0x140029a96  jnb     short loc_140029A20
0x140029a98  mov     r14, [rbp+var_50]
0x140029a9c  mov     rax, [rbp+var_50+8]
0x140029aa0  sub     rax, r14
0x140029aa3  sar     rax, 5
0x140029aa7  cmp     rax, 1
0x140029aab  jbe     loc_140029D6D
0x140029ab1  mov     rsi, r12
0x140029ab4  dec     rax
0x140029ab7  lea     r13, [rcx-50h]
0x140029abb  mov     r15, [r13+0]
0x140029abf  mov     r12, [r13+8]
0x140029ac3  sub     r12, r15
0x140029ac6  sar     r12, 5
0x140029aca  mov     rdi, r12
0x140029acd  cmp     rax, r12
0x140029ad0  cmovb   rdi, rax
0x140029ad4  test    rdi, rdi
0x140029ad7  jz      short loc_140029B33
0x140029ad9  nop     dword ptr [rax+00000000h]
0x140029ae0  mov     rax, rsi
0x140029ae3  shl     rax, 5
0x140029ae7  lea     rdx, [r14+rax]
0x140029aeb  lea     rcx, [rax+r15]
0x140029aef  cmp     qword ptr [rdx+18h], 0Fh
0x140029af4  jbe     short loc_140029AFB
0x140029af6  mov     r9, [rdx]
0x140029af9  jmp     short loc_140029AFE
0x140029afb  mov     r9, rdx
0x140029afe  cmp     qword ptr [rcx+18h], 0Fh
0x140029b03  jbe     short loc_140029B0A
0x140029b05  mov     rax, [rcx]
0x140029b08  jmp     short loc_140029B0D
0x140029b0a  mov     rax, rcx
0x140029b0d  mov     r8, [rcx+10h]; Size
0x140029b11  cmp     r8, [rdx+10h]
0x140029b15  jnz     short loc_140029B5C
0x140029b17  test    r8, r8
0x140029b1a  jz      short loc_140029B2B
0x140029b1c  mov     rdx, r9; Buf2
0x140029b1f  mov     rcx, rax; Buf1
0x140029b22  call    memcmp_0
0x140029b27  test    eax, eax
0x140029b29  jnz     short loc_140029B5C
0x140029b2b  inc     rsi
0x140029b2e  cmp     rsi, rdi
0x140029b31  jb      short loc_140029AE0
0x140029b33  cmp     rsi, rdi
0x140029b36  jnz     short loc_140029B5C
0x140029b38  lea     rcx, [r13+38h]
0x140029b3c  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x140029b41  lea     rcx, [r13+18h]; void *
0x140029b45  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140029b4a  mov     rcx, r13
0x140029b4d  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x140029b52  add     qword ptr [rbx+8], 0FFFFFFFFFFFFFFB0h
0x140029b57  jmp     loc_140029BE4
0x140029b5c  mov     rdi, [rbx+8]
0x140029b60  lea     r15, [rsi+1]
0x140029b64  cmp     r12, r15
0x140029b67  jbe     short loc_140029BE8
0x140029b69  nop     dword ptr [rax+00000000h]
0x140029b70  cmp     rdi, [rbx+10h]
0x140029b74  jz      short loc_140029BAA
0x140029b76  mov     [rbp+var_38], rdi
0x140029b7a  lea     rdx, [rdi-50h]
0x140029b7e  mov     rcx, rdi
0x140029b81  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::string>::vector<std::string>(std::vector<std::string> const &)
0x140029b86  nop
0x140029b87  lea     rdx, [rdi-38h]
0x140029b8b  lea     rcx, [rdi+18h]
0x140029b8f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140029b94  nop
0x140029b95  lea     rdx, [rdi-18h]
0x140029b99  lea     rcx, [rdi+38h]
0x140029b9d  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::string>::vector<std::string>(std::vector<std::string> const &)
0x140029ba2  nop
0x140029ba3  add     qword ptr [rbx+8], 50h ; 'P'
0x140029ba8  jmp     short loc_140029BB9
0x140029baa  lea     r8, [rdi-50h]
0x140029bae  mov     rdx, rdi
0x140029bb1  mov     rcx, rbx
0x140029bb4  call    ??$_Emplace_reallocate@AEBUConfigItem@CLI@@@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAPEAUConfigItem@CLI@@QEAU23@AEBU23@@Z; std::vector<CLI::ConfigItem>::_Emplace_reallocate<CLI::ConfigItem const &>(CLI::ConfigItem * const,CLI::ConfigItem const &)
0x140029bb9  mov     rdi, [rbx+8]
0x140029bbd  mov     rcx, [rdi-48h]
0x140029bc1  sub     rcx, 20h ; ' '; void *
0x140029bc5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140029bca  add     qword ptr [rdi-48h], 0FFFFFFFFFFFFFFE0h
0x140029bcf  mov     rdi, [rbx+8]
0x140029bd3  mov     rax, [rdi-48h]
0x140029bd7  sub     rax, [rdi-50h]
0x140029bdb  sar     rax, 5
0x140029bdf  cmp     rax, r15
0x140029be2  ja      short loc_140029B70
0x140029be4  mov     r14, [rbp+var_50]
0x140029be8  mov     rax, [rbp+var_50+8]
0x140029bec  sub     rax, r14
0x140029bef  sar     rax, 5
0x140029bf3  dec     rax
0x140029bf6  cmp     rsi, rax
0x140029bf9  jnb     loc_140029D6A
0x140029bff  nop
0x140029c00  mov     rdx, [rbx+8]
0x140029c04  cmp     rdx, [rbx+10h]
0x140029c08  jz      short loc_140029C42
0x140029c0a  xor     r12d, r12d
0x140029c0d  mov     [rdx], r12
0x140029c10  mov     [rdx+8], r12
0x140029c14  mov     [rdx+10h], r12
0x140029c18  xorps   xmm0, xmm0
0x140029c1b  movups  xmmword ptr [rdx+18h], xmm0
0x140029c1f  mov     [rdx+28h], r12
0x140029c23  mov     qword ptr [rdx+30h], 0Fh
0x140029c2b  mov     [rdx+18h], r12b
0x140029c2f  mov     [rdx+38h], r12
0x140029c33  mov     [rdx+40h], r12
0x140029c37  mov     [rdx+48h], r12
0x140029c3b  add     qword ptr [rbx+8], 50h ; 'P'
0x140029c40  jmp     short loc_140029C4D
0x140029c42  mov     rcx, rbx
0x140029c45  call    ??$_Emplace_reallocate@$$V@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAPEAUConfigItem@CLI@@QEAU23@@Z; std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(CLI::ConfigItem * const)
0x140029c4a  xor     r12d, r12d
0x140029c4d  mov     rdx, [rbp+var_50]
0x140029c51  mov     rax, rsi
0x140029c54  shl     rax, 5
0x140029c58  lea     r8, [rdx+20h]
0x140029c5c  add     r8, rax
0x140029c5f  sub     r8, rdx
0x140029c62  sar     r8, 5
0x140029c66  mov     rcx, [rbx+8]
0x140029c6a  sub     rcx, 50h ; 'P'
0x140029c6e  call    ??$_Assign_counted_range@PEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXPEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K@Z; std::vector<std::string>::_Assign_counted_range<std::string const *>(std::string const *,unsigned __int64)
0x140029c73  mov     rcx, [rbx+8]
0x140029c77  sub     rcx, 38h ; '8'
0x140029c7b  mov     r8d, 2
0x140029c81  lea     rdx, asc_14006CF78; "++"
0x140029c88  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x140029c8d  inc     rsi
0x140029c90  mov     rax, [rbp+var_50+8]
0x140029c94  sub     rax, [rbp+var_50]
0x140029c98  sar     rax, 5
0x140029c9c  dec     rax
0x140029c9f  cmp     rsi, rax
0x140029ca2  jb      loc_140029C00
0x140029ca8  jmp     loc_140029D6D
0x140029cad  mov     rax, [rbp+var_50+8]
0x140029cb1  sub     rax, [rbp+var_50]
0x140029cb5  sar     rax, 5
0x140029cb9  cmp     rax, 1
0x140029cbd  jbe     loc_140029D6D
0x140029cc3  mov     rdi, r12
0x140029cc6  mov     rdx, [rbx+8]
0x140029cca  cmp     rdx, [rbx+10h]
0x140029cce  jz      short loc_140029D05
0x140029cd0  mov     [rdx], r12
0x140029cd3  mov     [rdx+8], r12
0x140029cd7  mov     [rdx+10h], r12
0x140029cdb  xorps   xmm0, xmm0
0x140029cde  movups  xmmword ptr [rdx+18h], xmm0
0x140029ce2  mov     [rdx+28h], r12
0x140029ce6  mov     qword ptr [rdx+30h], 0Fh
0x140029cee  mov     byte ptr [rdx+18h], 0
0x140029cf2  mov     [rdx+38h], r12
0x140029cf6  mov     [rdx+40h], r12
0x140029cfa  mov     [rdx+48h], r12
0x140029cfe  add     qword ptr [rbx+8], 50h ; 'P'
0x140029d03  jmp     short loc_140029D0D
0x140029d05  mov     rcx, rbx
0x140029d08  call    ??$_Emplace_reallocate@$$V@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAPEAUConfigItem@CLI@@QEAU23@@Z; std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(CLI::ConfigItem * const)
0x140029d0d  mov     rdx, [rbp+var_50]
0x140029d11  mov     rax, rdi
0x140029d14  shl     rax, 5
0x140029d18  lea     r8, [rdx+20h]
0x140029d1c  add     r8, rax
0x140029d1f  sub     r8, rdx
0x140029d22  sar     r8, 5
0x140029d26  mov     rcx, [rbx+8]
0x140029d2a  sub     rcx, 50h ; 'P'
0x140029d2e  call    ??$_Assign_counted_range@PEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXPEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K@Z; std::vector<std::string>::_Assign_counted_range<std::string const *>(std::string const *,unsigned __int64)
0x140029d33  mov     rcx, [rbx+8]
0x140029d37  sub     rcx, 38h ; '8'
0x140029d3b  mov     r8d, 2
0x140029d41  lea     rdx, asc_14006CF78; "++"
0x140029d48  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x140029d4d  inc     rdi
0x140029d50  mov     rax, [rbp+var_50+8]
0x140029d54  sub     rax, [rbp+var_50]
0x140029d58  sar     rax, 5
0x140029d5c  dec     rax
0x140029d5f  cmp     rdi, rax
0x140029d62  jb      loc_140029CC6
0x140029d68  jmp     short loc_140029D6D
0x140029d6a  xor     r12d, r12d
0x140029d6d  mov     rdx, [rbx+8]
0x140029d71  cmp     rdx, [rbx+10h]
0x140029d75  jz      short loc_140029DAC
0x140029d77  mov     [rdx], r12
0x140029d7a  mov     [rdx+8], r12
0x140029d7e  mov     [rdx+10h], r12
0x140029d82  xorps   xmm0, xmm0
0x140029d85  movups  xmmword ptr [rdx+18h], xmm0
0x140029d89  mov     [rdx+28h], r12
0x140029d8d  mov     qword ptr [rdx+30h], 0Fh
0x140029d95  mov     byte ptr [rdx+18h], 0
0x140029d99  mov     [rdx+38h], r12
0x140029d9d  mov     [rdx+40h], r12
0x140029da1  mov     [rdx+48h], r12
0x140029da5  add     qword ptr [rbx+8], 50h ; 'P'
0x140029daa  jmp     short loc_140029DB4
0x140029dac  mov     rcx, rbx
0x140029daf  call    ??$_Emplace_reallocate@$$V@?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAAPEAUConfigItem@CLI@@QEAU23@@Z; std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(CLI::ConfigItem * const)
0x140029db4  mov     rcx, [rbx+8]
0x140029db8  sub     rcx, 50h ; 'P'
0x140029dbc  lea     rdx, [rbp+var_50]
  ... truncated ...
```
