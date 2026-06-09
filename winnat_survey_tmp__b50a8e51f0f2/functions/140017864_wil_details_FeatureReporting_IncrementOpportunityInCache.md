# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x140017864`
- end: `0x14001792e`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017a10`

## callees

- `0x140017864`

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
0x140017864  push    rbx
0x140017866  push    rsi
0x140017867  push    rdi
0x140017868  mov     r8d, [rcx]
0x14001786b  lea     r10, [r9+8]
0x14001786f  xor     ebx, ebx
0x140017871  mov     r11d, edx
0x140017874  cmp     edx, 5
0x140017877  mov     rdi, rcx
0x14001787a  mov     esi, 1
0x14001787f  setz    bl
0x140017882  mov     eax, r8d
0x140017885  mov     dword ptr [r9+4], 0
0x14001788d  or      eax, esi
0x14001788f  mov     ecx, eax
0x140017891  shr     ecx, 16h
0x140017894  and     ecx, esi
0x140017896  cmp     ecx, ebx
0x140017898  jz      short loc_1400178D7
0x14001789a  mov     edx, eax
0x14001789c  shr     edx, 0Fh
0x14001789f  and     edx, 7Fh
0x1400178a2  jbe     short loc_1400178BF
0x1400178a4  cmp     r11d, esi
0x1400178a7  mov     [r9+4], edx
0x1400178ab  mov     ecx, 5
0x1400178b0  lea     r10, [r9+8]
0x1400178b4  cmovnz  ecx, esi
0x1400178b7  and     eax, 0FFC07FFFh
0x1400178bc  mov     [r10], ecx
0x1400178bf  xor     edx, edx
0x1400178c1  mov     ecx, 400000h
0x1400178c6  cmp     r11d, 5
0x1400178ca  cmovz   edx, ecx
0x1400178cd  mov     ecx, eax
0x1400178cf  btr     ecx, 16h
0x1400178d3  mov     eax, edx
0x1400178d5  or      eax, ecx
0x1400178d7  mov     ecx, eax
0x1400178d9  shr     ecx, 0Fh
0x1400178dc  and     ecx, 7Fh
0x1400178df  lea     edx, [rcx+1]
0x1400178e2  cmp     edx, 7Fh
0x1400178e5  ja      short loc_1400178F1
0x1400178e7  cmp     edx, ecx
0x1400178e9  jb      short loc_1400178F1
0x1400178eb  lea     r10, [r9+8]
0x1400178ef  jmp     short loc_1400178FA
0x1400178f1  mov     edx, esi
0x1400178f3  mov     [r10], r11d
0x1400178f6  mov     [r9+4], ecx
0x1400178fa  shl     edx, 0Fh
0x1400178fd  xor     edx, eax
0x1400178ff  and     edx, 3F8000h
0x140017905  xor     edx, eax
0x140017907  mov     eax, r8d
0x14001790a  lock cmpxchg [rdi], edx
0x14001790e  jz      short loc_140017918
0x140017910  mov     r8d, eax
0x140017913  jmp     loc_140017882
0x140017918  not     r8d
0x14001791b  mov     dword ptr [r9+10h], 0
0x140017923  and     r8d, esi
0x140017926  mov     [r9], r8d
0x140017929  pop     rdi
0x14001792a  pop     rsi
0x14001792b  pop     rbx
0x14001792c  retn
```
