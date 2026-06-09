# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400279c8`
- end: `0x140027a7e`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
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
0x1400279c8  push    rbx
0x1400279ca  push    rbp
0x1400279cb  push    rsi
0x1400279cc  push    rdi
0x1400279cd  sub     rsp, 28h
0x1400279d1  mov     edi, edx
0x1400279d3  mov     [rsp+48h+arg_0], 0
0x1400279dc  shr     edi, 6
0x1400279df  mov     rbx, rdx
0x1400279e2  mov     rbp, rcx
0x1400279e5  and     edi, 1
0x1400279e8  jz      short loc_140027A44
0x1400279ea  mov     rsi, [r8+20h]
0x1400279ee  test    rsi, rsi
0x1400279f1  jz      short loc_140027A44
0x1400279f3  mov     rax, [rsi]
0x1400279f6  test    rax, rax
0x1400279f9  jz      short loc_140027A44
0x1400279fb  cmp     byte ptr [rax+1Eh], 0
0x1400279ff  jnz     short loc_140027A2D
0x140027a01  cmp     byte ptr [rax+1Dh], 0
0x140027a05  jnz     short loc_140027A2D
0x140027a07  mov     rcx, [rax]
0x140027a0a  mov     rdx, rax
0x140027a0d  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140027a12  test    edi, edi
0x140027a14  jz      short loc_140027A21
0x140027a16  test    al, 1
0x140027a18  jz      short loc_140027A21
0x140027a1a  mov     edi, 1
0x140027a1f  jmp     short loc_140027A23
0x140027a21  xor     edi, edi
0x140027a23  add     rsi, 8
0x140027a27  test    edi, edi
0x140027a29  jnz     short loc_1400279F3
0x140027a2b  jmp     short loc_140027A44
0x140027a2d  test    edi, edi
0x140027a2f  jz      short loc_140027A42
0x140027a31  cmp     byte ptr [rax+1Fh], 0
0x140027a35  jz      short loc_140027A42
0x140027a37  mov     edi, 1
0x140027a3c  add     rsi, 8
0x140027a40  jmp     short loc_1400279F3
0x140027a42  xor     edi, edi
0x140027a44  mov     ecx, ebx
0x140027a46  mov     eax, ebx
0x140027a48  and     ecx, 0FFFFFFFEh
0x140027a4b  and     eax, 1
0x140027a4e  or      ecx, edi
0x140027a50  mov     edx, ecx
0x140027a52  and     edx, 0FFFFFFCFh
0x140027a55  cmp     eax, edi
0x140027a57  mov     eax, ebx
0x140027a59  cmovz   edx, ecx
0x140027a5c  btr     edx, 9
0x140027a60  mov     dword ptr [rsp+48h+arg_0], edx
0x140027a64  lock cmpxchg [rbp+0], edx
0x140027a69  jz      short loc_140027A6F
0x140027a6b  mov     ebx, eax
0x140027a6d  jmp     short loc_140027A44
0x140027a6f  mov     rax, [rsp+48h+arg_0]
0x140027a74  add     rsp, 28h
0x140027a78  pop     rdi
0x140027a79  pop     rsi
0x140027a7a  pop     rbp
0x140027a7b  pop     rbx
0x140027a7c  retn
```
