# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180015620`
- end: `0x1800156e9`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800157cc`

## callees

- `0x180015620`

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
0x180015620  push    rbx
0x180015622  push    rsi
0x180015623  push    rdi
0x180015624  mov     r8d, [rcx]
0x180015627  lea     r10, [r9+8]
0x18001562b  xor     ebx, ebx
0x18001562d  mov     r11d, edx
0x180015630  cmp     edx, 5
0x180015633  mov     rdi, rcx
0x180015636  mov     esi, 1
0x18001563b  setz    bl
0x18001563e  mov     eax, r8d
0x180015641  mov     dword ptr [r9+4], 0
0x180015649  or      eax, esi
0x18001564b  mov     ecx, eax
0x18001564d  shr     ecx, 16h
0x180015650  and     ecx, esi
0x180015652  cmp     ecx, ebx
0x180015654  jz      short loc_180015693
0x180015656  mov     edx, eax
0x180015658  shr     edx, 0Fh
0x18001565b  and     edx, 7Fh
0x18001565e  jbe     short loc_18001567B
0x180015660  cmp     r11d, esi
0x180015663  mov     [r9+4], edx
0x180015667  mov     ecx, 5
0x18001566c  lea     r10, [r9+8]
0x180015670  cmovnz  ecx, esi
0x180015673  and     eax, 0FFC07FFFh
0x180015678  mov     [r10], ecx
0x18001567b  xor     edx, edx
0x18001567d  mov     ecx, 400000h
0x180015682  cmp     r11d, 5
0x180015686  cmovz   edx, ecx
0x180015689  mov     ecx, eax
0x18001568b  btr     ecx, 16h
0x18001568f  mov     eax, edx
0x180015691  or      eax, ecx
0x180015693  mov     ecx, eax
0x180015695  shr     ecx, 0Fh
0x180015698  and     ecx, 7Fh
0x18001569b  lea     edx, [rcx+1]
0x18001569e  cmp     edx, 7Fh
0x1800156a1  ja      short loc_1800156AD
0x1800156a3  cmp     edx, ecx
0x1800156a5  jb      short loc_1800156AD
0x1800156a7  lea     r10, [r9+8]
0x1800156ab  jmp     short loc_1800156B6
0x1800156ad  mov     edx, esi
0x1800156af  mov     [r10], r11d
0x1800156b2  mov     [r9+4], ecx
0x1800156b6  shl     edx, 0Fh
0x1800156b9  xor     edx, eax
0x1800156bb  and     edx, 3F8000h
0x1800156c1  xor     edx, eax
0x1800156c3  mov     eax, r8d
0x1800156c6  lock cmpxchg [rdi], edx
0x1800156ca  jz      short loc_1800156D4
0x1800156cc  mov     r8d, eax
0x1800156cf  jmp     loc_18001563E
0x1800156d4  not     r8d
0x1800156d7  mov     dword ptr [r9+10h], 0
0x1800156df  and     r8d, esi
0x1800156e2  mov     [r9], r8d
0x1800156e5  pop     rdi
0x1800156e6  pop     rsi
0x1800156e7  pop     rbx
0x1800156e8  retn
```
