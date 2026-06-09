# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800183b8`
- end: `0x180018521`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180017ab8`

## callees

- `0x180017450`
- `0x1800183b8`
- `0x180018ac8`
- `0x180018f80`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989021, 3);
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
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_1800295E8, 58599553, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800183b8  mov     [rsp+arg_10], rbx
0x1800183bd  mov     [rsp+arg_0], rcx
0x1800183c2  push    rbp
0x1800183c3  push    rsi
0x1800183c4  push    rdi
0x1800183c5  sub     rsp, 40h
0x1800183c9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800183d0  mov     rbx, rdx
0x1800183d3  test    rax, rax
0x1800183d6  jz      short loc_1800183EB
0x1800183d8  mov     edx, 3
0x1800183dd  mov     ecx, 38419DDh
0x1800183e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183e7  mov     edx, eax
0x1800183e9  jmp     short loc_1800183F9
0x1800183eb  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800183f2  test    rax, rax
0x1800183f5  jnz     short loc_1800183D8
0x1800183f7  xor     edx, edx
0x1800183f9  mov     r8d, edx
0x1800183fc  mov     qword ptr [rbx], 0
0x180018403  and     r8d, 0FFFFFF3Fh
0x18001840a  mov     eax, edx
0x18001840c  and     edx, 80h
0x180018412  mov     ecx, r8d
0x180018415  and     ecx, 3
0x180018418  mov     ebp, 40h ; '@'
0x18001841d  shl     ecx, 2
0x180018420  and     eax, ebp
0x180018422  or      ecx, eax
0x180018424  shl     ecx, 2
0x180018427  or      ecx, edx
0x180018429  shl     ecx, 3
0x18001842c  test    r8d, r8d
0x18001842f  jnz     short loc_180018438
0x180018431  mov     edx, ebp
0x180018433  mov     r8d, ebp
0x180018436  jmp     short loc_180018444
0x180018438  xor     edx, edx
0x18001843a  cmp     r8d, 2
0x18001843e  cmovz   edx, ebp
0x180018441  mov     r8d, edx
0x180018444  mov     eax, ecx
0x180018446  mov     edi, 1
0x18001844b  or      eax, r8d
0x18001844e  or      ecx, edx
0x180018450  mov     [rbx], eax
0x180018452  bt      ecx, 0Ah
0x180018456  jnb     short loc_180018465
0x180018458  cmp     ecx, 800h
0x18001845e  jb      short loc_180018465
0x180018460  mov     sil, dil
0x180018463  jmp     short loc_180018473
0x180018465  xor     sil, sil
0x180018468  xor     dl, dl
0x18001846a  test    bpl, cl
0x18001846d  jz      loc_1800184FD
0x180018473  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18001847a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18001847f  test    al, al
0x180018481  jz      short loc_1800184EE
0x180018483  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18001848a  mov     r8d, [rax]
0x18001848d  test    r8b, 4
0x180018491  jnz     short loc_1800184A8
0x180018493  lea     rdx, [rsp+58h+arg_8]
0x180018498  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x18001849d  mov     rcx, [rax]
0x1800184a0  mov     [rsp+58h+arg_8], rcx
0x1800184a5  mov     r8d, ecx
0x1800184a8  xor     eax, eax
0x1800184aa  mov     word ptr [rsp+58h+arg_0+4], 3
0x1800184b1  mov     r9d, r8d
0x1800184b4  mov     [rsp+58h+var_28], eax
0x1800184b8  mov     dword ptr [rsp+58h+arg_0], eax
0x1800184bc  lea     rcx, qword_1800295E8
0x1800184c3  shr     r9d, 0Bh
0x1800184c7  lea     rax, [rsp+58h+arg_0]
0x1800184cc  shr     r8d, 0Ah
0x1800184d0  and     r9d, edi
0x1800184d3  and     r8d, edi
0x1800184d6  mov     [rsp+58h+var_30], edi
0x1800184da  mov     edx, 37E2881h
0x1800184df  mov     [rsp+58h+var_38], rax
0x1800184e4  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800184e9  mov     dl, dil
0x1800184ec  jmp     short loc_1800184F0
0x1800184ee  xor     dl, dl
0x1800184f0  test    sil, sil
0x1800184f3  jz      short loc_1800184FD
0x1800184f5  test    dl, dl
0x1800184f7  jnz     short loc_1800184FD
0x1800184f9  btr     dword ptr [rbx], 0Ah
0x1800184fd  mov     eax, [rbx]
0x1800184ff  test    bpl, al
0x180018502  jz      short loc_180018508
0x180018504  test    dl, dl
0x180018506  jnz     short loc_18001850A
0x180018508  xor     edi, edi
0x18001850a  and     eax, 0FFFFFFFEh
0x18001850d  or      eax, edi
0x18001850f  mov     [rbx], eax
0x180018511  mov     rax, rbx
0x180018514  mov     rbx, [rsp+58h+arg_10]
0x180018519  add     rsp, 40h
0x18001851d  pop     rdi
0x18001851e  pop     rsi
0x18001851f  pop     rbp
0x180018520  retn
```
