# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14001186c`
- end: `0x1400119e9`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140011a78`

## callees

- `0x140010574`
- `0x14001179c`
- `0x14001186c`

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
0x14001186c  mov     [rsp+arg_0], rbx
0x140011871  push    rdi
0x140011872  sub     rsp, 20h
0x140011876  xor     eax, eax
0x140011878  xorps   xmm0, xmm0
0x14001187b  mov     edi, r9d
0x14001187e  mov     r11, rdx
0x140011881  mov     r9, rcx
0x140011884  mov     r10d, r8d
0x140011887  movups  xmmword ptr [rcx], xmm0
0x14001188a  mov     [rcx+10h], rax
0x14001188e  test    r8d, r8d
0x140011891  jz      loc_1400119CF
0x140011897  sub     r10d, 1
0x14001189b  jz      loc_1400119C2
0x1400118a1  sub     r10d, 1
0x1400118a5  jz      loc_140011944
0x1400118ab  sub     r10d, 1
0x1400118af  jz      loc_140011944
0x1400118b5  sub     r10d, 1
0x1400118b9  jz      loc_1400119CF
0x1400118bf  sub     r10d, 1
0x1400118c3  jz      loc_1400119C2
0x1400118c9  sub     r10d, 1
0x1400118cd  jz      short loc_140011944
0x1400118cf  cmp     r10d, 1
0x1400118d3  jz      short loc_140011944
0x1400118d5  lea     r10d, [r8-140h]
0x1400118dc  cmp     r10d, 40h ; '@'
0x1400118e0  jge     short loc_14001192F
0x1400118e2  mov     eax, [rdx+4]
0x1400118e5  mov     ebx, r10d
0x1400118e8  shl     ebx, 5
0x1400118eb  mov     ecx, 10h
0x1400118f0  test    cl, al
0x1400118f2  jz      short loc_140011908
0x1400118f4  mov     edx, eax
0x1400118f6  shr     edx, 5
0x1400118f9  and     edx, 3Fh
0x1400118fc  cmp     edx, r10d
0x1400118ff  jnz     short loc_140011908
0x140011901  mov     edx, 1
0x140011906  jmp     short loc_14001190A
0x140011908  xor     edx, edx
0x14001190a  mov     [r9+10h], edx
0x14001190e  mov     edx, ebx
0x140011910  xor     edx, eax
0x140011912  and     edx, 7E0h
0x140011918  xor     edx, eax
0x14001191a  or      edx, ecx
0x14001191c  lock cmpxchg [r11+4], edx
0x140011922  jnz     short loc_1400118F0
0x140011924  cmp     dword ptr [r9+10h], 0
0x140011929  jnz     loc_1400119DA
0x14001192f  mov     [r9+8], r8d
0x140011933  mov     dword ptr [r9+4], 1
0x14001193b  mov     [r9+0Ch], edi
0x14001193f  jmp     loc_1400119DA
0x140011944  xor     ecx, ecx
0x140011946  sub     r8d, 2
0x14001194a  jz      short loc_140011972
0x14001194c  sub     r8d, 1
0x140011950  jz      short loc_14001196B
0x140011952  sub     r8d, 3
0x140011956  jz      short loc_140011964
0x140011958  cmp     r8d, 1
0x14001195c  jnz     short loc_140011977
0x14001195e  lea     ecx, [r8+0Fh]
0x140011962  jmp     short loc_140011977
0x140011964  mov     ecx, 4
0x140011969  jmp     short loc_140011977
0x14001196b  mov     ecx, 8
0x140011970  jmp     short loc_140011977
0x140011972  mov     ecx, 2
0x140011977  mov     edx, [rdx]
0x140011979  xor     eax, eax
0x14001197b  mov     r8d, ecx
0x14001197e  or      r8d, edx
0x140011981  cmp     r8d, edx
0x140011984  mov     r10d, r8d
0x140011987  setz    al
0x14001198a  or      r10d, 1
0x14001198e  cmp     r8d, edx
0x140011991  mov     [r9+10h], eax
0x140011995  mov     eax, edx
0x140011997  cmovz   r10d, r8d
0x14001199b  lock cmpxchg [r11], r10d
0x1400119a0  jz      short loc_1400119A6
0x1400119a2  mov     edx, eax
0x1400119a4  jmp     short loc_140011979
0x1400119a6  test    r10b, 1
0x1400119aa  setnz   cl
0x1400119ad  test    dl, 1
0x1400119b0  setz    al
0x1400119b3  test    al, cl
0x1400119b5  mov     eax, 0
0x1400119ba  setnz   al
0x1400119bd  mov     [r9], eax
0x1400119c0  jmp     short loc_1400119DA
0x1400119c2  mov     edx, r8d
0x1400119c5  mov     rcx, r11
0x1400119c8  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1400119cd  jmp     short loc_1400119DA
0x1400119cf  mov     edx, r8d
0x1400119d2  mov     rcx, r11
0x1400119d5  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1400119da  mov     rbx, [rsp+28h+arg_0]
0x1400119df  mov     rax, r9
0x1400119e2  add     rsp, 20h
0x1400119e6  pop     rdi
0x1400119e7  retn
```
