# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140001978`
- end: `0x140001c4b`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001c54`

## callees

- `0x140001978`

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
0x140001978  push    rbx
0x14000197a  push    rbp
0x14000197b  push    rsi
0x14000197c  push    rdi
0x14000197d  xor     eax, eax
0x14000197f  xorps   xmm0, xmm0
0x140001982  mov     r10, rcx
0x140001985  mov     edi, r9d
0x140001988  mov     r11d, r8d
0x14000198b  mov     rsi, rdx
0x14000198e  movups  xmmword ptr [rcx], xmm0
0x140001991  mov     [rcx+10h], rax
0x140001995  mov     ecx, r8d
0x140001998  test    r8d, r8d
0x14000199b  jz      loc_140001B74
0x1400019a1  sub     ecx, 1
0x1400019a4  jz      loc_140001ABB
0x1400019aa  sub     ecx, 1
0x1400019ad  jz      loc_140001A42
0x1400019b3  sub     ecx, 1
0x1400019b6  jz      loc_140001A42
0x1400019bc  sub     ecx, 1
0x1400019bf  jz      loc_140001B74
0x1400019c5  sub     ecx, 1
0x1400019c8  jz      loc_140001ABB
0x1400019ce  sub     ecx, 1
0x1400019d1  jz      short loc_140001A42
0x1400019d3  cmp     ecx, 1
0x1400019d6  jz      short loc_140001A42
0x1400019d8  add     r8d, 0FFFFFEC0h
0x1400019df  lea     ebx, [rax+1]
0x1400019e2  cmp     r8d, 40h ; '@'
0x1400019e6  jge     short loc_140001A31
0x1400019e8  mov     eax, [rdx+4]
0x1400019eb  lea     ecx, [rbx+0Fh]
0x1400019ee  mov     r9d, r8d
0x1400019f1  shl     r9d, 5
0x1400019f5  test    cl, al
0x1400019f7  jz      short loc_140001A0A
0x1400019f9  mov     edx, eax
0x1400019fb  shr     edx, 5
0x1400019fe  and     edx, 3Fh
0x140001a01  cmp     edx, r8d
0x140001a04  jnz     short loc_140001A0A
0x140001a06  mov     edx, ebx
0x140001a08  jmp     short loc_140001A0C
0x140001a0a  xor     edx, edx
0x140001a0c  mov     [r10+10h], edx
0x140001a10  mov     edx, r9d
0x140001a13  xor     edx, eax
0x140001a15  and     edx, 7E0h
0x140001a1b  xor     edx, eax
0x140001a1d  or      edx, ecx
0x140001a1f  lock cmpxchg [rsi+4], edx
0x140001a24  jnz     short loc_1400019F5
0x140001a26  cmp     dword ptr [r10+10h], 0
0x140001a2b  jnz     loc_140001C42
0x140001a31  mov     [r10+8], r11d
0x140001a35  mov     [r10+4], ebx
0x140001a39  mov     [r10+0Ch], edi
0x140001a3d  jmp     loc_140001C42
0x140001a42  xor     ecx, ecx
0x140001a44  sub     r11d, 2
0x140001a48  jz      short loc_140001A70
0x140001a4a  sub     r11d, 1
0x140001a4e  jz      short loc_140001A69
0x140001a50  sub     r11d, 3
0x140001a54  jz      short loc_140001A62
0x140001a56  cmp     r11d, 1
0x140001a5a  jnz     short loc_140001A75
0x140001a5c  lea     ecx, [r11+0Fh]
0x140001a60  jmp     short loc_140001A75
0x140001a62  mov     ecx, 4
0x140001a67  jmp     short loc_140001A75
0x140001a69  mov     ecx, 8
0x140001a6e  jmp     short loc_140001A75
0x140001a70  mov     ecx, 2
0x140001a75  mov     edx, [rdx]
0x140001a77  mov     ebx, 1
0x140001a7c  xor     eax, eax
0x140001a7e  mov     r8d, ecx
0x140001a81  or      r8d, edx
0x140001a84  cmp     r8d, edx
0x140001a87  mov     r9d, r8d
0x140001a8a  setz    al
0x140001a8d  or      r9d, ebx
0x140001a90  cmp     r8d, edx
0x140001a93  mov     [r10+10h], eax
0x140001a97  mov     eax, edx
0x140001a99  cmovz   r9d, r8d
0x140001a9d  lock cmpxchg [rsi], r9d
0x140001aa2  jz      short loc_140001AA8
0x140001aa4  mov     edx, eax
0x140001aa6  jmp     short loc_140001A7C
0x140001aa8  test    bl, r9b
0x140001aab  jz      short loc_140001AB1
0x140001aad  test    bl, dl
0x140001aaf  jz      short loc_140001AB3
0x140001ab1  xor     ebx, ebx
0x140001ab3  mov     [r10], ebx
0x140001ab6  jmp     loc_140001C42
0x140001abb  mov     ecx, [rdx]
0x140001abd  xor     r9d, r9d
0x140001ac0  cmp     r11d, 5
0x140001ac4  mov     ebx, 1
0x140001ac9  setz    r9b
0x140001acd  mov     eax, ecx
0x140001acf  mov     dword ptr [r10+4], 0
0x140001ad7  or      eax, ebx
0x140001ad9  mov     edx, eax
0x140001adb  shr     edx, 16h
0x140001ade  and     edx, ebx
0x140001ae0  cmp     edx, r9d
0x140001ae3  jz      short loc_140001B25
0x140001ae5  mov     r8d, eax
0x140001ae8  shr     r8d, 0Fh
0x140001aec  and     r8d, 7Fh
0x140001af0  jbe     short loc_140001B0A
0x140001af2  cmp     r11d, ebx
0x140001af5  mov     [r10+4], r8d
0x140001af9  mov     edx, 5
0x140001afe  cmovnz  edx, ebx
0x140001b01  and     eax, 0FFC07FFFh
0x140001b06  mov     [r10+8], edx
0x140001b0a  xor     r8d, r8d
0x140001b0d  mov     edx, 400000h
0x140001b12  cmp     r11d, 5
0x140001b16  cmovz   r8d, edx
0x140001b1a  mov     edx, eax
0x140001b1c  btr     edx, 16h
0x140001b20  mov     eax, r8d
0x140001b23  or      eax, edx
0x140001b25  mov     edx, eax
0x140001b27  shr     edx, 0Fh
0x140001b2a  and     edx, 7Fh
0x140001b2d  lea     r8d, [rdx+1]
0x140001b31  cmp     r8d, 7Fh
0x140001b35  ja      short loc_140001B3C
0x140001b37  cmp     r8d, edx
0x140001b3a  jnb     short loc_140001B47
0x140001b3c  mov     r8d, ebx
0x140001b3f  mov     [r10+8], r11d
0x140001b43  mov     [r10+4], edx
0x140001b47  shl     r8d, 0Fh
0x140001b4b  xor     r8d, eax
0x140001b4e  and     r8d, 3F8000h
0x140001b55  xor     r8d, eax
0x140001b58  mov     eax, ecx
0x140001b5a  lock cmpxchg [rsi], r8d
0x140001b5f  jz      short loc_140001B68
0x140001b61  mov     ecx, eax
0x140001b63  jmp     loc_140001ACD
0x140001b68  not     ecx
0x140001b6a  and     ecx, ebx
0x140001b6c  mov     [r10], ecx
0x140001b6f  jmp     loc_140001C3A
0x140001b74  mov     edx, [rdx]
0x140001b76  xor     ebp, ebp
0x140001b78  lea     ecx, [rbp+4]
0x140001b7b  cmp     r11d, ecx
0x140001b7e  lea     ebx, [rcx-3]
0x140001b81  setz    bpl
0x140001b85  mov     eax, edx
0x140001b87  mov     dword ptr [r10+4], 0
0x140001b8f  or      eax, ebx
0x140001b91  mov     r8d, eax
0x140001b94  shr     r8d, 0Eh
0x140001b98  and     r8d, ebx
0x140001b9b  cmp     r8d, ebp
0x140001b9e  jz      short loc_140001BE7
0x140001ba0  mov     edi, eax
0x140001ba2  shr     edi, 5
0x140001ba5  and     edi, 1FFh
0x140001bab  jbe     short loc_140001BC9
0x140001bad  mov     r8d, r11d
0x140001bb0  mov     [r10+4], edi
0x140001bb4  neg     r8d
0x140001bb7  sbb     r9d, r9d
0x140001bba  not     r9d
0x140001bbd  and     r9d, ecx
0x140001bc0  mov     [r10+8], r9d
0x140001bc4  and     eax, 0FFFFC01Fh
0x140001bc9  xor     r9d, r9d
0x140001bcc  mov     r8d, 4000h
0x140001bd2  cmp     r11d, ecx
0x140001bd5  cmovz   r9d, r8d
0x140001bd9  mov     r8d, eax
0x140001bdc  btr     r8d, 0Eh
0x140001be1  mov     eax, r9d
0x140001be4  or      eax, r8d
0x140001be7  mov     r8d, eax
0x140001bea  shr     r8d, 5
0x140001bee  and     r8d, 1FFh
0x140001bf5  lea     r9d, [r8+1]
0x140001bf9  cmp     r9d, 1FFh
0x140001c00  ja      short loc_140001C07
0x140001c02  cmp     r9d, r8d
0x140001c05  jnb     short loc_140001C12
0x140001c07  mov     r9d, ebx
0x140001c0a  mov     [r10+8], r11d
0x140001c0e  mov     [r10+4], r8d
0x140001c12  shl     r9d, 5
0x140001c16  xor     r9d, eax
0x140001c19  and     r9d, 3FE0h
0x140001c20  xor     r9d, eax
0x140001c23  mov     eax, edx
0x140001c25  lock cmpxchg [rsi], r9d
0x140001c2a  jz      short loc_140001C33
0x140001c2c  mov     edx, eax
0x140001c2e  jmp     loc_140001B85
0x140001c33  not     edx
0x140001c35  and     edx, ebx
0x140001c37  mov     [r10], edx
0x140001c3a  mov     dword ptr [r10+10h], 0
0x140001c42  mov     rax, r10
0x140001c45  pop     rdi
0x140001c46  pop     rsi
0x140001c47  pop     rbp
0x140001c48  pop     rbx
0x140001c49  retn
```
