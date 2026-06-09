# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::GetCachedFeatureEnabledState(void)

- ea: `0x140055bc4`
- end: `0x140055ca5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a77c`
- `0x14005d458`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x140055bc4`
- `0x1400567ec`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID58336780__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID58336780__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID58336780__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ID58336780__descriptor,
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
0x140055bc4  mov     [rsp+arg_10], rbx
0x140055bc9  mov     [rsp+arg_0], rcx
0x140055bce  push    rbp
0x140055bcf  push    rsi
0x140055bd0  push    rdi
0x140055bd1  sub     rsp, 20h
0x140055bd5  mov     rsi, cs:Feature_ID58336780__descriptor
0x140055bdc  mov     rdi, rdx
0x140055bdf  mov     qword ptr [rdx], 0
0x140055be6  mov     eax, [rsi]
0x140055be8  mov     [rdx], eax
0x140055bea  and     eax, 6
0x140055bed  cmp     al, 6
0x140055bef  jz      loc_140055C95
0x140055bf5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140055bfa  lea     r8, [rsp+38h+arg_0]
0x140055bff  mov     dword ptr [rsp+38h+arg_0], 0
0x140055c07  lea     rdx, [rsp+38h+arg_8]
0x140055c0c  mov     ebp, eax
0x140055c0e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::GetCurrentFeatureEnabledState(int *)
0x140055c13  mov     eax, [rdi]
0x140055c15  mov     rbx, [rsp+38h+arg_8]
0x140055c1a  cmp     dword ptr [rsp+38h+arg_0], 0
0x140055c1f  mov     edx, eax
0x140055c21  mov     [rdi], eax
0x140055c23  mov     ecx, eax
0x140055c25  jz      short loc_140055C40
0x140055c27  test    dl, 2
0x140055c2a  jnz     short loc_140055C40
0x140055c2c  and     ecx, 0FFFFF63Eh
0x140055c32  mov     eax, ebx
0x140055c34  and     eax, 9C1h
0x140055c39  or      ecx, eax
0x140055c3b  or      ecx, 2
0x140055c3e  mov     [rdi], ecx
0x140055c40  mov     r8d, edx
0x140055c43  and     r8d, 4
0x140055c47  jnz     short loc_140055C5B
0x140055c49  btr     ecx, 0Ah
0x140055c4d  mov     eax, ebx
0x140055c4f  and     eax, 400h
0x140055c54  or      ecx, eax
0x140055c56  or      ecx, 4
0x140055c59  mov     [rdi], ecx
0x140055c5b  mov     eax, edx
0x140055c5d  lock cmpxchg [rsi], ecx
0x140055c61  jnz     short loc_140055C1A
0x140055c63  test    r8d, r8d
0x140055c66  jnz     short loc_140055C80
0x140055c68  mov     r9d, ebp
0x140055c6b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140055c72  mov     r8d, 3
0x140055c78  mov     rdx, rsi
0x140055c7b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140055c80  mov     eax, [rdi]
0x140055c82  test    al, 2
0x140055c84  jnz     short loc_140055C95
0x140055c86  and     eax, 0FFFFF63Eh
0x140055c8b  and     ebx, 9C1h
0x140055c91  or      eax, ebx
0x140055c93  mov     [rdi], eax
0x140055c95  mov     rbx, [rsp+38h+arg_10]
0x140055c9a  mov     rax, rdi
0x140055c9d  add     rsp, 20h
0x140055ca1  pop     rdi
0x140055ca2  pop     rsi
0x140055ca3  pop     rbp
0x140055ca4  retn
```
