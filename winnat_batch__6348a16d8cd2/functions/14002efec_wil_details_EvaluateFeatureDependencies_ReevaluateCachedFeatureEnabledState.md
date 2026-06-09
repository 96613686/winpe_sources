# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14002efec`
- end: `0x14002f0a2`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002efb0`

## callees

- `0x14002efb0`
- `0x14002efec`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        unsigned __int32 a2,
        __int64 a3)
{
  signed __int32 v3; // ebx
  int v5; // edi
  __int64 *v6; // rsi
  __int64 v7; // rax
  unsigned int v8; // edx
  signed __int32 v9; // eax
  __int64 v11; // [rsp+50h] [rbp+8h]

  HIDWORD(v11) = 0;
  v3 = a2;
  v5 = (a2 >> 6) & 1;
  if ( v5 )
  {
    v6 = *(__int64 **)(a3 + 32);
    if ( v6 )
    {
      while ( 1 )
      {
        v7 = *v6;
        if ( !*v6 )
          break;
        if ( *(_BYTE *)(v7 + 30) || *(_BYTE *)(v7 + 29) )
        {
          if ( !*(_BYTE *)(v7 + 31) )
          {
            v5 = 0;
            goto LABEL_11;
          }
          v5 = 1;
          ++v6;
        }
        else
        {
          v5 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_DWORD **)v7, *v6++) & 1) != 0;
          if ( !v5 )
            goto LABEL_11;
        }
      }
    }
  }
  while ( 1 )
  {
LABEL_11:
    v8 = v5 & 0xFFFFFFCF | v3 & 0xFFFFFFCE;
    if ( (v3 & 1) == v5 )
      v8 = v5 | v3 & 0xFFFFFFFE;
    v9 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v3);
    if ( v3 == v9 )
      break;
    v3 = v9;
  }
  LODWORD(v11) = v8 & 0xFFFFFDFF;
  return v11;
}

```

## disassembly

```asm
0x14002efec  push    rbx
0x14002efee  push    rbp
0x14002efef  push    rsi
0x14002eff0  push    rdi
0x14002eff1  sub     rsp, 28h
0x14002eff5  mov     edi, edx
0x14002eff7  mov     [rsp+48h+arg_0], 0
0x14002f000  shr     edi, 6
0x14002f003  mov     rbx, rdx
0x14002f006  mov     rbp, rcx
0x14002f009  and     edi, 1
0x14002f00c  jz      short loc_14002F068
0x14002f00e  mov     rsi, [r8+20h]
0x14002f012  test    rsi, rsi
0x14002f015  jz      short loc_14002F068
0x14002f017  mov     rax, [rsi]
0x14002f01a  test    rax, rax
0x14002f01d  jz      short loc_14002F068
0x14002f01f  cmp     byte ptr [rax+1Eh], 0
0x14002f023  jnz     short loc_14002F051
0x14002f025  cmp     byte ptr [rax+1Dh], 0
0x14002f029  jnz     short loc_14002F051
0x14002f02b  mov     rcx, [rax]
0x14002f02e  mov     rdx, rax
0x14002f031  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14002f036  test    edi, edi
0x14002f038  jz      short loc_14002F045
0x14002f03a  test    al, 1
0x14002f03c  jz      short loc_14002F045
0x14002f03e  mov     edi, 1
0x14002f043  jmp     short loc_14002F047
0x14002f045  xor     edi, edi
0x14002f047  add     rsi, 8
0x14002f04b  test    edi, edi
0x14002f04d  jnz     short loc_14002F017
0x14002f04f  jmp     short loc_14002F068
0x14002f051  test    edi, edi
0x14002f053  jz      short loc_14002F066
0x14002f055  cmp     byte ptr [rax+1Fh], 0
0x14002f059  jz      short loc_14002F066
0x14002f05b  mov     edi, 1
0x14002f060  add     rsi, 8
0x14002f064  jmp     short loc_14002F017
0x14002f066  xor     edi, edi
0x14002f068  mov     ecx, ebx
0x14002f06a  mov     eax, ebx
0x14002f06c  and     ecx, 0FFFFFFFEh
0x14002f06f  and     eax, 1
0x14002f072  or      ecx, edi
0x14002f074  mov     edx, ecx
0x14002f076  and     edx, 0FFFFFFCFh
0x14002f079  cmp     eax, edi
0x14002f07b  mov     eax, ebx
0x14002f07d  cmovz   edx, ecx
0x14002f080  btr     edx, 9
0x14002f084  mov     dword ptr [rsp+48h+arg_0], edx
0x14002f088  lock cmpxchg [rbp+0], edx
0x14002f08d  jz      short loc_14002F093
0x14002f08f  mov     ebx, eax
0x14002f091  jmp     short loc_14002F068
0x14002f093  mov     rax, [rsp+48h+arg_0]
0x14002f098  add     rsp, 28h
0x14002f09c  pop     rdi
0x14002f09d  pop     rsi
0x14002f09e  pop     rbp
0x14002f09f  pop     rbx
0x14002f0a0  retn
```
