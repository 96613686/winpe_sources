# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000bc50`
- end: `0x18000bf2a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a1b8`

## callees

- `0x18000bc50`

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
0x18000bc50  push    rbx
0x18000bc52  push    rbp
0x18000bc53  push    rsi
0x18000bc54  push    rdi
0x18000bc55  xor     eax, eax
0x18000bc57  xorps   xmm0, xmm0
0x18000bc5a  mov     r11d, r8d
0x18000bc5d  mov     rsi, rdx
0x18000bc60  mov     r10, rcx
0x18000bc63  mov     r9d, r8d
0x18000bc66  movups  xmmword ptr [rcx], xmm0
0x18000bc69  mov     [rcx+10h], rax
0x18000bc6d  test    r8d, r8d
0x18000bc70  jz      loc_18000BE54
0x18000bc76  sub     r9d, 1
0x18000bc7a  jz      loc_18000BD9B
0x18000bc80  sub     r9d, 1
0x18000bc84  jz      loc_18000BD22
0x18000bc8a  sub     r9d, 1
0x18000bc8e  jz      loc_18000BD22
0x18000bc94  sub     r9d, 1
0x18000bc98  jz      loc_18000BE54
0x18000bc9e  sub     r9d, 1
0x18000bca2  jz      loc_18000BD9B
0x18000bca8  sub     r9d, 1
0x18000bcac  jz      short loc_18000BD22
0x18000bcae  cmp     r9d, 1
0x18000bcb2  jz      short loc_18000BD22
0x18000bcb4  add     r8d, 0FFFFFEC0h
0x18000bcbb  lea     ebx, [rax+1]
0x18000bcbe  cmp     r8d, 40h ; '@'
0x18000bcc2  jge     short loc_18000BD0D
0x18000bcc4  mov     eax, [rdx+4]
0x18000bcc7  lea     ecx, [rbx+0Fh]
0x18000bcca  mov     r9d, r8d
0x18000bccd  shl     r9d, 5
0x18000bcd1  test    cl, al
0x18000bcd3  jz      short loc_18000BCE6
0x18000bcd5  mov     edx, eax
0x18000bcd7  shr     edx, 5
0x18000bcda  and     edx, 3Fh
0x18000bcdd  cmp     edx, r8d
0x18000bce0  jnz     short loc_18000BCE6
0x18000bce2  mov     edx, ebx
0x18000bce4  jmp     short loc_18000BCE8
0x18000bce6  xor     edx, edx
0x18000bce8  mov     [r10+10h], edx
0x18000bcec  mov     edx, r9d
0x18000bcef  xor     edx, eax
0x18000bcf1  and     edx, 7E0h
0x18000bcf7  xor     edx, eax
0x18000bcf9  or      edx, ecx
0x18000bcfb  lock cmpxchg [rsi+4], edx
0x18000bd00  jnz     short loc_18000BCD1
0x18000bd02  cmp     dword ptr [r10+10h], 0
0x18000bd07  jnz     loc_18000BF22
0x18000bd0d  mov     [r10+8], r11d
0x18000bd11  mov     [r10+4], ebx
0x18000bd15  mov     dword ptr [r10+0Ch], 0
0x18000bd1d  jmp     loc_18000BF22
0x18000bd22  xor     ecx, ecx
0x18000bd24  sub     r11d, 2
0x18000bd28  jz      short loc_18000BD50
0x18000bd2a  sub     r11d, 1
0x18000bd2e  jz      short loc_18000BD49
0x18000bd30  sub     r11d, 3
0x18000bd34  jz      short loc_18000BD42
0x18000bd36  cmp     r11d, 1
0x18000bd3a  jnz     short loc_18000BD55
0x18000bd3c  lea     ecx, [r11+0Fh]
0x18000bd40  jmp     short loc_18000BD55
0x18000bd42  mov     ecx, 4
0x18000bd47  jmp     short loc_18000BD55
0x18000bd49  mov     ecx, 8
0x18000bd4e  jmp     short loc_18000BD55
0x18000bd50  mov     ecx, 2
0x18000bd55  mov     edx, [rdx]
0x18000bd57  mov     ebx, 1
0x18000bd5c  xor     eax, eax
0x18000bd5e  mov     r8d, ecx
0x18000bd61  or      r8d, edx
0x18000bd64  cmp     r8d, edx
0x18000bd67  mov     r9d, r8d
0x18000bd6a  setz    al
0x18000bd6d  or      r9d, ebx
0x18000bd70  cmp     r8d, edx
0x18000bd73  mov     [r10+10h], eax
0x18000bd77  mov     eax, edx
0x18000bd79  cmovz   r9d, r8d
0x18000bd7d  lock cmpxchg [rsi], r9d
0x18000bd82  jz      short loc_18000BD88
0x18000bd84  mov     edx, eax
0x18000bd86  jmp     short loc_18000BD5C
0x18000bd88  test    bl, r9b
0x18000bd8b  jz      short loc_18000BD91
0x18000bd8d  test    bl, dl
0x18000bd8f  jz      short loc_18000BD93
0x18000bd91  xor     ebx, ebx
0x18000bd93  mov     [r10], ebx
0x18000bd96  jmp     loc_18000BF22
0x18000bd9b  mov     ecx, [rdx]
0x18000bd9d  xor     r9d, r9d
0x18000bda0  cmp     r11d, 5
0x18000bda4  mov     ebx, 1
0x18000bda9  setz    r9b
0x18000bdad  mov     eax, ecx
0x18000bdaf  mov     dword ptr [r10+4], 0
0x18000bdb7  or      eax, ebx
0x18000bdb9  mov     edx, eax
0x18000bdbb  shr     edx, 16h
0x18000bdbe  and     edx, ebx
0x18000bdc0  cmp     edx, r9d
0x18000bdc3  jz      short loc_18000BE05
0x18000bdc5  mov     r8d, eax
0x18000bdc8  shr     r8d, 0Fh
0x18000bdcc  and     r8d, 7Fh
0x18000bdd0  jbe     short loc_18000BDEA
0x18000bdd2  cmp     r11d, ebx
0x18000bdd5  mov     [r10+4], r8d
0x18000bdd9  mov     edx, 5
0x18000bdde  cmovnz  edx, ebx
0x18000bde1  and     eax, 0FFC07FFFh
0x18000bde6  mov     [r10+8], edx
0x18000bdea  xor     r8d, r8d
0x18000bded  mov     edx, 400000h
0x18000bdf2  cmp     r11d, 5
0x18000bdf6  cmovz   r8d, edx
0x18000bdfa  mov     edx, eax
0x18000bdfc  btr     edx, 16h
0x18000be00  mov     eax, r8d
0x18000be03  or      eax, edx
0x18000be05  mov     edx, eax
0x18000be07  shr     edx, 0Fh
0x18000be0a  and     edx, 7Fh
0x18000be0d  lea     r8d, [rdx+1]
0x18000be11  cmp     r8d, 7Fh
0x18000be15  ja      short loc_18000BE1C
0x18000be17  cmp     r8d, edx
0x18000be1a  jnb     short loc_18000BE27
0x18000be1c  mov     r8d, ebx
0x18000be1f  mov     [r10+8], r11d
0x18000be23  mov     [r10+4], edx
0x18000be27  shl     r8d, 0Fh
0x18000be2b  xor     r8d, eax
0x18000be2e  and     r8d, 3F8000h
0x18000be35  xor     r8d, eax
0x18000be38  mov     eax, ecx
0x18000be3a  lock cmpxchg [rsi], r8d
0x18000be3f  jz      short loc_18000BE48
0x18000be41  mov     ecx, eax
0x18000be43  jmp     loc_18000BDAD
0x18000be48  not     ecx
0x18000be4a  and     ecx, ebx
0x18000be4c  mov     [r10], ecx
0x18000be4f  jmp     loc_18000BF1A
0x18000be54  mov     edx, [rdx]
0x18000be56  xor     ebp, ebp
0x18000be58  lea     ecx, [rbp+4]
0x18000be5b  cmp     r11d, ecx
0x18000be5e  lea     ebx, [rcx-3]
0x18000be61  setz    bpl
0x18000be65  mov     eax, edx
0x18000be67  mov     dword ptr [r10+4], 0
0x18000be6f  or      eax, ebx
0x18000be71  mov     r8d, eax
0x18000be74  shr     r8d, 0Eh
0x18000be78  and     r8d, ebx
0x18000be7b  cmp     r8d, ebp
0x18000be7e  jz      short loc_18000BEC7
0x18000be80  mov     edi, eax
0x18000be82  shr     edi, 5
0x18000be85  and     edi, 1FFh
0x18000be8b  jbe     short loc_18000BEA9
0x18000be8d  mov     r8d, r11d
0x18000be90  mov     [r10+4], edi
0x18000be94  neg     r8d
0x18000be97  sbb     r9d, r9d
0x18000be9a  not     r9d
0x18000be9d  and     r9d, ecx
0x18000bea0  mov     [r10+8], r9d
0x18000bea4  and     eax, 0FFFFC01Fh
0x18000bea9  xor     r9d, r9d
0x18000beac  mov     r8d, 4000h
0x18000beb2  cmp     r11d, ecx
0x18000beb5  cmovz   r9d, r8d
0x18000beb9  mov     r8d, eax
0x18000bebc  btr     r8d, 0Eh
0x18000bec1  mov     eax, r9d
0x18000bec4  or      eax, r8d
0x18000bec7  mov     r8d, eax
0x18000beca  shr     r8d, 5
0x18000bece  and     r8d, 1FFh
0x18000bed5  lea     r9d, [r8+1]
0x18000bed9  cmp     r9d, 1FFh
0x18000bee0  ja      short loc_18000BEE7
0x18000bee2  cmp     r9d, r8d
0x18000bee5  jnb     short loc_18000BEF2
0x18000bee7  mov     r9d, ebx
0x18000beea  mov     [r10+8], r11d
0x18000beee  mov     [r10+4], r8d
0x18000bef2  shl     r9d, 5
0x18000bef6  xor     r9d, eax
0x18000bef9  and     r9d, 3FE0h
0x18000bf00  xor     r9d, eax
0x18000bf03  mov     eax, edx
0x18000bf05  lock cmpxchg [rsi], r9d
0x18000bf0a  jz      short loc_18000BF13
0x18000bf0c  mov     edx, eax
0x18000bf0e  jmp     loc_18000BE65
0x18000bf13  not     edx
0x18000bf15  and     edx, ebx
0x18000bf17  mov     [r10], edx
0x18000bf1a  mov     dword ptr [r10+10h], 0
0x18000bf22  mov     rax, r10
0x18000bf25  pop     rdi
0x18000bf26  pop     rsi
0x18000bf27  pop     rbp
0x18000bf28  pop     rbx
0x18000bf29  retn
```
