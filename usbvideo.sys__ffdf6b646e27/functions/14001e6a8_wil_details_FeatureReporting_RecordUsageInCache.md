# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14001e6a8`
- end: `0x14001e825`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001e8b4`

## callees

- `0x14001e4fc`
- `0x14001e5cc`
- `0x14001e6a8`

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
0x14001e6a8  mov     [rsp+arg_0], rbx
0x14001e6ad  push    rdi
0x14001e6ae  sub     rsp, 20h
0x14001e6b2  xor     eax, eax
0x14001e6b4  xorps   xmm0, xmm0
0x14001e6b7  mov     edi, r9d
0x14001e6ba  mov     r11, rdx
0x14001e6bd  mov     r9, rcx
0x14001e6c0  mov     r10d, r8d
0x14001e6c3  movups  xmmword ptr [rcx], xmm0
0x14001e6c6  mov     [rcx+10h], rax
0x14001e6ca  test    r8d, r8d
0x14001e6cd  jz      loc_14001E80B
0x14001e6d3  sub     r10d, 1
0x14001e6d7  jz      loc_14001E7FE
0x14001e6dd  sub     r10d, 1
0x14001e6e1  jz      loc_14001E780
0x14001e6e7  sub     r10d, 1
0x14001e6eb  jz      loc_14001E780
0x14001e6f1  sub     r10d, 1
0x14001e6f5  jz      loc_14001E80B
0x14001e6fb  sub     r10d, 1
0x14001e6ff  jz      loc_14001E7FE
0x14001e705  sub     r10d, 1
0x14001e709  jz      short loc_14001E780
0x14001e70b  cmp     r10d, 1
0x14001e70f  jz      short loc_14001E780
0x14001e711  lea     r10d, [r8-140h]
0x14001e718  cmp     r10d, 40h ; '@'
0x14001e71c  jge     short loc_14001E76B
0x14001e71e  mov     eax, [rdx+4]
0x14001e721  mov     ebx, r10d
0x14001e724  shl     ebx, 5
0x14001e727  mov     ecx, 10h
0x14001e72c  test    cl, al
0x14001e72e  jz      short loc_14001E744
0x14001e730  mov     edx, eax
0x14001e732  shr     edx, 5
0x14001e735  and     edx, 3Fh
0x14001e738  cmp     edx, r10d
0x14001e73b  jnz     short loc_14001E744
0x14001e73d  mov     edx, 1
0x14001e742  jmp     short loc_14001E746
0x14001e744  xor     edx, edx
0x14001e746  mov     [r9+10h], edx
0x14001e74a  mov     edx, ebx
0x14001e74c  xor     edx, eax
0x14001e74e  and     edx, 7E0h
0x14001e754  xor     edx, eax
0x14001e756  or      edx, ecx
0x14001e758  lock cmpxchg [r11+4], edx
0x14001e75e  jnz     short loc_14001E72C
0x14001e760  cmp     dword ptr [r9+10h], 0
0x14001e765  jnz     loc_14001E816
0x14001e76b  mov     [r9+8], r8d
0x14001e76f  mov     dword ptr [r9+4], 1
0x14001e777  mov     [r9+0Ch], edi
0x14001e77b  jmp     loc_14001E816
0x14001e780  xor     ecx, ecx
0x14001e782  sub     r8d, 2
0x14001e786  jz      short loc_14001E7AE
0x14001e788  sub     r8d, 1
0x14001e78c  jz      short loc_14001E7A7
0x14001e78e  sub     r8d, 3
0x14001e792  jz      short loc_14001E7A0
0x14001e794  cmp     r8d, 1
0x14001e798  jnz     short loc_14001E7B3
0x14001e79a  lea     ecx, [r8+0Fh]
0x14001e79e  jmp     short loc_14001E7B3
0x14001e7a0  mov     ecx, 4
0x14001e7a5  jmp     short loc_14001E7B3
0x14001e7a7  mov     ecx, 8
0x14001e7ac  jmp     short loc_14001E7B3
0x14001e7ae  mov     ecx, 2
0x14001e7b3  mov     edx, [rdx]
0x14001e7b5  xor     eax, eax
0x14001e7b7  mov     r8d, ecx
0x14001e7ba  or      r8d, edx
0x14001e7bd  cmp     r8d, edx
0x14001e7c0  mov     r10d, r8d
0x14001e7c3  setz    al
0x14001e7c6  or      r10d, 1
0x14001e7ca  cmp     r8d, edx
0x14001e7cd  mov     [r9+10h], eax
0x14001e7d1  mov     eax, edx
0x14001e7d3  cmovz   r10d, r8d
0x14001e7d7  lock cmpxchg [r11], r10d
0x14001e7dc  jz      short loc_14001E7E2
0x14001e7de  mov     edx, eax
0x14001e7e0  jmp     short loc_14001E7B5
0x14001e7e2  test    r10b, 1
0x14001e7e6  setnz   cl
0x14001e7e9  test    dl, 1
0x14001e7ec  setz    al
0x14001e7ef  test    al, cl
0x14001e7f1  mov     eax, 0
0x14001e7f6  setnz   al
0x14001e7f9  mov     [r9], eax
0x14001e7fc  jmp     short loc_14001E816
0x14001e7fe  mov     edx, r8d
0x14001e801  mov     rcx, r11
0x14001e804  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14001e809  jmp     short loc_14001E816
0x14001e80b  mov     edx, r8d
0x14001e80e  mov     rcx, r11
0x14001e811  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14001e816  mov     rbx, [rsp+28h+arg_0]
0x14001e81b  mov     rax, r9
0x14001e81e  add     rsp, 20h
0x14001e822  pop     rdi
0x14001e823  retn
```
