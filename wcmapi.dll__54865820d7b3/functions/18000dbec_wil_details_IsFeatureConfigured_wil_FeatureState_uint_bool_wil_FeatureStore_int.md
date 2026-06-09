# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000dbec`
- end: `0x18000dcc6`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010880`

## callees

- `0x18000cdac`
- `0x18000dbec`
- `0x180010298`
- `0x18001426c`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  int v11; // r14d
  int v12; // eax
  int v13; // edx
  bool v14; // di
  char v15; // r8
  int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !v13 && (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v11);
    return v14;
  }
}

```

## disassembly

```asm
0x18000dbec  mov     [rsp+arg_0], rbx
0x18000dbf1  mov     [rsp+arg_8], rbp
0x18000dbf6  push    rsi
0x18000dbf7  push    rdi
0x18000dbf8  push    r14
0x18000dbfa  sub     rsp, 20h
0x18000dbfe  test    r9d, r9d
0x18000dc01  movzx   edi, r8b
0x18000dc05  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000dc0c  mov     esi, edx
0x18000dc0e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000dc15  mov     rbp, rcx
0x18000dc18  cmovnz  rbx, rax
0x18000dc1c  mov     r9d, [rbx]
0x18000dc1f  mov     eax, r9d
0x18000dc22  and     al, 3
0x18000dc24  cmp     al, 2
0x18000dc26  jnz     short loc_18000DC2F
0x18000dc28  xor     al, al
0x18000dc2a  jmp     loc_18000DCB2
0x18000dc2f  test    r9b, 2
0x18000dc33  jnz     short loc_18000DC97
0x18000dc35  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000dc3a  mov     rcx, [rsp+38h+arg_20]
0x18000dc3f  lea     r9, [rsp+38h+arg_18]
0x18000dc44  mov     r8d, edi
0x18000dc47  mov     [rsp+38h+arg_18], 0
0x18000dc4f  mov     edx, esi
0x18000dc51  mov     r14d, eax
0x18000dc54  mov     dword ptr [rcx], 1
0x18000dc5a  mov     rcx, rbp
0x18000dc5d  call    wil_RtlStagingConfig_QueryFeatureState
0x18000dc62  mov     edx, [rsp+38h+arg_18]
0x18000dc66  test    eax, eax
0x18000dc68  mov     ecx, edx
0x18000dc6a  setnz   dil
0x18000dc6e  neg     ecx
0x18000dc70  sbb     r8d, r8d
0x18000dc73  neg     r8d
0x18000dc76  add     r8d, 6
0x18000dc7a  xchg    r8d, [rbx]
0x18000dc7d  test    edx, edx
0x18000dc7f  jnz     short loc_18000DC92
0x18000dc81  test    r8b, 4
0x18000dc85  jnz     short loc_18000DC92
0x18000dc87  mov     r8d, r14d
0x18000dc8a  mov     rcx, rbx
0x18000dc8d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dc92  mov     al, dil
0x18000dc95  jmp     short loc_18000DCB2
0x18000dc97  mov     rax, [rsp+38h+arg_20]
0x18000dc9c  mov     r8d, edi
0x18000dc9f  xor     r9d, r9d
0x18000dca2  mov     dword ptr [rax], 1
0x18000dca8  call    wil_RtlStagingConfig_QueryFeatureState
0x18000dcad  test    eax, eax
0x18000dcaf  setnz   al
0x18000dcb2  mov     rbx, [rsp+38h+arg_0]
0x18000dcb7  mov     rbp, [rsp+38h+arg_8]
0x18000dcbc  add     rsp, 20h
0x18000dcc0  pop     r14
0x18000dcc2  pop     rdi
0x18000dcc3  pop     rsi
0x18000dcc4  retn
```
