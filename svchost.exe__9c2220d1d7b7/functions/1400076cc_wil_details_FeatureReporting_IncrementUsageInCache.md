# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1400076cc`
- end: `0x1400077a2`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400077a8`

## callees

- `0x1400076cc`

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
0x1400076cc  push    rbx
0x1400076ce  push    rsi
0x1400076cf  push    rdi
0x1400076d0  mov     r8d, [rcx]
0x1400076d3  lea     r10, [r9+8]
0x1400076d7  xor     edi, edi
0x1400076d9  mov     ebx, edx
0x1400076db  cmp     edx, 4
0x1400076de  mov     rsi, rcx
0x1400076e1  setz    dil
0x1400076e5  mov     eax, r8d
0x1400076e8  mov     dword ptr [r9+4], 0
0x1400076f0  or      eax, 1
0x1400076f3  mov     ecx, eax
0x1400076f5  shr     ecx, 0Eh
0x1400076f8  and     ecx, 1
0x1400076fb  cmp     ecx, edi
0x1400076fd  jz      short loc_140007741
0x1400076ff  mov     r11d, eax
0x140007702  shr     r11d, 5
0x140007706  and     r11d, 1FFh
0x14000770d  jbe     short loc_14000772A
0x14000770f  mov     ecx, ebx
0x140007711  mov     [r9+4], r11d
0x140007715  neg     ecx
0x140007717  lea     r10, [r9+8]
0x14000771b  sbb     edx, edx
0x14000771d  not     edx
0x14000771f  and     edx, 4
0x140007722  mov     [r10], edx
0x140007725  and     eax, 0FFFFC01Fh
0x14000772a  xor     edx, edx
0x14000772c  mov     ecx, 4000h
0x140007731  cmp     ebx, 4
0x140007734  cmovz   edx, ecx
0x140007737  mov     ecx, eax
0x140007739  btr     ecx, 0Eh
0x14000773d  mov     eax, edx
0x14000773f  or      eax, ecx
0x140007741  mov     ecx, eax
0x140007743  shr     ecx, 5
0x140007746  and     ecx, 1FFh
0x14000774c  lea     edx, [rcx+1]
0x14000774f  cmp     edx, 1FFh
0x140007755  ja      short loc_140007761
0x140007757  cmp     edx, ecx
0x140007759  jb      short loc_140007761
0x14000775b  lea     r10, [r9+8]
0x14000775f  jmp     short loc_14000776D
0x140007761  mov     edx, 1
0x140007766  mov     [r10], ebx
0x140007769  mov     [r9+4], ecx
0x14000776d  shl     edx, 5
0x140007770  xor     edx, eax
0x140007772  and     edx, 3FE0h
0x140007778  xor     edx, eax
0x14000777a  mov     eax, r8d
0x14000777d  lock cmpxchg [rsi], edx
0x140007781  jz      short loc_14000778B
0x140007783  mov     r8d, eax
0x140007786  jmp     loc_1400076E5
0x14000778b  not     r8d
0x14000778e  mov     dword ptr [r9+10h], 0
0x140007796  and     r8d, 1
0x14000779a  mov     [r9], r8d
0x14000779d  pop     rdi
0x14000779e  pop     rsi
0x14000779f  pop     rbx
0x1400077a0  retn
```
