# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400225c8`
- end: `0x14002267e`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
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
0x1400225c8  push    rbx
0x1400225ca  push    rbp
0x1400225cb  push    rsi
0x1400225cc  push    rdi
0x1400225cd  sub     rsp, 28h
0x1400225d1  mov     edi, edx
0x1400225d3  mov     [rsp+48h+arg_0], 0
0x1400225dc  shr     edi, 6
0x1400225df  mov     rbx, rdx
0x1400225e2  mov     rbp, rcx
0x1400225e5  and     edi, 1
0x1400225e8  jz      short loc_140022644
0x1400225ea  mov     rsi, [r8+20h]
0x1400225ee  test    rsi, rsi
0x1400225f1  jz      short loc_140022644
0x1400225f3  mov     rax, [rsi]
0x1400225f6  test    rax, rax
0x1400225f9  jz      short loc_140022644
0x1400225fb  cmp     byte ptr [rax+1Eh], 0
0x1400225ff  jnz     short loc_14002262D
0x140022601  cmp     byte ptr [rax+1Dh], 0
0x140022605  jnz     short loc_14002262D
0x140022607  mov     rcx, [rax]
0x14002260a  mov     rdx, rax
0x14002260d  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140022612  test    edi, edi
0x140022614  jz      short loc_140022621
0x140022616  test    al, 1
0x140022618  jz      short loc_140022621
0x14002261a  mov     edi, 1
0x14002261f  jmp     short loc_140022623
0x140022621  xor     edi, edi
0x140022623  add     rsi, 8
0x140022627  test    edi, edi
0x140022629  jnz     short loc_1400225F3
0x14002262b  jmp     short loc_140022644
0x14002262d  test    edi, edi
0x14002262f  jz      short loc_140022642
0x140022631  cmp     byte ptr [rax+1Fh], 0
0x140022635  jz      short loc_140022642
0x140022637  mov     edi, 1
0x14002263c  add     rsi, 8
0x140022640  jmp     short loc_1400225F3
0x140022642  xor     edi, edi
0x140022644  mov     ecx, ebx
0x140022646  mov     eax, ebx
0x140022648  and     ecx, 0FFFFFFFEh
0x14002264b  and     eax, 1
0x14002264e  or      ecx, edi
0x140022650  mov     edx, ecx
0x140022652  and     edx, 0FFFFFFCFh
0x140022655  cmp     eax, edi
0x140022657  mov     eax, ebx
0x140022659  cmovz   edx, ecx
0x14002265c  btr     edx, 9
0x140022660  mov     dword ptr [rsp+48h+arg_0], edx
0x140022664  lock cmpxchg [rbp+0], edx
0x140022669  jz      short loc_14002266F
0x14002266b  mov     ebx, eax
0x14002266d  jmp     short loc_140022644
0x14002266f  mov     rax, [rsp+48h+arg_0]
0x140022674  add     rsp, 28h
0x140022678  pop     rdi
0x140022679  pop     rsi
0x14002267a  pop     rbp
0x14002267b  pop     rbx
0x14002267c  retn
```
