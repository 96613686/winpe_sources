# wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000a02c`
- end: `0x14000a143`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a14c`

## callees

- `0x140009f10`
- `0x14000a02c`
- `0x1400206e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // eax
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // eax
  int v8; // edx
  unsigned int v9; // eax
  bool v10; // dl
  int v11; // esi
  char v12; // bp
  bool v13; // al
  _QWORD *result; // rax

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      *a2 = 0;
      v6 = 0;
      goto LABEL_8;
    }
  }
  v4 = v2(57048237, 64);
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) == 0 )
  {
LABEL_8:
    v7 = 0;
    v8 = v6;
    goto LABEL_9;
  }
  v7 = 0;
  if ( v5 == 2 )
    v7 = 64;
  v8 = v6 | v7;
LABEL_9:
  *(_DWORD *)a2 = v8;
  v9 = v6 | v7;
  v10 = 0;
  v11 = 1;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_16;
  }
  v13 = wil::Wil_Staging_AreExternalFeatureDependenciesEnabled((wil *)0x3667CAD);
  v10 = v13;
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v10 )
    v11 = 0;
  result = a2;
  *(_DWORD *)a2 = v11 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x14000a02c  mov     [rsp+arg_0], rbx
0x14000a031  mov     [rsp+arg_8], rbp
0x14000a036  mov     [rsp+arg_10], rsi
0x14000a03b  push    rdi
0x14000a03c  sub     rsp, 20h
0x14000a040  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000a047  mov     rbx, rdx
0x14000a04a  test    rax, rax
0x14000a04d  jnz     short loc_14000A05B
0x14000a04f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000a056  test    rax, rax
0x14000a059  jz      short loc_14000A0AE
0x14000a05b  mov     edi, 40h ; '@'
0x14000a060  mov     ecx, 3667CADh
0x14000a065  mov     edx, edi
0x14000a067  call    _guard_dispatch_icall
0x14000a06c  mov     r8d, eax
0x14000a06f  mov     qword ptr [rbx], 0
0x14000a076  and     r8d, 0FFFFFF3Fh
0x14000a07d  mov     edx, eax
0x14000a07f  and     eax, edi
0x14000a081  and     edx, 80h
0x14000a087  mov     ecx, r8d
0x14000a08a  and     ecx, 3
0x14000a08d  shl     ecx, 2
0x14000a090  or      ecx, eax
0x14000a092  shl     ecx, 2
0x14000a095  or      ecx, edx
0x14000a097  shl     ecx, 3
0x14000a09a  test    r8d, r8d
0x14000a09d  jz      short loc_14000A0D5
0x14000a09f  xor     eax, eax
0x14000a0a1  cmp     r8d, 2
0x14000a0a5  cmovz   eax, edi
0x14000a0a8  mov     edx, eax
0x14000a0aa  or      edx, ecx
0x14000a0ac  jmp     short loc_14000A0D9
0x14000a0ae  xor     ecx, ecx
0x14000a0b0  mov     qword ptr [rdx], 0
0x14000a0b7  xor     eax, eax
0x14000a0b9  and     ecx, 3
0x14000a0bc  shl     ecx, 2
0x14000a0bf  lea     edi, [rax+40h]
0x14000a0c2  and     eax, edi
0x14000a0c4  or      ecx, eax
0x14000a0c6  xor     eax, eax
0x14000a0c8  and     eax, 80h
0x14000a0cd  shl     ecx, 2
0x14000a0d0  or      ecx, eax
0x14000a0d2  shl     ecx, 3
0x14000a0d5  xor     eax, eax
0x14000a0d7  mov     edx, ecx
0x14000a0d9  mov     [rbx], edx
0x14000a0db  or      eax, ecx
0x14000a0dd  xor     dl, dl; unsigned int
0x14000a0df  mov     esi, 1
0x14000a0e4  bt      eax, 0Ah
0x14000a0e8  jnb     short loc_14000A0F6
0x14000a0ea  cmp     eax, 800h
0x14000a0ef  jb      short loc_14000A0F6
0x14000a0f1  mov     bpl, sil
0x14000a0f4  jmp     short loc_14000A0FE
0x14000a0f6  xor     bpl, bpl
0x14000a0f9  test    dil, al
0x14000a0fc  jz      short loc_14000A117
0x14000a0fe  mov     ecx, 3667CADh; this
0x14000a103  call    ?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z; wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)
0x14000a108  mov     dl, al
0x14000a10a  test    bpl, bpl
0x14000a10d  jz      short loc_14000A117
0x14000a10f  test    al, al
0x14000a111  jnz     short loc_14000A117
0x14000a113  btr     dword ptr [rbx], 0Ah
0x14000a117  mov     ecx, [rbx]
0x14000a119  test    dil, cl
0x14000a11c  jz      short loc_14000A122
0x14000a11e  test    dl, dl
0x14000a120  jnz     short loc_14000A124
0x14000a122  xor     esi, esi
0x14000a124  mov     rbp, [rsp+28h+arg_8]
0x14000a129  and     ecx, 0FFFFFFFEh
0x14000a12c  or      ecx, esi
0x14000a12e  mov     rax, rbx
0x14000a131  mov     rsi, [rsp+28h+arg_10]
0x14000a136  mov     [rbx], ecx
0x14000a138  mov     rbx, [rsp+28h+arg_0]
0x14000a13d  add     rsp, 20h
0x14000a141  pop     rdi
0x14000a142  retn
```
