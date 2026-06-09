# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCachedFeatureEnabledState(void)

- ea: `0x180002214`
- end: `0x1800022fe`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800021d8`
- `0x180002304`

## callees

- `0x180002214`
- `0x1800023a4`
- `0x180003820`
- `0x180003aa8`
- `0x180010310`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCachedFeatureEnabledState(
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCurrentFeatureEnabledState(
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
0x180002214  mov     [rsp+arg_10], rbx
0x180002219  push    rbp
0x18000221a  push    rsi
0x18000221b  push    rdi
0x18000221c  sub     rsp, 40h
0x180002220  mov     rax, cs:__security_cookie
0x180002227  xor     rax, rsp
0x18000222a  mov     [rsp+58h+var_28], rax
0x18000222f  mov     qword ptr [rdx], 0
0x180002236  mov     rdi, rdx
0x180002239  mov     eax, [rcx]
0x18000223b  mov     rsi, rcx
0x18000223e  mov     [rdx], eax
0x180002240  and     eax, 6
0x180002243  cmp     al, 6
0x180002245  jz      loc_1800022E1
0x18000224b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180002250  lea     r8, [rsp+58h+var_30]
0x180002255  mov     [rsp+58h+var_30], 0
0x18000225d  lea     rdx, [rsp+58h+var_38]
0x180002262  mov     ebp, eax
0x180002264  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCurrentFeatureEnabledState(int *)
0x180002269  mov     eax, [rdi]
0x18000226b  mov     rbx, [rsp+58h+var_38]
0x180002270  cmp     [rsp+58h+var_30], 0
0x180002275  mov     edx, eax
0x180002277  mov     [rdi], eax
0x180002279  mov     ecx, eax
0x18000227b  jz      short loc_180002296
0x18000227d  test    dl, 2
0x180002280  jnz     short loc_180002296
0x180002282  and     ecx, 0FFFFF63Eh
0x180002288  mov     eax, ebx
0x18000228a  and     eax, 9C1h
0x18000228f  or      ecx, eax
0x180002291  or      ecx, 2
0x180002294  mov     [rdi], ecx
0x180002296  test    dl, 4
0x180002299  jnz     short loc_1800022AD
0x18000229b  btr     ecx, 0Ah
0x18000229f  mov     eax, ebx
0x1800022a1  and     eax, 400h
0x1800022a6  or      ecx, eax
0x1800022a8  or      ecx, 4
0x1800022ab  mov     [rdi], ecx
0x1800022ad  mov     eax, edx
0x1800022af  lock cmpxchg [rsi], ecx
0x1800022b3  jnz     short loc_180002270
0x1800022b5  test    dl, 4
0x1800022b8  jnz     short loc_1800022CA
0x1800022ba  mov     r8d, ebp
0x1800022bd  mov     edx, 3
0x1800022c2  mov     rcx, rsi
0x1800022c5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800022ca  mov     ecx, [rdi]
0x1800022cc  test    cl, 2
0x1800022cf  jnz     short loc_1800022E1
0x1800022d1  and     ecx, 0FFFFF63Eh
0x1800022d7  and     ebx, 9C1h
0x1800022dd  or      ecx, ebx
0x1800022df  mov     [rdi], ecx
0x1800022e1  mov     rax, rdi
0x1800022e4  mov     rcx, [rsp+58h+var_28]
0x1800022e9  xor     rcx, rsp; StackCookie
0x1800022ec  call    __security_check_cookie
0x1800022f1  mov     rbx, [rsp+58h+arg_10]
0x1800022f6  add     rsp, 40h
0x1800022fa  pop     rdi
0x1800022fb  pop     rsi
0x1800022fc  pop     rbp
0x1800022fd  retn
```
