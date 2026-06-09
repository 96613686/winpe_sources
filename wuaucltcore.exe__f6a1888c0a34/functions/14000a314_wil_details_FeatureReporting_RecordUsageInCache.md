# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000a314`
- end: `0x14000a5e6`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a788`

## callees

- `0x14000a314`

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
  int v16; // r9d
  unsigned int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  unsigned int v20; // edx
  signed __int32 v21; // eax
  signed __int32 v22; // edx
  int v23; // ebp
  unsigned int v24; // eax
  unsigned int v25; // r9d
  unsigned int v26; // r8d
  signed __int32 v27; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_47;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_47:
      v22 = *a2;
      v23 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v24 = v22 | 1;
        if ( (((v22 | 1u) >> 14) & 1) != v23 )
        {
          if ( ((v24 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v24 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v24 = v22 & 0xFFFFC01E | 1;
          }
          v24 = (v23 << 14) | v24 & 0xFFFFBFFF;
        }
        v25 = (v24 >> 5) & 0x1FF;
        v26 = v25 + 1;
        if ( v25 + 1 > 0x1FF || v26 < v25 )
        {
          LOWORD(v26) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v25;
        }
        v27 = _InterlockedCompareExchange(
                a2,
                v24 ^ ((unsigned __int16)v24 ^ (unsigned __int16)(32 * v26)) & 0x3FE0,
                v22);
        if ( v22 == v27 )
          break;
        v22 = v27;
      }
      *(_DWORD *)a1 = (v22 & 1) == 0;
      goto LABEL_58;
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
            v18 = 1;
            if ( a3 == 1 )
              v18 = 5;
            v17 = v15 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v18;
          }
          v17 = v17 & 0xFFBFFFFF | (v16 << 22);
        }
        v19 = (v17 >> 15) & 0x7F;
        v20 = v19 + 1;
        if ( v19 + 1 > 0x7F || v20 < v19 )
        {
          v20 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v19;
        }
        v21 = _InterlockedCompareExchange(a2, v17 ^ (v17 ^ (v20 << 15)) & 0x3F8000, v15);
        if ( v15 == v21 )
          break;
        v15 = v21;
      }
      *(_DWORD *)a1 = (v15 & 1) == 0;
LABEL_58:
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
0x14000a314  mov     rax, rsp
0x14000a317  mov     [rax+8], rbx
0x14000a31b  mov     [rax+10h], rbp
0x14000a31f  mov     [rax+18h], rsi
0x14000a323  mov     [rax+20h], rdi
0x14000a327  xor     eax, eax
0x14000a329  xorps   xmm0, xmm0
0x14000a32c  mov     r10, rcx
0x14000a32f  mov     r11d, r8d
0x14000a332  mov     rsi, rdx
0x14000a335  movups  xmmword ptr [rcx], xmm0
0x14000a338  mov     [rcx+10h], rax
0x14000a33c  mov     ecx, r8d
0x14000a33f  test    r8d, r8d
0x14000a342  jz      loc_14000A510
0x14000a348  sub     ecx, 1
0x14000a34b  jz      loc_14000A466
0x14000a351  sub     ecx, 1
0x14000a354  jz      loc_14000A3ED
0x14000a35a  sub     ecx, 1
0x14000a35d  jz      loc_14000A3ED
0x14000a363  sub     ecx, 1
0x14000a366  jz      loc_14000A510
0x14000a36c  sub     ecx, 1
0x14000a36f  jz      loc_14000A466
0x14000a375  sub     ecx, 1
0x14000a378  jz      short loc_14000A3ED
0x14000a37a  cmp     ecx, 1
0x14000a37d  jz      short loc_14000A3ED
0x14000a37f  add     r8d, 0FFFFFEC0h
0x14000a386  lea     ebx, [rax+1]
0x14000a389  cmp     r8d, 40h ; '@'
0x14000a38d  jge     short loc_14000A3D8
0x14000a38f  mov     eax, [rdx+4]
0x14000a392  lea     ecx, [rbx+0Fh]
0x14000a395  mov     r9d, r8d
0x14000a398  shl     r9d, 5
0x14000a39c  test    cl, al
0x14000a39e  jz      short loc_14000A3B1
0x14000a3a0  mov     edx, eax
0x14000a3a2  shr     edx, 5
0x14000a3a5  and     edx, 3Fh
0x14000a3a8  cmp     edx, r8d
0x14000a3ab  jnz     short loc_14000A3B1
0x14000a3ad  mov     edx, ebx
0x14000a3af  jmp     short loc_14000A3B3
0x14000a3b1  xor     edx, edx
0x14000a3b3  mov     [r10+10h], edx
0x14000a3b7  mov     edx, r9d
0x14000a3ba  xor     edx, eax
0x14000a3bc  and     edx, 7E0h
0x14000a3c2  xor     edx, eax
0x14000a3c4  or      edx, ecx
0x14000a3c6  lock cmpxchg [rsi+4], edx
0x14000a3cb  jnz     short loc_14000A39C
0x14000a3cd  cmp     dword ptr [r10+10h], 0
0x14000a3d2  jnz     loc_14000A5CE
0x14000a3d8  mov     [r10+8], r11d
0x14000a3dc  mov     [r10+4], ebx
0x14000a3e0  mov     dword ptr [r10+0Ch], 0
0x14000a3e8  jmp     loc_14000A5CE
0x14000a3ed  xor     ecx, ecx
0x14000a3ef  sub     r11d, 2
0x14000a3f3  jz      short loc_14000A41B
0x14000a3f5  sub     r11d, 1
0x14000a3f9  jz      short loc_14000A414
0x14000a3fb  sub     r11d, 3
0x14000a3ff  jz      short loc_14000A40D
0x14000a401  cmp     r11d, 1
0x14000a405  jnz     short loc_14000A420
0x14000a407  lea     ecx, [r11+0Fh]
0x14000a40b  jmp     short loc_14000A420
0x14000a40d  mov     ecx, 4
0x14000a412  jmp     short loc_14000A420
0x14000a414  mov     ecx, 8
0x14000a419  jmp     short loc_14000A420
0x14000a41b  mov     ecx, 2
0x14000a420  mov     edx, [rdx]
0x14000a422  mov     ebx, 1
0x14000a427  xor     eax, eax
0x14000a429  mov     r8d, ecx
0x14000a42c  or      r8d, edx
0x14000a42f  cmp     r8d, edx
0x14000a432  mov     r9d, r8d
0x14000a435  setz    al
0x14000a438  or      r9d, ebx
0x14000a43b  cmp     r8d, edx
0x14000a43e  mov     [r10+10h], eax
0x14000a442  mov     eax, edx
0x14000a444  cmovz   r9d, r8d
0x14000a448  lock cmpxchg [rsi], r9d
0x14000a44d  jz      short loc_14000A453
0x14000a44f  mov     edx, eax
0x14000a451  jmp     short loc_14000A427
0x14000a453  test    bl, r9b
0x14000a456  jz      short loc_14000A45C
0x14000a458  test    bl, dl
0x14000a45a  jz      short loc_14000A45E
0x14000a45c  xor     ebx, ebx
0x14000a45e  mov     [r10], ebx
0x14000a461  jmp     loc_14000A5CE
0x14000a466  mov     ecx, [rdx]
0x14000a468  xor     r9d, r9d
0x14000a46b  lea     edi, [r9+5]
0x14000a46f  cmp     r11d, edi
0x14000a472  lea     ebx, [rdi-4]
0x14000a475  setz    r9b
0x14000a479  mov     eax, ecx
0x14000a47b  mov     dword ptr [r10+4], 0
0x14000a483  or      eax, ebx
0x14000a485  mov     edx, eax
0x14000a487  shr     edx, 16h
0x14000a48a  and     edx, ebx
0x14000a48c  cmp     edx, r9d
0x14000a48f  jz      short loc_14000A4C5
0x14000a491  mov     r8d, eax
0x14000a494  shr     r8d, 0Fh
0x14000a498  and     r8d, 7Fh
0x14000a49c  jbe     short loc_14000A4B3
0x14000a49e  cmp     r11d, ebx
0x14000a4a1  mov     [r10+4], r8d
0x14000a4a5  mov     edx, ebx
0x14000a4a7  cmovz   edx, edi
0x14000a4aa  and     eax, 0FFC07FFFh
0x14000a4af  mov     [r10+8], edx
0x14000a4b3  mov     edx, eax
0x14000a4b5  mov     r8d, r9d
0x14000a4b8  shl     r8d, 16h
0x14000a4bc  btr     edx, 16h
0x14000a4c0  mov     eax, r8d
0x14000a4c3  or      eax, edx
0x14000a4c5  mov     r8d, eax
0x14000a4c8  shr     r8d, 0Fh
0x14000a4cc  and     r8d, 7Fh
0x14000a4d0  lea     edx, [r8+1]
0x14000a4d4  cmp     edx, 7Fh
0x14000a4d7  ja      short loc_14000A4DE
0x14000a4d9  cmp     edx, r8d
0x14000a4dc  jnb     short loc_14000A4E8
0x14000a4de  mov     edx, ebx
0x14000a4e0  mov     [r10+8], r11d
0x14000a4e4  mov     [r10+4], r8d
0x14000a4e8  shl     edx, 0Fh
0x14000a4eb  xor     edx, eax
0x14000a4ed  and     edx, 3F8000h
0x14000a4f3  xor     edx, eax
0x14000a4f5  mov     eax, ecx
0x14000a4f7  lock cmpxchg [rsi], edx
0x14000a4fb  jz      short loc_14000A504
0x14000a4fd  mov     ecx, eax
0x14000a4ff  jmp     loc_14000A479
0x14000a504  not     ecx
0x14000a506  and     ecx, ebx
0x14000a508  mov     [r10], ecx
0x14000a50b  jmp     loc_14000A5C6
0x14000a510  mov     edx, [rdx]
0x14000a512  xor     ebp, ebp
0x14000a514  lea     ecx, [rbp+4]
0x14000a517  cmp     r11d, ecx
0x14000a51a  lea     ebx, [rcx-3]
0x14000a51d  setz    bpl
0x14000a521  mov     eax, edx
0x14000a523  mov     dword ptr [r10+4], 0
0x14000a52b  or      eax, ebx
0x14000a52d  mov     r8d, eax
0x14000a530  shr     r8d, 0Eh
0x14000a534  and     r8d, ebx
0x14000a537  cmp     r8d, ebp
0x14000a53a  jz      short loc_14000A573
0x14000a53c  mov     edi, eax
0x14000a53e  shr     edi, 5
0x14000a541  and     edi, 1FFh
0x14000a547  jbe     short loc_14000A565
0x14000a549  mov     r8d, r11d
0x14000a54c  mov     [r10+4], edi
0x14000a550  neg     r8d
0x14000a553  sbb     r9d, r9d
0x14000a556  not     r9d
0x14000a559  and     r9d, ecx
0x14000a55c  mov     [r10+8], r9d
0x14000a560  and     eax, 0FFFFC01Fh
0x14000a565  mov     r8d, ebp
0x14000a568  btr     eax, 0Eh
0x14000a56c  shl     r8d, 0Eh
0x14000a570  or      eax, r8d
0x14000a573  mov     r9d, eax
0x14000a576  shr     r9d, 5
0x14000a57a  and     r9d, 1FFh
0x14000a581  lea     r8d, [r9+1]
0x14000a585  cmp     r8d, 1FFh
0x14000a58c  ja      short loc_14000A593
0x14000a58e  cmp     r8d, r9d
0x14000a591  jnb     short loc_14000A59E
0x14000a593  mov     r8d, ebx
0x14000a596  mov     [r10+8], r11d
0x14000a59a  mov     [r10+4], r9d
0x14000a59e  shl     r8d, 5
0x14000a5a2  xor     r8d, eax
0x14000a5a5  and     r8d, 3FE0h
0x14000a5ac  xor     r8d, eax
0x14000a5af  mov     eax, edx
0x14000a5b1  lock cmpxchg [rsi], r8d
0x14000a5b6  jz      short loc_14000A5BF
0x14000a5b8  mov     edx, eax
0x14000a5ba  jmp     loc_14000A521
0x14000a5bf  not     edx
0x14000a5c1  and     edx, ebx
0x14000a5c3  mov     [r10], edx
0x14000a5c6  mov     dword ptr [r10+10h], 0
0x14000a5ce  mov     rbx, [rsp+arg_0]
0x14000a5d3  mov     rax, r10
0x14000a5d6  mov     rbp, [rsp+arg_8]
0x14000a5db  mov     rsi, [rsp+arg_10]
0x14000a5e0  mov     rdi, [rsp+arg_18]
0x14000a5e5  retn
```
