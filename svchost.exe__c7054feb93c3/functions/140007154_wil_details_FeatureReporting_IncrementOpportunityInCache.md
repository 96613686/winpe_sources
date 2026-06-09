# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x140007154`
- end: `0x14000721d`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007300`

## callees

- `0x140007154`

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
0x140007154  push    rbx
0x140007156  push    rsi
0x140007157  push    rdi
0x140007158  mov     r8d, [rcx]
0x14000715b  lea     r10, [r9+8]
0x14000715f  xor     ebx, ebx
0x140007161  mov     r11d, edx
0x140007164  cmp     edx, 5
0x140007167  mov     rdi, rcx
0x14000716a  mov     esi, 1
0x14000716f  setz    bl
0x140007172  mov     eax, r8d
0x140007175  mov     dword ptr [r9+4], 0
0x14000717d  or      eax, esi
0x14000717f  mov     ecx, eax
0x140007181  shr     ecx, 16h
0x140007184  and     ecx, esi
0x140007186  cmp     ecx, ebx
0x140007188  jz      short loc_1400071C7
0x14000718a  mov     edx, eax
0x14000718c  shr     edx, 0Fh
0x14000718f  and     edx, 7Fh
0x140007192  jbe     short loc_1400071AF
0x140007194  cmp     r11d, esi
0x140007197  mov     [r9+4], edx
0x14000719b  mov     ecx, 5
0x1400071a0  lea     r10, [r9+8]
0x1400071a4  cmovnz  ecx, esi
0x1400071a7  and     eax, 0FFC07FFFh
0x1400071ac  mov     [r10], ecx
0x1400071af  xor     edx, edx
0x1400071b1  mov     ecx, 400000h
0x1400071b6  cmp     r11d, 5
0x1400071ba  cmovz   edx, ecx
0x1400071bd  mov     ecx, eax
0x1400071bf  btr     ecx, 16h
0x1400071c3  mov     eax, edx
0x1400071c5  or      eax, ecx
0x1400071c7  mov     ecx, eax
0x1400071c9  shr     ecx, 0Fh
0x1400071cc  and     ecx, 7Fh
0x1400071cf  lea     edx, [rcx+1]
0x1400071d2  cmp     edx, 7Fh
0x1400071d5  ja      short loc_1400071E1
0x1400071d7  cmp     edx, ecx
0x1400071d9  jb      short loc_1400071E1
0x1400071db  lea     r10, [r9+8]
0x1400071df  jmp     short loc_1400071EA
0x1400071e1  mov     edx, esi
0x1400071e3  mov     [r10], r11d
0x1400071e6  mov     [r9+4], ecx
0x1400071ea  shl     edx, 0Fh
0x1400071ed  xor     edx, eax
0x1400071ef  and     edx, 3F8000h
0x1400071f5  xor     edx, eax
0x1400071f7  mov     eax, r8d
0x1400071fa  lock cmpxchg [rdi], edx
0x1400071fe  jz      short loc_140007208
0x140007200  mov     r8d, eax
0x140007203  jmp     loc_140007172
0x140007208  not     r8d
0x14000720b  mov     dword ptr [r9+10h], 0
0x140007213  and     r8d, esi
0x140007216  mov     [r9], r8d
0x140007219  pop     rdi
0x14000721a  pop     rsi
0x14000721b  pop     rbx
0x14000721c  retn
```
