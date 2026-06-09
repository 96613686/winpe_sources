# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008b58`
- end: `0x180008c12`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800086c8`

## callees

- `0x180008b58`
- `0x18000c068`
- `0x18000c480`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x380E04B, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl);
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
0x180008b58  push    rbx
0x180008b5a  push    rbp
0x180008b5b  push    rsi
0x180008b5c  push    rdi
0x180008b5d  sub     rsp, 28h
0x180008b61  mov     ecx, 380E04Bh; this
0x180008b66  mov     rbx, rdx
0x180008b69  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180008b6e  mov     edx, eax
0x180008b70  mov     qword ptr [rbx], 0
0x180008b77  and     edx, 0FFFFFF3Fh
0x180008b7d  mov     ecx, eax
0x180008b7f  and     eax, 80h
0x180008b84  mov     r8d, edx
0x180008b87  and     r8d, 3
0x180008b8b  mov     ebp, 40h ; '@'
0x180008b90  shl     r8d, 2
0x180008b94  and     ecx, ebp
0x180008b96  or      r8d, ecx
0x180008b99  shl     r8d, 2
0x180008b9d  or      r8d, eax
0x180008ba0  shl     r8d, 3
0x180008ba4  test    edx, edx
0x180008ba6  jz      short loc_180008BB3
0x180008ba8  xor     eax, eax
0x180008baa  cmp     edx, 2
0x180008bad  cmovz   eax, ebp
0x180008bb0  or      r8d, eax
0x180008bb3  mov     ecx, 0C00h
0x180008bb8  mov     [rbx], r8d
0x180008bbb  mov     eax, r8d
0x180008bbe  mov     edi, 1
0x180008bc3  and     eax, ecx
0x180008bc5  cmp     eax, ecx
0x180008bc7  jnz     short loc_180008BCE
0x180008bc9  mov     sil, dil
0x180008bcc  jmp     short loc_180008BD8
0x180008bce  xor     sil, sil
0x180008bd1  xor     al, al
0x180008bd3  test    bpl, r8b
0x180008bd6  jz      short loc_180008BF1
0x180008bd8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x180008bdf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(wil::ReportingKind)
0x180008be4  test    sil, sil
0x180008be7  jz      short loc_180008BF1
0x180008be9  test    al, al
0x180008beb  jnz     short loc_180008BF1
0x180008bed  btr     dword ptr [rbx], 0Ah
0x180008bf1  mov     ecx, [rbx]
0x180008bf3  test    bpl, cl
0x180008bf6  jz      short loc_180008BFC
0x180008bf8  test    al, al
0x180008bfa  jnz     short loc_180008BFE
0x180008bfc  xor     edi, edi
0x180008bfe  and     ecx, 0FFFFFFFEh
0x180008c01  mov     rax, rbx
0x180008c04  or      ecx, edi
0x180008c06  mov     [rbx], ecx
0x180008c08  add     rsp, 28h
0x180008c0c  pop     rdi
0x180008c0d  pop     rsi
0x180008c0e  pop     rbp
0x180008c0f  pop     rbx
0x180008c10  retn
```
