# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008488`
- end: `0x18000855b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008118`

## callees

- `0x180008488`
- `0x180009f60`
- `0x18000b744`
- `0x18000bb04`

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
  int v9; // r8d
  int v10; // ecx
  __int16 v11; // r8
  int v12; // edi
  char v13; // si
  bool v14; // cl
  char IsEnabled; // al

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x380E04B, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v8 = 0;
  v9 = 8 * v7;
  if ( v6 )
  {
    if ( v6 == 2 )
      v8 = 64;
    v10 = v9 | v8;
  }
  else
  {
    v10 = v9;
  }
  v11 = v8 | v9;
  *(_DWORD *)a2 = v10;
  v12 = 1;
  if ( (v11 & 0xC00) == 0xC00 )
  {
    v13 = 1;
  }
  else
  {
    v13 = 0;
    v14 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_12;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl'::`2'::impl);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl);
  v14 = IsEnabled != 0;
  if ( v13 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v14 )
    v12 = 0;
  *(_DWORD *)a2 = v12 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180008488  push    rbx
0x18000848a  push    rbp
0x18000848b  push    rsi
0x18000848c  push    rdi
0x18000848d  sub     rsp, 28h
0x180008491  mov     ecx, 380E04Bh; this
0x180008496  mov     rbx, rdx
0x180008499  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000849e  mov     edx, eax
0x1800084a0  mov     qword ptr [rbx], 0
0x1800084a7  mov     ecx, eax
0x1800084a9  and     edx, 0FFFFFF3Fh
0x1800084af  and     eax, 80h
0x1800084b4  mov     r8d, edx
0x1800084b7  and     r8d, 3
0x1800084bb  mov     ebp, 40h ; '@'
0x1800084c0  shl     r8d, 2
0x1800084c4  and     ecx, ebp
0x1800084c6  or      r8d, ecx
0x1800084c9  shl     r8d, 2
0x1800084cd  or      r8d, eax
0x1800084d0  xor     eax, eax
0x1800084d2  shl     r8d, 3
0x1800084d6  test    edx, edx
0x1800084d8  jnz     short loc_1800084DF
0x1800084da  mov     ecx, r8d
0x1800084dd  jmp     short loc_1800084EA
0x1800084df  cmp     edx, 2
0x1800084e2  cmovz   eax, ebp
0x1800084e5  mov     ecx, eax
0x1800084e7  or      ecx, r8d
0x1800084ea  or      r8d, eax
0x1800084ed  mov     [rbx], ecx
0x1800084ef  mov     ecx, 0C00h
0x1800084f4  mov     eax, r8d
0x1800084f7  and     eax, ecx
0x1800084f9  mov     edi, 1
0x1800084fe  cmp     eax, ecx
0x180008500  jnz     short loc_180008507
0x180008502  mov     sil, dil
0x180008505  jmp     short loc_180008511
0x180008507  xor     sil, sil
0x18000850a  xor     cl, cl
0x18000850c  test    bpl, r8b
0x18000850f  jz      short loc_18000853B
0x180008511  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api> `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl(void)'::`2'::impl
0x180008518  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000851d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x180008524  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(wil::ReportingKind)
0x180008529  test    al, al
0x18000852b  setnz   cl
0x18000852e  test    sil, sil
0x180008531  jz      short loc_18000853B
0x180008533  test    cl, cl
0x180008535  jnz     short loc_18000853B
0x180008537  btr     dword ptr [rbx], 0Ah
0x18000853b  mov     eax, [rbx]
0x18000853d  test    bpl, al
0x180008540  jz      short loc_180008546
0x180008542  test    cl, cl
0x180008544  jnz     short loc_180008548
0x180008546  xor     edi, edi
0x180008548  and     eax, 0FFFFFFFEh
0x18000854b  or      eax, edi
0x18000854d  mov     [rbx], eax
0x18000854f  mov     rax, rbx
0x180008552  add     rsp, 28h
0x180008556  pop     rdi
0x180008557  pop     rsi
0x180008558  pop     rbp
0x180008559  pop     rbx
0x18000855a  retn
```
