# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180009434`
- end: `0x18000950d`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b850`

## callees

- `0x1800084c4`
- `0x180009434`
- `0x18000b21c`
- `0x18000c850`

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
0x180009434  mov     [rsp+arg_0], rbx
0x180009439  mov     [rsp+arg_8], rbp
0x18000943e  push    rsi
0x18000943f  push    rdi
0x180009440  push    r14
0x180009442  sub     rsp, 20h
0x180009446  test    r9d, r9d
0x180009449  movzx   edi, r8b
0x18000944d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180009454  mov     esi, edx
0x180009456  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000945d  mov     rbp, rcx
0x180009460  cmovnz  rbx, rax
0x180009464  mov     r9d, [rbx]
0x180009467  mov     eax, r9d
0x18000946a  and     al, 3
0x18000946c  cmp     al, 2
0x18000946e  jnz     short loc_180009477
0x180009470  xor     al, al
0x180009472  jmp     loc_1800094FA
0x180009477  test    r9b, 2
0x18000947b  jnz     short loc_1800094DF
0x18000947d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009482  mov     rcx, [rsp+38h+arg_20]
0x180009487  lea     r9, [rsp+38h+arg_18]
0x18000948c  mov     r8d, edi
0x18000948f  mov     [rsp+38h+arg_18], 0
0x180009497  mov     edx, esi
0x180009499  mov     r14d, eax
0x18000949c  mov     dword ptr [rcx], 1
0x1800094a2  mov     rcx, rbp
0x1800094a5  call    wil_RtlStagingConfig_QueryFeatureState
0x1800094aa  mov     edx, [rsp+38h+arg_18]
0x1800094ae  test    eax, eax
0x1800094b0  mov     ecx, edx
0x1800094b2  setnz   dil
0x1800094b6  neg     ecx
0x1800094b8  sbb     r8d, r8d
0x1800094bb  neg     r8d
0x1800094be  add     r8d, 6
0x1800094c2  xchg    r8d, [rbx]
0x1800094c5  test    edx, edx
0x1800094c7  jnz     short loc_1800094DA
0x1800094c9  test    r8b, 4
0x1800094cd  jnz     short loc_1800094DA
0x1800094cf  mov     r8d, r14d
0x1800094d2  mov     rcx, rbx
0x1800094d5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800094da  mov     al, dil
0x1800094dd  jmp     short loc_1800094FA
0x1800094df  mov     rax, [rsp+38h+arg_20]
0x1800094e4  mov     r8d, edi
0x1800094e7  xor     r9d, r9d
0x1800094ea  mov     dword ptr [rax], 1
0x1800094f0  call    wil_RtlStagingConfig_QueryFeatureState
0x1800094f5  test    eax, eax
0x1800094f7  setnz   al
0x1800094fa  mov     rbx, [rsp+38h+arg_0]
0x1800094ff  mov     rbp, [rsp+38h+arg_8]
0x180009504  add     rsp, 20h
0x180009508  pop     r14
0x18000950a  pop     rdi
0x18000950b  pop     rsi
0x18000950c  retn
```
