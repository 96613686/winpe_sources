# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180015130`
- end: `0x180015205`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001520c`

## callees

- `0x180015130`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  _DWORD *v5; // r10
  BOOL v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 4;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 14) & 1) != v8 )
    {
      if ( ((v9 >> 5) & 0x1FF) != 0 )
      {
        a4[1] = (v9 >> 5) & 0x1FF;
        v5 = a4 + 2;
        a4[2] = a2 == 0 ? 4 : 0;
        v9 = v4 & 0xFFFFC01E | 1;
      }
      v10 = 0;
      if ( a2 == 4 )
        v10 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v10;
    }
    v11 = (v9 >> 5) & 0x1FF;
    v12 = v11 + 1;
    if ( v11 + 1 > 0x1FF || v12 < v11 )
    {
      LOWORD(v12) = 1;
      *v5 = a2;
      a4[1] = v11;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v12)) & 0x3FE0,
                             v4);
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
0x180015130  push    rbx
0x180015132  push    rsi
0x180015133  push    rdi
0x180015134  mov     r8d, [rcx]
0x180015137  lea     r10, [r9+8]
0x18001513b  xor     edi, edi
0x18001513d  mov     ebx, edx
0x18001513f  cmp     edx, 4
0x180015142  mov     rsi, rcx
0x180015145  setz    dil
0x180015149  mov     eax, r8d
0x18001514c  mov     dword ptr [r9+4], 0
0x180015154  or      eax, 1
0x180015157  mov     ecx, eax
0x180015159  shr     ecx, 0Eh
0x18001515c  and     ecx, 1
0x18001515f  cmp     ecx, edi
0x180015161  jz      short loc_1800151A5
0x180015163  mov     r11d, eax
0x180015166  shr     r11d, 5
0x18001516a  and     r11d, 1FFh
0x180015171  jbe     short loc_18001518E
0x180015173  mov     ecx, ebx
0x180015175  mov     [r9+4], r11d
0x180015179  neg     ecx
0x18001517b  lea     r10, [r9+8]
0x18001517f  sbb     edx, edx
0x180015181  not     edx
0x180015183  and     edx, 4
0x180015186  mov     [r10], edx
0x180015189  and     eax, 0FFFFC01Fh
0x18001518e  xor     edx, edx
0x180015190  mov     ecx, 4000h
0x180015195  cmp     ebx, 4
0x180015198  cmovz   edx, ecx
0x18001519b  mov     ecx, eax
0x18001519d  btr     ecx, 0Eh
0x1800151a1  mov     eax, edx
0x1800151a3  or      eax, ecx
0x1800151a5  mov     ecx, eax
0x1800151a7  shr     ecx, 5
0x1800151aa  and     ecx, 1FFh
0x1800151b0  lea     edx, [rcx+1]
0x1800151b3  cmp     edx, 1FFh
0x1800151b9  ja      short loc_1800151C5
0x1800151bb  cmp     edx, ecx
0x1800151bd  jb      short loc_1800151C5
0x1800151bf  lea     r10, [r9+8]
0x1800151c3  jmp     short loc_1800151D1
0x1800151c5  mov     edx, 1
0x1800151ca  mov     [r10], ebx
0x1800151cd  mov     [r9+4], ecx
0x1800151d1  shl     edx, 5
0x1800151d4  xor     edx, eax
0x1800151d6  and     edx, 3FE0h
0x1800151dc  xor     edx, eax
0x1800151de  mov     eax, r8d
0x1800151e1  lock cmpxchg [rsi], edx
0x1800151e5  jz      short loc_1800151EF
0x1800151e7  mov     r8d, eax
0x1800151ea  jmp     loc_180015149
0x1800151ef  not     r8d
0x1800151f2  mov     dword ptr [r9+10h], 0
0x1800151fa  and     r8d, 1
0x1800151fe  mov     [r9], r8d
0x180015201  pop     rdi
0x180015202  pop     rsi
0x180015203  pop     rbx
0x180015204  retn
```
