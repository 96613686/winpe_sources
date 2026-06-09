# wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800131e0`
- end: `0x1800133ae`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180011e5c`

## callees

- `0x18000a358`
- `0x1800124a4`
- `0x180012dfc`
- `0x1800131e0`
- `0x180015348`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // edi
  char v11; // si
  bool v12; // dl
  unsigned int v13; // r8d
  __int64 v14; // rcx
  unsigned int v15; // r8d
  char IsEnabled; // al
  __int64 v18; // [rsp+60h] [rbp+20h] BYREF
  __int64 v19; // [rsp+68h] [rbp+28h] BYREF

  v18 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(47942714, 3);
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
    v8 = v7 | v6;
  }
  else
  {
    v7 = 64;
    v8 = v6 | 0x40;
  }
  v9 = v7 | (unsigned int)v6;
  *(_DWORD *)a2 = v8;
  v10 = 1;
  if ( (v9 & 0x400) != 0 && (unsigned int)v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    v12 = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_21;
  }
  v13 = *(_DWORD *)Feature_53693389__descriptor;
  if ( (*(_DWORD *)Feature_53693389__descriptor & 4) == 0 )
  {
    v19 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53693389>::GetCachedFeatureEnabledState(
                       v9,
                       &v19);
    v13 = v19;
  }
  WORD2(v18) = 3;
  LODWORD(v18) = 0;
  wil::details::ReportUsageToService(
    (__int64)&qword_180023988,
    0x3334BCDu,
    (v13 >> 10) & 1,
    (v13 >> 11) & 1,
    (__int64)&v18,
    1u,
    0);
  v15 = *(_DWORD *)Feature_Standalone_25_03_NonSec__descriptor;
  if ( (*(_DWORD *)Feature_Standalone_25_03_NonSec__descriptor & 4) == 0 )
  {
    v19 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_03_NonSec>::GetCachedFeatureEnabledState(
                       v14,
                       &v19);
    v15 = v19;
  }
  WORD2(v18) = 3;
  LODWORD(v18) = 0;
  wil::details::ReportUsageToService(
    (__int64)&qword_180023A38,
    0x2AF34E6u,
    (v15 >> 10) & 1,
    (v15 >> 11) & 1,
    (__int64)&v18,
    1u,
    0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_51718004>::GetImpl'::`2'::impl);
  v12 = IsEnabled != 0;
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_21:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v10 = 0;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800131e0  mov     [rsp-18h+arg_10], rbx
0x1800131e5  mov     [rsp-18h+arg_18], rsi
0x1800131ea  mov     [rsp-18h+arg_0], rcx
0x1800131ef  push    rbp
0x1800131f0  push    rdi
0x1800131f1  push    r15
0x1800131f3  mov     rbp, rsp
0x1800131f6  sub     rsp, 40h
0x1800131fa  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013201  mov     rbx, rdx
0x180013204  test    rax, rax
0x180013207  jz      short loc_18001321C
0x180013209  mov     edx, 3
0x18001320e  mov     ecx, 2DB8C3Ah
0x180013213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013218  mov     edx, eax
0x18001321a  jmp     short loc_18001322A
0x18001321c  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013223  test    rax, rax
0x180013226  jnz     short loc_180013209
0x180013228  xor     edx, edx
0x18001322a  mov     r8d, edx
0x18001322d  mov     qword ptr [rbx], 0
0x180013234  and     r8d, 0FFFFFF3Fh
0x18001323b  mov     eax, edx
0x18001323d  and     edx, 80h
0x180013243  mov     ecx, r8d
0x180013246  and     ecx, 3
0x180013249  mov     r15d, 40h ; '@'
0x18001324f  shl     ecx, 2
0x180013252  and     eax, r15d
0x180013255  or      ecx, eax
0x180013257  shl     ecx, 2
0x18001325a  or      ecx, edx
0x18001325c  shl     ecx, 3
0x18001325f  mov     eax, ecx
0x180013261  test    r8d, r8d
0x180013264  jnz     short loc_18001326E
0x180013266  mov     edx, r15d
0x180013269  or      eax, r15d
0x18001326c  jmp     short loc_18001327A
0x18001326e  xor     edx, edx
0x180013270  cmp     r8d, 2
0x180013274  cmovz   edx, r15d
0x180013278  or      eax, edx
0x18001327a  or      ecx, edx
0x18001327c  mov     [rbx], eax
0x18001327e  mov     edi, 1
0x180013283  bt      ecx, 0Ah
0x180013287  jnb     short loc_180013296
0x180013289  cmp     ecx, 800h
0x18001328f  jb      short loc_180013296
0x180013291  mov     sil, dil
0x180013294  jmp     short loc_1800132A4
0x180013296  xor     sil, sil
0x180013299  xor     dl, dl
0x18001329b  test    r15b, cl
0x18001329e  jz      loc_180013384
0x1800132a4  mov     rax, cs:Feature_53693389__descriptor
0x1800132ab  mov     r8d, [rax]
0x1800132ae  test    r8b, 4
0x1800132b2  jnz     short loc_1800132C7
0x1800132b4  lea     rdx, [rbp+arg_8]
0x1800132b8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_53693389@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53693389>::GetCachedFeatureEnabledState(void)
0x1800132bd  mov     rcx, [rax]
0x1800132c0  mov     [rbp+arg_8], rcx
0x1800132c4  mov     r8d, ecx
0x1800132c7  xor     eax, eax
0x1800132c9  mov     word ptr [rbp+arg_0+4], 3
0x1800132cf  mov     r9d, r8d
0x1800132d2  mov     [rsp+40h+var_10], eax
0x1800132d6  mov     dword ptr [rbp+arg_0], eax
0x1800132d9  lea     rcx, qword_180023988
0x1800132e0  shr     r9d, 0Bh
0x1800132e4  lea     rax, [rbp+arg_0]
0x1800132e8  shr     r8d, 0Ah
0x1800132ec  and     r9d, edi
0x1800132ef  and     r8d, edi
0x1800132f2  mov     [rsp+40h+var_18], edi
0x1800132f6  mov     edx, 3334BCDh
0x1800132fb  mov     [rsp+40h+var_20], rax
0x180013300  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180013305  mov     rax, cs:Feature_Standalone_25_03_NonSec__descriptor
0x18001330c  mov     r8d, [rax]
0x18001330f  test    r8b, 4
0x180013313  jnz     short loc_180013328
0x180013315  lea     rdx, [rbp+arg_8]
0x180013319  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_03_NonSec>::GetCachedFeatureEnabledState(void)
0x18001331e  mov     rcx, [rax]
0x180013321  mov     [rbp+arg_8], rcx
0x180013325  mov     r8d, ecx
0x180013328  xor     eax, eax
0x18001332a  mov     word ptr [rbp+arg_0+4], 3
0x180013330  mov     r9d, r8d
0x180013333  mov     [rsp+40h+var_10], eax
0x180013337  mov     dword ptr [rbp+arg_0], eax
0x18001333a  lea     rcx, qword_180023A38
0x180013341  shr     r9d, 0Bh
0x180013345  lea     rax, [rbp+arg_0]
0x180013349  shr     r8d, 0Ah
0x18001334d  and     r9d, edi
0x180013350  and     r8d, edi
0x180013353  mov     [rsp+40h+var_18], edi
0x180013357  mov     edx, 2AF34E6h
0x18001335c  mov     [rsp+40h+var_20], rax
0x180013361  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180013366  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_51718004@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_51718004@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004> `wil::Feature<__WilFeatureTraits_Feature_51718004>::GetImpl(void)'::`2'::impl
0x18001336d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_51718004@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::__private_IsEnabled(wil::ReportingKind)
0x180013372  test    al, al
0x180013374  setnz   dl
0x180013377  test    sil, sil
0x18001337a  jz      short loc_180013384
0x18001337c  test    dl, dl
0x18001337e  jnz     short loc_180013384
0x180013380  btr     dword ptr [rbx], 0Ah
0x180013384  mov     eax, [rbx]
0x180013386  test    r15b, al
0x180013389  jz      short loc_18001338F
0x18001338b  test    dl, dl
0x18001338d  jnz     short loc_180013391
0x18001338f  xor     edi, edi
0x180013391  mov     rsi, [rsp+40h+arg_18]
0x180013396  and     eax, 0FFFFFFFEh
0x180013399  or      eax, edi
0x18001339b  mov     [rbx], eax
0x18001339d  mov     rax, rbx
0x1800133a0  mov     rbx, [rsp+40h+arg_10]
0x1800133a5  add     rsp, 40h
0x1800133a9  pop     r15
0x1800133ab  pop     rdi
0x1800133ac  pop     rbp
0x1800133ad  retn
```
