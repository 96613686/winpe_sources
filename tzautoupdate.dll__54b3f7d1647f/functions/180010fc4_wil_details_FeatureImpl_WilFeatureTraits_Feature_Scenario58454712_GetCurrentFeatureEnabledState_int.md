# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180010fc4`
- end: `0x180011086`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `194`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010e04`

## callees

- `0x180009b84`
- `0x180010fc4`
- `0x180011da8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37BF2B8, (unsigned int)a2, a3, a4);
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl'::`2'::impl);
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
0x180010fc4  mov     [rsp+arg_0], rbx
0x180010fc9  mov     [rsp+arg_8], rsi
0x180010fce  push    rdi
0x180010fcf  sub     rsp, 20h
0x180010fd3  mov     ecx, 37BF2B8h; this
0x180010fd8  mov     rbx, rdx
0x180010fdb  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180010fe0  mov     edx, eax
0x180010fe2  mov     qword ptr [rbx], 0
0x180010fe9  and     edx, 0FFFFFF3Fh
0x180010fef  mov     ecx, eax
0x180010ff1  and     eax, 80h
0x180010ff6  mov     r8d, edx
0x180010ff9  and     r8d, 3
0x180010ffd  mov     esi, 40h ; '@'
0x180011002  shl     r8d, 2
0x180011006  and     ecx, esi
0x180011008  or      r8d, ecx
0x18001100b  shl     r8d, 2
0x18001100f  or      r8d, eax
0x180011012  shl     r8d, 3
0x180011016  test    edx, edx
0x180011018  jnz     short loc_180011020
0x18001101a  mov     ecx, esi
0x18001101c  mov     edx, esi
0x18001101e  jmp     short loc_18001102A
0x180011020  xor     ecx, ecx
0x180011022  cmp     edx, 2
0x180011025  cmovz   ecx, esi
0x180011028  mov     edx, ecx
0x18001102a  mov     eax, r8d
0x18001102d  mov     edi, 1
0x180011032  or      eax, edx
0x180011034  or      r8d, ecx
0x180011037  mov     [rbx], eax
0x180011039  bt      r8d, 0Ah
0x18001103e  jnb     short loc_180011049
0x180011040  cmp     r8d, 800h
0x180011047  jnb     short loc_180011050
0x180011049  xor     cl, cl
0x18001104b  test    sil, r8b
0x18001104e  jz      short loc_18001105F
0x180011050  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x180011057  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001105c  mov     cl, dil
0x18001105f  mov     eax, [rbx]
0x180011061  test    sil, al
0x180011064  jz      short loc_18001106A
0x180011066  test    cl, cl
0x180011068  jnz     short loc_18001106C
0x18001106a  xor     edi, edi
0x18001106c  mov     rsi, [rsp+28h+arg_8]
0x180011071  and     eax, 0FFFFFFFEh
0x180011074  or      eax, edi
0x180011076  mov     [rbx], eax
0x180011078  mov     rax, rbx
0x18001107b  mov     rbx, [rsp+28h+arg_0]
0x180011080  add     rsp, 20h
0x180011084  pop     rdi
0x180011085  retn
```
