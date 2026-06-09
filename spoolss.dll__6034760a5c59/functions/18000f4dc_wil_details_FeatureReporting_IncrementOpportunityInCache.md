# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000f4dc`
- end: `0x18000f5a5`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f688`

## callees

- `0x18000f4dc`

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
0x18000f4dc  push    rbx
0x18000f4de  push    rsi
0x18000f4df  push    rdi
0x18000f4e0  mov     r8d, [rcx]
0x18000f4e3  lea     r10, [r9+8]
0x18000f4e7  xor     ebx, ebx
0x18000f4e9  mov     r11d, edx
0x18000f4ec  cmp     edx, 5
0x18000f4ef  mov     rdi, rcx
0x18000f4f2  mov     esi, 1
0x18000f4f7  setz    bl
0x18000f4fa  mov     eax, r8d
0x18000f4fd  mov     dword ptr [r9+4], 0
0x18000f505  or      eax, esi
0x18000f507  mov     ecx, eax
0x18000f509  shr     ecx, 16h
0x18000f50c  and     ecx, esi
0x18000f50e  cmp     ecx, ebx
0x18000f510  jz      short loc_18000F54F
0x18000f512  mov     edx, eax
0x18000f514  shr     edx, 0Fh
0x18000f517  and     edx, 7Fh
0x18000f51a  jbe     short loc_18000F537
0x18000f51c  cmp     r11d, esi
0x18000f51f  mov     [r9+4], edx
0x18000f523  mov     ecx, 5
0x18000f528  lea     r10, [r9+8]
0x18000f52c  cmovnz  ecx, esi
0x18000f52f  and     eax, 0FFC07FFFh
0x18000f534  mov     [r10], ecx
0x18000f537  xor     edx, edx
0x18000f539  mov     ecx, 400000h
0x18000f53e  cmp     r11d, 5
0x18000f542  cmovz   edx, ecx
0x18000f545  mov     ecx, eax
0x18000f547  btr     ecx, 16h
0x18000f54b  mov     eax, edx
0x18000f54d  or      eax, ecx
0x18000f54f  mov     ecx, eax
0x18000f551  shr     ecx, 0Fh
0x18000f554  and     ecx, 7Fh
0x18000f557  lea     edx, [rcx+1]
0x18000f55a  cmp     edx, 7Fh
0x18000f55d  ja      short loc_18000F569
0x18000f55f  cmp     edx, ecx
0x18000f561  jb      short loc_18000F569
0x18000f563  lea     r10, [r9+8]
0x18000f567  jmp     short loc_18000F572
0x18000f569  mov     edx, esi
0x18000f56b  mov     [r10], r11d
0x18000f56e  mov     [r9+4], ecx
0x18000f572  shl     edx, 0Fh
0x18000f575  xor     edx, eax
0x18000f577  and     edx, 3F8000h
0x18000f57d  xor     edx, eax
0x18000f57f  mov     eax, r8d
0x18000f582  lock cmpxchg [rdi], edx
0x18000f586  jz      short loc_18000F590
0x18000f588  mov     r8d, eax
0x18000f58b  jmp     loc_18000F4FA
0x18000f590  not     r8d
0x18000f593  mov     dword ptr [r9+10h], 0
0x18000f59b  and     r8d, esi
0x18000f59e  mov     [r9], r8d
0x18000f5a1  pop     rdi
0x18000f5a2  pop     rsi
0x18000f5a3  pop     rbx
0x18000f5a4  retn
```
