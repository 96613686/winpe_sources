# wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x1800026f8`
- end: `0x1800027e2`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800027e8`
- `0x180002884`

## callees

- `0x1800024e0`
- `0x1800026f8`
- `0x180003820`
- `0x180003aa8`
- `0x180010310`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
    wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 64, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800026f8  mov     [rsp+arg_10], rbx
0x1800026fd  push    rbp
0x1800026fe  push    rsi
0x1800026ff  push    rdi
0x180002700  sub     rsp, 40h
0x180002704  mov     rax, cs:__security_cookie
0x18000270b  xor     rax, rsp
0x18000270e  mov     [rsp+58h+var_28], rax
0x180002713  mov     qword ptr [rdx], 0
0x18000271a  mov     rdi, rdx
0x18000271d  mov     eax, [rcx]
0x18000271f  mov     rsi, rcx
0x180002722  mov     [rdx], eax
0x180002724  and     eax, 6
0x180002727  cmp     al, 6
0x180002729  jz      loc_1800027C5
0x18000272f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180002734  lea     r8, [rsp+58h+var_30]
0x180002739  mov     [rsp+58h+var_30], 0
0x180002741  lea     rdx, [rsp+58h+var_38]
0x180002746  mov     ebp, eax
0x180002748  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18000274d  mov     eax, [rdi]
0x18000274f  mov     rbx, [rsp+58h+var_38]
0x180002754  cmp     [rsp+58h+var_30], 0
0x180002759  mov     edx, eax
0x18000275b  mov     [rdi], eax
0x18000275d  mov     ecx, eax
0x18000275f  jz      short loc_18000277A
0x180002761  test    dl, 2
0x180002764  jnz     short loc_18000277A
0x180002766  and     ecx, 0FFFFF63Eh
0x18000276c  mov     eax, ebx
0x18000276e  and     eax, 9C1h
0x180002773  or      ecx, eax
0x180002775  or      ecx, 2
0x180002778  mov     [rdi], ecx
0x18000277a  test    dl, 4
0x18000277d  jnz     short loc_180002791
0x18000277f  btr     ecx, 0Ah
0x180002783  mov     eax, ebx
0x180002785  and     eax, 400h
0x18000278a  or      ecx, eax
0x18000278c  or      ecx, 4
0x18000278f  mov     [rdi], ecx
0x180002791  mov     eax, edx
0x180002793  lock cmpxchg [rsi], ecx
0x180002797  jnz     short loc_180002754
0x180002799  test    dl, 4
0x18000279c  jnz     short loc_1800027AE
0x18000279e  mov     r8d, ebp
0x1800027a1  mov     edx, 40h ; '@'
0x1800027a6  mov     rcx, rsi
0x1800027a9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800027ae  mov     ecx, [rdi]
0x1800027b0  test    cl, 2
0x1800027b3  jnz     short loc_1800027C5
0x1800027b5  and     ecx, 0FFFFF63Eh
0x1800027bb  and     ebx, 9C1h
0x1800027c1  or      ecx, ebx
0x1800027c3  mov     [rdi], ecx
0x1800027c5  mov     rax, rdi
0x1800027c8  mov     rcx, [rsp+58h+var_28]
0x1800027cd  xor     rcx, rsp; StackCookie
0x1800027d0  call    __security_check_cookie
0x1800027d5  mov     rbx, [rsp+58h+arg_10]
0x1800027da  add     rsp, 40h
0x1800027de  pop     rdi
0x1800027df  pop     rsi
0x1800027e0  pop     rbp
0x1800027e1  retn
```
