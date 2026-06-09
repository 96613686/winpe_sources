# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f8a0`
- end: `0x18000f9f5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fba4`

## callees

- `0x18000f670`
- `0x18000f8a0`
- `0x180011240`
- `0x180011e70`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  unsigned int v6; // edx
  int *v7; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v9; // r8d
  int v10; // edi
  int v11; // eax
  int v12; // edi
  int v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  wil::details *v18; // [rsp+40h] [rbp+8h] BYREF

  v18 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2F29A04,
                            v6,
                            (enum FEATURE_CHANGE_TIME)&v18,
                            v7);
    v9 = FeatureEnabledState & 0xFFFFFF3F;
    v10 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v11 = 0;
      if ( v9 == 2 )
        v11 = 64;
    }
    else
    {
      v11 = 64;
    }
    v12 = v11 | v10;
    v13 = *(_DWORD *)a2;
    do
    {
      v14 = (_DWORD)v18 == 0;
      v15 = v13;
      *(_DWORD *)a2 = v13;
      if ( !v14 && (v13 & 2) == 0 )
      {
        v13 = (v13
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v13)
             & 0x180
             ^ (v12
              ^ v13
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v13)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v12
             ^ ((unsigned __int16)(v13 ^ (v12 ^ v13) & 0x180 ^ (v12 ^ v13 ^ (v12 ^ v13) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v13;
      }
      if ( (v15 & 4) != 0 )
      {
        v16 = v13;
      }
      else
      {
        v16 = v13 ^ ((unsigned __int16)v13 ^ (unsigned __int16)v12) & 0x400 | 4;
        *(_DWORD *)a2 = v16;
      }
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v16, v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_Standalone_Future__descriptor,
        3,
        v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v12
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v12
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v12
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v12
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v12
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18000f8a0  mov     [rsp+arg_8], rbx
0x18000f8a5  mov     [rsp+arg_10], rbp
0x18000f8aa  mov     [rsp+arg_0], rcx
0x18000f8af  push    rsi
0x18000f8b0  push    rdi
0x18000f8b1  push    r15
0x18000f8b3  sub     rsp, 20h
0x18000f8b7  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18000f8be  mov     rbx, rdx
0x18000f8c1  mov     qword ptr [rdx], 0
0x18000f8c8  mov     eax, [rsi]
0x18000f8ca  mov     [rdx], eax
0x18000f8cc  and     eax, 6
0x18000f8cf  cmp     al, 6
0x18000f8d1  jz      loc_18000F9DF
0x18000f8d7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f8dc  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18000f8e1  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f8e9  mov     ecx, 2F29A04h; this
0x18000f8ee  mov     ebp, eax
0x18000f8f0  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000f8f5  mov     r8d, eax
0x18000f8f8  mov     ecx, eax
0x18000f8fa  and     r8d, 0FFFFFF3Fh
0x18000f901  and     eax, 80h
0x18000f906  mov     edx, r8d
0x18000f909  mov     r15d, 40h ; '@'
0x18000f90f  and     edx, 3
0x18000f912  and     ecx, r15d
0x18000f915  shl     edx, 2
0x18000f918  or      edx, ecx
0x18000f91a  shl     edx, 2
0x18000f91d  or      edx, eax
0x18000f91f  lea     edi, ds:0[rdx*8]
0x18000f926  test    r8d, r8d
0x18000f929  jnz     short loc_18000F930
0x18000f92b  mov     eax, r15d
0x18000f92e  jmp     short loc_18000F93A
0x18000f930  xor     eax, eax
0x18000f932  cmp     r8d, 2
0x18000f936  cmovz   eax, r15d
0x18000f93a  or      edi, eax
0x18000f93c  mov     eax, [rbx]
0x18000f93e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f943  mov     edx, eax
0x18000f945  mov     [rbx], eax
0x18000f947  jz      short loc_18000F973
0x18000f949  test    dl, 2
0x18000f94c  jnz     short loc_18000F973
0x18000f94e  xor     eax, edi
0x18000f950  and     eax, 180h
0x18000f955  xor     eax, edx
0x18000f957  mov     ecx, eax
0x18000f959  xor     ecx, edi
0x18000f95b  and     ecx, r15d
0x18000f95e  xor     ecx, eax
0x18000f960  or      ecx, 1
0x18000f963  mov     eax, ecx
0x18000f965  xor     eax, edi
0x18000f967  and     eax, 800h
0x18000f96c  xor     eax, ecx
0x18000f96e  or      eax, 2
0x18000f971  mov     [rbx], eax
0x18000f973  mov     r8d, edx
0x18000f976  and     r8d, 4
0x18000f97a  jnz     short loc_18000F98F
0x18000f97c  mov     ecx, edi
0x18000f97e  xor     ecx, eax
0x18000f980  and     ecx, 400h
0x18000f986  xor     ecx, eax
0x18000f988  or      ecx, 4
0x18000f98b  mov     [rbx], ecx
0x18000f98d  jmp     short loc_18000F991
0x18000f98f  mov     ecx, eax
0x18000f991  mov     eax, edx
0x18000f993  lock cmpxchg [rsi], ecx
0x18000f997  jnz     short loc_18000F93E
0x18000f999  test    r8d, r8d
0x18000f99c  jnz     short loc_18000F9B6
0x18000f99e  mov     r9d, ebp
0x18000f9a1  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f9a8  mov     r8d, 3
0x18000f9ae  mov     rdx, rsi
0x18000f9b1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f9b6  test    byte ptr [rbx], 2
0x18000f9b9  jnz     short loc_18000F9DF
0x18000f9bb  mov     eax, [rbx]
0x18000f9bd  xor     eax, edi
0x18000f9bf  and     eax, 180h
0x18000f9c4  xor     eax, [rbx]
0x18000f9c6  mov     ecx, eax
0x18000f9c8  xor     ecx, edi
0x18000f9ca  and     ecx, r15d
0x18000f9cd  xor     ecx, eax
0x18000f9cf  or      ecx, 1
0x18000f9d2  mov     eax, ecx
0x18000f9d4  xor     eax, edi
0x18000f9d6  and     eax, 800h
0x18000f9db  xor     eax, ecx
0x18000f9dd  mov     [rbx], eax
0x18000f9df  mov     rbp, [rsp+38h+arg_10]
0x18000f9e4  mov     rax, rbx
0x18000f9e7  mov     rbx, [rsp+38h+arg_8]
0x18000f9ec  add     rsp, 20h
0x18000f9f0  pop     r15
0x18000f9f2  pop     rdi
0x18000f9f3  pop     rsi
0x18000f9f4  retn
```
