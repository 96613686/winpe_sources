# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000f688`
- end: `0x18000f7ff`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a1ac`

## callees

- `0x18000f4dc`
- `0x18000f5ac`
- `0x18000f688`

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
0x18000f688  mov     [rsp+arg_0], rbx
0x18000f68d  push    rdi
0x18000f68e  sub     rsp, 20h
0x18000f692  xor     eax, eax
0x18000f694  xorps   xmm0, xmm0
0x18000f697  mov     r10, rdx
0x18000f69a  mov     rbx, rcx
0x18000f69d  mov     r9d, r8d
0x18000f6a0  movups  xmmword ptr [rcx], xmm0
0x18000f6a3  mov     [rcx+10h], rax
0x18000f6a7  test    r8d, r8d
0x18000f6aa  jz      loc_18000F7E3
0x18000f6b0  sub     r9d, 1
0x18000f6b4  jz      loc_18000F7D3
0x18000f6ba  sub     r9d, 1
0x18000f6be  jz      loc_18000F75B
0x18000f6c4  sub     r9d, 1
0x18000f6c8  jz      loc_18000F75B
0x18000f6ce  sub     r9d, 1
0x18000f6d2  jz      loc_18000F7E3
0x18000f6d8  sub     r9d, 1
0x18000f6dc  jz      loc_18000F7D3
0x18000f6e2  sub     r9d, 1
0x18000f6e6  jz      short loc_18000F75B
0x18000f6e8  cmp     r9d, 1
0x18000f6ec  jz      short loc_18000F75B
0x18000f6ee  lea     r11d, [r8-140h]
0x18000f6f5  lea     r9d, [rax+1]
0x18000f6f9  cmp     r11d, 40h ; '@'
0x18000f6fd  jge     short loc_18000F747
0x18000f6ff  mov     eax, [rdx+4]
0x18000f702  lea     ecx, [r9+0Fh]
0x18000f706  mov     edi, r11d
0x18000f709  shl     edi, 5
0x18000f70c  test    cl, al
0x18000f70e  jz      short loc_18000F722
0x18000f710  mov     edx, eax
0x18000f712  shr     edx, 5
0x18000f715  and     edx, 3Fh
0x18000f718  cmp     edx, r11d
0x18000f71b  jnz     short loc_18000F722
0x18000f71d  mov     edx, r9d
0x18000f720  jmp     short loc_18000F724
0x18000f722  xor     edx, edx
0x18000f724  mov     [rbx+10h], edx
0x18000f727  mov     edx, edi
0x18000f729  xor     edx, eax
0x18000f72b  and     edx, 7E0h
0x18000f731  xor     edx, eax
0x18000f733  or      edx, ecx
0x18000f735  lock cmpxchg [r10+4], edx
0x18000f73b  jnz     short loc_18000F70C
0x18000f73d  cmp     dword ptr [rbx+10h], 0
0x18000f741  jnz     loc_18000F7F1
0x18000f747  mov     [rbx+8], r8d
0x18000f74b  mov     [rbx+4], r9d
0x18000f74f  mov     dword ptr [rbx+0Ch], 0
0x18000f756  jmp     loc_18000F7F1
0x18000f75b  xor     ecx, ecx
0x18000f75d  sub     r8d, 2
0x18000f761  jz      short loc_18000F789
0x18000f763  sub     r8d, 1
0x18000f767  jz      short loc_18000F782
0x18000f769  sub     r8d, 3
0x18000f76d  jz      short loc_18000F77B
0x18000f76f  cmp     r8d, 1
0x18000f773  jnz     short loc_18000F78E
0x18000f775  lea     ecx, [r8+0Fh]
0x18000f779  jmp     short loc_18000F78E
0x18000f77b  mov     ecx, 4
0x18000f780  jmp     short loc_18000F78E
0x18000f782  mov     ecx, 8
0x18000f787  jmp     short loc_18000F78E
0x18000f789  mov     ecx, 2
0x18000f78e  mov     edx, [rdx]
0x18000f790  mov     r9d, 1
0x18000f796  xor     eax, eax
0x18000f798  mov     r8d, ecx
0x18000f79b  or      r8d, edx
0x18000f79e  cmp     r8d, edx
0x18000f7a1  mov     r11d, r8d
0x18000f7a4  setz    al
0x18000f7a7  or      r11d, r9d
0x18000f7aa  cmp     r8d, edx
0x18000f7ad  mov     [rbx+10h], eax
0x18000f7b0  mov     eax, edx
0x18000f7b2  cmovz   r11d, r8d
0x18000f7b6  lock cmpxchg [r10], r11d
0x18000f7bb  jz      short loc_18000F7C1
0x18000f7bd  mov     edx, eax
0x18000f7bf  jmp     short loc_18000F796
0x18000f7c1  test    r9b, r11b
0x18000f7c4  jz      short loc_18000F7CB
0x18000f7c6  test    r9b, dl
0x18000f7c9  jz      short loc_18000F7CE
0x18000f7cb  xor     r9d, r9d
0x18000f7ce  mov     [rbx], r9d
0x18000f7d1  jmp     short loc_18000F7F1
0x18000f7d3  mov     r9, rbx
0x18000f7d6  mov     edx, r8d
0x18000f7d9  mov     rcx, r10
0x18000f7dc  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000f7e1  jmp     short loc_18000F7F1
0x18000f7e3  mov     r9, rbx
0x18000f7e6  mov     edx, r8d
0x18000f7e9  mov     rcx, r10
0x18000f7ec  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000f7f1  mov     rax, rbx
0x18000f7f4  mov     rbx, [rsp+28h+arg_0]
0x18000f7f9  add     rsp, 20h
0x18000f7fd  pop     rdi
0x18000f7fe  retn
```
