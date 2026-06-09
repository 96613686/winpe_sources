# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetCachedFeatureEnabledState(void)

- ea: `0x180014a0c`
- end: `0x180014aed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014d14`
- `0x180015024`

## callees

- `0x18000bccc`
- `0x18000d3b8`
- `0x180014a0c`
- `0x180014af4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_WinIoTBugFixBundle_Ge_6__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WinIoTBugFixBundle_Ge_6__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_WinIoTBugFixBundle_Ge_6__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        Feature_WinIoTBugFixBundle_Ge_6__descriptor,
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
0x180014a0c  mov     [rsp+arg_10], rbx
0x180014a11  mov     [rsp+arg_0], rcx
0x180014a16  push    rbp
0x180014a17  push    rsi
0x180014a18  push    rdi
0x180014a19  sub     rsp, 20h
0x180014a1d  mov     rsi, cs:Feature_WinIoTBugFixBundle_Ge_6__descriptor
0x180014a24  mov     rdi, rdx
0x180014a27  mov     qword ptr [rdx], 0
0x180014a2e  mov     eax, [rsi]
0x180014a30  mov     [rdx], eax
0x180014a32  and     eax, 6
0x180014a35  cmp     al, 6
0x180014a37  jz      loc_180014ADD
0x180014a3d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014a42  lea     r8, [rsp+38h+arg_0]
0x180014a47  mov     dword ptr [rsp+38h+arg_0], 0
0x180014a4f  lea     rdx, [rsp+38h+arg_8]
0x180014a54  mov     ebp, eax
0x180014a56  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetCurrentFeatureEnabledState(int *)
0x180014a5b  mov     eax, [rdi]
0x180014a5d  mov     rbx, [rsp+38h+arg_8]
0x180014a62  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014a67  mov     edx, eax
0x180014a69  mov     [rdi], eax
0x180014a6b  mov     ecx, eax
0x180014a6d  jz      short loc_180014A88
0x180014a6f  test    dl, 2
0x180014a72  jnz     short loc_180014A88
0x180014a74  and     ecx, 0FFFFF63Eh
0x180014a7a  mov     eax, ebx
0x180014a7c  and     eax, 9C1h
0x180014a81  or      ecx, eax
0x180014a83  or      ecx, 2
0x180014a86  mov     [rdi], ecx
0x180014a88  mov     r8d, edx
0x180014a8b  and     r8d, 4
0x180014a8f  jnz     short loc_180014AA3
0x180014a91  btr     ecx, 0Ah
0x180014a95  mov     eax, ebx
0x180014a97  and     eax, 400h
0x180014a9c  or      ecx, eax
0x180014a9e  or      ecx, 4
0x180014aa1  mov     [rdi], ecx
0x180014aa3  mov     eax, edx
0x180014aa5  lock cmpxchg [rsi], ecx
0x180014aa9  jnz     short loc_180014A62
0x180014aab  test    r8d, r8d
0x180014aae  jnz     short loc_180014AC8
0x180014ab0  mov     r9d, ebp
0x180014ab3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014aba  mov     r8d, 3
0x180014ac0  mov     rdx, rsi
0x180014ac3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014ac8  mov     eax, [rdi]
0x180014aca  test    al, 2
0x180014acc  jnz     short loc_180014ADD
0x180014ace  and     eax, 0FFFFF63Eh
0x180014ad3  and     ebx, 9C1h
0x180014ad9  or      eax, ebx
0x180014adb  mov     [rdi], eax
0x180014add  mov     rbx, [rsp+38h+arg_10]
0x180014ae2  mov     rax, rdi
0x180014ae5  add     rsp, 20h
0x180014ae9  pop     rdi
0x180014aea  pop     rsi
0x180014aeb  pop     rbp
0x180014aec  retn
```
