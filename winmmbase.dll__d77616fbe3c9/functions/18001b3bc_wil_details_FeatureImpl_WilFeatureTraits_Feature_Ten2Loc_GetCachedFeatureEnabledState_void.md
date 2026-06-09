# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b3bc`
- end: `0x18001b495`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c528`
- `0x18001c8ac`

## callees

- `0x18001403c`
- `0x180016068`
- `0x18001b3bc`
- `0x18001bc64`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Ten2Loc__descriptor,
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
0x18001b3bc  mov     [rsp+arg_10], rbx
0x18001b3c1  mov     [rsp+arg_0], rcx
0x18001b3c6  push    rbp
0x18001b3c7  push    rsi
0x18001b3c8  push    rdi
0x18001b3c9  sub     rsp, 20h
0x18001b3cd  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18001b3d4  mov     rdi, rdx
0x18001b3d7  mov     qword ptr [rdx], 0
0x18001b3de  mov     eax, [rsi]
0x18001b3e0  mov     [rdx], eax
0x18001b3e2  and     eax, 6
0x18001b3e5  cmp     al, 6
0x18001b3e7  jz      loc_18001B485
0x18001b3ed  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b3f2  lea     r8, [rsp+38h+arg_0]
0x18001b3f7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b3ff  lea     rdx, [rsp+38h+arg_8]
0x18001b404  mov     ebp, eax
0x18001b406  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18001b40b  mov     eax, [rdi]
0x18001b40d  mov     rbx, [rsp+38h+arg_8]
0x18001b412  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001b417  mov     edx, eax
0x18001b419  mov     [rdi], eax
0x18001b41b  mov     ecx, eax
0x18001b41d  jz      short loc_18001B438
0x18001b41f  test    dl, 2
0x18001b422  jnz     short loc_18001B438
0x18001b424  and     ecx, 0FFFFF63Eh
0x18001b42a  mov     eax, ebx
0x18001b42c  and     eax, 9C1h
0x18001b431  or      ecx, eax
0x18001b433  or      ecx, 2
0x18001b436  mov     [rdi], ecx
0x18001b438  mov     r8d, edx
0x18001b43b  and     r8d, 4
0x18001b43f  jnz     short loc_18001B453
0x18001b441  btr     ecx, 0Ah
0x18001b445  mov     eax, ebx
0x18001b447  and     eax, 400h
0x18001b44c  or      ecx, eax
0x18001b44e  or      ecx, 4
0x18001b451  mov     [rdi], ecx
0x18001b453  mov     eax, edx
0x18001b455  lock cmpxchg [rsi], ecx
0x18001b459  jnz     short loc_18001B412
0x18001b45b  test    r8d, r8d
0x18001b45e  jnz     short loc_18001B470
0x18001b460  mov     r8d, ebp
0x18001b463  mov     edx, 3
0x18001b468  mov     rcx, rsi
0x18001b46b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b470  mov     eax, [rdi]
0x18001b472  test    al, 2
0x18001b474  jnz     short loc_18001B485
0x18001b476  and     eax, 0FFFFF63Eh
0x18001b47b  and     ebx, 9C1h
0x18001b481  or      eax, ebx
0x18001b483  mov     [rdi], eax
0x18001b485  mov     rbx, [rsp+38h+arg_10]
0x18001b48a  mov     rax, rdi
0x18001b48d  add     rsp, 20h
0x18001b491  pop     rdi
0x18001b492  pop     rsi
0x18001b493  pop     rbp
0x18001b494  retn
```
