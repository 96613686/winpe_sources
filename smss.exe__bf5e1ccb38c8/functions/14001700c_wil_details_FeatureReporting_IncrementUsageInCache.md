# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x14001700c`
- end: `0x1400170e1`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400170e8`

## callees

- `0x14001700c`

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
0x14001700c  push    rbx
0x14001700e  push    rsi
0x14001700f  push    rdi
0x140017010  mov     r8d, [rcx]
0x140017013  lea     r10, [r9+8]
0x140017017  xor     edi, edi
0x140017019  mov     ebx, edx
0x14001701b  cmp     edx, 4
0x14001701e  mov     rsi, rcx
0x140017021  setz    dil
0x140017025  mov     eax, r8d
0x140017028  mov     dword ptr [r9+4], 0
0x140017030  or      eax, 1
0x140017033  mov     ecx, eax
0x140017035  shr     ecx, 0Eh
0x140017038  and     ecx, 1
0x14001703b  cmp     ecx, edi
0x14001703d  jz      short loc_140017081
0x14001703f  mov     r11d, eax
0x140017042  shr     r11d, 5
0x140017046  and     r11d, 1FFh
0x14001704d  jbe     short loc_14001706A
0x14001704f  mov     ecx, ebx
0x140017051  mov     [r9+4], r11d
0x140017055  neg     ecx
0x140017057  lea     r10, [r9+8]
0x14001705b  sbb     edx, edx
0x14001705d  not     edx
0x14001705f  and     edx, 4
0x140017062  mov     [r10], edx
0x140017065  and     eax, 0FFFFC01Fh
0x14001706a  xor     edx, edx
0x14001706c  mov     ecx, 4000h
0x140017071  cmp     ebx, 4
0x140017074  cmovz   edx, ecx
0x140017077  mov     ecx, eax
0x140017079  btr     ecx, 0Eh
0x14001707d  mov     eax, edx
0x14001707f  or      eax, ecx
0x140017081  mov     ecx, eax
0x140017083  shr     ecx, 5
0x140017086  and     ecx, 1FFh
0x14001708c  lea     edx, [rcx+1]
0x14001708f  cmp     edx, 1FFh
0x140017095  ja      short loc_1400170A1
0x140017097  cmp     edx, ecx
0x140017099  jb      short loc_1400170A1
0x14001709b  lea     r10, [r9+8]
0x14001709f  jmp     short loc_1400170AD
0x1400170a1  mov     edx, 1
0x1400170a6  mov     [r10], ebx
0x1400170a9  mov     [r9+4], ecx
0x1400170ad  shl     edx, 5
0x1400170b0  xor     edx, eax
0x1400170b2  and     edx, 3FE0h
0x1400170b8  xor     edx, eax
0x1400170ba  mov     eax, r8d
0x1400170bd  lock cmpxchg [rsi], edx
0x1400170c1  jz      short loc_1400170CB
0x1400170c3  mov     r8d, eax
0x1400170c6  jmp     loc_140017025
0x1400170cb  not     r8d
0x1400170ce  mov     dword ptr [r9+10h], 0
0x1400170d6  and     r8d, 1
0x1400170da  mov     [r9], r8d
0x1400170dd  pop     rdi
0x1400170de  pop     rsi
0x1400170df  pop     rbx
0x1400170e0  retn
```
