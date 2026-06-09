# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x14001179c`
- end: `0x140011866`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001186c`

## callees

- `0x14001179c`

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
0x14001179c  push    rbx
0x14001179e  push    rsi
0x14001179f  push    rdi
0x1400117a0  mov     r8d, [rcx]
0x1400117a3  lea     r10, [r9+8]
0x1400117a7  xor     ebx, ebx
0x1400117a9  mov     r11d, edx
0x1400117ac  cmp     edx, 5
0x1400117af  mov     rdi, rcx
0x1400117b2  mov     esi, 1
0x1400117b7  setz    bl
0x1400117ba  mov     eax, r8d
0x1400117bd  mov     dword ptr [r9+4], 0
0x1400117c5  or      eax, esi
0x1400117c7  mov     ecx, eax
0x1400117c9  shr     ecx, 16h
0x1400117cc  and     ecx, esi
0x1400117ce  cmp     ecx, ebx
0x1400117d0  jz      short loc_14001180F
0x1400117d2  mov     edx, eax
0x1400117d4  shr     edx, 0Fh
0x1400117d7  and     edx, 7Fh
0x1400117da  jbe     short loc_1400117F7
0x1400117dc  cmp     r11d, esi
0x1400117df  mov     [r9+4], edx
0x1400117e3  mov     ecx, 5
0x1400117e8  lea     r10, [r9+8]
0x1400117ec  cmovnz  ecx, esi
0x1400117ef  and     eax, 0FFC07FFFh
0x1400117f4  mov     [r10], ecx
0x1400117f7  xor     edx, edx
0x1400117f9  mov     ecx, 400000h
0x1400117fe  cmp     r11d, 5
0x140011802  cmovz   edx, ecx
0x140011805  mov     ecx, eax
0x140011807  btr     ecx, 16h
0x14001180b  mov     eax, edx
0x14001180d  or      eax, ecx
0x14001180f  mov     ecx, eax
0x140011811  shr     ecx, 0Fh
0x140011814  and     ecx, 7Fh
0x140011817  lea     edx, [rcx+1]
0x14001181a  cmp     edx, 7Fh
0x14001181d  ja      short loc_140011829
0x14001181f  cmp     edx, ecx
0x140011821  jb      short loc_140011829
0x140011823  lea     r10, [r9+8]
0x140011827  jmp     short loc_140011832
0x140011829  mov     edx, esi
0x14001182b  mov     [r10], r11d
0x14001182e  mov     [r9+4], ecx
0x140011832  shl     edx, 0Fh
0x140011835  xor     edx, eax
0x140011837  and     edx, 3F8000h
0x14001183d  xor     edx, eax
0x14001183f  mov     eax, r8d
0x140011842  lock cmpxchg [rdi], edx
0x140011846  jz      short loc_140011850
0x140011848  mov     r8d, eax
0x14001184b  jmp     loc_1400117BA
0x140011850  not     r8d
0x140011853  mov     dword ptr [r9+10h], 0
0x14001185b  and     r8d, esi
0x14001185e  mov     [r9], r8d
0x140011861  pop     rdi
0x140011862  pop     rsi
0x140011863  pop     rbx
0x140011864  retn
```
