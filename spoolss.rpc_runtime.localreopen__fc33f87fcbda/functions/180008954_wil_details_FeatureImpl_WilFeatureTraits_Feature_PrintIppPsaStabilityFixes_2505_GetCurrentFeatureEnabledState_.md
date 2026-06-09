# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008954`
- end: `0x180008a17`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800082f0`

## callees

- `0x180008954`
- `0x18000a860`
- `0x18000c068`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37832CE, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_UxLabTest>::GetImpl'::`2'::impl);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180008954  mov     [rsp+arg_0], rbx
0x180008959  mov     [rsp+arg_8], rsi
0x18000895e  push    rdi
0x18000895f  sub     rsp, 20h
0x180008963  mov     ecx, 37832CEh; this
0x180008968  mov     rbx, rdx
0x18000896b  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180008970  mov     edx, eax
0x180008972  mov     qword ptr [rbx], 0
0x180008979  and     edx, 0FFFFFF3Fh
0x18000897f  mov     ecx, eax
0x180008981  and     eax, 80h
0x180008986  mov     r8d, edx
0x180008989  and     r8d, 3
0x18000898d  mov     esi, 40h ; '@'
0x180008992  shl     r8d, 2
0x180008996  and     ecx, esi
0x180008998  or      r8d, ecx
0x18000899b  shl     r8d, 2
0x18000899f  or      r8d, eax
0x1800089a2  shl     r8d, 3
0x1800089a6  test    edx, edx
0x1800089a8  jnz     short loc_1800089B0
0x1800089aa  mov     ecx, esi
0x1800089ac  mov     edx, esi
0x1800089ae  jmp     short loc_1800089BA
0x1800089b0  xor     ecx, ecx
0x1800089b2  cmp     edx, 2
0x1800089b5  cmovz   ecx, esi
0x1800089b8  mov     edx, ecx
0x1800089ba  mov     eax, r8d
0x1800089bd  mov     edi, 1
0x1800089c2  or      eax, edx
0x1800089c4  or      r8d, ecx
0x1800089c7  mov     [rbx], eax
0x1800089c9  bt      r8d, 0Ah
0x1800089ce  jnb     short loc_1800089D9
0x1800089d0  cmp     r8d, 800h
0x1800089d7  jnb     short loc_1800089E0
0x1800089d9  xor     cl, cl
0x1800089db  test    sil, r8b
0x1800089de  jz      short loc_1800089EF
0x1800089e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest> `wil::Feature<__WilFeatureTraits_Feature_UxLabTest>::GetImpl(void)'::`2'::impl
0x1800089e7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800089ec  mov     cl, dil
0x1800089ef  mov     eax, [rbx]
0x1800089f1  test    sil, al
0x1800089f4  jz      short loc_1800089FA
0x1800089f6  test    cl, cl
0x1800089f8  jnz     short loc_1800089FC
0x1800089fa  xor     edi, edi
0x1800089fc  mov     rsi, [rsp+28h+arg_8]
0x180008a01  and     eax, 0FFFFFFFEh
0x180008a04  or      eax, edi
0x180008a06  mov     [rbx], eax
0x180008a08  mov     rax, rbx
0x180008a0b  mov     rbx, [rsp+28h+arg_0]
0x180008a10  add     rsp, 20h
0x180008a14  pop     rdi
0x180008a15  retn
```
