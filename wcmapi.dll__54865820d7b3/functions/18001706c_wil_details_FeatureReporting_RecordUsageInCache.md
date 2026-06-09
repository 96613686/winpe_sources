# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001706c`
- end: `0x1800171e4`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016ba4`

## callees

- `0x180016ec0`
- `0x180016f90`
- `0x18001706c`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r11d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 v13; // edx
  int v14; // r9d
  signed __int32 v15; // r11d
  signed __int32 v16; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_35;
    case 1:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_34;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v5 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
      goto LABEL_16;
    v6 = *((_DWORD *)a2 + 1);
    do
    {
      v7 = (v6 & 0x10) != 0 && ((v6 >> 5) & 0x3F) == v5;
      *(_DWORD *)(a1 + 16) = v7;
      v8 = v6;
      v6 = _InterlockedCompareExchange(
             a2 + 1,
             v6 ^ ((unsigned __int16)v6 ^ (unsigned __int16)(32 * v5)) & 0x7E0 | 0x10,
             v6);
    }
    while ( v8 != v6 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v9 = 0;
  v10 = a3 - 2;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 )
      {
        if ( v12 == 1 )
          v9 = 16;
      }
      else
      {
        v9 = 4;
      }
    }
    else
    {
      v9 = 8;
    }
  }
  else
  {
    v9 = 2;
  }
  v13 = *a2;
  v14 = 1;
  while ( 1 )
  {
    v15 = v13 | v9 | 1;
    *(_DWORD *)(a1 + 16) = (v13 | v9) == v13;
    if ( (v13 | v9) == v13 )
      v15 = v13 | v9;
    v16 = _InterlockedCompareExchange(a2, v15, v13);
    if ( v13 == v16 )
      break;
    v13 = v16;
  }
  if ( (v15 & 1) == 0 || (v13 & 1) != 0 )
    v14 = 0;
  *(_DWORD *)a1 = v14;
  return a1;
}

```

## disassembly

```asm
0x18001706c  mov     [rsp+arg_0], rbx
0x180017071  push    rdi
0x180017072  sub     rsp, 20h
0x180017076  xor     eax, eax
0x180017078  xorps   xmm0, xmm0
0x18001707b  mov     r10, rdx
0x18001707e  mov     rbx, rcx
0x180017081  mov     r9d, r8d
0x180017084  movups  xmmword ptr [rcx], xmm0
0x180017087  mov     [rcx+10h], rax
0x18001708b  test    r8d, r8d
0x18001708e  jz      loc_1800171C7
0x180017094  sub     r9d, 1
0x180017098  jz      loc_1800171B7
0x18001709e  sub     r9d, 1
0x1800170a2  jz      loc_18001713F
0x1800170a8  sub     r9d, 1
0x1800170ac  jz      loc_18001713F
0x1800170b2  sub     r9d, 1
0x1800170b6  jz      loc_1800171C7
0x1800170bc  sub     r9d, 1
0x1800170c0  jz      loc_1800171B7
0x1800170c6  sub     r9d, 1
0x1800170ca  jz      short loc_18001713F
0x1800170cc  cmp     r9d, 1
0x1800170d0  jz      short loc_18001713F
0x1800170d2  lea     r11d, [r8-140h]
0x1800170d9  lea     r9d, [rax+1]
0x1800170dd  cmp     r11d, 40h ; '@'
0x1800170e1  jge     short loc_18001712B
0x1800170e3  mov     eax, [rdx+4]
0x1800170e6  lea     ecx, [r9+0Fh]
0x1800170ea  mov     edi, r11d
0x1800170ed  shl     edi, 5
0x1800170f0  test    cl, al
0x1800170f2  jz      short loc_180017106
0x1800170f4  mov     edx, eax
0x1800170f6  shr     edx, 5
0x1800170f9  and     edx, 3Fh
0x1800170fc  cmp     edx, r11d
0x1800170ff  jnz     short loc_180017106
0x180017101  mov     edx, r9d
0x180017104  jmp     short loc_180017108
0x180017106  xor     edx, edx
0x180017108  mov     [rbx+10h], edx
0x18001710b  mov     edx, edi
0x18001710d  xor     edx, eax
0x18001710f  and     edx, 7E0h
0x180017115  xor     edx, eax
0x180017117  or      edx, ecx
0x180017119  lock cmpxchg [r10+4], edx
0x18001711f  jnz     short loc_1800170F0
0x180017121  cmp     dword ptr [rbx+10h], 0
0x180017125  jnz     loc_1800171D5
0x18001712b  mov     [rbx+8], r8d
0x18001712f  mov     [rbx+4], r9d
0x180017133  mov     dword ptr [rbx+0Ch], 0
0x18001713a  jmp     loc_1800171D5
0x18001713f  xor     ecx, ecx
0x180017141  sub     r8d, 2
0x180017145  jz      short loc_18001716D
0x180017147  sub     r8d, 1
0x18001714b  jz      short loc_180017166
0x18001714d  sub     r8d, 3
0x180017151  jz      short loc_18001715F
0x180017153  cmp     r8d, 1
0x180017157  jnz     short loc_180017172
0x180017159  lea     ecx, [r8+0Fh]
0x18001715d  jmp     short loc_180017172
0x18001715f  mov     ecx, 4
0x180017164  jmp     short loc_180017172
0x180017166  mov     ecx, 8
0x18001716b  jmp     short loc_180017172
0x18001716d  mov     ecx, 2
0x180017172  mov     edx, [rdx]
0x180017174  mov     r9d, 1
0x18001717a  xor     eax, eax
0x18001717c  mov     r8d, ecx
0x18001717f  or      r8d, edx
0x180017182  cmp     r8d, edx
0x180017185  mov     r11d, r8d
0x180017188  setz    al
0x18001718b  or      r11d, r9d
0x18001718e  cmp     r8d, edx
0x180017191  mov     [rbx+10h], eax
0x180017194  mov     eax, edx
0x180017196  cmovz   r11d, r8d
0x18001719a  lock cmpxchg [r10], r11d
0x18001719f  jz      short loc_1800171A5
0x1800171a1  mov     edx, eax
0x1800171a3  jmp     short loc_18001717A
0x1800171a5  test    r9b, r11b
0x1800171a8  jz      short loc_1800171AF
0x1800171aa  test    r9b, dl
0x1800171ad  jz      short loc_1800171B2
0x1800171af  xor     r9d, r9d
0x1800171b2  mov     [rbx], r9d
0x1800171b5  jmp     short loc_1800171D5
0x1800171b7  mov     r9, rbx
0x1800171ba  mov     edx, r8d
0x1800171bd  mov     rcx, r10
0x1800171c0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800171c5  jmp     short loc_1800171D5
0x1800171c7  mov     r9, rbx
0x1800171ca  mov     edx, r8d
0x1800171cd  mov     rcx, r10
0x1800171d0  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1800171d5  mov     rax, rbx
0x1800171d8  mov     rbx, [rsp+28h+arg_0]
0x1800171dd  add     rsp, 20h
0x1800171e1  pop     rdi
0x1800171e2  retn
```
