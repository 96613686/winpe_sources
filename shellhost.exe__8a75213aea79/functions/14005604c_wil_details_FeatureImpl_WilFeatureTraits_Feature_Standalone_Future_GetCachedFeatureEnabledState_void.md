# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x14005604c`
- end: `0x1400561a6`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140056594`
- `0x140056c84`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x14005604c`
- `0x14005c0d4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2F29A04,
                            3u,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v11
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v11
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v11 ^ v12) & 0x180 ^ (v11 ^ v12 ^ (v11 ^ v12) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_Standalone_Future__descriptor,
        3,
        v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
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
0x14005604c  mov     [rsp+arg_8], rbx
0x140056051  mov     [rsp+arg_10], rbp
0x140056056  mov     [rsp+arg_0], rcx
0x14005605b  push    rsi
0x14005605c  push    rdi
0x14005605d  push    r15
0x14005605f  sub     rsp, 20h
0x140056063  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x14005606a  mov     rbx, rdx
0x14005606d  mov     qword ptr [rdx], 0
0x140056074  mov     eax, [rsi]
0x140056076  mov     [rdx], eax
0x140056078  and     eax, 6
0x14005607b  cmp     al, 6
0x14005607d  jz      loc_140056190
0x140056083  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140056088  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x14005608d  mov     dword ptr [rsp+38h+arg_0], 0
0x140056095  mov     edx, 3; unsigned int
0x14005609a  mov     ecx, 2F29A04h; this
0x14005609f  mov     ebp, eax
0x1400560a1  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1400560a6  mov     r8d, eax
0x1400560a9  mov     ecx, eax
0x1400560ab  and     r8d, 0FFFFFF3Fh
0x1400560b2  and     eax, 80h
0x1400560b7  mov     edx, r8d
0x1400560ba  mov     r15d, 40h ; '@'
0x1400560c0  and     edx, 3
0x1400560c3  and     ecx, r15d
0x1400560c6  shl     edx, 2
0x1400560c9  or      edx, ecx
0x1400560cb  shl     edx, 2
0x1400560ce  or      edx, eax
0x1400560d0  lea     edi, ds:0[rdx*8]
0x1400560d7  test    r8d, r8d
0x1400560da  jnz     short loc_1400560E1
0x1400560dc  mov     eax, r15d
0x1400560df  jmp     short loc_1400560EB
0x1400560e1  xor     eax, eax
0x1400560e3  cmp     r8d, 2
0x1400560e7  cmovz   eax, r15d
0x1400560eb  or      edi, eax
0x1400560ed  mov     eax, [rbx]
0x1400560ef  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400560f4  mov     edx, eax
0x1400560f6  mov     [rbx], eax
0x1400560f8  jz      short loc_140056124
0x1400560fa  test    dl, 2
0x1400560fd  jnz     short loc_140056124
0x1400560ff  xor     eax, edi
0x140056101  and     eax, 180h
0x140056106  xor     eax, edx
0x140056108  mov     ecx, eax
0x14005610a  xor     ecx, edi
0x14005610c  and     ecx, r15d
0x14005610f  xor     ecx, eax
0x140056111  or      ecx, 1
0x140056114  mov     eax, ecx
0x140056116  xor     eax, edi
0x140056118  and     eax, 800h
0x14005611d  xor     eax, ecx
0x14005611f  or      eax, 2
0x140056122  mov     [rbx], eax
0x140056124  mov     r8d, edx
0x140056127  and     r8d, 4
0x14005612b  jnz     short loc_140056140
0x14005612d  mov     ecx, edi
0x14005612f  xor     ecx, eax
0x140056131  and     ecx, 400h
0x140056137  xor     ecx, eax
0x140056139  or      ecx, 4
0x14005613c  mov     [rbx], ecx
0x14005613e  jmp     short loc_140056142
0x140056140  mov     ecx, eax
0x140056142  mov     eax, edx
0x140056144  lock cmpxchg [rsi], ecx
0x140056148  jnz     short loc_1400560EF
0x14005614a  test    r8d, r8d
0x14005614d  jnz     short loc_140056167
0x14005614f  mov     r9d, ebp
0x140056152  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140056159  mov     r8d, 3
0x14005615f  mov     rdx, rsi
0x140056162  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140056167  test    byte ptr [rbx], 2
0x14005616a  jnz     short loc_140056190
0x14005616c  mov     eax, [rbx]
0x14005616e  xor     eax, edi
0x140056170  and     eax, 180h
0x140056175  xor     eax, [rbx]
0x140056177  mov     ecx, eax
0x140056179  xor     ecx, edi
0x14005617b  and     ecx, r15d
0x14005617e  xor     ecx, eax
0x140056180  or      ecx, 1
0x140056183  mov     eax, ecx
0x140056185  xor     eax, edi
0x140056187  and     eax, 800h
0x14005618c  xor     eax, ecx
0x14005618e  mov     [rbx], eax
0x140056190  mov     rbp, [rsp+38h+arg_10]
0x140056195  mov     rax, rbx
0x140056198  mov     rbx, [rsp+38h+arg_8]
0x14005619d  add     rsp, 20h
0x1400561a1  pop     r15
0x1400561a3  pop     rdi
0x1400561a4  pop     rsi
0x1400561a5  retn
```
