# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::GetCachedFeatureEnabledState(void)

- ea: `0x1800162c8`
- end: `0x1800163b2`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180014ee4`
- `0x180015c9c`
- `0x180015cdc`

## callees

- `0x180010910`
- `0x1800109d4`
- `0x1800161ac`
- `0x1800162c8`
- `0x18002ffd0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::GetCachedFeatureEnabledState(
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::GetCurrentFeatureEnabledState(
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
0x1800162c8  mov     [rsp+arg_10], rbx
0x1800162cd  push    rbp
0x1800162ce  push    rsi
0x1800162cf  push    rdi
0x1800162d0  sub     rsp, 40h
0x1800162d4  mov     rax, cs:__security_cookie
0x1800162db  xor     rax, rsp
0x1800162de  mov     [rsp+58h+var_28], rax
0x1800162e3  mov     qword ptr [rdx], 0
0x1800162ea  mov     rdi, rdx
0x1800162ed  mov     eax, [rcx]
0x1800162ef  mov     rsi, rcx
0x1800162f2  mov     [rdx], eax
0x1800162f4  and     eax, 6
0x1800162f7  cmp     al, 6
0x1800162f9  jz      loc_180016395
0x1800162ff  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016304  lea     r8, [rsp+58h+var_30]
0x180016309  mov     [rsp+58h+var_30], 0
0x180016311  lea     rdx, [rsp+58h+var_38]
0x180016316  mov     ebp, eax
0x180016318  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::GetCurrentFeatureEnabledState(int *)
0x18001631d  mov     eax, [rdi]
0x18001631f  mov     rbx, [rsp+58h+var_38]
0x180016324  cmp     [rsp+58h+var_30], 0
0x180016329  mov     edx, eax
0x18001632b  mov     [rdi], eax
0x18001632d  mov     ecx, eax
0x18001632f  jz      short loc_18001634A
0x180016331  test    dl, 2
0x180016334  jnz     short loc_18001634A
0x180016336  and     ecx, 0FFFFF63Eh
0x18001633c  mov     eax, ebx
0x18001633e  and     eax, 9C1h
0x180016343  or      ecx, eax
0x180016345  or      ecx, 2
0x180016348  mov     [rdi], ecx
0x18001634a  test    dl, 4
0x18001634d  jnz     short loc_180016361
0x18001634f  btr     ecx, 0Ah
0x180016353  mov     eax, ebx
0x180016355  and     eax, 400h
0x18001635a  or      ecx, eax
0x18001635c  or      ecx, 4
0x18001635f  mov     [rdi], ecx
0x180016361  mov     eax, edx
0x180016363  lock cmpxchg [rsi], ecx
0x180016367  jnz     short loc_180016324
0x180016369  test    dl, 4
0x18001636c  jnz     short loc_18001637E
0x18001636e  mov     r8d, ebp
0x180016371  mov     edx, 3
0x180016376  mov     rcx, rsi
0x180016379  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001637e  mov     ecx, [rdi]
0x180016380  test    cl, 2
0x180016383  jnz     short loc_180016395
0x180016385  and     ecx, 0FFFFF63Eh
0x18001638b  and     ebx, 9C1h
0x180016391  or      ecx, ebx
0x180016393  mov     [rdi], ecx
0x180016395  mov     rax, rdi
0x180016398  mov     rcx, [rsp+58h+var_28]
0x18001639d  xor     rcx, rsp; StackCookie
0x1800163a0  call    __security_check_cookie
0x1800163a5  mov     rbx, [rsp+58h+arg_10]
0x1800163aa  add     rsp, 40h
0x1800163ae  pop     rdi
0x1800163af  pop     rsi
0x1800163b0  pop     rbp
0x1800163b1  retn
```
