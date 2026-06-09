# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14004e864`
- end: `0x14004e971`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14004e828`

## callees

- `0x14004e828`
- `0x14004e864`

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
0x14004e864  mov     [rsp+arg_8], rbx
0x14004e869  mov     [rsp+arg_10], rbp
0x14004e86e  push    rsi
0x14004e86f  push    rdi
0x14004e870  push    r13
0x14004e872  push    r14
0x14004e874  push    r15
0x14004e876  sub     rsp, 20h
0x14004e87a  mov     r13d, 1
0x14004e880  mov     [rsp+48h+arg_0], 0
0x14004e889  mov     esi, edx
0x14004e88b  mov     r15, rcx
0x14004e88e  shr     esi, 6
0x14004e891  mov     ecx, 0C00h
0x14004e896  mov     eax, edx
0x14004e898  and     esi, r13d
0x14004e89b  and     eax, ecx
0x14004e89d  mov     rbx, rdx
0x14004e8a0  mov     edi, r13d
0x14004e8a3  cmp     eax, ecx
0x14004e8a5  jz      short loc_14004E8AF
0x14004e8a7  test    esi, esi
0x14004e8a9  jnz     short loc_14004E8AF
0x14004e8ab  xor     ebp, ebp
0x14004e8ad  jmp     short loc_14004E91D
0x14004e8af  mov     r14, [r8+20h]
0x14004e8b3  xor     ebp, ebp
0x14004e8b5  cmp     eax, ecx
0x14004e8b7  setz    bpl
0x14004e8bb  test    r14, r14
0x14004e8be  jz      short loc_14004E91D
0x14004e8c0  mov     rax, [r14]
0x14004e8c3  test    rax, rax
0x14004e8c6  jz      short loc_14004E90E
0x14004e8c8  cmp     byte ptr [rax+1Eh], 0
0x14004e8cc  jnz     short loc_14004E8F9
0x14004e8ce  cmp     byte ptr [rax+1Dh], 0
0x14004e8d2  jnz     short loc_14004E8F9
0x14004e8d4  mov     rcx, [rax]
0x14004e8d7  mov     rdx, rax
0x14004e8da  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14004e8df  test    edi, edi
0x14004e8e1  jz      short loc_14004E8ED
0x14004e8e3  test    r13b, al
0x14004e8e6  jz      short loc_14004E8ED
0x14004e8e8  mov     edi, r13d
0x14004e8eb  jmp     short loc_14004E8EF
0x14004e8ed  xor     edi, edi
0x14004e8ef  add     r14, 8
0x14004e8f3  test    edi, edi
0x14004e8f5  jnz     short loc_14004E8C0
0x14004e8f7  jmp     short loc_14004E90E
0x14004e8f9  test    edi, edi
0x14004e8fb  jz      short loc_14004E90C
0x14004e8fd  cmp     byte ptr [rax+1Fh], 0
0x14004e901  jz      short loc_14004E90C
0x14004e903  mov     edi, r13d
0x14004e906  add     r14, 8
0x14004e90a  jmp     short loc_14004E8C0
0x14004e90c  xor     edi, edi
0x14004e90e  test    esi, esi
0x14004e910  jz      short loc_14004E91B
0x14004e912  test    edi, edi
0x14004e914  jz      short loc_14004E91B
0x14004e916  mov     esi, r13d
0x14004e919  jmp     short loc_14004E91D
0x14004e91b  xor     esi, esi
0x14004e91d  mov     edx, ebx
0x14004e91f  and     edx, 0FFFFFFFEh
0x14004e922  or      edx, esi
0x14004e924  test    ebp, ebp
0x14004e926  jz      short loc_14004E930
0x14004e928  test    edi, edi
0x14004e92a  jnz     short loc_14004E930
0x14004e92c  btr     edx, 0Ah
0x14004e930  mov     eax, ebx
0x14004e932  mov     ecx, edx
0x14004e934  and     eax, r13d
0x14004e937  and     ecx, 0FFFFFFCFh
0x14004e93a  cmp     eax, esi
0x14004e93c  mov     eax, ebx
0x14004e93e  cmovz   ecx, edx
0x14004e941  btr     ecx, 9
0x14004e945  mov     dword ptr [rsp+48h+arg_0], ecx
0x14004e949  lock cmpxchg [r15], ecx
0x14004e94e  jz      short loc_14004E954
0x14004e950  mov     ebx, eax
0x14004e952  jmp     short loc_14004E91D
0x14004e954  mov     rax, [rsp+48h+arg_0]
0x14004e959  mov     rbx, [rsp+48h+arg_8]
0x14004e95e  mov     rbp, [rsp+48h+arg_10]
0x14004e963  add     rsp, 20h
0x14004e967  pop     r15
0x14004e969  pop     r14
0x14004e96b  pop     r13
0x14004e96d  pop     rdi
0x14004e96e  pop     rsi
0x14004e96f  retn
```
