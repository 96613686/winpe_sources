# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140025948`
- end: `0x1400259fe`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002590c`

## callees

- `0x14002590c`
- `0x140025948`

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
0x140025948  push    rbx
0x14002594a  push    rbp
0x14002594b  push    rsi
0x14002594c  push    rdi
0x14002594d  sub     rsp, 28h
0x140025951  mov     edi, edx
0x140025953  mov     [rsp+48h+arg_0], 0
0x14002595c  shr     edi, 6
0x14002595f  mov     rbx, rdx
0x140025962  mov     rbp, rcx
0x140025965  and     edi, 1
0x140025968  jz      short loc_1400259C4
0x14002596a  mov     rsi, [r8+20h]
0x14002596e  test    rsi, rsi
0x140025971  jz      short loc_1400259C4
0x140025973  mov     rax, [rsi]
0x140025976  test    rax, rax
0x140025979  jz      short loc_1400259C4
0x14002597b  cmp     byte ptr [rax+1Eh], 0
0x14002597f  jnz     short loc_1400259AD
0x140025981  cmp     byte ptr [rax+1Dh], 0
0x140025985  jnz     short loc_1400259AD
0x140025987  mov     rcx, [rax]
0x14002598a  mov     rdx, rax
0x14002598d  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140025992  test    edi, edi
0x140025994  jz      short loc_1400259A1
0x140025996  test    al, 1
0x140025998  jz      short loc_1400259A1
0x14002599a  mov     edi, 1
0x14002599f  jmp     short loc_1400259A3
0x1400259a1  xor     edi, edi
0x1400259a3  add     rsi, 8
0x1400259a7  test    edi, edi
0x1400259a9  jnz     short loc_140025973
0x1400259ab  jmp     short loc_1400259C4
0x1400259ad  test    edi, edi
0x1400259af  jz      short loc_1400259C2
0x1400259b1  cmp     byte ptr [rax+1Fh], 0
0x1400259b5  jz      short loc_1400259C2
0x1400259b7  mov     edi, 1
0x1400259bc  add     rsi, 8
0x1400259c0  jmp     short loc_140025973
0x1400259c2  xor     edi, edi
0x1400259c4  mov     ecx, ebx
0x1400259c6  mov     eax, ebx
0x1400259c8  and     ecx, 0FFFFFFFEh
0x1400259cb  and     eax, 1
0x1400259ce  or      ecx, edi
0x1400259d0  mov     edx, ecx
0x1400259d2  and     edx, 0FFFFFFCFh
0x1400259d5  cmp     eax, edi
0x1400259d7  mov     eax, ebx
0x1400259d9  cmovz   edx, ecx
0x1400259dc  btr     edx, 9
0x1400259e0  mov     dword ptr [rsp+48h+arg_0], edx
0x1400259e4  lock cmpxchg [rbp+0], edx
0x1400259e9  jz      short loc_1400259EF
0x1400259eb  mov     ebx, eax
0x1400259ed  jmp     short loc_1400259C4
0x1400259ef  mov     rax, [rsp+48h+arg_0]
0x1400259f4  add     rsp, 28h
0x1400259f8  pop     rdi
0x1400259f9  pop     rsi
0x1400259fa  pop     rbp
0x1400259fb  pop     rbx
0x1400259fc  retn
```
