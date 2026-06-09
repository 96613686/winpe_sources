# wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetCachedFeatureEnabledState(void)

- ea: `0x180018170`
- end: `0x180018253`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017c48`

## callees

- `0x180018170`
- `0x18001e3e8`
- `0x18001e8bc`
- `0x180021bc8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetCachedFeatureEnabledState(
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
  int v12; // r8d
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_FixSmartcardRedirection_Deadlock__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_FixSmartcardRedirection_Deadlock__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetCurrentFeatureEnabledState(
      v6,
      &v15,
      &v14);
    if ( !v5 )
      LODWORD(v14) = 0;
    v7 = *(_DWORD *)a2;
    v8 = v15;
    do
    {
      v9 = (_DWORD)v14 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_FixSmartcardRedirection_Deadlock__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (unsigned int *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_FixSmartcardRedirection_Deadlock__descriptor,
        0,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180018170  mov     [rsp+arg_10], rbx
0x180018175  mov     [rsp+arg_0], rcx
0x18001817a  push    rbp
0x18001817b  push    rsi
0x18001817c  push    rdi
0x18001817d  sub     rsp, 20h
0x180018181  mov     rsi, cs:Feature_FixSmartcardRedirection_Deadlock__descriptor
0x180018188  mov     rdi, rdx
0x18001818b  mov     qword ptr [rdx], 0
0x180018192  mov     eax, [rsi]
0x180018194  mov     [rdx], eax
0x180018196  and     eax, 6
0x180018199  cmp     al, 6
0x18001819b  jz      loc_180018243
0x1800181a1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800181a6  lea     r8, [rsp+38h+arg_0]
0x1800181ab  mov     dword ptr [rsp+38h+arg_0], 0
0x1800181b3  lea     rdx, [rsp+38h+arg_8]
0x1800181b8  mov     ebp, eax
0x1800181ba  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetCurrentFeatureEnabledState(int *)
0x1800181bf  test    ebp, ebp
0x1800181c1  jnz     short loc_1800181C7
0x1800181c3  mov     dword ptr [rsp+38h+arg_0], ebp
0x1800181c7  mov     eax, [rdi]
0x1800181c9  mov     rbx, [rsp+38h+arg_8]
0x1800181ce  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800181d3  mov     edx, eax
0x1800181d5  mov     [rdi], eax
0x1800181d7  mov     ecx, eax
0x1800181d9  jz      short loc_1800181F4
0x1800181db  test    dl, 2
0x1800181de  jnz     short loc_1800181F4
0x1800181e0  and     ecx, 0FFFFF63Eh
0x1800181e6  mov     eax, ebx
0x1800181e8  and     eax, 9C1h
0x1800181ed  or      ecx, eax
0x1800181ef  or      ecx, 2
0x1800181f2  mov     [rdi], ecx
0x1800181f4  mov     r8d, edx
0x1800181f7  and     r8d, 4
0x1800181fb  jnz     short loc_18001820F
0x1800181fd  btr     ecx, 0Ah
0x180018201  mov     eax, ebx
0x180018203  and     eax, 400h
0x180018208  or      ecx, eax
0x18001820a  or      ecx, 4
0x18001820d  mov     [rdi], ecx
0x18001820f  mov     eax, edx
0x180018211  lock cmpxchg [rsi], ecx
0x180018215  jnz     short loc_1800181CE
0x180018217  test    r8d, r8d
0x18001821a  jnz     short loc_18001822E
0x18001821c  mov     r9d, ebp
0x18001821f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180018226  mov     rdx, rsi
0x180018229  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001822e  mov     eax, [rdi]
0x180018230  test    al, 2
0x180018232  jnz     short loc_180018243
0x180018234  and     eax, 0FFFFF63Eh
0x180018239  and     ebx, 9C1h
0x18001823f  or      eax, ebx
0x180018241  mov     [rdi], eax
0x180018243  mov     rbx, [rsp+38h+arg_10]
0x180018248  mov     rax, rdi
0x18001824b  add     rsp, 20h
0x18001824f  pop     rdi
0x180018250  pop     rsi
0x180018251  pop     rbp
0x180018252  retn
```
