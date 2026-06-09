# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1400122d8`
- end: `0x1400125aa`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400126dc`

## callees

- `0x1400122d8`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  int v7; // r8d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  signed __int32 v12; // edx
  int v13; // ebx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  BOOL v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  signed __int32 v23; // eax
  signed __int32 v24; // edx
  BOOL v25; // ebp
  unsigned int v26; // eax
  int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // r9d
  signed __int32 v30; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v24 = *a2;
      v25 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v26 = v24 | 1;
        if ( (((v24 | 1u) >> 14) & 1) != v25 )
        {
          if ( ((v26 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v26 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v26 = v24 & 0xFFFFC01E | 1;
          }
          v27 = 0;
          if ( a3 == 4 )
            v27 = 0x4000;
          v26 = v26 & 0xFFFFBFFF | v27;
        }
        v28 = (v26 >> 5) & 0x1FF;
        v29 = v28 + 1;
        if ( v28 + 1 > 0x1FF || v29 < v28 )
        {
          LOWORD(v29) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v28;
        }
        v30 = _InterlockedCompareExchange(
                a2,
                v26 ^ ((unsigned __int16)v26 ^ (unsigned __int16)(32 * v29)) & 0x3FE0,
                v24);
        if ( v24 == v30 )
          break;
        v24 = v30;
      }
      *(_DWORD *)a1 = (v24 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v16 = *a2;
      v17 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v19 = 5;
            if ( a3 != 1 )
              v19 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v19;
          }
          v20 = 0;
          if ( a3 == 5 )
            v20 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v20;
        }
        v21 = (v18 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v18 ^ (v18 ^ (v22 << 15)) & 0x3F8000, v16);
        if ( v16 == v23 )
          break;
        v16 = v23;
      }
      *(_DWORD *)a1 = (v16 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( v7 >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return a1;
  }
LABEL_17:
  v11 = 0;
  switch ( a3 )
  {
    case 2:
      v11 = 2;
      break;
    case 3:
      v11 = 8;
      break;
    case 6:
      v11 = 4;
      break;
    case 7:
      v11 = 16;
      break;
  }
  v12 = *a2;
  v13 = 1;
  while ( 1 )
  {
    v14 = v12 | v11 | 1;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    if ( (v12 | v11) == v12 )
      v14 = v12 | v11;
    v15 = _InterlockedCompareExchange(a2, v14, v12);
    if ( v12 == v15 )
      break;
    v12 = v15;
  }
  if ( (v14 & 1) == 0 || (v12 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x1400122d8  push    rbx
0x1400122da  push    rbp
0x1400122db  push    rsi
0x1400122dc  push    rdi
0x1400122dd  xor     eax, eax
0x1400122df  xorps   xmm0, xmm0
0x1400122e2  mov     r10, rcx
0x1400122e5  mov     edi, r9d
0x1400122e8  mov     r11d, r8d
0x1400122eb  mov     rsi, rdx
0x1400122ee  movups  xmmword ptr [rcx], xmm0
0x1400122f1  mov     [rcx+10h], rax
0x1400122f5  mov     ecx, r8d
0x1400122f8  test    r8d, r8d
0x1400122fb  jz      loc_1400124D4
0x140012301  sub     ecx, 1
0x140012304  jz      loc_14001241B
0x14001230a  sub     ecx, 1
0x14001230d  jz      loc_1400123A2
0x140012313  sub     ecx, 1
0x140012316  jz      loc_1400123A2
0x14001231c  sub     ecx, 1
0x14001231f  jz      loc_1400124D4
0x140012325  sub     ecx, 1
0x140012328  jz      loc_14001241B
0x14001232e  sub     ecx, 1
0x140012331  jz      short loc_1400123A2
0x140012333  cmp     ecx, 1
0x140012336  jz      short loc_1400123A2
0x140012338  add     r8d, 0FFFFFEC0h
0x14001233f  lea     ebx, [rax+1]
0x140012342  cmp     r8d, 40h ; '@'
0x140012346  jge     short loc_140012391
0x140012348  mov     eax, [rdx+4]
0x14001234b  lea     ecx, [rbx+0Fh]
0x14001234e  mov     r9d, r8d
0x140012351  shl     r9d, 5
0x140012355  test    cl, al
0x140012357  jz      short loc_14001236A
0x140012359  mov     edx, eax
0x14001235b  shr     edx, 5
0x14001235e  and     edx, 3Fh
0x140012361  cmp     edx, r8d
0x140012364  jnz     short loc_14001236A
0x140012366  mov     edx, ebx
0x140012368  jmp     short loc_14001236C
0x14001236a  xor     edx, edx
0x14001236c  mov     [r10+10h], edx
0x140012370  mov     edx, r9d
0x140012373  xor     edx, eax
0x140012375  and     edx, 7E0h
0x14001237b  xor     edx, eax
0x14001237d  or      edx, ecx
0x14001237f  lock cmpxchg [rsi+4], edx
0x140012384  jnz     short loc_140012355
0x140012386  cmp     dword ptr [r10+10h], 0
0x14001238b  jnz     loc_1400125A2
0x140012391  mov     [r10+8], r11d
0x140012395  mov     [r10+4], ebx
0x140012399  mov     [r10+0Ch], edi
0x14001239d  jmp     loc_1400125A2
0x1400123a2  xor     ecx, ecx
0x1400123a4  sub     r11d, 2
0x1400123a8  jz      short loc_1400123D0
0x1400123aa  sub     r11d, 1
0x1400123ae  jz      short loc_1400123C9
0x1400123b0  sub     r11d, 3
0x1400123b4  jz      short loc_1400123C2
0x1400123b6  cmp     r11d, 1
0x1400123ba  jnz     short loc_1400123D5
0x1400123bc  lea     ecx, [r11+0Fh]
0x1400123c0  jmp     short loc_1400123D5
0x1400123c2  mov     ecx, 4
0x1400123c7  jmp     short loc_1400123D5
0x1400123c9  mov     ecx, 8
0x1400123ce  jmp     short loc_1400123D5
0x1400123d0  mov     ecx, 2
0x1400123d5  mov     edx, [rdx]
0x1400123d7  mov     ebx, 1
0x1400123dc  xor     eax, eax
0x1400123de  mov     r8d, ecx
0x1400123e1  or      r8d, edx
0x1400123e4  cmp     r8d, edx
0x1400123e7  mov     r9d, r8d
0x1400123ea  setz    al
0x1400123ed  or      r9d, ebx
0x1400123f0  cmp     r8d, edx
0x1400123f3  mov     [r10+10h], eax
0x1400123f7  mov     eax, edx
0x1400123f9  cmovz   r9d, r8d
0x1400123fd  lock cmpxchg [rsi], r9d
0x140012402  jz      short loc_140012408
0x140012404  mov     edx, eax
0x140012406  jmp     short loc_1400123DC
0x140012408  test    bl, r9b
0x14001240b  jz      short loc_140012411
0x14001240d  test    bl, dl
0x14001240f  jz      short loc_140012413
0x140012411  xor     ebx, ebx
0x140012413  mov     [r10], ebx
0x140012416  jmp     loc_1400125A2
0x14001241b  mov     ecx, [rdx]
0x14001241d  xor     r9d, r9d
0x140012420  cmp     r11d, 5
0x140012424  mov     ebx, 1
0x140012429  setz    r9b
0x14001242d  mov     eax, ecx
0x14001242f  mov     dword ptr [r10+4], 0
0x140012437  or      eax, ebx
0x140012439  mov     edx, eax
0x14001243b  shr     edx, 16h
0x14001243e  and     edx, ebx
0x140012440  cmp     edx, r9d
0x140012443  jz      short loc_140012485
0x140012445  mov     r8d, eax
0x140012448  shr     r8d, 0Fh
0x14001244c  and     r8d, 7Fh
0x140012450  jbe     short loc_14001246A
0x140012452  cmp     r11d, ebx
0x140012455  mov     [r10+4], r8d
0x140012459  mov     edx, 5
0x14001245e  cmovnz  edx, ebx
0x140012461  and     eax, 0FFC07FFFh
0x140012466  mov     [r10+8], edx
0x14001246a  xor     r8d, r8d
0x14001246d  mov     edx, 400000h
0x140012472  cmp     r11d, 5
0x140012476  cmovz   r8d, edx
0x14001247a  mov     edx, eax
0x14001247c  btr     edx, 16h
0x140012480  mov     eax, r8d
0x140012483  or      eax, edx
0x140012485  mov     edx, eax
0x140012487  shr     edx, 0Fh
0x14001248a  and     edx, 7Fh
0x14001248d  lea     r8d, [rdx+1]
0x140012491  cmp     r8d, 7Fh
0x140012495  ja      short loc_14001249C
0x140012497  cmp     r8d, edx
0x14001249a  jnb     short loc_1400124A7
0x14001249c  mov     r8d, ebx
0x14001249f  mov     [r10+8], r11d
0x1400124a3  mov     [r10+4], edx
0x1400124a7  shl     r8d, 0Fh
0x1400124ab  xor     r8d, eax
0x1400124ae  and     r8d, 3F8000h
0x1400124b5  xor     r8d, eax
0x1400124b8  mov     eax, ecx
0x1400124ba  lock cmpxchg [rsi], r8d
0x1400124bf  jz      short loc_1400124C8
0x1400124c1  mov     ecx, eax
0x1400124c3  jmp     loc_14001242D
0x1400124c8  not     ecx
0x1400124ca  and     ecx, ebx
0x1400124cc  mov     [r10], ecx
0x1400124cf  jmp     loc_14001259A
0x1400124d4  mov     edx, [rdx]
0x1400124d6  xor     ebp, ebp
0x1400124d8  lea     ecx, [rbp+4]
0x1400124db  cmp     r11d, ecx
0x1400124de  lea     ebx, [rcx-3]
0x1400124e1  setz    bpl
0x1400124e5  mov     eax, edx
0x1400124e7  mov     dword ptr [r10+4], 0
0x1400124ef  or      eax, ebx
0x1400124f1  mov     r8d, eax
0x1400124f4  shr     r8d, 0Eh
0x1400124f8  and     r8d, ebx
0x1400124fb  cmp     r8d, ebp
0x1400124fe  jz      short loc_140012547
0x140012500  mov     edi, eax
0x140012502  shr     edi, 5
0x140012505  and     edi, 1FFh
0x14001250b  jbe     short loc_140012529
0x14001250d  mov     r8d, r11d
0x140012510  mov     [r10+4], edi
0x140012514  neg     r8d
0x140012517  sbb     r9d, r9d
0x14001251a  not     r9d
0x14001251d  and     r9d, ecx
0x140012520  mov     [r10+8], r9d
0x140012524  and     eax, 0FFFFC01Fh
0x140012529  xor     r9d, r9d
0x14001252c  mov     r8d, 4000h
0x140012532  cmp     r11d, ecx
0x140012535  cmovz   r9d, r8d
0x140012539  mov     r8d, eax
0x14001253c  btr     r8d, 0Eh
0x140012541  mov     eax, r9d
0x140012544  or      eax, r8d
0x140012547  mov     r8d, eax
0x14001254a  shr     r8d, 5
0x14001254e  and     r8d, 1FFh
0x140012555  lea     r9d, [r8+1]
0x140012559  cmp     r9d, 1FFh
0x140012560  ja      short loc_140012567
0x140012562  cmp     r9d, r8d
0x140012565  jnb     short loc_140012572
0x140012567  mov     r9d, ebx
0x14001256a  mov     [r10+8], r11d
0x14001256e  mov     [r10+4], r8d
0x140012572  shl     r9d, 5
0x140012576  xor     r9d, eax
0x140012579  and     r9d, 3FE0h
0x140012580  xor     r9d, eax
0x140012583  mov     eax, edx
0x140012585  lock cmpxchg [rsi], r9d
0x14001258a  jz      short loc_140012593
0x14001258c  mov     edx, eax
0x14001258e  jmp     loc_1400124E5
0x140012593  not     edx
0x140012595  and     edx, ebx
0x140012597  mov     [r10], edx
0x14001259a  mov     dword ptr [r10+10h], 0
0x1400125a2  mov     rax, r10
0x1400125a5  pop     rdi
0x1400125a6  pop     rsi
0x1400125a7  pop     rbp
0x1400125a8  pop     rbx
0x1400125a9  retn
```
