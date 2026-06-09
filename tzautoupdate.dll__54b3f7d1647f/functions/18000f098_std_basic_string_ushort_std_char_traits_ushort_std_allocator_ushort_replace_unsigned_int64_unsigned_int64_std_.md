# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x18000f098`
- end: `0x18000f34e`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `694`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64, _QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000f928`

## callees

- `0x180002220`
- `0x18000224c`
- `0x18000e73c`
- `0x18000eb88`
- `0x18000f074`
- `0x18000f098`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  _QWORD *v7; // r15
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r14
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rbp
  unsigned __int64 v14; // rax
  __int64 v15; // r12
  __int64 v16; // r13
  unsigned __int64 v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  _QWORD *v24; // rdx
  __int64 v25; // r8
  char *v26; // rdx
  char *v27; // rcx
  _QWORD *v28; // rcx
  _QWORD *v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  unsigned __int64 v32; // r15
  _QWORD *v33; // rcx
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  __int64 v37; // r14
  _QWORD *v38; // rax
  _QWORD *v39; // rcx
  _QWORD *v40; // rcx
  _QWORD *v41; // rdx
  _QWORD *v42; // rax
  unsigned __int64 v44; // [rsp+70h] [rbp+8h]

  v7 = a4;
  v8 = a1[2];
  v9 = a3;
  if ( v8 < a2 || (v11 = a4[2], v12 = a5, v11 < a5) )
    std::_Xout_of_range("invalid string position");
  v13 = a6;
  if ( v8 - a2 < a3 )
    v9 = v8 - a2;
  v14 = v11 - a5;
  if ( v14 < a6 )
    v13 = v14;
  if ( ~v13 <= v8 - v9 )
    std::_Xlength_error("string too long");
  v15 = v8 - a2 - v9;
  v16 = v13 - v9;
  v44 = v8 + v13 - v9;
  if ( v8 < v44 )
    std::wstring::_Grow(a1, v8 + v13 - v9, 0);
  v17 = a1[3];
  if ( a1 == v7 )
  {
    if ( v13 > v9 )
    {
      if ( a5 > a2 )
      {
        v32 = a2 + v9;
        if ( a2 + v9 > a5 )
        {
          if ( v17 < 8 )
          {
            v35 = a1;
            v36 = a1;
          }
          else
          {
            v35 = (_QWORD *)*a1;
            v36 = (_QWORD *)*a1;
          }
          std::char_traits<unsigned short>::move((char *)v35 + 2 * a2, (char *)v36 + 2 * a5, v9);
          v37 = 2 * v32;
          if ( a1[3] < 8u )
          {
            v39 = a1;
            v38 = a1;
          }
          else
          {
            v38 = (_QWORD *)*a1;
            v39 = (_QWORD *)*a1;
          }
          std::char_traits<unsigned short>::move((char *)v39 + 2 * a2 + 2 * v13, (char *)v38 + v37, v15);
          if ( a1[3] < 8u )
          {
            v40 = a1;
            v41 = a1;
          }
          else
          {
            v40 = (_QWORD *)*a1;
            v41 = (_QWORD *)*a1;
          }
          v27 = (char *)v40 + v37;
          v26 = (char *)v41 + 2 * a5 + 2 * v13;
          v25 = v16;
          goto LABEL_55;
        }
        if ( v17 < 8 )
        {
          v33 = a1;
          v34 = a1;
        }
        else
        {
          v33 = (_QWORD *)*a1;
          v34 = (_QWORD *)*a1;
        }
        std::char_traits<unsigned short>::move((char *)v33 + 2 * a2 + 2 * v13, (char *)v34 + 2 * v32, v15);
        if ( a1[3] < 8u )
        {
          v30 = a1;
          v31 = a1;
        }
        else
        {
          v30 = (_QWORD *)*a1;
          v31 = (_QWORD *)*a1;
        }
        v12 = v13 + a5 - v9;
      }
      else
      {
        if ( v17 < 8 )
        {
          v28 = a1;
          v29 = a1;
        }
        else
        {
          v28 = (_QWORD *)*a1;
          v29 = (_QWORD *)*a1;
        }
        std::char_traits<unsigned short>::move((char *)v28 + 2 * a2 + 2 * v13, (char *)v29 + 2 * a2 + 2 * v9, v15);
        if ( a1[3] < 8u )
        {
          v30 = a1;
          v31 = a1;
        }
        else
        {
          v30 = (_QWORD *)*a1;
          v31 = (_QWORD *)*a1;
        }
      }
      v26 = (char *)v31 + 2 * v12;
      v25 = v13;
      v27 = (char *)v30 + 2 * a2;
    }
    else
    {
      if ( v17 < 8 )
      {
        v21 = a1;
        v22 = a1;
      }
      else
      {
        v21 = (_QWORD *)*a1;
        v22 = (_QWORD *)*a1;
      }
      std::char_traits<unsigned short>::move((char *)v21 + 2 * a2, (char *)v22 + 2 * a5, v13);
      if ( a1[3] < 8u )
      {
        v23 = a1;
        v24 = a1;
      }
      else
      {
        v23 = (_QWORD *)*a1;
        v24 = (_QWORD *)*a1;
      }
      v25 = v15;
      v26 = (char *)v24 + 2 * a2 + 2 * v9;
      v27 = (char *)v23 + 2 * a2 + 2 * v13;
    }
LABEL_55:
    std::char_traits<unsigned short>::move(v27, v26, v25);
    goto LABEL_56;
  }
  if ( v17 < 8 )
  {
    v18 = a1;
    v19 = a1;
  }
  else
  {
    v18 = (_QWORD *)*a1;
    v19 = (_QWORD *)*a1;
  }
  std::char_traits<unsigned short>::move((char *)v18 + 2 * a2 + 2 * v13, (char *)v19 + 2 * a2 + 2 * v9, v15);
  if ( v7[3] >= 8u )
    v7 = (_QWORD *)*v7;
  if ( a1[3] < 8u )
    v20 = a1;
  else
    v20 = (_QWORD *)*a1;
  std::char_traits<unsigned short>::copy((char *)v20 + 2 * a2, (char *)v7 + 2 * a5, v13);
LABEL_56:
  if ( a1[3] < 8u )
    v42 = a1;
  else
    v42 = (_QWORD *)*a1;
  a1[2] = v44;
  *((_WORD *)v42 + v44) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000f098  push    rbx
0x18000f09a  push    rbp
0x18000f09b  push    rsi
0x18000f09c  push    rdi
0x18000f09d  push    r12
0x18000f09f  push    r13
0x18000f0a1  push    r14
0x18000f0a3  push    r15
0x18000f0a5  sub     rsp, 28h
0x18000f0a9  mov     rdi, rdx
0x18000f0ac  mov     r15, r9
0x18000f0af  mov     rdx, [rcx+10h]
0x18000f0b3  mov     r14, r8
0x18000f0b6  mov     rbx, rcx
0x18000f0b9  cmp     rdx, rdi
0x18000f0bc  jb      loc_18000F341
0x18000f0c2  mov     rax, [r9+10h]
0x18000f0c6  mov     rsi, [rsp+68h+arg_20]
0x18000f0ce  cmp     rax, rsi
0x18000f0d1  jb      loc_18000F341
0x18000f0d7  mov     rbp, [rsp+68h+arg_28]
0x18000f0df  mov     r12, rdx
0x18000f0e2  sub     r12, rdi
0x18000f0e5  mov     rcx, rdx
0x18000f0e8  cmp     r12, r8
0x18000f0eb  cmovb   r14, r12
0x18000f0ef  sub     rax, rsi
0x18000f0f2  cmp     rax, rbp
0x18000f0f5  cmovb   rbp, rax
0x18000f0f9  sub     rcx, r14
0x18000f0fc  mov     rax, rbp
0x18000f0ff  not     rax
0x18000f102  cmp     rax, rcx
0x18000f105  ja      short loc_18000F114
0x18000f107  lea     rcx, aStringTooLong; "string too long"
0x18000f10e  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f114  mov     r13, rbp
0x18000f117  sub     r12, r14
0x18000f11a  sub     r13, r14
0x18000f11d  lea     rax, [rdx+r13]
0x18000f121  mov     [rsp+68h+arg_0], rax
0x18000f126  cmp     rdx, rax
0x18000f129  jnb     short loc_18000F139
0x18000f12b  xor     r8d, r8d
0x18000f12e  mov     rdx, rax
0x18000f131  mov     rcx, rbx
0x18000f134  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x18000f139  mov     rax, [rbx+18h]
0x18000f13d  cmp     rbx, r15
0x18000f140  jz      short loc_18000F19C
0x18000f142  cmp     rax, 8
0x18000f146  jb      short loc_18000F150
0x18000f148  mov     rcx, [rbx]
0x18000f14b  mov     rdx, rcx
0x18000f14e  jmp     short loc_18000F156
0x18000f150  mov     rcx, rbx
0x18000f153  mov     rdx, rbx
0x18000f156  lea     rax, [rdi+r14]
0x18000f15a  mov     r8, r12
0x18000f15d  lea     rdx, [rdx+rax*2]
0x18000f161  lea     rax, [rdi+rbp]
0x18000f165  lea     rcx, [rcx+rax*2]
0x18000f169  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18000f16e  cmp     qword ptr [r15+18h], 8
0x18000f173  jb      short loc_18000F178
0x18000f175  mov     r15, [r15]
0x18000f178  cmp     qword ptr [rbx+18h], 8
0x18000f17d  jb      short loc_18000F184
0x18000f17f  mov     rax, [rbx]
0x18000f182  jmp     short loc_18000F187
0x18000f184  mov     rax, rbx
0x18000f187  lea     rdx, [r15+rsi*2]
0x18000f18b  mov     r8, rbp
0x18000f18e  lea     rcx, [rax+rdi*2]
0x18000f192  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x18000f197  jmp     loc_18000F30F
0x18000f19c  cmp     rbp, r14
0x18000f19f  ja      short loc_18000F1F2
0x18000f1a1  cmp     rax, 8
0x18000f1a5  jb      short loc_18000F1AF
0x18000f1a7  mov     rax, [rbx]
0x18000f1aa  mov     rcx, rax
0x18000f1ad  jmp     short loc_18000F1B5
0x18000f1af  mov     rax, rbx
0x18000f1b2  mov     rcx, rbx
0x18000f1b5  lea     rdx, [rcx+rsi*2]
0x18000f1b9  mov     r8, rbp
0x18000f1bc  lea     rcx, [rax+rdi*2]
0x18000f1c0  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18000f1c5  cmp     qword ptr [rbx+18h], 8
0x18000f1ca  jb      short loc_18000F1D4
0x18000f1cc  mov     rcx, [rbx]
0x18000f1cf  mov     rdx, rcx
0x18000f1d2  jmp     short loc_18000F1DA
0x18000f1d4  mov     rcx, rbx
0x18000f1d7  mov     rdx, rbx
0x18000f1da  lea     rax, [rdi+r14]
0x18000f1de  mov     r8, r12
0x18000f1e1  lea     rdx, [rdx+rax*2]
0x18000f1e5  lea     rax, [rdi+rbp]
0x18000f1e9  lea     rcx, [rcx+rax*2]
0x18000f1ed  jmp     loc_18000F30A
0x18000f1f2  cmp     rsi, rdi
0x18000f1f5  ja      short loc_18000F248
0x18000f1f7  cmp     rax, 8
0x18000f1fb  jb      short loc_18000F205
0x18000f1fd  mov     rcx, [rbx]
0x18000f200  mov     rdx, rcx
0x18000f203  jmp     short loc_18000F20B
0x18000f205  mov     rcx, rbx
0x18000f208  mov     rdx, rbx
0x18000f20b  lea     rax, [rdi+r14]
0x18000f20f  mov     r8, r12
0x18000f212  lea     rdx, [rdx+rax*2]
0x18000f216  lea     rax, [rdi+rbp]
0x18000f21a  lea     rcx, [rcx+rax*2]
0x18000f21e  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18000f223  cmp     qword ptr [rbx+18h], 8
0x18000f228  jb      short loc_18000F232
0x18000f22a  mov     rax, [rbx]
0x18000f22d  mov     rcx, rax
0x18000f230  jmp     short loc_18000F238
0x18000f232  mov     rax, rbx
0x18000f235  mov     rcx, rbx
0x18000f238  lea     rdx, [rcx+rsi*2]
0x18000f23c  mov     r8, rbp
0x18000f23f  lea     rcx, [rax+rdi*2]
0x18000f243  jmp     loc_18000F30A
0x18000f248  lea     r15, [rdi+r14]
0x18000f24c  cmp     r15, rsi
0x18000f24f  ja      short loc_18000F296
0x18000f251  cmp     rax, 8
0x18000f255  jb      short loc_18000F25F
0x18000f257  mov     rcx, [rbx]
0x18000f25a  mov     rax, rcx
0x18000f25d  jmp     short loc_18000F265
0x18000f25f  mov     rcx, rbx
0x18000f262  mov     rax, rbx
0x18000f265  lea     rdx, [rax+r15*2]
0x18000f269  mov     r8, r12
0x18000f26c  lea     rax, [rdi+rbp]
0x18000f270  lea     rcx, [rcx+rax*2]
0x18000f274  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18000f279  cmp     qword ptr [rbx+18h], 8
0x18000f27e  jb      short loc_18000F288
0x18000f280  mov     rax, [rbx]
0x18000f283  mov     rcx, rax
0x18000f286  jmp     short loc_18000F28E
0x18000f288  mov     rax, rbx
0x18000f28b  mov     rcx, rbx
0x18000f28e  sub     rsi, r14
0x18000f291  add     rsi, rbp
0x18000f294  jmp     short loc_18000F238
0x18000f296  cmp     rax, 8
0x18000f29a  jb      short loc_18000F2A4
0x18000f29c  mov     rax, [rbx]
0x18000f29f  mov     rcx, rax
0x18000f2a2  jmp     short loc_18000F2AA
0x18000f2a4  mov     rax, rbx
0x18000f2a7  mov     rcx, rbx
0x18000f2aa  lea     rdx, [rcx+rsi*2]
0x18000f2ae  mov     r8, r14
0x18000f2b1  lea     rcx, [rax+rdi*2]
0x18000f2b5  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18000f2ba  cmp     qword ptr [rbx+18h], 8
0x18000f2bf  lea     r14, [r15+r15]
0x18000f2c3  jb      short loc_18000F2CD
0x18000f2c5  mov     rax, [rbx]
0x18000f2c8  mov     rcx, rax
0x18000f2cb  jmp     short loc_18000F2D3
0x18000f2cd  mov     rcx, rbx
0x18000f2d0  mov     rax, rbx
0x18000f2d3  lea     rdx, [r14+rax]
0x18000f2d7  mov     r8, r12
0x18000f2da  lea     rax, [rdi+rbp]
0x18000f2de  lea     rcx, [rcx+rax*2]
0x18000f2e2  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18000f2e7  cmp     qword ptr [rbx+18h], 8
0x18000f2ec  jb      short loc_18000F2F6
0x18000f2ee  mov     rcx, [rbx]
0x18000f2f1  mov     rdx, rcx
0x18000f2f4  jmp     short loc_18000F2FC
0x18000f2f6  mov     rcx, rbx
0x18000f2f9  mov     rdx, rbx
0x18000f2fc  lea     rax, [rsi+rbp]
0x18000f300  add     rcx, r14
0x18000f303  lea     rdx, [rdx+rax*2]
0x18000f307  mov     r8, r13
0x18000f30a  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18000f30f  cmp     qword ptr [rbx+18h], 8
0x18000f314  jb      short loc_18000F31B
0x18000f316  mov     rax, [rbx]
0x18000f319  jmp     short loc_18000F31E
0x18000f31b  mov     rax, rbx
0x18000f31e  mov     rcx, [rsp+68h+arg_0]
0x18000f323  xor     edx, edx
0x18000f325  mov     [rbx+10h], rcx
0x18000f329  mov     [rax+rcx*2], dx
0x18000f32d  mov     rax, rbx
0x18000f330  add     rsp, 28h
0x18000f334  pop     r15
0x18000f336  pop     r14
0x18000f338  pop     r13
0x18000f33a  pop     r12
0x18000f33c  pop     rdi
0x18000f33d  pop     rsi
0x18000f33e  pop     rbp
0x18000f33f  pop     rbx
0x18000f340  retn
0x18000f341  lea     rcx, aInvalidStringP; "invalid string position"
0x18000f348  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
