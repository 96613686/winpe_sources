# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18001349c`
- end: `0x180013575`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800175f4`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001349c`
- `0x180013ce4`

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
0x18001349c  mov     [rsp+arg_10], rbx
0x1800134a1  mov     [rsp+arg_0], rcx
0x1800134a6  push    rbp
0x1800134a7  push    rsi
0x1800134a8  push    rdi
0x1800134a9  sub     rsp, 20h
0x1800134ad  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x1800134b4  mov     rdi, rdx
0x1800134b7  mov     qword ptr [rdx], 0
0x1800134be  mov     eax, [rsi]
0x1800134c0  mov     [rdx], eax
0x1800134c2  and     eax, 6
0x1800134c5  cmp     al, 6
0x1800134c7  jz      loc_180013565
0x1800134cd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800134d2  lea     r8, [rsp+38h+arg_0]
0x1800134d7  mov     dword ptr [rsp+38h+arg_0], 0
0x1800134df  lea     rdx, [rsp+38h+arg_8]
0x1800134e4  mov     ebp, eax
0x1800134e6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x1800134eb  mov     eax, [rdi]
0x1800134ed  mov     rbx, [rsp+38h+arg_8]
0x1800134f2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800134f7  mov     edx, eax
0x1800134f9  mov     [rdi], eax
0x1800134fb  mov     ecx, eax
0x1800134fd  jz      short loc_180013518
0x1800134ff  test    dl, 2
0x180013502  jnz     short loc_180013518
0x180013504  and     ecx, 0FFFFF63Eh
0x18001350a  mov     eax, ebx
0x18001350c  and     eax, 9C1h
0x180013511  or      ecx, eax
0x180013513  or      ecx, 2
0x180013516  mov     [rdi], ecx
0x180013518  mov     r8d, edx
0x18001351b  and     r8d, 4
0x18001351f  jnz     short loc_180013533
0x180013521  btr     ecx, 0Ah
0x180013525  mov     eax, ebx
0x180013527  and     eax, 400h
0x18001352c  or      ecx, eax
0x18001352e  or      ecx, 4
0x180013531  mov     [rdi], ecx
0x180013533  mov     eax, edx
0x180013535  lock cmpxchg [rsi], ecx
0x180013539  jnz     short loc_1800134F2
0x18001353b  test    r8d, r8d
0x18001353e  jnz     short loc_180013550
0x180013540  mov     r8d, ebp
0x180013543  mov     edx, 3
0x180013548  mov     rcx, rsi
0x18001354b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013550  mov     eax, [rdi]
0x180013552  test    al, 2
0x180013554  jnz     short loc_180013565
0x180013556  and     eax, 0FFFFF63Eh
0x18001355b  and     ebx, 9C1h
0x180013561  or      eax, ebx
0x180013563  mov     [rdi], eax
0x180013565  mov     rbx, [rsp+38h+arg_10]
0x18001356a  mov     rax, rdi
0x18001356d  add     rsp, 20h
0x180013571  pop     rdi
0x180013572  pop     rsi
0x180013573  pop     rbp
0x180013574  retn
```
