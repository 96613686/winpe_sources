# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140022c1c`
- end: `0x140022cd2`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022554`

## callees

- `0x140022554`
- `0x140022c1c`

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
0x140022c1c  push    rbx
0x140022c1e  push    rbp
0x140022c1f  push    rsi
0x140022c20  push    rdi
0x140022c21  sub     rsp, 28h
0x140022c25  mov     edi, edx
0x140022c27  mov     [rsp+48h+arg_0], 0
0x140022c30  shr     edi, 6
0x140022c33  mov     rbx, rdx
0x140022c36  mov     rbp, rcx
0x140022c39  and     edi, 1
0x140022c3c  jz      short loc_140022C98
0x140022c3e  mov     rsi, [r8+20h]
0x140022c42  test    rsi, rsi
0x140022c45  jz      short loc_140022C98
0x140022c47  mov     rax, [rsi]
0x140022c4a  test    rax, rax
0x140022c4d  jz      short loc_140022C98
0x140022c4f  cmp     byte ptr [rax+1Eh], 0
0x140022c53  jnz     short loc_140022C81
0x140022c55  cmp     byte ptr [rax+1Dh], 0
0x140022c59  jnz     short loc_140022C81
0x140022c5b  mov     rcx, [rax]
0x140022c5e  mov     rdx, rax
0x140022c61  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140022c66  test    edi, edi
0x140022c68  jz      short loc_140022C75
0x140022c6a  test    al, 1
0x140022c6c  jz      short loc_140022C75
0x140022c6e  mov     edi, 1
0x140022c73  jmp     short loc_140022C77
0x140022c75  xor     edi, edi
0x140022c77  add     rsi, 8
0x140022c7b  test    edi, edi
0x140022c7d  jnz     short loc_140022C47
0x140022c7f  jmp     short loc_140022C98
0x140022c81  test    edi, edi
0x140022c83  jz      short loc_140022C96
0x140022c85  cmp     byte ptr [rax+1Fh], 0
0x140022c89  jz      short loc_140022C96
0x140022c8b  mov     edi, 1
0x140022c90  add     rsi, 8
0x140022c94  jmp     short loc_140022C47
0x140022c96  xor     edi, edi
0x140022c98  mov     ecx, ebx
0x140022c9a  mov     eax, ebx
0x140022c9c  and     ecx, 0FFFFFFFEh
0x140022c9f  and     eax, 1
0x140022ca2  or      ecx, edi
0x140022ca4  mov     edx, ecx
0x140022ca6  and     edx, 0FFFFFFCFh
0x140022ca9  cmp     eax, edi
0x140022cab  mov     eax, ebx
0x140022cad  cmovz   edx, ecx
0x140022cb0  btr     edx, 9
0x140022cb4  mov     dword ptr [rsp+48h+arg_0], edx
0x140022cb8  lock cmpxchg [rbp+0], edx
0x140022cbd  jz      short loc_140022CC3
0x140022cbf  mov     ebx, eax
0x140022cc1  jmp     short loc_140022C98
0x140022cc3  mov     rax, [rsp+48h+arg_0]
0x140022cc8  add     rsp, 28h
0x140022ccc  pop     rdi
0x140022ccd  pop     rsi
0x140022cce  pop     rbp
0x140022ccf  pop     rbx
0x140022cd0  retn
```
