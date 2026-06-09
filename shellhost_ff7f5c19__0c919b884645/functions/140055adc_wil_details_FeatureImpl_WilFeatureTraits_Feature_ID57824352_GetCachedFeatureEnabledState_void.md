# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57824352>::GetCachedFeatureEnabledState(void)

- ea: `0x140055adc`
- end: `0x140055bbd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID57824352@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a6f4`
- `0x14005d41c`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x140055adc`
- `0x140056720`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57824352>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID57824352__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID57824352__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57824352>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID57824352__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ID57824352__descriptor,
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
0x140055adc  mov     [rsp+arg_10], rbx
0x140055ae1  mov     [rsp+arg_0], rcx
0x140055ae6  push    rbp
0x140055ae7  push    rsi
0x140055ae8  push    rdi
0x140055ae9  sub     rsp, 20h
0x140055aed  mov     rsi, cs:Feature_ID57824352__descriptor
0x140055af4  mov     rdi, rdx
0x140055af7  mov     qword ptr [rdx], 0
0x140055afe  mov     eax, [rsi]
0x140055b00  mov     [rdx], eax
0x140055b02  and     eax, 6
0x140055b05  cmp     al, 6
0x140055b07  jz      loc_140055BAD
0x140055b0d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140055b12  lea     r8, [rsp+38h+arg_0]
0x140055b17  mov     dword ptr [rsp+38h+arg_0], 0
0x140055b1f  lea     rdx, [rsp+38h+arg_8]
0x140055b24  mov     ebp, eax
0x140055b26  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID57824352@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57824352>::GetCurrentFeatureEnabledState(int *)
0x140055b2b  mov     eax, [rdi]
0x140055b2d  mov     rbx, [rsp+38h+arg_8]
0x140055b32  cmp     dword ptr [rsp+38h+arg_0], 0
0x140055b37  mov     edx, eax
0x140055b39  mov     [rdi], eax
0x140055b3b  mov     ecx, eax
0x140055b3d  jz      short loc_140055B58
0x140055b3f  test    dl, 2
0x140055b42  jnz     short loc_140055B58
0x140055b44  and     ecx, 0FFFFF63Eh
0x140055b4a  mov     eax, ebx
0x140055b4c  and     eax, 9C1h
0x140055b51  or      ecx, eax
0x140055b53  or      ecx, 2
0x140055b56  mov     [rdi], ecx
0x140055b58  mov     r8d, edx
0x140055b5b  and     r8d, 4
0x140055b5f  jnz     short loc_140055B73
0x140055b61  btr     ecx, 0Ah
0x140055b65  mov     eax, ebx
0x140055b67  and     eax, 400h
0x140055b6c  or      ecx, eax
0x140055b6e  or      ecx, 4
0x140055b71  mov     [rdi], ecx
0x140055b73  mov     eax, edx
0x140055b75  lock cmpxchg [rsi], ecx
0x140055b79  jnz     short loc_140055B32
0x140055b7b  test    r8d, r8d
0x140055b7e  jnz     short loc_140055B98
0x140055b80  mov     r9d, ebp
0x140055b83  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140055b8a  mov     r8d, 3
0x140055b90  mov     rdx, rsi
0x140055b93  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140055b98  mov     eax, [rdi]
0x140055b9a  test    al, 2
0x140055b9c  jnz     short loc_140055BAD
0x140055b9e  and     eax, 0FFFFF63Eh
0x140055ba3  and     ebx, 9C1h
0x140055ba9  or      eax, ebx
0x140055bab  mov     [rdi], eax
0x140055bad  mov     rbx, [rsp+38h+arg_10]
0x140055bb2  mov     rax, rdi
0x140055bb5  add     rsp, 20h
0x140055bb9  pop     rdi
0x140055bba  pop     rsi
0x140055bbb  pop     rbp
0x140055bbc  retn
```
