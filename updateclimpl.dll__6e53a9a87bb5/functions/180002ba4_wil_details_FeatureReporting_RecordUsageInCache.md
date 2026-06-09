# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180002ba4`
- end: `0x180002e76`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003248`

## callees

- `0x180002ba4`

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
0x180002ba4  mov     rax, rsp
0x180002ba7  mov     [rax+8], rbx
0x180002bab  mov     [rax+10h], rbp
0x180002baf  mov     [rax+18h], rsi
0x180002bb3  mov     [rax+20h], rdi
0x180002bb7  xor     eax, eax
0x180002bb9  xorps   xmm0, xmm0
0x180002bbc  mov     r10, rcx
0x180002bbf  mov     r11d, r8d
0x180002bc2  mov     rsi, rdx
0x180002bc5  movups  xmmword ptr [rcx], xmm0
0x180002bc8  mov     [rcx+10h], rax
0x180002bcc  mov     ecx, r8d
0x180002bcf  test    r8d, r8d
0x180002bd2  jz      loc_180002DA0
0x180002bd8  sub     ecx, 1
0x180002bdb  jz      loc_180002CF6
0x180002be1  sub     ecx, 1
0x180002be4  jz      loc_180002C7D
0x180002bea  sub     ecx, 1
0x180002bed  jz      loc_180002C7D
0x180002bf3  sub     ecx, 1
0x180002bf6  jz      loc_180002DA0
0x180002bfc  sub     ecx, 1
0x180002bff  jz      loc_180002CF6
0x180002c05  sub     ecx, 1
0x180002c08  jz      short loc_180002C7D
0x180002c0a  cmp     ecx, 1
0x180002c0d  jz      short loc_180002C7D
0x180002c0f  add     r8d, 0FFFFFEC0h
0x180002c16  lea     ebx, [rax+1]
0x180002c19  cmp     r8d, 40h ; '@'
0x180002c1d  jge     short loc_180002C68
0x180002c1f  mov     eax, [rdx+4]
0x180002c22  lea     ecx, [rbx+0Fh]
0x180002c25  mov     r9d, r8d
0x180002c28  shl     r9d, 5
0x180002c2c  test    cl, al
0x180002c2e  jz      short loc_180002C41
0x180002c30  mov     edx, eax
0x180002c32  shr     edx, 5
0x180002c35  and     edx, 3Fh
0x180002c38  cmp     edx, r8d
0x180002c3b  jnz     short loc_180002C41
0x180002c3d  mov     edx, ebx
0x180002c3f  jmp     short loc_180002C43
0x180002c41  xor     edx, edx
0x180002c43  mov     [r10+10h], edx
0x180002c47  mov     edx, r9d
0x180002c4a  xor     edx, eax
0x180002c4c  and     edx, 7E0h
0x180002c52  xor     edx, eax
0x180002c54  or      edx, ecx
0x180002c56  lock cmpxchg [rsi+4], edx
0x180002c5b  jnz     short loc_180002C2C
0x180002c5d  cmp     dword ptr [r10+10h], 0
0x180002c62  jnz     loc_180002E5E
0x180002c68  mov     [r10+8], r11d
0x180002c6c  mov     [r10+4], ebx
0x180002c70  mov     dword ptr [r10+0Ch], 0
0x180002c78  jmp     loc_180002E5E
0x180002c7d  xor     ecx, ecx
0x180002c7f  sub     r11d, 2
0x180002c83  jz      short loc_180002CAB
0x180002c85  sub     r11d, 1
0x180002c89  jz      short loc_180002CA4
0x180002c8b  sub     r11d, 3
0x180002c8f  jz      short loc_180002C9D
0x180002c91  cmp     r11d, 1
0x180002c95  jnz     short loc_180002CB0
0x180002c97  lea     ecx, [r11+0Fh]
0x180002c9b  jmp     short loc_180002CB0
0x180002c9d  mov     ecx, 4
0x180002ca2  jmp     short loc_180002CB0
0x180002ca4  mov     ecx, 8
0x180002ca9  jmp     short loc_180002CB0
0x180002cab  mov     ecx, 2
0x180002cb0  mov     edx, [rdx]
0x180002cb2  mov     ebx, 1
0x180002cb7  xor     eax, eax
0x180002cb9  mov     r8d, ecx
0x180002cbc  or      r8d, edx
0x180002cbf  cmp     r8d, edx
0x180002cc2  mov     r9d, r8d
0x180002cc5  setz    al
0x180002cc8  or      r9d, ebx
0x180002ccb  cmp     r8d, edx
0x180002cce  mov     [r10+10h], eax
0x180002cd2  mov     eax, edx
0x180002cd4  cmovz   r9d, r8d
0x180002cd8  lock cmpxchg [rsi], r9d
0x180002cdd  jz      short loc_180002CE3
0x180002cdf  mov     edx, eax
0x180002ce1  jmp     short loc_180002CB7
0x180002ce3  test    bl, r9b
0x180002ce6  jz      short loc_180002CEC
0x180002ce8  test    bl, dl
0x180002cea  jz      short loc_180002CEE
0x180002cec  xor     ebx, ebx
0x180002cee  mov     [r10], ebx
0x180002cf1  jmp     loc_180002E5E
0x180002cf6  mov     ecx, [rdx]
0x180002cf8  xor     r9d, r9d
0x180002cfb  lea     edi, [r9+5]
0x180002cff  cmp     r11d, edi
0x180002d02  lea     ebx, [rdi-4]
0x180002d05  setz    r9b
0x180002d09  mov     eax, ecx
0x180002d0b  mov     dword ptr [r10+4], 0
0x180002d13  or      eax, ebx
0x180002d15  mov     edx, eax
0x180002d17  shr     edx, 16h
0x180002d1a  and     edx, ebx
0x180002d1c  cmp     edx, r9d
0x180002d1f  jz      short loc_180002D55
0x180002d21  mov     r8d, eax
0x180002d24  shr     r8d, 0Fh
0x180002d28  and     r8d, 7Fh
0x180002d2c  jbe     short loc_180002D43
0x180002d2e  cmp     r11d, ebx
0x180002d31  mov     [r10+4], r8d
0x180002d35  mov     edx, ebx
0x180002d37  cmovz   edx, edi
0x180002d3a  and     eax, 0FFC07FFFh
0x180002d3f  mov     [r10+8], edx
0x180002d43  mov     edx, eax
0x180002d45  mov     r8d, r9d
0x180002d48  shl     r8d, 16h
0x180002d4c  btr     edx, 16h
0x180002d50  mov     eax, r8d
0x180002d53  or      eax, edx
0x180002d55  mov     r8d, eax
0x180002d58  shr     r8d, 0Fh
0x180002d5c  and     r8d, 7Fh
0x180002d60  lea     edx, [r8+1]
0x180002d64  cmp     edx, 7Fh
0x180002d67  ja      short loc_180002D6E
0x180002d69  cmp     edx, r8d
0x180002d6c  jnb     short loc_180002D78
0x180002d6e  mov     edx, ebx
0x180002d70  mov     [r10+8], r11d
0x180002d74  mov     [r10+4], r8d
0x180002d78  shl     edx, 0Fh
0x180002d7b  xor     edx, eax
0x180002d7d  and     edx, 3F8000h
0x180002d83  xor     edx, eax
0x180002d85  mov     eax, ecx
0x180002d87  lock cmpxchg [rsi], edx
0x180002d8b  jz      short loc_180002D94
0x180002d8d  mov     ecx, eax
0x180002d8f  jmp     loc_180002D09
0x180002d94  not     ecx
0x180002d96  and     ecx, ebx
0x180002d98  mov     [r10], ecx
0x180002d9b  jmp     loc_180002E56
0x180002da0  mov     edx, [rdx]
0x180002da2  xor     ebp, ebp
0x180002da4  lea     ecx, [rbp+4]
0x180002da7  cmp     r11d, ecx
0x180002daa  lea     ebx, [rcx-3]
0x180002dad  setz    bpl
0x180002db1  mov     eax, edx
0x180002db3  mov     dword ptr [r10+4], 0
0x180002dbb  or      eax, ebx
0x180002dbd  mov     r8d, eax
0x180002dc0  shr     r8d, 0Eh
0x180002dc4  and     r8d, ebx
0x180002dc7  cmp     r8d, ebp
0x180002dca  jz      short loc_180002E03
0x180002dcc  mov     edi, eax
0x180002dce  shr     edi, 5
0x180002dd1  and     edi, 1FFh
0x180002dd7  jbe     short loc_180002DF5
0x180002dd9  mov     r8d, r11d
0x180002ddc  mov     [r10+4], edi
0x180002de0  neg     r8d
0x180002de3  sbb     r9d, r9d
0x180002de6  not     r9d
0x180002de9  and     r9d, ecx
0x180002dec  mov     [r10+8], r9d
0x180002df0  and     eax, 0FFFFC01Fh
0x180002df5  mov     r8d, ebp
0x180002df8  btr     eax, 0Eh
0x180002dfc  shl     r8d, 0Eh
0x180002e00  or      eax, r8d
0x180002e03  mov     r9d, eax
0x180002e06  shr     r9d, 5
0x180002e0a  and     r9d, 1FFh
0x180002e11  lea     r8d, [r9+1]
0x180002e15  cmp     r8d, 1FFh
0x180002e1c  ja      short loc_180002E23
0x180002e1e  cmp     r8d, r9d
0x180002e21  jnb     short loc_180002E2E
0x180002e23  mov     r8d, ebx
0x180002e26  mov     [r10+8], r11d
0x180002e2a  mov     [r10+4], r9d
0x180002e2e  shl     r8d, 5
0x180002e32  xor     r8d, eax
0x180002e35  and     r8d, 3FE0h
0x180002e3c  xor     r8d, eax
0x180002e3f  mov     eax, edx
0x180002e41  lock cmpxchg [rsi], r8d
0x180002e46  jz      short loc_180002E4F
0x180002e48  mov     edx, eax
0x180002e4a  jmp     loc_180002DB1
0x180002e4f  not     edx
0x180002e51  and     edx, ebx
0x180002e53  mov     [r10], edx
0x180002e56  mov     dword ptr [r10+10h], 0
0x180002e5e  mov     rbx, [rsp+arg_0]
0x180002e63  mov     rax, r10
0x180002e66  mov     rbp, [rsp+arg_8]
0x180002e6b  mov     rsi, [rsp+arg_10]
0x180002e70  mov     rdi, [rsp+arg_18]
0x180002e75  retn
```
