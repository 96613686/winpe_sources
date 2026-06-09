# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShdocvwAllowUseOfMOTWCache_60851840>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d930`
- end: `0x18000da09`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShdocvwAllowUseOfMOTWCache_60851840@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fbc0`
- `0x18001180c`

## callees

- `0x18000d020`
- `0x18000d930`
- `0x18000e6f8`
- `0x1800105e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShdocvwAllowUseOfMOTWCache_60851840>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ShdocvwAllowUseOfMOTWCache_60851840__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ShdocvwAllowUseOfMOTWCache_60851840__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShdocvwAllowUseOfMOTWCache_60851840>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_ShdocvwAllowUseOfMOTWCache_60851840__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ShdocvwAllowUseOfMOTWCache_60851840__descriptor,
        1,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000d930  mov     [rsp+arg_10], rbx
0x18000d935  mov     [rsp+arg_0], rcx
0x18000d93a  push    rbp
0x18000d93b  push    rsi
0x18000d93c  push    rdi
0x18000d93d  sub     rsp, 20h
0x18000d941  mov     rsi, cs:Feature_ShdocvwAllowUseOfMOTWCache_60851840__descriptor
0x18000d948  mov     rdi, rdx
0x18000d94b  mov     qword ptr [rdx], 0
0x18000d952  mov     eax, [rsi]
0x18000d954  mov     [rdx], eax
0x18000d956  and     eax, 6
0x18000d959  cmp     al, 6
0x18000d95b  jz      loc_18000D9F9
0x18000d961  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d966  lea     r8, [rsp+38h+arg_0]
0x18000d96b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d973  lea     rdx, [rsp+38h+arg_8]
0x18000d978  mov     ebp, eax
0x18000d97a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShdocvwAllowUseOfMOTWCache_60851840@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShdocvwAllowUseOfMOTWCache_60851840>::GetCurrentFeatureEnabledState(int *)
0x18000d97f  mov     eax, [rdi]
0x18000d981  mov     rbx, [rsp+38h+arg_8]
0x18000d986  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000d98b  mov     edx, eax
0x18000d98d  mov     [rdi], eax
0x18000d98f  mov     ecx, eax
0x18000d991  jz      short loc_18000D9AC
0x18000d993  test    dl, 2
0x18000d996  jnz     short loc_18000D9AC
0x18000d998  and     ecx, 0FFFFF63Eh
0x18000d99e  mov     eax, ebx
0x18000d9a0  and     eax, 9C1h
0x18000d9a5  or      ecx, eax
0x18000d9a7  or      ecx, 2
0x18000d9aa  mov     [rdi], ecx
0x18000d9ac  mov     r8d, edx
0x18000d9af  and     r8d, 4
0x18000d9b3  jnz     short loc_18000D9C7
0x18000d9b5  btr     ecx, 0Ah
0x18000d9b9  mov     eax, ebx
0x18000d9bb  and     eax, 400h
0x18000d9c0  or      ecx, eax
0x18000d9c2  or      ecx, 4
0x18000d9c5  mov     [rdi], ecx
0x18000d9c7  mov     eax, edx
0x18000d9c9  lock cmpxchg [rsi], ecx
0x18000d9cd  jnz     short loc_18000D986
0x18000d9cf  test    r8d, r8d
0x18000d9d2  jnz     short loc_18000D9E4
0x18000d9d4  mov     r8d, ebp
0x18000d9d7  mov     edx, 1
0x18000d9dc  mov     rcx, rsi
0x18000d9df  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d9e4  mov     eax, [rdi]
0x18000d9e6  test    al, 2
0x18000d9e8  jnz     short loc_18000D9F9
0x18000d9ea  and     eax, 0FFFFF63Eh
0x18000d9ef  and     ebx, 9C1h
0x18000d9f5  or      eax, ebx
0x18000d9f7  mov     [rdi], eax
0x18000d9f9  mov     rbx, [rsp+38h+arg_10]
0x18000d9fe  mov     rax, rdi
0x18000da01  add     rsp, 20h
0x18000da05  pop     rdi
0x18000da06  pop     rsi
0x18000da07  pop     rbp
0x18000da08  retn
```
