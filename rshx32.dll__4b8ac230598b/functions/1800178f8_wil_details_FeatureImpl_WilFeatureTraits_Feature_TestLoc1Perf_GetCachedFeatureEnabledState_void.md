# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800178f8`
- end: `0x1800179d1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800190b8`

## callees

- `0x180016be8`
- `0x1800178f8`
- `0x1800180d8`
- `0x180018da4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestLoc1Perf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800178f8  mov     [rsp+arg_10], rbx
0x1800178fd  mov     [rsp+arg_0], rcx
0x180017902  push    rbp
0x180017903  push    rsi
0x180017904  push    rdi
0x180017905  sub     rsp, 20h
0x180017909  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180017910  mov     rdi, rdx
0x180017913  mov     qword ptr [rdx], 0
0x18001791a  mov     eax, [rsi]
0x18001791c  mov     [rdx], eax
0x18001791e  and     eax, 6
0x180017921  cmp     al, 6
0x180017923  jz      loc_1800179C1
0x180017929  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001792e  lea     r8, [rsp+38h+arg_0]
0x180017933  mov     dword ptr [rsp+38h+arg_0], 0
0x18001793b  lea     rdx, [rsp+38h+arg_8]
0x180017940  mov     ebp, eax
0x180017942  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180017947  mov     eax, [rdi]
0x180017949  mov     rbx, [rsp+38h+arg_8]
0x18001794e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180017953  mov     edx, eax
0x180017955  mov     [rdi], eax
0x180017957  mov     ecx, eax
0x180017959  jz      short loc_180017974
0x18001795b  test    dl, 2
0x18001795e  jnz     short loc_180017974
0x180017960  and     ecx, 0FFFFF63Eh
0x180017966  mov     eax, ebx
0x180017968  and     eax, 9C1h
0x18001796d  or      ecx, eax
0x18001796f  or      ecx, 2
0x180017972  mov     [rdi], ecx
0x180017974  mov     r8d, edx
0x180017977  and     r8d, 4
0x18001797b  jnz     short loc_18001798F
0x18001797d  btr     ecx, 0Ah
0x180017981  mov     eax, ebx
0x180017983  and     eax, 400h
0x180017988  or      ecx, eax
0x18001798a  or      ecx, 4
0x18001798d  mov     [rdi], ecx
0x18001798f  mov     eax, edx
0x180017991  lock cmpxchg [rsi], ecx
0x180017995  jnz     short loc_18001794E
0x180017997  test    r8d, r8d
0x18001799a  jnz     short loc_1800179AC
0x18001799c  mov     r8d, ebp
0x18001799f  mov     edx, 3
0x1800179a4  mov     rcx, rsi
0x1800179a7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800179ac  mov     eax, [rdi]
0x1800179ae  test    al, 2
0x1800179b0  jnz     short loc_1800179C1
0x1800179b2  and     eax, 0FFFFF63Eh
0x1800179b7  and     ebx, 9C1h
0x1800179bd  or      eax, ebx
0x1800179bf  mov     [rdi], eax
0x1800179c1  mov     rbx, [rsp+38h+arg_10]
0x1800179c6  mov     rax, rdi
0x1800179c9  add     rsp, 20h
0x1800179cd  pop     rdi
0x1800179ce  pop     rsi
0x1800179cf  pop     rbp
0x1800179d0  retn
```
