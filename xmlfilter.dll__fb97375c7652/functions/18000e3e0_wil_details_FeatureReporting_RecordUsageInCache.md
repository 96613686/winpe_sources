# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000e3e0`
- end: `0x18000e6ba`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b418`

## callees

- `0x18000e3e0`

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
0x18000e3e0  push    rbx
0x18000e3e2  push    rbp
0x18000e3e3  push    rsi
0x18000e3e4  push    rdi
0x18000e3e5  xor     eax, eax
0x18000e3e7  xorps   xmm0, xmm0
0x18000e3ea  mov     r11d, r8d
0x18000e3ed  mov     rsi, rdx
0x18000e3f0  mov     r10, rcx
0x18000e3f3  mov     r9d, r8d
0x18000e3f6  movups  xmmword ptr [rcx], xmm0
0x18000e3f9  mov     [rcx+10h], rax
0x18000e3fd  test    r8d, r8d
0x18000e400  jz      loc_18000E5E4
0x18000e406  sub     r9d, 1
0x18000e40a  jz      loc_18000E52B
0x18000e410  sub     r9d, 1
0x18000e414  jz      loc_18000E4B2
0x18000e41a  sub     r9d, 1
0x18000e41e  jz      loc_18000E4B2
0x18000e424  sub     r9d, 1
0x18000e428  jz      loc_18000E5E4
0x18000e42e  sub     r9d, 1
0x18000e432  jz      loc_18000E52B
0x18000e438  sub     r9d, 1
0x18000e43c  jz      short loc_18000E4B2
0x18000e43e  cmp     r9d, 1
0x18000e442  jz      short loc_18000E4B2
0x18000e444  add     r8d, 0FFFFFEC0h
0x18000e44b  lea     ebx, [rax+1]
0x18000e44e  cmp     r8d, 40h ; '@'
0x18000e452  jge     short loc_18000E49D
0x18000e454  mov     eax, [rdx+4]
0x18000e457  lea     ecx, [rbx+0Fh]
0x18000e45a  mov     r9d, r8d
0x18000e45d  shl     r9d, 5
0x18000e461  test    cl, al
0x18000e463  jz      short loc_18000E476
0x18000e465  mov     edx, eax
0x18000e467  shr     edx, 5
0x18000e46a  and     edx, 3Fh
0x18000e46d  cmp     edx, r8d
0x18000e470  jnz     short loc_18000E476
0x18000e472  mov     edx, ebx
0x18000e474  jmp     short loc_18000E478
0x18000e476  xor     edx, edx
0x18000e478  mov     [r10+10h], edx
0x18000e47c  mov     edx, r9d
0x18000e47f  xor     edx, eax
0x18000e481  and     edx, 7E0h
0x18000e487  xor     edx, eax
0x18000e489  or      edx, ecx
0x18000e48b  lock cmpxchg [rsi+4], edx
0x18000e490  jnz     short loc_18000E461
0x18000e492  cmp     dword ptr [r10+10h], 0
0x18000e497  jnz     loc_18000E6B2
0x18000e49d  mov     [r10+8], r11d
0x18000e4a1  mov     [r10+4], ebx
0x18000e4a5  mov     dword ptr [r10+0Ch], 0
0x18000e4ad  jmp     loc_18000E6B2
0x18000e4b2  xor     ecx, ecx
0x18000e4b4  sub     r11d, 2
0x18000e4b8  jz      short loc_18000E4E0
0x18000e4ba  sub     r11d, 1
0x18000e4be  jz      short loc_18000E4D9
0x18000e4c0  sub     r11d, 3
0x18000e4c4  jz      short loc_18000E4D2
0x18000e4c6  cmp     r11d, 1
0x18000e4ca  jnz     short loc_18000E4E5
0x18000e4cc  lea     ecx, [r11+0Fh]
0x18000e4d0  jmp     short loc_18000E4E5
0x18000e4d2  mov     ecx, 4
0x18000e4d7  jmp     short loc_18000E4E5
0x18000e4d9  mov     ecx, 8
0x18000e4de  jmp     short loc_18000E4E5
0x18000e4e0  mov     ecx, 2
0x18000e4e5  mov     edx, [rdx]
0x18000e4e7  mov     ebx, 1
0x18000e4ec  xor     eax, eax
0x18000e4ee  mov     r8d, ecx
0x18000e4f1  or      r8d, edx
0x18000e4f4  cmp     r8d, edx
0x18000e4f7  mov     r9d, r8d
0x18000e4fa  setz    al
0x18000e4fd  or      r9d, ebx
0x18000e500  cmp     r8d, edx
0x18000e503  mov     [r10+10h], eax
0x18000e507  mov     eax, edx
0x18000e509  cmovz   r9d, r8d
0x18000e50d  lock cmpxchg [rsi], r9d
0x18000e512  jz      short loc_18000E518
0x18000e514  mov     edx, eax
0x18000e516  jmp     short loc_18000E4EC
0x18000e518  test    bl, r9b
0x18000e51b  jz      short loc_18000E521
0x18000e51d  test    bl, dl
0x18000e51f  jz      short loc_18000E523
0x18000e521  xor     ebx, ebx
0x18000e523  mov     [r10], ebx
0x18000e526  jmp     loc_18000E6B2
0x18000e52b  mov     ecx, [rdx]
0x18000e52d  xor     r9d, r9d
0x18000e530  cmp     r11d, 5
0x18000e534  mov     ebx, 1
0x18000e539  setz    r9b
0x18000e53d  mov     eax, ecx
0x18000e53f  mov     dword ptr [r10+4], 0
0x18000e547  or      eax, ebx
0x18000e549  mov     edx, eax
0x18000e54b  shr     edx, 16h
0x18000e54e  and     edx, ebx
0x18000e550  cmp     edx, r9d
0x18000e553  jz      short loc_18000E595
0x18000e555  mov     r8d, eax
0x18000e558  shr     r8d, 0Fh
0x18000e55c  and     r8d, 7Fh
0x18000e560  jbe     short loc_18000E57A
0x18000e562  cmp     r11d, ebx
0x18000e565  mov     [r10+4], r8d
0x18000e569  mov     edx, 5
0x18000e56e  cmovnz  edx, ebx
0x18000e571  and     eax, 0FFC07FFFh
0x18000e576  mov     [r10+8], edx
0x18000e57a  xor     r8d, r8d
0x18000e57d  mov     edx, 400000h
0x18000e582  cmp     r11d, 5
0x18000e586  cmovz   r8d, edx
0x18000e58a  mov     edx, eax
0x18000e58c  btr     edx, 16h
0x18000e590  mov     eax, r8d
0x18000e593  or      eax, edx
0x18000e595  mov     edx, eax
0x18000e597  shr     edx, 0Fh
0x18000e59a  and     edx, 7Fh
0x18000e59d  lea     r8d, [rdx+1]
0x18000e5a1  cmp     r8d, 7Fh
0x18000e5a5  ja      short loc_18000E5AC
0x18000e5a7  cmp     r8d, edx
0x18000e5aa  jnb     short loc_18000E5B7
0x18000e5ac  mov     r8d, ebx
0x18000e5af  mov     [r10+8], r11d
0x18000e5b3  mov     [r10+4], edx
0x18000e5b7  shl     r8d, 0Fh
0x18000e5bb  xor     r8d, eax
0x18000e5be  and     r8d, 3F8000h
0x18000e5c5  xor     r8d, eax
0x18000e5c8  mov     eax, ecx
0x18000e5ca  lock cmpxchg [rsi], r8d
0x18000e5cf  jz      short loc_18000E5D8
0x18000e5d1  mov     ecx, eax
0x18000e5d3  jmp     loc_18000E53D
0x18000e5d8  not     ecx
0x18000e5da  and     ecx, ebx
0x18000e5dc  mov     [r10], ecx
0x18000e5df  jmp     loc_18000E6AA
0x18000e5e4  mov     edx, [rdx]
0x18000e5e6  xor     ebp, ebp
0x18000e5e8  lea     ecx, [rbp+4]
0x18000e5eb  cmp     r11d, ecx
0x18000e5ee  lea     ebx, [rcx-3]
0x18000e5f1  setz    bpl
0x18000e5f5  mov     eax, edx
0x18000e5f7  mov     dword ptr [r10+4], 0
0x18000e5ff  or      eax, ebx
0x18000e601  mov     r8d, eax
0x18000e604  shr     r8d, 0Eh
0x18000e608  and     r8d, ebx
0x18000e60b  cmp     r8d, ebp
0x18000e60e  jz      short loc_18000E657
0x18000e610  mov     edi, eax
0x18000e612  shr     edi, 5
0x18000e615  and     edi, 1FFh
0x18000e61b  jbe     short loc_18000E639
0x18000e61d  mov     r8d, r11d
0x18000e620  mov     [r10+4], edi
0x18000e624  neg     r8d
0x18000e627  sbb     r9d, r9d
0x18000e62a  not     r9d
0x18000e62d  and     r9d, ecx
0x18000e630  mov     [r10+8], r9d
0x18000e634  and     eax, 0FFFFC01Fh
0x18000e639  xor     r9d, r9d
0x18000e63c  mov     r8d, 4000h
0x18000e642  cmp     r11d, ecx
0x18000e645  cmovz   r9d, r8d
0x18000e649  mov     r8d, eax
0x18000e64c  btr     r8d, 0Eh
0x18000e651  mov     eax, r9d
0x18000e654  or      eax, r8d
0x18000e657  mov     r8d, eax
0x18000e65a  shr     r8d, 5
0x18000e65e  and     r8d, 1FFh
0x18000e665  lea     r9d, [r8+1]
0x18000e669  cmp     r9d, 1FFh
0x18000e670  ja      short loc_18000E677
0x18000e672  cmp     r9d, r8d
0x18000e675  jnb     short loc_18000E682
0x18000e677  mov     r9d, ebx
0x18000e67a  mov     [r10+8], r11d
0x18000e67e  mov     [r10+4], r8d
0x18000e682  shl     r9d, 5
0x18000e686  xor     r9d, eax
0x18000e689  and     r9d, 3FE0h
0x18000e690  xor     r9d, eax
0x18000e693  mov     eax, edx
0x18000e695  lock cmpxchg [rsi], r9d
0x18000e69a  jz      short loc_18000E6A3
0x18000e69c  mov     edx, eax
0x18000e69e  jmp     loc_18000E5F5
0x18000e6a3  not     edx
0x18000e6a5  and     edx, ebx
0x18000e6a7  mov     [r10], edx
0x18000e6aa  mov     dword ptr [r10+10h], 0
0x18000e6b2  mov     rax, r10
0x18000e6b5  pop     rdi
0x18000e6b6  pop     rsi
0x18000e6b7  pop     rbp
0x18000e6b8  pop     rbx
0x18000e6b9  retn
```
