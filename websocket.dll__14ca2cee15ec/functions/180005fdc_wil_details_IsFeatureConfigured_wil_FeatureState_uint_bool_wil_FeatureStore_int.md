# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180005fdc`
- end: `0x1800060be`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008760`

## callees

- `0x180004bb8`
- `0x180005fdc`
- `0x1800080e8`
- `0x1800090b4`

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
  __int64 v9; // r9
  unsigned int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rdx
  bool v15; // di
  char v16; // r8
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v9 = *(unsigned int *)v7;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (v9 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((__int64)a1, a2, a3, v9, 0, a5) != 0;
  v17 = 1;
  v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v13 = wil_QueryFeatureState((__int64)a1, a2, v5, v12, &v17, a5);
  v14 = v17;
  v15 = v13 != 0;
  v16 = _InterlockedExchange((volatile __int32 *)v7, (v17 != 0) + 6);
  if ( !(_DWORD)v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v14, v11);
  return v15;
}

```

## disassembly

```asm
0x180005fdc  mov     [rsp+arg_0], rbx
0x180005fe1  mov     [rsp+arg_8], rbp
0x180005fe6  push    rsi
0x180005fe7  push    rdi
0x180005fe8  push    r14
0x180005fea  sub     rsp, 30h
0x180005fee  test    r9d, r9d
0x180005ff1  movzx   edi, r8b
0x180005ff5  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180005ffc  mov     esi, edx
0x180005ffe  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180006005  mov     rbp, rcx
0x180006008  cmovnz  rbx, rax
0x18000600c  mov     r9d, [rbx]
0x18000600f  mov     eax, r9d
0x180006012  and     al, 3
0x180006014  cmp     al, 2
0x180006016  jnz     short loc_18000601F
0x180006018  xor     al, al
0x18000601a  jmp     loc_1800060AB
0x18000601f  test    r9b, 2
0x180006023  jnz     short loc_18000608B
0x180006025  mov     [rsp+48h+arg_18], 1
0x18000602d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006032  mov     rcx, [rsp+48h+arg_20]
0x180006037  mov     r14d, eax
0x18000603a  mov     [rsp+48h+var_20], rcx
0x18000603f  lea     rax, [rsp+48h+arg_18]
0x180006044  mov     rcx, rbp
0x180006047  mov     [rsp+48h+var_28], rax
0x18000604c  mov     r8d, edi
0x18000604f  mov     edx, esi
0x180006051  call    wil_QueryFeatureState
0x180006056  mov     edx, [rsp+48h+arg_18]
0x18000605a  test    eax, eax
0x18000605c  mov     ecx, edx
0x18000605e  setnz   dil
0x180006062  neg     ecx
0x180006064  sbb     r8d, r8d
0x180006067  neg     r8d
0x18000606a  add     r8d, 6
0x18000606e  xchg    r8d, [rbx]
0x180006071  test    edx, edx
0x180006073  jnz     short loc_180006086
0x180006075  test    r8b, 4
0x180006079  jnz     short loc_180006086
0x18000607b  mov     r8d, r14d
0x18000607e  mov     rcx, rbx
0x180006081  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006086  mov     al, dil
0x180006089  jmp     short loc_1800060AB
0x18000608b  mov     rax, [rsp+48h+arg_20]
0x180006090  mov     r8d, edi
0x180006093  mov     [rsp+48h+var_20], rax
0x180006098  mov     [rsp+48h+var_28], 0
0x1800060a1  call    wil_QueryFeatureState
0x1800060a6  test    eax, eax
0x1800060a8  setnz   al
0x1800060ab  mov     rbx, [rsp+48h+arg_0]
0x1800060b0  mov     rbp, [rsp+48h+arg_8]
0x1800060b5  add     rsp, 30h
0x1800060b9  pop     r14
0x1800060bb  pop     rdi
0x1800060bc  pop     rsi
0x1800060bd  retn
```
