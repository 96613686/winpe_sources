# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000b008`
- end: `0x18000b17f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ad50`

## callees

- `0x18000b008`
- `0x1800107b8`
- `0x18001a3e4`

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
0x18000b008  mov     [rsp+arg_0], rbx
0x18000b00d  push    rdi
0x18000b00e  sub     rsp, 20h
0x18000b012  xor     eax, eax
0x18000b014  xorps   xmm0, xmm0
0x18000b017  mov     r10, rdx
0x18000b01a  mov     rbx, rcx
0x18000b01d  mov     r9d, r8d
0x18000b020  movups  xmmword ptr [rcx], xmm0
0x18000b023  mov     [rcx+10h], rax
0x18000b027  test    r8d, r8d
0x18000b02a  jz      loc_18000B163
0x18000b030  sub     r9d, 1
0x18000b034  jz      loc_18000B153
0x18000b03a  sub     r9d, 1
0x18000b03e  jz      loc_18000B0DB
0x18000b044  sub     r9d, 1
0x18000b048  jz      loc_18000B0DB
0x18000b04e  sub     r9d, 1
0x18000b052  jz      loc_18000B163
0x18000b058  sub     r9d, 1
0x18000b05c  jz      loc_18000B153
0x18000b062  sub     r9d, 1
0x18000b066  jz      short loc_18000B0DB
0x18000b068  cmp     r9d, 1
0x18000b06c  jz      short loc_18000B0DB
0x18000b06e  lea     r11d, [r8-140h]
0x18000b075  lea     r9d, [rax+1]
0x18000b079  cmp     r11d, 40h ; '@'
0x18000b07d  jge     short loc_18000B0C7
0x18000b07f  mov     eax, [rdx+4]
0x18000b082  lea     ecx, [r9+0Fh]
0x18000b086  mov     edi, r11d
0x18000b089  shl     edi, 5
0x18000b08c  test    cl, al
0x18000b08e  jz      short loc_18000B0A2
0x18000b090  mov     edx, eax
0x18000b092  shr     edx, 5
0x18000b095  and     edx, 3Fh
0x18000b098  cmp     edx, r11d
0x18000b09b  jnz     short loc_18000B0A2
0x18000b09d  mov     edx, r9d
0x18000b0a0  jmp     short loc_18000B0A4
0x18000b0a2  xor     edx, edx
0x18000b0a4  mov     [rbx+10h], edx
0x18000b0a7  mov     edx, edi
0x18000b0a9  xor     edx, eax
0x18000b0ab  and     edx, 7E0h
0x18000b0b1  xor     edx, eax
0x18000b0b3  or      edx, ecx
0x18000b0b5  lock cmpxchg [r10+4], edx
0x18000b0bb  jnz     short loc_18000B08C
0x18000b0bd  cmp     dword ptr [rbx+10h], 0
0x18000b0c1  jnz     loc_18000B171
0x18000b0c7  mov     [rbx+8], r8d
0x18000b0cb  mov     [rbx+4], r9d
0x18000b0cf  mov     dword ptr [rbx+0Ch], 0
0x18000b0d6  jmp     loc_18000B171
0x18000b0db  xor     ecx, ecx
0x18000b0dd  sub     r8d, 2
0x18000b0e1  jz      short loc_18000B109
0x18000b0e3  sub     r8d, 1
0x18000b0e7  jz      short loc_18000B102
0x18000b0e9  sub     r8d, 3
0x18000b0ed  jz      short loc_18000B0FB
0x18000b0ef  cmp     r8d, 1
0x18000b0f3  jnz     short loc_18000B10E
0x18000b0f5  lea     ecx, [r8+0Fh]
0x18000b0f9  jmp     short loc_18000B10E
0x18000b0fb  mov     ecx, 4
0x18000b100  jmp     short loc_18000B10E
0x18000b102  mov     ecx, 8
0x18000b107  jmp     short loc_18000B10E
0x18000b109  mov     ecx, 2
0x18000b10e  mov     edx, [rdx]
0x18000b110  mov     r9d, 1
0x18000b116  xor     eax, eax
0x18000b118  mov     r8d, ecx
0x18000b11b  or      r8d, edx
0x18000b11e  cmp     r8d, edx
0x18000b121  mov     r11d, r8d
0x18000b124  setz    al
0x18000b127  or      r11d, r9d
0x18000b12a  cmp     r8d, edx
0x18000b12d  mov     [rbx+10h], eax
0x18000b130  mov     eax, edx
0x18000b132  cmovz   r11d, r8d
0x18000b136  lock cmpxchg [r10], r11d
0x18000b13b  jz      short loc_18000B141
0x18000b13d  mov     edx, eax
0x18000b13f  jmp     short loc_18000B116
0x18000b141  test    r9b, r11b
0x18000b144  jz      short loc_18000B14B
0x18000b146  test    r9b, dl
0x18000b149  jz      short loc_18000B14E
0x18000b14b  xor     r9d, r9d
0x18000b14e  mov     [rbx], r9d
0x18000b151  jmp     short loc_18000B171
0x18000b153  mov     r9, rbx
0x18000b156  mov     edx, r8d
0x18000b159  mov     rcx, r10
0x18000b15c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000b161  jmp     short loc_18000B171
0x18000b163  mov     r9, rbx
0x18000b166  mov     edx, r8d
0x18000b169  mov     rcx, r10
0x18000b16c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000b171  mov     rax, rbx
0x18000b174  mov     rbx, [rsp+28h+arg_0]
0x18000b179  add     rsp, 20h
0x18000b17d  pop     rdi
0x18000b17e  retn
```
