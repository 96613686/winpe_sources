# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000f554`
- end: `0x18000f834`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c918`

## callees

- `0x18000f554`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // ecx
  unsigned __int32 v9; // ett
  int v10; // edx
  signed __int32 v11; // eax
  int v12; // ebx
  char v13; // r9
  signed __int32 v14; // r8d
  signed __int32 v15; // ett
  signed __int32 v16; // eax
  BOOL v17; // edi
  unsigned int v18; // ecx
  char v19; // r9
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // edx
  signed __int32 v24; // ett
  signed __int32 v25; // eax
  BOOL v26; // r14d
  unsigned int v27; // ecx
  char v28; // di
  int v29; // r9d
  unsigned int v30; // r9d
  unsigned int v31; // r8d
  signed __int32 v32; // ett

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_47;
    case 1:
      goto LABEL_33;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_47:
      v25 = *a2;
      v26 = a3 == 4;
      do
      {
        *(_DWORD *)(a1 + 4) = 0;
        v27 = v25 | 1;
        v28 = v25;
        if ( (((v25 | 1u) >> 14) & 1) != v26 )
        {
          if ( ((v27 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v27 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v27 = v25 & 0xFFFFC01E | 1;
          }
          v29 = 0;
          if ( a3 == 4 )
            v29 = 0x4000;
          v27 = v27 & 0xFFFFBFFF | v29;
        }
        v30 = (v27 >> 5) & 0x1FF;
        v31 = v30 + 1;
        if ( v30 + 1 > 0x1FF || v31 < v30 )
        {
          LOWORD(v31) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v30;
        }
        v32 = v25;
        v25 = _InterlockedCompareExchange(
                a2,
                ((unsigned __int16)v27 ^ (unsigned __int16)(32 * v31)) & 0x3FE0 ^ v27,
                v25);
      }
      while ( v32 != v25 );
      *(_DWORD *)a1 = (v28 & 1) == 0;
      goto LABEL_59;
    case 5:
LABEL_33:
      v16 = *a2;
      v17 = a3 == 5;
      do
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        v19 = v16;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v20 = 5;
            if ( a3 != 1 )
              v20 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v20;
          }
          v21 = 0;
          if ( a3 == 5 )
            v21 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v21;
        }
        v22 = (v18 >> 15) & 0x7F;
        v23 = v22 + 1;
        if ( v22 + 1 > 0x7F || v23 < v22 )
        {
          v23 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v22;
        }
        v24 = v16;
        v16 = _InterlockedCompareExchange(a2, (v18 ^ (v23 << 15)) & 0x3F8000 ^ v18, v16);
      }
      while ( v24 != v16 );
      *(_DWORD *)a1 = (v19 & 1) == 0;
LABEL_59:
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
      *(_DWORD *)(a1 + 12) = 0;
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
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
  do
  {
    v13 = v11;
    *(_DWORD *)(a1 + 16) = (v11 | v10) == v11;
    v14 = v11 | v10 | 1;
    if ( (v11 | v10) == v11 )
      v14 = v11 | v10;
    v15 = v11;
    v11 = _InterlockedCompareExchange(a2, v14, v11);
  }
  while ( v15 != v11 );
  if ( (v14 & 1) == 0 || (v13 & 1) != 0 )
    v12 = 0;
  *(_DWORD *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x18000f554  mov     rax, rsp
0x18000f557  mov     [rax+8], rbx
0x18000f55b  mov     [rax+10h], rbp
0x18000f55f  mov     [rax+18h], rsi
0x18000f563  mov     [rax+20h], rdi
0x18000f567  push    r14
0x18000f569  xor     eax, eax
0x18000f56b  xorps   xmm0, xmm0
0x18000f56e  mov     r10, rcx
0x18000f571  mov     r11d, r8d
0x18000f574  mov     rsi, rdx
0x18000f577  movups  xmmword ptr [rcx], xmm0
0x18000f57a  mov     [rcx+10h], rax
0x18000f57e  mov     ecx, r8d
0x18000f581  test    r8d, r8d
0x18000f584  jz      loc_18000F752
0x18000f58a  sub     ecx, 1
0x18000f58d  jz      loc_18000F6A1
0x18000f593  sub     ecx, 1
0x18000f596  jz      loc_18000F62C
0x18000f59c  sub     ecx, 1
0x18000f59f  jz      loc_18000F62C
0x18000f5a5  sub     ecx, 1
0x18000f5a8  jz      loc_18000F752
0x18000f5ae  sub     ecx, 1
0x18000f5b1  jz      loc_18000F6A1
0x18000f5b7  sub     ecx, 1
0x18000f5ba  jz      short loc_18000F62C
0x18000f5bc  cmp     ecx, 1
0x18000f5bf  jz      short loc_18000F62C
0x18000f5c1  add     r8d, 0FFFFFEC0h
0x18000f5c8  lea     ebx, [rax+1]
0x18000f5cb  cmp     r8d, 40h ; '@'
0x18000f5cf  jge     short loc_18000F61A
0x18000f5d1  mov     eax, [rdx+4]
0x18000f5d4  mov     r9d, r8d
0x18000f5d7  shl     r9d, 5
0x18000f5db  lea     edx, [rbx+0Fh]
0x18000f5de  test    dl, al
0x18000f5e0  jz      short loc_18000F5F3
0x18000f5e2  mov     ecx, eax
0x18000f5e4  shr     ecx, 5
0x18000f5e7  and     ecx, 3Fh
0x18000f5ea  cmp     ecx, r8d
0x18000f5ed  jnz     short loc_18000F5F3
0x18000f5ef  mov     ecx, ebx
0x18000f5f1  jmp     short loc_18000F5F5
0x18000f5f3  xor     ecx, ecx
0x18000f5f5  mov     [r10+10h], ecx
0x18000f5f9  mov     ecx, r9d
0x18000f5fc  xor     ecx, eax
0x18000f5fe  and     ecx, 7E0h
0x18000f604  xor     ecx, eax
0x18000f606  or      ecx, edx
0x18000f608  lock cmpxchg [rsi+4], ecx
0x18000f60d  jnz     short loc_18000F5DE
0x18000f60f  cmp     dword ptr [r10+10h], 0
0x18000f614  jnz     loc_18000F819
0x18000f61a  and     dword ptr [r10+0Ch], 0
0x18000f61f  mov     [r10+8], r11d
0x18000f623  mov     [r10+4], ebx
0x18000f627  jmp     loc_18000F819
0x18000f62c  xor     edx, edx
0x18000f62e  sub     r11d, 2
0x18000f632  jz      short loc_18000F65A
0x18000f634  sub     r11d, 1
0x18000f638  jz      short loc_18000F653
0x18000f63a  sub     r11d, 3
0x18000f63e  jz      short loc_18000F64C
0x18000f640  cmp     r11d, 1
0x18000f644  jnz     short loc_18000F65F
0x18000f646  lea     edx, [r11+0Fh]
0x18000f64a  jmp     short loc_18000F65F
0x18000f64c  mov     edx, 4
0x18000f651  jmp     short loc_18000F65F
0x18000f653  mov     edx, 8
0x18000f658  jmp     short loc_18000F65F
0x18000f65a  mov     edx, 2
0x18000f65f  mov     eax, [rsi]
0x18000f661  mov     ebx, 1
0x18000f666  xor     r8d, r8d
0x18000f669  mov     ecx, edx
0x18000f66b  or      ecx, eax
0x18000f66d  mov     r9d, eax
0x18000f670  cmp     ecx, eax
0x18000f672  setz    r8b
0x18000f676  mov     [r10+10h], r8d
0x18000f67a  mov     r8d, ecx
0x18000f67d  or      r8d, ebx
0x18000f680  cmp     ecx, eax
0x18000f682  cmovz   r8d, ecx
0x18000f686  lock cmpxchg [rsi], r8d
0x18000f68b  jnz     short loc_18000F666
0x18000f68d  test    bl, r8b
0x18000f690  jz      short loc_18000F697
0x18000f692  test    bl, r9b
0x18000f695  jz      short loc_18000F699
0x18000f697  xor     ebx, ebx
0x18000f699  mov     [r10], ebx
0x18000f69c  jmp     loc_18000F819
0x18000f6a1  mov     eax, [rdx]
0x18000f6a3  xor     edi, edi
0x18000f6a5  cmp     r11d, 5
0x18000f6a9  mov     ebx, 1
0x18000f6ae  setz    dil
0x18000f6b2  and     dword ptr [r10+4], 0
0x18000f6b7  mov     ecx, eax
0x18000f6b9  or      ecx, ebx
0x18000f6bb  mov     r9d, eax
0x18000f6be  mov     edx, ecx
0x18000f6c0  shr     edx, 16h
0x18000f6c3  and     edx, ebx
0x18000f6c5  cmp     edx, edi
0x18000f6c7  jz      short loc_18000F70A
0x18000f6c9  mov     r8d, ecx
0x18000f6cc  shr     r8d, 0Fh
0x18000f6d0  and     r8d, 7Fh
0x18000f6d4  jbe     short loc_18000F6EF
0x18000f6d6  cmp     r11d, ebx
0x18000f6d9  mov     [r10+4], r8d
0x18000f6dd  mov     edx, 5
0x18000f6e2  cmovnz  edx, ebx
0x18000f6e5  and     ecx, 0FFC07FFFh
0x18000f6eb  mov     [r10+8], edx
0x18000f6ef  xor     r8d, r8d
0x18000f6f2  mov     edx, 400000h
0x18000f6f7  cmp     r11d, 5
0x18000f6fb  cmovz   r8d, edx
0x18000f6ff  mov     edx, ecx
0x18000f701  btr     edx, 16h
0x18000f705  mov     ecx, r8d
0x18000f708  or      ecx, edx
0x18000f70a  mov     r8d, ecx
0x18000f70d  shr     r8d, 0Fh
0x18000f711  and     r8d, 7Fh
0x18000f715  lea     edx, [r8+1]
0x18000f719  cmp     edx, 7Fh
0x18000f71c  ja      short loc_18000F723
0x18000f71e  cmp     edx, r8d
0x18000f721  jnb     short loc_18000F72D
0x18000f723  mov     edx, ebx
0x18000f725  mov     [r10+8], r11d
0x18000f729  mov     [r10+4], r8d
0x18000f72d  shl     edx, 0Fh
0x18000f730  xor     edx, ecx
0x18000f732  and     edx, 3F8000h
0x18000f738  xor     ecx, edx
0x18000f73a  lock cmpxchg [rsi], ecx
0x18000f73e  jnz     loc_18000F6B2
0x18000f744  not     r9d
0x18000f747  and     r9d, ebx
0x18000f74a  mov     [r10], r9d
0x18000f74d  jmp     loc_18000F814
0x18000f752  mov     eax, [rdx]
0x18000f754  xor     r14d, r14d
0x18000f757  lea     edx, [r14+4]
0x18000f75b  cmp     r11d, edx
0x18000f75e  lea     ebx, [rdx-3]
0x18000f761  setz    r14b
0x18000f765  and     dword ptr [r10+4], 0
0x18000f76a  mov     ecx, eax
0x18000f76c  or      ecx, ebx
0x18000f76e  mov     edi, eax
0x18000f770  mov     r8d, ecx
0x18000f773  shr     r8d, 0Eh
0x18000f777  and     r8d, ebx
0x18000f77a  cmp     r8d, r14d
0x18000f77d  jz      short loc_18000F7C7
0x18000f77f  mov     ebp, ecx
0x18000f781  shr     ebp, 5
0x18000f784  and     ebp, 1FFh
0x18000f78a  jbe     short loc_18000F7A9
0x18000f78c  mov     r8d, r11d
0x18000f78f  mov     [r10+4], ebp
0x18000f793  neg     r8d
0x18000f796  sbb     r9d, r9d
0x18000f799  not     r9d
0x18000f79c  and     r9d, edx
0x18000f79f  mov     [r10+8], r9d
0x18000f7a3  and     ecx, 0FFFFC01Fh
0x18000f7a9  xor     r9d, r9d
0x18000f7ac  mov     r8d, 4000h
0x18000f7b2  cmp     r11d, edx
0x18000f7b5  cmovz   r9d, r8d
0x18000f7b9  mov     r8d, ecx
0x18000f7bc  btr     r8d, 0Eh
0x18000f7c1  mov     ecx, r9d
0x18000f7c4  or      ecx, r8d
0x18000f7c7  mov     r9d, ecx
0x18000f7ca  shr     r9d, 5
0x18000f7ce  and     r9d, 1FFh
0x18000f7d5  lea     r8d, [r9+1]
0x18000f7d9  cmp     r8d, 1FFh
0x18000f7e0  ja      short loc_18000F7E7
0x18000f7e2  cmp     r8d, r9d
0x18000f7e5  jnb     short loc_18000F7F2
0x18000f7e7  mov     r8d, ebx
0x18000f7ea  mov     [r10+8], r11d
0x18000f7ee  mov     [r10+4], r9d
0x18000f7f2  shl     r8d, 5
0x18000f7f6  xor     r8d, ecx
0x18000f7f9  and     r8d, 3FE0h
0x18000f800  xor     ecx, r8d
0x18000f803  lock cmpxchg [rsi], ecx
0x18000f807  jnz     loc_18000F765
0x18000f80d  not     edi
0x18000f80f  and     edi, ebx
0x18000f811  mov     [r10], edi
0x18000f814  and     dword ptr [r10+10h], 0
0x18000f819  mov     rbx, [rsp+8+arg_0]
0x18000f81e  mov     rax, r10
0x18000f821  mov     rbp, [rsp+8+arg_8]
0x18000f826  mov     rsi, [rsp+8+arg_10]
0x18000f82b  mov     rdi, [rsp+8+arg_18]
0x18000f830  pop     r14
0x18000f832  retn
```
