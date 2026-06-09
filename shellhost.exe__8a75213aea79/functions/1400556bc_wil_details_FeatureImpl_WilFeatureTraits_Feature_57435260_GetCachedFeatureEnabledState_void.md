# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57435260>::GetCachedFeatureEnabledState(void)

- ea: `0x1400556bc`
- end: `0x14005579d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57435260@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a558`
- `0x14005d368`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x1400556bc`
- `0x1400563fc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57435260>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_57435260__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57435260__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57435260>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57435260__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_57435260__descriptor,
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
0x1400556bc  mov     [rsp+arg_10], rbx
0x1400556c1  mov     [rsp+arg_0], rcx
0x1400556c6  push    rbp
0x1400556c7  push    rsi
0x1400556c8  push    rdi
0x1400556c9  sub     rsp, 20h
0x1400556cd  mov     rsi, cs:Feature_57435260__descriptor
0x1400556d4  mov     rdi, rdx
0x1400556d7  mov     qword ptr [rdx], 0
0x1400556de  mov     eax, [rsi]
0x1400556e0  mov     [rdx], eax
0x1400556e2  and     eax, 6
0x1400556e5  cmp     al, 6
0x1400556e7  jz      loc_14005578D
0x1400556ed  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400556f2  lea     r8, [rsp+38h+arg_0]
0x1400556f7  mov     dword ptr [rsp+38h+arg_0], 0
0x1400556ff  lea     rdx, [rsp+38h+arg_8]
0x140055704  mov     ebp, eax
0x140055706  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57435260@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57435260>::GetCurrentFeatureEnabledState(int *)
0x14005570b  mov     eax, [rdi]
0x14005570d  mov     rbx, [rsp+38h+arg_8]
0x140055712  cmp     dword ptr [rsp+38h+arg_0], 0
0x140055717  mov     edx, eax
0x140055719  mov     [rdi], eax
0x14005571b  mov     ecx, eax
0x14005571d  jz      short loc_140055738
0x14005571f  test    dl, 2
0x140055722  jnz     short loc_140055738
0x140055724  and     ecx, 0FFFFF63Eh
0x14005572a  mov     eax, ebx
0x14005572c  and     eax, 9C1h
0x140055731  or      ecx, eax
0x140055733  or      ecx, 2
0x140055736  mov     [rdi], ecx
0x140055738  mov     r8d, edx
0x14005573b  and     r8d, 4
0x14005573f  jnz     short loc_140055753
0x140055741  btr     ecx, 0Ah
0x140055745  mov     eax, ebx
0x140055747  and     eax, 400h
0x14005574c  or      ecx, eax
0x14005574e  or      ecx, 4
0x140055751  mov     [rdi], ecx
0x140055753  mov     eax, edx
0x140055755  lock cmpxchg [rsi], ecx
0x140055759  jnz     short loc_140055712
0x14005575b  test    r8d, r8d
0x14005575e  jnz     short loc_140055778
0x140055760  mov     r9d, ebp
0x140055763  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14005576a  mov     r8d, 3
0x140055770  mov     rdx, rsi
0x140055773  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140055778  mov     eax, [rdi]
0x14005577a  test    al, 2
0x14005577c  jnz     short loc_14005578D
0x14005577e  and     eax, 0FFFFF63Eh
0x140055783  and     ebx, 9C1h
0x140055789  or      eax, ebx
0x14005578b  mov     [rdi], eax
0x14005578d  mov     rbx, [rsp+38h+arg_10]
0x140055792  mov     rax, rdi
0x140055795  add     rsp, 20h
0x140055799  pop     rdi
0x14005579a  pop     rsi
0x14005579b  pop     rbp
0x14005579c  retn
```
