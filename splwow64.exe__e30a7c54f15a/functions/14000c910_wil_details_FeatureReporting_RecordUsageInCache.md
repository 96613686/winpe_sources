# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000c910`
- end: `0x14000cbea`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b708`

## callees

- `0x14000c910`

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
0x14000c910  push    rbx
0x14000c912  push    rbp
0x14000c913  push    rsi
0x14000c914  push    rdi
0x14000c915  xor     eax, eax
0x14000c917  xorps   xmm0, xmm0
0x14000c91a  mov     r11d, r8d
0x14000c91d  mov     rsi, rdx
0x14000c920  mov     r10, rcx
0x14000c923  mov     r9d, r8d
0x14000c926  movups  xmmword ptr [rcx], xmm0
0x14000c929  mov     [rcx+10h], rax
0x14000c92d  test    r8d, r8d
0x14000c930  jz      loc_14000CB14
0x14000c936  sub     r9d, 1
0x14000c93a  jz      loc_14000CA5B
0x14000c940  sub     r9d, 1
0x14000c944  jz      loc_14000C9E2
0x14000c94a  sub     r9d, 1
0x14000c94e  jz      loc_14000C9E2
0x14000c954  sub     r9d, 1
0x14000c958  jz      loc_14000CB14
0x14000c95e  sub     r9d, 1
0x14000c962  jz      loc_14000CA5B
0x14000c968  sub     r9d, 1
0x14000c96c  jz      short loc_14000C9E2
0x14000c96e  cmp     r9d, 1
0x14000c972  jz      short loc_14000C9E2
0x14000c974  add     r8d, 0FFFFFEC0h
0x14000c97b  lea     ebx, [rax+1]
0x14000c97e  cmp     r8d, 40h ; '@'
0x14000c982  jge     short loc_14000C9CD
0x14000c984  mov     eax, [rdx+4]
0x14000c987  lea     ecx, [rbx+0Fh]
0x14000c98a  mov     r9d, r8d
0x14000c98d  shl     r9d, 5
0x14000c991  test    cl, al
0x14000c993  jz      short loc_14000C9A6
0x14000c995  mov     edx, eax
0x14000c997  shr     edx, 5
0x14000c99a  and     edx, 3Fh
0x14000c99d  cmp     edx, r8d
0x14000c9a0  jnz     short loc_14000C9A6
0x14000c9a2  mov     edx, ebx
0x14000c9a4  jmp     short loc_14000C9A8
0x14000c9a6  xor     edx, edx
0x14000c9a8  mov     [r10+10h], edx
0x14000c9ac  mov     edx, r9d
0x14000c9af  xor     edx, eax
0x14000c9b1  and     edx, 7E0h
0x14000c9b7  xor     edx, eax
0x14000c9b9  or      edx, ecx
0x14000c9bb  lock cmpxchg [rsi+4], edx
0x14000c9c0  jnz     short loc_14000C991
0x14000c9c2  cmp     dword ptr [r10+10h], 0
0x14000c9c7  jnz     loc_14000CBE2
0x14000c9cd  mov     [r10+8], r11d
0x14000c9d1  mov     [r10+4], ebx
0x14000c9d5  mov     dword ptr [r10+0Ch], 0
0x14000c9dd  jmp     loc_14000CBE2
0x14000c9e2  xor     ecx, ecx
0x14000c9e4  sub     r11d, 2
0x14000c9e8  jz      short loc_14000CA10
0x14000c9ea  sub     r11d, 1
0x14000c9ee  jz      short loc_14000CA09
0x14000c9f0  sub     r11d, 3
0x14000c9f4  jz      short loc_14000CA02
0x14000c9f6  cmp     r11d, 1
0x14000c9fa  jnz     short loc_14000CA15
0x14000c9fc  lea     ecx, [r11+0Fh]
0x14000ca00  jmp     short loc_14000CA15
0x14000ca02  mov     ecx, 4
0x14000ca07  jmp     short loc_14000CA15
0x14000ca09  mov     ecx, 8
0x14000ca0e  jmp     short loc_14000CA15
0x14000ca10  mov     ecx, 2
0x14000ca15  mov     edx, [rdx]
0x14000ca17  mov     ebx, 1
0x14000ca1c  xor     eax, eax
0x14000ca1e  mov     r8d, ecx
0x14000ca21  or      r8d, edx
0x14000ca24  cmp     r8d, edx
0x14000ca27  mov     r9d, r8d
0x14000ca2a  setz    al
0x14000ca2d  or      r9d, ebx
0x14000ca30  cmp     r8d, edx
0x14000ca33  mov     [r10+10h], eax
0x14000ca37  mov     eax, edx
0x14000ca39  cmovz   r9d, r8d
0x14000ca3d  lock cmpxchg [rsi], r9d
0x14000ca42  jz      short loc_14000CA48
0x14000ca44  mov     edx, eax
0x14000ca46  jmp     short loc_14000CA1C
0x14000ca48  test    bl, r9b
0x14000ca4b  jz      short loc_14000CA51
0x14000ca4d  test    bl, dl
0x14000ca4f  jz      short loc_14000CA53
0x14000ca51  xor     ebx, ebx
0x14000ca53  mov     [r10], ebx
0x14000ca56  jmp     loc_14000CBE2
0x14000ca5b  mov     ecx, [rdx]
0x14000ca5d  xor     r9d, r9d
0x14000ca60  cmp     r11d, 5
0x14000ca64  mov     ebx, 1
0x14000ca69  setz    r9b
0x14000ca6d  mov     eax, ecx
0x14000ca6f  mov     dword ptr [r10+4], 0
0x14000ca77  or      eax, ebx
0x14000ca79  mov     edx, eax
0x14000ca7b  shr     edx, 16h
0x14000ca7e  and     edx, ebx
0x14000ca80  cmp     edx, r9d
0x14000ca83  jz      short loc_14000CAC5
0x14000ca85  mov     r8d, eax
0x14000ca88  shr     r8d, 0Fh
0x14000ca8c  and     r8d, 7Fh
0x14000ca90  jbe     short loc_14000CAAA
0x14000ca92  cmp     r11d, ebx
0x14000ca95  mov     [r10+4], r8d
0x14000ca99  mov     edx, 5
0x14000ca9e  cmovnz  edx, ebx
0x14000caa1  and     eax, 0FFC07FFFh
0x14000caa6  mov     [r10+8], edx
0x14000caaa  xor     r8d, r8d
0x14000caad  mov     edx, 400000h
0x14000cab2  cmp     r11d, 5
0x14000cab6  cmovz   r8d, edx
0x14000caba  mov     edx, eax
0x14000cabc  btr     edx, 16h
0x14000cac0  mov     eax, r8d
0x14000cac3  or      eax, edx
0x14000cac5  mov     edx, eax
0x14000cac7  shr     edx, 0Fh
0x14000caca  and     edx, 7Fh
0x14000cacd  lea     r8d, [rdx+1]
0x14000cad1  cmp     r8d, 7Fh
0x14000cad5  ja      short loc_14000CADC
0x14000cad7  cmp     r8d, edx
0x14000cada  jnb     short loc_14000CAE7
0x14000cadc  mov     r8d, ebx
0x14000cadf  mov     [r10+8], r11d
0x14000cae3  mov     [r10+4], edx
0x14000cae7  shl     r8d, 0Fh
0x14000caeb  xor     r8d, eax
0x14000caee  and     r8d, 3F8000h
0x14000caf5  xor     r8d, eax
0x14000caf8  mov     eax, ecx
0x14000cafa  lock cmpxchg [rsi], r8d
0x14000caff  jz      short loc_14000CB08
0x14000cb01  mov     ecx, eax
0x14000cb03  jmp     loc_14000CA6D
0x14000cb08  not     ecx
0x14000cb0a  and     ecx, ebx
0x14000cb0c  mov     [r10], ecx
0x14000cb0f  jmp     loc_14000CBDA
0x14000cb14  mov     edx, [rdx]
0x14000cb16  xor     ebp, ebp
0x14000cb18  lea     ecx, [rbp+4]
0x14000cb1b  cmp     r11d, ecx
0x14000cb1e  lea     ebx, [rcx-3]
0x14000cb21  setz    bpl
0x14000cb25  mov     eax, edx
0x14000cb27  mov     dword ptr [r10+4], 0
0x14000cb2f  or      eax, ebx
0x14000cb31  mov     r8d, eax
0x14000cb34  shr     r8d, 0Eh
0x14000cb38  and     r8d, ebx
0x14000cb3b  cmp     r8d, ebp
0x14000cb3e  jz      short loc_14000CB87
0x14000cb40  mov     edi, eax
0x14000cb42  shr     edi, 5
0x14000cb45  and     edi, 1FFh
0x14000cb4b  jbe     short loc_14000CB69
0x14000cb4d  mov     r8d, r11d
0x14000cb50  mov     [r10+4], edi
0x14000cb54  neg     r8d
0x14000cb57  sbb     r9d, r9d
0x14000cb5a  not     r9d
0x14000cb5d  and     r9d, ecx
0x14000cb60  mov     [r10+8], r9d
0x14000cb64  and     eax, 0FFFFC01Fh
0x14000cb69  xor     r9d, r9d
0x14000cb6c  mov     r8d, 4000h
0x14000cb72  cmp     r11d, ecx
0x14000cb75  cmovz   r9d, r8d
0x14000cb79  mov     r8d, eax
0x14000cb7c  btr     r8d, 0Eh
0x14000cb81  mov     eax, r9d
0x14000cb84  or      eax, r8d
0x14000cb87  mov     r8d, eax
0x14000cb8a  shr     r8d, 5
0x14000cb8e  and     r8d, 1FFh
0x14000cb95  lea     r9d, [r8+1]
0x14000cb99  cmp     r9d, 1FFh
0x14000cba0  ja      short loc_14000CBA7
0x14000cba2  cmp     r9d, r8d
0x14000cba5  jnb     short loc_14000CBB2
0x14000cba7  mov     r9d, ebx
0x14000cbaa  mov     [r10+8], r11d
0x14000cbae  mov     [r10+4], r8d
0x14000cbb2  shl     r9d, 5
0x14000cbb6  xor     r9d, eax
0x14000cbb9  and     r9d, 3FE0h
0x14000cbc0  xor     r9d, eax
0x14000cbc3  mov     eax, edx
0x14000cbc5  lock cmpxchg [rsi], r9d
0x14000cbca  jz      short loc_14000CBD3
0x14000cbcc  mov     edx, eax
0x14000cbce  jmp     loc_14000CB25
0x14000cbd3  not     edx
0x14000cbd5  and     edx, ebx
0x14000cbd7  mov     [r10], edx
0x14000cbda  mov     dword ptr [r10+10h], 0
0x14000cbe2  mov     rax, r10
0x14000cbe5  pop     rdi
0x14000cbe6  pop     rsi
0x14000cbe7  pop     rbp
0x14000cbe8  pop     rbx
0x14000cbe9  retn
```
