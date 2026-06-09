# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000d440`
- end: `0x18000d712`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a498`

## callees

- `0x18000d440`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  int v7; // r8d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  signed __int32 v12; // edx
  int v13; // ebx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  BOOL v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  signed __int32 v23; // eax
  signed __int32 v24; // edx
  BOOL v25; // ebp
  unsigned int v26; // eax
  int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // r9d
  signed __int32 v30; // eax

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
      v24 = *a2;
      v25 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v26 = v24 | 1;
        if ( (((v24 | 1u) >> 14) & 1) != v25 )
        {
          if ( ((v26 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v26 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v26 = v24 & 0xFFFFC01E | 1;
          }
          v27 = 0;
          if ( a3 == 4 )
            v27 = 0x4000;
          v26 = v26 & 0xFFFFBFFF | v27;
        }
        v28 = (v26 >> 5) & 0x1FF;
        v29 = v28 + 1;
        if ( v28 + 1 > 0x1FF || v29 < v28 )
        {
          LOWORD(v29) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v28;
        }
        v30 = _InterlockedCompareExchange(
                a2,
                v26 ^ ((unsigned __int16)v26 ^ (unsigned __int16)(32 * v29)) & 0x3FE0,
                v24);
        if ( v24 == v30 )
          break;
        v24 = v30;
      }
      *(_DWORD *)a1 = (v24 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v16 = *a2;
      v17 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v19 = 5;
            if ( a3 != 1 )
              v19 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v19;
          }
          v20 = 0;
          if ( a3 == 5 )
            v20 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v20;
        }
        v21 = (v18 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v18 ^ (v18 ^ (v22 << 15)) & 0x3F8000, v16);
        if ( v16 == v23 )
          break;
        v16 = v23;
      }
      *(_DWORD *)a1 = (v16 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( v7 >= 64 )
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
    return a1;
  }
LABEL_17:
  v11 = 0;
  switch ( a3 )
  {
    case 2:
      v11 = 2;
      break;
    case 3:
      v11 = 8;
      break;
    case 6:
      v11 = 4;
      break;
    case 7:
      v11 = 16;
      break;
  }
  v12 = *a2;
  v13 = 1;
  while ( 1 )
  {
    v14 = v12 | v11 | 1;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    if ( (v12 | v11) == v12 )
      v14 = v12 | v11;
    v15 = _InterlockedCompareExchange(a2, v14, v12);
    if ( v12 == v15 )
      break;
    v12 = v15;
  }
  if ( (v14 & 1) == 0 || (v12 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x18000d440  push    rbx
0x18000d442  push    rbp
0x18000d443  push    rsi
0x18000d444  push    rdi
0x18000d445  xor     eax, eax
0x18000d447  xorps   xmm0, xmm0
0x18000d44a  mov     r10, rcx
0x18000d44d  mov     edi, r9d
0x18000d450  mov     r11d, r8d
0x18000d453  mov     rsi, rdx
0x18000d456  movups  xmmword ptr [rcx], xmm0
0x18000d459  mov     [rcx+10h], rax
0x18000d45d  mov     ecx, r8d
0x18000d460  test    r8d, r8d
0x18000d463  jz      loc_18000D63C
0x18000d469  sub     ecx, 1
0x18000d46c  jz      loc_18000D583
0x18000d472  sub     ecx, 1
0x18000d475  jz      loc_18000D50A
0x18000d47b  sub     ecx, 1
0x18000d47e  jz      loc_18000D50A
0x18000d484  sub     ecx, 1
0x18000d487  jz      loc_18000D63C
0x18000d48d  sub     ecx, 1
0x18000d490  jz      loc_18000D583
0x18000d496  sub     ecx, 1
0x18000d499  jz      short loc_18000D50A
0x18000d49b  cmp     ecx, 1
0x18000d49e  jz      short loc_18000D50A
0x18000d4a0  add     r8d, 0FFFFFEC0h
0x18000d4a7  lea     ebx, [rax+1]
0x18000d4aa  cmp     r8d, 40h ; '@'
0x18000d4ae  jge     short loc_18000D4F9
0x18000d4b0  mov     eax, [rdx+4]
0x18000d4b3  lea     ecx, [rbx+0Fh]
0x18000d4b6  mov     r9d, r8d
0x18000d4b9  shl     r9d, 5
0x18000d4bd  test    cl, al
0x18000d4bf  jz      short loc_18000D4D2
0x18000d4c1  mov     edx, eax
0x18000d4c3  shr     edx, 5
0x18000d4c6  and     edx, 3Fh
0x18000d4c9  cmp     edx, r8d
0x18000d4cc  jnz     short loc_18000D4D2
0x18000d4ce  mov     edx, ebx
0x18000d4d0  jmp     short loc_18000D4D4
0x18000d4d2  xor     edx, edx
0x18000d4d4  mov     [r10+10h], edx
0x18000d4d8  mov     edx, r9d
0x18000d4db  xor     edx, eax
0x18000d4dd  and     edx, 7E0h
0x18000d4e3  xor     edx, eax
0x18000d4e5  or      edx, ecx
0x18000d4e7  lock cmpxchg [rsi+4], edx
0x18000d4ec  jnz     short loc_18000D4BD
0x18000d4ee  cmp     dword ptr [r10+10h], 0
0x18000d4f3  jnz     loc_18000D70A
0x18000d4f9  mov     [r10+8], r11d
0x18000d4fd  mov     [r10+4], ebx
0x18000d501  mov     [r10+0Ch], edi
0x18000d505  jmp     loc_18000D70A
0x18000d50a  xor     ecx, ecx
0x18000d50c  sub     r11d, 2
0x18000d510  jz      short loc_18000D538
0x18000d512  sub     r11d, 1
0x18000d516  jz      short loc_18000D531
0x18000d518  sub     r11d, 3
0x18000d51c  jz      short loc_18000D52A
0x18000d51e  cmp     r11d, 1
0x18000d522  jnz     short loc_18000D53D
0x18000d524  lea     ecx, [r11+0Fh]
0x18000d528  jmp     short loc_18000D53D
0x18000d52a  mov     ecx, 4
0x18000d52f  jmp     short loc_18000D53D
0x18000d531  mov     ecx, 8
0x18000d536  jmp     short loc_18000D53D
0x18000d538  mov     ecx, 2
0x18000d53d  mov     edx, [rdx]
0x18000d53f  mov     ebx, 1
0x18000d544  xor     eax, eax
0x18000d546  mov     r8d, ecx
0x18000d549  or      r8d, edx
0x18000d54c  cmp     r8d, edx
0x18000d54f  mov     r9d, r8d
0x18000d552  setz    al
0x18000d555  or      r9d, ebx
0x18000d558  cmp     r8d, edx
0x18000d55b  mov     [r10+10h], eax
0x18000d55f  mov     eax, edx
0x18000d561  cmovz   r9d, r8d
0x18000d565  lock cmpxchg [rsi], r9d
0x18000d56a  jz      short loc_18000D570
0x18000d56c  mov     edx, eax
0x18000d56e  jmp     short loc_18000D544
0x18000d570  test    bl, r9b
0x18000d573  jz      short loc_18000D579
0x18000d575  test    bl, dl
0x18000d577  jz      short loc_18000D57B
0x18000d579  xor     ebx, ebx
0x18000d57b  mov     [r10], ebx
0x18000d57e  jmp     loc_18000D70A
0x18000d583  mov     ecx, [rdx]
0x18000d585  xor     r9d, r9d
0x18000d588  cmp     r11d, 5
0x18000d58c  mov     ebx, 1
0x18000d591  setz    r9b
0x18000d595  mov     eax, ecx
0x18000d597  mov     dword ptr [r10+4], 0
0x18000d59f  or      eax, ebx
0x18000d5a1  mov     edx, eax
0x18000d5a3  shr     edx, 16h
0x18000d5a6  and     edx, ebx
0x18000d5a8  cmp     edx, r9d
0x18000d5ab  jz      short loc_18000D5ED
0x18000d5ad  mov     r8d, eax
0x18000d5b0  shr     r8d, 0Fh
0x18000d5b4  and     r8d, 7Fh
0x18000d5b8  jbe     short loc_18000D5D2
0x18000d5ba  cmp     r11d, ebx
0x18000d5bd  mov     [r10+4], r8d
0x18000d5c1  mov     edx, 5
0x18000d5c6  cmovnz  edx, ebx
0x18000d5c9  and     eax, 0FFC07FFFh
0x18000d5ce  mov     [r10+8], edx
0x18000d5d2  xor     r8d, r8d
0x18000d5d5  mov     edx, 400000h
0x18000d5da  cmp     r11d, 5
0x18000d5de  cmovz   r8d, edx
0x18000d5e2  mov     edx, eax
0x18000d5e4  btr     edx, 16h
0x18000d5e8  mov     eax, r8d
0x18000d5eb  or      eax, edx
0x18000d5ed  mov     edx, eax
0x18000d5ef  shr     edx, 0Fh
0x18000d5f2  and     edx, 7Fh
0x18000d5f5  lea     r8d, [rdx+1]
0x18000d5f9  cmp     r8d, 7Fh
0x18000d5fd  ja      short loc_18000D604
0x18000d5ff  cmp     r8d, edx
0x18000d602  jnb     short loc_18000D60F
0x18000d604  mov     r8d, ebx
0x18000d607  mov     [r10+8], r11d
0x18000d60b  mov     [r10+4], edx
0x18000d60f  shl     r8d, 0Fh
0x18000d613  xor     r8d, eax
0x18000d616  and     r8d, 3F8000h
0x18000d61d  xor     r8d, eax
0x18000d620  mov     eax, ecx
0x18000d622  lock cmpxchg [rsi], r8d
0x18000d627  jz      short loc_18000D630
0x18000d629  mov     ecx, eax
0x18000d62b  jmp     loc_18000D595
0x18000d630  not     ecx
0x18000d632  and     ecx, ebx
0x18000d634  mov     [r10], ecx
0x18000d637  jmp     loc_18000D702
0x18000d63c  mov     edx, [rdx]
0x18000d63e  xor     ebp, ebp
0x18000d640  lea     ecx, [rbp+4]
0x18000d643  cmp     r11d, ecx
0x18000d646  lea     ebx, [rcx-3]
0x18000d649  setz    bpl
0x18000d64d  mov     eax, edx
0x18000d64f  mov     dword ptr [r10+4], 0
0x18000d657  or      eax, ebx
0x18000d659  mov     r8d, eax
0x18000d65c  shr     r8d, 0Eh
0x18000d660  and     r8d, ebx
0x18000d663  cmp     r8d, ebp
0x18000d666  jz      short loc_18000D6AF
0x18000d668  mov     edi, eax
0x18000d66a  shr     edi, 5
0x18000d66d  and     edi, 1FFh
0x18000d673  jbe     short loc_18000D691
0x18000d675  mov     r8d, r11d
0x18000d678  mov     [r10+4], edi
0x18000d67c  neg     r8d
0x18000d67f  sbb     r9d, r9d
0x18000d682  not     r9d
0x18000d685  and     r9d, ecx
0x18000d688  mov     [r10+8], r9d
0x18000d68c  and     eax, 0FFFFC01Fh
0x18000d691  xor     r9d, r9d
0x18000d694  mov     r8d, 4000h
0x18000d69a  cmp     r11d, ecx
0x18000d69d  cmovz   r9d, r8d
0x18000d6a1  mov     r8d, eax
0x18000d6a4  btr     r8d, 0Eh
0x18000d6a9  mov     eax, r9d
0x18000d6ac  or      eax, r8d
0x18000d6af  mov     r8d, eax
0x18000d6b2  shr     r8d, 5
0x18000d6b6  and     r8d, 1FFh
0x18000d6bd  lea     r9d, [r8+1]
0x18000d6c1  cmp     r9d, 1FFh
0x18000d6c8  ja      short loc_18000D6CF
0x18000d6ca  cmp     r9d, r8d
0x18000d6cd  jnb     short loc_18000D6DA
0x18000d6cf  mov     r9d, ebx
0x18000d6d2  mov     [r10+8], r11d
0x18000d6d6  mov     [r10+4], r8d
0x18000d6da  shl     r9d, 5
0x18000d6de  xor     r9d, eax
0x18000d6e1  and     r9d, 3FE0h
0x18000d6e8  xor     r9d, eax
0x18000d6eb  mov     eax, edx
0x18000d6ed  lock cmpxchg [rsi], r9d
0x18000d6f2  jz      short loc_18000D6FB
0x18000d6f4  mov     edx, eax
0x18000d6f6  jmp     loc_18000D64D
0x18000d6fb  not     edx
0x18000d6fd  and     edx, ebx
0x18000d6ff  mov     [r10], edx
0x18000d702  mov     dword ptr [r10+10h], 0
0x18000d70a  mov     rax, r10
0x18000d70d  pop     rdi
0x18000d70e  pop     rsi
0x18000d70f  pop     rbp
0x18000d710  pop     rbx
0x18000d711  retn
```
