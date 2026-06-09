# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180006870`
- end: `0x180006949`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009a00`

## callees

- `0x180005384`
- `0x180006870`
- `0x180009148`
- `0x18000c784`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, __int64 a2, unsigned __int8 a3, int a4, _DWORD *a5)
{
  unsigned int v5; // edi
  unsigned int v6; // esi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  __int64 v13; // rdx
  bool v14; // di
  char v15; // r8
  unsigned int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v6 = a2;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState(a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState(a1, v6, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !(_DWORD)v13 && (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v13, v11);
    return v14;
  }
}

```

## disassembly

```asm
0x180006870  mov     [rsp+arg_0], rbx
0x180006875  mov     [rsp+arg_8], rbp
0x18000687a  push    rsi
0x18000687b  push    rdi
0x18000687c  push    r14
0x18000687e  sub     rsp, 20h
0x180006882  test    r9d, r9d
0x180006885  movzx   edi, r8b
0x180006889  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180006890  mov     esi, edx
0x180006892  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180006899  mov     rbp, rcx
0x18000689c  cmovnz  rbx, rax
0x1800068a0  mov     r9d, [rbx]
0x1800068a3  mov     eax, r9d
0x1800068a6  and     al, 3
0x1800068a8  cmp     al, 2
0x1800068aa  jnz     short loc_1800068B3
0x1800068ac  xor     al, al
0x1800068ae  jmp     loc_180006936
0x1800068b3  test    r9b, 2
0x1800068b7  jnz     short loc_18000691B
0x1800068b9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800068be  mov     rcx, [rsp+38h+arg_20]
0x1800068c3  lea     r9, [rsp+38h+arg_18]
0x1800068c8  mov     r8d, edi
0x1800068cb  mov     [rsp+38h+arg_18], 0
0x1800068d3  mov     edx, esi
0x1800068d5  mov     r14d, eax
0x1800068d8  mov     dword ptr [rcx], 1
0x1800068de  mov     rcx, rbp
0x1800068e1  call    wil_RtlStagingConfig_QueryFeatureState
0x1800068e6  mov     edx, [rsp+38h+arg_18]
0x1800068ea  test    eax, eax
0x1800068ec  mov     ecx, edx
0x1800068ee  setnz   dil
0x1800068f2  neg     ecx
0x1800068f4  sbb     r8d, r8d
0x1800068f7  neg     r8d
0x1800068fa  add     r8d, 6
0x1800068fe  xchg    r8d, [rbx]
0x180006901  test    edx, edx
0x180006903  jnz     short loc_180006916
0x180006905  test    r8b, 4
0x180006909  jnz     short loc_180006916
0x18000690b  mov     r8d, r14d
0x18000690e  mov     rcx, rbx
0x180006911  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006916  mov     al, dil
0x180006919  jmp     short loc_180006936
0x18000691b  mov     rax, [rsp+38h+arg_20]
0x180006920  mov     r8d, edi
0x180006923  xor     r9d, r9d
0x180006926  mov     dword ptr [rax], 1
0x18000692c  call    wil_RtlStagingConfig_QueryFeatureState
0x180006931  test    eax, eax
0x180006933  setnz   al
0x180006936  mov     rbx, [rsp+38h+arg_0]
0x18000693b  mov     rbp, [rsp+38h+arg_8]
0x180006940  add     rsp, 20h
0x180006944  pop     r14
0x180006946  pop     rdi
0x180006947  pop     rsi
0x180006948  retn
```
