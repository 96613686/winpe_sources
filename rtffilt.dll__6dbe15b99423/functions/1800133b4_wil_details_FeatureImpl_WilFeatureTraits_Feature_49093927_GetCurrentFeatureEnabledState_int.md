# wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800133b4`
- end: `0x180013593`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_49093927@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180011f3c`

## callees

- `0x1800064f4`
- `0x18000a358`
- `0x18000c6b4`
- `0x1800124a4`
- `0x1800133b4`
- `0x180015190`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // eax
  __int16 v7; // cx
  int v8; // edx
  __int16 v9; // cx
  int v10; // edi
  char v11; // si
  char v12; // dl
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v15; // rcx
  unsigned int v16; // r8d
  __int64 v18; // [rsp+60h] [rbp+20h] BYREF
  __int64 v19; // [rsp+68h] [rbp+28h] BYREF

  v18 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(49093927, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 0;
  v7 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  v8 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( v5 )
  {
    if ( v5 == 2 )
      v6 = 64;
    v8 |= v6;
  }
  v9 = v6 | v7;
  *(_DWORD *)a2 = v8;
  v10 = 1;
  if ( (v9 & 0xC00) == 0xC00 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    v12 = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_23;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl) )
    goto LABEL_19;
  v14 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
  {
    v19 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
                       v13,
                       &v19);
    v14 = v19;
  }
  WORD2(v18) = 3;
  LODWORD(v18) = 0;
  wil::details::ReportUsageToService(
    (__int64)&qword_1800236B8,
    0x2F29A04u,
    (v14 >> 10) & 1,
    (v14 >> 11) & 1,
    (__int64)&v18,
    1u,
    0);
  v16 = *(_DWORD *)Feature_53693389__descriptor;
  if ( (*(_DWORD *)Feature_53693389__descriptor & 4) == 0 )
  {
    v19 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53693389>::GetCachedFeatureEnabledState(
                       v15,
                       &v19);
    v16 = v19;
  }
  WORD2(v18) = 3;
  LODWORD(v18) = 0;
  wil::details::ReportUsageToService(
    (__int64)&qword_180023988,
    0x3334BCDu,
    (v16 >> 10) & 1,
    (v16 >> 11) & 1,
    (__int64)&v18,
    1u,
    0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
    v12 = 1;
  else
LABEL_19:
    v12 = 0;
  if ( v11 && !v12 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_23:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v10 = 0;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800133b4  mov     [rsp-18h+arg_10], rbx
0x1800133b9  mov     [rsp-18h+arg_18], rsi
0x1800133be  mov     [rsp-18h+arg_0], rcx
0x1800133c3  push    rbp
0x1800133c4  push    rdi
0x1800133c5  push    r15
0x1800133c7  mov     rbp, rsp
0x1800133ca  sub     rsp, 40h
0x1800133ce  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800133d5  mov     rbx, rdx
0x1800133d8  test    rax, rax
0x1800133db  jz      short loc_1800133F0
0x1800133dd  mov     edx, 3
0x1800133e2  mov     ecx, 2ED1D27h
0x1800133e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133ec  mov     edx, eax
0x1800133ee  jmp     short loc_1800133FE
0x1800133f0  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800133f7  test    rax, rax
0x1800133fa  jnz     short loc_1800133DD
0x1800133fc  xor     edx, edx
0x1800133fe  mov     r8d, edx
0x180013401  mov     qword ptr [rbx], 0
0x180013408  mov     eax, edx
0x18001340a  and     r8d, 0FFFFFF3Fh
0x180013411  and     edx, 80h
0x180013417  mov     ecx, r8d
0x18001341a  and     ecx, 3
0x18001341d  mov     r15d, 40h ; '@'
0x180013423  shl     ecx, 2
0x180013426  and     eax, r15d
0x180013429  or      ecx, eax
0x18001342b  xor     eax, eax
0x18001342d  shl     ecx, 2
0x180013430  or      ecx, edx
0x180013432  shl     ecx, 3
0x180013435  mov     edx, ecx
0x180013437  test    r8d, r8d
0x18001343a  jz      short loc_180013446
0x18001343c  cmp     r8d, 2
0x180013440  cmovz   eax, r15d
0x180013444  or      edx, eax
0x180013446  or      ecx, eax
0x180013448  mov     [rbx], edx
0x18001344a  mov     edx, 0C00h
0x18001344f  mov     eax, ecx
0x180013451  and     eax, edx
0x180013453  mov     edi, 1
0x180013458  cmp     eax, edx
0x18001345a  jnz     short loc_180013461
0x18001345c  mov     sil, dil
0x18001345f  jmp     short loc_18001346F
0x180013461  xor     sil, sil
0x180013464  xor     dl, dl
0x180013466  test    r15b, cl
0x180013469  jz      loc_180013569
0x18001346f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x180013476  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001347b  test    al, al
0x18001347d  jz      loc_18001355A
0x180013483  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18001348a  mov     r8d, [rax]
0x18001348d  test    r8b, 4
0x180013491  jnz     short loc_1800134A6
0x180013493  lea     rdx, [rbp+arg_8]
0x180013497  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x18001349c  mov     rcx, [rax]
0x18001349f  mov     [rbp+arg_8], rcx
0x1800134a3  mov     r8d, ecx
0x1800134a6  xor     eax, eax
0x1800134a8  mov     word ptr [rbp+arg_0+4], 3
0x1800134ae  mov     r9d, r8d
0x1800134b1  mov     [rsp+40h+var_10], eax
0x1800134b5  mov     dword ptr [rbp+arg_0], eax
0x1800134b8  lea     rcx, qword_1800236B8
0x1800134bf  shr     r9d, 0Bh
0x1800134c3  lea     rax, [rbp+arg_0]
0x1800134c7  shr     r8d, 0Ah
0x1800134cb  and     r9d, edi
0x1800134ce  and     r8d, edi
0x1800134d1  mov     [rsp+40h+var_18], edi
0x1800134d5  mov     edx, 2F29A04h
0x1800134da  mov     [rsp+40h+var_20], rax
0x1800134df  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800134e4  mov     rax, cs:Feature_53693389__descriptor
0x1800134eb  mov     r8d, [rax]
0x1800134ee  test    r8b, 4
0x1800134f2  jnz     short loc_180013507
0x1800134f4  lea     rdx, [rbp+arg_8]
0x1800134f8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_53693389@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53693389>::GetCachedFeatureEnabledState(void)
0x1800134fd  mov     rcx, [rax]
0x180013500  mov     [rbp+arg_8], rcx
0x180013504  mov     r8d, ecx
0x180013507  xor     eax, eax
0x180013509  mov     word ptr [rbp+arg_0+4], 3
0x18001350f  mov     r9d, r8d
0x180013512  mov     [rsp+40h+var_10], eax
0x180013516  mov     dword ptr [rbp+arg_0], eax
0x180013519  lea     rcx, qword_180023988
0x180013520  shr     r9d, 0Bh
0x180013524  lea     rax, [rbp+arg_0]
0x180013528  shr     r8d, 0Ah
0x18001352c  and     r9d, edi
0x18001352f  and     r8d, edi
0x180013532  mov     [rsp+40h+var_18], edi
0x180013536  mov     edx, 3334BCDh
0x18001353b  mov     [rsp+40h+var_20], rax
0x180013540  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180013545  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x18001354c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(wil::ReportingKind)
0x180013551  test    al, al
0x180013553  jz      short loc_18001355A
0x180013555  mov     dl, dil
0x180013558  jmp     short loc_18001355C
0x18001355a  xor     dl, dl
0x18001355c  test    sil, sil
0x18001355f  jz      short loc_180013569
0x180013561  test    dl, dl
0x180013563  jnz     short loc_180013569
0x180013565  btr     dword ptr [rbx], 0Ah
0x180013569  mov     eax, [rbx]
0x18001356b  test    r15b, al
0x18001356e  jz      short loc_180013574
0x180013570  test    dl, dl
0x180013572  jnz     short loc_180013576
0x180013574  xor     edi, edi
0x180013576  mov     rsi, [rsp+40h+arg_18]
0x18001357b  and     eax, 0FFFFFFFEh
0x18001357e  or      eax, edi
0x180013580  mov     [rbx], eax
0x180013582  mov     rax, rbx
0x180013585  mov     rbx, [rsp+40h+arg_10]
0x18001358a  add     rsp, 40h
0x18001358e  pop     r15
0x180013590  pop     rdi
0x180013591  pop     rbp
0x180013592  retn
```
