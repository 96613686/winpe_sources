# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18003c508`
- end: `0x18003c67e`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003a450`

## callees

- `0x18003c35c`
- `0x18003c42c`
- `0x18003c508`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r9d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 i; // edx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_31;
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
  for ( i = *a2; ; i = v15 )
  {
    v14 = i | v9 | 1;
    *(_DWORD *)(a1 + 16) = (i | v9) == i;
    if ( (i | v9) == i )
      v14 = i | v9;
    v15 = _InterlockedCompareExchange(a2, v14, i);
    if ( i == v15 )
      break;
  }
  *(_DWORD *)a1 = (v14 & 1) != 0 && (i & 1) == 0;
  return a1;
}

```

## disassembly

```asm
0x18003c508  push    rbx
0x18003c50a  sub     rsp, 20h
0x18003c50e  xor     eax, eax
0x18003c510  xorps   xmm0, xmm0
0x18003c513  mov     r10, rdx
0x18003c516  mov     rbx, rcx
0x18003c519  mov     r9d, r8d
0x18003c51c  movups  xmmword ptr [rcx], xmm0
0x18003c51f  mov     [rcx+10h], rax
0x18003c523  test    r8d, r8d
0x18003c526  jz      loc_18003C667
0x18003c52c  sub     r9d, 1
0x18003c530  jz      loc_18003C657
0x18003c536  sub     r9d, 1
0x18003c53a  jz      loc_18003C5DB
0x18003c540  sub     r9d, 1
0x18003c544  jz      loc_18003C5DB
0x18003c54a  sub     r9d, 1
0x18003c54e  jz      loc_18003C667
0x18003c554  sub     r9d, 1
0x18003c558  jz      loc_18003C657
0x18003c55e  sub     r9d, 1
0x18003c562  jz      short loc_18003C5DB
0x18003c564  cmp     r9d, 1
0x18003c568  jz      short loc_18003C5DB
0x18003c56a  lea     r9d, [r8-140h]
0x18003c571  cmp     r9d, 40h ; '@'
0x18003c575  jge     short loc_18003C5C4
0x18003c577  mov     eax, [rdx+4]
0x18003c57a  mov     r11d, r9d
0x18003c57d  shl     r11d, 5
0x18003c581  mov     ecx, 10h
0x18003c586  test    cl, al
0x18003c588  jz      short loc_18003C59E
0x18003c58a  mov     edx, eax
0x18003c58c  shr     edx, 5
0x18003c58f  and     edx, 3Fh
0x18003c592  cmp     edx, r9d
0x18003c595  jnz     short loc_18003C59E
0x18003c597  mov     edx, 1
0x18003c59c  jmp     short loc_18003C5A0
0x18003c59e  xor     edx, edx
0x18003c5a0  mov     [rbx+10h], edx
0x18003c5a3  mov     edx, r11d
0x18003c5a6  xor     edx, eax
0x18003c5a8  and     edx, 7E0h
0x18003c5ae  xor     edx, eax
0x18003c5b0  or      edx, ecx
0x18003c5b2  lock cmpxchg [r10+4], edx
0x18003c5b8  jnz     short loc_18003C586
0x18003c5ba  cmp     dword ptr [rbx+10h], 0
0x18003c5be  jnz     loc_18003C675
0x18003c5c4  mov     [rbx+8], r8d
0x18003c5c8  mov     dword ptr [rbx+4], 1
0x18003c5cf  mov     dword ptr [rbx+0Ch], 0
0x18003c5d6  jmp     loc_18003C675
0x18003c5db  xor     ecx, ecx
0x18003c5dd  sub     r8d, 2
0x18003c5e1  jz      short loc_18003C609
0x18003c5e3  sub     r8d, 1
0x18003c5e7  jz      short loc_18003C602
0x18003c5e9  sub     r8d, 3
0x18003c5ed  jz      short loc_18003C5FB
0x18003c5ef  cmp     r8d, 1
0x18003c5f3  jnz     short loc_18003C60E
0x18003c5f5  lea     ecx, [r8+0Fh]
0x18003c5f9  jmp     short loc_18003C60E
0x18003c5fb  mov     ecx, 4
0x18003c600  jmp     short loc_18003C60E
0x18003c602  mov     ecx, 8
0x18003c607  jmp     short loc_18003C60E
0x18003c609  mov     ecx, 2
0x18003c60e  mov     edx, [rdx]
0x18003c610  xor     eax, eax
0x18003c612  mov     r8d, ecx
0x18003c615  or      r8d, edx
0x18003c618  cmp     r8d, edx
0x18003c61b  mov     r9d, r8d
0x18003c61e  setz    al
0x18003c621  or      r9d, 1
0x18003c625  cmp     r8d, edx
0x18003c628  mov     [rbx+10h], eax
0x18003c62b  mov     eax, edx
0x18003c62d  cmovz   r9d, r8d
0x18003c631  lock cmpxchg [r10], r9d
0x18003c636  jz      short loc_18003C63C
0x18003c638  mov     edx, eax
0x18003c63a  jmp     short loc_18003C610
0x18003c63c  test    r9b, 1
0x18003c640  setnz   cl
0x18003c643  test    dl, 1
0x18003c646  setz    al
0x18003c649  test    al, cl
0x18003c64b  mov     eax, 0
0x18003c650  setnz   al
0x18003c653  mov     [rbx], eax
0x18003c655  jmp     short loc_18003C675
0x18003c657  mov     r9, rbx
0x18003c65a  mov     edx, r8d
0x18003c65d  mov     rcx, r10
0x18003c660  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18003c665  jmp     short loc_18003C675
0x18003c667  mov     r9, rbx
0x18003c66a  mov     edx, r8d
0x18003c66d  mov     rcx, r10
0x18003c670  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18003c675  mov     rax, rbx
0x18003c678  add     rsp, 20h
0x18003c67c  pop     rbx
0x18003c67d  retn
```
