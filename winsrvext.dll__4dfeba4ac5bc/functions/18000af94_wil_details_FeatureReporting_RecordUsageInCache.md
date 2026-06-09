# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000af94`
- end: `0x18000b27a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b3b0`

## callees

- `0x18000af94`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4,
        int a5)
{
  int v8; // r8d
  unsigned __int32 v9; // eax
  BOOL v10; // edx
  unsigned __int32 v11; // ett
  int v12; // ecx
  signed __int32 v13; // edx
  int v14; // ebx
  signed __int32 v15; // r9d
  signed __int32 v16; // eax
  signed __int32 v17; // ecx
  BOOL v18; // edi
  unsigned int v19; // eax
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // edx
  unsigned int v23; // r8d
  signed __int32 v24; // eax
  signed __int32 v25; // edx
  BOOL v26; // r14d
  unsigned int v27; // eax
  int v28; // r9d
  unsigned int v29; // r8d
  unsigned int v30; // r9d
  signed __int32 v31; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v25 = *a2;
      v26 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v27 = v25 | 1;
        if ( (((v25 | 1u) >> 14) & 1) != v26 )
        {
          if ( ((v27 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v27 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v27 = v25 & 0xFFFFC01E | 1;
          }
          v28 = 0;
          if ( a3 == 4 )
            v28 = 0x4000;
          v27 = v27 & 0xFFFFBFFF | v28;
        }
        v29 = (v27 >> 5) & 0x1FF;
        v30 = v29 + a5;
        if ( v29 + a5 > 0x1FF || v30 < v29 )
        {
          LOWORD(v30) = a5;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v29;
        }
        v31 = _InterlockedCompareExchange(
                a2,
                v27 ^ ((unsigned __int16)v27 ^ (unsigned __int16)(32 * v30)) & 0x3FE0,
                v25);
        if ( v25 == v31 )
          break;
        v25 = v31;
      }
      *(_DWORD *)a1 = (v25 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v17 = *a2;
      v18 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v19 = v17 | 1;
        if ( (((v17 | 1u) >> 22) & 1) != v18 )
        {
          if ( ((v19 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v19 >> 15) & 0x7F;
            v20 = 5;
            if ( a3 != 1 )
              v20 = 1;
            v19 = v17 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v20;
          }
          v21 = 0;
          if ( a3 == 5 )
            v21 = 0x400000;
          v19 = v19 & 0xFFBFFFFF | v21;
        }
        v22 = (v19 >> 15) & 0x7F;
        v23 = v22 + a5;
        if ( v22 + a5 > 0x7F || v23 < v22 )
        {
          v23 = a5;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v22;
        }
        v24 = _InterlockedCompareExchange(a2, v19 ^ (v19 ^ (v23 << 15)) & 0x3F8000, v17);
        if ( v17 == v24 )
          break;
        v17 = v24;
      }
      *(_DWORD *)a1 = (v17 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v8 = a3 - 320;
    if ( v8 >= 64 )
      goto LABEL_16;
    v9 = *((_DWORD *)a2 + 1);
    do
    {
      v10 = (v9 & 0x10) != 0 && ((v9 >> 5) & 0x3F) == v8;
      *(_DWORD *)(a1 + 16) = v10;
      v11 = v9;
      v9 = _InterlockedCompareExchange(
             a2 + 1,
             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v8)) & 0x7E0 | 0x10,
             v9);
    }
    while ( v11 != v9 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 4) = a5;
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return a1;
  }
LABEL_17:
  v12 = 0;
  switch ( a3 )
  {
    case 2:
      v12 = 2;
      break;
    case 3:
      v12 = 8;
      break;
    case 6:
      v12 = 4;
      break;
    case 7:
      v12 = 16;
      break;
  }
  v13 = *a2;
  v14 = 1;
  while ( 1 )
  {
    v15 = v13 | v12 | 1;
    *(_DWORD *)(a1 + 16) = (v13 | v12) == v13;
    if ( (v13 | v12) == v13 )
      v15 = v13 | v12;
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
0x18000af94  push    rbx
0x18000af96  push    rbp
0x18000af97  push    rsi
0x18000af98  push    rdi
0x18000af99  push    r14
0x18000af9b  xor     eax, eax
0x18000af9d  xorps   xmm0, xmm0
0x18000afa0  mov     r10, rcx
0x18000afa3  mov     edi, r9d
0x18000afa6  mov     r11d, r8d
0x18000afa9  mov     rsi, rdx
0x18000afac  movups  xmmword ptr [rcx], xmm0
0x18000afaf  mov     [rcx+10h], rax
0x18000afb3  mov     ecx, r8d
0x18000afb6  test    r8d, r8d
0x18000afb9  jz      loc_18000B19B
0x18000afbf  sub     ecx, 1
0x18000afc2  jz      loc_18000B0DF
0x18000afc8  sub     ecx, 1
0x18000afcb  jz      loc_18000B066
0x18000afd1  sub     ecx, 1
0x18000afd4  jz      loc_18000B066
0x18000afda  sub     ecx, 1
0x18000afdd  jz      loc_18000B19B
0x18000afe3  sub     ecx, 1
0x18000afe6  jz      loc_18000B0DF
0x18000afec  sub     ecx, 1
0x18000afef  jz      short loc_18000B066
0x18000aff1  cmp     ecx, 1
0x18000aff4  jz      short loc_18000B066
0x18000aff6  add     r8d, 0FFFFFEC0h
0x18000affd  cmp     r8d, 40h ; '@'
0x18000b001  jge     short loc_18000B051
0x18000b003  mov     eax, [rdx+4]
0x18000b006  mov     ecx, 10h
0x18000b00b  mov     r9d, r8d
0x18000b00e  shl     r9d, 5
0x18000b012  lea     ebx, [rcx-0Fh]
0x18000b015  test    cl, al
0x18000b017  jz      short loc_18000B02A
0x18000b019  mov     edx, eax
0x18000b01b  shr     edx, 5
0x18000b01e  and     edx, 3Fh
0x18000b021  cmp     edx, r8d
0x18000b024  jnz     short loc_18000B02A
0x18000b026  mov     edx, ebx
0x18000b028  jmp     short loc_18000B02C
0x18000b02a  xor     edx, edx
0x18000b02c  mov     [r10+10h], edx
0x18000b030  mov     edx, r9d
0x18000b033  xor     edx, eax
0x18000b035  and     edx, 7E0h
0x18000b03b  xor     edx, eax
0x18000b03d  or      edx, ecx
0x18000b03f  lock cmpxchg [rsi+4], edx
0x18000b044  jnz     short loc_18000B015
0x18000b046  cmp     dword ptr [r10+10h], 0
0x18000b04b  jnz     loc_18000B26F
0x18000b051  mov     eax, [rsp+28h+arg_20]
0x18000b055  mov     [r10+4], eax
0x18000b059  mov     [r10+8], r11d
0x18000b05d  mov     [r10+0Ch], edi
0x18000b061  jmp     loc_18000B26F
0x18000b066  xor     ecx, ecx
0x18000b068  sub     r11d, 2
0x18000b06c  jz      short loc_18000B094
0x18000b06e  sub     r11d, 1
0x18000b072  jz      short loc_18000B08D
0x18000b074  sub     r11d, 3
0x18000b078  jz      short loc_18000B086
0x18000b07a  cmp     r11d, 1
0x18000b07e  jnz     short loc_18000B099
0x18000b080  lea     ecx, [r11+0Fh]
0x18000b084  jmp     short loc_18000B099
0x18000b086  mov     ecx, 4
0x18000b08b  jmp     short loc_18000B099
0x18000b08d  mov     ecx, 8
0x18000b092  jmp     short loc_18000B099
0x18000b094  mov     ecx, 2
0x18000b099  mov     edx, [rdx]
0x18000b09b  mov     ebx, 1
0x18000b0a0  xor     eax, eax
0x18000b0a2  mov     r8d, ecx
0x18000b0a5  or      r8d, edx
0x18000b0a8  cmp     r8d, edx
0x18000b0ab  mov     r9d, r8d
0x18000b0ae  setz    al
0x18000b0b1  or      r9d, ebx
0x18000b0b4  cmp     r8d, edx
0x18000b0b7  mov     [r10+10h], eax
0x18000b0bb  mov     eax, edx
0x18000b0bd  cmovz   r9d, r8d
0x18000b0c1  lock cmpxchg [rsi], r9d
0x18000b0c6  jz      short loc_18000B0CC
0x18000b0c8  mov     edx, eax
0x18000b0ca  jmp     short loc_18000B0A0
0x18000b0cc  test    bl, r9b
0x18000b0cf  jz      short loc_18000B0D5
0x18000b0d1  test    bl, dl
0x18000b0d3  jz      short loc_18000B0D7
0x18000b0d5  xor     ebx, ebx
0x18000b0d7  mov     [r10], ebx
0x18000b0da  jmp     loc_18000B26F
0x18000b0df  mov     ecx, [rdx]
0x18000b0e1  xor     edi, edi
0x18000b0e3  mov     r9d, [rsp+28h+arg_20]
0x18000b0e8  cmp     r11d, 5
0x18000b0ec  mov     ebx, 1
0x18000b0f1  setz    dil
0x18000b0f5  mov     eax, ecx
0x18000b0f7  mov     dword ptr [r10+4], 0
0x18000b0ff  or      eax, ebx
0x18000b101  mov     edx, eax
0x18000b103  shr     edx, 16h
0x18000b106  and     edx, ebx
0x18000b108  cmp     edx, edi
0x18000b10a  jz      short loc_18000B14C
0x18000b10c  mov     r8d, eax
0x18000b10f  shr     r8d, 0Fh
0x18000b113  and     r8d, 7Fh
0x18000b117  jbe     short loc_18000B131
0x18000b119  cmp     r11d, ebx
0x18000b11c  mov     [r10+4], r8d
0x18000b120  mov     edx, 5
0x18000b125  cmovnz  edx, ebx
0x18000b128  and     eax, 0FFC07FFFh
0x18000b12d  mov     [r10+8], edx
0x18000b131  xor     r8d, r8d
0x18000b134  mov     edx, 400000h
0x18000b139  cmp     r11d, 5
0x18000b13d  cmovz   r8d, edx
0x18000b141  mov     edx, eax
0x18000b143  btr     edx, 16h
0x18000b147  mov     eax, r8d
0x18000b14a  or      eax, edx
0x18000b14c  mov     edx, eax
0x18000b14e  shr     edx, 0Fh
0x18000b151  and     edx, 7Fh
0x18000b154  lea     r8d, [rdx+r9]
0x18000b158  cmp     r8d, 7Fh
0x18000b15c  ja      short loc_18000B163
0x18000b15e  cmp     r8d, edx
0x18000b161  jnb     short loc_18000B16E
0x18000b163  mov     r8d, r9d
0x18000b166  mov     [r10+8], r11d
0x18000b16a  mov     [r10+4], edx
0x18000b16e  shl     r8d, 0Fh
0x18000b172  xor     r8d, eax
0x18000b175  and     r8d, 3F8000h
0x18000b17c  xor     r8d, eax
0x18000b17f  mov     eax, ecx
0x18000b181  lock cmpxchg [rsi], r8d
0x18000b186  jz      short loc_18000B18F
0x18000b188  mov     ecx, eax
0x18000b18a  jmp     loc_18000B0F5
0x18000b18f  not     ecx
0x18000b191  and     ecx, ebx
0x18000b193  mov     [r10], ecx
0x18000b196  jmp     loc_18000B267
0x18000b19b  mov     edx, [rdx]
0x18000b19d  xor     r14d, r14d
0x18000b1a0  mov     ebp, [rsp+28h+arg_20]
0x18000b1a4  lea     ecx, [r14+4]
0x18000b1a8  cmp     r11d, ecx
0x18000b1ab  lea     ebx, [rcx-3]
0x18000b1ae  setz    r14b
0x18000b1b2  mov     eax, edx
0x18000b1b4  mov     dword ptr [r10+4], 0
0x18000b1bc  or      eax, ebx
0x18000b1be  mov     r8d, eax
0x18000b1c1  shr     r8d, 0Eh
0x18000b1c5  and     r8d, ebx
0x18000b1c8  cmp     r8d, r14d
0x18000b1cb  jz      short loc_18000B214
0x18000b1cd  mov     edi, eax
0x18000b1cf  shr     edi, 5
0x18000b1d2  and     edi, 1FFh
0x18000b1d8  jbe     short loc_18000B1F6
0x18000b1da  mov     r8d, r11d
0x18000b1dd  mov     [r10+4], edi
0x18000b1e1  neg     r8d
0x18000b1e4  sbb     r9d, r9d
0x18000b1e7  not     r9d
0x18000b1ea  and     r9d, ecx
0x18000b1ed  mov     [r10+8], r9d
0x18000b1f1  and     eax, 0FFFFC01Fh
0x18000b1f6  xor     r9d, r9d
0x18000b1f9  mov     r8d, 4000h
0x18000b1ff  cmp     r11d, ecx
0x18000b202  cmovz   r9d, r8d
0x18000b206  mov     r8d, eax
0x18000b209  btr     r8d, 0Eh
0x18000b20e  mov     eax, r9d
0x18000b211  or      eax, r8d
0x18000b214  mov     r8d, eax
0x18000b217  shr     r8d, 5
0x18000b21b  and     r8d, 1FFh
0x18000b222  lea     r9d, [r8+rbp]
0x18000b226  cmp     r9d, 1FFh
0x18000b22d  ja      short loc_18000B234
0x18000b22f  cmp     r9d, r8d
0x18000b232  jnb     short loc_18000B23F
0x18000b234  mov     r9d, ebp
0x18000b237  mov     [r10+8], r11d
0x18000b23b  mov     [r10+4], r8d
0x18000b23f  shl     r9d, 5
0x18000b243  xor     r9d, eax
0x18000b246  and     r9d, 3FE0h
0x18000b24d  xor     r9d, eax
0x18000b250  mov     eax, edx
0x18000b252  lock cmpxchg [rsi], r9d
0x18000b257  jz      short loc_18000B260
0x18000b259  mov     edx, eax
0x18000b25b  jmp     loc_18000B1B2
0x18000b260  not     edx
0x18000b262  and     edx, ebx
0x18000b264  mov     [r10], edx
0x18000b267  mov     dword ptr [r10+10h], 0
0x18000b26f  mov     rax, r10
0x18000b272  pop     r14
0x18000b274  pop     rdi
0x18000b275  pop     rsi
0x18000b276  pop     rbp
0x18000b277  pop     rbx
0x18000b278  retn
```
