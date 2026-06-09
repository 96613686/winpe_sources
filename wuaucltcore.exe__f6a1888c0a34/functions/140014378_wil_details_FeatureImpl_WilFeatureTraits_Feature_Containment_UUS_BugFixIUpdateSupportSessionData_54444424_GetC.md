# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCachedFeatureEnabledState(void)

- ea: `0x140014378`
- end: `0x140014462`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140014468`
- `0x140014514`

## callees

- `0x140005090`
- `0x140005154`
- `0x14001425c`
- `0x140014378`
- `0x14001aa60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v5; // ebp
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCurrentFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)a1, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140014378  mov     [rsp+arg_10], rbx
0x14001437d  push    rbp
0x14001437e  push    rsi
0x14001437f  push    rdi
0x140014380  sub     rsp, 40h
0x140014384  mov     rax, cs:__security_cookie
0x14001438b  xor     rax, rsp
0x14001438e  mov     [rsp+58h+var_28], rax
0x140014393  mov     qword ptr [rdx], 0
0x14001439a  mov     rdi, rdx
0x14001439d  mov     eax, [rcx]
0x14001439f  mov     rsi, rcx
0x1400143a2  mov     [rdx], eax
0x1400143a4  and     eax, 6
0x1400143a7  cmp     al, 6
0x1400143a9  jz      loc_140014445
0x1400143af  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400143b4  lea     r8, [rsp+58h+var_30]
0x1400143b9  mov     [rsp+58h+var_30], 0
0x1400143c1  lea     rdx, [rsp+58h+var_38]
0x1400143c6  mov     ebp, eax
0x1400143c8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCurrentFeatureEnabledState(int *)
0x1400143cd  mov     eax, [rdi]
0x1400143cf  mov     rbx, [rsp+58h+var_38]
0x1400143d4  cmp     [rsp+58h+var_30], 0
0x1400143d9  mov     edx, eax
0x1400143db  mov     [rdi], eax
0x1400143dd  mov     ecx, eax
0x1400143df  jz      short loc_1400143FA
0x1400143e1  test    dl, 2
0x1400143e4  jnz     short loc_1400143FA
0x1400143e6  and     ecx, 0FFFFF63Eh
0x1400143ec  mov     eax, ebx
0x1400143ee  and     eax, 9C1h
0x1400143f3  or      ecx, eax
0x1400143f5  or      ecx, 2
0x1400143f8  mov     [rdi], ecx
0x1400143fa  test    dl, 4
0x1400143fd  jnz     short loc_140014411
0x1400143ff  btr     ecx, 0Ah
0x140014403  mov     eax, ebx
0x140014405  and     eax, 400h
0x14001440a  or      ecx, eax
0x14001440c  or      ecx, 4
0x14001440f  mov     [rdi], ecx
0x140014411  mov     eax, edx
0x140014413  lock cmpxchg [rsi], ecx
0x140014417  jnz     short loc_1400143D4
0x140014419  test    dl, 4
0x14001441c  jnz     short loc_14001442E
0x14001441e  mov     r8d, ebp
0x140014421  mov     edx, 3
0x140014426  mov     rcx, rsi
0x140014429  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14001442e  mov     ecx, [rdi]
0x140014430  test    cl, 2
0x140014433  jnz     short loc_140014445
0x140014435  and     ecx, 0FFFFF63Eh
0x14001443b  and     ebx, 9C1h
0x140014441  or      ecx, ebx
0x140014443  mov     [rdi], ecx
0x140014445  mov     rax, rdi
0x140014448  mov     rcx, [rsp+58h+var_28]
0x14001444d  xor     rcx, rsp; StackCookie
0x140014450  call    __security_check_cookie
0x140014455  mov     rbx, [rsp+58h+arg_10]
0x14001445a  add     rsp, 40h
0x14001445e  pop     rdi
0x14001445f  pop     rsi
0x140014460  pop     rbp
0x140014461  retn
```
