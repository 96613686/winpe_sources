# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400108e4`
- end: `0x1400109f1`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: `__int64 __fastcall(volatile signed __int32 *, unsigned __int32, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010790`
- `0x1400108a8`

## callees

- `0x1400108a8`
- `0x1400108e4`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        unsigned __int32 a2,
        __int64 a3)
{
  int v4; // esi
  signed __int32 v5; // ebx
  BOOL v6; // edi
  BOOL v7; // ebp
  __int64 *v8; // r14
  __int64 v9; // rax
  char CachedFeatureEnabledState; // al
  unsigned int v11; // edx
  unsigned int v12; // ecx
  signed __int32 v13; // eax
  __int64 v15; // [rsp+50h] [rbp+8h]

  HIDWORD(v15) = 0;
  v4 = (a2 >> 6) & 1;
  v5 = a2;
  v6 = 1;
  if ( (a2 & 0xC00) == 0xC00 || v4 )
  {
    v8 = *(__int64 **)(a3 + 32);
    v7 = (a2 & 0xC00) == 3072;
    if ( v8 )
    {
      while ( 1 )
      {
        v9 = *v8;
        if ( !*v8 )
          break;
        if ( *(_BYTE *)(v9 + 30) || *(_BYTE *)(v9 + 29) )
        {
          if ( !*(_BYTE *)(v9 + 31) )
          {
            v6 = 0;
            break;
          }
          v6 = 1;
          ++v8;
        }
        else
        {
          CachedFeatureEnabledState = wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
                                        *(unsigned int **)v9,
                                        *v8);
          v6 = (CachedFeatureEnabledState & 1) != 0;
          ++v8;
          if ( (CachedFeatureEnabledState & 1) == 0 )
            break;
        }
      }
      v4 = v4 && v6;
    }
  }
  else
  {
    v7 = 0;
  }
  while ( 1 )
  {
    v11 = v4 | v5 & 0xFFFFFFFE;
    if ( v7 && !v6 )
      v11 = v4 & 0xFFFFFBFF | v5 & 0xFFFFFBFE;
    v12 = v11 & 0xFFFFFFCF;
    if ( (v5 & 1) == v4 )
      v12 = v11;
    v13 = _InterlockedCompareExchange(a1, v12 & 0xFFFFFDFF, v5);
    if ( v5 == v13 )
      break;
    v5 = v13;
  }
  LODWORD(v15) = v12 & 0xFFFFFDFF;
  return v15;
}

```

## disassembly

```asm
0x1400108e4  mov     [rsp+arg_8], rbx
0x1400108e9  mov     [rsp+arg_10], rbp
0x1400108ee  push    rsi
0x1400108ef  push    rdi
0x1400108f0  push    r13
0x1400108f2  push    r14
0x1400108f4  push    r15
0x1400108f6  sub     rsp, 20h
0x1400108fa  mov     r13d, 1
0x140010900  mov     [rsp+48h+arg_0], 0
0x140010909  mov     esi, edx
0x14001090b  mov     r15, rcx
0x14001090e  shr     esi, 6
0x140010911  mov     ecx, 0C00h
0x140010916  mov     eax, edx
0x140010918  and     esi, r13d
0x14001091b  and     eax, ecx
0x14001091d  mov     rbx, rdx
0x140010920  mov     edi, r13d
0x140010923  cmp     eax, ecx
0x140010925  jz      short loc_14001092F
0x140010927  test    esi, esi
0x140010929  jnz     short loc_14001092F
0x14001092b  xor     ebp, ebp
0x14001092d  jmp     short loc_14001099D
0x14001092f  mov     r14, [r8+20h]
0x140010933  xor     ebp, ebp
0x140010935  cmp     eax, ecx
0x140010937  setz    bpl
0x14001093b  test    r14, r14
0x14001093e  jz      short loc_14001099D
0x140010940  mov     rax, [r14]
0x140010943  test    rax, rax
0x140010946  jz      short loc_14001098E
0x140010948  cmp     byte ptr [rax+1Eh], 0
0x14001094c  jnz     short loc_140010979
0x14001094e  cmp     byte ptr [rax+1Dh], 0
0x140010952  jnz     short loc_140010979
0x140010954  mov     rcx, [rax]
0x140010957  mov     rdx, rax
0x14001095a  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14001095f  test    edi, edi
0x140010961  jz      short loc_14001096D
0x140010963  test    r13b, al
0x140010966  jz      short loc_14001096D
0x140010968  mov     edi, r13d
0x14001096b  jmp     short loc_14001096F
0x14001096d  xor     edi, edi
0x14001096f  add     r14, 8
0x140010973  test    edi, edi
0x140010975  jnz     short loc_140010940
0x140010977  jmp     short loc_14001098E
0x140010979  test    edi, edi
0x14001097b  jz      short loc_14001098C
0x14001097d  cmp     byte ptr [rax+1Fh], 0
0x140010981  jz      short loc_14001098C
0x140010983  mov     edi, r13d
0x140010986  add     r14, 8
0x14001098a  jmp     short loc_140010940
0x14001098c  xor     edi, edi
0x14001098e  test    esi, esi
0x140010990  jz      short loc_14001099B
0x140010992  test    edi, edi
0x140010994  jz      short loc_14001099B
0x140010996  mov     esi, r13d
0x140010999  jmp     short loc_14001099D
0x14001099b  xor     esi, esi
0x14001099d  mov     edx, ebx
0x14001099f  and     edx, 0FFFFFFFEh
0x1400109a2  or      edx, esi
0x1400109a4  test    ebp, ebp
0x1400109a6  jz      short loc_1400109B0
0x1400109a8  test    edi, edi
0x1400109aa  jnz     short loc_1400109B0
0x1400109ac  btr     edx, 0Ah
0x1400109b0  mov     eax, ebx
0x1400109b2  mov     ecx, edx
0x1400109b4  and     eax, r13d
0x1400109b7  and     ecx, 0FFFFFFCFh
0x1400109ba  cmp     eax, esi
0x1400109bc  mov     eax, ebx
0x1400109be  cmovz   ecx, edx
0x1400109c1  btr     ecx, 9
0x1400109c5  mov     dword ptr [rsp+48h+arg_0], ecx
0x1400109c9  lock cmpxchg [r15], ecx
0x1400109ce  jz      short loc_1400109D4
0x1400109d0  mov     ebx, eax
0x1400109d2  jmp     short loc_14001099D
0x1400109d4  mov     rax, [rsp+48h+arg_0]
0x1400109d9  mov     rbx, [rsp+48h+arg_8]
0x1400109de  mov     rbp, [rsp+48h+arg_10]
0x1400109e3  add     rsp, 20h
0x1400109e7  pop     r15
0x1400109e9  pop     r14
0x1400109eb  pop     r13
0x1400109ed  pop     rdi
0x1400109ee  pop     rsi
0x1400109ef  retn
```
