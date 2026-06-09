# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18002a438`
- end: `0x18002a58d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a73c`

## callees

- `0x180029c18`
- `0x18002a438`
- `0x18002bacc`
- `0x18002bfe4`

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
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
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
0x18002a438  mov     [rsp+arg_8], rbx
0x18002a43d  mov     [rsp+arg_10], rbp
0x18002a442  mov     [rsp+arg_0], rcx
0x18002a447  push    rsi
0x18002a448  push    rdi
0x18002a449  push    r15
0x18002a44b  sub     rsp, 20h
0x18002a44f  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18002a456  mov     rbx, rdx
0x18002a459  mov     qword ptr [rdx], 0
0x18002a460  mov     eax, [rsi]
0x18002a462  mov     [rdx], eax
0x18002a464  and     eax, 6
0x18002a467  cmp     al, 6
0x18002a469  jz      loc_18002A577
0x18002a46f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002a474  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18002a479  mov     dword ptr [rsp+38h+arg_0], 0
0x18002a481  mov     ecx, 2F29A04h; this
0x18002a486  mov     ebp, eax
0x18002a488  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18002a48d  mov     r8d, eax
0x18002a490  mov     ecx, eax
0x18002a492  and     r8d, 0FFFFFF3Fh
0x18002a499  and     eax, 80h
0x18002a49e  mov     edx, r8d
0x18002a4a1  mov     r15d, 40h ; '@'
0x18002a4a7  and     edx, 3
0x18002a4aa  and     ecx, r15d
0x18002a4ad  shl     edx, 2
0x18002a4b0  or      edx, ecx
0x18002a4b2  shl     edx, 2
0x18002a4b5  or      edx, eax
0x18002a4b7  lea     edi, ds:0[rdx*8]
0x18002a4be  test    r8d, r8d
0x18002a4c1  jnz     short loc_18002A4C8
0x18002a4c3  mov     eax, r15d
0x18002a4c6  jmp     short loc_18002A4D2
0x18002a4c8  xor     eax, eax
0x18002a4ca  cmp     r8d, 2
0x18002a4ce  cmovz   eax, r15d
0x18002a4d2  or      edi, eax
0x18002a4d4  mov     eax, [rbx]
0x18002a4d6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002a4db  mov     edx, eax
0x18002a4dd  mov     [rbx], eax
0x18002a4df  jz      short loc_18002A50B
0x18002a4e1  test    dl, 2
0x18002a4e4  jnz     short loc_18002A50B
0x18002a4e6  xor     eax, edi
0x18002a4e8  and     eax, 180h
0x18002a4ed  xor     eax, edx
0x18002a4ef  mov     ecx, eax
0x18002a4f1  xor     ecx, edi
0x18002a4f3  and     ecx, r15d
0x18002a4f6  xor     ecx, eax
0x18002a4f8  or      ecx, 1
0x18002a4fb  mov     eax, ecx
0x18002a4fd  xor     eax, edi
0x18002a4ff  and     eax, 800h
0x18002a504  xor     eax, ecx
0x18002a506  or      eax, 2
0x18002a509  mov     [rbx], eax
0x18002a50b  mov     r8d, edx
0x18002a50e  and     r8d, 4
0x18002a512  jnz     short loc_18002A527
0x18002a514  mov     ecx, edi
0x18002a516  xor     ecx, eax
0x18002a518  and     ecx, 400h
0x18002a51e  xor     ecx, eax
0x18002a520  or      ecx, 4
0x18002a523  mov     [rbx], ecx
0x18002a525  jmp     short loc_18002A529
0x18002a527  mov     ecx, eax
0x18002a529  mov     eax, edx
0x18002a52b  lock cmpxchg [rsi], ecx
0x18002a52f  jnz     short loc_18002A4D6
0x18002a531  test    r8d, r8d
0x18002a534  jnz     short loc_18002A54E
0x18002a536  mov     r9d, ebp
0x18002a539  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002a540  mov     r8d, 3
0x18002a546  mov     rdx, rsi
0x18002a549  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002a54e  test    byte ptr [rbx], 2
0x18002a551  jnz     short loc_18002A577
0x18002a553  mov     eax, [rbx]
0x18002a555  xor     eax, edi
0x18002a557  and     eax, 180h
0x18002a55c  xor     eax, [rbx]
0x18002a55e  mov     ecx, eax
0x18002a560  xor     ecx, edi
0x18002a562  and     ecx, r15d
0x18002a565  xor     ecx, eax
0x18002a567  or      ecx, 1
0x18002a56a  mov     eax, ecx
0x18002a56c  xor     eax, edi
0x18002a56e  and     eax, 800h
0x18002a573  xor     eax, ecx
0x18002a575  mov     [rbx], eax
0x18002a577  mov     rbp, [rsp+38h+arg_10]
0x18002a57c  mov     rax, rbx
0x18002a57f  mov     rbx, [rsp+38h+arg_8]
0x18002a584  add     rsp, 20h
0x18002a588  pop     r15
0x18002a58a  pop     rdi
0x18002a58b  pop     rsi
0x18002a58c  retn
```
