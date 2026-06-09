# wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent>::GetCachedFeatureEnabledState(void)

- ea: `0x180016164`
- end: `0x18001623d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004f90`
- `0x1800069bc`

## callees

- `0x18000d020`
- `0x1800105e0`
- `0x180016164`
- `0x180016640`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_LegacyUXIfPurchaseAppNotPresent__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_LegacyUXIfPurchaseAppNotPresent__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_LegacyUXIfPurchaseAppNotPresent__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_LegacyUXIfPurchaseAppNotPresent__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180016164  mov     [rsp+arg_10], rbx
0x180016169  mov     [rsp+arg_0], rcx
0x18001616e  push    rbp
0x18001616f  push    rsi
0x180016170  push    rdi
0x180016171  sub     rsp, 20h
0x180016175  mov     rsi, cs:Feature_LegacyUXIfPurchaseAppNotPresent__descriptor
0x18001617c  mov     rdi, rdx
0x18001617f  mov     qword ptr [rdx], 0
0x180016186  mov     eax, [rsi]
0x180016188  mov     [rdx], eax
0x18001618a  and     eax, 6
0x18001618d  cmp     al, 6
0x18001618f  jz      loc_18001622D
0x180016195  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001619a  lea     r8, [rsp+38h+arg_0]
0x18001619f  mov     dword ptr [rsp+38h+arg_0], 0
0x1800161a7  lea     rdx, [rsp+38h+arg_8]
0x1800161ac  mov     ebp, eax
0x1800161ae  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent>::GetCurrentFeatureEnabledState(int *)
0x1800161b3  mov     eax, [rdi]
0x1800161b5  mov     rbx, [rsp+38h+arg_8]
0x1800161ba  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800161bf  mov     edx, eax
0x1800161c1  mov     [rdi], eax
0x1800161c3  mov     ecx, eax
0x1800161c5  jz      short loc_1800161E0
0x1800161c7  test    dl, 2
0x1800161ca  jnz     short loc_1800161E0
0x1800161cc  and     ecx, 0FFFFF63Eh
0x1800161d2  mov     eax, ebx
0x1800161d4  and     eax, 9C1h
0x1800161d9  or      ecx, eax
0x1800161db  or      ecx, 2
0x1800161de  mov     [rdi], ecx
0x1800161e0  mov     r8d, edx
0x1800161e3  and     r8d, 4
0x1800161e7  jnz     short loc_1800161FB
0x1800161e9  btr     ecx, 0Ah
0x1800161ed  mov     eax, ebx
0x1800161ef  and     eax, 400h
0x1800161f4  or      ecx, eax
0x1800161f6  or      ecx, 4
0x1800161f9  mov     [rdi], ecx
0x1800161fb  mov     eax, edx
0x1800161fd  lock cmpxchg [rsi], ecx
0x180016201  jnz     short loc_1800161BA
0x180016203  test    r8d, r8d
0x180016206  jnz     short loc_180016218
0x180016208  mov     r8d, ebp
0x18001620b  mov     edx, 3
0x180016210  mov     rcx, rsi
0x180016213  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180016218  mov     eax, [rdi]
0x18001621a  test    al, 2
0x18001621c  jnz     short loc_18001622D
0x18001621e  and     eax, 0FFFFF63Eh
0x180016223  and     ebx, 9C1h
0x180016229  or      eax, ebx
0x18001622b  mov     [rdi], eax
0x18001622d  mov     rbx, [rsp+38h+arg_10]
0x180016232  mov     rax, rdi
0x180016235  add     rsp, 20h
0x180016239  pop     rdi
0x18001623a  pop     rsi
0x18001623b  pop     rbp
0x18001623c  retn
```
