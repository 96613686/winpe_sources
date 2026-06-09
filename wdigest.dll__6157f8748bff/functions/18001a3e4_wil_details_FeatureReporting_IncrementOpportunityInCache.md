# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18001a3e4`
- end: `0x18001a4ad`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b008`

## callees

- `0x18001a3e4`

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
0x18001a3e4  push    rbx
0x18001a3e6  push    rsi
0x18001a3e7  push    rdi
0x18001a3e8  mov     r8d, [rcx]
0x18001a3eb  lea     r10, [r9+8]
0x18001a3ef  xor     ebx, ebx
0x18001a3f1  mov     r11d, edx
0x18001a3f4  cmp     edx, 5
0x18001a3f7  mov     rdi, rcx
0x18001a3fa  mov     esi, 1
0x18001a3ff  setz    bl
0x18001a402  mov     eax, r8d
0x18001a405  mov     dword ptr [r9+4], 0
0x18001a40d  or      eax, esi
0x18001a40f  mov     ecx, eax
0x18001a411  shr     ecx, 16h
0x18001a414  and     ecx, esi
0x18001a416  cmp     ecx, ebx
0x18001a418  jz      short loc_18001A457
0x18001a41a  mov     edx, eax
0x18001a41c  shr     edx, 0Fh
0x18001a41f  and     edx, 7Fh
0x18001a422  jbe     short loc_18001A43F
0x18001a424  cmp     r11d, esi
0x18001a427  mov     [r9+4], edx
0x18001a42b  mov     ecx, 5
0x18001a430  lea     r10, [r9+8]
0x18001a434  cmovnz  ecx, esi
0x18001a437  and     eax, 0FFC07FFFh
0x18001a43c  mov     [r10], ecx
0x18001a43f  xor     edx, edx
0x18001a441  mov     ecx, 400000h
0x18001a446  cmp     r11d, 5
0x18001a44a  cmovz   edx, ecx
0x18001a44d  mov     ecx, eax
0x18001a44f  btr     ecx, 16h
0x18001a453  mov     eax, edx
0x18001a455  or      eax, ecx
0x18001a457  mov     ecx, eax
0x18001a459  shr     ecx, 0Fh
0x18001a45c  and     ecx, 7Fh
0x18001a45f  lea     edx, [rcx+1]
0x18001a462  cmp     edx, 7Fh
0x18001a465  ja      short loc_18001A471
0x18001a467  cmp     edx, ecx
0x18001a469  jb      short loc_18001A471
0x18001a46b  lea     r10, [r9+8]
0x18001a46f  jmp     short loc_18001A47A
0x18001a471  mov     edx, esi
0x18001a473  mov     [r10], r11d
0x18001a476  mov     [r9+4], ecx
0x18001a47a  shl     edx, 0Fh
0x18001a47d  xor     edx, eax
0x18001a47f  and     edx, 3F8000h
0x18001a485  xor     edx, eax
0x18001a487  mov     eax, r8d
0x18001a48a  lock cmpxchg [rdi], edx
0x18001a48e  jz      short loc_18001A498
0x18001a490  mov     r8d, eax
0x18001a493  jmp     loc_18001A402
0x18001a498  not     r8d
0x18001a49b  mov     dword ptr [r9+10h], 0
0x18001a4a3  and     r8d, esi
0x18001a4a6  mov     [r9], r8d
0x18001a4a9  pop     rdi
0x18001a4aa  pop     rsi
0x18001a4ab  pop     rbx
0x18001a4ac  retn
```
