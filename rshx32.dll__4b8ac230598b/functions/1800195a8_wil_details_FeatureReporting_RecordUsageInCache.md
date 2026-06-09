# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800195a8`
- end: `0x180019882`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018c00`

## callees

- `0x1800195a8`

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
0x1800195a8  push    rbx
0x1800195aa  push    rbp
0x1800195ab  push    rsi
0x1800195ac  push    rdi
0x1800195ad  xor     eax, eax
0x1800195af  xorps   xmm0, xmm0
0x1800195b2  mov     r11d, r8d
0x1800195b5  mov     rsi, rdx
0x1800195b8  mov     r10, rcx
0x1800195bb  mov     r9d, r8d
0x1800195be  movups  xmmword ptr [rcx], xmm0
0x1800195c1  mov     [rcx+10h], rax
0x1800195c5  test    r8d, r8d
0x1800195c8  jz      loc_1800197AC
0x1800195ce  sub     r9d, 1
0x1800195d2  jz      loc_1800196F3
0x1800195d8  sub     r9d, 1
0x1800195dc  jz      loc_18001967A
0x1800195e2  sub     r9d, 1
0x1800195e6  jz      loc_18001967A
0x1800195ec  sub     r9d, 1
0x1800195f0  jz      loc_1800197AC
0x1800195f6  sub     r9d, 1
0x1800195fa  jz      loc_1800196F3
0x180019600  sub     r9d, 1
0x180019604  jz      short loc_18001967A
0x180019606  cmp     r9d, 1
0x18001960a  jz      short loc_18001967A
0x18001960c  add     r8d, 0FFFFFEC0h
0x180019613  lea     ebx, [rax+1]
0x180019616  cmp     r8d, 40h ; '@'
0x18001961a  jge     short loc_180019665
0x18001961c  mov     eax, [rdx+4]
0x18001961f  lea     ecx, [rbx+0Fh]
0x180019622  mov     r9d, r8d
0x180019625  shl     r9d, 5
0x180019629  test    cl, al
0x18001962b  jz      short loc_18001963E
0x18001962d  mov     edx, eax
0x18001962f  shr     edx, 5
0x180019632  and     edx, 3Fh
0x180019635  cmp     edx, r8d
0x180019638  jnz     short loc_18001963E
0x18001963a  mov     edx, ebx
0x18001963c  jmp     short loc_180019640
0x18001963e  xor     edx, edx
0x180019640  mov     [r10+10h], edx
0x180019644  mov     edx, r9d
0x180019647  xor     edx, eax
0x180019649  and     edx, 7E0h
0x18001964f  xor     edx, eax
0x180019651  or      edx, ecx
0x180019653  lock cmpxchg [rsi+4], edx
0x180019658  jnz     short loc_180019629
0x18001965a  cmp     dword ptr [r10+10h], 0
0x18001965f  jnz     loc_18001987A
0x180019665  mov     [r10+8], r11d
0x180019669  mov     [r10+4], ebx
0x18001966d  mov     dword ptr [r10+0Ch], 0
0x180019675  jmp     loc_18001987A
0x18001967a  xor     ecx, ecx
0x18001967c  sub     r11d, 2
0x180019680  jz      short loc_1800196A8
0x180019682  sub     r11d, 1
0x180019686  jz      short loc_1800196A1
0x180019688  sub     r11d, 3
0x18001968c  jz      short loc_18001969A
0x18001968e  cmp     r11d, 1
0x180019692  jnz     short loc_1800196AD
0x180019694  lea     ecx, [r11+0Fh]
0x180019698  jmp     short loc_1800196AD
0x18001969a  mov     ecx, 4
0x18001969f  jmp     short loc_1800196AD
0x1800196a1  mov     ecx, 8
0x1800196a6  jmp     short loc_1800196AD
0x1800196a8  mov     ecx, 2
0x1800196ad  mov     edx, [rdx]
0x1800196af  mov     ebx, 1
0x1800196b4  xor     eax, eax
0x1800196b6  mov     r8d, ecx
0x1800196b9  or      r8d, edx
0x1800196bc  cmp     r8d, edx
0x1800196bf  mov     r9d, r8d
0x1800196c2  setz    al
0x1800196c5  or      r9d, ebx
0x1800196c8  cmp     r8d, edx
0x1800196cb  mov     [r10+10h], eax
0x1800196cf  mov     eax, edx
0x1800196d1  cmovz   r9d, r8d
0x1800196d5  lock cmpxchg [rsi], r9d
0x1800196da  jz      short loc_1800196E0
0x1800196dc  mov     edx, eax
0x1800196de  jmp     short loc_1800196B4
0x1800196e0  test    bl, r9b
0x1800196e3  jz      short loc_1800196E9
0x1800196e5  test    bl, dl
0x1800196e7  jz      short loc_1800196EB
0x1800196e9  xor     ebx, ebx
0x1800196eb  mov     [r10], ebx
0x1800196ee  jmp     loc_18001987A
0x1800196f3  mov     ecx, [rdx]
0x1800196f5  xor     r9d, r9d
0x1800196f8  cmp     r11d, 5
0x1800196fc  mov     ebx, 1
0x180019701  setz    r9b
0x180019705  mov     eax, ecx
0x180019707  mov     dword ptr [r10+4], 0
0x18001970f  or      eax, ebx
0x180019711  mov     edx, eax
0x180019713  shr     edx, 16h
0x180019716  and     edx, ebx
0x180019718  cmp     edx, r9d
0x18001971b  jz      short loc_18001975D
0x18001971d  mov     r8d, eax
0x180019720  shr     r8d, 0Fh
0x180019724  and     r8d, 7Fh
0x180019728  jbe     short loc_180019742
0x18001972a  cmp     r11d, ebx
0x18001972d  mov     [r10+4], r8d
0x180019731  mov     edx, 5
0x180019736  cmovnz  edx, ebx
0x180019739  and     eax, 0FFC07FFFh
0x18001973e  mov     [r10+8], edx
0x180019742  xor     r8d, r8d
0x180019745  mov     edx, 400000h
0x18001974a  cmp     r11d, 5
0x18001974e  cmovz   r8d, edx
0x180019752  mov     edx, eax
0x180019754  btr     edx, 16h
0x180019758  mov     eax, r8d
0x18001975b  or      eax, edx
0x18001975d  mov     edx, eax
0x18001975f  shr     edx, 0Fh
0x180019762  and     edx, 7Fh
0x180019765  lea     r8d, [rdx+1]
0x180019769  cmp     r8d, 7Fh
0x18001976d  ja      short loc_180019774
0x18001976f  cmp     r8d, edx
0x180019772  jnb     short loc_18001977F
0x180019774  mov     r8d, ebx
0x180019777  mov     [r10+8], r11d
0x18001977b  mov     [r10+4], edx
0x18001977f  shl     r8d, 0Fh
0x180019783  xor     r8d, eax
0x180019786  and     r8d, 3F8000h
0x18001978d  xor     r8d, eax
0x180019790  mov     eax, ecx
0x180019792  lock cmpxchg [rsi], r8d
0x180019797  jz      short loc_1800197A0
0x180019799  mov     ecx, eax
0x18001979b  jmp     loc_180019705
0x1800197a0  not     ecx
0x1800197a2  and     ecx, ebx
0x1800197a4  mov     [r10], ecx
0x1800197a7  jmp     loc_180019872
0x1800197ac  mov     edx, [rdx]
0x1800197ae  xor     ebp, ebp
0x1800197b0  lea     ecx, [rbp+4]
0x1800197b3  cmp     r11d, ecx
0x1800197b6  lea     ebx, [rcx-3]
0x1800197b9  setz    bpl
0x1800197bd  mov     eax, edx
0x1800197bf  mov     dword ptr [r10+4], 0
0x1800197c7  or      eax, ebx
0x1800197c9  mov     r8d, eax
0x1800197cc  shr     r8d, 0Eh
0x1800197d0  and     r8d, ebx
0x1800197d3  cmp     r8d, ebp
0x1800197d6  jz      short loc_18001981F
0x1800197d8  mov     edi, eax
0x1800197da  shr     edi, 5
0x1800197dd  and     edi, 1FFh
0x1800197e3  jbe     short loc_180019801
0x1800197e5  mov     r8d, r11d
0x1800197e8  mov     [r10+4], edi
0x1800197ec  neg     r8d
0x1800197ef  sbb     r9d, r9d
0x1800197f2  not     r9d
0x1800197f5  and     r9d, ecx
0x1800197f8  mov     [r10+8], r9d
0x1800197fc  and     eax, 0FFFFC01Fh
0x180019801  xor     r9d, r9d
0x180019804  mov     r8d, 4000h
0x18001980a  cmp     r11d, ecx
0x18001980d  cmovz   r9d, r8d
0x180019811  mov     r8d, eax
0x180019814  btr     r8d, 0Eh
0x180019819  mov     eax, r9d
0x18001981c  or      eax, r8d
0x18001981f  mov     r8d, eax
0x180019822  shr     r8d, 5
0x180019826  and     r8d, 1FFh
0x18001982d  lea     r9d, [r8+1]
0x180019831  cmp     r9d, 1FFh
0x180019838  ja      short loc_18001983F
0x18001983a  cmp     r9d, r8d
0x18001983d  jnb     short loc_18001984A
0x18001983f  mov     r9d, ebx
0x180019842  mov     [r10+8], r11d
0x180019846  mov     [r10+4], r8d
0x18001984a  shl     r9d, 5
0x18001984e  xor     r9d, eax
0x180019851  and     r9d, 3FE0h
0x180019858  xor     r9d, eax
0x18001985b  mov     eax, edx
0x18001985d  lock cmpxchg [rsi], r9d
0x180019862  jz      short loc_18001986B
0x180019864  mov     edx, eax
0x180019866  jmp     loc_1800197BD
0x18001986b  not     edx
0x18001986d  and     edx, ebx
0x18001986f  mov     [r10], edx
0x180019872  mov     dword ptr [r10+10h], 0
0x18001987a  mov     rax, r10
0x18001987d  pop     rdi
0x18001987e  pop     rsi
0x18001987f  pop     rbp
0x180019880  pop     rbx
0x180019881  retn
```
