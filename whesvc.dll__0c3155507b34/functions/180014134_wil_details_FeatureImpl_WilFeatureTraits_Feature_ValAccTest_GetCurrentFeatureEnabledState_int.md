# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014134`
- end: `0x1800142d8`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001373c`

## callees

- `0x180012a24`
- `0x18001381c`
- `0x180014134`
- `0x180015608`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // ebx
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  wil::details *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+20h] BYREF
  __int64 v18; // [rsp+68h] [rbp+28h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048231, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
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
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(v11, &v18);
      v13 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180034CF0, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v17, 1, 0);
    v15 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180034D20, 45036792, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x180014134  mov     [rsp-18h+arg_10], rbx
0x180014139  mov     [rsp-18h+arg_0], rcx
0x18001413e  push    rbp
0x18001413f  push    rdi
0x180014140  push    r14
0x180014142  mov     rbp, rsp
0x180014145  sub     rsp, 40h
0x180014149  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180014150  mov     rdi, rdx
0x180014153  test    rax, rax
0x180014156  jz      short loc_18001416B
0x180014158  mov     edx, 3
0x18001415d  mov     ecx, 3667CA7h
0x180014162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014167  mov     edx, eax
0x180014169  jmp     short loc_180014179
0x18001416b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014172  test    rax, rax
0x180014175  jnz     short loc_180014158
0x180014177  xor     edx, edx
0x180014179  mov     r8d, edx
0x18001417c  mov     qword ptr [rdi], 0
0x180014183  and     r8d, 0FFFFFF3Fh
0x18001418a  mov     eax, edx
0x18001418c  and     edx, 80h
0x180014192  mov     ecx, r8d
0x180014195  and     ecx, 3
0x180014198  mov     r14d, 40h ; '@'
0x18001419e  shl     ecx, 2
0x1800141a1  and     eax, r14d
0x1800141a4  or      ecx, eax
0x1800141a6  shl     ecx, 2
0x1800141a9  or      ecx, edx
0x1800141ab  shl     ecx, 3
0x1800141ae  test    r8d, r8d
0x1800141b1  jnz     short loc_1800141BB
0x1800141b3  mov     edx, r14d
0x1800141b6  mov     r8d, r14d
0x1800141b9  jmp     short loc_1800141C8
0x1800141bb  xor     edx, edx
0x1800141bd  cmp     r8d, 2
0x1800141c1  cmovz   edx, r14d
0x1800141c5  mov     r8d, edx
0x1800141c8  mov     eax, ecx
0x1800141ca  mov     ebx, 1
0x1800141cf  or      eax, r8d
0x1800141d2  or      ecx, edx
0x1800141d4  mov     [rdi], eax
0x1800141d6  bt      ecx, 0Ah
0x1800141da  jnb     short loc_1800141E4
0x1800141dc  cmp     ecx, 800h
0x1800141e2  jnb     short loc_1800141EF
0x1800141e4  xor     dl, dl
0x1800141e6  test    r14b, cl
0x1800141e9  jz      loc_1800142B3
0x1800141ef  mov     rax, cs:Feature_ValLabTest__descriptor
0x1800141f6  mov     r8d, [rax]
0x1800141f9  test    r8b, 4
0x1800141fd  jnz     short loc_180014212
0x1800141ff  lea     rdx, [rbp+arg_8]
0x180014203  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180014208  mov     rcx, [rax]
0x18001420b  mov     [rbp+arg_8], rcx
0x18001420f  mov     r8d, ecx
0x180014212  xor     eax, eax
0x180014214  mov     word ptr [rbp+arg_0+4], 3
0x18001421a  mov     r9d, r8d
0x18001421d  mov     [rsp+40h+var_10], eax
0x180014221  mov     dword ptr [rbp+arg_0], eax
0x180014224  lea     rcx, qword_180034CF0
0x18001422b  shr     r9d, 0Bh
0x18001422f  lea     rax, [rbp+arg_0]
0x180014233  shr     r8d, 0Ah
0x180014237  and     r9d, ebx
0x18001423a  and     r8d, ebx
0x18001423d  mov     [rsp+40h+var_18], ebx
0x180014241  mov     edx, 3667CA2h
0x180014246  mov     [rsp+40h+var_20], rax
0x18001424b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180014250  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180014257  mov     r8d, [rax]
0x18001425a  test    r8b, 4
0x18001425e  jnz     short loc_180014273
0x180014260  lea     rdx, [rbp+arg_8]
0x180014264  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x180014269  mov     rcx, [rax]
0x18001426c  mov     [rbp+arg_8], rcx
0x180014270  mov     r8d, ecx
0x180014273  xor     eax, eax
0x180014275  mov     word ptr [rbp+arg_0+4], 3
0x18001427b  mov     r9d, r8d
0x18001427e  mov     [rsp+40h+var_10], eax
0x180014282  mov     dword ptr [rbp+arg_0], eax
0x180014285  lea     rcx, qword_180034D20
0x18001428c  shr     r9d, 0Bh
0x180014290  lea     rax, [rbp+arg_0]
0x180014294  shr     r8d, 0Ah
0x180014298  and     r9d, ebx
0x18001429b  and     r8d, ebx
0x18001429e  mov     [rsp+40h+var_18], ebx
0x1800142a2  mov     edx, 2AF34F8h
0x1800142a7  mov     [rsp+40h+var_20], rax
0x1800142ac  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800142b1  mov     dl, bl
0x1800142b3  mov     eax, [rdi]
0x1800142b5  test    r14b, al
0x1800142b8  jz      short loc_1800142BE
0x1800142ba  test    dl, dl
0x1800142bc  jnz     short loc_1800142C0
0x1800142be  xor     ebx, ebx
0x1800142c0  and     eax, 0FFFFFFFEh
0x1800142c3  or      eax, ebx
0x1800142c5  mov     rbx, [rsp+40h+arg_10]
0x1800142ca  mov     [rdi], eax
0x1800142cc  mov     rax, rdi
0x1800142cf  add     rsp, 40h
0x1800142d3  pop     r14
0x1800142d5  pop     rdi
0x1800142d6  pop     rbp
0x1800142d7  retn
```
