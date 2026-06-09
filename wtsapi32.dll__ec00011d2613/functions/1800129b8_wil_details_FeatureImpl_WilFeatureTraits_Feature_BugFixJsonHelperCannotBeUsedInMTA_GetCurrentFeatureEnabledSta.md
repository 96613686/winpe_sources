# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800129b8`
- end: `0x180012a71`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800128d0`

## callees

- `0x180011e70`
- `0x180011f84`
- `0x1800129b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x391F742, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
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
0x1800129b8  push    rbx
0x1800129ba  push    rbp
0x1800129bb  push    rsi
0x1800129bc  push    rdi
0x1800129bd  sub     rsp, 28h
0x1800129c1  mov     ecx, 391F742h; this
0x1800129c6  mov     rbx, rdx
0x1800129c9  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800129ce  mov     edx, eax
0x1800129d0  mov     qword ptr [rbx], 0
0x1800129d7  and     edx, 0FFFFFF3Fh
0x1800129dd  mov     ecx, eax
0x1800129df  and     eax, 80h
0x1800129e4  mov     r8d, edx
0x1800129e7  and     r8d, 3
0x1800129eb  mov     ebp, 40h ; '@'
0x1800129f0  shl     r8d, 2
0x1800129f4  and     ecx, ebp
0x1800129f6  or      r8d, ecx
0x1800129f9  shl     r8d, 2
0x1800129fd  or      r8d, eax
0x180012a00  shl     r8d, 3
0x180012a04  test    edx, edx
0x180012a06  jz      short loc_180012A13
0x180012a08  xor     eax, eax
0x180012a0a  cmp     edx, 2
0x180012a0d  cmovz   eax, ebp
0x180012a10  or      r8d, eax
0x180012a13  mov     ecx, 0C00h
0x180012a18  mov     [rbx], r8d
0x180012a1b  mov     eax, r8d
0x180012a1e  mov     edi, 1
0x180012a23  and     eax, ecx
0x180012a25  cmp     eax, ecx
0x180012a27  jnz     short loc_180012A2E
0x180012a29  mov     sil, dil
0x180012a2c  jmp     short loc_180012A38
0x180012a2e  xor     sil, sil
0x180012a31  xor     al, al
0x180012a33  test    bpl, r8b
0x180012a36  jz      short loc_180012A51
0x180012a38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x180012a3f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x180012a44  test    sil, sil
0x180012a47  jz      short loc_180012A51
0x180012a49  test    al, al
0x180012a4b  jnz     short loc_180012A51
0x180012a4d  btr     dword ptr [rbx], 0Ah
0x180012a51  mov     ecx, [rbx]
0x180012a53  test    bpl, cl
0x180012a56  jz      short loc_180012A5C
0x180012a58  test    al, al
0x180012a5a  jnz     short loc_180012A5E
0x180012a5c  xor     edi, edi
0x180012a5e  and     ecx, 0FFFFFFFEh
0x180012a61  mov     rax, rbx
0x180012a64  or      ecx, edi
0x180012a66  mov     [rbx], ecx
0x180012a68  add     rsp, 28h
0x180012a6c  pop     rdi
0x180012a6d  pop     rsi
0x180012a6e  pop     rbp
0x180012a6f  pop     rbx
0x180012a70  retn
```
