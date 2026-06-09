# wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::GetCachedFeatureEnabledState(void)

- ea: `0x180022bf8`
- end: `0x180022cd1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023d30`
- `0x18002463c`

## callees

- `0x18000d020`
- `0x1800105e0`
- `0x180022bf8`
- `0x180022d98`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_FullHostUrlInSmartScreenInitializedTelemetry__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_FullHostUrlInSmartScreenInitializedTelemetry__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_FullHostUrlInSmartScreenInitializedTelemetry__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_FullHostUrlInSmartScreenInitializedTelemetry__descriptor,
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
0x180022bf8  mov     [rsp+arg_10], rbx
0x180022bfd  mov     [rsp+arg_0], rcx
0x180022c02  push    rbp
0x180022c03  push    rsi
0x180022c04  push    rdi
0x180022c05  sub     rsp, 20h
0x180022c09  mov     rsi, cs:Feature_FullHostUrlInSmartScreenInitializedTelemetry__descriptor
0x180022c10  mov     rdi, rdx
0x180022c13  mov     qword ptr [rdx], 0
0x180022c1a  mov     eax, [rsi]
0x180022c1c  mov     [rdx], eax
0x180022c1e  and     eax, 6
0x180022c21  cmp     al, 6
0x180022c23  jz      loc_180022CC1
0x180022c29  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180022c2e  lea     r8, [rsp+38h+arg_0]
0x180022c33  mov     dword ptr [rsp+38h+arg_0], 0
0x180022c3b  lea     rdx, [rsp+38h+arg_8]
0x180022c40  mov     ebp, eax
0x180022c42  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FullHostUrlInSmartScreenInitializedTelemetry>::GetCurrentFeatureEnabledState(int *)
0x180022c47  mov     eax, [rdi]
0x180022c49  mov     rbx, [rsp+38h+arg_8]
0x180022c4e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180022c53  mov     edx, eax
0x180022c55  mov     [rdi], eax
0x180022c57  mov     ecx, eax
0x180022c59  jz      short loc_180022C74
0x180022c5b  test    dl, 2
0x180022c5e  jnz     short loc_180022C74
0x180022c60  and     ecx, 0FFFFF63Eh
0x180022c66  mov     eax, ebx
0x180022c68  and     eax, 9C1h
0x180022c6d  or      ecx, eax
0x180022c6f  or      ecx, 2
0x180022c72  mov     [rdi], ecx
0x180022c74  mov     r8d, edx
0x180022c77  and     r8d, 4
0x180022c7b  jnz     short loc_180022C8F
0x180022c7d  btr     ecx, 0Ah
0x180022c81  mov     eax, ebx
0x180022c83  and     eax, 400h
0x180022c88  or      ecx, eax
0x180022c8a  or      ecx, 4
0x180022c8d  mov     [rdi], ecx
0x180022c8f  mov     eax, edx
0x180022c91  lock cmpxchg [rsi], ecx
0x180022c95  jnz     short loc_180022C4E
0x180022c97  test    r8d, r8d
0x180022c9a  jnz     short loc_180022CAC
0x180022c9c  mov     r8d, ebp
0x180022c9f  mov     edx, 3
0x180022ca4  mov     rcx, rsi
0x180022ca7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180022cac  mov     eax, [rdi]
0x180022cae  test    al, 2
0x180022cb0  jnz     short loc_180022CC1
0x180022cb2  and     eax, 0FFFFF63Eh
0x180022cb7  and     ebx, 9C1h
0x180022cbd  or      eax, ebx
0x180022cbf  mov     [rdi], eax
0x180022cc1  mov     rbx, [rsp+38h+arg_10]
0x180022cc6  mov     rax, rdi
0x180022cc9  add     rsp, 20h
0x180022ccd  pop     rdi
0x180022cce  pop     rsi
0x180022ccf  pop     rbp
0x180022cd0  retn
```
