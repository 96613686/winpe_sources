# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000b600`
- end: `0x18000b77b`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `379`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b800`
- `0x180010938`

## callees

- `0x18000b454`
- `0x18000b524`
- `0x18000b600`

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
0x18000b600  mov     [rsp+arg_0], rbx
0x18000b605  mov     [rsp+arg_8], rsi
0x18000b60a  push    rdi
0x18000b60b  sub     rsp, 20h
0x18000b60f  xor     eax, eax
0x18000b611  xorps   xmm0, xmm0
0x18000b614  mov     esi, r9d
0x18000b617  mov     r11, rdx
0x18000b61a  mov     r9, rcx
0x18000b61d  mov     r10d, r8d
0x18000b620  movups  xmmword ptr [rcx], xmm0
0x18000b623  mov     [rcx+10h], rax
0x18000b627  test    r8d, r8d
0x18000b62a  jz      loc_18000B75D
0x18000b630  sub     r10d, 1
0x18000b634  jz      loc_18000B750
0x18000b63a  sub     r10d, 1
0x18000b63e  jz      loc_18000B6D7
0x18000b644  sub     r10d, 1
0x18000b648  jz      loc_18000B6D7
0x18000b64e  sub     r10d, 1
0x18000b652  jz      loc_18000B75D
0x18000b658  sub     r10d, 1
0x18000b65c  jz      loc_18000B750
0x18000b662  sub     r10d, 1
0x18000b666  jz      short loc_18000B6D7
0x18000b668  cmp     r10d, 1
0x18000b66c  jz      short loc_18000B6D7
0x18000b66e  lea     ebx, [r8-140h]
0x18000b675  lea     r10d, [rax+1]
0x18000b679  cmp     ebx, 40h ; '@'
0x18000b67c  jge     short loc_18000B6C6
0x18000b67e  mov     eax, [rdx+4]
0x18000b681  lea     ecx, [r10+0Fh]
0x18000b685  mov     edi, ebx
0x18000b687  shl     edi, 5
0x18000b68a  test    cl, al
0x18000b68c  jz      short loc_18000B69F
0x18000b68e  mov     edx, eax
0x18000b690  shr     edx, 5
0x18000b693  and     edx, 3Fh
0x18000b696  cmp     edx, ebx
0x18000b698  jnz     short loc_18000B69F
0x18000b69a  mov     edx, r10d
0x18000b69d  jmp     short loc_18000B6A1
0x18000b69f  xor     edx, edx
0x18000b6a1  mov     [r9+10h], edx
0x18000b6a5  mov     edx, edi
0x18000b6a7  xor     edx, eax
0x18000b6a9  and     edx, 7E0h
0x18000b6af  xor     edx, eax
0x18000b6b1  or      edx, ecx
0x18000b6b3  lock cmpxchg [r11+4], edx
0x18000b6b9  jnz     short loc_18000B68A
0x18000b6bb  cmp     dword ptr [r9+10h], 0
0x18000b6c0  jnz     loc_18000B768
0x18000b6c6  mov     [r9+8], r8d
0x18000b6ca  mov     [r9+4], r10d
0x18000b6ce  mov     [r9+0Ch], esi
0x18000b6d2  jmp     loc_18000B768
0x18000b6d7  xor     ecx, ecx
0x18000b6d9  sub     r8d, 2
0x18000b6dd  jz      short loc_18000B705
0x18000b6df  sub     r8d, 1
0x18000b6e3  jz      short loc_18000B6FE
0x18000b6e5  sub     r8d, 3
0x18000b6e9  jz      short loc_18000B6F7
0x18000b6eb  cmp     r8d, 1
0x18000b6ef  jnz     short loc_18000B70A
0x18000b6f1  lea     ecx, [r8+0Fh]
0x18000b6f5  jmp     short loc_18000B70A
0x18000b6f7  mov     ecx, 4
0x18000b6fc  jmp     short loc_18000B70A
0x18000b6fe  mov     ecx, 8
0x18000b703  jmp     short loc_18000B70A
0x18000b705  mov     ecx, 2
0x18000b70a  mov     edx, [rdx]
0x18000b70c  mov     r10d, 1
0x18000b712  xor     eax, eax
0x18000b714  mov     r8d, ecx
0x18000b717  or      r8d, edx
0x18000b71a  cmp     r8d, edx
0x18000b71d  mov     ebx, r8d
0x18000b720  setz    al
0x18000b723  or      ebx, r10d
0x18000b726  cmp     r8d, edx
0x18000b729  mov     [r9+10h], eax
0x18000b72d  mov     eax, edx
0x18000b72f  cmovz   ebx, r8d
0x18000b733  lock cmpxchg [r11], ebx
0x18000b738  jz      short loc_18000B73E
0x18000b73a  mov     edx, eax
0x18000b73c  jmp     short loc_18000B712
0x18000b73e  test    r10b, bl
0x18000b741  jz      short loc_18000B748
0x18000b743  test    r10b, dl
0x18000b746  jz      short loc_18000B74B
0x18000b748  xor     r10d, r10d
0x18000b74b  mov     [r9], r10d
0x18000b74e  jmp     short loc_18000B768
0x18000b750  mov     edx, r8d
0x18000b753  mov     rcx, r11
0x18000b756  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000b75b  jmp     short loc_18000B768
0x18000b75d  mov     edx, r8d
0x18000b760  mov     rcx, r11
0x18000b763  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000b768  mov     rbx, [rsp+28h+arg_0]
0x18000b76d  mov     rax, r9
0x18000b770  mov     rsi, [rsp+28h+arg_8]
0x18000b775  add     rsp, 20h
0x18000b779  pop     rdi
0x18000b77a  retn
```
