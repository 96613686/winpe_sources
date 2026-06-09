# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14000b2b4`
- end: `0x14000b3c1`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b278`

## callees

- `0x14000b278`
- `0x14000b2b4`

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
0x14000b2b4  mov     [rsp+arg_8], rbx
0x14000b2b9  mov     [rsp+arg_10], rbp
0x14000b2be  push    rsi
0x14000b2bf  push    rdi
0x14000b2c0  push    r13
0x14000b2c2  push    r14
0x14000b2c4  push    r15
0x14000b2c6  sub     rsp, 20h
0x14000b2ca  mov     r13d, 1
0x14000b2d0  mov     [rsp+48h+arg_0], 0
0x14000b2d9  mov     esi, edx
0x14000b2db  mov     r15, rcx
0x14000b2de  shr     esi, 6
0x14000b2e1  mov     ecx, 0C00h
0x14000b2e6  mov     eax, edx
0x14000b2e8  and     esi, r13d
0x14000b2eb  and     eax, ecx
0x14000b2ed  mov     rbx, rdx
0x14000b2f0  mov     edi, r13d
0x14000b2f3  cmp     eax, ecx
0x14000b2f5  jz      short loc_14000B2FF
0x14000b2f7  test    esi, esi
0x14000b2f9  jnz     short loc_14000B2FF
0x14000b2fb  xor     ebp, ebp
0x14000b2fd  jmp     short loc_14000B36D
0x14000b2ff  mov     r14, [r8+20h]
0x14000b303  xor     ebp, ebp
0x14000b305  cmp     eax, ecx
0x14000b307  setz    bpl
0x14000b30b  test    r14, r14
0x14000b30e  jz      short loc_14000B36D
0x14000b310  mov     rax, [r14]
0x14000b313  test    rax, rax
0x14000b316  jz      short loc_14000B35E
0x14000b318  cmp     byte ptr [rax+1Eh], 0
0x14000b31c  jnz     short loc_14000B349
0x14000b31e  cmp     byte ptr [rax+1Dh], 0
0x14000b322  jnz     short loc_14000B349
0x14000b324  mov     rcx, [rax]
0x14000b327  mov     rdx, rax
0x14000b32a  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000b32f  test    edi, edi
0x14000b331  jz      short loc_14000B33D
0x14000b333  test    r13b, al
0x14000b336  jz      short loc_14000B33D
0x14000b338  mov     edi, r13d
0x14000b33b  jmp     short loc_14000B33F
0x14000b33d  xor     edi, edi
0x14000b33f  add     r14, 8
0x14000b343  test    edi, edi
0x14000b345  jnz     short loc_14000B310
0x14000b347  jmp     short loc_14000B35E
0x14000b349  test    edi, edi
0x14000b34b  jz      short loc_14000B35C
0x14000b34d  cmp     byte ptr [rax+1Fh], 0
0x14000b351  jz      short loc_14000B35C
0x14000b353  mov     edi, r13d
0x14000b356  add     r14, 8
0x14000b35a  jmp     short loc_14000B310
0x14000b35c  xor     edi, edi
0x14000b35e  test    esi, esi
0x14000b360  jz      short loc_14000B36B
0x14000b362  test    edi, edi
0x14000b364  jz      short loc_14000B36B
0x14000b366  mov     esi, r13d
0x14000b369  jmp     short loc_14000B36D
0x14000b36b  xor     esi, esi
0x14000b36d  mov     edx, ebx
0x14000b36f  and     edx, 0FFFFFFFEh
0x14000b372  or      edx, esi
0x14000b374  test    ebp, ebp
0x14000b376  jz      short loc_14000B380
0x14000b378  test    edi, edi
0x14000b37a  jnz     short loc_14000B380
0x14000b37c  btr     edx, 0Ah
0x14000b380  mov     eax, ebx
0x14000b382  mov     ecx, edx
0x14000b384  and     eax, r13d
0x14000b387  and     ecx, 0FFFFFFCFh
0x14000b38a  cmp     eax, esi
0x14000b38c  mov     eax, ebx
0x14000b38e  cmovz   ecx, edx
0x14000b391  btr     ecx, 9
0x14000b395  mov     dword ptr [rsp+48h+arg_0], ecx
0x14000b399  lock cmpxchg [r15], ecx
0x14000b39e  jz      short loc_14000B3A4
0x14000b3a0  mov     ebx, eax
0x14000b3a2  jmp     short loc_14000B36D
0x14000b3a4  mov     rax, [rsp+48h+arg_0]
0x14000b3a9  mov     rbx, [rsp+48h+arg_8]
0x14000b3ae  mov     rbp, [rsp+48h+arg_10]
0x14000b3b3  add     rsp, 20h
0x14000b3b7  pop     r15
0x14000b3b9  pop     r14
0x14000b3bb  pop     r13
0x14000b3bd  pop     rdi
0x14000b3be  pop     rsi
0x14000b3bf  retn
```
