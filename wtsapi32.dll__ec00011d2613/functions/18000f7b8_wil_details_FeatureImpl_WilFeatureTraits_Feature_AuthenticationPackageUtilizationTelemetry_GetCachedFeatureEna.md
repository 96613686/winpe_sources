# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f7b8`
- end: `0x18000f899`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010f38`
- `0x180011f48`

## callees

- `0x18000f670`
- `0x18000f7b8`
- `0x18000fae4`
- `0x180011240`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AuthenticationPackageUtilizationTelemetry__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AuthenticationPackageUtilizationTelemetry__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_AuthenticationPackageUtilizationTelemetry__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_AuthenticationPackageUtilizationTelemetry__descriptor,
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
0x18000f7b8  mov     [rsp+arg_10], rbx
0x18000f7bd  mov     [rsp+arg_0], rcx
0x18000f7c2  push    rbp
0x18000f7c3  push    rsi
0x18000f7c4  push    rdi
0x18000f7c5  sub     rsp, 20h
0x18000f7c9  mov     rsi, cs:Feature_AuthenticationPackageUtilizationTelemetry__descriptor
0x18000f7d0  mov     rdi, rdx
0x18000f7d3  mov     qword ptr [rdx], 0
0x18000f7da  mov     eax, [rsi]
0x18000f7dc  mov     [rdx], eax
0x18000f7de  and     eax, 6
0x18000f7e1  cmp     al, 6
0x18000f7e3  jz      loc_18000F889
0x18000f7e9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f7ee  lea     r8, [rsp+38h+arg_0]
0x18000f7f3  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f7fb  lea     rdx, [rsp+38h+arg_8]
0x18000f800  mov     ebp, eax
0x18000f802  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::GetCurrentFeatureEnabledState(int *)
0x18000f807  mov     eax, [rdi]
0x18000f809  mov     rbx, [rsp+38h+arg_8]
0x18000f80e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f813  mov     edx, eax
0x18000f815  mov     [rdi], eax
0x18000f817  mov     ecx, eax
0x18000f819  jz      short loc_18000F834
0x18000f81b  test    dl, 2
0x18000f81e  jnz     short loc_18000F834
0x18000f820  and     ecx, 0FFFFF63Eh
0x18000f826  mov     eax, ebx
0x18000f828  and     eax, 9C1h
0x18000f82d  or      ecx, eax
0x18000f82f  or      ecx, 2
0x18000f832  mov     [rdi], ecx
0x18000f834  mov     r8d, edx
0x18000f837  and     r8d, 4
0x18000f83b  jnz     short loc_18000F84F
0x18000f83d  btr     ecx, 0Ah
0x18000f841  mov     eax, ebx
0x18000f843  and     eax, 400h
0x18000f848  or      ecx, eax
0x18000f84a  or      ecx, 4
0x18000f84d  mov     [rdi], ecx
0x18000f84f  mov     eax, edx
0x18000f851  lock cmpxchg [rsi], ecx
0x18000f855  jnz     short loc_18000F80E
0x18000f857  test    r8d, r8d
0x18000f85a  jnz     short loc_18000F874
0x18000f85c  mov     r9d, ebp
0x18000f85f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f866  mov     r8d, 3
0x18000f86c  mov     rdx, rsi
0x18000f86f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f874  mov     eax, [rdi]
0x18000f876  test    al, 2
0x18000f878  jnz     short loc_18000F889
0x18000f87a  and     eax, 0FFFFF63Eh
0x18000f87f  and     ebx, 9C1h
0x18000f885  or      eax, ebx
0x18000f887  mov     [rdi], eax
0x18000f889  mov     rbx, [rsp+38h+arg_10]
0x18000f88e  mov     rax, rdi
0x18000f891  add     rsp, 20h
0x18000f895  pop     rdi
0x18000f896  pop     rsi
0x18000f897  pop     rbp
0x18000f898  retn
```
