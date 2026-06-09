# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x140056294`
- end: `0x1400563f4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140056a90`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x140056294`
- `0x14005c0d4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x3667C9A,
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
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
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
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxLabTest__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_UxLabTest__descriptor,
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
0x140056294  mov     [rsp+arg_8], rbx
0x140056299  mov     [rsp+arg_10], rbp
0x14005629e  mov     [rsp+arg_0], rcx
0x1400562a3  push    rsi
0x1400562a4  push    rdi
0x1400562a5  push    r15
0x1400562a7  sub     rsp, 20h
0x1400562ab  mov     rsi, cs:Feature_UxLabTest__descriptor
0x1400562b2  mov     rbx, rdx
0x1400562b5  mov     qword ptr [rdx], 0
0x1400562bc  mov     eax, [rsi]
0x1400562be  mov     [rdx], eax
0x1400562c0  and     eax, 6
0x1400562c3  cmp     al, 6
0x1400562c5  jz      loc_1400563DE
0x1400562cb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400562d0  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1400562d5  mov     dword ptr [rsp+38h+arg_0], 0
0x1400562dd  mov     edx, 3; unsigned int
0x1400562e2  mov     ecx, 3667C9Ah; this
0x1400562e7  mov     ebp, eax
0x1400562e9  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1400562ee  mov     r8d, eax
0x1400562f1  mov     ecx, eax
0x1400562f3  and     r8d, 0FFFFFF3Fh
0x1400562fa  and     eax, 80h
0x1400562ff  mov     edx, r8d
0x140056302  mov     r15d, 40h ; '@'
0x140056308  and     edx, 3
0x14005630b  and     ecx, r15d
0x14005630e  shl     edx, 2
0x140056311  or      edx, ecx
0x140056313  shl     edx, 2
0x140056316  or      edx, eax
0x140056318  lea     edi, ds:0[rdx*8]
0x14005631f  test    r8d, r8d
0x140056322  jnz     short loc_140056329
0x140056324  mov     eax, r15d
0x140056327  jmp     short loc_140056333
0x140056329  xor     eax, eax
0x14005632b  cmp     r8d, 2
0x14005632f  cmovz   eax, r15d
0x140056333  or      edi, eax
0x140056335  mov     eax, [rbx]
0x140056337  cmp     dword ptr [rsp+38h+arg_0], 0
0x14005633c  mov     edx, eax
0x14005633e  mov     [rbx], eax
0x140056340  jz      short loc_140056370
0x140056342  test    dl, 2
0x140056345  jnz     short loc_140056370
0x140056347  mov     eax, edi
0x140056349  xor     eax, edx
0x14005634b  and     eax, 180h
0x140056350  xor     eax, edx
0x140056352  mov     ecx, eax
0x140056354  xor     ecx, edi
0x140056356  and     ecx, r15d
0x140056359  xor     ecx, eax
0x14005635b  or      ecx, 1
0x14005635e  mov     eax, ecx
0x140056360  xor     eax, edi
0x140056362  and     eax, 800h
0x140056367  xor     eax, ecx
0x140056369  or      eax, 2
0x14005636c  mov     [rbx], eax
0x14005636e  jmp     short loc_140056372
0x140056370  mov     eax, edx
0x140056372  mov     r8d, edx
0x140056375  and     r8d, 4
0x140056379  jnz     short loc_14005638E
0x14005637b  mov     ecx, edi
0x14005637d  xor     ecx, eax
0x14005637f  and     ecx, 400h
0x140056385  xor     ecx, eax
0x140056387  or      ecx, 4
0x14005638a  mov     [rbx], ecx
0x14005638c  jmp     short loc_140056390
0x14005638e  mov     ecx, eax
0x140056390  mov     eax, edx
0x140056392  lock cmpxchg [rsi], ecx
0x140056396  jnz     short loc_140056337
0x140056398  test    r8d, r8d
0x14005639b  jnz     short loc_1400563B5
0x14005639d  mov     r9d, ebp
0x1400563a0  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400563a7  mov     r8d, 3
0x1400563ad  mov     rdx, rsi
0x1400563b0  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400563b5  test    byte ptr [rbx], 2
0x1400563b8  jnz     short loc_1400563DE
0x1400563ba  mov     eax, [rbx]
0x1400563bc  xor     eax, edi
0x1400563be  and     eax, 180h
0x1400563c3  xor     eax, [rbx]
0x1400563c5  mov     ecx, eax
0x1400563c7  xor     ecx, edi
0x1400563c9  and     ecx, r15d
0x1400563cc  xor     ecx, eax
0x1400563ce  or      ecx, 1
0x1400563d1  mov     eax, ecx
0x1400563d3  xor     eax, edi
0x1400563d5  and     eax, 800h
0x1400563da  xor     eax, ecx
0x1400563dc  mov     [rbx], eax
0x1400563de  mov     rbp, [rsp+38h+arg_10]
0x1400563e3  mov     rax, rbx
0x1400563e6  mov     rbx, [rsp+38h+arg_8]
0x1400563eb  add     rsp, 20h
0x1400563ef  pop     r15
0x1400563f1  pop     rdi
0x1400563f2  pop     rsi
0x1400563f3  retn
```
