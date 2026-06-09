# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000cbe0`
- end: `0x14000ceba`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a324`

## callees

- `0x14000cbe0`

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
0x14000cbe0  push    rbx
0x14000cbe2  push    rbp
0x14000cbe3  push    rsi
0x14000cbe4  push    rdi
0x14000cbe5  xor     eax, eax
0x14000cbe7  xorps   xmm0, xmm0
0x14000cbea  mov     r11d, r8d
0x14000cbed  mov     rsi, rdx
0x14000cbf0  mov     r10, rcx
0x14000cbf3  mov     r9d, r8d
0x14000cbf6  movups  xmmword ptr [rcx], xmm0
0x14000cbf9  mov     [rcx+10h], rax
0x14000cbfd  test    r8d, r8d
0x14000cc00  jz      loc_14000CDE4
0x14000cc06  sub     r9d, 1
0x14000cc0a  jz      loc_14000CD2B
0x14000cc10  sub     r9d, 1
0x14000cc14  jz      loc_14000CCB2
0x14000cc1a  sub     r9d, 1
0x14000cc1e  jz      loc_14000CCB2
0x14000cc24  sub     r9d, 1
0x14000cc28  jz      loc_14000CDE4
0x14000cc2e  sub     r9d, 1
0x14000cc32  jz      loc_14000CD2B
0x14000cc38  sub     r9d, 1
0x14000cc3c  jz      short loc_14000CCB2
0x14000cc3e  cmp     r9d, 1
0x14000cc42  jz      short loc_14000CCB2
0x14000cc44  add     r8d, 0FFFFFEC0h
0x14000cc4b  lea     ebx, [rax+1]
0x14000cc4e  cmp     r8d, 40h ; '@'
0x14000cc52  jge     short loc_14000CC9D
0x14000cc54  mov     eax, [rdx+4]
0x14000cc57  lea     ecx, [rbx+0Fh]
0x14000cc5a  mov     r9d, r8d
0x14000cc5d  shl     r9d, 5
0x14000cc61  test    cl, al
0x14000cc63  jz      short loc_14000CC76
0x14000cc65  mov     edx, eax
0x14000cc67  shr     edx, 5
0x14000cc6a  and     edx, 3Fh
0x14000cc6d  cmp     edx, r8d
0x14000cc70  jnz     short loc_14000CC76
0x14000cc72  mov     edx, ebx
0x14000cc74  jmp     short loc_14000CC78
0x14000cc76  xor     edx, edx
0x14000cc78  mov     [r10+10h], edx
0x14000cc7c  mov     edx, r9d
0x14000cc7f  xor     edx, eax
0x14000cc81  and     edx, 7E0h
0x14000cc87  xor     edx, eax
0x14000cc89  or      edx, ecx
0x14000cc8b  lock cmpxchg [rsi+4], edx
0x14000cc90  jnz     short loc_14000CC61
0x14000cc92  cmp     dword ptr [r10+10h], 0
0x14000cc97  jnz     loc_14000CEB2
0x14000cc9d  mov     [r10+8], r11d
0x14000cca1  mov     [r10+4], ebx
0x14000cca5  mov     dword ptr [r10+0Ch], 0
0x14000ccad  jmp     loc_14000CEB2
0x14000ccb2  xor     ecx, ecx
0x14000ccb4  sub     r11d, 2
0x14000ccb8  jz      short loc_14000CCE0
0x14000ccba  sub     r11d, 1
0x14000ccbe  jz      short loc_14000CCD9
0x14000ccc0  sub     r11d, 3
0x14000ccc4  jz      short loc_14000CCD2
0x14000ccc6  cmp     r11d, 1
0x14000ccca  jnz     short loc_14000CCE5
0x14000cccc  lea     ecx, [r11+0Fh]
0x14000ccd0  jmp     short loc_14000CCE5
0x14000ccd2  mov     ecx, 4
0x14000ccd7  jmp     short loc_14000CCE5
0x14000ccd9  mov     ecx, 8
0x14000ccde  jmp     short loc_14000CCE5
0x14000cce0  mov     ecx, 2
0x14000cce5  mov     edx, [rdx]
0x14000cce7  mov     ebx, 1
0x14000ccec  xor     eax, eax
0x14000ccee  mov     r8d, ecx
0x14000ccf1  or      r8d, edx
0x14000ccf4  cmp     r8d, edx
0x14000ccf7  mov     r9d, r8d
0x14000ccfa  setz    al
0x14000ccfd  or      r9d, ebx
0x14000cd00  cmp     r8d, edx
0x14000cd03  mov     [r10+10h], eax
0x14000cd07  mov     eax, edx
0x14000cd09  cmovz   r9d, r8d
0x14000cd0d  lock cmpxchg [rsi], r9d
0x14000cd12  jz      short loc_14000CD18
0x14000cd14  mov     edx, eax
0x14000cd16  jmp     short loc_14000CCEC
0x14000cd18  test    bl, r9b
0x14000cd1b  jz      short loc_14000CD21
0x14000cd1d  test    bl, dl
0x14000cd1f  jz      short loc_14000CD23
0x14000cd21  xor     ebx, ebx
0x14000cd23  mov     [r10], ebx
0x14000cd26  jmp     loc_14000CEB2
0x14000cd2b  mov     ecx, [rdx]
0x14000cd2d  xor     r9d, r9d
0x14000cd30  cmp     r11d, 5
0x14000cd34  mov     ebx, 1
0x14000cd39  setz    r9b
0x14000cd3d  mov     eax, ecx
0x14000cd3f  mov     dword ptr [r10+4], 0
0x14000cd47  or      eax, ebx
0x14000cd49  mov     edx, eax
0x14000cd4b  shr     edx, 16h
0x14000cd4e  and     edx, ebx
0x14000cd50  cmp     edx, r9d
0x14000cd53  jz      short loc_14000CD95
0x14000cd55  mov     r8d, eax
0x14000cd58  shr     r8d, 0Fh
0x14000cd5c  and     r8d, 7Fh
0x14000cd60  jbe     short loc_14000CD7A
0x14000cd62  cmp     r11d, ebx
0x14000cd65  mov     [r10+4], r8d
0x14000cd69  mov     edx, 5
0x14000cd6e  cmovnz  edx, ebx
0x14000cd71  and     eax, 0FFC07FFFh
0x14000cd76  mov     [r10+8], edx
0x14000cd7a  xor     r8d, r8d
0x14000cd7d  mov     edx, 400000h
0x14000cd82  cmp     r11d, 5
0x14000cd86  cmovz   r8d, edx
0x14000cd8a  mov     edx, eax
0x14000cd8c  btr     edx, 16h
0x14000cd90  mov     eax, r8d
0x14000cd93  or      eax, edx
0x14000cd95  mov     edx, eax
0x14000cd97  shr     edx, 0Fh
0x14000cd9a  and     edx, 7Fh
0x14000cd9d  lea     r8d, [rdx+1]
0x14000cda1  cmp     r8d, 7Fh
0x14000cda5  ja      short loc_14000CDAC
0x14000cda7  cmp     r8d, edx
0x14000cdaa  jnb     short loc_14000CDB7
0x14000cdac  mov     r8d, ebx
0x14000cdaf  mov     [r10+8], r11d
0x14000cdb3  mov     [r10+4], edx
0x14000cdb7  shl     r8d, 0Fh
0x14000cdbb  xor     r8d, eax
0x14000cdbe  and     r8d, 3F8000h
0x14000cdc5  xor     r8d, eax
0x14000cdc8  mov     eax, ecx
0x14000cdca  lock cmpxchg [rsi], r8d
0x14000cdcf  jz      short loc_14000CDD8
0x14000cdd1  mov     ecx, eax
0x14000cdd3  jmp     loc_14000CD3D
0x14000cdd8  not     ecx
0x14000cdda  and     ecx, ebx
0x14000cddc  mov     [r10], ecx
0x14000cddf  jmp     loc_14000CEAA
0x14000cde4  mov     edx, [rdx]
0x14000cde6  xor     ebp, ebp
0x14000cde8  lea     ecx, [rbp+4]
0x14000cdeb  cmp     r11d, ecx
0x14000cdee  lea     ebx, [rcx-3]
0x14000cdf1  setz    bpl
0x14000cdf5  mov     eax, edx
0x14000cdf7  mov     dword ptr [r10+4], 0
0x14000cdff  or      eax, ebx
0x14000ce01  mov     r8d, eax
0x14000ce04  shr     r8d, 0Eh
0x14000ce08  and     r8d, ebx
0x14000ce0b  cmp     r8d, ebp
0x14000ce0e  jz      short loc_14000CE57
0x14000ce10  mov     edi, eax
0x14000ce12  shr     edi, 5
0x14000ce15  and     edi, 1FFh
0x14000ce1b  jbe     short loc_14000CE39
0x14000ce1d  mov     r8d, r11d
0x14000ce20  mov     [r10+4], edi
0x14000ce24  neg     r8d
0x14000ce27  sbb     r9d, r9d
0x14000ce2a  not     r9d
0x14000ce2d  and     r9d, ecx
0x14000ce30  mov     [r10+8], r9d
0x14000ce34  and     eax, 0FFFFC01Fh
0x14000ce39  xor     r9d, r9d
0x14000ce3c  mov     r8d, 4000h
0x14000ce42  cmp     r11d, ecx
0x14000ce45  cmovz   r9d, r8d
0x14000ce49  mov     r8d, eax
0x14000ce4c  btr     r8d, 0Eh
0x14000ce51  mov     eax, r9d
0x14000ce54  or      eax, r8d
0x14000ce57  mov     r8d, eax
0x14000ce5a  shr     r8d, 5
0x14000ce5e  and     r8d, 1FFh
0x14000ce65  lea     r9d, [r8+1]
0x14000ce69  cmp     r9d, 1FFh
0x14000ce70  ja      short loc_14000CE77
0x14000ce72  cmp     r9d, r8d
0x14000ce75  jnb     short loc_14000CE82
0x14000ce77  mov     r9d, ebx
0x14000ce7a  mov     [r10+8], r11d
0x14000ce7e  mov     [r10+4], r8d
0x14000ce82  shl     r9d, 5
0x14000ce86  xor     r9d, eax
0x14000ce89  and     r9d, 3FE0h
0x14000ce90  xor     r9d, eax
0x14000ce93  mov     eax, edx
0x14000ce95  lock cmpxchg [rsi], r9d
0x14000ce9a  jz      short loc_14000CEA3
0x14000ce9c  mov     edx, eax
0x14000ce9e  jmp     loc_14000CDF5
0x14000cea3  not     edx
0x14000cea5  and     edx, ebx
0x14000cea7  mov     [r10], edx
0x14000ceaa  mov     dword ptr [r10+10h], 0
0x14000ceb2  mov     rax, r10
0x14000ceb5  pop     rdi
0x14000ceb6  pop     rsi
0x14000ceb7  pop     rbp
0x14000ceb8  pop     rbx
0x14000ceb9  retn
```
