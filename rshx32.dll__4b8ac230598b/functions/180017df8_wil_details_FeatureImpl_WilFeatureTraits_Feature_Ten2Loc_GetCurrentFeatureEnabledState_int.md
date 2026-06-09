# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180017df8`
- end: `0x180017f61`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180017738`

## callees

- `0x1800172dc`
- `0x180017df8`
- `0x180018ac8`
- `0x1800190b8`
- `0x18001e010`

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
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_1800295D8, 58599550, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180017df8  mov     [rsp+arg_10], rbx
0x180017dfd  mov     [rsp+arg_0], rcx
0x180017e02  push    rbp
0x180017e03  push    rsi
0x180017e04  push    rdi
0x180017e05  sub     rsp, 40h
0x180017e09  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180017e10  mov     rbx, rdx
0x180017e13  test    rax, rax
0x180017e16  jz      short loc_180017E2B
0x180017e18  mov     edx, 3
0x180017e1d  mov     ecx, 38419CAh
0x180017e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e27  mov     edx, eax
0x180017e29  jmp     short loc_180017E39
0x180017e2b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180017e32  test    rax, rax
0x180017e35  jnz     short loc_180017E18
0x180017e37  xor     edx, edx
0x180017e39  mov     r8d, edx
0x180017e3c  mov     qword ptr [rbx], 0
0x180017e43  and     r8d, 0FFFFFF3Fh
0x180017e4a  mov     eax, edx
0x180017e4c  and     edx, 80h
0x180017e52  mov     ecx, r8d
0x180017e55  and     ecx, 3
0x180017e58  mov     ebp, 40h ; '@'
0x180017e5d  shl     ecx, 2
0x180017e60  and     eax, ebp
0x180017e62  or      ecx, eax
0x180017e64  shl     ecx, 2
0x180017e67  or      ecx, edx
0x180017e69  shl     ecx, 3
0x180017e6c  test    r8d, r8d
0x180017e6f  jnz     short loc_180017E78
0x180017e71  mov     edx, ebp
0x180017e73  mov     r8d, ebp
0x180017e76  jmp     short loc_180017E84
0x180017e78  xor     edx, edx
0x180017e7a  cmp     r8d, 2
0x180017e7e  cmovz   edx, ebp
0x180017e81  mov     r8d, edx
0x180017e84  mov     eax, ecx
0x180017e86  mov     edi, 1
0x180017e8b  or      eax, r8d
0x180017e8e  or      ecx, edx
0x180017e90  mov     [rbx], eax
0x180017e92  bt      ecx, 0Ah
0x180017e96  jnb     short loc_180017EA5
0x180017e98  cmp     ecx, 800h
0x180017e9e  jb      short loc_180017EA5
0x180017ea0  mov     sil, dil
0x180017ea3  jmp     short loc_180017EB3
0x180017ea5  xor     sil, sil
0x180017ea8  xor     dl, dl
0x180017eaa  test    bpl, cl
0x180017ead  jz      loc_180017F3D
0x180017eb3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180017eba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180017ebf  test    al, al
0x180017ec1  jz      short loc_180017F2E
0x180017ec3  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180017eca  mov     r8d, [rax]
0x180017ecd  test    r8b, 4
0x180017ed1  jnz     short loc_180017EE8
0x180017ed3  lea     rdx, [rsp+58h+arg_8]
0x180017ed8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180017edd  mov     rcx, [rax]
0x180017ee0  mov     [rsp+58h+arg_8], rcx
0x180017ee5  mov     r8d, ecx
0x180017ee8  xor     eax, eax
0x180017eea  mov     word ptr [rsp+58h+arg_0+4], 3
0x180017ef1  mov     r9d, r8d
0x180017ef4  mov     [rsp+58h+var_28], eax
0x180017ef8  mov     dword ptr [rsp+58h+arg_0], eax
0x180017efc  lea     rcx, qword_1800295D8
0x180017f03  shr     r9d, 0Bh
0x180017f07  lea     rax, [rsp+58h+arg_0]
0x180017f0c  shr     r8d, 0Ah
0x180017f10  and     r9d, edi
0x180017f13  and     r8d, edi
0x180017f16  mov     [rsp+58h+var_30], edi
0x180017f1a  mov     edx, 37E287Eh
0x180017f1f  mov     [rsp+58h+var_38], rax
0x180017f24  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180017f29  mov     dl, dil
0x180017f2c  jmp     short loc_180017F30
0x180017f2e  xor     dl, dl
0x180017f30  test    sil, sil
0x180017f33  jz      short loc_180017F3D
0x180017f35  test    dl, dl
0x180017f37  jnz     short loc_180017F3D
0x180017f39  btr     dword ptr [rbx], 0Ah
0x180017f3d  mov     eax, [rbx]
0x180017f3f  test    bpl, al
0x180017f42  jz      short loc_180017F48
0x180017f44  test    dl, dl
0x180017f46  jnz     short loc_180017F4A
0x180017f48  xor     edi, edi
0x180017f4a  and     eax, 0FFFFFFFEh
0x180017f4d  or      eax, edi
0x180017f4f  mov     [rbx], eax
0x180017f51  mov     rax, rbx
0x180017f54  mov     rbx, [rsp+58h+arg_10]
0x180017f59  add     rsp, 40h
0x180017f5d  pop     rdi
0x180017f5e  pop     rsi
0x180017f5f  pop     rbp
0x180017f60  retn
```
