# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000f484`
- end: `0x14000f75e`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400094a4`

## callees

- `0x14000f484`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // edx
  unsigned __int32 v9; // ett
  int v10; // ecx
  signed __int32 v11; // edx
  int v12; // ebx
  signed __int32 v13; // r9d
  signed __int32 v14; // eax
  signed __int32 v15; // ecx
  BOOL v16; // r9d
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // edx
  unsigned int v21; // r8d
  signed __int32 v22; // eax
  signed __int32 v23; // edx
  BOOL v24; // ebp
  unsigned int v25; // eax
  int v26; // r9d
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  signed __int32 v29; // eax

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
      v23 = *a2;
      v24 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v25 = v23 | 1;
        if ( (((v23 | 1u) >> 14) & 1) != v24 )
        {
          if ( ((v25 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v25 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v25 = v23 & 0xFFFFC01E | 1;
          }
          v26 = 0;
          if ( a3 == 4 )
            v26 = 0x4000;
          v25 = v25 & 0xFFFFBFFF | v26;
        }
        v27 = (v25 >> 5) & 0x1FF;
        v28 = v27 + 1;
        if ( v27 + 1 > 0x1FF || v28 < v27 )
        {
          LOWORD(v28) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v27;
        }
        v29 = _InterlockedCompareExchange(
                a2,
                v25 ^ ((unsigned __int16)v25 ^ (unsigned __int16)(32 * v28)) & 0x3FE0,
                v23);
        if ( v23 == v29 )
          break;
        v23 = v29;
      }
      *(_DWORD *)a1 = (v23 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v15 = *a2;
      v16 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v17 = v15 | 1;
        if ( (((v15 | 1u) >> 22) & 1) != v16 )
        {
          if ( ((v17 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v17 >> 15) & 0x7F;
            v18 = 5;
            if ( a3 != 1 )
              v18 = 1;
            v17 = v15 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v18;
          }
          v19 = 0;
          if ( a3 == 5 )
            v19 = 0x400000;
          v17 = v17 & 0xFFBFFFFF | v19;
        }
        v20 = (v17 >> 15) & 0x7F;
        v21 = v20 + 1;
        if ( v20 + 1 > 0x7F || v21 < v20 )
        {
          v21 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v20;
        }
        v22 = _InterlockedCompareExchange(a2, v17 ^ (v17 ^ (v21 << 15)) & 0x3F8000, v15);
        if ( v15 == v22 )
          break;
        v15 = v22;
      }
      *(_DWORD *)a1 = (v15 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v6 = a3 - 320;
    if ( v6 >= 64 )
      goto LABEL_16;
    v7 = *((_DWORD *)a2 + 1);
    do
    {
      v8 = (v7 & 0x10) != 0 && ((v7 >> 5) & 0x3F) == v6;
      *(_DWORD *)(a1 + 16) = v8;
      v9 = v7;
      v7 = _InterlockedCompareExchange(
             a2 + 1,
             v7 ^ ((unsigned __int16)v7 ^ (unsigned __int16)(32 * v6)) & 0x7E0 | 0x10,
             v7);
    }
    while ( v9 != v7 );
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
  v10 = 0;
  switch ( a3 )
  {
    case 2:
      v10 = 2;
      break;
    case 3:
      v10 = 8;
      break;
    case 6:
      v10 = 4;
      break;
    case 7:
      v10 = 16;
      break;
  }
  v11 = *a2;
  v12 = 1;
  while ( 1 )
  {
    v13 = v11 | v10 | 1;
    *(_DWORD *)(a1 + 16) = (v11 | v10) == v11;
    if ( (v11 | v10) == v11 )
      v13 = v11 | v10;
    v14 = _InterlockedCompareExchange(a2, v13, v11);
    if ( v11 == v14 )
      break;
    v11 = v14;
  }
  if ( (v13 & 1) == 0 || (v11 & 1) != 0 )
    v12 = 0;
  *(_DWORD *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x14000f484  push    rbx
0x14000f486  push    rbp
0x14000f487  push    rsi
0x14000f488  push    rdi
0x14000f489  xor     eax, eax
0x14000f48b  xorps   xmm0, xmm0
0x14000f48e  mov     r11d, r8d
0x14000f491  mov     rsi, rdx
0x14000f494  mov     r10, rcx
0x14000f497  mov     r9d, r8d
0x14000f49a  movups  xmmword ptr [rcx], xmm0
0x14000f49d  mov     [rcx+10h], rax
0x14000f4a1  test    r8d, r8d
0x14000f4a4  jz      loc_14000F688
0x14000f4aa  sub     r9d, 1
0x14000f4ae  jz      loc_14000F5CF
0x14000f4b4  sub     r9d, 1
0x14000f4b8  jz      loc_14000F556
0x14000f4be  sub     r9d, 1
0x14000f4c2  jz      loc_14000F556
0x14000f4c8  sub     r9d, 1
0x14000f4cc  jz      loc_14000F688
0x14000f4d2  sub     r9d, 1
0x14000f4d6  jz      loc_14000F5CF
0x14000f4dc  sub     r9d, 1
0x14000f4e0  jz      short loc_14000F556
0x14000f4e2  cmp     r9d, 1
0x14000f4e6  jz      short loc_14000F556
0x14000f4e8  add     r8d, 0FFFFFEC0h
0x14000f4ef  lea     ebx, [rax+1]
0x14000f4f2  cmp     r8d, 40h ; '@'
0x14000f4f6  jge     short loc_14000F541
0x14000f4f8  mov     eax, [rdx+4]
0x14000f4fb  lea     ecx, [rbx+0Fh]
0x14000f4fe  mov     r9d, r8d
0x14000f501  shl     r9d, 5
0x14000f505  test    cl, al
0x14000f507  jz      short loc_14000F51A
0x14000f509  mov     edx, eax
0x14000f50b  shr     edx, 5
0x14000f50e  and     edx, 3Fh
0x14000f511  cmp     edx, r8d
0x14000f514  jnz     short loc_14000F51A
0x14000f516  mov     edx, ebx
0x14000f518  jmp     short loc_14000F51C
0x14000f51a  xor     edx, edx
0x14000f51c  mov     [r10+10h], edx
0x14000f520  mov     edx, r9d
0x14000f523  xor     edx, eax
0x14000f525  and     edx, 7E0h
0x14000f52b  xor     edx, eax
0x14000f52d  or      edx, ecx
0x14000f52f  lock cmpxchg [rsi+4], edx
0x14000f534  jnz     short loc_14000F505
0x14000f536  cmp     dword ptr [r10+10h], 0
0x14000f53b  jnz     loc_14000F756
0x14000f541  mov     [r10+8], r11d
0x14000f545  mov     [r10+4], ebx
0x14000f549  mov     dword ptr [r10+0Ch], 0
0x14000f551  jmp     loc_14000F756
0x14000f556  xor     ecx, ecx
0x14000f558  sub     r11d, 2
0x14000f55c  jz      short loc_14000F584
0x14000f55e  sub     r11d, 1
0x14000f562  jz      short loc_14000F57D
0x14000f564  sub     r11d, 3
0x14000f568  jz      short loc_14000F576
0x14000f56a  cmp     r11d, 1
0x14000f56e  jnz     short loc_14000F589
0x14000f570  lea     ecx, [r11+0Fh]
0x14000f574  jmp     short loc_14000F589
0x14000f576  mov     ecx, 4
0x14000f57b  jmp     short loc_14000F589
0x14000f57d  mov     ecx, 8
0x14000f582  jmp     short loc_14000F589
0x14000f584  mov     ecx, 2
0x14000f589  mov     edx, [rdx]
0x14000f58b  mov     ebx, 1
0x14000f590  xor     eax, eax
0x14000f592  mov     r8d, ecx
0x14000f595  or      r8d, edx
0x14000f598  cmp     r8d, edx
0x14000f59b  mov     r9d, r8d
0x14000f59e  setz    al
0x14000f5a1  or      r9d, ebx
0x14000f5a4  cmp     r8d, edx
0x14000f5a7  mov     [r10+10h], eax
0x14000f5ab  mov     eax, edx
0x14000f5ad  cmovz   r9d, r8d
0x14000f5b1  lock cmpxchg [rsi], r9d
0x14000f5b6  jz      short loc_14000F5BC
0x14000f5b8  mov     edx, eax
0x14000f5ba  jmp     short loc_14000F590
0x14000f5bc  test    bl, r9b
0x14000f5bf  jz      short loc_14000F5C5
0x14000f5c1  test    bl, dl
0x14000f5c3  jz      short loc_14000F5C7
0x14000f5c5  xor     ebx, ebx
0x14000f5c7  mov     [r10], ebx
0x14000f5ca  jmp     loc_14000F756
0x14000f5cf  mov     ecx, [rdx]
0x14000f5d1  xor     r9d, r9d
0x14000f5d4  cmp     r11d, 5
0x14000f5d8  mov     ebx, 1
0x14000f5dd  setz    r9b
0x14000f5e1  mov     eax, ecx
0x14000f5e3  mov     dword ptr [r10+4], 0
0x14000f5eb  or      eax, ebx
0x14000f5ed  mov     edx, eax
0x14000f5ef  shr     edx, 16h
0x14000f5f2  and     edx, ebx
0x14000f5f4  cmp     edx, r9d
0x14000f5f7  jz      short loc_14000F639
0x14000f5f9  mov     r8d, eax
0x14000f5fc  shr     r8d, 0Fh
0x14000f600  and     r8d, 7Fh
0x14000f604  jbe     short loc_14000F61E
0x14000f606  cmp     r11d, ebx
0x14000f609  mov     [r10+4], r8d
0x14000f60d  mov     edx, 5
0x14000f612  cmovnz  edx, ebx
0x14000f615  and     eax, 0FFC07FFFh
0x14000f61a  mov     [r10+8], edx
0x14000f61e  xor     r8d, r8d
0x14000f621  mov     edx, 400000h
0x14000f626  cmp     r11d, 5
0x14000f62a  cmovz   r8d, edx
0x14000f62e  mov     edx, eax
0x14000f630  btr     edx, 16h
0x14000f634  mov     eax, r8d
0x14000f637  or      eax, edx
0x14000f639  mov     edx, eax
0x14000f63b  shr     edx, 0Fh
0x14000f63e  and     edx, 7Fh
0x14000f641  lea     r8d, [rdx+1]
0x14000f645  cmp     r8d, 7Fh
0x14000f649  ja      short loc_14000F650
0x14000f64b  cmp     r8d, edx
0x14000f64e  jnb     short loc_14000F65B
0x14000f650  mov     r8d, ebx
0x14000f653  mov     [r10+8], r11d
0x14000f657  mov     [r10+4], edx
0x14000f65b  shl     r8d, 0Fh
0x14000f65f  xor     r8d, eax
0x14000f662  and     r8d, 3F8000h
0x14000f669  xor     r8d, eax
0x14000f66c  mov     eax, ecx
0x14000f66e  lock cmpxchg [rsi], r8d
0x14000f673  jz      short loc_14000F67C
0x14000f675  mov     ecx, eax
0x14000f677  jmp     loc_14000F5E1
0x14000f67c  not     ecx
0x14000f67e  and     ecx, ebx
0x14000f680  mov     [r10], ecx
0x14000f683  jmp     loc_14000F74E
0x14000f688  mov     edx, [rdx]
0x14000f68a  xor     ebp, ebp
0x14000f68c  lea     ecx, [rbp+4]
0x14000f68f  cmp     r11d, ecx
0x14000f692  lea     ebx, [rcx-3]
0x14000f695  setz    bpl
0x14000f699  mov     eax, edx
0x14000f69b  mov     dword ptr [r10+4], 0
0x14000f6a3  or      eax, ebx
0x14000f6a5  mov     r8d, eax
0x14000f6a8  shr     r8d, 0Eh
0x14000f6ac  and     r8d, ebx
0x14000f6af  cmp     r8d, ebp
0x14000f6b2  jz      short loc_14000F6FB
0x14000f6b4  mov     edi, eax
0x14000f6b6  shr     edi, 5
0x14000f6b9  and     edi, 1FFh
0x14000f6bf  jbe     short loc_14000F6DD
0x14000f6c1  mov     r8d, r11d
0x14000f6c4  mov     [r10+4], edi
0x14000f6c8  neg     r8d
0x14000f6cb  sbb     r9d, r9d
0x14000f6ce  not     r9d
0x14000f6d1  and     r9d, ecx
0x14000f6d4  mov     [r10+8], r9d
0x14000f6d8  and     eax, 0FFFFC01Fh
0x14000f6dd  xor     r9d, r9d
0x14000f6e0  mov     r8d, 4000h
0x14000f6e6  cmp     r11d, ecx
0x14000f6e9  cmovz   r9d, r8d
0x14000f6ed  mov     r8d, eax
0x14000f6f0  btr     r8d, 0Eh
0x14000f6f5  mov     eax, r9d
0x14000f6f8  or      eax, r8d
0x14000f6fb  mov     r8d, eax
0x14000f6fe  shr     r8d, 5
0x14000f702  and     r8d, 1FFh
0x14000f709  lea     r9d, [r8+1]
0x14000f70d  cmp     r9d, 1FFh
0x14000f714  ja      short loc_14000F71B
0x14000f716  cmp     r9d, r8d
0x14000f719  jnb     short loc_14000F726
0x14000f71b  mov     r9d, ebx
0x14000f71e  mov     [r10+8], r11d
0x14000f722  mov     [r10+4], r8d
0x14000f726  shl     r9d, 5
0x14000f72a  xor     r9d, eax
0x14000f72d  and     r9d, 3FE0h
0x14000f734  xor     r9d, eax
0x14000f737  mov     eax, edx
0x14000f739  lock cmpxchg [rsi], r9d
0x14000f73e  jz      short loc_14000F747
0x14000f740  mov     edx, eax
0x14000f742  jmp     loc_14000F699
0x14000f747  not     edx
0x14000f749  and     edx, ebx
0x14000f74b  mov     [r10], edx
0x14000f74e  mov     dword ptr [r10+10h], 0
0x14000f756  mov     rax, r10
0x14000f759  pop     rdi
0x14000f75a  pop     rsi
0x14000f75b  pop     rbp
0x14000f75c  pop     rbx
0x14000f75d  retn
```
