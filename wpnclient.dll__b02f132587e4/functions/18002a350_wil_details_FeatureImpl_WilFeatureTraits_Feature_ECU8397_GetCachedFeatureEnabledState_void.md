# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECU8397>::GetCachedFeatureEnabledState(void)

- ea: `0x18002a350`
- end: `0x18002a431`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ECU8397@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b540`
- `0x18002c1e4`

## callees

- `0x180029c18`
- `0x18002a350`
- `0x18002a67c`
- `0x18002bacc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECU8397>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ECU8397__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ECU8397__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECU8397>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ECU8397__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ECU8397__descriptor,
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
0x18002a350  mov     [rsp+arg_10], rbx
0x18002a355  mov     [rsp+arg_0], rcx
0x18002a35a  push    rbp
0x18002a35b  push    rsi
0x18002a35c  push    rdi
0x18002a35d  sub     rsp, 20h
0x18002a361  mov     rsi, cs:Feature_ECU8397__descriptor
0x18002a368  mov     rdi, rdx
0x18002a36b  mov     qword ptr [rdx], 0
0x18002a372  mov     eax, [rsi]
0x18002a374  mov     [rdx], eax
0x18002a376  and     eax, 6
0x18002a379  cmp     al, 6
0x18002a37b  jz      loc_18002A421
0x18002a381  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002a386  lea     r8, [rsp+38h+arg_0]
0x18002a38b  mov     dword ptr [rsp+38h+arg_0], 0
0x18002a393  lea     rdx, [rsp+38h+arg_8]
0x18002a398  mov     ebp, eax
0x18002a39a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ECU8397@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECU8397>::GetCurrentFeatureEnabledState(int *)
0x18002a39f  mov     eax, [rdi]
0x18002a3a1  mov     rbx, [rsp+38h+arg_8]
0x18002a3a6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002a3ab  mov     edx, eax
0x18002a3ad  mov     [rdi], eax
0x18002a3af  mov     ecx, eax
0x18002a3b1  jz      short loc_18002A3CC
0x18002a3b3  test    dl, 2
0x18002a3b6  jnz     short loc_18002A3CC
0x18002a3b8  and     ecx, 0FFFFF63Eh
0x18002a3be  mov     eax, ebx
0x18002a3c0  and     eax, 9C1h
0x18002a3c5  or      ecx, eax
0x18002a3c7  or      ecx, 2
0x18002a3ca  mov     [rdi], ecx
0x18002a3cc  mov     r8d, edx
0x18002a3cf  and     r8d, 4
0x18002a3d3  jnz     short loc_18002A3E7
0x18002a3d5  btr     ecx, 0Ah
0x18002a3d9  mov     eax, ebx
0x18002a3db  and     eax, 400h
0x18002a3e0  or      ecx, eax
0x18002a3e2  or      ecx, 4
0x18002a3e5  mov     [rdi], ecx
0x18002a3e7  mov     eax, edx
0x18002a3e9  lock cmpxchg [rsi], ecx
0x18002a3ed  jnz     short loc_18002A3A6
0x18002a3ef  test    r8d, r8d
0x18002a3f2  jnz     short loc_18002A40C
0x18002a3f4  mov     r9d, ebp
0x18002a3f7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002a3fe  mov     r8d, 3
0x18002a404  mov     rdx, rsi
0x18002a407  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002a40c  mov     eax, [rdi]
0x18002a40e  test    al, 2
0x18002a410  jnz     short loc_18002A421
0x18002a412  and     eax, 0FFFFF63Eh
0x18002a417  and     ebx, 9C1h
0x18002a41d  or      eax, ebx
0x18002a41f  mov     [rdi], eax
0x18002a421  mov     rbx, [rsp+38h+arg_10]
0x18002a426  mov     rax, rdi
0x18002a429  add     rsp, 20h
0x18002a42d  pop     rdi
0x18002a42e  pop     rsi
0x18002a42f  pop     rbp
0x18002a430  retn
```
