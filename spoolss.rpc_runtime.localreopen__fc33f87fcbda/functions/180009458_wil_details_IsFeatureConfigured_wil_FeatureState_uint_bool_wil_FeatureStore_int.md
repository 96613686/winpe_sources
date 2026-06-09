# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180009458`
- end: `0x180009540`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000be70`

## callees

- `0x180007f30`
- `0x180009458`
- `0x18000b894`
- `0x180010390`

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
  __int64 v14; // r8
  bool v15; // di
  char v16; // dl
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
    wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
      &wil::details::g_enabledStateManager,
      v7,
      v14,
      v11);
  return v15;
}

```

## disassembly

```asm
0x180009458  mov     [rsp+arg_0], rbx
0x18000945d  mov     [rsp+arg_8], rbp
0x180009462  push    rsi
0x180009463  push    rdi
0x180009464  push    r14
0x180009466  sub     rsp, 30h
0x18000946a  test    r9d, r9d
0x18000946d  movzx   edi, r8b
0x180009471  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180009478  mov     esi, edx
0x18000947a  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180009481  mov     rbp, rcx
0x180009484  cmovnz  rbx, rax
0x180009488  mov     r9d, [rbx]
0x18000948b  mov     eax, r9d
0x18000948e  and     al, 3
0x180009490  cmp     al, 2
0x180009492  jnz     short loc_18000949B
0x180009494  xor     al, al
0x180009496  jmp     loc_18000952C
0x18000949b  test    r9b, 2
0x18000949f  jnz     short loc_18000950C
0x1800094a1  mov     [rsp+48h+arg_18], 1
0x1800094a9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800094ae  mov     rcx, [rsp+48h+arg_20]
0x1800094b3  mov     r14d, eax
0x1800094b6  mov     [rsp+48h+var_20], rcx
0x1800094bb  lea     rax, [rsp+48h+arg_18]
0x1800094c0  mov     rcx, rbp
0x1800094c3  mov     [rsp+48h+var_28], rax
0x1800094c8  mov     r8d, edi
0x1800094cb  mov     edx, esi
0x1800094cd  call    wil_QueryFeatureState
0x1800094d2  mov     r8d, [rsp+48h+arg_18]
0x1800094d7  test    eax, eax
0x1800094d9  mov     ecx, r8d
0x1800094dc  setnz   dil
0x1800094e0  neg     ecx
0x1800094e2  sbb     edx, edx
0x1800094e4  neg     edx
0x1800094e6  add     edx, 6
0x1800094e9  xchg    edx, [rbx]
0x1800094eb  test    r8d, r8d
0x1800094ee  jnz     short loc_180009507
0x1800094f0  test    dl, 4
0x1800094f3  jnz     short loc_180009507
0x1800094f5  mov     r9d, r14d
0x1800094f8  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800094ff  mov     rdx, rbx
0x180009502  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180009507  mov     al, dil
0x18000950a  jmp     short loc_18000952C
0x18000950c  mov     rax, [rsp+48h+arg_20]
0x180009511  mov     r8d, edi
0x180009514  mov     [rsp+48h+var_20], rax
0x180009519  mov     [rsp+48h+var_28], 0
0x180009522  call    wil_QueryFeatureState
0x180009527  test    eax, eax
0x180009529  setnz   al
0x18000952c  mov     rbx, [rsp+48h+arg_0]
0x180009531  mov     rbp, [rsp+48h+arg_8]
0x180009536  add     rsp, 30h
0x18000953a  pop     r14
0x18000953c  pop     rdi
0x18000953d  pop     rsi
0x18000953e  retn
```
