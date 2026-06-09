# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::GetCachedFeatureEnabledState(void)

- ea: `0x140055f64`
- end: `0x140056045`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400093dc`
- `0x14000b420`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x140055f64`
- `0x140056bb8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_SWT_4__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_SWT_4__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_SWT_4__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_SWT_4__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140055f64  mov     [rsp+arg_10], rbx
0x140055f69  mov     [rsp+arg_0], rcx
0x140055f6e  push    rbp
0x140055f6f  push    rsi
0x140055f70  push    rdi
0x140055f71  sub     rsp, 20h
0x140055f75  mov     rsi, cs:Feature_SWT_4__descriptor
0x140055f7c  mov     rdi, rdx
0x140055f7f  mov     qword ptr [rdx], 0
0x140055f86  mov     eax, [rsi]
0x140055f88  mov     [rdx], eax
0x140055f8a  and     eax, 6
0x140055f8d  cmp     al, 6
0x140055f8f  jz      loc_140056035
0x140055f95  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140055f9a  lea     r8, [rsp+38h+arg_0]
0x140055f9f  mov     dword ptr [rsp+38h+arg_0], 0
0x140055fa7  lea     rdx, [rsp+38h+arg_8]
0x140055fac  mov     ebp, eax
0x140055fae  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::GetCurrentFeatureEnabledState(int *)
0x140055fb3  mov     eax, [rdi]
0x140055fb5  mov     rbx, [rsp+38h+arg_8]
0x140055fba  cmp     dword ptr [rsp+38h+arg_0], 0
0x140055fbf  mov     edx, eax
0x140055fc1  mov     [rdi], eax
0x140055fc3  mov     ecx, eax
0x140055fc5  jz      short loc_140055FE0
0x140055fc7  test    dl, 2
0x140055fca  jnz     short loc_140055FE0
0x140055fcc  and     ecx, 0FFFFF63Eh
0x140055fd2  mov     eax, ebx
0x140055fd4  and     eax, 9C1h
0x140055fd9  or      ecx, eax
0x140055fdb  or      ecx, 2
0x140055fde  mov     [rdi], ecx
0x140055fe0  mov     r8d, edx
0x140055fe3  and     r8d, 4
0x140055fe7  jnz     short loc_140055FFB
0x140055fe9  btr     ecx, 0Ah
0x140055fed  mov     eax, ebx
0x140055fef  and     eax, 400h
0x140055ff4  or      ecx, eax
0x140055ff6  or      ecx, 4
0x140055ff9  mov     [rdi], ecx
0x140055ffb  mov     eax, edx
0x140055ffd  lock cmpxchg [rsi], ecx
0x140056001  jnz     short loc_140055FBA
0x140056003  test    r8d, r8d
0x140056006  jnz     short loc_140056020
0x140056008  mov     r9d, ebp
0x14005600b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140056012  mov     r8d, 3
0x140056018  mov     rdx, rsi
0x14005601b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140056020  mov     eax, [rdi]
0x140056022  test    al, 2
0x140056024  jnz     short loc_140056035
0x140056026  and     eax, 0FFFFF63Eh
0x14005602b  and     ebx, 9C1h
0x140056031  or      eax, ebx
0x140056033  mov     [rdi], eax
0x140056035  mov     rbx, [rsp+38h+arg_10]
0x14005603a  mov     rax, rdi
0x14005603d  add     rsp, 20h
0x140056041  pop     rdi
0x140056042  pop     rsi
0x140056043  pop     rbp
0x140056044  retn
```
