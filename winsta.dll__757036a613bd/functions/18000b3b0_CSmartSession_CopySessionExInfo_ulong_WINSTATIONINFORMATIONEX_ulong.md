# CSmartSession::CopySessionExInfo(ulong,_WINSTATIONINFORMATIONEX *,ulong)

- ea: `0x18000b3b0`
- end: `0x18000b86a`
- name: `?CopySessionExInfo@CSmartSession@@QEAAJKPEAU_WINSTATIONINFORMATIONEX@@K@Z`
- size: `1210`
- prototype: `int(CSmartSession *__hidden this, unsigned int, struct _WINSTATIONINFORMATIONEX *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ad50`

## callees

- `0x180007890`
- `0x18000b3b0`
- `0x18002fe06`

## string_xrefs

- `0x18000b6d4`: `CSmartSession::CopySessionExInfo`
- `0x18000b6f3`: `CSmartSession::CopySessionExInfo`
- `0x18000b712`: `CSmartSession::CopySessionExInfo`
- `0x18000b804`: `CSmartSession::CopySessionExInfo`
- `0x18000b826`: `CSmartSession::CopySessionExInfo`
- `0x18000b848`: `CSmartSession::CopySessionExInfo`
- `0x18000b6fd`: `StringCchCopy on Domain Name failed: 0x%x in %s`
- `0x18000b830`: `StringCchCopy on WinStation Name failed: 0x%x in %s`
- `0x18000b852`: `StringCchCopy on User Name failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSmartSession::CopySessionExInfo(CSmartSession *this, int a2, struct _WINSTATIONINFORMATIONEX *a3)
{
  __int128 v6; // xmm0
  __int128 *v7; // r14
  __int128 v8; // xmm1
  __int128 v9; // xmm2
  __int128 v10; // xmm3
  __int128 v11; // xmm4
  __int128 v12; // xmm5
  __int128 v13; // xmm6
  __int128 v14; // xmm7
  __int128 v15; // xmm8
  __m128i v16; // xmm10
  __m128i v17; // xmm9
  __m128i v18; // xmm11
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 *v21; // rax
  __int64 v22; // r11
  __int64 v23; // rax
  __int64 *v24; // rdx
  __int64 v25; // r9
  _WORD *v26; // rcx
  _WORD *v27; // rdx
  unsigned int v28; // ebp
  unsigned int v29; // ebx
  __int64 v30; // rdx
  _WORD *v31; // rax
  __int64 v32; // rax
  _WORD *v33; // rdx
  __int64 v34; // r9
  _WORD *v35; // rcx
  _WORD *v36; // rdx
  unsigned int v37; // ebx
  _WORD *v38; // rax
  _WORD *v39; // rax
  __int64 v40; // r8
  _WORD *v41; // rcx
  _WORD *v42; // rdx
  char *v44; // rdi
  __int64 v45; // rax
  __int128 v46; // xmm0
  __int64 v47; // [rsp+28h] [rbp-140h] BYREF
  __int128 v48; // [rsp+30h] [rbp-138h]
  __int128 v49; // [rsp+40h] [rbp-128h]
  __int128 v50; // [rsp+50h] [rbp-118h]
  _OWORD v51[2]; // [rsp+60h] [rbp-108h] BYREF
  _OWORD v52[6]; // [rsp+80h] [rbp-E8h] BYREF
  __int128 *v53; // [rsp+E0h] [rbp-88h]

  memset_0(a3, 0, 0x4C8u);
  v6 = *((_OWORD *)this + 5);
  v7 = (__int128 *)*((_QWORD *)this + 34);
  v8 = *((_OWORD *)this + 6);
  v9 = *((_OWORD *)this + 7);
  v10 = *((_OWORD *)this + 8);
  v11 = *((_OWORD *)this + 9);
  v12 = *((_OWORD *)this + 10);
  v13 = *((_OWORD *)this + 11);
  v14 = *((_OWORD *)this + 12);
  v15 = *((_OWORD *)this + 13);
  v16 = *((__m128i *)this + 14);
  v17 = *((__m128i *)this + 15);
  v18 = *((__m128i *)this + 16);
  if ( *((_DWORD *)this + 18) != 1 )
    return 2147942413LL;
  *(_DWORD *)a3 = 1;
  *((_DWORD *)a3 + 3) = v6;
  v19 = 0x7FFFFFFF;
  v20 = 0x7FFFFFFF;
  *((_DWORD *)a3 + 4) = DWORD1(v6);
  v21 = &v47;
  v47 = *((_QWORD *)&v6 + 1);
  v53 = v7;
  v48 = v8;
  *((_DWORD *)a3 + 2) = a2;
  v49 = v9;
  v50 = v10;
  v51[0] = v11;
  v51[1] = v12;
  v52[0] = v13;
  v52[1] = v14;
  v52[2] = v15;
  v52[3] = v16;
  v52[4] = v17;
  v52[5] = v18;
  do
  {
    if ( !*(_WORD *)v21 )
      break;
    v21 = (__int64 *)((char *)v21 + 2);
    --v20;
  }
  while ( v20 );
  if ( v20 )
  {
    v22 = 2147483646;
    v23 = 2147483646;
    v24 = &v47;
    v25 = 33;
    v26 = (_WORD *)((char *)a3 + 20);
    do
    {
      if ( !v23 )
        break;
      if ( !*(_WORD *)v24 )
        break;
      *v26 = *(_WORD *)v24;
      v24 = (__int64 *)((char *)v24 + 2);
      ++v26;
      --v23;
      --v25;
    }
    while ( v25 );
    v27 = v26 - 1;
    v28 = -2147024774;
    v29 = -2147024774;
    if ( v25 )
    {
      v27 = v26;
      v29 = 0;
    }
    *v27 = 0;
    if ( v25 )
    {
      v30 = 0x7FFFFFFF;
      v31 = (_WORD *)v52 + 7;
      do
      {
        if ( !*v31 )
          break;
        ++v31;
        --v30;
      }
      while ( v30 );
      if ( v30 )
      {
        v32 = 2147483646;
        v33 = (_WORD *)v52 + 7;
        v34 = 21;
        v35 = (_WORD *)((char *)a3 + 86);
        do
        {
          if ( !v32 )
            break;
          if ( !*v33 )
            break;
          *v35++ = *v33++;
          --v32;
          --v34;
        }
        while ( v34 );
        v36 = v35 - 1;
        v37 = -2147024774;
        if ( v34 )
        {
          v36 = v35;
          v37 = 0;
        }
        *v36 = 0;
        if ( v34 )
        {
          v38 = (_WORD *)v51 + 5;
          do
          {
            if ( !*v38 )
              break;
            ++v38;
            --v19;
          }
          while ( v19 );
          if ( v19 )
          {
            v39 = (_WORD *)v51 + 5;
            v40 = 18;
            v41 = (_WORD *)((char *)a3 + 128);
            do
            {
              if ( !v22 )
                break;
              if ( !*v39 )
                break;
              *v41++ = *v39++;
              --v22;
              --v40;
            }
            while ( v40 );
            v42 = v41 - 1;
            if ( v40 )
            {
              v42 = v41;
              v28 = 0;
            }
            *v42 = 0;
            if ( v40 )
            {
              *((_QWORD *)a3 + 23) = v17.m128i_i64[0];
              *((_QWORD *)a3 + 21) = _mm_srli_si128(v17, 8).m128i_u64[0];
              *((_QWORD *)a3 + 22) = _mm_srli_si128(v16, 8).m128i_u64[0];
              *((_QWORD *)a3 + 24) = v18.m128i_i64[0];
              if ( v7 && (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v18, 8)) >= 0x3F4 )
              {
                v44 = (char *)a3 + 208;
                v45 = 7;
                do
                {
                  v44 += 128;
                  v46 = *v7;
                  v7 += 8;
                  *((_OWORD *)v44 - 8) = v46;
                  *((_OWORD *)v44 - 7) = *(v7 - 7);
                  *((_OWORD *)v44 - 6) = *(v7 - 6);
                  *((_OWORD *)v44 - 5) = *(v7 - 5);
                  *((_OWORD *)v44 - 4) = *(v7 - 4);
                  *((_OWORD *)v44 - 3) = *(v7 - 3);
                  *((_OWORD *)v44 - 2) = *(v7 - 2);
                  *((_OWORD *)v44 - 1) = *(v7 - 1);
                  --v45;
                }
                while ( v45 );
                *(_OWORD *)v44 = *v7;
                *((_OWORD *)v44 + 1) = v7[1];
                *((_OWORD *)v44 + 2) = v7[2];
                *((_OWORD *)v44 + 3) = v7[3];
                *((_OWORD *)v44 + 4) = v7[4];
                *((_OWORD *)v44 + 5) = v7[5];
                *((_OWORD *)v44 + 6) = v7[6];
                *((_DWORD *)v44 + 28) = *((_DWORD *)v7 + 28);
              }
              return 0;
            }
            else
            {
              _DbgPrintMessage(
                8,
                "StringCchCopy on Domain Name failed: 0x%x in %s",
                v28,
                "CSmartSession::CopySessionExInfo");
              return v28;
            }
          }
          else
          {
            _DbgPrintMessage(
              8,
              "StringCchLength on Domain Name failed: 0x%x in %s",
              -2147024809,
              "CSmartSession::CopySessionExInfo");
            return 2147942487LL;
          }
        }
        else
        {
          _DbgPrintMessage(8, "StringCchCopy on User Name failed: 0x%x in %s", v37, "CSmartSession::CopySessionExInfo");
          return v37;
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "StringCchLength on User Name failed: 0x%x in %s",
          -2147024809,
          "CSmartSession::CopySessionExInfo");
        return 2147942487LL;
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "StringCchCopy on WinStation Name failed: 0x%x in %s",
        v29,
        "CSmartSession::CopySessionExInfo");
      return v29;
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "StringCchLength on WinStation Name failed: 0x%x in %s",
      -2147024809,
      "CSmartSession::CopySessionExInfo");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000b3b0  mov     rax, rsp
0x18000b3b3  mov     [rax+10h], rbx
0x18000b3b7  push    rsi
0x18000b3b8  push    rdi
0x18000b3b9  push    r14
0x18000b3bb  sub     rsp, 150h
0x18000b3c2  movaps  xmmword ptr [rax-28h], xmm6
0x18000b3c6  mov     rdi, r8
0x18000b3c9  movaps  xmmword ptr [rax-38h], xmm7
0x18000b3cd  mov     esi, edx
0x18000b3cf  movaps  xmmword ptr [rax-48h], xmm8
0x18000b3d4  mov     rbx, rcx
0x18000b3d7  movaps  xmmword ptr [rax-58h], xmm9
0x18000b3dc  xor     edx, edx; Val
0x18000b3de  movaps  xmmword ptr [rax-68h], xmm10
0x18000b3e3  mov     r8d, 4C8h; Size
0x18000b3e9  mov     rcx, rdi; void *
0x18000b3ec  movaps  xmmword ptr [rax-78h], xmm11
0x18000b3f1  call    memset_0
0x18000b3f6  cmp     dword ptr [rbx+48h], 1
0x18000b3fa  movups  xmm0, xmmword ptr [rbx+50h]
0x18000b3fe  mov     r14, [rbx+110h]
0x18000b405  movups  xmm1, xmmword ptr [rbx+60h]
0x18000b409  movups  xmm2, xmmword ptr [rbx+70h]
0x18000b40d  movups  xmm3, xmmword ptr [rbx+80h]
0x18000b414  movups  xmm4, xmmword ptr [rbx+90h]
0x18000b41b  movups  xmm5, xmmword ptr [rbx+0A0h]
0x18000b422  movups  xmm6, xmmword ptr [rbx+0B0h]
0x18000b429  movups  xmm7, xmmword ptr [rbx+0C0h]
0x18000b430  movups  xmm8, xmmword ptr [rbx+0D0h]
0x18000b438  movups  xmm10, xmmword ptr [rbx+0E0h]
0x18000b440  movups  xmm9, xmmword ptr [rbx+0F0h]
0x18000b448  movups  xmm11, xmmword ptr [rbx+100h]
0x18000b450  jnz     loc_18000B7FA
0x18000b456  mov     dword ptr [rdi], 1
0x18000b45c  movq    rax, xmm0
0x18000b461  mov     [rdi+0Ch], eax
0x18000b464  mov     r8d, 7FFFFFFFh
0x18000b46a  shr     rax, 20h
0x18000b46e  mov     edx, r8d
0x18000b471  mov     [rdi+10h], eax
0x18000b474  lea     rax, [rsp+168h+var_140]
0x18000b479  movups  xmmword ptr [rsp+20h], xmm0
0x18000b47e  mov     [rsp+168h+var_88], r14
0x18000b486  movups  [rsp+168h+var_138], xmm1
0x18000b48b  mov     [rdi+8], esi
0x18000b48e  movups  [rsp+168h+var_128], xmm2
0x18000b493  movups  [rsp+168h+var_118], xmm3
0x18000b498  movups  [rsp+168h+var_108], xmm4
0x18000b49d  movups  [rsp+168h+var_F8], xmm5
0x18000b4a2  movups  [rsp+168h+var_E8], xmm6
0x18000b4aa  movups  [rsp+168h+var_D8], xmm7
0x18000b4b2  movups  [rsp+168h+var_C8], xmm8
0x18000b4bb  movups  [rsp+168h+var_B8], xmm10
0x18000b4c4  movups  [rsp+168h+var_A8], xmm9
0x18000b4cd  movups  [rsp+168h+var_98], xmm11
0x18000b4d6  cmp     word ptr [rax], 0
0x18000b4da  jz      short loc_18000B4E6
0x18000b4dc  add     rax, 2
0x18000b4e0  sub     rdx, 1
0x18000b4e4  jnz     short loc_18000B4D6
0x18000b4e6  xor     ecx, ecx
0x18000b4e8  mov     esi, 80070057h
0x18000b4ed  test    rdx, rdx
0x18000b4f0  mov     ebx, esi
0x18000b4f2  cmovnz  ebx, ecx
0x18000b4f5  jz      loc_18000B804
0x18000b4fb  mov     r11d, 7FFFFFFEh
0x18000b501  mov     [rsp+168h+arg_0], rbp
0x18000b509  mov     eax, r11d
0x18000b50c  lea     rdx, [rsp+168h+var_140]
0x18000b511  mov     r9d, 21h ; '!'
0x18000b517  lea     rcx, [rdi+14h]
0x18000b51b  nop     dword ptr [rax+rax+00h]
0x18000b520  test    rax, rax
0x18000b523  jz      short loc_18000B544
0x18000b525  movzx   r10d, word ptr [rdx]
0x18000b529  test    r10w, r10w
0x18000b52d  jz      short loc_18000B544
0x18000b52f  mov     [rcx], r10w
0x18000b533  add     rdx, 2
0x18000b537  add     rcx, 2
0x18000b53b  dec     rax
0x18000b53e  sub     r9, 1
0x18000b542  jnz     short loc_18000B520
0x18000b544  xor     eax, eax
0x18000b546  lea     rdx, [rcx-2]
0x18000b54a  test    r9, r9
0x18000b54d  mov     ebp, 8007007Ah
0x18000b552  mov     ebx, ebp
0x18000b554  cmovnz  rdx, rcx
0x18000b558  cmovnz  ebx, eax
0x18000b55b  xor     ecx, ecx
0x18000b55d  mov     [rdx], cx
0x18000b560  test    r9, r9
0x18000b563  jz      loc_18000B826
0x18000b569  mov     rdx, r8
0x18000b56c  lea     rax, [rsp+168h+var_E8+0Eh]
0x18000b574  cmp     [rax], cx
0x18000b577  jz      short loc_18000B583
0x18000b579  add     rax, 2
0x18000b57d  sub     rdx, 1
0x18000b581  jnz     short loc_18000B574
0x18000b583  test    rdx, rdx
0x18000b586  mov     ebx, esi
0x18000b588  cmovnz  ebx, ecx
0x18000b58b  jz      loc_18000B712
0x18000b591  mov     rax, r11
0x18000b594  lea     rdx, [rsp+168h+var_E8+0Eh]
0x18000b59c  mov     r9d, 15h
0x18000b5a2  lea     rcx, [rdi+56h]
0x18000b5a6  test    rax, rax
0x18000b5a9  jz      short loc_18000B5CA
0x18000b5ab  movzx   r10d, word ptr [rdx]
0x18000b5af  test    r10w, r10w
0x18000b5b3  jz      short loc_18000B5CA
0x18000b5b5  mov     [rcx], r10w
0x18000b5b9  add     rdx, 2
0x18000b5bd  add     rcx, 2
0x18000b5c1  dec     rax
0x18000b5c4  sub     r9, 1
0x18000b5c8  jnz     short loc_18000B5A6
0x18000b5ca  xor     eax, eax
0x18000b5cc  lea     rdx, [rcx-2]
0x18000b5d0  test    r9, r9
0x18000b5d3  mov     ebx, ebp
0x18000b5d5  cmovnz  rdx, rcx
0x18000b5d9  cmovnz  ebx, eax
0x18000b5dc  xor     ecx, ecx
0x18000b5de  mov     [rdx], cx
0x18000b5e1  test    r9, r9
0x18000b5e4  jz      loc_18000B848
0x18000b5ea  lea     rax, [rsp+168h+var_108+0Ah]
0x18000b5ef  nop
0x18000b5f0  cmp     [rax], cx
0x18000b5f3  jz      short loc_18000B5FF
0x18000b5f5  add     rax, 2
0x18000b5f9  sub     r8, 1
0x18000b5fd  jnz     short loc_18000B5F0
0x18000b5ff  test    r8, r8
0x18000b602  cmovnz  esi, ecx
0x18000b605  jz      loc_18000B6D4
0x18000b60b  lea     rax, [rsp+168h+var_108+0Ah]
0x18000b610  mov     r8d, 12h
0x18000b616  lea     rcx, [rdi+80h]
0x18000b61d  nop     dword ptr [rax]
0x18000b620  test    r11, r11
0x18000b623  jz      short loc_18000B641
0x18000b625  movzx   edx, word ptr [rax]
0x18000b628  test    dx, dx
0x18000b62b  jz      short loc_18000B641
0x18000b62d  mov     [rcx], dx
0x18000b630  add     rax, 2
0x18000b634  add     rcx, 2
0x18000b638  dec     r11
0x18000b63b  sub     r8, 1
0x18000b63f  jnz     short loc_18000B620
0x18000b641  xor     eax, eax
0x18000b643  lea     rdx, [rcx-2]
0x18000b647  test    r8, r8
0x18000b64a  cmovnz  rdx, rcx
0x18000b64e  cmovnz  ebp, eax
0x18000b651  xor     ecx, ecx
0x18000b653  mov     [rdx], cx
0x18000b656  test    r8, r8
0x18000b659  jz      loc_18000B6F3
0x18000b65f  movsd   qword ptr [rdi+0B8h], xmm9
0x18000b668  psrldq  xmm9, 8
0x18000b66e  psrldq  xmm10, 8
0x18000b674  movq    qword ptr [rdi+0A8h], xmm9
0x18000b67d  movq    qword ptr [rdi+0B0h], xmm10
0x18000b686  movsd   qword ptr [rdi+0C0h], xmm11
0x18000b68f  test    r14, r14
0x18000b692  jnz     loc_18000B734
0x18000b698  xor     eax, eax
0x18000b69a  mov     rbp, [rsp+168h+arg_0]
0x18000b6a2  lea     r11, [rsp+168h+var_18]
0x18000b6aa  mov     rbx, [r11+28h]
0x18000b6ae  movaps  xmm6, xmmword ptr [r11-10h]
0x18000b6b3  movaps  xmm7, xmmword ptr [r11-20h]
0x18000b6b8  movaps  xmm8, xmmword ptr [r11-30h]
0x18000b6bd  movaps  xmm9, xmmword ptr [r11-40h]
0x18000b6c2  movaps  xmm10, xmmword ptr [r11-50h]
0x18000b6c7  movaps  xmm11, xmmword ptr [r11-60h]
0x18000b6cc  mov     rsp, r11
0x18000b6cf  pop     r14
0x18000b6d1  pop     rdi
0x18000b6d2  pop     rsi
0x18000b6d3  retn
0x18000b6d4  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000b6db  mov     r8d, esi
0x18000b6de  lea     rdx, aStringcchlengt_1; "StringCchLength on Domain Name failed: "...
0x18000b6e5  mov     ecx, 8; int
0x18000b6ea  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b6ef  mov     eax, esi
0x18000b6f1  jmp     short loc_18000B69A
0x18000b6f3  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000b6fa  mov     r8d, ebp
0x18000b6fd  lea     rdx, aStringcchcopyO_0; "StringCchCopy on Domain Name failed: 0x"...
0x18000b704  mov     ecx, 8; int
0x18000b709  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b70e  mov     eax, ebp
0x18000b710  jmp     short loc_18000B69A
0x18000b712  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000b719  mov     r8d, ebx
0x18000b71c  lea     rdx, aStringcchlengt_0; "StringCchLength on User Name failed: 0x"...
0x18000b723  mov     ecx, 8; int
0x18000b728  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b72d  mov     eax, ebx
0x18000b72f  jmp     loc_18000B69A
0x18000b734  psrldq  xmm11, 8
0x18000b73a  movd    eax, xmm11
0x18000b73f  cmp     eax, 3F4h
0x18000b744  jb      loc_18000B698
0x18000b74a  add     rdi, 0D0h
0x18000b751  mov     eax, 7
0x18000b756  lea     rdi, [rdi+80h]
0x18000b75d  movups  xmm0, xmmword ptr [r14]
0x18000b761  lea     r14, [r14+80h]
0x18000b768  movups  xmmword ptr [rdi-80h], xmm0
0x18000b76c  movups  xmm1, xmmword ptr [r14-70h]
0x18000b771  movups  xmmword ptr [rdi-70h], xmm1
0x18000b775  movups  xmm0, xmmword ptr [r14-60h]
0x18000b77a  movups  xmmword ptr [rdi-60h], xmm0
0x18000b77e  movups  xmm1, xmmword ptr [r14-50h]
0x18000b783  movups  xmmword ptr [rdi-50h], xmm1
0x18000b787  movups  xmm0, xmmword ptr [r14-40h]
0x18000b78c  movups  xmmword ptr [rdi-40h], xmm0
0x18000b790  movups  xmm1, xmmword ptr [r14-30h]
0x18000b795  movups  xmmword ptr [rdi-30h], xmm1
0x18000b799  movups  xmm0, xmmword ptr [r14-20h]
0x18000b79e  movups  xmmword ptr [rdi-20h], xmm0
0x18000b7a2  movups  xmm1, xmmword ptr [r14-10h]
0x18000b7a7  movups  xmmword ptr [rdi-10h], xmm1
0x18000b7ab  sub     rax, 1
0x18000b7af  jnz     short loc_18000B756
0x18000b7b1  movups  xmm0, xmmword ptr [r14]
0x18000b7b5  movups  xmmword ptr [rdi], xmm0
0x18000b7b8  movups  xmm1, xmmword ptr [r14+10h]
0x18000b7bd  movups  xmmword ptr [rdi+10h], xmm1
0x18000b7c1  movups  xmm0, xmmword ptr [r14+20h]
0x18000b7c6  movups  xmmword ptr [rdi+20h], xmm0
0x18000b7ca  movups  xmm1, xmmword ptr [r14+30h]
0x18000b7cf  movups  xmmword ptr [rdi+30h], xmm1
0x18000b7d3  movups  xmm0, xmmword ptr [r14+40h]
0x18000b7d8  movups  xmmword ptr [rdi+40h], xmm0
0x18000b7dc  movups  xmm1, xmmword ptr [r14+50h]
0x18000b7e1  movups  xmmword ptr [rdi+50h], xmm1
0x18000b7e5  movups  xmm0, xmmword ptr [r14+60h]
0x18000b7ea  movups  xmmword ptr [rdi+60h], xmm0
0x18000b7ee  mov     eax, [r14+70h]
0x18000b7f2  mov     [rdi+70h], eax
0x18000b7f5  jmp     loc_18000B698
0x18000b7fa  mov     eax, 8007000Dh
0x18000b7ff  jmp     loc_18000B6A2
0x18000b804  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000b80b  mov     r8d, ebx
0x18000b80e  lea     rdx, aStringcchlengt; "StringCchLength on WinStation Name fail"...
0x18000b815  mov     ecx, 8; int
0x18000b81a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b81f  mov     eax, ebx
0x18000b821  jmp     loc_18000B6A2
0x18000b826  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000b82d  mov     r8d, ebx
0x18000b830  lea     rdx, aStringcchcopyO_1; "StringCchCopy on WinStation Name failed"...
0x18000b837  mov     ecx, 8; int
0x18000b83c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b841  mov     eax, ebx
0x18000b843  jmp     loc_18000B69A
0x18000b848  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000b84f  mov     r8d, ebx
0x18000b852  lea     rdx, aStringcchcopyO; "StringCchCopy on User Name failed: 0x%x"...
0x18000b859  mov     ecx, 8; int
0x18000b85e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b863  mov     eax, ebx
0x18000b865  jmp     loc_18000B69A
```
