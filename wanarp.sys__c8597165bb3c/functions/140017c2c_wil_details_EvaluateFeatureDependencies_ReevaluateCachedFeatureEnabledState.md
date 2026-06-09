# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140017c2c`
- end: `0x140017d39`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140017bf0`

## callees

- `0x140017bf0`
- `0x140017c2c`

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
  _QWORD *v8; // r14
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
    v8 = *(_QWORD **)(a3 + 32);
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
                                        *(_QWORD *)v9,
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
0x140017c2c  mov     [rsp+arg_8], rbx
0x140017c31  mov     [rsp+arg_10], rbp
0x140017c36  push    rsi
0x140017c37  push    rdi
0x140017c38  push    r13
0x140017c3a  push    r14
0x140017c3c  push    r15
0x140017c3e  sub     rsp, 20h
0x140017c42  mov     r13d, 1
0x140017c48  mov     [rsp+48h+arg_0], 0
0x140017c51  mov     esi, edx
0x140017c53  mov     r15, rcx
0x140017c56  shr     esi, 6
0x140017c59  mov     ecx, 0C00h
0x140017c5e  mov     eax, edx
0x140017c60  and     esi, r13d
0x140017c63  and     eax, ecx
0x140017c65  mov     rbx, rdx
0x140017c68  mov     edi, r13d
0x140017c6b  cmp     eax, ecx
0x140017c6d  jz      short loc_140017C77
0x140017c6f  test    esi, esi
0x140017c71  jnz     short loc_140017C77
0x140017c73  xor     ebp, ebp
0x140017c75  jmp     short loc_140017CE5
0x140017c77  mov     r14, [r8+20h]
0x140017c7b  xor     ebp, ebp
0x140017c7d  cmp     eax, ecx
0x140017c7f  setz    bpl
0x140017c83  test    r14, r14
0x140017c86  jz      short loc_140017CE5
0x140017c88  mov     rax, [r14]
0x140017c8b  test    rax, rax
0x140017c8e  jz      short loc_140017CD6
0x140017c90  cmp     byte ptr [rax+1Eh], 0
0x140017c94  jnz     short loc_140017CC1
0x140017c96  cmp     byte ptr [rax+1Dh], 0
0x140017c9a  jnz     short loc_140017CC1
0x140017c9c  mov     rcx, [rax]
0x140017c9f  mov     rdx, rax
0x140017ca2  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140017ca7  test    edi, edi
0x140017ca9  jz      short loc_140017CB5
0x140017cab  test    r13b, al
0x140017cae  jz      short loc_140017CB5
0x140017cb0  mov     edi, r13d
0x140017cb3  jmp     short loc_140017CB7
0x140017cb5  xor     edi, edi
0x140017cb7  add     r14, 8
0x140017cbb  test    edi, edi
0x140017cbd  jnz     short loc_140017C88
0x140017cbf  jmp     short loc_140017CD6
0x140017cc1  test    edi, edi
0x140017cc3  jz      short loc_140017CD4
0x140017cc5  cmp     byte ptr [rax+1Fh], 0
0x140017cc9  jz      short loc_140017CD4
0x140017ccb  mov     edi, r13d
0x140017cce  add     r14, 8
0x140017cd2  jmp     short loc_140017C88
0x140017cd4  xor     edi, edi
0x140017cd6  test    esi, esi
0x140017cd8  jz      short loc_140017CE3
0x140017cda  test    edi, edi
0x140017cdc  jz      short loc_140017CE3
0x140017cde  mov     esi, r13d
0x140017ce1  jmp     short loc_140017CE5
0x140017ce3  xor     esi, esi
0x140017ce5  mov     edx, ebx
0x140017ce7  and     edx, 0FFFFFFFEh
0x140017cea  or      edx, esi
0x140017cec  test    ebp, ebp
0x140017cee  jz      short loc_140017CF8
0x140017cf0  test    edi, edi
0x140017cf2  jnz     short loc_140017CF8
0x140017cf4  btr     edx, 0Ah
0x140017cf8  mov     eax, ebx
0x140017cfa  mov     ecx, edx
0x140017cfc  and     eax, r13d
0x140017cff  and     ecx, 0FFFFFFCFh
0x140017d02  cmp     eax, esi
0x140017d04  mov     eax, ebx
0x140017d06  cmovz   ecx, edx
0x140017d09  btr     ecx, 9
0x140017d0d  mov     dword ptr [rsp+48h+arg_0], ecx
0x140017d11  lock cmpxchg [r15], ecx
0x140017d16  jz      short loc_140017D1C
0x140017d18  mov     ebx, eax
0x140017d1a  jmp     short loc_140017CE5
0x140017d1c  mov     rax, [rsp+48h+arg_0]
0x140017d21  mov     rbx, [rsp+48h+arg_8]
0x140017d26  mov     rbp, [rsp+48h+arg_10]
0x140017d2b  add     rsp, 20h
0x140017d2f  pop     r15
0x140017d31  pop     r14
0x140017d33  pop     r13
0x140017d35  pop     rdi
0x140017d36  pop     rsi
0x140017d37  retn
```
