# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1800156f0`
- end: `0x1800157c5`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800157cc`

## callees

- `0x1800156f0`

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
0x1800156f0  push    rbx
0x1800156f2  push    rsi
0x1800156f3  push    rdi
0x1800156f4  mov     r8d, [rcx]
0x1800156f7  lea     r10, [r9+8]
0x1800156fb  xor     edi, edi
0x1800156fd  mov     ebx, edx
0x1800156ff  cmp     edx, 4
0x180015702  mov     rsi, rcx
0x180015705  setz    dil
0x180015709  mov     eax, r8d
0x18001570c  mov     dword ptr [r9+4], 0
0x180015714  or      eax, 1
0x180015717  mov     ecx, eax
0x180015719  shr     ecx, 0Eh
0x18001571c  and     ecx, 1
0x18001571f  cmp     ecx, edi
0x180015721  jz      short loc_180015765
0x180015723  mov     r11d, eax
0x180015726  shr     r11d, 5
0x18001572a  and     r11d, 1FFh
0x180015731  jbe     short loc_18001574E
0x180015733  mov     ecx, ebx
0x180015735  mov     [r9+4], r11d
0x180015739  neg     ecx
0x18001573b  lea     r10, [r9+8]
0x18001573f  sbb     edx, edx
0x180015741  not     edx
0x180015743  and     edx, 4
0x180015746  mov     [r10], edx
0x180015749  and     eax, 0FFFFC01Fh
0x18001574e  xor     edx, edx
0x180015750  mov     ecx, 4000h
0x180015755  cmp     ebx, 4
0x180015758  cmovz   edx, ecx
0x18001575b  mov     ecx, eax
0x18001575d  btr     ecx, 0Eh
0x180015761  mov     eax, edx
0x180015763  or      eax, ecx
0x180015765  mov     ecx, eax
0x180015767  shr     ecx, 5
0x18001576a  and     ecx, 1FFh
0x180015770  lea     edx, [rcx+1]
0x180015773  cmp     edx, 1FFh
0x180015779  ja      short loc_180015785
0x18001577b  cmp     edx, ecx
0x18001577d  jb      short loc_180015785
0x18001577f  lea     r10, [r9+8]
0x180015783  jmp     short loc_180015791
0x180015785  mov     edx, 1
0x18001578a  mov     [r10], ebx
0x18001578d  mov     [r9+4], ecx
0x180015791  shl     edx, 5
0x180015794  xor     edx, eax
0x180015796  and     edx, 3FE0h
0x18001579c  xor     edx, eax
0x18001579e  mov     eax, r8d
0x1800157a1  lock cmpxchg [rsi], edx
0x1800157a5  jz      short loc_1800157AF
0x1800157a7  mov     r8d, eax
0x1800157aa  jmp     loc_180015709
0x1800157af  not     r8d
0x1800157b2  mov     dword ptr [r9+10h], 0
0x1800157ba  and     r8d, 1
0x1800157be  mov     [r9], r8d
0x1800157c1  pop     rdi
0x1800157c2  pop     rsi
0x1800157c3  pop     rbx
0x1800157c4  retn
```
