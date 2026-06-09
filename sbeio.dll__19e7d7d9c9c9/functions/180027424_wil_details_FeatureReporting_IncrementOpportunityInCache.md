# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180027424`
- end: `0x1800274ed`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800275d0`

## callees

- `0x180027424`

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
0x180027424  push    rbx
0x180027426  push    rsi
0x180027427  push    rdi
0x180027428  mov     r8d, [rcx]
0x18002742b  lea     r10, [r9+8]
0x18002742f  xor     ebx, ebx
0x180027431  mov     r11d, edx
0x180027434  cmp     edx, 5
0x180027437  mov     rdi, rcx
0x18002743a  mov     esi, 1
0x18002743f  setz    bl
0x180027442  mov     eax, r8d
0x180027445  mov     dword ptr [r9+4], 0
0x18002744d  or      eax, esi
0x18002744f  mov     ecx, eax
0x180027451  shr     ecx, 16h
0x180027454  and     ecx, esi
0x180027456  cmp     ecx, ebx
0x180027458  jz      short loc_180027497
0x18002745a  mov     edx, eax
0x18002745c  shr     edx, 0Fh
0x18002745f  and     edx, 7Fh
0x180027462  jbe     short loc_18002747F
0x180027464  cmp     r11d, esi
0x180027467  mov     [r9+4], edx
0x18002746b  mov     ecx, 5
0x180027470  lea     r10, [r9+8]
0x180027474  cmovnz  ecx, esi
0x180027477  and     eax, 0FFC07FFFh
0x18002747c  mov     [r10], ecx
0x18002747f  xor     edx, edx
0x180027481  mov     ecx, 400000h
0x180027486  cmp     r11d, 5
0x18002748a  cmovz   edx, ecx
0x18002748d  mov     ecx, eax
0x18002748f  btr     ecx, 16h
0x180027493  mov     eax, edx
0x180027495  or      eax, ecx
0x180027497  mov     ecx, eax
0x180027499  shr     ecx, 0Fh
0x18002749c  and     ecx, 7Fh
0x18002749f  lea     edx, [rcx+1]
0x1800274a2  cmp     edx, 7Fh
0x1800274a5  ja      short loc_1800274B1
0x1800274a7  cmp     edx, ecx
0x1800274a9  jb      short loc_1800274B1
0x1800274ab  lea     r10, [r9+8]
0x1800274af  jmp     short loc_1800274BA
0x1800274b1  mov     edx, esi
0x1800274b3  mov     [r10], r11d
0x1800274b6  mov     [r9+4], ecx
0x1800274ba  shl     edx, 0Fh
0x1800274bd  xor     edx, eax
0x1800274bf  and     edx, 3F8000h
0x1800274c5  xor     edx, eax
0x1800274c7  mov     eax, r8d
0x1800274ca  lock cmpxchg [rdi], edx
0x1800274ce  jz      short loc_1800274D8
0x1800274d0  mov     r8d, eax
0x1800274d3  jmp     loc_180027442
0x1800274d8  not     r8d
0x1800274db  mov     dword ptr [r9+10h], 0
0x1800274e3  and     r8d, esi
0x1800274e6  mov     [r9], r8d
0x1800274e9  pop     rdi
0x1800274ea  pop     rsi
0x1800274eb  pop     rbx
0x1800274ec  retn
```
