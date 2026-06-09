# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180008e50`
- end: `0x180008f32`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000cc50`

## callees

- `0x180005dd0`
- `0x180008e50`
- `0x18000c3f0`
- `0x18000e1e8`

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
0x180008e50  mov     [rsp+arg_0], rbx
0x180008e55  mov     [rsp+arg_8], rbp
0x180008e5a  push    rsi
0x180008e5b  push    rdi
0x180008e5c  push    r14
0x180008e5e  sub     rsp, 30h
0x180008e62  test    r9d, r9d
0x180008e65  movzx   edi, r8b
0x180008e69  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180008e70  mov     esi, edx
0x180008e72  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180008e79  mov     rbp, rcx
0x180008e7c  cmovnz  rbx, rax
0x180008e80  mov     r9d, [rbx]
0x180008e83  mov     eax, r9d
0x180008e86  and     al, 3
0x180008e88  cmp     al, 2
0x180008e8a  jnz     short loc_180008E93
0x180008e8c  xor     al, al
0x180008e8e  jmp     loc_180008F1F
0x180008e93  test    r9b, 2
0x180008e97  jnz     short loc_180008EFF
0x180008e99  mov     [rsp+48h+arg_18], 1
0x180008ea1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008ea6  mov     rcx, [rsp+48h+arg_20]
0x180008eab  mov     r14d, eax
0x180008eae  mov     [rsp+48h+var_20], rcx
0x180008eb3  lea     rax, [rsp+48h+arg_18]
0x180008eb8  mov     rcx, rbp
0x180008ebb  mov     [rsp+48h+var_28], rax
0x180008ec0  mov     r8d, edi
0x180008ec3  mov     edx, esi
0x180008ec5  call    wil_QueryFeatureState
0x180008eca  mov     edx, [rsp+48h+arg_18]
0x180008ece  test    eax, eax
0x180008ed0  mov     ecx, edx
0x180008ed2  setnz   dil
0x180008ed6  neg     ecx
0x180008ed8  sbb     r8d, r8d
0x180008edb  neg     r8d
0x180008ede  add     r8d, 6
0x180008ee2  xchg    r8d, [rbx]
0x180008ee5  test    edx, edx
0x180008ee7  jnz     short loc_180008EFA
0x180008ee9  test    r8b, 4
0x180008eed  jnz     short loc_180008EFA
0x180008eef  mov     r8d, r14d
0x180008ef2  mov     rcx, rbx
0x180008ef5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008efa  mov     al, dil
0x180008efd  jmp     short loc_180008F1F
0x180008eff  mov     rax, [rsp+48h+arg_20]
0x180008f04  mov     r8d, edi
0x180008f07  mov     [rsp+48h+var_20], rax
0x180008f0c  mov     [rsp+48h+var_28], 0
0x180008f15  call    wil_QueryFeatureState
0x180008f1a  test    eax, eax
0x180008f1c  setnz   al
0x180008f1f  mov     rbx, [rsp+48h+arg_0]
0x180008f24  mov     rbp, [rsp+48h+arg_8]
0x180008f29  add     rsp, 30h
0x180008f2d  pop     r14
0x180008f2f  pop     rdi
0x180008f30  pop     rsi
0x180008f31  retn
```
