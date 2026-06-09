# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180016ec0`
- end: `0x180016f8a`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001706c`

## callees

- `0x180016ec0`

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
0x180016ec0  push    rbx
0x180016ec2  push    rsi
0x180016ec3  push    rdi
0x180016ec4  mov     r8d, [rcx]
0x180016ec7  lea     r10, [r9+8]
0x180016ecb  xor     ebx, ebx
0x180016ecd  mov     r11d, edx
0x180016ed0  cmp     edx, 5
0x180016ed3  mov     rdi, rcx
0x180016ed6  mov     esi, 1
0x180016edb  setz    bl
0x180016ede  mov     eax, r8d
0x180016ee1  mov     dword ptr [r9+4], 0
0x180016ee9  or      eax, esi
0x180016eeb  mov     ecx, eax
0x180016eed  shr     ecx, 16h
0x180016ef0  and     ecx, esi
0x180016ef2  cmp     ecx, ebx
0x180016ef4  jz      short loc_180016F33
0x180016ef6  mov     edx, eax
0x180016ef8  shr     edx, 0Fh
0x180016efb  and     edx, 7Fh
0x180016efe  jbe     short loc_180016F1B
0x180016f00  cmp     r11d, esi
0x180016f03  mov     [r9+4], edx
0x180016f07  mov     ecx, 5
0x180016f0c  lea     r10, [r9+8]
0x180016f10  cmovnz  ecx, esi
0x180016f13  and     eax, 0FFC07FFFh
0x180016f18  mov     [r10], ecx
0x180016f1b  xor     edx, edx
0x180016f1d  mov     ecx, 400000h
0x180016f22  cmp     r11d, 5
0x180016f26  cmovz   edx, ecx
0x180016f29  mov     ecx, eax
0x180016f2b  btr     ecx, 16h
0x180016f2f  mov     eax, edx
0x180016f31  or      eax, ecx
0x180016f33  mov     ecx, eax
0x180016f35  shr     ecx, 0Fh
0x180016f38  and     ecx, 7Fh
0x180016f3b  lea     edx, [rcx+1]
0x180016f3e  cmp     edx, 7Fh
0x180016f41  ja      short loc_180016F4D
0x180016f43  cmp     edx, ecx
0x180016f45  jb      short loc_180016F4D
0x180016f47  lea     r10, [r9+8]
0x180016f4b  jmp     short loc_180016F56
0x180016f4d  mov     edx, esi
0x180016f4f  mov     [r10], r11d
0x180016f52  mov     [r9+4], ecx
0x180016f56  shl     edx, 0Fh
0x180016f59  xor     edx, eax
0x180016f5b  and     edx, 3F8000h
0x180016f61  xor     edx, eax
0x180016f63  mov     eax, r8d
0x180016f66  lock cmpxchg [rdi], edx
0x180016f6a  jz      short loc_180016F74
0x180016f6c  mov     r8d, eax
0x180016f6f  jmp     loc_180016EDE
0x180016f74  not     r8d
0x180016f77  mov     dword ptr [r9+10h], 0
0x180016f7f  and     r8d, esi
0x180016f82  mov     [r9], r8d
0x180016f85  pop     rdi
0x180016f86  pop     rsi
0x180016f87  pop     rbx
0x180016f88  retn
```
