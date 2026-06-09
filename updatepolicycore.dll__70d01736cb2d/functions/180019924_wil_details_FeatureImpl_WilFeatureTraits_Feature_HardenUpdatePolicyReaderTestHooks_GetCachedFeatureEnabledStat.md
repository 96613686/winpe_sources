# wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::GetCachedFeatureEnabledState(void)

- ea: `0x180019924`
- end: `0x180019a0e`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800196a4`
- `0x180019a14`

## callees

- `0x180010910`
- `0x1800109d4`
- `0x180019924`
- `0x180019ab4`
- `0x18002ffd0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  __int64 v13; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+28h] [rbp-30h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) != 6 )
  {
    v14 = 0;
    v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::GetCurrentFeatureEnabledState(
      v6,
      &v13,
      &v14);
    v7 = *(_DWORD *)a2;
    v8 = v13;
    do
    {
      v9 = v14 == 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180019924  mov     [rsp+arg_10], rbx
0x180019929  push    rbp
0x18001992a  push    rsi
0x18001992b  push    rdi
0x18001992c  sub     rsp, 40h
0x180019930  mov     rax, cs:__security_cookie
0x180019937  xor     rax, rsp
0x18001993a  mov     [rsp+58h+var_28], rax
0x18001993f  mov     qword ptr [rdx], 0
0x180019946  mov     rdi, rdx
0x180019949  mov     eax, [rcx]
0x18001994b  mov     rsi, rcx
0x18001994e  mov     [rdx], eax
0x180019950  and     eax, 6
0x180019953  cmp     al, 6
0x180019955  jz      loc_1800199F1
0x18001995b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180019960  lea     r8, [rsp+58h+var_30]
0x180019965  mov     [rsp+58h+var_30], 0
0x18001996d  lea     rdx, [rsp+58h+var_38]
0x180019972  mov     ebp, eax
0x180019974  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::GetCurrentFeatureEnabledState(int *)
0x180019979  mov     eax, [rdi]
0x18001997b  mov     rbx, [rsp+58h+var_38]
0x180019980  cmp     [rsp+58h+var_30], 0
0x180019985  mov     edx, eax
0x180019987  mov     [rdi], eax
0x180019989  mov     ecx, eax
0x18001998b  jz      short loc_1800199A6
0x18001998d  test    dl, 2
0x180019990  jnz     short loc_1800199A6
0x180019992  and     ecx, 0FFFFF63Eh
0x180019998  mov     eax, ebx
0x18001999a  and     eax, 9C1h
0x18001999f  or      ecx, eax
0x1800199a1  or      ecx, 2
0x1800199a4  mov     [rdi], ecx
0x1800199a6  test    dl, 4
0x1800199a9  jnz     short loc_1800199BD
0x1800199ab  btr     ecx, 0Ah
0x1800199af  mov     eax, ebx
0x1800199b1  and     eax, 400h
0x1800199b6  or      ecx, eax
0x1800199b8  or      ecx, 4
0x1800199bb  mov     [rdi], ecx
0x1800199bd  mov     eax, edx
0x1800199bf  lock cmpxchg [rsi], ecx
0x1800199c3  jnz     short loc_180019980
0x1800199c5  test    dl, 4
0x1800199c8  jnz     short loc_1800199DA
0x1800199ca  mov     r8d, ebp
0x1800199cd  mov     edx, 3
0x1800199d2  mov     rcx, rsi
0x1800199d5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800199da  mov     ecx, [rdi]
0x1800199dc  test    cl, 2
0x1800199df  jnz     short loc_1800199F1
0x1800199e1  and     ecx, 0FFFFF63Eh
0x1800199e7  and     ebx, 9C1h
0x1800199ed  or      ecx, ebx
0x1800199ef  mov     [rdi], ecx
0x1800199f1  mov     rax, rdi
0x1800199f4  mov     rcx, [rsp+58h+var_28]
0x1800199f9  xor     rcx, rsp; StackCookie
0x1800199fc  call    __security_check_cookie
0x180019a01  mov     rbx, [rsp+58h+arg_10]
0x180019a06  add     rsp, 40h
0x180019a0a  pop     rdi
0x180019a0b  pop     rsi
0x180019a0c  pop     rbp
0x180019a0d  retn
```
