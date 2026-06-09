# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800275d0`
- end: `0x180027747`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800208b0`

## callees

- `0x180027424`
- `0x1800274f4`
- `0x1800275d0`

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
0x1800275d0  mov     [rsp+arg_0], rbx
0x1800275d5  push    rdi
0x1800275d6  sub     rsp, 20h
0x1800275da  xor     eax, eax
0x1800275dc  xorps   xmm0, xmm0
0x1800275df  mov     r10, rdx
0x1800275e2  mov     rbx, rcx
0x1800275e5  mov     r9d, r8d
0x1800275e8  movups  xmmword ptr [rcx], xmm0
0x1800275eb  mov     [rcx+10h], rax
0x1800275ef  test    r8d, r8d
0x1800275f2  jz      loc_18002772B
0x1800275f8  sub     r9d, 1
0x1800275fc  jz      loc_18002771B
0x180027602  sub     r9d, 1
0x180027606  jz      loc_1800276A3
0x18002760c  sub     r9d, 1
0x180027610  jz      loc_1800276A3
0x180027616  sub     r9d, 1
0x18002761a  jz      loc_18002772B
0x180027620  sub     r9d, 1
0x180027624  jz      loc_18002771B
0x18002762a  sub     r9d, 1
0x18002762e  jz      short loc_1800276A3
0x180027630  cmp     r9d, 1
0x180027634  jz      short loc_1800276A3
0x180027636  lea     r11d, [r8-140h]
0x18002763d  lea     r9d, [rax+1]
0x180027641  cmp     r11d, 40h ; '@'
0x180027645  jge     short loc_18002768F
0x180027647  mov     eax, [rdx+4]
0x18002764a  lea     ecx, [r9+0Fh]
0x18002764e  mov     edi, r11d
0x180027651  shl     edi, 5
0x180027654  test    cl, al
0x180027656  jz      short loc_18002766A
0x180027658  mov     edx, eax
0x18002765a  shr     edx, 5
0x18002765d  and     edx, 3Fh
0x180027660  cmp     edx, r11d
0x180027663  jnz     short loc_18002766A
0x180027665  mov     edx, r9d
0x180027668  jmp     short loc_18002766C
0x18002766a  xor     edx, edx
0x18002766c  mov     [rbx+10h], edx
0x18002766f  mov     edx, edi
0x180027671  xor     edx, eax
0x180027673  and     edx, 7E0h
0x180027679  xor     edx, eax
0x18002767b  or      edx, ecx
0x18002767d  lock cmpxchg [r10+4], edx
0x180027683  jnz     short loc_180027654
0x180027685  cmp     dword ptr [rbx+10h], 0
0x180027689  jnz     loc_180027739
0x18002768f  mov     [rbx+8], r8d
0x180027693  mov     [rbx+4], r9d
0x180027697  mov     dword ptr [rbx+0Ch], 0
0x18002769e  jmp     loc_180027739
0x1800276a3  xor     ecx, ecx
0x1800276a5  sub     r8d, 2
0x1800276a9  jz      short loc_1800276D1
0x1800276ab  sub     r8d, 1
0x1800276af  jz      short loc_1800276CA
0x1800276b1  sub     r8d, 3
0x1800276b5  jz      short loc_1800276C3
0x1800276b7  cmp     r8d, 1
0x1800276bb  jnz     short loc_1800276D6
0x1800276bd  lea     ecx, [r8+0Fh]
0x1800276c1  jmp     short loc_1800276D6
0x1800276c3  mov     ecx, 4
0x1800276c8  jmp     short loc_1800276D6
0x1800276ca  mov     ecx, 8
0x1800276cf  jmp     short loc_1800276D6
0x1800276d1  mov     ecx, 2
0x1800276d6  mov     edx, [rdx]
0x1800276d8  mov     r9d, 1
0x1800276de  xor     eax, eax
0x1800276e0  mov     r8d, ecx
0x1800276e3  or      r8d, edx
0x1800276e6  cmp     r8d, edx
0x1800276e9  mov     r11d, r8d
0x1800276ec  setz    al
0x1800276ef  or      r11d, r9d
0x1800276f2  cmp     r8d, edx
0x1800276f5  mov     [rbx+10h], eax
0x1800276f8  mov     eax, edx
0x1800276fa  cmovz   r11d, r8d
0x1800276fe  lock cmpxchg [r10], r11d
0x180027703  jz      short loc_180027709
0x180027705  mov     edx, eax
0x180027707  jmp     short loc_1800276DE
0x180027709  test    r9b, r11b
0x18002770c  jz      short loc_180027713
0x18002770e  test    r9b, dl
0x180027711  jz      short loc_180027716
0x180027713  xor     r9d, r9d
0x180027716  mov     [rbx], r9d
0x180027719  jmp     short loc_180027739
0x18002771b  mov     r9, rbx
0x18002771e  mov     edx, r8d
0x180027721  mov     rcx, r10
0x180027724  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180027729  jmp     short loc_180027739
0x18002772b  mov     r9, rbx
0x18002772e  mov     edx, r8d
0x180027731  mov     rcx, r10
0x180027734  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180027739  mov     rax, rbx
0x18002773c  mov     rbx, [rsp+28h+arg_0]
0x180027741  add     rsp, 20h
0x180027745  pop     rdi
0x180027746  retn
```
