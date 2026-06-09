# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1400075fc`
- end: `0x1400076c6`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400077a8`

## callees

- `0x1400075fc`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementOpportunityInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  int *v5; // r10
  BOOL v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 5;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 22) & 1) != v8 )
    {
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        a4[1] = (v9 >> 15) & 0x7F;
        v10 = 5;
        v5 = a4 + 2;
        if ( a2 != 1 )
          v10 = 1;
        v9 = v4 & 0xFFC07FFE | 1;
        *v5 = v10;
      }
      v11 = 0;
      if ( a2 == 5 )
        v11 = 0x400000;
      v9 = v9 & 0xFFBFFFFF | v11;
    }
    v12 = (v9 >> 15) & 0x7F;
    v13 = v12 + 1;
    if ( v12 + 1 > 0x7F || v13 < v12 )
    {
      v13 = 1;
      *v5 = a2;
      a4[1] = v12;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(a1, v9 ^ (v9 ^ (v13 << 15)) & 0x3F8000, v4);
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
0x1400075fc  push    rbx
0x1400075fe  push    rsi
0x1400075ff  push    rdi
0x140007600  mov     r8d, [rcx]
0x140007603  lea     r10, [r9+8]
0x140007607  xor     ebx, ebx
0x140007609  mov     r11d, edx
0x14000760c  cmp     edx, 5
0x14000760f  mov     rdi, rcx
0x140007612  mov     esi, 1
0x140007617  setz    bl
0x14000761a  mov     eax, r8d
0x14000761d  mov     dword ptr [r9+4], 0
0x140007625  or      eax, esi
0x140007627  mov     ecx, eax
0x140007629  shr     ecx, 16h
0x14000762c  and     ecx, esi
0x14000762e  cmp     ecx, ebx
0x140007630  jz      short loc_14000766F
0x140007632  mov     edx, eax
0x140007634  shr     edx, 0Fh
0x140007637  and     edx, 7Fh
0x14000763a  jbe     short loc_140007657
0x14000763c  cmp     r11d, esi
0x14000763f  mov     [r9+4], edx
0x140007643  mov     ecx, 5
0x140007648  lea     r10, [r9+8]
0x14000764c  cmovnz  ecx, esi
0x14000764f  and     eax, 0FFC07FFFh
0x140007654  mov     [r10], ecx
0x140007657  xor     edx, edx
0x140007659  mov     ecx, 400000h
0x14000765e  cmp     r11d, 5
0x140007662  cmovz   edx, ecx
0x140007665  mov     ecx, eax
0x140007667  btr     ecx, 16h
0x14000766b  mov     eax, edx
0x14000766d  or      eax, ecx
0x14000766f  mov     ecx, eax
0x140007671  shr     ecx, 0Fh
0x140007674  and     ecx, 7Fh
0x140007677  lea     edx, [rcx+1]
0x14000767a  cmp     edx, 7Fh
0x14000767d  ja      short loc_140007689
0x14000767f  cmp     edx, ecx
0x140007681  jb      short loc_140007689
0x140007683  lea     r10, [r9+8]
0x140007687  jmp     short loc_140007692
0x140007689  mov     edx, esi
0x14000768b  mov     [r10], r11d
0x14000768e  mov     [r9+4], ecx
0x140007692  shl     edx, 0Fh
0x140007695  xor     edx, eax
0x140007697  and     edx, 3F8000h
0x14000769d  xor     edx, eax
0x14000769f  mov     eax, r8d
0x1400076a2  lock cmpxchg [rdi], edx
0x1400076a6  jz      short loc_1400076B0
0x1400076a8  mov     r8d, eax
0x1400076ab  jmp     loc_14000761A
0x1400076b0  not     r8d
0x1400076b3  mov     dword ptr [r9+10h], 0
0x1400076bb  and     r8d, esi
0x1400076be  mov     [r9], r8d
0x1400076c1  pop     rdi
0x1400076c2  pop     rsi
0x1400076c3  pop     rbx
0x1400076c4  retn
```
