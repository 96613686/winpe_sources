# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800148a8`
- end: `0x180014a03`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `347`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014af4`

## callees

- `0x18000bccc`
- `0x18000d3b8`
- `0x1800148a8`
- `0x180014ff8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
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
  v3 = *(_DWORD *)Feature_UxLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x3667C9A,
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
             ^ ((unsigned __int16)v13
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v12
              ^ v13
              ^ ((unsigned __int16)v13
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v12
             ^ ((unsigned __int16)(v13 ^ (v13 ^ v12) & 0x180 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x180) & 0x40) | 1))
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
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxLabTest__descriptor, v16, v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        Feature_UxLabTest__descriptor,
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
0x1800148a8  mov     [rsp+arg_8], rbx
0x1800148ad  mov     [rsp+arg_10], rbp
0x1800148b2  mov     [rsp+arg_0], rcx
0x1800148b7  push    rsi
0x1800148b8  push    rdi
0x1800148b9  push    r15
0x1800148bb  sub     rsp, 20h
0x1800148bf  mov     rsi, cs:Feature_UxLabTest__descriptor
0x1800148c6  mov     rbx, rdx
0x1800148c9  mov     qword ptr [rdx], 0
0x1800148d0  mov     eax, [rsi]
0x1800148d2  mov     [rdx], eax
0x1800148d4  and     eax, 6
0x1800148d7  cmp     al, 6
0x1800148d9  jz      loc_1800149ED
0x1800148df  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800148e4  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800148e9  mov     dword ptr [rsp+38h+arg_0], 0
0x1800148f1  mov     ecx, 3667C9Ah; this
0x1800148f6  mov     ebp, eax
0x1800148f8  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800148fd  mov     r8d, eax
0x180014900  mov     ecx, eax
0x180014902  and     r8d, 0FFFFFF3Fh
0x180014909  and     eax, 80h
0x18001490e  mov     edx, r8d
0x180014911  mov     r15d, 40h ; '@'
0x180014917  and     edx, 3
0x18001491a  and     ecx, r15d
0x18001491d  shl     edx, 2
0x180014920  or      edx, ecx
0x180014922  shl     edx, 2
0x180014925  or      edx, eax
0x180014927  lea     edi, ds:0[rdx*8]
0x18001492e  test    r8d, r8d
0x180014931  jnz     short loc_180014938
0x180014933  mov     eax, r15d
0x180014936  jmp     short loc_180014942
0x180014938  xor     eax, eax
0x18001493a  cmp     r8d, 2
0x18001493e  cmovz   eax, r15d
0x180014942  or      edi, eax
0x180014944  mov     eax, [rbx]
0x180014946  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001494b  mov     edx, eax
0x18001494d  mov     [rbx], eax
0x18001494f  jz      short loc_18001497F
0x180014951  test    dl, 2
0x180014954  jnz     short loc_18001497F
0x180014956  mov     eax, edi
0x180014958  xor     eax, edx
0x18001495a  and     eax, 180h
0x18001495f  xor     eax, edx
0x180014961  mov     ecx, eax
0x180014963  xor     ecx, edi
0x180014965  and     ecx, r15d
0x180014968  xor     ecx, eax
0x18001496a  or      ecx, 1
0x18001496d  mov     eax, ecx
0x18001496f  xor     eax, edi
0x180014971  and     eax, 800h
0x180014976  xor     eax, ecx
0x180014978  or      eax, 2
0x18001497b  mov     [rbx], eax
0x18001497d  jmp     short loc_180014981
0x18001497f  mov     eax, edx
0x180014981  mov     r8d, edx
0x180014984  and     r8d, 4
0x180014988  jnz     short loc_18001499D
0x18001498a  mov     ecx, edi
0x18001498c  xor     ecx, eax
0x18001498e  and     ecx, 400h
0x180014994  xor     ecx, eax
0x180014996  or      ecx, 4
0x180014999  mov     [rbx], ecx
0x18001499b  jmp     short loc_18001499F
0x18001499d  mov     ecx, eax
0x18001499f  mov     eax, edx
0x1800149a1  lock cmpxchg [rsi], ecx
0x1800149a5  jnz     short loc_180014946
0x1800149a7  test    r8d, r8d
0x1800149aa  jnz     short loc_1800149C4
0x1800149ac  mov     r9d, ebp
0x1800149af  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800149b6  mov     r8d, 3
0x1800149bc  mov     rdx, rsi
0x1800149bf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800149c4  test    byte ptr [rbx], 2
0x1800149c7  jnz     short loc_1800149ED
0x1800149c9  mov     eax, [rbx]
0x1800149cb  xor     eax, edi
0x1800149cd  and     eax, 180h
0x1800149d2  xor     eax, [rbx]
0x1800149d4  mov     ecx, eax
0x1800149d6  xor     ecx, edi
0x1800149d8  and     ecx, r15d
0x1800149db  xor     ecx, eax
0x1800149dd  or      ecx, 1
0x1800149e0  mov     eax, ecx
0x1800149e2  xor     eax, edi
0x1800149e4  and     eax, 800h
0x1800149e9  xor     eax, ecx
0x1800149eb  mov     [rbx], eax
0x1800149ed  mov     rbp, [rsp+38h+arg_10]
0x1800149f2  mov     rax, rbx
0x1800149f5  mov     rbx, [rsp+38h+arg_8]
0x1800149fa  add     rsp, 20h
0x1800149fe  pop     r15
0x180014a00  pop     rdi
0x180014a01  pop     rsi
0x180014a02  retn
```
