# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800078e8`
- end: `0x1800079ca`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ae40`

## callees

- `0x180006740`
- `0x1800078e8`
- `0x18000a780`
- `0x18000ba64`

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
0x1800078e8  mov     [rsp+arg_0], rbx
0x1800078ed  mov     [rsp+arg_8], rbp
0x1800078f2  push    rsi
0x1800078f3  push    rdi
0x1800078f4  push    r14
0x1800078f6  sub     rsp, 30h
0x1800078fa  test    r9d, r9d
0x1800078fd  movzx   edi, r8b
0x180007901  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180007908  mov     esi, edx
0x18000790a  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180007911  mov     rbp, rcx
0x180007914  cmovnz  rbx, rax
0x180007918  mov     r9d, [rbx]
0x18000791b  mov     eax, r9d
0x18000791e  and     al, 3
0x180007920  cmp     al, 2
0x180007922  jnz     short loc_18000792B
0x180007924  xor     al, al
0x180007926  jmp     loc_1800079B7
0x18000792b  test    r9b, 2
0x18000792f  jnz     short loc_180007997
0x180007931  mov     [rsp+48h+arg_18], 1
0x180007939  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000793e  mov     rcx, [rsp+48h+arg_20]
0x180007943  mov     r14d, eax
0x180007946  mov     [rsp+48h+var_20], rcx
0x18000794b  lea     rax, [rsp+48h+arg_18]
0x180007950  mov     rcx, rbp
0x180007953  mov     [rsp+48h+var_28], rax
0x180007958  mov     r8d, edi
0x18000795b  mov     edx, esi
0x18000795d  call    wil_QueryFeatureState
0x180007962  mov     edx, [rsp+48h+arg_18]
0x180007966  test    eax, eax
0x180007968  mov     ecx, edx
0x18000796a  setnz   dil
0x18000796e  neg     ecx
0x180007970  sbb     r8d, r8d
0x180007973  neg     r8d
0x180007976  add     r8d, 6
0x18000797a  xchg    r8d, [rbx]
0x18000797d  test    edx, edx
0x18000797f  jnz     short loc_180007992
0x180007981  test    r8b, 4
0x180007985  jnz     short loc_180007992
0x180007987  mov     r8d, r14d
0x18000798a  mov     rcx, rbx
0x18000798d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007992  mov     al, dil
0x180007995  jmp     short loc_1800079B7
0x180007997  mov     rax, [rsp+48h+arg_20]
0x18000799c  mov     r8d, edi
0x18000799f  mov     [rsp+48h+var_20], rax
0x1800079a4  mov     [rsp+48h+var_28], 0
0x1800079ad  call    wil_QueryFeatureState
0x1800079b2  test    eax, eax
0x1800079b4  setnz   al
0x1800079b7  mov     rbx, [rsp+48h+arg_0]
0x1800079bc  mov     rbp, [rsp+48h+arg_8]
0x1800079c1  add     rsp, 30h
0x1800079c5  pop     r14
0x1800079c7  pop     rdi
0x1800079c8  pop     rsi
0x1800079c9  retn
```
