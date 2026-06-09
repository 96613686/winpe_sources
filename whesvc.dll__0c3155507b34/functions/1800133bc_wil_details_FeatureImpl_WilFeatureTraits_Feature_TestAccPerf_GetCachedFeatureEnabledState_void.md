# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800133bc`
- end: `0x180013495`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017558`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x1800133bc`
- `0x180013b74`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestAccPerf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800133bc  mov     [rsp+arg_10], rbx
0x1800133c1  mov     [rsp+arg_0], rcx
0x1800133c6  push    rbp
0x1800133c7  push    rsi
0x1800133c8  push    rdi
0x1800133c9  sub     rsp, 20h
0x1800133cd  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x1800133d4  mov     rdi, rdx
0x1800133d7  mov     qword ptr [rdx], 0
0x1800133de  mov     eax, [rsi]
0x1800133e0  mov     [rdx], eax
0x1800133e2  and     eax, 6
0x1800133e5  cmp     al, 6
0x1800133e7  jz      loc_180013485
0x1800133ed  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800133f2  lea     r8, [rsp+38h+arg_0]
0x1800133f7  mov     dword ptr [rsp+38h+arg_0], 0
0x1800133ff  lea     rdx, [rsp+38h+arg_8]
0x180013404  mov     ebp, eax
0x180013406  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18001340b  mov     eax, [rdi]
0x18001340d  mov     rbx, [rsp+38h+arg_8]
0x180013412  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013417  mov     edx, eax
0x180013419  mov     [rdi], eax
0x18001341b  mov     ecx, eax
0x18001341d  jz      short loc_180013438
0x18001341f  test    dl, 2
0x180013422  jnz     short loc_180013438
0x180013424  and     ecx, 0FFFFF63Eh
0x18001342a  mov     eax, ebx
0x18001342c  and     eax, 9C1h
0x180013431  or      ecx, eax
0x180013433  or      ecx, 2
0x180013436  mov     [rdi], ecx
0x180013438  mov     r8d, edx
0x18001343b  and     r8d, 4
0x18001343f  jnz     short loc_180013453
0x180013441  btr     ecx, 0Ah
0x180013445  mov     eax, ebx
0x180013447  and     eax, 400h
0x18001344c  or      ecx, eax
0x18001344e  or      ecx, 4
0x180013451  mov     [rdi], ecx
0x180013453  mov     eax, edx
0x180013455  lock cmpxchg [rsi], ecx
0x180013459  jnz     short loc_180013412
0x18001345b  test    r8d, r8d
0x18001345e  jnz     short loc_180013470
0x180013460  mov     r8d, ebp
0x180013463  mov     edx, 3
0x180013468  mov     rcx, rsi
0x18001346b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013470  mov     eax, [rdi]
0x180013472  test    al, 2
0x180013474  jnz     short loc_180013485
0x180013476  and     eax, 0FFFFF63Eh
0x18001347b  and     ebx, 9C1h
0x180013481  or      eax, ebx
0x180013483  mov     [rdi], eax
0x180013485  mov     rbx, [rsp+38h+arg_10]
0x18001348a  mov     rax, rdi
0x18001348d  add     rsp, 20h
0x180013491  pop     rdi
0x180013492  pop     rsi
0x180013493  pop     rbp
0x180013494  retn
```
