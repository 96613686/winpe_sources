# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180013a04`
- end: `0x180013b6d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800132dc`

## callees

- `0x180012e80`
- `0x180013a04`
- `0x180015608`
- `0x1800175f4`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  char v13; // dl
  wil::details *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989002, 3);
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180034CB0, 58599550, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180013a04  mov     [rsp+arg_10], rbx
0x180013a09  mov     [rsp+arg_0], rcx
0x180013a0e  push    rbp
0x180013a0f  push    rsi
0x180013a10  push    rdi
0x180013a11  sub     rsp, 40h
0x180013a15  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013a1c  mov     rbx, rdx
0x180013a1f  test    rax, rax
0x180013a22  jz      short loc_180013A37
0x180013a24  mov     edx, 3
0x180013a29  mov     ecx, 38419CAh
0x180013a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a33  mov     edx, eax
0x180013a35  jmp     short loc_180013A45
0x180013a37  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013a3e  test    rax, rax
0x180013a41  jnz     short loc_180013A24
0x180013a43  xor     edx, edx
0x180013a45  mov     r8d, edx
0x180013a48  mov     qword ptr [rbx], 0
0x180013a4f  and     r8d, 0FFFFFF3Fh
0x180013a56  mov     eax, edx
0x180013a58  and     edx, 80h
0x180013a5e  mov     ecx, r8d
0x180013a61  and     ecx, 3
0x180013a64  mov     ebp, 40h ; '@'
0x180013a69  shl     ecx, 2
0x180013a6c  and     eax, ebp
0x180013a6e  or      ecx, eax
0x180013a70  shl     ecx, 2
0x180013a73  or      ecx, edx
0x180013a75  shl     ecx, 3
0x180013a78  test    r8d, r8d
0x180013a7b  jnz     short loc_180013A84
0x180013a7d  mov     edx, ebp
0x180013a7f  mov     r8d, ebp
0x180013a82  jmp     short loc_180013A90
0x180013a84  xor     edx, edx
0x180013a86  cmp     r8d, 2
0x180013a8a  cmovz   edx, ebp
0x180013a8d  mov     r8d, edx
0x180013a90  mov     eax, ecx
0x180013a92  mov     edi, 1
0x180013a97  or      eax, r8d
0x180013a9a  or      ecx, edx
0x180013a9c  mov     [rbx], eax
0x180013a9e  bt      ecx, 0Ah
0x180013aa2  jnb     short loc_180013AB1
0x180013aa4  cmp     ecx, 800h
0x180013aaa  jb      short loc_180013AB1
0x180013aac  mov     sil, dil
0x180013aaf  jmp     short loc_180013ABF
0x180013ab1  xor     sil, sil
0x180013ab4  xor     dl, dl
0x180013ab6  test    bpl, cl
0x180013ab9  jz      loc_180013B49
0x180013abf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180013ac6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180013acb  test    al, al
0x180013acd  jz      short loc_180013B3A
0x180013acf  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180013ad6  mov     r8d, [rax]
0x180013ad9  test    r8b, 4
0x180013add  jnz     short loc_180013AF4
0x180013adf  lea     rdx, [rsp+58h+arg_8]
0x180013ae4  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180013ae9  mov     rcx, [rax]
0x180013aec  mov     [rsp+58h+arg_8], rcx
0x180013af1  mov     r8d, ecx
0x180013af4  xor     eax, eax
0x180013af6  mov     word ptr [rsp+58h+arg_0+4], 3
0x180013afd  mov     r9d, r8d
0x180013b00  mov     [rsp+58h+var_28], eax
0x180013b04  mov     dword ptr [rsp+58h+arg_0], eax
0x180013b08  lea     rcx, qword_180034CB0
0x180013b0f  shr     r9d, 0Bh
0x180013b13  lea     rax, [rsp+58h+arg_0]
0x180013b18  shr     r8d, 0Ah
0x180013b1c  and     r9d, edi
0x180013b1f  and     r8d, edi
0x180013b22  mov     [rsp+58h+var_30], edi
0x180013b26  mov     edx, 37E287Eh
0x180013b2b  mov     [rsp+58h+var_38], rax
0x180013b30  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180013b35  mov     dl, dil
0x180013b38  jmp     short loc_180013B3C
0x180013b3a  xor     dl, dl
0x180013b3c  test    sil, sil
0x180013b3f  jz      short loc_180013B49
0x180013b41  test    dl, dl
0x180013b43  jnz     short loc_180013B49
0x180013b45  btr     dword ptr [rbx], 0Ah
0x180013b49  mov     eax, [rbx]
0x180013b4b  test    bpl, al
0x180013b4e  jz      short loc_180013B54
0x180013b50  test    dl, dl
0x180013b52  jnz     short loc_180013B56
0x180013b54  xor     edi, edi
0x180013b56  and     eax, 0FFFFFFFEh
0x180013b59  or      eax, edi
0x180013b5b  mov     [rbx], eax
0x180013b5d  mov     rax, rbx
0x180013b60  mov     rbx, [rsp+58h+arg_10]
0x180013b65  add     rsp, 40h
0x180013b69  pop     rdi
0x180013b6a  pop     rsi
0x180013b6b  pop     rbp
0x180013b6c  retn
```
