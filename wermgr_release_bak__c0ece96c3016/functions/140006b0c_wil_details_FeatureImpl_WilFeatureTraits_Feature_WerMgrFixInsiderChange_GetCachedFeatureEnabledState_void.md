# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCachedFeatureEnabledState(void)

- ea: `0x140006b0c`
- end: `0x140006be5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000daa4`

## callees

- `0x140006724`
- `0x140006b0c`
- `0x140006bec`
- `0x14000a768`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_WerMgrFixInsiderChange__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WerMgrFixInsiderChange__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCurrentFeatureEnabledState(
      v5,
      &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_WerMgrFixInsiderChange__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_WerMgrFixInsiderChange__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140006b0c  mov     [rsp+arg_10], rbx
0x140006b11  mov     [rsp+arg_0], rcx
0x140006b16  push    rbp
0x140006b17  push    rsi
0x140006b18  push    rdi
0x140006b19  sub     rsp, 20h
0x140006b1d  mov     rsi, cs:Feature_WerMgrFixInsiderChange__descriptor
0x140006b24  mov     rdi, rdx
0x140006b27  mov     qword ptr [rdx], 0
0x140006b2e  mov     eax, [rsi]
0x140006b30  mov     [rdx], eax
0x140006b32  and     eax, 6
0x140006b35  cmp     al, 6
0x140006b37  jz      loc_140006BD5
0x140006b3d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006b42  lea     r8, [rsp+38h+arg_0]
0x140006b47  mov     dword ptr [rsp+38h+arg_0], 0
0x140006b4f  lea     rdx, [rsp+38h+arg_8]
0x140006b54  mov     ebp, eax
0x140006b56  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCurrentFeatureEnabledState(int *)
0x140006b5b  mov     eax, [rdi]
0x140006b5d  mov     rbx, [rsp+38h+arg_8]
0x140006b62  cmp     dword ptr [rsp+38h+arg_0], 0
0x140006b67  mov     edx, eax
0x140006b69  mov     [rdi], eax
0x140006b6b  mov     ecx, eax
0x140006b6d  jz      short loc_140006B88
0x140006b6f  test    dl, 2
0x140006b72  jnz     short loc_140006B88
0x140006b74  and     ecx, 0FFFFF63Eh
0x140006b7a  mov     eax, ebx
0x140006b7c  and     eax, 9C1h
0x140006b81  or      ecx, eax
0x140006b83  or      ecx, 2
0x140006b86  mov     [rdi], ecx
0x140006b88  mov     r8d, edx
0x140006b8b  and     r8d, 4
0x140006b8f  jnz     short loc_140006BA3
0x140006b91  btr     ecx, 0Ah
0x140006b95  mov     eax, ebx
0x140006b97  and     eax, 400h
0x140006b9c  or      ecx, eax
0x140006b9e  or      ecx, 4
0x140006ba1  mov     [rdi], ecx
0x140006ba3  mov     eax, edx
0x140006ba5  lock cmpxchg [rsi], ecx
0x140006ba9  jnz     short loc_140006B62
0x140006bab  test    r8d, r8d
0x140006bae  jnz     short loc_140006BC0
0x140006bb0  mov     r8d, ebp
0x140006bb3  mov     edx, 3
0x140006bb8  mov     rcx, rsi
0x140006bbb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006bc0  mov     eax, [rdi]
0x140006bc2  test    al, 2
0x140006bc4  jnz     short loc_140006BD5
0x140006bc6  and     eax, 0FFFFF63Eh
0x140006bcb  and     ebx, 9C1h
0x140006bd1  or      eax, ebx
0x140006bd3  mov     [rdi], eax
0x140006bd5  mov     rbx, [rsp+38h+arg_10]
0x140006bda  mov     rax, rdi
0x140006bdd  add     rsp, 20h
0x140006be1  pop     rdi
0x140006be2  pop     rsi
0x140006be3  pop     rbp
0x140006be4  retn
```
