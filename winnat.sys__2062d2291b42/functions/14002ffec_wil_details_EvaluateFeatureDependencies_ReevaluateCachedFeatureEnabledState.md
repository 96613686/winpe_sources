# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14002ffec`
- end: `0x1400300f9`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002ffb0`

## callees

- `0x14002ffb0`
- `0x14002ffec`

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
0x14002ffec  mov     [rsp+arg_8], rbx
0x14002fff1  mov     [rsp+arg_10], rbp
0x14002fff6  push    rsi
0x14002fff7  push    rdi
0x14002fff8  push    r13
0x14002fffa  push    r14
0x14002fffc  push    r15
0x14002fffe  sub     rsp, 20h
0x140030002  mov     r13d, 1
0x140030008  mov     [rsp+48h+arg_0], 0
0x140030011  mov     esi, edx
0x140030013  mov     r15, rcx
0x140030016  shr     esi, 6
0x140030019  mov     ecx, 0C00h
0x14003001e  mov     eax, edx
0x140030020  and     esi, r13d
0x140030023  and     eax, ecx
0x140030025  mov     rbx, rdx
0x140030028  mov     edi, r13d
0x14003002b  cmp     eax, ecx
0x14003002d  jz      short loc_140030037
0x14003002f  test    esi, esi
0x140030031  jnz     short loc_140030037
0x140030033  xor     ebp, ebp
0x140030035  jmp     short loc_1400300A5
0x140030037  mov     r14, [r8+20h]
0x14003003b  xor     ebp, ebp
0x14003003d  cmp     eax, ecx
0x14003003f  setz    bpl
0x140030043  test    r14, r14
0x140030046  jz      short loc_1400300A5
0x140030048  mov     rax, [r14]
0x14003004b  test    rax, rax
0x14003004e  jz      short loc_140030096
0x140030050  cmp     byte ptr [rax+1Eh], 0
0x140030054  jnz     short loc_140030081
0x140030056  cmp     byte ptr [rax+1Dh], 0
0x14003005a  jnz     short loc_140030081
0x14003005c  mov     rcx, [rax]
0x14003005f  mov     rdx, rax
0x140030062  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140030067  test    edi, edi
0x140030069  jz      short loc_140030075
0x14003006b  test    r13b, al
0x14003006e  jz      short loc_140030075
0x140030070  mov     edi, r13d
0x140030073  jmp     short loc_140030077
0x140030075  xor     edi, edi
0x140030077  add     r14, 8
0x14003007b  test    edi, edi
0x14003007d  jnz     short loc_140030048
0x14003007f  jmp     short loc_140030096
0x140030081  test    edi, edi
0x140030083  jz      short loc_140030094
0x140030085  cmp     byte ptr [rax+1Fh], 0
0x140030089  jz      short loc_140030094
0x14003008b  mov     edi, r13d
0x14003008e  add     r14, 8
0x140030092  jmp     short loc_140030048
0x140030094  xor     edi, edi
0x140030096  test    esi, esi
0x140030098  jz      short loc_1400300A3
0x14003009a  test    edi, edi
0x14003009c  jz      short loc_1400300A3
0x14003009e  mov     esi, r13d
0x1400300a1  jmp     short loc_1400300A5
0x1400300a3  xor     esi, esi
0x1400300a5  mov     edx, ebx
0x1400300a7  and     edx, 0FFFFFFFEh
0x1400300aa  or      edx, esi
0x1400300ac  test    ebp, ebp
0x1400300ae  jz      short loc_1400300B8
0x1400300b0  test    edi, edi
0x1400300b2  jnz     short loc_1400300B8
0x1400300b4  btr     edx, 0Ah
0x1400300b8  mov     eax, ebx
0x1400300ba  mov     ecx, edx
0x1400300bc  and     eax, r13d
0x1400300bf  and     ecx, 0FFFFFFCFh
0x1400300c2  cmp     eax, esi
0x1400300c4  mov     eax, ebx
0x1400300c6  cmovz   ecx, edx
0x1400300c9  btr     ecx, 9
0x1400300cd  mov     dword ptr [rsp+48h+arg_0], ecx
0x1400300d1  lock cmpxchg [r15], ecx
0x1400300d6  jz      short loc_1400300DC
0x1400300d8  mov     ebx, eax
0x1400300da  jmp     short loc_1400300A5
0x1400300dc  mov     rax, [rsp+48h+arg_0]
0x1400300e1  mov     rbx, [rsp+48h+arg_8]
0x1400300e6  mov     rbp, [rsp+48h+arg_10]
0x1400300eb  add     rsp, 20h
0x1400300ef  pop     r15
0x1400300f1  pop     r14
0x1400300f3  pop     r13
0x1400300f5  pop     rdi
0x1400300f6  pop     rsi
0x1400300f7  retn
```
