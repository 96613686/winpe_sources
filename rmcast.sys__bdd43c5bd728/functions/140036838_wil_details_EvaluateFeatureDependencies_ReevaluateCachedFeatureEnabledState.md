# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140036838`
- end: `0x140036945`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400367fc`

## callees

- `0x1400367fc`
- `0x140036838`

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
0x140036838  mov     [rsp+arg_8], rbx
0x14003683d  mov     [rsp+arg_10], rbp
0x140036842  push    rsi
0x140036843  push    rdi
0x140036844  push    r13
0x140036846  push    r14
0x140036848  push    r15
0x14003684a  sub     rsp, 20h
0x14003684e  mov     r13d, 1
0x140036854  mov     [rsp+48h+arg_0], 0
0x14003685d  mov     esi, edx
0x14003685f  mov     r15, rcx
0x140036862  shr     esi, 6
0x140036865  mov     ecx, 0C00h
0x14003686a  mov     eax, edx
0x14003686c  and     esi, r13d
0x14003686f  and     eax, ecx
0x140036871  mov     rbx, rdx
0x140036874  mov     edi, r13d
0x140036877  cmp     eax, ecx
0x140036879  jz      short loc_140036883
0x14003687b  test    esi, esi
0x14003687d  jnz     short loc_140036883
0x14003687f  xor     ebp, ebp
0x140036881  jmp     short loc_1400368F1
0x140036883  mov     r14, [r8+20h]
0x140036887  xor     ebp, ebp
0x140036889  cmp     eax, ecx
0x14003688b  setz    bpl
0x14003688f  test    r14, r14
0x140036892  jz      short loc_1400368F1
0x140036894  mov     rax, [r14]
0x140036897  test    rax, rax
0x14003689a  jz      short loc_1400368E2
0x14003689c  cmp     byte ptr [rax+1Eh], 0
0x1400368a0  jnz     short loc_1400368CD
0x1400368a2  cmp     byte ptr [rax+1Dh], 0
0x1400368a6  jnz     short loc_1400368CD
0x1400368a8  mov     rcx, [rax]
0x1400368ab  mov     rdx, rax
0x1400368ae  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400368b3  test    edi, edi
0x1400368b5  jz      short loc_1400368C1
0x1400368b7  test    r13b, al
0x1400368ba  jz      short loc_1400368C1
0x1400368bc  mov     edi, r13d
0x1400368bf  jmp     short loc_1400368C3
0x1400368c1  xor     edi, edi
0x1400368c3  add     r14, 8
0x1400368c7  test    edi, edi
0x1400368c9  jnz     short loc_140036894
0x1400368cb  jmp     short loc_1400368E2
0x1400368cd  test    edi, edi
0x1400368cf  jz      short loc_1400368E0
0x1400368d1  cmp     byte ptr [rax+1Fh], 0
0x1400368d5  jz      short loc_1400368E0
0x1400368d7  mov     edi, r13d
0x1400368da  add     r14, 8
0x1400368de  jmp     short loc_140036894
0x1400368e0  xor     edi, edi
0x1400368e2  test    esi, esi
0x1400368e4  jz      short loc_1400368EF
0x1400368e6  test    edi, edi
0x1400368e8  jz      short loc_1400368EF
0x1400368ea  mov     esi, r13d
0x1400368ed  jmp     short loc_1400368F1
0x1400368ef  xor     esi, esi
0x1400368f1  mov     edx, ebx
0x1400368f3  and     edx, 0FFFFFFFEh
0x1400368f6  or      edx, esi
0x1400368f8  test    ebp, ebp
0x1400368fa  jz      short loc_140036904
0x1400368fc  test    edi, edi
0x1400368fe  jnz     short loc_140036904
0x140036900  btr     edx, 0Ah
0x140036904  mov     eax, ebx
0x140036906  mov     ecx, edx
0x140036908  and     eax, r13d
0x14003690b  and     ecx, 0FFFFFFCFh
0x14003690e  cmp     eax, esi
0x140036910  mov     eax, ebx
0x140036912  cmovz   ecx, edx
0x140036915  btr     ecx, 9
0x140036919  mov     dword ptr [rsp+48h+arg_0], ecx
0x14003691d  lock cmpxchg [r15], ecx
0x140036922  jz      short loc_140036928
0x140036924  mov     ebx, eax
0x140036926  jmp     short loc_1400368F1
0x140036928  mov     rax, [rsp+48h+arg_0]
0x14003692d  mov     rbx, [rsp+48h+arg_8]
0x140036932  mov     rbp, [rsp+48h+arg_10]
0x140036937  add     rsp, 20h
0x14003693b  pop     r15
0x14003693d  pop     r14
0x14003693f  pop     r13
0x140036941  pop     rdi
0x140036942  pop     rsi
0x140036943  retn
```
