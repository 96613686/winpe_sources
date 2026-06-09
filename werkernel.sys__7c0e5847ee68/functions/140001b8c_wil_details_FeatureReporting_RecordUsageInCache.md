# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140001b8c`
- end: `0x140001e5f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001f88`

## callees

- `0x140001b8c`

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
0x140001b8c  push    rbx
0x140001b8e  push    rbp
0x140001b8f  push    rsi
0x140001b90  push    rdi
0x140001b91  xor     eax, eax
0x140001b93  xorps   xmm0, xmm0
0x140001b96  mov     r10, rcx
0x140001b99  mov     edi, r9d
0x140001b9c  mov     r11d, r8d
0x140001b9f  mov     rsi, rdx
0x140001ba2  movups  xmmword ptr [rcx], xmm0
0x140001ba5  mov     [rcx+10h], rax
0x140001ba9  mov     ecx, r8d
0x140001bac  test    r8d, r8d
0x140001baf  jz      loc_140001D88
0x140001bb5  sub     ecx, 1
0x140001bb8  jz      loc_140001CCF
0x140001bbe  sub     ecx, 1
0x140001bc1  jz      loc_140001C56
0x140001bc7  sub     ecx, 1
0x140001bca  jz      loc_140001C56
0x140001bd0  sub     ecx, 1
0x140001bd3  jz      loc_140001D88
0x140001bd9  sub     ecx, 1
0x140001bdc  jz      loc_140001CCF
0x140001be2  sub     ecx, 1
0x140001be5  jz      short loc_140001C56
0x140001be7  cmp     ecx, 1
0x140001bea  jz      short loc_140001C56
0x140001bec  add     r8d, 0FFFFFEC0h
0x140001bf3  lea     ebx, [rax+1]
0x140001bf6  cmp     r8d, 40h ; '@'
0x140001bfa  jge     short loc_140001C45
0x140001bfc  mov     eax, [rdx+4]
0x140001bff  lea     ecx, [rbx+0Fh]
0x140001c02  mov     r9d, r8d
0x140001c05  shl     r9d, 5
0x140001c09  test    cl, al
0x140001c0b  jz      short loc_140001C1E
0x140001c0d  mov     edx, eax
0x140001c0f  shr     edx, 5
0x140001c12  and     edx, 3Fh
0x140001c15  cmp     edx, r8d
0x140001c18  jnz     short loc_140001C1E
0x140001c1a  mov     edx, ebx
0x140001c1c  jmp     short loc_140001C20
0x140001c1e  xor     edx, edx
0x140001c20  mov     [r10+10h], edx
0x140001c24  mov     edx, r9d
0x140001c27  xor     edx, eax
0x140001c29  and     edx, 7E0h
0x140001c2f  xor     edx, eax
0x140001c31  or      edx, ecx
0x140001c33  lock cmpxchg [rsi+4], edx
0x140001c38  jnz     short loc_140001C09
0x140001c3a  cmp     dword ptr [r10+10h], 0
0x140001c3f  jnz     loc_140001E56
0x140001c45  mov     [r10+8], r11d
0x140001c49  mov     [r10+4], ebx
0x140001c4d  mov     [r10+0Ch], edi
0x140001c51  jmp     loc_140001E56
0x140001c56  xor     ecx, ecx
0x140001c58  sub     r11d, 2
0x140001c5c  jz      short loc_140001C84
0x140001c5e  sub     r11d, 1
0x140001c62  jz      short loc_140001C7D
0x140001c64  sub     r11d, 3
0x140001c68  jz      short loc_140001C76
0x140001c6a  cmp     r11d, 1
0x140001c6e  jnz     short loc_140001C89
0x140001c70  lea     ecx, [r11+0Fh]
0x140001c74  jmp     short loc_140001C89
0x140001c76  mov     ecx, 4
0x140001c7b  jmp     short loc_140001C89
0x140001c7d  mov     ecx, 8
0x140001c82  jmp     short loc_140001C89
0x140001c84  mov     ecx, 2
0x140001c89  mov     edx, [rdx]
0x140001c8b  mov     ebx, 1
0x140001c90  xor     eax, eax
0x140001c92  mov     r8d, ecx
0x140001c95  or      r8d, edx
0x140001c98  cmp     r8d, edx
0x140001c9b  mov     r9d, r8d
0x140001c9e  setz    al
0x140001ca1  or      r9d, ebx
0x140001ca4  cmp     r8d, edx
0x140001ca7  mov     [r10+10h], eax
0x140001cab  mov     eax, edx
0x140001cad  cmovz   r9d, r8d
0x140001cb1  lock cmpxchg [rsi], r9d
0x140001cb6  jz      short loc_140001CBC
0x140001cb8  mov     edx, eax
0x140001cba  jmp     short loc_140001C90
0x140001cbc  test    bl, r9b
0x140001cbf  jz      short loc_140001CC5
0x140001cc1  test    bl, dl
0x140001cc3  jz      short loc_140001CC7
0x140001cc5  xor     ebx, ebx
0x140001cc7  mov     [r10], ebx
0x140001cca  jmp     loc_140001E56
0x140001ccf  mov     ecx, [rdx]
0x140001cd1  xor     r9d, r9d
0x140001cd4  cmp     r11d, 5
0x140001cd8  mov     ebx, 1
0x140001cdd  setz    r9b
0x140001ce1  mov     eax, ecx
0x140001ce3  mov     dword ptr [r10+4], 0
0x140001ceb  or      eax, ebx
0x140001ced  mov     edx, eax
0x140001cef  shr     edx, 16h
0x140001cf2  and     edx, ebx
0x140001cf4  cmp     edx, r9d
0x140001cf7  jz      short loc_140001D39
0x140001cf9  mov     r8d, eax
0x140001cfc  shr     r8d, 0Fh
0x140001d00  and     r8d, 7Fh
0x140001d04  jbe     short loc_140001D1E
0x140001d06  cmp     r11d, ebx
0x140001d09  mov     [r10+4], r8d
0x140001d0d  mov     edx, 5
0x140001d12  cmovnz  edx, ebx
0x140001d15  and     eax, 0FFC07FFFh
0x140001d1a  mov     [r10+8], edx
0x140001d1e  xor     r8d, r8d
0x140001d21  mov     edx, 400000h
0x140001d26  cmp     r11d, 5
0x140001d2a  cmovz   r8d, edx
0x140001d2e  mov     edx, eax
0x140001d30  btr     edx, 16h
0x140001d34  mov     eax, r8d
0x140001d37  or      eax, edx
0x140001d39  mov     edx, eax
0x140001d3b  shr     edx, 0Fh
0x140001d3e  and     edx, 7Fh
0x140001d41  lea     r8d, [rdx+1]
0x140001d45  cmp     r8d, 7Fh
0x140001d49  ja      short loc_140001D50
0x140001d4b  cmp     r8d, edx
0x140001d4e  jnb     short loc_140001D5B
0x140001d50  mov     r8d, ebx
0x140001d53  mov     [r10+8], r11d
0x140001d57  mov     [r10+4], edx
0x140001d5b  shl     r8d, 0Fh
0x140001d5f  xor     r8d, eax
0x140001d62  and     r8d, 3F8000h
0x140001d69  xor     r8d, eax
0x140001d6c  mov     eax, ecx
0x140001d6e  lock cmpxchg [rsi], r8d
0x140001d73  jz      short loc_140001D7C
0x140001d75  mov     ecx, eax
0x140001d77  jmp     loc_140001CE1
0x140001d7c  not     ecx
0x140001d7e  and     ecx, ebx
0x140001d80  mov     [r10], ecx
0x140001d83  jmp     loc_140001E4E
0x140001d88  mov     edx, [rdx]
0x140001d8a  xor     ebp, ebp
0x140001d8c  lea     ecx, [rbp+4]
0x140001d8f  cmp     r11d, ecx
0x140001d92  lea     ebx, [rcx-3]
0x140001d95  setz    bpl
0x140001d99  mov     eax, edx
0x140001d9b  mov     dword ptr [r10+4], 0
0x140001da3  or      eax, ebx
0x140001da5  mov     r8d, eax
0x140001da8  shr     r8d, 0Eh
0x140001dac  and     r8d, ebx
0x140001daf  cmp     r8d, ebp
0x140001db2  jz      short loc_140001DFB
0x140001db4  mov     edi, eax
0x140001db6  shr     edi, 5
0x140001db9  and     edi, 1FFh
0x140001dbf  jbe     short loc_140001DDD
0x140001dc1  mov     r8d, r11d
0x140001dc4  mov     [r10+4], edi
0x140001dc8  neg     r8d
0x140001dcb  sbb     r9d, r9d
0x140001dce  not     r9d
0x140001dd1  and     r9d, ecx
0x140001dd4  mov     [r10+8], r9d
0x140001dd8  and     eax, 0FFFFC01Fh
0x140001ddd  xor     r9d, r9d
0x140001de0  mov     r8d, 4000h
0x140001de6  cmp     r11d, ecx
0x140001de9  cmovz   r9d, r8d
0x140001ded  mov     r8d, eax
0x140001df0  btr     r8d, 0Eh
0x140001df5  mov     eax, r9d
0x140001df8  or      eax, r8d
0x140001dfb  mov     r8d, eax
0x140001dfe  shr     r8d, 5
0x140001e02  and     r8d, 1FFh
0x140001e09  lea     r9d, [r8+1]
0x140001e0d  cmp     r9d, 1FFh
0x140001e14  ja      short loc_140001E1B
0x140001e16  cmp     r9d, r8d
0x140001e19  jnb     short loc_140001E26
0x140001e1b  mov     r9d, ebx
0x140001e1e  mov     [r10+8], r11d
0x140001e22  mov     [r10+4], r8d
0x140001e26  shl     r9d, 5
0x140001e2a  xor     r9d, eax
0x140001e2d  and     r9d, 3FE0h
0x140001e34  xor     r9d, eax
0x140001e37  mov     eax, edx
0x140001e39  lock cmpxchg [rsi], r9d
0x140001e3e  jz      short loc_140001E47
0x140001e40  mov     edx, eax
0x140001e42  jmp     loc_140001D99
0x140001e47  not     edx
0x140001e49  and     edx, ebx
0x140001e4b  mov     [r10], edx
0x140001e4e  mov     dword ptr [r10+10h], 0
0x140001e56  mov     rax, r10
0x140001e59  pop     rdi
0x140001e5a  pop     rsi
0x140001e5b  pop     rbp
0x140001e5c  pop     rbx
0x140001e5d  retn
```
