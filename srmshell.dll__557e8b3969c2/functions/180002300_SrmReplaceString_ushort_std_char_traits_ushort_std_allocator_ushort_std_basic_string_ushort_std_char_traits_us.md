# SrmReplaceString<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ushort const *,ushort const *)

- ea: `0x180002300`
- end: `0x180002652`
- name: `??$SrmReplaceString@GU?$char_traits@G@std@@V?$allocator@G@2@@@YA_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1@Z`
- size: `850`
- prototype: `__int64 __fastcall(char *Src, char *, char *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b95c`
- `0x18000ce98`
- `0x18000d880`

## callees

- `0x180002300`
- `0x18000ff54`
- `0x180010360`
- `0x180010390`
- `0x180010958`
- `0x18001b3d6`
- `0x18001b3e2`

## pseudocode

```c
__int64 __fastcall SrmReplaceString<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
        char *Src,
        char *a2,
        char *a3)
{
  unsigned __int64 v3; // r14
  char *v4; // rsi
  unsigned __int64 v5; // rdx
  char *v7; // rbx
  __int64 v8; // rax
  unsigned __int64 *v9; // rbp
  unsigned __int64 v10; // rdi
  __int64 v11; // r9
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rdx
  __int64 v14; // rdx
  char *v15; // rax
  char *v16; // r11
  __int64 v17; // rax
  char *i; // rdi
  unsigned __int64 v20; // r10
  char *v21; // r9
  char *v22; // rax
  __int64 v23; // rcx
  char *v24; // rax
  _QWORD *v25; // rcx
  char *v26; // rcx
  unsigned __int64 v27; // r15
  unsigned __int64 v28; // r12
  unsigned __int64 v29; // r15
  unsigned __int64 v30; // r15
  _QWORD *v31; // rcx
  _QWORD *v32; // rdx
  unsigned __int64 v33; // rsi
  _QWORD *v34; // rcx
  _QWORD *v35; // rdx
  _QWORD *v36; // rax
  unsigned __int64 v37; // [rsp+30h] [rbp-48h]
  __int64 v38; // [rsp+38h] [rbp-40h]
  __int64 v40; // [rsp+98h] [rbp+20h]

  v3 = -1;
  v4 = a2;
  v5 = -1;
  v7 = Src;
  do
    ++v5;
  while ( *(_WORD *)&v4[2 * v5] );
  v37 = v5;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&a3[2 * v8] );
  v38 = v8;
  v9 = (unsigned __int64 *)(Src + 16);
  v10 = 0;
  v40 = 0;
  v11 = 0;
  while ( 1 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)&v4[2 * v12] );
    if ( !v12 && v10 <= *v9 )
      goto LABEL_31;
    if ( v10 >= *v9 )
      return v11;
    v13 = *v9 - v10;
    if ( v12 > v13 )
      return v11;
    v14 = v13 - v12 + 1;
    if ( *((_QWORD *)v7 + 3) < 8u )
      v15 = v7;
    else
      v15 = *(char **)v7;
    v16 = &v15[2 * v10];
    while ( 1 )
    {
      if ( !v14 )
        return v40;
      v17 = v14;
      for ( i = v16; *(_WORD *)i != *(_WORD *)v4; i += 2 )
      {
        if ( !--v17 )
          return v40;
      }
      if ( !i )
        return v40;
      v20 = v12;
      Src = v4;
      v21 = i;
      if ( !v12 )
        break;
      while ( *(_WORD *)v21 == *(_WORD *)Src )
      {
        v21 += 2;
        Src += 2;
        if ( !--v20 )
          goto LABEL_26;
      }
      v23 = i - v16;
      v16 = i + 2;
      v14 += -1 - (v23 >> 1);
    }
LABEL_26:
    if ( *((_QWORD *)v7 + 3) < 8u )
      v22 = v7;
    else
      v22 = *(char **)v7;
    v5 = v37;
    v11 = v40;
    v10 = (i - v22) >> 1;
LABEL_31:
    if ( v10 == -1 )
      return v11;
    do
      ++v3;
    while ( *(_WORD *)&a3[2 * v3] );
    if ( a3
      && (*((_QWORD *)v7 + 3) < 8u ? (v24 = v7) : (v24 = *(char **)v7),
          a3 >= v24
       && (*((_QWORD *)v7 + 3) < 8u ? (v25 = v7) : (v25 = *(_QWORD **)v7), Src = (char *)v25 + 2 * *v9, Src > a3)) )
    {
      if ( *((_QWORD *)v7 + 3) < 8u )
        v26 = v7;
      else
        v26 = *(char **)v7;
      std::wstring::replace(v7, (a3 - v26) >> 1, v3);
    }
    else
    {
      v27 = *v9;
      if ( *v9 < v10 )
        std::wstring::_Xran(Src, v5, v12, v11);
      v28 = v5;
      if ( v27 - v10 < v5 )
        v28 = v27 - v10;
      v29 = v27 - v28;
      if ( ~v3 <= v29 )
        std::wstring::_Xlen(Src, v5, v12, v11);
      v30 = v29 - v10;
      if ( v3 < v28 )
      {
        if ( *((_QWORD *)v7 + 3) < 8u )
        {
          v31 = v7;
          v32 = v7;
        }
        else
        {
          v31 = *(_QWORD **)v7;
          v32 = *(_QWORD **)v7;
        }
        memmove_0((char *)v31 + 2 * v3 + 2 * v10, (char *)v32 + 2 * v28 + 2 * v10, 2 * v30);
      }
      if ( v3 || v28 )
      {
        v33 = v3 + *v9 - v28;
        if ( v33 > 0x7FFFFFFFFFFFFFFELL )
          std::wstring::_Xlen(Src, v5, v12, v11);
        if ( *((_QWORD *)v7 + 3) >= v33 )
        {
          if ( v33 )
          {
LABEL_60:
            if ( v28 < v3 )
            {
              if ( *((_QWORD *)v7 + 3) < 8u )
              {
                v34 = v7;
                v35 = v7;
              }
              else
              {
                v34 = *(_QWORD **)v7;
                v35 = *(_QWORD **)v7;
              }
              memmove_0((char *)v34 + 2 * v3 + 2 * v10, (char *)v35 + 2 * v28 + 2 * v10, 2 * v30);
            }
            if ( *((_QWORD *)v7 + 3) < 8u )
              v36 = v7;
            else
              v36 = *(_QWORD **)v7;
            memcpy_0((char *)v36 + 2 * v10, a3, 2 * v3);
            if ( *((_QWORD *)v7 + 3) < 8u )
              Src = v7;
            else
              Src = *(char **)v7;
            *v9 = v33;
            *(_WORD *)&Src[2 * v33] = 0;
          }
          else
          {
            if ( *((_QWORD *)v7 + 3) < 8u )
              Src = v7;
            else
              Src = *(char **)v7;
            *v9 = 0;
            *(_WORD *)Src = 0;
          }
        }
        else
        {
          std::wstring::_Copy(v7);
          if ( v33 )
            goto LABEL_60;
        }
        v4 = a2;
      }
    }
    v10 += v38;
    v11 = v40 + 1;
    v5 = v37;
    v3 = -1;
    ++v40;
  }
}

```

## disassembly

```asm
0x180002300  mov     [rsp+arg_0], rbx
0x180002305  mov     [rsp+arg_8], rdx
0x18000230a  push    rbp
0x18000230b  push    rsi
0x18000230c  push    rdi
0x18000230d  push    r12
0x18000230f  push    r13
0x180002311  push    r14
0x180002313  push    r15
0x180002315  sub     rsp, 40h
0x180002319  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000231d  mov     rsi, rdx
0x180002320  mov     rdx, r14
0x180002323  xor     r10d, r10d
0x180002326  mov     r13, r8
0x180002329  mov     rbx, rcx
0x18000232c  inc     rdx
0x18000232f  cmp     [rsi+rdx*2], r10w
0x180002334  jnz     short loc_18000232C
0x180002336  mov     [rsp+78h+var_48], rdx
0x18000233b  mov     rax, r14
0x18000233e  inc     rax
0x180002341  cmp     [r8+rax*2], r10w
0x180002346  jnz     short loc_18000233E
0x180002348  mov     [rsp+78h+var_40], rax
0x18000234d  lea     rbp, [rcx+10h]
0x180002351  mov     rdi, r10
0x180002354  mov     [rsp+78h+arg_18], r10
0x18000235c  mov     r9, r10
0x18000235f  mov     r8, r14
0x180002362  inc     r8
0x180002365  cmp     [rsi+r8*2], r10w
0x18000236a  jnz     short loc_180002362
0x18000236c  test    r8, r8
0x18000236f  jnz     short loc_18000237B
0x180002371  cmp     rdi, [rbp+0]
0x180002375  jbe     loc_18000244F
0x18000237b  mov     rdx, [rbp+0]
0x18000237f  cmp     rdi, rdx
0x180002382  jnb     short loc_1800023CA
0x180002384  sub     rdx, rdi
0x180002387  cmp     r8, rdx
0x18000238a  ja      short loc_1800023CA
0x18000238c  sub     rdx, r8
0x18000238f  inc     rdx
0x180002392  cmp     qword ptr [rbx+18h], 8
0x180002397  jb      short loc_18000239E
0x180002399  mov     rax, [rbx]
0x18000239c  jmp     short loc_1800023A1
0x18000239e  mov     rax, rbx
0x1800023a1  lea     r11, [rax+rdi*2]
0x1800023a5  test    rdx, rdx
0x1800023a8  jz      short loc_1800023C2
0x1800023aa  movzx   ecx, word ptr [rsi]
0x1800023ad  mov     rax, rdx
0x1800023b0  mov     rdi, r11
0x1800023b3  cmp     [rdi], cx
0x1800023b6  jz      short loc_1800023E5
0x1800023b8  add     rdi, 2
0x1800023bc  sub     rax, 1
0x1800023c0  jnz     short loc_1800023B3
0x1800023c2  mov     r9, [rsp+78h+arg_18]
0x1800023ca  mov     rbx, [rsp+78h+arg_0]
0x1800023d2  mov     rax, r9
0x1800023d5  add     rsp, 40h
0x1800023d9  pop     r15
0x1800023db  pop     r14
0x1800023dd  pop     r13
0x1800023df  pop     r12
0x1800023e1  pop     rdi
0x1800023e2  pop     rsi
0x1800023e3  pop     rbp
0x1800023e4  retn
0x1800023e5  test    rdi, rdi
0x1800023e8  jz      short loc_1800023C2
0x1800023ea  mov     r10, r8
0x1800023ed  mov     rcx, rsi
0x1800023f0  mov     r9, rdi
0x1800023f3  test    r8, r8
0x1800023f6  jz      short loc_18000240F
0x1800023f8  movzx   eax, word ptr [rcx]
0x1800023fb  cmp     [r9], ax
0x1800023ff  jnz     short loc_18000241B
0x180002401  add     r9, 2
0x180002405  add     rcx, 2
0x180002409  sub     r10, 1
0x18000240d  jnz     short loc_1800023F8
0x18000240f  cmp     qword ptr [rbx+18h], 8
0x180002414  jb      short loc_180002436
0x180002416  mov     rax, [rbx]
0x180002419  jmp     short loc_180002439
0x18000241b  mov     rcx, rdi
0x18000241e  mov     rax, r14
0x180002421  sub     rcx, r11
0x180002424  lea     r11, [rdi+2]
0x180002428  sar     rcx, 1
0x18000242b  sub     rax, rcx
0x18000242e  add     rdx, rax
0x180002431  jmp     loc_1800023A5
0x180002436  mov     rax, rbx
0x180002439  mov     rdx, [rsp+78h+var_48]
0x18000243e  sub     rdi, rax
0x180002441  mov     r9, [rsp+78h+arg_18]
0x180002449  sar     rdi, 1
0x18000244c  xor     r10d, r10d
0x18000244f  cmp     rdi, r14
0x180002452  jz      loc_1800023CA
0x180002458  inc     r14
0x18000245b  cmp     [r13+r14*2+0], r10w
0x180002461  jnz     short loc_180002458
0x180002463  test    r13, r13
0x180002466  jz      short loc_1800024D3
0x180002468  cmp     qword ptr [rbx+18h], 8
0x18000246d  jb      short loc_180002474
0x18000246f  mov     rax, [rbx]
0x180002472  jmp     short loc_180002477
0x180002474  mov     rax, rbx
0x180002477  cmp     r13, rax
0x18000247a  jb      short loc_1800024D3
0x18000247c  cmp     qword ptr [rbx+18h], 8
0x180002481  jb      short loc_180002488
0x180002483  mov     rcx, [rbx]
0x180002486  jmp     short loc_18000248B
0x180002488  mov     rcx, rbx
0x18000248b  mov     rax, [rbp+0]
0x18000248f  lea     rcx, [rcx+rax*2]
0x180002493  cmp     rcx, r13
0x180002496  jbe     short loc_1800024D3
0x180002498  cmp     qword ptr [rbx+18h], 8
0x18000249d  jb      short loc_1800024A4
0x18000249f  mov     rcx, [rbx]
0x1800024a2  jmp     short loc_1800024A7
0x1800024a4  mov     rcx, rbx
0x1800024a7  mov     r8, rdx
0x1800024aa  mov     [rsp+78h+var_50], r14; __int64
0x1800024af  mov     rax, r13
0x1800024b2  mov     r9, rbx
0x1800024b5  sub     rax, rcx
0x1800024b8  mov     rdx, rdi
0x1800024bb  sar     rax, 1
0x1800024be  mov     rcx, rbx; Src
0x1800024c1  mov     [rsp+78h+var_58], rax; __int64
0x1800024c6  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x1800024cb  xor     r10d, r10d
0x1800024ce  jmp     loc_18000261A
0x1800024d3  mov     r15, [rbp+0]
0x1800024d7  cmp     r15, rdi
0x1800024da  jb      loc_180002640
0x1800024e0  mov     rax, r15
0x1800024e3  mov     r12, rdx
0x1800024e6  sub     rax, rdi
0x1800024e9  cmp     rax, rdx
0x1800024ec  cmovb   r12, rax
0x1800024f0  mov     rax, r14
0x1800024f3  not     rax
0x1800024f6  sub     r15, r12
0x1800024f9  cmp     rax, r15
0x1800024fc  jbe     loc_18000264C
0x180002502  sub     r15, rdi
0x180002505  cmp     r14, r12
0x180002508  jnb     short loc_18000253B
0x18000250a  cmp     qword ptr [rbx+18h], 8
0x18000250f  jb      short loc_180002519
0x180002511  mov     rcx, [rbx]
0x180002514  mov     rdx, rcx
0x180002517  jmp     short loc_18000251F
0x180002519  mov     rcx, rbx
0x18000251c  mov     rdx, rbx
0x18000251f  lea     rax, [r12+rdi]
0x180002523  lea     rdx, [rdx+rax*2]; Src
0x180002527  lea     rax, [r14+rdi]
0x18000252b  lea     rcx, [rcx+rax*2]; void *
0x18000252f  lea     r8, [r15+r15]; Size
0x180002533  call    memmove_0
0x180002538  xor     r10d, r10d
0x18000253b  test    r14, r14
0x18000253e  jnz     short loc_180002549
0x180002540  test    r12, r12
0x180002543  jz      loc_18000261A
0x180002549  mov     rsi, [rbp+0]
0x18000254d  mov     rax, 7FFFFFFFFFFFFFFEh
0x180002557  sub     rsi, r12
0x18000255a  add     rsi, r14
0x18000255d  cmp     rsi, rax
0x180002560  ja      loc_180002646
0x180002566  cmp     [rbx+18h], rsi
0x18000256a  jnb     short loc_18000259B
0x18000256c  mov     r8, [rbp+0]
0x180002570  mov     rdx, rsi
0x180002573  mov     rcx, rbx; Src
0x180002576  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000257b  xor     r10d, r10d
0x18000257e  test    rsi, rsi
0x180002581  jz      loc_180002612
0x180002587  cmp     r12, r14
0x18000258a  jnb     short loc_1800025D8
0x18000258c  cmp     qword ptr [rbx+18h], 8
0x180002591  jb      short loc_1800025B9
0x180002593  mov     rcx, [rbx]
0x180002596  mov     rdx, rcx
0x180002599  jmp     short loc_1800025BF
0x18000259b  test    rsi, rsi
0x18000259e  jnz     short loc_180002587
0x1800025a0  cmp     qword ptr [rbx+18h], 8
0x1800025a5  jb      short loc_1800025AC
0x1800025a7  mov     rcx, [rbx]
0x1800025aa  jmp     short loc_1800025AF
0x1800025ac  mov     rcx, rbx
0x1800025af  mov     [rbp+0], r10
0x1800025b3  mov     [rcx], r10w
0x1800025b7  jmp     short loc_180002612
0x1800025b9  mov     rcx, rbx
0x1800025bc  mov     rdx, rbx
0x1800025bf  lea     rax, [r12+rdi]
0x1800025c3  lea     rdx, [rdx+rax*2]; Src
0x1800025c7  lea     rax, [r14+rdi]
0x1800025cb  lea     rcx, [rcx+rax*2]; void *
0x1800025cf  lea     r8, [r15+r15]; Size
0x1800025d3  call    memmove_0
0x1800025d8  cmp     qword ptr [rbx+18h], 8
0x1800025dd  jb      short loc_1800025E4
0x1800025df  mov     rax, [rbx]
0x1800025e2  jmp     short loc_1800025E7
0x1800025e4  mov     rax, rbx
0x1800025e7  lea     r8, [r14+r14]; Size
0x1800025eb  mov     rdx, r13; Src
0x1800025ee  lea     rcx, [rax+rdi*2]; void *
0x1800025f2  call    memcpy_0
0x1800025f7  cmp     qword ptr [rbx+18h], 8
0x1800025fc  jb      short loc_180002603
0x1800025fe  mov     rcx, [rbx]
0x180002601  jmp     short loc_180002606
0x180002603  mov     rcx, rbx
0x180002606  xor     r10d, r10d
0x180002609  mov     [rbp+0], rsi
0x18000260d  mov     [rcx+rsi*2], r10w
0x180002612  mov     rsi, [rsp+78h+arg_8]
0x18000261a  mov     r9, [rsp+78h+arg_18]
0x180002622  add     rdi, [rsp+78h+var_40]
0x180002627  inc     r9
0x18000262a  mov     rdx, [rsp+78h+var_48]
0x18000262f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002633  mov     [rsp+78h+arg_18], r9
0x18000263b  jmp     loc_18000235F
0x180002640  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180002646  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x18000264c  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
