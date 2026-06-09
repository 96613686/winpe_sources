# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000fae4`
- end: `0x18000fb9d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f7b8`

## callees

- `0x18000fae4`
- `0x180011e70`
- `0x180011f84`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2E2D11E, (unsigned int)a2, a3, a4);
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
0x18000fae4  push    rbx
0x18000fae6  push    rbp
0x18000fae7  push    rsi
0x18000fae8  push    rdi
0x18000fae9  sub     rsp, 28h
0x18000faed  mov     ecx, 2E2D11Eh; this
0x18000faf2  mov     rbx, rdx
0x18000faf5  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000fafa  mov     edx, eax
0x18000fafc  mov     qword ptr [rbx], 0
0x18000fb03  and     edx, 0FFFFFF3Fh
0x18000fb09  mov     ecx, eax
0x18000fb0b  and     eax, 80h
0x18000fb10  mov     r8d, edx
0x18000fb13  and     r8d, 3
0x18000fb17  mov     ebp, 40h ; '@'
0x18000fb1c  shl     r8d, 2
0x18000fb20  and     ecx, ebp
0x18000fb22  or      r8d, ecx
0x18000fb25  shl     r8d, 2
0x18000fb29  or      r8d, eax
0x18000fb2c  shl     r8d, 3
0x18000fb30  test    edx, edx
0x18000fb32  jz      short loc_18000FB3F
0x18000fb34  xor     eax, eax
0x18000fb36  cmp     edx, 2
0x18000fb39  cmovz   eax, ebp
0x18000fb3c  or      r8d, eax
0x18000fb3f  mov     ecx, 0C00h
0x18000fb44  mov     [rbx], r8d
0x18000fb47  mov     eax, r8d
0x18000fb4a  mov     edi, 1
0x18000fb4f  and     eax, ecx
0x18000fb51  cmp     eax, ecx
0x18000fb53  jnz     short loc_18000FB5A
0x18000fb55  mov     sil, dil
0x18000fb58  jmp     short loc_18000FB64
0x18000fb5a  xor     sil, sil
0x18000fb5d  xor     al, al
0x18000fb5f  test    bpl, r8b
0x18000fb62  jz      short loc_18000FB7D
0x18000fb64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18000fb6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18000fb70  test    sil, sil
0x18000fb73  jz      short loc_18000FB7D
0x18000fb75  test    al, al
0x18000fb77  jnz     short loc_18000FB7D
0x18000fb79  btr     dword ptr [rbx], 0Ah
0x18000fb7d  mov     ecx, [rbx]
0x18000fb7f  test    bpl, cl
0x18000fb82  jz      short loc_18000FB88
0x18000fb84  test    al, al
0x18000fb86  jnz     short loc_18000FB8A
0x18000fb88  xor     edi, edi
0x18000fb8a  and     ecx, 0FFFFFFFEh
0x18000fb8d  mov     rax, rbx
0x18000fb90  or      ecx, edi
0x18000fb92  mov     [rbx], ecx
0x18000fb94  add     rsp, 28h
0x18000fb98  pop     rdi
0x18000fb99  pop     rsi
0x18000fb9a  pop     rbp
0x18000fb9b  pop     rbx
0x18000fb9c  retn
```
