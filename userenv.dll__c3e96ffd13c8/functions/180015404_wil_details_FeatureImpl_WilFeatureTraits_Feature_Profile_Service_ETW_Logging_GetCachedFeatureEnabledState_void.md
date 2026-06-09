# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(void)

- ea: `0x180015404`
- end: `0x1800154dd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016d84`
- `0x180017a94`

## callees

- `0x1800150a0`
- `0x180015404`
- `0x1800154e4`
- `0x180017190`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Profile_Service_ETW_Logging__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Profile_Service_ETW_Logging__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Profile_Service_ETW_Logging__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Profile_Service_ETW_Logging__descriptor,
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
0x180015404  mov     [rsp+arg_10], rbx
0x180015409  mov     [rsp+arg_0], rcx
0x18001540e  push    rbp
0x18001540f  push    rsi
0x180015410  push    rdi
0x180015411  sub     rsp, 20h
0x180015415  mov     rsi, cs:Feature_Profile_Service_ETW_Logging__descriptor
0x18001541c  mov     rdi, rdx
0x18001541f  mov     qword ptr [rdx], 0
0x180015426  mov     eax, [rsi]
0x180015428  mov     [rdx], eax
0x18001542a  and     eax, 6
0x18001542d  cmp     al, 6
0x18001542f  jz      loc_1800154CD
0x180015435  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001543a  lea     r8, [rsp+38h+arg_0]
0x18001543f  mov     dword ptr [rsp+38h+arg_0], 0
0x180015447  lea     rdx, [rsp+38h+arg_8]
0x18001544c  mov     ebp, eax
0x18001544e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCurrentFeatureEnabledState(int *)
0x180015453  mov     eax, [rdi]
0x180015455  mov     rbx, [rsp+38h+arg_8]
0x18001545a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001545f  mov     edx, eax
0x180015461  mov     [rdi], eax
0x180015463  mov     ecx, eax
0x180015465  jz      short loc_180015480
0x180015467  test    dl, 2
0x18001546a  jnz     short loc_180015480
0x18001546c  and     ecx, 0FFFFF63Eh
0x180015472  mov     eax, ebx
0x180015474  and     eax, 9C1h
0x180015479  or      ecx, eax
0x18001547b  or      ecx, 2
0x18001547e  mov     [rdi], ecx
0x180015480  mov     r8d, edx
0x180015483  and     r8d, 4
0x180015487  jnz     short loc_18001549B
0x180015489  btr     ecx, 0Ah
0x18001548d  mov     eax, ebx
0x18001548f  and     eax, 400h
0x180015494  or      ecx, eax
0x180015496  or      ecx, 4
0x180015499  mov     [rdi], ecx
0x18001549b  mov     eax, edx
0x18001549d  lock cmpxchg [rsi], ecx
0x1800154a1  jnz     short loc_18001545A
0x1800154a3  test    r8d, r8d
0x1800154a6  jnz     short loc_1800154B8
0x1800154a8  mov     r8d, ebp
0x1800154ab  mov     edx, 3
0x1800154b0  mov     rcx, rsi
0x1800154b3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800154b8  mov     eax, [rdi]
0x1800154ba  test    al, 2
0x1800154bc  jnz     short loc_1800154CD
0x1800154be  and     eax, 0FFFFF63Eh
0x1800154c3  and     ebx, 9C1h
0x1800154c9  or      eax, ebx
0x1800154cb  mov     [rdi], eax
0x1800154cd  mov     rbx, [rsp+38h+arg_10]
0x1800154d2  mov     rax, rdi
0x1800154d5  add     rsp, 20h
0x1800154d9  pop     rdi
0x1800154da  pop     rsi
0x1800154db  pop     rbp
0x1800154dc  retn
```
