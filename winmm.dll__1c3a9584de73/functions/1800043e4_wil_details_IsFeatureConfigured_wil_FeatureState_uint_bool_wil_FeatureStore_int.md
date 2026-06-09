# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800043e4`
- end: `0x1800044c7`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004370`

## callees

- `0x1800043e4`
- `0x1800044d0`
- `0x180004628`
- `0x18000b6fc`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  int v13; // r8d
  bool v14; // di
  char v15; // dl
  int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !v13 && (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        v7,
        0,
        v11);
    return v14;
  }
}

```

## disassembly

```asm
0x1800043e4  mov     [rsp+arg_0], rbx
0x1800043e9  mov     [rsp+arg_8], rbp
0x1800043ee  push    rsi
0x1800043ef  push    rdi
0x1800043f0  push    r14
0x1800043f2  sub     rsp, 20h
0x1800043f6  test    r9d, r9d
0x1800043f9  movzx   edi, r8b
0x1800043fd  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180004404  mov     esi, edx
0x180004406  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000440d  mov     rbp, rcx
0x180004410  cmovnz  rbx, rax
0x180004414  mov     r9d, [rbx]
0x180004417  mov     eax, r9d
0x18000441a  and     al, 3
0x18000441c  cmp     al, 2
0x18000441e  jnz     short loc_180004435
0x180004420  xor     al, al
0x180004422  mov     rbx, [rsp+38h+arg_0]
0x180004427  mov     rbp, [rsp+38h+arg_8]
0x18000442c  add     rsp, 20h
0x180004430  pop     r14
0x180004432  pop     rdi
0x180004433  pop     rsi
0x180004434  retn
0x180004435  test    r9b, 2
0x180004439  jz      short loc_180004458
0x18000443b  mov     rax, [rsp+38h+arg_20]
0x180004440  mov     r8d, edi
0x180004443  xor     r9d, r9d
0x180004446  mov     dword ptr [rax], 1
0x18000444c  call    wil_RtlStagingConfig_QueryFeatureState
0x180004451  test    eax, eax
0x180004453  setnz   al
0x180004456  jmp     short loc_180004422
0x180004458  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000445d  mov     rcx, [rsp+38h+arg_20]
0x180004462  lea     r9, [rsp+38h+arg_18]
0x180004467  mov     r8d, edi
0x18000446a  mov     [rsp+38h+arg_18], 0
0x180004472  mov     edx, esi
0x180004474  mov     r14d, eax
0x180004477  mov     dword ptr [rcx], 1
0x18000447d  mov     rcx, rbp
0x180004480  call    wil_RtlStagingConfig_QueryFeatureState
0x180004485  mov     r8d, [rsp+38h+arg_18]
0x18000448a  test    eax, eax
0x18000448c  mov     ecx, r8d
0x18000448f  setnz   dil
0x180004493  neg     ecx
0x180004495  sbb     edx, edx
0x180004497  neg     edx
0x180004499  add     edx, 6
0x18000449c  xchg    edx, [rbx]
0x18000449e  test    r8d, r8d
0x1800044a1  jz      short loc_1800044AB
0x1800044a3  mov     al, dil
0x1800044a6  jmp     loc_180004422
0x1800044ab  test    dl, 4
0x1800044ae  jnz     short loc_1800044A3
0x1800044b0  mov     r9d, r14d
0x1800044b3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800044ba  xor     r8d, r8d
0x1800044bd  mov     rdx, rbx
0x1800044c0  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800044c5  jmp     short loc_1800044A3
```
