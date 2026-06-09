# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x140011ec0`
- end: `0x140011fa2`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140014460`

## callees

- `0x140006724`
- `0x14000a768`
- `0x140011ec0`
- `0x140014e18`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, int a2, unsigned __int8 a3, int a4, __int64 a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  int v8; // ebp
  volatile __int32 v9; // r9d
  unsigned int v11; // r14d
  int v12; // r9d
  int FeatureState; // eax
  __int64 v14; // rdx
  bool v15; // di
  char v16; // r8
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  v8 = (int)a1;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v9 = *(_DWORD *)v7;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (v9 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((_DWORD)a1, a2, a3, v9, 0, a5) != 0;
  v17 = 1;
  v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  FeatureState = wil_QueryFeatureState(v8, a2, v5, v12, (__int64)&v17, a5);
  v14 = v17;
  v15 = FeatureState != 0;
  v16 = _InterlockedExchange((volatile __int32 *)v7, (v17 != 0) + 6);
  if ( !(_DWORD)v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v14, v11);
  return v15;
}

```

## disassembly

```asm
0x140011ec0  mov     [rsp+arg_0], rbx
0x140011ec5  mov     [rsp+arg_8], rbp
0x140011eca  push    rsi
0x140011ecb  push    rdi
0x140011ecc  push    r14
0x140011ece  sub     rsp, 30h
0x140011ed2  test    r9d, r9d
0x140011ed5  movzx   edi, r8b
0x140011ed9  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x140011ee0  mov     esi, edx
0x140011ee2  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x140011ee9  mov     rbp, rcx
0x140011eec  cmovnz  rbx, rax
0x140011ef0  mov     r9d, [rbx]
0x140011ef3  mov     eax, r9d
0x140011ef6  and     al, 3
0x140011ef8  cmp     al, 2
0x140011efa  jnz     short loc_140011F03
0x140011efc  xor     al, al
0x140011efe  jmp     loc_140011F8F
0x140011f03  test    r9b, 2
0x140011f07  jnz     short loc_140011F6F
0x140011f09  mov     [rsp+48h+arg_18], 1
0x140011f11  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140011f16  mov     rcx, [rsp+48h+arg_20]
0x140011f1b  mov     r14d, eax
0x140011f1e  mov     [rsp+48h+var_20], rcx
0x140011f23  lea     rax, [rsp+48h+arg_18]
0x140011f28  mov     rcx, rbp
0x140011f2b  mov     [rsp+48h+var_28], rax
0x140011f30  mov     r8d, edi
0x140011f33  mov     edx, esi
0x140011f35  call    wil_QueryFeatureState
0x140011f3a  mov     edx, [rsp+48h+arg_18]
0x140011f3e  test    eax, eax
0x140011f40  mov     ecx, edx
0x140011f42  setnz   dil
0x140011f46  neg     ecx
0x140011f48  sbb     r8d, r8d
0x140011f4b  neg     r8d
0x140011f4e  add     r8d, 6
0x140011f52  xchg    r8d, [rbx]
0x140011f55  test    edx, edx
0x140011f57  jnz     short loc_140011F6A
0x140011f59  test    r8b, 4
0x140011f5d  jnz     short loc_140011F6A
0x140011f5f  mov     r8d, r14d
0x140011f62  mov     rcx, rbx
0x140011f65  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140011f6a  mov     al, dil
0x140011f6d  jmp     short loc_140011F8F
0x140011f6f  mov     rax, [rsp+48h+arg_20]
0x140011f74  mov     r8d, edi
0x140011f77  mov     [rsp+48h+var_20], rax
0x140011f7c  mov     [rsp+48h+var_28], 0
0x140011f85  call    wil_QueryFeatureState
0x140011f8a  test    eax, eax
0x140011f8c  setnz   al
0x140011f8f  mov     rbx, [rsp+48h+arg_0]
0x140011f94  mov     rbp, [rsp+48h+arg_8]
0x140011f99  add     rsp, 30h
0x140011f9d  pop     r14
0x140011f9f  pop     rdi
0x140011fa0  pop     rsi
0x140011fa1  retn
```
