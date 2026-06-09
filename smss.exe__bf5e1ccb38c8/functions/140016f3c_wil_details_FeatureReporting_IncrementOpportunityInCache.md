# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x140016f3c`
- end: `0x140017005`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400170e8`

## callees

- `0x140016f3c`

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
0x140016f3c  push    rbx
0x140016f3e  push    rsi
0x140016f3f  push    rdi
0x140016f40  mov     r8d, [rcx]
0x140016f43  lea     r10, [r9+8]
0x140016f47  xor     ebx, ebx
0x140016f49  mov     r11d, edx
0x140016f4c  cmp     edx, 5
0x140016f4f  mov     rdi, rcx
0x140016f52  mov     esi, 1
0x140016f57  setz    bl
0x140016f5a  mov     eax, r8d
0x140016f5d  mov     dword ptr [r9+4], 0
0x140016f65  or      eax, esi
0x140016f67  mov     ecx, eax
0x140016f69  shr     ecx, 16h
0x140016f6c  and     ecx, esi
0x140016f6e  cmp     ecx, ebx
0x140016f70  jz      short loc_140016FAF
0x140016f72  mov     edx, eax
0x140016f74  shr     edx, 0Fh
0x140016f77  and     edx, 7Fh
0x140016f7a  jbe     short loc_140016F97
0x140016f7c  cmp     r11d, esi
0x140016f7f  mov     [r9+4], edx
0x140016f83  mov     ecx, 5
0x140016f88  lea     r10, [r9+8]
0x140016f8c  cmovnz  ecx, esi
0x140016f8f  and     eax, 0FFC07FFFh
0x140016f94  mov     [r10], ecx
0x140016f97  xor     edx, edx
0x140016f99  mov     ecx, 400000h
0x140016f9e  cmp     r11d, 5
0x140016fa2  cmovz   edx, ecx
0x140016fa5  mov     ecx, eax
0x140016fa7  btr     ecx, 16h
0x140016fab  mov     eax, edx
0x140016fad  or      eax, ecx
0x140016faf  mov     ecx, eax
0x140016fb1  shr     ecx, 0Fh
0x140016fb4  and     ecx, 7Fh
0x140016fb7  lea     edx, [rcx+1]
0x140016fba  cmp     edx, 7Fh
0x140016fbd  ja      short loc_140016FC9
0x140016fbf  cmp     edx, ecx
0x140016fc1  jb      short loc_140016FC9
0x140016fc3  lea     r10, [r9+8]
0x140016fc7  jmp     short loc_140016FD2
0x140016fc9  mov     edx, esi
0x140016fcb  mov     [r10], r11d
0x140016fce  mov     [r9+4], ecx
0x140016fd2  shl     edx, 0Fh
0x140016fd5  xor     edx, eax
0x140016fd7  and     edx, 3F8000h
0x140016fdd  xor     edx, eax
0x140016fdf  mov     eax, r8d
0x140016fe2  lock cmpxchg [rdi], edx
0x140016fe6  jz      short loc_140016FF0
0x140016fe8  mov     r8d, eax
0x140016feb  jmp     loc_140016F5A
0x140016ff0  not     r8d
0x140016ff3  mov     dword ptr [r9+10h], 0
0x140016ffb  and     r8d, esi
0x140016ffe  mov     [r9], r8d
0x140017001  pop     rdi
0x140017002  pop     rsi
0x140017003  pop     rbx
0x140017004  retn
```
