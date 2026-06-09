# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCachedFeatureEnabledState(void)

- ea: `0x140055d94`
- end: `0x140055e75`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59399909@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a88c`
- `0x14005d4d0`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x140055d94`
- `0x1400569c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID59399909__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID59399909__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID59399909__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ID59399909__descriptor,
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
0x140055d94  mov     [rsp+arg_10], rbx
0x140055d99  mov     [rsp+arg_0], rcx
0x140055d9e  push    rbp
0x140055d9f  push    rsi
0x140055da0  push    rdi
0x140055da1  sub     rsp, 20h
0x140055da5  mov     rsi, cs:Feature_ID59399909__descriptor
0x140055dac  mov     rdi, rdx
0x140055daf  mov     qword ptr [rdx], 0
0x140055db6  mov     eax, [rsi]
0x140055db8  mov     [rdx], eax
0x140055dba  and     eax, 6
0x140055dbd  cmp     al, 6
0x140055dbf  jz      loc_140055E65
0x140055dc5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140055dca  lea     r8, [rsp+38h+arg_0]
0x140055dcf  mov     dword ptr [rsp+38h+arg_0], 0
0x140055dd7  lea     rdx, [rsp+38h+arg_8]
0x140055ddc  mov     ebp, eax
0x140055dde  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59399909@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCurrentFeatureEnabledState(int *)
0x140055de3  mov     eax, [rdi]
0x140055de5  mov     rbx, [rsp+38h+arg_8]
0x140055dea  cmp     dword ptr [rsp+38h+arg_0], 0
0x140055def  mov     edx, eax
0x140055df1  mov     [rdi], eax
0x140055df3  mov     ecx, eax
0x140055df5  jz      short loc_140055E10
0x140055df7  test    dl, 2
0x140055dfa  jnz     short loc_140055E10
0x140055dfc  and     ecx, 0FFFFF63Eh
0x140055e02  mov     eax, ebx
0x140055e04  and     eax, 9C1h
0x140055e09  or      ecx, eax
0x140055e0b  or      ecx, 2
0x140055e0e  mov     [rdi], ecx
0x140055e10  mov     r8d, edx
0x140055e13  and     r8d, 4
0x140055e17  jnz     short loc_140055E2B
0x140055e19  btr     ecx, 0Ah
0x140055e1d  mov     eax, ebx
0x140055e1f  and     eax, 400h
0x140055e24  or      ecx, eax
0x140055e26  or      ecx, 4
0x140055e29  mov     [rdi], ecx
0x140055e2b  mov     eax, edx
0x140055e2d  lock cmpxchg [rsi], ecx
0x140055e31  jnz     short loc_140055DEA
0x140055e33  test    r8d, r8d
0x140055e36  jnz     short loc_140055E50
0x140055e38  mov     r9d, ebp
0x140055e3b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140055e42  mov     r8d, 3
0x140055e48  mov     rdx, rsi
0x140055e4b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140055e50  mov     eax, [rdi]
0x140055e52  test    al, 2
0x140055e54  jnz     short loc_140055E65
0x140055e56  and     eax, 0FFFFF63Eh
0x140055e5b  and     ebx, 9C1h
0x140055e61  or      eax, ebx
0x140055e63  mov     [rdi], eax
0x140055e65  mov     rbx, [rsp+38h+arg_10]
0x140055e6a  mov     rax, rdi
0x140055e6d  add     rsp, 20h
0x140055e71  pop     rdi
0x140055e72  pop     rsi
0x140055e73  pop     rbp
0x140055e74  retn
```
