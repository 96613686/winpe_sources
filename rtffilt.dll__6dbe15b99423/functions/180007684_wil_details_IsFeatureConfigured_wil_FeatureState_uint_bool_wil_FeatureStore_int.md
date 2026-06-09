# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180007684`
- end: `0x180007766`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000be60`
- `0x18000bed0`

## callees

- `0x180005dd8`
- `0x180007684`
- `0x18000b3d8`
- `0x18000d24c`

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
  int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  int v14; // edx
  bool v15; // di
  char v16; // r8
  int v17; // [rsp+68h] [rbp+20h] BYREF

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
  if ( !v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v11);
  return v15;
}

```

## disassembly

```asm
0x180007684  mov     [rsp+arg_0], rbx
0x180007689  mov     [rsp+arg_8], rbp
0x18000768e  push    rsi
0x18000768f  push    rdi
0x180007690  push    r14
0x180007692  sub     rsp, 30h
0x180007696  test    r9d, r9d
0x180007699  movzx   edi, r8b
0x18000769d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800076a4  mov     esi, edx
0x1800076a6  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800076ad  mov     rbp, rcx
0x1800076b0  cmovnz  rbx, rax
0x1800076b4  mov     r9d, [rbx]
0x1800076b7  mov     eax, r9d
0x1800076ba  and     al, 3
0x1800076bc  cmp     al, 2
0x1800076be  jnz     short loc_1800076C7
0x1800076c0  xor     al, al
0x1800076c2  jmp     loc_180007753
0x1800076c7  test    r9b, 2
0x1800076cb  jnz     short loc_180007733
0x1800076cd  mov     [rsp+48h+arg_18], 1
0x1800076d5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800076da  mov     rcx, [rsp+48h+arg_20]
0x1800076df  mov     r14d, eax
0x1800076e2  mov     [rsp+48h+var_20], rcx
0x1800076e7  lea     rax, [rsp+48h+arg_18]
0x1800076ec  mov     rcx, rbp
0x1800076ef  mov     [rsp+48h+var_28], rax
0x1800076f4  mov     r8d, edi
0x1800076f7  mov     edx, esi
0x1800076f9  call    wil_QueryFeatureState
0x1800076fe  mov     edx, [rsp+48h+arg_18]
0x180007702  test    eax, eax
0x180007704  mov     ecx, edx
0x180007706  setnz   dil
0x18000770a  neg     ecx
0x18000770c  sbb     r8d, r8d
0x18000770f  neg     r8d
0x180007712  add     r8d, 6
0x180007716  xchg    r8d, [rbx]
0x180007719  test    edx, edx
0x18000771b  jnz     short loc_18000772E
0x18000771d  test    r8b, 4
0x180007721  jnz     short loc_18000772E
0x180007723  mov     r8d, r14d
0x180007726  mov     rcx, rbx
0x180007729  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000772e  mov     al, dil
0x180007731  jmp     short loc_180007753
0x180007733  mov     rax, [rsp+48h+arg_20]
0x180007738  mov     r8d, edi
0x18000773b  mov     [rsp+48h+var_20], rax
0x180007740  mov     [rsp+48h+var_28], 0
0x180007749  call    wil_QueryFeatureState
0x18000774e  test    eax, eax
0x180007750  setnz   al
0x180007753  mov     rbx, [rsp+48h+arg_0]
0x180007758  mov     rbp, [rsp+48h+arg_8]
0x18000775d  add     rsp, 30h
0x180007761  pop     r14
0x180007763  pop     rdi
0x180007764  pop     rsi
0x180007765  retn
```
