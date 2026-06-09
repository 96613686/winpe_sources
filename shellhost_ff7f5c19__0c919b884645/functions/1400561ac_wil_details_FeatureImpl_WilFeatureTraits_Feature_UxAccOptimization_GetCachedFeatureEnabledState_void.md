# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x1400561ac`
- end: `0x14005628d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a9a0`
- `0x14005d548`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x1400561ac`
- `0x140056c84`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_UxAccOptimization__descriptor,
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
0x1400561ac  mov     [rsp+arg_10], rbx
0x1400561b1  mov     [rsp+arg_0], rcx
0x1400561b6  push    rbp
0x1400561b7  push    rsi
0x1400561b8  push    rdi
0x1400561b9  sub     rsp, 20h
0x1400561bd  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x1400561c4  mov     rdi, rdx
0x1400561c7  mov     qword ptr [rdx], 0
0x1400561ce  mov     eax, [rsi]
0x1400561d0  mov     [rdx], eax
0x1400561d2  and     eax, 6
0x1400561d5  cmp     al, 6
0x1400561d7  jz      loc_14005627D
0x1400561dd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400561e2  lea     r8, [rsp+38h+arg_0]
0x1400561e7  mov     dword ptr [rsp+38h+arg_0], 0
0x1400561ef  lea     rdx, [rsp+38h+arg_8]
0x1400561f4  mov     ebp, eax
0x1400561f6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x1400561fb  mov     eax, [rdi]
0x1400561fd  mov     rbx, [rsp+38h+arg_8]
0x140056202  cmp     dword ptr [rsp+38h+arg_0], 0
0x140056207  mov     edx, eax
0x140056209  mov     [rdi], eax
0x14005620b  mov     ecx, eax
0x14005620d  jz      short loc_140056228
0x14005620f  test    dl, 2
0x140056212  jnz     short loc_140056228
0x140056214  and     ecx, 0FFFFF63Eh
0x14005621a  mov     eax, ebx
0x14005621c  and     eax, 9C1h
0x140056221  or      ecx, eax
0x140056223  or      ecx, 2
0x140056226  mov     [rdi], ecx
0x140056228  mov     r8d, edx
0x14005622b  and     r8d, 4
0x14005622f  jnz     short loc_140056243
0x140056231  btr     ecx, 0Ah
0x140056235  mov     eax, ebx
0x140056237  and     eax, 400h
0x14005623c  or      ecx, eax
0x14005623e  or      ecx, 4
0x140056241  mov     [rdi], ecx
0x140056243  mov     eax, edx
0x140056245  lock cmpxchg [rsi], ecx
0x140056249  jnz     short loc_140056202
0x14005624b  test    r8d, r8d
0x14005624e  jnz     short loc_140056268
0x140056250  mov     r9d, ebp
0x140056253  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14005625a  mov     r8d, 3
0x140056260  mov     rdx, rsi
0x140056263  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140056268  mov     eax, [rdi]
0x14005626a  test    al, 2
0x14005626c  jnz     short loc_14005627D
0x14005626e  and     eax, 0FFFFF63Eh
0x140056273  and     ebx, 9C1h
0x140056279  or      eax, ebx
0x14005627b  mov     [rdi], eax
0x14005627d  mov     rbx, [rsp+38h+arg_10]
0x140056282  mov     rax, rdi
0x140056285  add     rsp, 20h
0x140056289  pop     rdi
0x14005628a  pop     rsi
0x14005628b  pop     rbp
0x14005628c  retn
```
