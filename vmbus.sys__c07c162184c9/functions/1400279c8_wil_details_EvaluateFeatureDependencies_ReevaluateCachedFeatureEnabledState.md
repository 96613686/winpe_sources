# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400279c8`
- end: `0x140027ad5`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002798c`

## callees

- `0x14002798c`
- `0x1400279c8`

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
0x1400279c8  mov     [rsp+arg_8], rbx
0x1400279cd  mov     [rsp+arg_10], rbp
0x1400279d2  push    rsi
0x1400279d3  push    rdi
0x1400279d4  push    r13
0x1400279d6  push    r14
0x1400279d8  push    r15
0x1400279da  sub     rsp, 20h
0x1400279de  mov     r13d, 1
0x1400279e4  mov     [rsp+48h+arg_0], 0
0x1400279ed  mov     esi, edx
0x1400279ef  mov     r15, rcx
0x1400279f2  shr     esi, 6
0x1400279f5  mov     ecx, 0C00h
0x1400279fa  mov     eax, edx
0x1400279fc  and     esi, r13d
0x1400279ff  and     eax, ecx
0x140027a01  mov     rbx, rdx
0x140027a04  mov     edi, r13d
0x140027a07  cmp     eax, ecx
0x140027a09  jz      short loc_140027A13
0x140027a0b  test    esi, esi
0x140027a0d  jnz     short loc_140027A13
0x140027a0f  xor     ebp, ebp
0x140027a11  jmp     short loc_140027A81
0x140027a13  mov     r14, [r8+20h]
0x140027a17  xor     ebp, ebp
0x140027a19  cmp     eax, ecx
0x140027a1b  setz    bpl
0x140027a1f  test    r14, r14
0x140027a22  jz      short loc_140027A81
0x140027a24  mov     rax, [r14]
0x140027a27  test    rax, rax
0x140027a2a  jz      short loc_140027A72
0x140027a2c  cmp     byte ptr [rax+1Eh], 0
0x140027a30  jnz     short loc_140027A5D
0x140027a32  cmp     byte ptr [rax+1Dh], 0
0x140027a36  jnz     short loc_140027A5D
0x140027a38  mov     rcx, [rax]
0x140027a3b  mov     rdx, rax
0x140027a3e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140027a43  test    edi, edi
0x140027a45  jz      short loc_140027A51
0x140027a47  test    r13b, al
0x140027a4a  jz      short loc_140027A51
0x140027a4c  mov     edi, r13d
0x140027a4f  jmp     short loc_140027A53
0x140027a51  xor     edi, edi
0x140027a53  add     r14, 8
0x140027a57  test    edi, edi
0x140027a59  jnz     short loc_140027A24
0x140027a5b  jmp     short loc_140027A72
0x140027a5d  test    edi, edi
0x140027a5f  jz      short loc_140027A70
0x140027a61  cmp     byte ptr [rax+1Fh], 0
0x140027a65  jz      short loc_140027A70
0x140027a67  mov     edi, r13d
0x140027a6a  add     r14, 8
0x140027a6e  jmp     short loc_140027A24
0x140027a70  xor     edi, edi
0x140027a72  test    esi, esi
0x140027a74  jz      short loc_140027A7F
0x140027a76  test    edi, edi
0x140027a78  jz      short loc_140027A7F
0x140027a7a  mov     esi, r13d
0x140027a7d  jmp     short loc_140027A81
0x140027a7f  xor     esi, esi
0x140027a81  mov     edx, ebx
0x140027a83  and     edx, 0FFFFFFFEh
0x140027a86  or      edx, esi
0x140027a88  test    ebp, ebp
0x140027a8a  jz      short loc_140027A94
0x140027a8c  test    edi, edi
0x140027a8e  jnz     short loc_140027A94
0x140027a90  btr     edx, 0Ah
0x140027a94  mov     eax, ebx
0x140027a96  mov     ecx, edx
0x140027a98  and     eax, r13d
0x140027a9b  and     ecx, 0FFFFFFCFh
0x140027a9e  cmp     eax, esi
0x140027aa0  mov     eax, ebx
0x140027aa2  cmovz   ecx, edx
0x140027aa5  btr     ecx, 9
0x140027aa9  mov     dword ptr [rsp+48h+arg_0], ecx
0x140027aad  lock cmpxchg [r15], ecx
0x140027ab2  jz      short loc_140027AB8
0x140027ab4  mov     ebx, eax
0x140027ab6  jmp     short loc_140027A81
0x140027ab8  mov     rax, [rsp+48h+arg_0]
0x140027abd  mov     rbx, [rsp+48h+arg_8]
0x140027ac2  mov     rbp, [rsp+48h+arg_10]
0x140027ac7  add     rsp, 20h
0x140027acb  pop     r15
0x140027acd  pop     r14
0x140027acf  pop     r13
0x140027ad1  pop     rdi
0x140027ad2  pop     rsi
0x140027ad3  retn
```
