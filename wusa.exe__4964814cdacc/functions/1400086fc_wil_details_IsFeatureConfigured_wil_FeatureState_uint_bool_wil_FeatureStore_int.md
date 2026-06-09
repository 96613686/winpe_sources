# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1400086fc`
- end: `0x1400087de`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000bc70`

## callees

- `0x1400068a4`
- `0x1400086fc`
- `0x14000ac68`
- `0x14000c9ec`

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
0x1400086fc  mov     [rsp+arg_0], rbx
0x140008701  mov     [rsp+arg_8], rbp
0x140008706  push    rsi
0x140008707  push    rdi
0x140008708  push    r14
0x14000870a  sub     rsp, 30h
0x14000870e  test    r9d, r9d
0x140008711  movzx   edi, r8b
0x140008715  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x14000871c  mov     esi, edx
0x14000871e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x140008725  mov     rbp, rcx
0x140008728  cmovnz  rbx, rax
0x14000872c  mov     r9d, [rbx]
0x14000872f  mov     eax, r9d
0x140008732  and     al, 3
0x140008734  cmp     al, 2
0x140008736  jnz     short loc_14000873F
0x140008738  xor     al, al
0x14000873a  jmp     loc_1400087CB
0x14000873f  test    r9b, 2
0x140008743  jnz     short loc_1400087AB
0x140008745  mov     [rsp+48h+arg_18], 1
0x14000874d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140008752  mov     rcx, [rsp+48h+arg_20]
0x140008757  mov     r14d, eax
0x14000875a  mov     [rsp+48h+var_20], rcx
0x14000875f  lea     rax, [rsp+48h+arg_18]
0x140008764  mov     rcx, rbp
0x140008767  mov     [rsp+48h+var_28], rax
0x14000876c  mov     r8d, edi
0x14000876f  mov     edx, esi
0x140008771  call    wil_QueryFeatureState
0x140008776  mov     edx, [rsp+48h+arg_18]
0x14000877a  test    eax, eax
0x14000877c  mov     ecx, edx
0x14000877e  setnz   dil
0x140008782  neg     ecx
0x140008784  sbb     r8d, r8d
0x140008787  neg     r8d
0x14000878a  add     r8d, 6
0x14000878e  xchg    r8d, [rbx]
0x140008791  test    edx, edx
0x140008793  jnz     short loc_1400087A6
0x140008795  test    r8b, 4
0x140008799  jnz     short loc_1400087A6
0x14000879b  mov     r8d, r14d
0x14000879e  mov     rcx, rbx
0x1400087a1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400087a6  mov     al, dil
0x1400087a9  jmp     short loc_1400087CB
0x1400087ab  mov     rax, [rsp+48h+arg_20]
0x1400087b0  mov     r8d, edi
0x1400087b3  mov     [rsp+48h+var_20], rax
0x1400087b8  mov     [rsp+48h+var_28], 0
0x1400087c1  call    wil_QueryFeatureState
0x1400087c6  test    eax, eax
0x1400087c8  setnz   al
0x1400087cb  mov     rbx, [rsp+48h+arg_0]
0x1400087d0  mov     rbp, [rsp+48h+arg_8]
0x1400087d5  add     rsp, 30h
0x1400087d9  pop     r14
0x1400087db  pop     rdi
0x1400087dc  pop     rsi
0x1400087dd  retn
```
