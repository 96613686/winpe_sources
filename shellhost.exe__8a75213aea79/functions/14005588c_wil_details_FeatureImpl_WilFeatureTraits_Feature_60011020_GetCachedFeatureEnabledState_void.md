# wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCachedFeatureEnabledState(void)

- ea: `0x14005588c`
- end: `0x1400559ec`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60011020@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140056594`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x14005588c`
- `0x14005c0d4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_60011020__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_60011020__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x393B20C,
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
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_60011020__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_60011020__descriptor,
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
0x14005588c  mov     [rsp+arg_8], rbx
0x140055891  mov     [rsp+arg_10], rbp
0x140055896  mov     [rsp+arg_0], rcx
0x14005589b  push    rsi
0x14005589c  push    rdi
0x14005589d  push    r15
0x14005589f  sub     rsp, 20h
0x1400558a3  mov     rsi, cs:Feature_60011020__descriptor
0x1400558aa  mov     rbx, rdx
0x1400558ad  mov     qword ptr [rdx], 0
0x1400558b4  mov     eax, [rsi]
0x1400558b6  mov     [rdx], eax
0x1400558b8  and     eax, 6
0x1400558bb  cmp     al, 6
0x1400558bd  jz      loc_1400559D6
0x1400558c3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400558c8  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1400558cd  mov     dword ptr [rsp+38h+arg_0], 0
0x1400558d5  mov     edx, 3; unsigned int
0x1400558da  mov     ecx, 393B20Ch; this
0x1400558df  mov     ebp, eax
0x1400558e1  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1400558e6  mov     r8d, eax
0x1400558e9  mov     ecx, eax
0x1400558eb  and     r8d, 0FFFFFF3Fh
0x1400558f2  and     eax, 80h
0x1400558f7  mov     edx, r8d
0x1400558fa  mov     r15d, 40h ; '@'
0x140055900  and     edx, 3
0x140055903  and     ecx, r15d
0x140055906  shl     edx, 2
0x140055909  or      edx, ecx
0x14005590b  shl     edx, 2
0x14005590e  or      edx, eax
0x140055910  lea     edi, ds:0[rdx*8]
0x140055917  test    r8d, r8d
0x14005591a  jnz     short loc_140055921
0x14005591c  mov     eax, r15d
0x14005591f  jmp     short loc_14005592B
0x140055921  xor     eax, eax
0x140055923  cmp     r8d, 2
0x140055927  cmovz   eax, r15d
0x14005592b  or      edi, eax
0x14005592d  mov     eax, [rbx]
0x14005592f  cmp     dword ptr [rsp+38h+arg_0], 0
0x140055934  mov     edx, eax
0x140055936  mov     [rbx], eax
0x140055938  jz      short loc_140055968
0x14005593a  test    dl, 2
0x14005593d  jnz     short loc_140055968
0x14005593f  mov     eax, edi
0x140055941  xor     eax, edx
0x140055943  and     eax, 180h
0x140055948  xor     eax, edx
0x14005594a  mov     ecx, eax
0x14005594c  xor     ecx, edi
0x14005594e  and     ecx, r15d
0x140055951  xor     ecx, eax
0x140055953  or      ecx, 1
0x140055956  mov     eax, ecx
0x140055958  xor     eax, edi
0x14005595a  and     eax, 800h
0x14005595f  xor     eax, ecx
0x140055961  or      eax, 2
0x140055964  mov     [rbx], eax
0x140055966  jmp     short loc_14005596A
0x140055968  mov     eax, edx
0x14005596a  mov     r8d, edx
0x14005596d  and     r8d, 4
0x140055971  jnz     short loc_140055986
0x140055973  mov     ecx, edi
0x140055975  xor     ecx, eax
0x140055977  and     ecx, 400h
0x14005597d  xor     ecx, eax
0x14005597f  or      ecx, 4
0x140055982  mov     [rbx], ecx
0x140055984  jmp     short loc_140055988
0x140055986  mov     ecx, eax
0x140055988  mov     eax, edx
0x14005598a  lock cmpxchg [rsi], ecx
0x14005598e  jnz     short loc_14005592F
0x140055990  test    r8d, r8d
0x140055993  jnz     short loc_1400559AD
0x140055995  mov     r9d, ebp
0x140055998  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14005599f  mov     r8d, 3
0x1400559a5  mov     rdx, rsi
0x1400559a8  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400559ad  test    byte ptr [rbx], 2
0x1400559b0  jnz     short loc_1400559D6
0x1400559b2  mov     eax, [rbx]
0x1400559b4  xor     eax, edi
0x1400559b6  and     eax, 180h
0x1400559bb  xor     eax, [rbx]
0x1400559bd  mov     ecx, eax
0x1400559bf  xor     ecx, edi
0x1400559c1  and     ecx, r15d
0x1400559c4  xor     ecx, eax
0x1400559c6  or      ecx, 1
0x1400559c9  mov     eax, ecx
0x1400559cb  xor     eax, edi
0x1400559cd  and     eax, 800h
0x1400559d2  xor     eax, ecx
0x1400559d4  mov     [rbx], eax
0x1400559d6  mov     rbp, [rsp+38h+arg_10]
0x1400559db  mov     rax, rbx
0x1400559de  mov     rbx, [rsp+38h+arg_8]
0x1400559e3  add     rsp, 20h
0x1400559e7  pop     r15
0x1400559e9  pop     rdi
0x1400559ea  pop     rsi
0x1400559eb  retn
```
