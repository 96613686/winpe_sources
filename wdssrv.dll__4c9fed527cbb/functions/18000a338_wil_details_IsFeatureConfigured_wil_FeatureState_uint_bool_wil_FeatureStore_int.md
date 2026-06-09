# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000a338`
- end: `0x18000a40e`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e480`

## callees

- `0x180008724`
- `0x18000a338`
- `0x18000da58`
- `0x18000f338`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        __int64 a4,
        _DWORD *a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  unsigned int v10; // r14d
  __int64 v11; // r9
  bool v12; // di
  char v13; // dl
  int v14; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( (_DWORD)a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 2) != 0 )
    return (*(_DWORD *)v7 & 1) != 0 && (unsigned int)wil_QueryFeatureState((__int64)a1, a2, a3, a4, 0, a5) != 0;
  v14 = 1;
  v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v12 = (unsigned int)wil_QueryFeatureState((__int64)a1, a2, v5, v11, &v14, a5) != 0;
  v13 = _InterlockedExchange((volatile __int32 *)v7, (v14 != 0) + 6);
  if ( !v14 && (v13 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, 0, v10);
  return v12;
}

```

## disassembly

```asm
0x18000a338  mov     [rsp+arg_0], rbx
0x18000a33d  mov     [rsp+arg_8], rbp
0x18000a342  push    rsi
0x18000a343  push    rdi
0x18000a344  push    r14
0x18000a346  sub     rsp, 30h
0x18000a34a  test    r9d, r9d
0x18000a34d  movzx   edi, r8b
0x18000a351  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000a358  mov     esi, edx
0x18000a35a  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000a361  mov     rbp, rcx
0x18000a364  cmovnz  rbx, rax
0x18000a368  mov     eax, [rbx]
0x18000a36a  test    al, 2
0x18000a36c  jz      short loc_18000A398
0x18000a36e  test    al, 1
0x18000a370  jnz     short loc_18000A379
0x18000a372  xor     al, al
0x18000a374  jmp     loc_18000A3FA
0x18000a379  mov     rax, [rsp+48h+arg_20]
0x18000a37e  mov     r8d, edi
0x18000a381  mov     [rsp+48h+var_20], rax
0x18000a386  and     [rsp+48h+var_28], 0
0x18000a38c  call    wil_QueryFeatureState
0x18000a391  test    eax, eax
0x18000a393  setnz   al
0x18000a396  jmp     short loc_18000A3FA
0x18000a398  mov     [rsp+48h+arg_18], 1
0x18000a3a0  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000a3a5  mov     rcx, [rsp+48h+arg_20]
0x18000a3aa  mov     r14d, eax
0x18000a3ad  mov     [rsp+48h+var_20], rcx
0x18000a3b2  lea     rax, [rsp+48h+arg_18]
0x18000a3b7  mov     rcx, rbp
0x18000a3ba  mov     [rsp+48h+var_28], rax
0x18000a3bf  mov     r8d, edi
0x18000a3c2  mov     edx, esi
0x18000a3c4  call    wil_QueryFeatureState
0x18000a3c9  mov     ecx, [rsp+48h+arg_18]
0x18000a3cd  test    eax, eax
0x18000a3cf  setnz   dil
0x18000a3d3  neg     ecx
0x18000a3d5  sbb     edx, edx
0x18000a3d7  neg     edx
0x18000a3d9  add     edx, 6
0x18000a3dc  xchg    edx, [rbx]
0x18000a3de  cmp     [rsp+48h+arg_18], 0
0x18000a3e3  jnz     short loc_18000A3F7
0x18000a3e5  test    dl, 4
0x18000a3e8  jnz     short loc_18000A3F7
0x18000a3ea  mov     r8d, r14d
0x18000a3ed  xor     edx, edx
0x18000a3ef  mov     rcx, rbx
0x18000a3f2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000a3f7  mov     al, dil
0x18000a3fa  mov     rbx, [rsp+48h+arg_0]
0x18000a3ff  mov     rbp, [rsp+48h+arg_8]
0x18000a404  add     rsp, 30h
0x18000a408  pop     r14
0x18000a40a  pop     rdi
0x18000a40b  pop     rsi
0x18000a40c  retn
```
