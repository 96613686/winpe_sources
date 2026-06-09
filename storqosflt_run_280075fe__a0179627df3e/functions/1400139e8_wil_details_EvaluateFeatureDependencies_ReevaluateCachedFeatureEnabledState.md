# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400139e8`
- end: `0x140013a9e`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400139ac`

## callees

- `0x1400139ac`
- `0x1400139e8`

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
0x1400139e8  push    rbx
0x1400139ea  push    rbp
0x1400139eb  push    rsi
0x1400139ec  push    rdi
0x1400139ed  sub     rsp, 28h
0x1400139f1  mov     edi, edx
0x1400139f3  mov     [rsp+48h+arg_0], 0
0x1400139fc  shr     edi, 6
0x1400139ff  mov     rbx, rdx
0x140013a02  mov     rbp, rcx
0x140013a05  and     edi, 1
0x140013a08  jz      short loc_140013A64
0x140013a0a  mov     rsi, [r8+20h]
0x140013a0e  test    rsi, rsi
0x140013a11  jz      short loc_140013A64
0x140013a13  mov     rax, [rsi]
0x140013a16  test    rax, rax
0x140013a19  jz      short loc_140013A64
0x140013a1b  cmp     byte ptr [rax+1Eh], 0
0x140013a1f  jnz     short loc_140013A4D
0x140013a21  cmp     byte ptr [rax+1Dh], 0
0x140013a25  jnz     short loc_140013A4D
0x140013a27  mov     rcx, [rax]
0x140013a2a  mov     rdx, rax
0x140013a2d  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140013a32  test    edi, edi
0x140013a34  jz      short loc_140013A41
0x140013a36  test    al, 1
0x140013a38  jz      short loc_140013A41
0x140013a3a  mov     edi, 1
0x140013a3f  jmp     short loc_140013A43
0x140013a41  xor     edi, edi
0x140013a43  add     rsi, 8
0x140013a47  test    edi, edi
0x140013a49  jnz     short loc_140013A13
0x140013a4b  jmp     short loc_140013A64
0x140013a4d  test    edi, edi
0x140013a4f  jz      short loc_140013A62
0x140013a51  cmp     byte ptr [rax+1Fh], 0
0x140013a55  jz      short loc_140013A62
0x140013a57  mov     edi, 1
0x140013a5c  add     rsi, 8
0x140013a60  jmp     short loc_140013A13
0x140013a62  xor     edi, edi
0x140013a64  mov     ecx, ebx
0x140013a66  mov     eax, ebx
0x140013a68  and     ecx, 0FFFFFFFEh
0x140013a6b  and     eax, 1
0x140013a6e  or      ecx, edi
0x140013a70  mov     edx, ecx
0x140013a72  and     edx, 0FFFFFFCFh
0x140013a75  cmp     eax, edi
0x140013a77  mov     eax, ebx
0x140013a79  cmovz   edx, ecx
0x140013a7c  btr     edx, 9
0x140013a80  mov     dword ptr [rsp+48h+arg_0], edx
0x140013a84  lock cmpxchg [rbp+0], edx
0x140013a89  jz      short loc_140013A8F
0x140013a8b  mov     ebx, eax
0x140013a8d  jmp     short loc_140013A64
0x140013a8f  mov     rax, [rsp+48h+arg_0]
0x140013a94  add     rsp, 28h
0x140013a98  pop     rdi
0x140013a99  pop     rsi
0x140013a9a  pop     rbp
0x140013a9b  pop     rbx
0x140013a9c  retn
```
