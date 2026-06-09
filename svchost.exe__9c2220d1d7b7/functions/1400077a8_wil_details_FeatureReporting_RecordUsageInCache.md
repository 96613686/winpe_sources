# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1400077a8`
- end: `0x140007924`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400079a8`

## callees

- `0x1400075fc`
- `0x1400076cc`
- `0x1400077a8`

## pseudocode

```c
int *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  int *v6; // r9
  unsigned int v7; // ebx
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 v15; // edx
  int v16; // r10d
  signed __int32 v17; // ebx
  signed __int32 v18; // eax

  v6 = (int *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_35;
    case 1u:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_34;
  }
  if ( a3 - 6 >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)(a3 - 320) >= 64 )
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
    return v6;
  }
LABEL_17:
  v11 = 0;
  v12 = a3 - 2;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 3;
      if ( v14 )
      {
        if ( v14 == 1 )
          v11 = 16;
      }
      else
      {
        v11 = 4;
      }
    }
    else
    {
      v11 = 8;
    }
  }
  else
  {
    v11 = 2;
  }
  v15 = *a2;
  v16 = 1;
  while ( 1 )
  {
    v17 = v15 | v11 | 1;
    v6[4] = (v15 | v11) == v15;
    if ( (v15 | v11) == v15 )
      v17 = v15 | v11;
    v18 = _InterlockedCompareExchange(a2, v17, v15);
    if ( v15 == v18 )
      break;
    v15 = v18;
  }
  if ( (v17 & 1) == 0 || (v15 & 1) != 0 )
    v16 = 0;
  *v6 = v16;
  return v6;
}

```

## disassembly

```asm
0x1400077a8  mov     [rsp+arg_0], rbx
0x1400077ad  mov     [rsp+arg_8], rsi
0x1400077b2  push    rdi
0x1400077b3  sub     rsp, 20h
0x1400077b7  xor     eax, eax
0x1400077b9  xorps   xmm0, xmm0
0x1400077bc  mov     esi, r9d
0x1400077bf  mov     r11, rdx
0x1400077c2  mov     r9, rcx
0x1400077c5  mov     r10d, r8d
0x1400077c8  movups  xmmword ptr [rcx], xmm0
0x1400077cb  mov     [rcx+10h], rax
0x1400077cf  test    r8d, r8d
0x1400077d2  jz      loc_140007905
0x1400077d8  sub     r10d, 1
0x1400077dc  jz      loc_1400078F8
0x1400077e2  sub     r10d, 1
0x1400077e6  jz      loc_14000787F
0x1400077ec  sub     r10d, 1
0x1400077f0  jz      loc_14000787F
0x1400077f6  sub     r10d, 1
0x1400077fa  jz      loc_140007905
0x140007800  sub     r10d, 1
0x140007804  jz      loc_1400078F8
0x14000780a  sub     r10d, 1
0x14000780e  jz      short loc_14000787F
0x140007810  cmp     r10d, 1
0x140007814  jz      short loc_14000787F
0x140007816  lea     ebx, [r8-140h]
0x14000781d  lea     r10d, [rax+1]
0x140007821  cmp     ebx, 40h ; '@'
0x140007824  jge     short loc_14000786E
0x140007826  mov     eax, [rdx+4]
0x140007829  lea     ecx, [r10+0Fh]
0x14000782d  mov     edi, ebx
0x14000782f  shl     edi, 5
0x140007832  test    cl, al
0x140007834  jz      short loc_140007847
0x140007836  mov     edx, eax
0x140007838  shr     edx, 5
0x14000783b  and     edx, 3Fh
0x14000783e  cmp     edx, ebx
0x140007840  jnz     short loc_140007847
0x140007842  mov     edx, r10d
0x140007845  jmp     short loc_140007849
0x140007847  xor     edx, edx
0x140007849  mov     [r9+10h], edx
0x14000784d  mov     edx, edi
0x14000784f  xor     edx, eax
0x140007851  and     edx, 7E0h
0x140007857  xor     edx, eax
0x140007859  or      edx, ecx
0x14000785b  lock cmpxchg [r11+4], edx
0x140007861  jnz     short loc_140007832
0x140007863  cmp     dword ptr [r9+10h], 0
0x140007868  jnz     loc_140007910
0x14000786e  mov     [r9+8], r8d
0x140007872  mov     [r9+4], r10d
0x140007876  mov     [r9+0Ch], esi
0x14000787a  jmp     loc_140007910
0x14000787f  xor     ecx, ecx
0x140007881  sub     r8d, 2
0x140007885  jz      short loc_1400078AD
0x140007887  sub     r8d, 1
0x14000788b  jz      short loc_1400078A6
0x14000788d  sub     r8d, 3
0x140007891  jz      short loc_14000789F
0x140007893  cmp     r8d, 1
0x140007897  jnz     short loc_1400078B2
0x140007899  lea     ecx, [r8+0Fh]
0x14000789d  jmp     short loc_1400078B2
0x14000789f  mov     ecx, 4
0x1400078a4  jmp     short loc_1400078B2
0x1400078a6  mov     ecx, 8
0x1400078ab  jmp     short loc_1400078B2
0x1400078ad  mov     ecx, 2
0x1400078b2  mov     edx, [rdx]
0x1400078b4  mov     r10d, 1
0x1400078ba  xor     eax, eax
0x1400078bc  mov     r8d, ecx
0x1400078bf  or      r8d, edx
0x1400078c2  cmp     r8d, edx
0x1400078c5  mov     ebx, r8d
0x1400078c8  setz    al
0x1400078cb  or      ebx, r10d
0x1400078ce  cmp     r8d, edx
0x1400078d1  mov     [r9+10h], eax
0x1400078d5  mov     eax, edx
0x1400078d7  cmovz   ebx, r8d
0x1400078db  lock cmpxchg [r11], ebx
0x1400078e0  jz      short loc_1400078E6
0x1400078e2  mov     edx, eax
0x1400078e4  jmp     short loc_1400078BA
0x1400078e6  test    r10b, bl
0x1400078e9  jz      short loc_1400078F0
0x1400078eb  test    r10b, dl
0x1400078ee  jz      short loc_1400078F3
0x1400078f0  xor     r10d, r10d
0x1400078f3  mov     [r9], r10d
0x1400078f6  jmp     short loc_140007910
0x1400078f8  mov     edx, r8d
0x1400078fb  mov     rcx, r11
0x1400078fe  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140007903  jmp     short loc_140007910
0x140007905  mov     edx, r8d
0x140007908  mov     rcx, r11
0x14000790b  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140007910  mov     rbx, [rsp+28h+arg_0]
0x140007915  mov     rax, r9
0x140007918  mov     rsi, [rsp+28h+arg_8]
0x14000791d  add     rsp, 20h
0x140007921  pop     rdi
0x140007922  retn
```
