# CSmartSession::CopySessionExInfo(ulong,_WINSTATIONINFORMATIONEX *,ulong)

- ea: `0x180002df0`
- end: `0x1800032ab`
- name: `?CopySessionExInfo@CSmartSession@@QEAAJKPEAU_WINSTATIONINFORMATIONEX@@K@Z`
- size: `1211`
- prototype: `int(CSmartSession *__hidden this, unsigned int, struct _WINSTATIONINFORMATIONEX *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003480`

## callees

- `0x180002df0`
- `0x180005b40`
- `0x180032be6`

## string_xrefs

- `0x180003115`: `CSmartSession::CopySessionExInfo`
- `0x180003134`: `CSmartSession::CopySessionExInfo`
- `0x180003153`: `CSmartSession::CopySessionExInfo`
- `0x180003245`: `CSmartSession::CopySessionExInfo`
- `0x180003267`: `CSmartSession::CopySessionExInfo`
- `0x180003289`: `CSmartSession::CopySessionExInfo`
- `0x18000313e`: `StringCchCopy on Domain Name failed: 0x%x in %s`
- `0x180003271`: `StringCchCopy on WinStation Name failed: 0x%x in %s`
- `0x180003293`: `StringCchCopy on User Name failed: 0x%x in %s`

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
0x180002df0  mov     rax, rsp
0x180002df3  mov     [rax+10h], rbx
0x180002df7  push    rsi
0x180002df8  push    rdi
0x180002df9  push    r14
0x180002dfb  sub     rsp, 150h
0x180002e02  movaps  xmmword ptr [rax-28h], xmm6
0x180002e06  mov     rdi, r8
0x180002e09  movaps  xmmword ptr [rax-38h], xmm7
0x180002e0d  mov     esi, edx
0x180002e0f  movaps  xmmword ptr [rax-48h], xmm8
0x180002e14  mov     rbx, rcx
0x180002e17  movaps  xmmword ptr [rax-58h], xmm9
0x180002e1c  xor     edx, edx; Val
0x180002e1e  movaps  xmmword ptr [rax-68h], xmm10
0x180002e23  mov     r8d, 4C8h; Size
0x180002e29  mov     rcx, rdi; void *
0x180002e2c  movaps  xmmword ptr [rax-78h], xmm11
0x180002e31  call    memset_0
0x180002e36  cmp     dword ptr [rbx+48h], 1
0x180002e3a  movups  xmm0, xmmword ptr [rbx+50h]
0x180002e3e  mov     r14, [rbx+110h]
0x180002e45  movups  xmm1, xmmword ptr [rbx+60h]
0x180002e49  movups  xmm2, xmmword ptr [rbx+70h]
0x180002e4d  movups  xmm3, xmmword ptr [rbx+80h]
0x180002e54  movups  xmm4, xmmword ptr [rbx+90h]
0x180002e5b  movups  xmm5, xmmword ptr [rbx+0A0h]
0x180002e62  movups  xmm6, xmmword ptr [rbx+0B0h]
0x180002e69  movups  xmm7, xmmword ptr [rbx+0C0h]
0x180002e70  movups  xmm8, xmmword ptr [rbx+0D0h]
0x180002e78  movups  xmm10, xmmword ptr [rbx+0E0h]
0x180002e80  movups  xmm9, xmmword ptr [rbx+0F0h]
0x180002e88  movups  xmm11, xmmword ptr [rbx+100h]
0x180002e90  jnz     loc_18000323B
0x180002e96  mov     dword ptr [rdi], 1
0x180002e9c  movq    rax, xmm0
0x180002ea1  mov     [rdi+0Ch], eax
0x180002ea4  mov     r8d, 7FFFFFFFh
0x180002eaa  shr     rax, 20h
0x180002eae  mov     edx, r8d
0x180002eb1  mov     [rdi+10h], eax
0x180002eb4  lea     rax, [rsp+168h+var_140]
0x180002eb9  movups  xmmword ptr [rsp+20h], xmm0
0x180002ebe  mov     [rsp+168h+var_88], r14
0x180002ec6  movups  [rsp+168h+var_138], xmm1
0x180002ecb  mov     [rdi+8], esi
0x180002ece  movups  [rsp+168h+var_128], xmm2
0x180002ed3  movups  [rsp+168h+var_118], xmm3
0x180002ed8  movups  [rsp+168h+var_108], xmm4
0x180002edd  movups  [rsp+168h+var_F8], xmm5
0x180002ee2  movups  [rsp+168h+var_E8], xmm6
0x180002eea  movups  [rsp+168h+var_D8], xmm7
0x180002ef2  movups  [rsp+168h+var_C8], xmm8
0x180002efb  movups  [rsp+168h+var_B8], xmm10
0x180002f04  movups  [rsp+168h+var_A8], xmm9
0x180002f0d  movups  [rsp+168h+var_98], xmm11
0x180002f16  cmp     word ptr [rax], 0
0x180002f1a  jz      short loc_180002F26
0x180002f1c  add     rax, 2
0x180002f20  sub     rdx, 1
0x180002f24  jnz     short loc_180002F16
0x180002f26  xor     ecx, ecx
0x180002f28  mov     esi, 80070057h
0x180002f2d  test    rdx, rdx
0x180002f30  mov     ebx, esi
0x180002f32  cmovnz  ebx, ecx
0x180002f35  jz      loc_180003245
0x180002f3b  mov     r11d, 7FFFFFFEh
0x180002f41  mov     [rsp+168h+arg_0], rbp
0x180002f49  mov     eax, r11d
0x180002f4c  lea     rdx, [rsp+168h+var_140]
0x180002f51  mov     r9d, 21h ; '!'
0x180002f57  lea     rcx, [rdi+14h]
0x180002f5b  nop     dword ptr [rax+rax+00h]
0x180002f60  test    rax, rax
0x180002f63  jz      short loc_180002F84
0x180002f65  movzx   r10d, word ptr [rdx]
0x180002f69  test    r10w, r10w
0x180002f6d  jz      short loc_180002F84
0x180002f6f  mov     [rcx], r10w
0x180002f73  add     rdx, 2
0x180002f77  add     rcx, 2
0x180002f7b  dec     rax
0x180002f7e  sub     r9, 1
0x180002f82  jnz     short loc_180002F60
0x180002f84  xor     eax, eax
0x180002f86  lea     rdx, [rcx-2]
0x180002f8a  test    r9, r9
0x180002f8d  mov     ebp, 8007007Ah
0x180002f92  mov     ebx, ebp
0x180002f94  cmovnz  rdx, rcx
0x180002f98  cmovnz  ebx, eax
0x180002f9b  xor     ecx, ecx
0x180002f9d  mov     [rdx], cx
0x180002fa0  test    r9, r9
0x180002fa3  jz      loc_180003267
0x180002fa9  mov     rdx, r8
0x180002fac  lea     rax, [rsp+168h+var_E8+0Eh]
0x180002fb4  cmp     [rax], cx
0x180002fb7  jz      short loc_180002FC3
0x180002fb9  add     rax, 2
0x180002fbd  sub     rdx, 1
0x180002fc1  jnz     short loc_180002FB4
0x180002fc3  test    rdx, rdx
0x180002fc6  mov     ebx, esi
0x180002fc8  cmovnz  ebx, ecx
0x180002fcb  jz      loc_180003153
0x180002fd1  mov     rax, r11
0x180002fd4  lea     rdx, [rsp+168h+var_E8+0Eh]
0x180002fdc  mov     r9d, 15h
0x180002fe2  lea     rcx, [rdi+56h]
0x180002fe6  test    rax, rax
0x180002fe9  jz      short loc_18000300A
0x180002feb  movzx   r10d, word ptr [rdx]
0x180002fef  test    r10w, r10w
0x180002ff3  jz      short loc_18000300A
0x180002ff5  mov     [rcx], r10w
0x180002ff9  add     rdx, 2
0x180002ffd  add     rcx, 2
0x180003001  dec     rax
0x180003004  sub     r9, 1
0x180003008  jnz     short loc_180002FE6
0x18000300a  xor     eax, eax
0x18000300c  lea     rdx, [rcx-2]
0x180003010  test    r9, r9
0x180003013  mov     ebx, ebp
0x180003015  cmovnz  rdx, rcx
0x180003019  cmovnz  ebx, eax
0x18000301c  xor     ecx, ecx
0x18000301e  mov     [rdx], cx
0x180003021  test    r9, r9
0x180003024  jz      loc_180003289
0x18000302a  lea     rax, [rsp+168h+var_108+0Ah]
0x18000302f  nop
0x180003030  cmp     [rax], cx
0x180003033  jz      short loc_18000303F
0x180003035  add     rax, 2
0x180003039  sub     r8, 1
0x18000303d  jnz     short loc_180003030
0x18000303f  test    r8, r8
0x180003042  cmovnz  esi, ecx
0x180003045  jz      loc_180003115
0x18000304b  lea     rax, [rsp+168h+var_108+0Ah]
0x180003050  mov     r8d, 12h
0x180003056  lea     rcx, [rdi+80h]
0x18000305d  nop     dword ptr [rax]
0x180003060  test    r11, r11
0x180003063  jz      short loc_180003081
0x180003065  movzx   edx, word ptr [rax]
0x180003068  test    dx, dx
0x18000306b  jz      short loc_180003081
0x18000306d  mov     [rcx], dx
0x180003070  add     rax, 2
0x180003074  add     rcx, 2
0x180003078  dec     r11
0x18000307b  sub     r8, 1
0x18000307f  jnz     short loc_180003060
0x180003081  xor     eax, eax
0x180003083  lea     rdx, [rcx-2]
0x180003087  test    r8, r8
0x18000308a  cmovnz  rdx, rcx
0x18000308e  cmovnz  ebp, eax
0x180003091  xor     ecx, ecx
0x180003093  mov     [rdx], cx
0x180003096  test    r8, r8
0x180003099  jz      loc_180003134
0x18000309f  movsd   qword ptr [rdi+0B8h], xmm9
0x1800030a8  psrldq  xmm9, 8
0x1800030ae  psrldq  xmm10, 8
0x1800030b4  movq    qword ptr [rdi+0A8h], xmm9
0x1800030bd  movq    qword ptr [rdi+0B0h], xmm10
0x1800030c6  movsd   qword ptr [rdi+0C0h], xmm11
0x1800030cf  test    r14, r14
0x1800030d2  jnz     loc_180003175
0x1800030d8  xor     eax, eax
0x1800030da  mov     rbp, [rsp+168h+arg_0]
0x1800030e2  lea     r11, [rsp+168h+var_18]
0x1800030ea  mov     rbx, [r11+28h]
0x1800030ee  movaps  xmm6, xmmword ptr [r11-10h]
0x1800030f3  movaps  xmm7, xmmword ptr [r11-20h]
0x1800030f8  movaps  xmm8, xmmword ptr [r11-30h]
0x1800030fd  movaps  xmm9, xmmword ptr [r11-40h]
0x180003102  movaps  xmm10, xmmword ptr [r11-50h]
0x180003107  movaps  xmm11, xmmword ptr [r11-60h]
0x18000310c  mov     rsp, r11
0x18000310f  pop     r14
0x180003111  pop     rdi
0x180003112  pop     rsi
0x180003113  retn
0x180003115  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000311c  mov     r8d, esi
0x18000311f  lea     rdx, aStringcchlengt_1; "StringCchLength on Domain Name failed: "...
0x180003126  mov     ecx, 8; int
0x18000312b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003130  mov     eax, esi
0x180003132  jmp     short loc_1800030DA
0x180003134  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000313b  mov     r8d, ebp
0x18000313e  lea     rdx, aStringcchcopyO_0; "StringCchCopy on Domain Name failed: 0x"...
0x180003145  mov     ecx, 8; int
0x18000314a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000314f  mov     eax, ebp
0x180003151  jmp     short loc_1800030DA
0x180003153  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000315a  mov     r8d, ebx
0x18000315d  lea     rdx, aStringcchlengt_0; "StringCchLength on User Name failed: 0x"...
0x180003164  mov     ecx, 8; int
0x180003169  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000316e  mov     eax, ebx
0x180003170  jmp     loc_1800030DA
0x180003175  psrldq  xmm11, 8
0x18000317b  movd    eax, xmm11
0x180003180  cmp     eax, 3F4h
0x180003185  jb      loc_1800030D8
0x18000318b  add     rdi, 0D0h
0x180003192  mov     eax, 7
0x180003197  lea     rdi, [rdi+80h]
0x18000319e  movups  xmm0, xmmword ptr [r14]
0x1800031a2  lea     r14, [r14+80h]
0x1800031a9  movups  xmmword ptr [rdi-80h], xmm0
0x1800031ad  movups  xmm1, xmmword ptr [r14-70h]
0x1800031b2  movups  xmmword ptr [rdi-70h], xmm1
0x1800031b6  movups  xmm0, xmmword ptr [r14-60h]
0x1800031bb  movups  xmmword ptr [rdi-60h], xmm0
0x1800031bf  movups  xmm1, xmmword ptr [r14-50h]
0x1800031c4  movups  xmmword ptr [rdi-50h], xmm1
0x1800031c8  movups  xmm0, xmmword ptr [r14-40h]
0x1800031cd  movups  xmmword ptr [rdi-40h], xmm0
0x1800031d1  movups  xmm1, xmmword ptr [r14-30h]
0x1800031d6  movups  xmmword ptr [rdi-30h], xmm1
0x1800031da  movups  xmm0, xmmword ptr [r14-20h]
0x1800031df  movups  xmmword ptr [rdi-20h], xmm0
0x1800031e3  movups  xmm1, xmmword ptr [r14-10h]
0x1800031e8  movups  xmmword ptr [rdi-10h], xmm1
0x1800031ec  sub     rax, 1
0x1800031f0  jnz     short loc_180003197
0x1800031f2  movups  xmm0, xmmword ptr [r14]
0x1800031f6  movups  xmmword ptr [rdi], xmm0
0x1800031f9  movups  xmm1, xmmword ptr [r14+10h]
0x1800031fe  movups  xmmword ptr [rdi+10h], xmm1
0x180003202  movups  xmm0, xmmword ptr [r14+20h]
0x180003207  movups  xmmword ptr [rdi+20h], xmm0
0x18000320b  movups  xmm1, xmmword ptr [r14+30h]
0x180003210  movups  xmmword ptr [rdi+30h], xmm1
0x180003214  movups  xmm0, xmmword ptr [r14+40h]
0x180003219  movups  xmmword ptr [rdi+40h], xmm0
0x18000321d  movups  xmm1, xmmword ptr [r14+50h]
0x180003222  movups  xmmword ptr [rdi+50h], xmm1
0x180003226  movups  xmm0, xmmword ptr [r14+60h]
0x18000322b  movups  xmmword ptr [rdi+60h], xmm0
0x18000322f  mov     eax, [r14+70h]
0x180003233  mov     [rdi+70h], eax
0x180003236  jmp     loc_1800030D8
0x18000323b  mov     eax, 8007000Dh
0x180003240  jmp     loc_1800030E2
0x180003245  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000324c  mov     r8d, ebx
0x18000324f  lea     rdx, aStringcchlengt; "StringCchLength on WinStation Name fail"...
0x180003256  mov     ecx, 8; int
0x18000325b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003260  mov     eax, ebx
0x180003262  jmp     loc_1800030E2
0x180003267  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x18000326e  mov     r8d, ebx
0x180003271  lea     rdx, aStringcchcopyO_1; "StringCchCopy on WinStation Name failed"...
0x180003278  mov     ecx, 8; int
0x18000327d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003282  mov     eax, ebx
0x180003284  jmp     loc_1800030DA
0x180003289  lea     r9, aCsmartsessionC; "CSmartSession::CopySessionExInfo"
0x180003290  mov     r8d, ebx
0x180003293  lea     rdx, aStringcchcopyO; "StringCchCopy on User Name failed: 0x%x"...
0x18000329a  mov     ecx, 8; int
0x18000329f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800032a4  mov     eax, ebx
0x1800032a6  jmp     loc_1800030DA
```
