# wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetCachedFeatureEnabledState(void)

- ea: `0x140055e7c`
- end: `0x140055f5d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a914`
- `0x14005d50c`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x140055e7c`
- `0x140056a90`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_OverlappedWindowBehavior__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_OverlappedWindowBehavior__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_OverlappedWindowBehavior__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_OverlappedWindowBehavior__descriptor,
        1,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140055e7c  mov     [rsp+arg_10], rbx
0x140055e81  mov     [rsp+arg_0], rcx
0x140055e86  push    rbp
0x140055e87  push    rsi
0x140055e88  push    rdi
0x140055e89  sub     rsp, 20h
0x140055e8d  mov     rsi, cs:Feature_OverlappedWindowBehavior__descriptor
0x140055e94  mov     rdi, rdx
0x140055e97  mov     qword ptr [rdx], 0
0x140055e9e  mov     eax, [rsi]
0x140055ea0  mov     [rdx], eax
0x140055ea2  and     eax, 6
0x140055ea5  cmp     al, 6
0x140055ea7  jz      loc_140055F4D
0x140055ead  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140055eb2  lea     r8, [rsp+38h+arg_0]
0x140055eb7  mov     dword ptr [rsp+38h+arg_0], 0
0x140055ebf  lea     rdx, [rsp+38h+arg_8]
0x140055ec4  mov     ebp, eax
0x140055ec6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetCurrentFeatureEnabledState(int *)
0x140055ecb  mov     eax, [rdi]
0x140055ecd  mov     rbx, [rsp+38h+arg_8]
0x140055ed2  cmp     dword ptr [rsp+38h+arg_0], 0
0x140055ed7  mov     edx, eax
0x140055ed9  mov     [rdi], eax
0x140055edb  mov     ecx, eax
0x140055edd  jz      short loc_140055EF8
0x140055edf  test    dl, 2
0x140055ee2  jnz     short loc_140055EF8
0x140055ee4  and     ecx, 0FFFFF63Eh
0x140055eea  mov     eax, ebx
0x140055eec  and     eax, 9C1h
0x140055ef1  or      ecx, eax
0x140055ef3  or      ecx, 2
0x140055ef6  mov     [rdi], ecx
0x140055ef8  mov     r8d, edx
0x140055efb  and     r8d, 4
0x140055eff  jnz     short loc_140055F13
0x140055f01  btr     ecx, 0Ah
0x140055f05  mov     eax, ebx
0x140055f07  and     eax, 400h
0x140055f0c  or      ecx, eax
0x140055f0e  or      ecx, 4
0x140055f11  mov     [rdi], ecx
0x140055f13  mov     eax, edx
0x140055f15  lock cmpxchg [rsi], ecx
0x140055f19  jnz     short loc_140055ED2
0x140055f1b  test    r8d, r8d
0x140055f1e  jnz     short loc_140055F38
0x140055f20  mov     r9d, ebp
0x140055f23  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140055f2a  mov     r8d, 1
0x140055f30  mov     rdx, rsi
0x140055f33  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140055f38  mov     eax, [rdi]
0x140055f3a  test    al, 2
0x140055f3c  jnz     short loc_140055F4D
0x140055f3e  and     eax, 0FFFFF63Eh
0x140055f43  and     ebx, 9C1h
0x140055f49  or      eax, ebx
0x140055f4b  mov     [rdi], eax
0x140055f4d  mov     rbx, [rsp+38h+arg_10]
0x140055f52  mov     rax, rdi
0x140055f55  add     rsp, 20h
0x140055f59  pop     rdi
0x140055f5a  pop     rsi
0x140055f5b  pop     rbp
0x140055f5c  retn
```
