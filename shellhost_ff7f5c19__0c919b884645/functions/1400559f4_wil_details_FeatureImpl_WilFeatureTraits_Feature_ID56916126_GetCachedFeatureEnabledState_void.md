# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCachedFeatureEnabledState(void)

- ea: `0x1400559f4`
- end: `0x140055ad5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a66c`
- `0x14005d3e0`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x1400559f4`
- `0x140056594`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  int *v7; // r9
  signed __int32 v8; // eax
  __int16 v9; // bx
  bool v10; // zf
  signed __int32 v11; // edx
  unsigned int v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ID56916126__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID56916126__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCurrentFeatureEnabledState(
      v6,
      &v15,
      (enum FEATURE_CHANGE_TIME)&v14,
      v7);
    v8 = *(_DWORD *)a2;
    v9 = v15;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v8;
      *(_DWORD *)a2 = v8;
      v12 = v8;
      if ( !v10 && (v8 & 2) == 0 )
      {
        v12 = v9 & 0x9C1 | v8 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v8 & 4) == 0 )
      {
        v12 = v9 & 0x400 | v12 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v12;
      }
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID56916126__descriptor, v12, v8);
    }
    while ( v11 != v8 );
    if ( (v11 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ID56916126__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v9 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1400559f4  mov     [rsp+arg_10], rbx
0x1400559f9  mov     [rsp+arg_0], rcx
0x1400559fe  push    rbp
0x1400559ff  push    rsi
0x140055a00  push    rdi
0x140055a01  sub     rsp, 20h
0x140055a05  mov     rsi, cs:Feature_ID56916126__descriptor
0x140055a0c  mov     rdi, rdx
0x140055a0f  mov     qword ptr [rdx], 0
0x140055a16  mov     eax, [rsi]
0x140055a18  mov     [rdx], eax
0x140055a1a  and     eax, 6
0x140055a1d  cmp     al, 6
0x140055a1f  jz      loc_140055AC5
0x140055a25  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140055a2a  lea     r8, [rsp+38h+arg_0]
0x140055a2f  mov     dword ptr [rsp+38h+arg_0], 0
0x140055a37  lea     rdx, [rsp+38h+arg_8]
0x140055a3c  mov     ebp, eax
0x140055a3e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCurrentFeatureEnabledState(int *)
0x140055a43  mov     eax, [rdi]
0x140055a45  mov     rbx, [rsp+38h+arg_8]
0x140055a4a  cmp     dword ptr [rsp+38h+arg_0], 0
0x140055a4f  mov     edx, eax
0x140055a51  mov     [rdi], eax
0x140055a53  mov     ecx, eax
0x140055a55  jz      short loc_140055A70
0x140055a57  test    dl, 2
0x140055a5a  jnz     short loc_140055A70
0x140055a5c  and     ecx, 0FFFFF63Eh
0x140055a62  mov     eax, ebx
0x140055a64  and     eax, 9C1h
0x140055a69  or      ecx, eax
0x140055a6b  or      ecx, 2
0x140055a6e  mov     [rdi], ecx
0x140055a70  mov     r8d, edx
0x140055a73  and     r8d, 4
0x140055a77  jnz     short loc_140055A8B
0x140055a79  btr     ecx, 0Ah
0x140055a7d  mov     eax, ebx
0x140055a7f  and     eax, 400h
0x140055a84  or      ecx, eax
0x140055a86  or      ecx, 4
0x140055a89  mov     [rdi], ecx
0x140055a8b  mov     eax, edx
0x140055a8d  lock cmpxchg [rsi], ecx
0x140055a91  jnz     short loc_140055A4A
0x140055a93  test    r8d, r8d
0x140055a96  jnz     short loc_140055AB0
0x140055a98  mov     r9d, ebp
0x140055a9b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140055aa2  mov     r8d, 3
0x140055aa8  mov     rdx, rsi
0x140055aab  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140055ab0  mov     eax, [rdi]
0x140055ab2  test    al, 2
0x140055ab4  jnz     short loc_140055AC5
0x140055ab6  and     eax, 0FFFFF63Eh
0x140055abb  and     ebx, 9C1h
0x140055ac1  or      eax, ebx
0x140055ac3  mov     [rdi], eax
0x140055ac5  mov     rbx, [rsp+38h+arg_10]
0x140055aca  mov     rax, rdi
0x140055acd  add     rsp, 20h
0x140055ad1  pop     rdi
0x140055ad2  pop     rsi
0x140055ad3  pop     rbp
0x140055ad4  retn
```
