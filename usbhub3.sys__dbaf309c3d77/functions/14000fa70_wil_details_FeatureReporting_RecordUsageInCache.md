# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000fa70`
- end: `0x14000fd43`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fe78`

## callees

- `0x14000fa70`

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
0x14000fa70  push    rbx
0x14000fa72  push    rbp
0x14000fa73  push    rsi
0x14000fa74  push    rdi
0x14000fa75  xor     eax, eax
0x14000fa77  xorps   xmm0, xmm0
0x14000fa7a  mov     r10, rcx
0x14000fa7d  mov     edi, r9d
0x14000fa80  mov     r11d, r8d
0x14000fa83  mov     rsi, rdx
0x14000fa86  movups  xmmword ptr [rcx], xmm0
0x14000fa89  mov     [rcx+10h], rax
0x14000fa8d  mov     ecx, r8d
0x14000fa90  test    r8d, r8d
0x14000fa93  jz      loc_14000FC6C
0x14000fa99  sub     ecx, 1
0x14000fa9c  jz      loc_14000FBB3
0x14000faa2  sub     ecx, 1
0x14000faa5  jz      loc_14000FB3A
0x14000faab  sub     ecx, 1
0x14000faae  jz      loc_14000FB3A
0x14000fab4  sub     ecx, 1
0x14000fab7  jz      loc_14000FC6C
0x14000fabd  sub     ecx, 1
0x14000fac0  jz      loc_14000FBB3
0x14000fac6  sub     ecx, 1
0x14000fac9  jz      short loc_14000FB3A
0x14000facb  cmp     ecx, 1
0x14000face  jz      short loc_14000FB3A
0x14000fad0  add     r8d, 0FFFFFEC0h
0x14000fad7  lea     ebx, [rax+1]
0x14000fada  cmp     r8d, 40h ; '@'
0x14000fade  jge     short loc_14000FB29
0x14000fae0  mov     eax, [rdx+4]
0x14000fae3  lea     ecx, [rbx+0Fh]
0x14000fae6  mov     r9d, r8d
0x14000fae9  shl     r9d, 5
0x14000faed  test    cl, al
0x14000faef  jz      short loc_14000FB02
0x14000faf1  mov     edx, eax
0x14000faf3  shr     edx, 5
0x14000faf6  and     edx, 3Fh
0x14000faf9  cmp     edx, r8d
0x14000fafc  jnz     short loc_14000FB02
0x14000fafe  mov     edx, ebx
0x14000fb00  jmp     short loc_14000FB04
0x14000fb02  xor     edx, edx
0x14000fb04  mov     [r10+10h], edx
0x14000fb08  mov     edx, r9d
0x14000fb0b  xor     edx, eax
0x14000fb0d  and     edx, 7E0h
0x14000fb13  xor     edx, eax
0x14000fb15  or      edx, ecx
0x14000fb17  lock cmpxchg [rsi+4], edx
0x14000fb1c  jnz     short loc_14000FAED
0x14000fb1e  cmp     dword ptr [r10+10h], 0
0x14000fb23  jnz     loc_14000FD3A
0x14000fb29  mov     [r10+8], r11d
0x14000fb2d  mov     [r10+4], ebx
0x14000fb31  mov     [r10+0Ch], edi
0x14000fb35  jmp     loc_14000FD3A
0x14000fb3a  xor     ecx, ecx
0x14000fb3c  sub     r11d, 2
0x14000fb40  jz      short loc_14000FB68
0x14000fb42  sub     r11d, 1
0x14000fb46  jz      short loc_14000FB61
0x14000fb48  sub     r11d, 3
0x14000fb4c  jz      short loc_14000FB5A
0x14000fb4e  cmp     r11d, 1
0x14000fb52  jnz     short loc_14000FB6D
0x14000fb54  lea     ecx, [r11+0Fh]
0x14000fb58  jmp     short loc_14000FB6D
0x14000fb5a  mov     ecx, 4
0x14000fb5f  jmp     short loc_14000FB6D
0x14000fb61  mov     ecx, 8
0x14000fb66  jmp     short loc_14000FB6D
0x14000fb68  mov     ecx, 2
0x14000fb6d  mov     edx, [rdx]
0x14000fb6f  mov     ebx, 1
0x14000fb74  xor     eax, eax
0x14000fb76  mov     r8d, ecx
0x14000fb79  or      r8d, edx
0x14000fb7c  cmp     r8d, edx
0x14000fb7f  mov     r9d, r8d
0x14000fb82  setz    al
0x14000fb85  or      r9d, ebx
0x14000fb88  cmp     r8d, edx
0x14000fb8b  mov     [r10+10h], eax
0x14000fb8f  mov     eax, edx
0x14000fb91  cmovz   r9d, r8d
0x14000fb95  lock cmpxchg [rsi], r9d
0x14000fb9a  jz      short loc_14000FBA0
0x14000fb9c  mov     edx, eax
0x14000fb9e  jmp     short loc_14000FB74
0x14000fba0  test    bl, r9b
0x14000fba3  jz      short loc_14000FBA9
0x14000fba5  test    bl, dl
0x14000fba7  jz      short loc_14000FBAB
0x14000fba9  xor     ebx, ebx
0x14000fbab  mov     [r10], ebx
0x14000fbae  jmp     loc_14000FD3A
0x14000fbb3  mov     ecx, [rdx]
0x14000fbb5  xor     r9d, r9d
0x14000fbb8  cmp     r11d, 5
0x14000fbbc  mov     ebx, 1
0x14000fbc1  setz    r9b
0x14000fbc5  mov     eax, ecx
0x14000fbc7  mov     dword ptr [r10+4], 0
0x14000fbcf  or      eax, ebx
0x14000fbd1  mov     edx, eax
0x14000fbd3  shr     edx, 16h
0x14000fbd6  and     edx, ebx
0x14000fbd8  cmp     edx, r9d
0x14000fbdb  jz      short loc_14000FC1D
0x14000fbdd  mov     r8d, eax
0x14000fbe0  shr     r8d, 0Fh
0x14000fbe4  and     r8d, 7Fh
0x14000fbe8  jbe     short loc_14000FC02
0x14000fbea  cmp     r11d, ebx
0x14000fbed  mov     [r10+4], r8d
0x14000fbf1  mov     edx, 5
0x14000fbf6  cmovnz  edx, ebx
0x14000fbf9  and     eax, 0FFC07FFFh
0x14000fbfe  mov     [r10+8], edx
0x14000fc02  xor     r8d, r8d
0x14000fc05  mov     edx, 400000h
0x14000fc0a  cmp     r11d, 5
0x14000fc0e  cmovz   r8d, edx
0x14000fc12  mov     edx, eax
0x14000fc14  btr     edx, 16h
0x14000fc18  mov     eax, r8d
0x14000fc1b  or      eax, edx
0x14000fc1d  mov     edx, eax
0x14000fc1f  shr     edx, 0Fh
0x14000fc22  and     edx, 7Fh
0x14000fc25  lea     r8d, [rdx+1]
0x14000fc29  cmp     r8d, 7Fh
0x14000fc2d  ja      short loc_14000FC34
0x14000fc2f  cmp     r8d, edx
0x14000fc32  jnb     short loc_14000FC3F
0x14000fc34  mov     r8d, ebx
0x14000fc37  mov     [r10+8], r11d
0x14000fc3b  mov     [r10+4], edx
0x14000fc3f  shl     r8d, 0Fh
0x14000fc43  xor     r8d, eax
0x14000fc46  and     r8d, 3F8000h
0x14000fc4d  xor     r8d, eax
0x14000fc50  mov     eax, ecx
0x14000fc52  lock cmpxchg [rsi], r8d
0x14000fc57  jz      short loc_14000FC60
0x14000fc59  mov     ecx, eax
0x14000fc5b  jmp     loc_14000FBC5
0x14000fc60  not     ecx
0x14000fc62  and     ecx, ebx
0x14000fc64  mov     [r10], ecx
0x14000fc67  jmp     loc_14000FD32
0x14000fc6c  mov     edx, [rdx]
0x14000fc6e  xor     ebp, ebp
0x14000fc70  lea     ecx, [rbp+4]
0x14000fc73  cmp     r11d, ecx
0x14000fc76  lea     ebx, [rcx-3]
0x14000fc79  setz    bpl
0x14000fc7d  mov     eax, edx
0x14000fc7f  mov     dword ptr [r10+4], 0
0x14000fc87  or      eax, ebx
0x14000fc89  mov     r8d, eax
0x14000fc8c  shr     r8d, 0Eh
0x14000fc90  and     r8d, ebx
0x14000fc93  cmp     r8d, ebp
0x14000fc96  jz      short loc_14000FCDF
0x14000fc98  mov     edi, eax
0x14000fc9a  shr     edi, 5
0x14000fc9d  and     edi, 1FFh
0x14000fca3  jbe     short loc_14000FCC1
0x14000fca5  mov     r8d, r11d
0x14000fca8  mov     [r10+4], edi
0x14000fcac  neg     r8d
0x14000fcaf  sbb     r9d, r9d
0x14000fcb2  not     r9d
0x14000fcb5  and     r9d, ecx
0x14000fcb8  mov     [r10+8], r9d
0x14000fcbc  and     eax, 0FFFFC01Fh
0x14000fcc1  xor     r9d, r9d
0x14000fcc4  mov     r8d, 4000h
0x14000fcca  cmp     r11d, ecx
0x14000fccd  cmovz   r9d, r8d
0x14000fcd1  mov     r8d, eax
0x14000fcd4  btr     r8d, 0Eh
0x14000fcd9  mov     eax, r9d
0x14000fcdc  or      eax, r8d
0x14000fcdf  mov     r8d, eax
0x14000fce2  shr     r8d, 5
0x14000fce6  and     r8d, 1FFh
0x14000fced  lea     r9d, [r8+1]
0x14000fcf1  cmp     r9d, 1FFh
0x14000fcf8  ja      short loc_14000FCFF
0x14000fcfa  cmp     r9d, r8d
0x14000fcfd  jnb     short loc_14000FD0A
0x14000fcff  mov     r9d, ebx
0x14000fd02  mov     [r10+8], r11d
0x14000fd06  mov     [r10+4], r8d
0x14000fd0a  shl     r9d, 5
0x14000fd0e  xor     r9d, eax
0x14000fd11  and     r9d, 3FE0h
0x14000fd18  xor     r9d, eax
0x14000fd1b  mov     eax, edx
0x14000fd1d  lock cmpxchg [rsi], r9d
0x14000fd22  jz      short loc_14000FD2B
0x14000fd24  mov     edx, eax
0x14000fd26  jmp     loc_14000FC7D
0x14000fd2b  not     edx
0x14000fd2d  and     edx, ebx
0x14000fd2f  mov     [r10], edx
0x14000fd32  mov     dword ptr [r10+10h], 0
0x14000fd3a  mov     rax, r10
0x14000fd3d  pop     rdi
0x14000fd3e  pop     rsi
0x14000fd3f  pop     rbp
0x14000fd40  pop     rbx
0x14000fd41  retn
```
