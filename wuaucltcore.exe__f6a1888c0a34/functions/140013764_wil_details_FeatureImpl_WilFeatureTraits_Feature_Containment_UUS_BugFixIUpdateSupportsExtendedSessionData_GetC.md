# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCachedFeatureEnabledState(void)

- ea: `0x140013764`
- end: `0x14001384e`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140013728`
- `0x140013854`

## callees

- `0x140005090`
- `0x140005154`
- `0x140013764`
- `0x140013938`
- `0x14001aa60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCachedFeatureEnabledState(
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCurrentFeatureEnabledState(
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
0x140013764  mov     [rsp+arg_10], rbx
0x140013769  push    rbp
0x14001376a  push    rsi
0x14001376b  push    rdi
0x14001376c  sub     rsp, 40h
0x140013770  mov     rax, cs:__security_cookie
0x140013777  xor     rax, rsp
0x14001377a  mov     [rsp+58h+var_28], rax
0x14001377f  mov     qword ptr [rdx], 0
0x140013786  mov     rdi, rdx
0x140013789  mov     eax, [rcx]
0x14001378b  mov     rsi, rcx
0x14001378e  mov     [rdx], eax
0x140013790  and     eax, 6
0x140013793  cmp     al, 6
0x140013795  jz      loc_140013831
0x14001379b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400137a0  lea     r8, [rsp+58h+var_30]
0x1400137a5  mov     [rsp+58h+var_30], 0
0x1400137ad  lea     rdx, [rsp+58h+var_38]
0x1400137b2  mov     ebp, eax
0x1400137b4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCurrentFeatureEnabledState(int *)
0x1400137b9  mov     eax, [rdi]
0x1400137bb  mov     rbx, [rsp+58h+var_38]
0x1400137c0  cmp     [rsp+58h+var_30], 0
0x1400137c5  mov     edx, eax
0x1400137c7  mov     [rdi], eax
0x1400137c9  mov     ecx, eax
0x1400137cb  jz      short loc_1400137E6
0x1400137cd  test    dl, 2
0x1400137d0  jnz     short loc_1400137E6
0x1400137d2  and     ecx, 0FFFFF63Eh
0x1400137d8  mov     eax, ebx
0x1400137da  and     eax, 9C1h
0x1400137df  or      ecx, eax
0x1400137e1  or      ecx, 2
0x1400137e4  mov     [rdi], ecx
0x1400137e6  test    dl, 4
0x1400137e9  jnz     short loc_1400137FD
0x1400137eb  btr     ecx, 0Ah
0x1400137ef  mov     eax, ebx
0x1400137f1  and     eax, 400h
0x1400137f6  or      ecx, eax
0x1400137f8  or      ecx, 4
0x1400137fb  mov     [rdi], ecx
0x1400137fd  mov     eax, edx
0x1400137ff  lock cmpxchg [rsi], ecx
0x140013803  jnz     short loc_1400137C0
0x140013805  test    dl, 4
0x140013808  jnz     short loc_14001381A
0x14001380a  mov     r8d, ebp
0x14001380d  mov     edx, 3
0x140013812  mov     rcx, rsi
0x140013815  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14001381a  mov     ecx, [rdi]
0x14001381c  test    cl, 2
0x14001381f  jnz     short loc_140013831
0x140013821  and     ecx, 0FFFFF63Eh
0x140013827  and     ebx, 9C1h
0x14001382d  or      ecx, ebx
0x14001382f  mov     [rdi], ecx
0x140013831  mov     rax, rdi
0x140013834  mov     rcx, [rsp+58h+var_28]
0x140013839  xor     rcx, rsp; StackCookie
0x14001383c  call    __security_check_cookie
0x140013841  mov     rbx, [rsp+58h+arg_10]
0x140013846  add     rsp, 40h
0x14001384a  pop     rdi
0x14001384b  pop     rsi
0x14001384c  pop     rbp
0x14001384d  retn
```
