# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::GetCachedFeatureEnabledState(void)

- ea: `0x140055cac`
- end: `0x140055d8d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a804`
- `0x14005d494`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x140055cac`
- `0x1400568dc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID59213523__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID59213523__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID59213523__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ID59213523__descriptor,
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
0x140055cac  mov     [rsp+arg_10], rbx
0x140055cb1  mov     [rsp+arg_0], rcx
0x140055cb6  push    rbp
0x140055cb7  push    rsi
0x140055cb8  push    rdi
0x140055cb9  sub     rsp, 20h
0x140055cbd  mov     rsi, cs:Feature_ID59213523__descriptor
0x140055cc4  mov     rdi, rdx
0x140055cc7  mov     qword ptr [rdx], 0
0x140055cce  mov     eax, [rsi]
0x140055cd0  mov     [rdx], eax
0x140055cd2  and     eax, 6
0x140055cd5  cmp     al, 6
0x140055cd7  jz      loc_140055D7D
0x140055cdd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140055ce2  lea     r8, [rsp+38h+arg_0]
0x140055ce7  mov     dword ptr [rsp+38h+arg_0], 0
0x140055cef  lea     rdx, [rsp+38h+arg_8]
0x140055cf4  mov     ebp, eax
0x140055cf6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::GetCurrentFeatureEnabledState(int *)
0x140055cfb  mov     eax, [rdi]
0x140055cfd  mov     rbx, [rsp+38h+arg_8]
0x140055d02  cmp     dword ptr [rsp+38h+arg_0], 0
0x140055d07  mov     edx, eax
0x140055d09  mov     [rdi], eax
0x140055d0b  mov     ecx, eax
0x140055d0d  jz      short loc_140055D28
0x140055d0f  test    dl, 2
0x140055d12  jnz     short loc_140055D28
0x140055d14  and     ecx, 0FFFFF63Eh
0x140055d1a  mov     eax, ebx
0x140055d1c  and     eax, 9C1h
0x140055d21  or      ecx, eax
0x140055d23  or      ecx, 2
0x140055d26  mov     [rdi], ecx
0x140055d28  mov     r8d, edx
0x140055d2b  and     r8d, 4
0x140055d2f  jnz     short loc_140055D43
0x140055d31  btr     ecx, 0Ah
0x140055d35  mov     eax, ebx
0x140055d37  and     eax, 400h
0x140055d3c  or      ecx, eax
0x140055d3e  or      ecx, 4
0x140055d41  mov     [rdi], ecx
0x140055d43  mov     eax, edx
0x140055d45  lock cmpxchg [rsi], ecx
0x140055d49  jnz     short loc_140055D02
0x140055d4b  test    r8d, r8d
0x140055d4e  jnz     short loc_140055D68
0x140055d50  mov     r9d, ebp
0x140055d53  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140055d5a  mov     r8d, 3
0x140055d60  mov     rdx, rsi
0x140055d63  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140055d68  mov     eax, [rdi]
0x140055d6a  test    al, 2
0x140055d6c  jnz     short loc_140055D7D
0x140055d6e  and     eax, 0FFFFF63Eh
0x140055d73  and     ebx, 9C1h
0x140055d79  or      eax, ebx
0x140055d7b  mov     [rdi], eax
0x140055d7d  mov     rbx, [rsp+38h+arg_10]
0x140055d82  mov     rax, rdi
0x140055d85  add     rsp, 20h
0x140055d89  pop     rdi
0x140055d8a  pop     rsi
0x140055d8b  pop     rbp
0x140055d8c  retn
```
