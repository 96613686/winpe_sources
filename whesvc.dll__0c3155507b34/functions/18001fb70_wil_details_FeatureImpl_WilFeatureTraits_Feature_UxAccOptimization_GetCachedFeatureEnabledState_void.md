# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18001fb70`
- end: `0x18001fc49`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025404`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001fb70`
- `0x180020160`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
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
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UxAccOptimization__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001fb70  mov     [rsp+arg_10], rbx
0x18001fb75  mov     [rsp+arg_0], rcx
0x18001fb7a  push    rbp
0x18001fb7b  push    rsi
0x18001fb7c  push    rdi
0x18001fb7d  sub     rsp, 20h
0x18001fb81  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18001fb88  mov     rdi, rdx
0x18001fb8b  mov     qword ptr [rdx], 0
0x18001fb92  mov     eax, [rsi]
0x18001fb94  mov     [rdx], eax
0x18001fb96  and     eax, 6
0x18001fb99  cmp     al, 6
0x18001fb9b  jz      loc_18001FC39
0x18001fba1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001fba6  lea     r8, [rsp+38h+arg_0]
0x18001fbab  mov     dword ptr [rsp+38h+arg_0], 0
0x18001fbb3  lea     rdx, [rsp+38h+arg_8]
0x18001fbb8  mov     ebp, eax
0x18001fbba  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18001fbbf  mov     eax, [rdi]
0x18001fbc1  mov     rbx, [rsp+38h+arg_8]
0x18001fbc6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001fbcb  mov     edx, eax
0x18001fbcd  mov     [rdi], eax
0x18001fbcf  mov     ecx, eax
0x18001fbd1  jz      short loc_18001FBEC
0x18001fbd3  test    dl, 2
0x18001fbd6  jnz     short loc_18001FBEC
0x18001fbd8  and     ecx, 0FFFFF63Eh
0x18001fbde  mov     eax, ebx
0x18001fbe0  and     eax, 9C1h
0x18001fbe5  or      ecx, eax
0x18001fbe7  or      ecx, 2
0x18001fbea  mov     [rdi], ecx
0x18001fbec  mov     r8d, edx
0x18001fbef  and     r8d, 4
0x18001fbf3  jnz     short loc_18001FC07
0x18001fbf5  btr     ecx, 0Ah
0x18001fbf9  mov     eax, ebx
0x18001fbfb  and     eax, 400h
0x18001fc00  or      ecx, eax
0x18001fc02  or      ecx, 4
0x18001fc05  mov     [rdi], ecx
0x18001fc07  mov     eax, edx
0x18001fc09  lock cmpxchg [rsi], ecx
0x18001fc0d  jnz     short loc_18001FBC6
0x18001fc0f  test    r8d, r8d
0x18001fc12  jnz     short loc_18001FC24
0x18001fc14  mov     r8d, ebp
0x18001fc17  mov     edx, 3
0x18001fc1c  mov     rcx, rsi
0x18001fc1f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001fc24  mov     eax, [rdi]
0x18001fc26  test    al, 2
0x18001fc28  jnz     short loc_18001FC39
0x18001fc2a  and     eax, 0FFFFF63Eh
0x18001fc2f  and     ebx, 9C1h
0x18001fc35  or      eax, ebx
0x18001fc37  mov     [rdi], eax
0x18001fc39  mov     rbx, [rsp+38h+arg_10]
0x18001fc3e  mov     rax, rdi
0x18001fc41  add     rsp, 20h
0x18001fc45  pop     rdi
0x18001fc46  pop     rsi
0x18001fc47  pop     rbp
0x18001fc48  retn
```
