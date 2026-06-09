# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1400170e8`
- end: `0x140017264`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140017398`

## callees

- `0x140016f3c`
- `0x14001700c`
- `0x1400170e8`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  _DWORD *v6; // r9
  unsigned int v7; // r10d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 i; // edx
  signed __int32 v16; // r10d
  signed __int32 v17; // eax

  v6 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_32;
    case 1u:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_31;
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
  for ( i = *a2; ; i = v17 )
  {
    v16 = i | v11 | 1;
    v6[4] = (i | v11) == i;
    if ( (i | v11) == i )
      v16 = i | v11;
    v17 = _InterlockedCompareExchange(a2, v16, i);
    if ( i == v17 )
      break;
  }
  *v6 = (v16 & 1) != 0 && (i & 1) == 0;
  return v6;
}

```

## disassembly

```asm
0x1400170e8  mov     [rsp+arg_0], rbx
0x1400170ed  push    rdi
0x1400170ee  sub     rsp, 20h
0x1400170f2  xor     eax, eax
0x1400170f4  xorps   xmm0, xmm0
0x1400170f7  mov     edi, r9d
0x1400170fa  mov     r11, rdx
0x1400170fd  mov     r9, rcx
0x140017100  mov     r10d, r8d
0x140017103  movups  xmmword ptr [rcx], xmm0
0x140017106  mov     [rcx+10h], rax
0x14001710a  test    r8d, r8d
0x14001710d  jz      loc_14001724B
0x140017113  sub     r10d, 1
0x140017117  jz      loc_14001723E
0x14001711d  sub     r10d, 1
0x140017121  jz      loc_1400171C0
0x140017127  sub     r10d, 1
0x14001712b  jz      loc_1400171C0
0x140017131  sub     r10d, 1
0x140017135  jz      loc_14001724B
0x14001713b  sub     r10d, 1
0x14001713f  jz      loc_14001723E
0x140017145  sub     r10d, 1
0x140017149  jz      short loc_1400171C0
0x14001714b  cmp     r10d, 1
0x14001714f  jz      short loc_1400171C0
0x140017151  lea     r10d, [r8-140h]
0x140017158  cmp     r10d, 40h ; '@'
0x14001715c  jge     short loc_1400171AB
0x14001715e  mov     eax, [rdx+4]
0x140017161  mov     ebx, r10d
0x140017164  shl     ebx, 5
0x140017167  mov     ecx, 10h
0x14001716c  test    cl, al
0x14001716e  jz      short loc_140017184
0x140017170  mov     edx, eax
0x140017172  shr     edx, 5
0x140017175  and     edx, 3Fh
0x140017178  cmp     edx, r10d
0x14001717b  jnz     short loc_140017184
0x14001717d  mov     edx, 1
0x140017182  jmp     short loc_140017186
0x140017184  xor     edx, edx
0x140017186  mov     [r9+10h], edx
0x14001718a  mov     edx, ebx
0x14001718c  xor     edx, eax
0x14001718e  and     edx, 7E0h
0x140017194  xor     edx, eax
0x140017196  or      edx, ecx
0x140017198  lock cmpxchg [r11+4], edx
0x14001719e  jnz     short loc_14001716C
0x1400171a0  cmp     dword ptr [r9+10h], 0
0x1400171a5  jnz     loc_140017256
0x1400171ab  mov     [r9+8], r8d
0x1400171af  mov     dword ptr [r9+4], 1
0x1400171b7  mov     [r9+0Ch], edi
0x1400171bb  jmp     loc_140017256
0x1400171c0  xor     ecx, ecx
0x1400171c2  sub     r8d, 2
0x1400171c6  jz      short loc_1400171EE
0x1400171c8  sub     r8d, 1
0x1400171cc  jz      short loc_1400171E7
0x1400171ce  sub     r8d, 3
0x1400171d2  jz      short loc_1400171E0
0x1400171d4  cmp     r8d, 1
0x1400171d8  jnz     short loc_1400171F3
0x1400171da  lea     ecx, [r8+0Fh]
0x1400171de  jmp     short loc_1400171F3
0x1400171e0  mov     ecx, 4
0x1400171e5  jmp     short loc_1400171F3
0x1400171e7  mov     ecx, 8
0x1400171ec  jmp     short loc_1400171F3
0x1400171ee  mov     ecx, 2
0x1400171f3  mov     edx, [rdx]
0x1400171f5  xor     eax, eax
0x1400171f7  mov     r8d, ecx
0x1400171fa  or      r8d, edx
0x1400171fd  cmp     r8d, edx
0x140017200  mov     r10d, r8d
0x140017203  setz    al
0x140017206  or      r10d, 1
0x14001720a  cmp     r8d, edx
0x14001720d  mov     [r9+10h], eax
0x140017211  mov     eax, edx
0x140017213  cmovz   r10d, r8d
0x140017217  lock cmpxchg [r11], r10d
0x14001721c  jz      short loc_140017222
0x14001721e  mov     edx, eax
0x140017220  jmp     short loc_1400171F5
0x140017222  test    r10b, 1
0x140017226  setnz   cl
0x140017229  test    dl, 1
0x14001722c  setz    al
0x14001722f  test    al, cl
0x140017231  mov     eax, 0
0x140017236  setnz   al
0x140017239  mov     [r9], eax
0x14001723c  jmp     short loc_140017256
0x14001723e  mov     edx, r8d
0x140017241  mov     rcx, r11
0x140017244  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140017249  jmp     short loc_140017256
0x14001724b  mov     edx, r8d
0x14001724e  mov     rcx, r11
0x140017251  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140017256  mov     rbx, [rsp+28h+arg_0]
0x14001725b  mov     rax, r9
0x14001725e  add     rsp, 20h
0x140017262  pop     rdi
0x140017263  retn
```
