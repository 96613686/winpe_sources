# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x140011c90`
- end: `0x140011d5a`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011e3c`

## callees

- `0x140011c90`

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
0x140011c90  push    rbx
0x140011c92  push    rsi
0x140011c93  push    rdi
0x140011c94  mov     r8d, [rcx]
0x140011c97  lea     r10, [r9+8]
0x140011c9b  xor     ebx, ebx
0x140011c9d  mov     r11d, edx
0x140011ca0  cmp     edx, 5
0x140011ca3  mov     rdi, rcx
0x140011ca6  mov     esi, 1
0x140011cab  setz    bl
0x140011cae  mov     eax, r8d
0x140011cb1  mov     dword ptr [r9+4], 0
0x140011cb9  or      eax, esi
0x140011cbb  mov     ecx, eax
0x140011cbd  shr     ecx, 16h
0x140011cc0  and     ecx, esi
0x140011cc2  cmp     ecx, ebx
0x140011cc4  jz      short loc_140011D03
0x140011cc6  mov     edx, eax
0x140011cc8  shr     edx, 0Fh
0x140011ccb  and     edx, 7Fh
0x140011cce  jbe     short loc_140011CEB
0x140011cd0  cmp     r11d, esi
0x140011cd3  mov     [r9+4], edx
0x140011cd7  mov     ecx, 5
0x140011cdc  lea     r10, [r9+8]
0x140011ce0  cmovnz  ecx, esi
0x140011ce3  and     eax, 0FFC07FFFh
0x140011ce8  mov     [r10], ecx
0x140011ceb  xor     edx, edx
0x140011ced  mov     ecx, 400000h
0x140011cf2  cmp     r11d, 5
0x140011cf6  cmovz   edx, ecx
0x140011cf9  mov     ecx, eax
0x140011cfb  btr     ecx, 16h
0x140011cff  mov     eax, edx
0x140011d01  or      eax, ecx
0x140011d03  mov     ecx, eax
0x140011d05  shr     ecx, 0Fh
0x140011d08  and     ecx, 7Fh
0x140011d0b  lea     edx, [rcx+1]
0x140011d0e  cmp     edx, 7Fh
0x140011d11  ja      short loc_140011D1D
0x140011d13  cmp     edx, ecx
0x140011d15  jb      short loc_140011D1D
0x140011d17  lea     r10, [r9+8]
0x140011d1b  jmp     short loc_140011D26
0x140011d1d  mov     edx, esi
0x140011d1f  mov     [r10], r11d
0x140011d22  mov     [r9+4], ecx
0x140011d26  shl     edx, 0Fh
0x140011d29  xor     edx, eax
0x140011d2b  and     edx, 3F8000h
0x140011d31  xor     edx, eax
0x140011d33  mov     eax, r8d
0x140011d36  lock cmpxchg [rdi], edx
0x140011d3a  jz      short loc_140011D44
0x140011d3c  mov     r8d, eax
0x140011d3f  jmp     loc_140011CAE
0x140011d44  not     r8d
0x140011d47  mov     dword ptr [r9+10h], 0
0x140011d4f  and     r8d, esi
0x140011d52  mov     [r9], r8d
0x140011d55  pop     rdi
0x140011d56  pop     rsi
0x140011d57  pop     rbx
0x140011d58  retn
```
