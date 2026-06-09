# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x140007224`
- end: `0x1400072f9`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007300`

## callees

- `0x140007224`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  _DWORD *v5; // r10
  BOOL v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 4;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 14) & 1) != v8 )
    {
      if ( ((v9 >> 5) & 0x1FF) != 0 )
      {
        a4[1] = (v9 >> 5) & 0x1FF;
        v5 = a4 + 2;
        a4[2] = a2 == 0 ? 4 : 0;
        v9 = v4 & 0xFFFFC01E | 1;
      }
      v10 = 0;
      if ( a2 == 4 )
        v10 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v10;
    }
    v11 = (v9 >> 5) & 0x1FF;
    v12 = v11 + 1;
    if ( v11 + 1 > 0x1FF || v12 < v11 )
    {
      LOWORD(v12) = 1;
      *v5 = a2;
      a4[1] = v11;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v12)) & 0x3FE0,
                             v4);
    if ( v4 == (_DWORD)result )
      break;
    v4 = result;
  }
  a4[4] = 0;
  *a4 = (v4 & 1) == 0;
  return result;
}

```

## disassembly

```asm
0x140007224  push    rbx
0x140007226  push    rsi
0x140007227  push    rdi
0x140007228  mov     r8d, [rcx]
0x14000722b  lea     r10, [r9+8]
0x14000722f  xor     edi, edi
0x140007231  mov     ebx, edx
0x140007233  cmp     edx, 4
0x140007236  mov     rsi, rcx
0x140007239  setz    dil
0x14000723d  mov     eax, r8d
0x140007240  mov     dword ptr [r9+4], 0
0x140007248  or      eax, 1
0x14000724b  mov     ecx, eax
0x14000724d  shr     ecx, 0Eh
0x140007250  and     ecx, 1
0x140007253  cmp     ecx, edi
0x140007255  jz      short loc_140007299
0x140007257  mov     r11d, eax
0x14000725a  shr     r11d, 5
0x14000725e  and     r11d, 1FFh
0x140007265  jbe     short loc_140007282
0x140007267  mov     ecx, ebx
0x140007269  mov     [r9+4], r11d
0x14000726d  neg     ecx
0x14000726f  lea     r10, [r9+8]
0x140007273  sbb     edx, edx
0x140007275  not     edx
0x140007277  and     edx, 4
0x14000727a  mov     [r10], edx
0x14000727d  and     eax, 0FFFFC01Fh
0x140007282  xor     edx, edx
0x140007284  mov     ecx, 4000h
0x140007289  cmp     ebx, 4
0x14000728c  cmovz   edx, ecx
0x14000728f  mov     ecx, eax
0x140007291  btr     ecx, 0Eh
0x140007295  mov     eax, edx
0x140007297  or      eax, ecx
0x140007299  mov     ecx, eax
0x14000729b  shr     ecx, 5
0x14000729e  and     ecx, 1FFh
0x1400072a4  lea     edx, [rcx+1]
0x1400072a7  cmp     edx, 1FFh
0x1400072ad  ja      short loc_1400072B9
0x1400072af  cmp     edx, ecx
0x1400072b1  jb      short loc_1400072B9
0x1400072b3  lea     r10, [r9+8]
0x1400072b7  jmp     short loc_1400072C5
0x1400072b9  mov     edx, 1
0x1400072be  mov     [r10], ebx
0x1400072c1  mov     [r9+4], ecx
0x1400072c5  shl     edx, 5
0x1400072c8  xor     edx, eax
0x1400072ca  and     edx, 3FE0h
0x1400072d0  xor     edx, eax
0x1400072d2  mov     eax, r8d
0x1400072d5  lock cmpxchg [rsi], edx
0x1400072d9  jz      short loc_1400072E3
0x1400072db  mov     r8d, eax
0x1400072de  jmp     loc_14000723D
0x1400072e3  not     r8d
0x1400072e6  mov     dword ptr [r9+10h], 0
0x1400072ee  and     r8d, 1
0x1400072f2  mov     [r9], r8d
0x1400072f5  pop     rdi
0x1400072f6  pop     rsi
0x1400072f7  pop     rbx
0x1400072f8  retn
```
