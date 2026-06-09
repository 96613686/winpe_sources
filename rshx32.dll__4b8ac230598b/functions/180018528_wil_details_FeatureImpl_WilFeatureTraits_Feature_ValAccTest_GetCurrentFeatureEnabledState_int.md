# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180018528`
- end: `0x1800186cc`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180017b98`

## callees

- `0x180016e80`
- `0x180017c78`
- `0x180018528`
- `0x180018ac8`
- `0x18001e010`

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
    wil::details::ReportUsageToService(&qword_180029518, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v17, 1, 0);
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
    wil::details::ReportUsageToService(&qword_1800295A8, 45036792, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x180018528  mov     [rsp-18h+arg_10], rbx
0x18001852d  mov     [rsp-18h+arg_0], rcx
0x180018532  push    rbp
0x180018533  push    rdi
0x180018534  push    r14
0x180018536  mov     rbp, rsp
0x180018539  sub     rsp, 40h
0x18001853d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180018544  mov     rdi, rdx
0x180018547  test    rax, rax
0x18001854a  jz      short loc_18001855F
0x18001854c  mov     edx, 3
0x180018551  mov     ecx, 3667CA7h
0x180018556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001855b  mov     edx, eax
0x18001855d  jmp     short loc_18001856D
0x18001855f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180018566  test    rax, rax
0x180018569  jnz     short loc_18001854C
0x18001856b  xor     edx, edx
0x18001856d  mov     r8d, edx
0x180018570  mov     qword ptr [rdi], 0
0x180018577  and     r8d, 0FFFFFF3Fh
0x18001857e  mov     eax, edx
0x180018580  and     edx, 80h
0x180018586  mov     ecx, r8d
0x180018589  and     ecx, 3
0x18001858c  mov     r14d, 40h ; '@'
0x180018592  shl     ecx, 2
0x180018595  and     eax, r14d
0x180018598  or      ecx, eax
0x18001859a  shl     ecx, 2
0x18001859d  or      ecx, edx
0x18001859f  shl     ecx, 3
0x1800185a2  test    r8d, r8d
0x1800185a5  jnz     short loc_1800185AF
0x1800185a7  mov     edx, r14d
0x1800185aa  mov     r8d, r14d
0x1800185ad  jmp     short loc_1800185BC
0x1800185af  xor     edx, edx
0x1800185b1  cmp     r8d, 2
0x1800185b5  cmovz   edx, r14d
0x1800185b9  mov     r8d, edx
0x1800185bc  mov     eax, ecx
0x1800185be  mov     ebx, 1
0x1800185c3  or      eax, r8d
0x1800185c6  or      ecx, edx
0x1800185c8  mov     [rdi], eax
0x1800185ca  bt      ecx, 0Ah
0x1800185ce  jnb     short loc_1800185D8
0x1800185d0  cmp     ecx, 800h
0x1800185d6  jnb     short loc_1800185E3
0x1800185d8  xor     dl, dl
0x1800185da  test    r14b, cl
0x1800185dd  jz      loc_1800186A7
0x1800185e3  mov     rax, cs:Feature_ValLabTest__descriptor
0x1800185ea  mov     r8d, [rax]
0x1800185ed  test    r8b, 4
0x1800185f1  jnz     short loc_180018606
0x1800185f3  lea     rdx, [rbp+arg_8]
0x1800185f7  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x1800185fc  mov     rcx, [rax]
0x1800185ff  mov     [rbp+arg_8], rcx
0x180018603  mov     r8d, ecx
0x180018606  xor     eax, eax
0x180018608  mov     word ptr [rbp+arg_0+4], 3
0x18001860e  mov     r9d, r8d
0x180018611  mov     [rsp+40h+var_10], eax
0x180018615  mov     dword ptr [rbp+arg_0], eax
0x180018618  lea     rcx, qword_180029518
0x18001861f  shr     r9d, 0Bh
0x180018623  lea     rax, [rbp+arg_0]
0x180018627  shr     r8d, 0Ah
0x18001862b  and     r9d, ebx
0x18001862e  and     r8d, ebx
0x180018631  mov     [rsp+40h+var_18], ebx
0x180018635  mov     edx, 3667CA2h
0x18001863a  mov     [rsp+40h+var_20], rax
0x18001863f  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180018644  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001864b  mov     r8d, [rax]
0x18001864e  test    r8b, 4
0x180018652  jnz     short loc_180018667
0x180018654  lea     rdx, [rbp+arg_8]
0x180018658  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x18001865d  mov     rcx, [rax]
0x180018660  mov     [rbp+arg_8], rcx
0x180018664  mov     r8d, ecx
0x180018667  xor     eax, eax
0x180018669  mov     word ptr [rbp+arg_0+4], 3
0x18001866f  mov     r9d, r8d
0x180018672  mov     [rsp+40h+var_10], eax
0x180018676  mov     dword ptr [rbp+arg_0], eax
0x180018679  lea     rcx, qword_1800295A8
0x180018680  shr     r9d, 0Bh
0x180018684  lea     rax, [rbp+arg_0]
0x180018688  shr     r8d, 0Ah
0x18001868c  and     r9d, ebx
0x18001868f  and     r8d, ebx
0x180018692  mov     [rsp+40h+var_18], ebx
0x180018696  mov     edx, 2AF34F8h
0x18001869b  mov     [rsp+40h+var_20], rax
0x1800186a0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800186a5  mov     dl, bl
0x1800186a7  mov     eax, [rdi]
0x1800186a9  test    r14b, al
0x1800186ac  jz      short loc_1800186B2
0x1800186ae  test    dl, dl
0x1800186b0  jnz     short loc_1800186B4
0x1800186b2  xor     ebx, ebx
0x1800186b4  and     eax, 0FFFFFFFEh
0x1800186b7  or      eax, ebx
0x1800186b9  mov     rbx, [rsp+40h+arg_10]
0x1800186be  mov     [rdi], eax
0x1800186c0  mov     rax, rdi
0x1800186c3  add     rsp, 40h
0x1800186c7  pop     r14
0x1800186c9  pop     rdi
0x1800186ca  pop     rbp
0x1800186cb  retn
```
