# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000ec7c`
- end: `0x18000ed55`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011c20`

## callees

- `0x18000b228`
- `0x18000d5d0`
- `0x18000ec7c`
- `0x180011590`

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
  v7 = `wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
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
0x18000ec7c  mov     [rsp+arg_0], rbx
0x18000ec81  mov     [rsp+arg_8], rbp
0x18000ec86  push    rsi
0x18000ec87  push    rdi
0x18000ec88  push    r14
0x18000ec8a  sub     rsp, 20h
0x18000ec8e  test    r9d, r9d
0x18000ec91  movzx   edi, r8b
0x18000ec95  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000ec9c  mov     esi, edx
0x18000ec9e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000eca5  mov     rbp, rcx
0x18000eca8  cmovnz  rbx, rax
0x18000ecac  mov     r9d, [rbx]
0x18000ecaf  mov     eax, r9d
0x18000ecb2  and     al, 3
0x18000ecb4  cmp     al, 2
0x18000ecb6  jnz     short loc_18000ECBF
0x18000ecb8  xor     al, al
0x18000ecba  jmp     loc_18000ED42
0x18000ecbf  test    r9b, 2
0x18000ecc3  jnz     short loc_18000ED27
0x18000ecc5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ecca  mov     rcx, [rsp+38h+arg_20]
0x18000eccf  lea     r9, [rsp+38h+arg_18]
0x18000ecd4  mov     r8d, edi
0x18000ecd7  mov     [rsp+38h+arg_18], 0
0x18000ecdf  mov     edx, esi
0x18000ece1  mov     r14d, eax
0x18000ece4  mov     dword ptr [rcx], 1
0x18000ecea  mov     rcx, rbp
0x18000eced  call    wil_RtlStagingConfig_QueryFeatureState
0x18000ecf2  mov     edx, [rsp+38h+arg_18]
0x18000ecf6  test    eax, eax
0x18000ecf8  mov     ecx, edx
0x18000ecfa  setnz   dil
0x18000ecfe  neg     ecx
0x18000ed00  sbb     r8d, r8d
0x18000ed03  neg     r8d
0x18000ed06  add     r8d, 6
0x18000ed0a  xchg    r8d, [rbx]
0x18000ed0d  test    edx, edx
0x18000ed0f  jnz     short loc_18000ED22
0x18000ed11  test    r8b, 4
0x18000ed15  jnz     short loc_18000ED22
0x18000ed17  mov     r8d, r14d
0x18000ed1a  mov     rcx, rbx
0x18000ed1d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ed22  mov     al, dil
0x18000ed25  jmp     short loc_18000ED42
0x18000ed27  mov     rax, [rsp+38h+arg_20]
0x18000ed2c  mov     r8d, edi
0x18000ed2f  xor     r9d, r9d
0x18000ed32  mov     dword ptr [rax], 1
0x18000ed38  call    wil_RtlStagingConfig_QueryFeatureState
0x18000ed3d  test    eax, eax
0x18000ed3f  setnz   al
0x18000ed42  mov     rbx, [rsp+38h+arg_0]
0x18000ed47  mov     rbp, [rsp+38h+arg_8]
0x18000ed4c  add     rsp, 20h
0x18000ed50  pop     r14
0x18000ed52  pop     rdi
0x18000ed53  pop     rsi
0x18000ed54  retn
```
