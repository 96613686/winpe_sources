# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008a20`
- end: `0x180008ada`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008438`

## callees

- `0x180008a20`
- `0x18000c068`
- `0x18000c444`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // edi
  char v10; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3710FA3, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
    v7 |= v8;
  }
  *(_DWORD *)a2 = v7;
  v9 = 1;
  if ( (v7 & 0xC00) == 0xC00 )
  {
    v10 = 1;
  }
  else
  {
    v10 = 0;
    IsEnabled = 0;
    if ( (v7 & 0x40) == 0 )
      goto LABEL_11;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl'::`2'::impl);
  if ( v10 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_11:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v9 = 0;
  result = a2;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x180008a20  push    rbx
0x180008a22  push    rbp
0x180008a23  push    rsi
0x180008a24  push    rdi
0x180008a25  sub     rsp, 28h
0x180008a29  mov     ecx, 3710FA3h; this
0x180008a2e  mov     rbx, rdx
0x180008a31  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180008a36  mov     edx, eax
0x180008a38  mov     qword ptr [rbx], 0
0x180008a3f  and     edx, 0FFFFFF3Fh
0x180008a45  mov     ecx, eax
0x180008a47  and     eax, 80h
0x180008a4c  mov     r8d, edx
0x180008a4f  and     r8d, 3
0x180008a53  mov     ebp, 40h ; '@'
0x180008a58  shl     r8d, 2
0x180008a5c  and     ecx, ebp
0x180008a5e  or      r8d, ecx
0x180008a61  shl     r8d, 2
0x180008a65  or      r8d, eax
0x180008a68  shl     r8d, 3
0x180008a6c  test    edx, edx
0x180008a6e  jz      short loc_180008A7B
0x180008a70  xor     eax, eax
0x180008a72  cmp     edx, 2
0x180008a75  cmovz   eax, ebp
0x180008a78  or      r8d, eax
0x180008a7b  mov     ecx, 0C00h
0x180008a80  mov     [rbx], r8d
0x180008a83  mov     eax, r8d
0x180008a86  mov     edi, 1
0x180008a8b  and     eax, ecx
0x180008a8d  cmp     eax, ecx
0x180008a8f  jnz     short loc_180008A96
0x180008a91  mov     sil, dil
0x180008a94  jmp     short loc_180008AA0
0x180008a96  xor     sil, sil
0x180008a99  xor     al, al
0x180008a9b  test    bpl, r8b
0x180008a9e  jz      short loc_180008AB9
0x180008aa0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505> `wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl(void)'::`2'::impl
0x180008aa7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled(wil::ReportingKind)
0x180008aac  test    sil, sil
0x180008aaf  jz      short loc_180008AB9
0x180008ab1  test    al, al
0x180008ab3  jnz     short loc_180008AB9
0x180008ab5  btr     dword ptr [rbx], 0Ah
0x180008ab9  mov     ecx, [rbx]
0x180008abb  test    bpl, cl
0x180008abe  jz      short loc_180008AC4
0x180008ac0  test    al, al
0x180008ac2  jnz     short loc_180008AC6
0x180008ac4  xor     edi, edi
0x180008ac6  and     ecx, 0FFFFFFFEh
0x180008ac9  mov     rax, rbx
0x180008acc  or      ecx, edi
0x180008ace  mov     [rbx], ecx
0x180008ad0  add     rsp, 28h
0x180008ad4  pop     rdi
0x180008ad5  pop     rsi
0x180008ad6  pop     rbp
0x180008ad7  pop     rbx
0x180008ad8  retn
```
