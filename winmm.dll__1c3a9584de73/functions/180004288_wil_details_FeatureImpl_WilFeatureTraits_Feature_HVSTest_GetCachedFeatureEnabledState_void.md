# wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180004288`
- end: `0x180004369`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HVSTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003fa0`

## callees

- `0x180004288`
- `0x1800044d0`
- `0x1800044f8`
- `0x180004628`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_HVSTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_HVSTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_HVSTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        Feature_HVSTest__descriptor,
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
0x180004288  mov     [rsp+arg_10], rbx
0x18000428d  mov     [rsp+arg_0], rcx
0x180004292  push    rbp
0x180004293  push    rsi
0x180004294  push    rdi
0x180004295  sub     rsp, 20h
0x180004299  mov     rsi, cs:Feature_HVSTest__descriptor
0x1800042a0  mov     rdi, rdx
0x1800042a3  mov     qword ptr [rdx], 0
0x1800042aa  mov     eax, [rsi]
0x1800042ac  mov     [rdx], eax
0x1800042ae  and     eax, 6
0x1800042b1  cmp     al, 6
0x1800042b3  jz      loc_180004359
0x1800042b9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800042be  lea     r8, [rsp+38h+arg_0]
0x1800042c3  mov     dword ptr [rsp+38h+arg_0], 0
0x1800042cb  lea     rdx, [rsp+38h+arg_8]
0x1800042d0  mov     ebp, eax
0x1800042d2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HVSTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest>::GetCurrentFeatureEnabledState(int *)
0x1800042d7  mov     eax, [rdi]
0x1800042d9  mov     rbx, [rsp+38h+arg_8]
0x1800042de  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800042e3  mov     edx, eax
0x1800042e5  mov     [rdi], eax
0x1800042e7  mov     ecx, eax
0x1800042e9  jz      short loc_180004304
0x1800042eb  test    dl, 2
0x1800042ee  jnz     short loc_180004304
0x1800042f0  and     ecx, 0FFFFF63Eh
0x1800042f6  mov     eax, ebx
0x1800042f8  and     eax, 9C1h
0x1800042fd  or      ecx, eax
0x1800042ff  or      ecx, 2
0x180004302  mov     [rdi], ecx
0x180004304  mov     r8d, edx
0x180004307  and     r8d, 4
0x18000430b  jnz     short loc_18000431F
0x18000430d  btr     ecx, 0Ah
0x180004311  mov     eax, ebx
0x180004313  and     eax, 400h
0x180004318  or      ecx, eax
0x18000431a  or      ecx, 4
0x18000431d  mov     [rdi], ecx
0x18000431f  mov     eax, edx
0x180004321  lock cmpxchg [rsi], ecx
0x180004325  jnz     short loc_1800042DE
0x180004327  test    r8d, r8d
0x18000432a  jnz     short loc_180004344
0x18000432c  mov     r9d, ebp
0x18000432f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004336  mov     r8d, 3
0x18000433c  mov     rdx, rsi
0x18000433f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180004344  mov     eax, [rdi]
0x180004346  test    al, 2
0x180004348  jnz     short loc_180004359
0x18000434a  and     eax, 0FFFFF63Eh
0x18000434f  and     ebx, 9C1h
0x180004355  or      eax, ebx
0x180004357  mov     [rdi], eax
0x180004359  mov     rbx, [rsp+38h+arg_10]
0x18000435e  mov     rax, rdi
0x180004361  add     rsp, 20h
0x180004365  pop     rdi
0x180004366  pop     rsi
0x180004367  pop     rbp
0x180004368  retn
```
