# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400225c8`
- end: `0x1400226d5`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: `__int64 __fastcall(volatile signed __int32 *, unsigned __int32, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002258c`

## callees

- `0x14002258c`
- `0x1400225c8`

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
                                        *(_DWORD **)v9,
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
0x1400225c8  mov     [rsp+arg_8], rbx
0x1400225cd  mov     [rsp+arg_10], rbp
0x1400225d2  push    rsi
0x1400225d3  push    rdi
0x1400225d4  push    r13
0x1400225d6  push    r14
0x1400225d8  push    r15
0x1400225da  sub     rsp, 20h
0x1400225de  mov     r13d, 1
0x1400225e4  mov     [rsp+48h+arg_0], 0
0x1400225ed  mov     esi, edx
0x1400225ef  mov     r15, rcx
0x1400225f2  shr     esi, 6
0x1400225f5  mov     ecx, 0C00h
0x1400225fa  mov     eax, edx
0x1400225fc  and     esi, r13d
0x1400225ff  and     eax, ecx
0x140022601  mov     rbx, rdx
0x140022604  mov     edi, r13d
0x140022607  cmp     eax, ecx
0x140022609  jz      short loc_140022613
0x14002260b  test    esi, esi
0x14002260d  jnz     short loc_140022613
0x14002260f  xor     ebp, ebp
0x140022611  jmp     short loc_140022681
0x140022613  mov     r14, [r8+20h]
0x140022617  xor     ebp, ebp
0x140022619  cmp     eax, ecx
0x14002261b  setz    bpl
0x14002261f  test    r14, r14
0x140022622  jz      short loc_140022681
0x140022624  mov     rax, [r14]
0x140022627  test    rax, rax
0x14002262a  jz      short loc_140022672
0x14002262c  cmp     byte ptr [rax+1Eh], 0
0x140022630  jnz     short loc_14002265D
0x140022632  cmp     byte ptr [rax+1Dh], 0
0x140022636  jnz     short loc_14002265D
0x140022638  mov     rcx, [rax]
0x14002263b  mov     rdx, rax
0x14002263e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140022643  test    edi, edi
0x140022645  jz      short loc_140022651
0x140022647  test    r13b, al
0x14002264a  jz      short loc_140022651
0x14002264c  mov     edi, r13d
0x14002264f  jmp     short loc_140022653
0x140022651  xor     edi, edi
0x140022653  add     r14, 8
0x140022657  test    edi, edi
0x140022659  jnz     short loc_140022624
0x14002265b  jmp     short loc_140022672
0x14002265d  test    edi, edi
0x14002265f  jz      short loc_140022670
0x140022661  cmp     byte ptr [rax+1Fh], 0
0x140022665  jz      short loc_140022670
0x140022667  mov     edi, r13d
0x14002266a  add     r14, 8
0x14002266e  jmp     short loc_140022624
0x140022670  xor     edi, edi
0x140022672  test    esi, esi
0x140022674  jz      short loc_14002267F
0x140022676  test    edi, edi
0x140022678  jz      short loc_14002267F
0x14002267a  mov     esi, r13d
0x14002267d  jmp     short loc_140022681
0x14002267f  xor     esi, esi
0x140022681  mov     edx, ebx
0x140022683  and     edx, 0FFFFFFFEh
0x140022686  or      edx, esi
0x140022688  test    ebp, ebp
0x14002268a  jz      short loc_140022694
0x14002268c  test    edi, edi
0x14002268e  jnz     short loc_140022694
0x140022690  btr     edx, 0Ah
0x140022694  mov     eax, ebx
0x140022696  mov     ecx, edx
0x140022698  and     eax, r13d
0x14002269b  and     ecx, 0FFFFFFCFh
0x14002269e  cmp     eax, esi
0x1400226a0  mov     eax, ebx
0x1400226a2  cmovz   ecx, edx
0x1400226a5  btr     ecx, 9
0x1400226a9  mov     dword ptr [rsp+48h+arg_0], ecx
0x1400226ad  lock cmpxchg [r15], ecx
0x1400226b2  jz      short loc_1400226B8
0x1400226b4  mov     ebx, eax
0x1400226b6  jmp     short loc_140022681
0x1400226b8  mov     rax, [rsp+48h+arg_0]
0x1400226bd  mov     rbx, [rsp+48h+arg_8]
0x1400226c2  mov     rbp, [rsp+48h+arg_10]
0x1400226c7  add     rsp, 20h
0x1400226cb  pop     r15
0x1400226cd  pop     r14
0x1400226cf  pop     r13
0x1400226d1  pop     rdi
0x1400226d2  pop     rsi
0x1400226d3  retn
```
