# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800156e4`
- end: `0x1800157bd`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800175a0`

## callees

- `0x1800150a0`
- `0x1800156e4`
- `0x180017190`
- `0x1800181bc`

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
0x1800156e4  mov     [rsp+arg_0], rbx
0x1800156e9  mov     [rsp+arg_8], rbp
0x1800156ee  push    rsi
0x1800156ef  push    rdi
0x1800156f0  push    r14
0x1800156f2  sub     rsp, 20h
0x1800156f6  test    r9d, r9d
0x1800156f9  movzx   edi, r8b
0x1800156fd  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180015704  mov     esi, edx
0x180015706  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18001570d  mov     rbp, rcx
0x180015710  cmovnz  rbx, rax
0x180015714  mov     r9d, [rbx]
0x180015717  mov     eax, r9d
0x18001571a  and     al, 3
0x18001571c  cmp     al, 2
0x18001571e  jnz     short loc_180015727
0x180015720  xor     al, al
0x180015722  jmp     loc_1800157AA
0x180015727  test    r9b, 2
0x18001572b  jnz     short loc_18001578F
0x18001572d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015732  mov     rcx, [rsp+38h+arg_20]
0x180015737  lea     r9, [rsp+38h+arg_18]
0x18001573c  mov     r8d, edi
0x18001573f  mov     [rsp+38h+arg_18], 0
0x180015747  mov     edx, esi
0x180015749  mov     r14d, eax
0x18001574c  mov     dword ptr [rcx], 1
0x180015752  mov     rcx, rbp
0x180015755  call    wil_RtlStagingConfig_QueryFeatureState
0x18001575a  mov     edx, [rsp+38h+arg_18]
0x18001575e  test    eax, eax
0x180015760  mov     ecx, edx
0x180015762  setnz   dil
0x180015766  neg     ecx
0x180015768  sbb     r8d, r8d
0x18001576b  neg     r8d
0x18001576e  add     r8d, 6
0x180015772  xchg    r8d, [rbx]
0x180015775  test    edx, edx
0x180015777  jnz     short loc_18001578A
0x180015779  test    r8b, 4
0x18001577d  jnz     short loc_18001578A
0x18001577f  mov     r8d, r14d
0x180015782  mov     rcx, rbx
0x180015785  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001578a  mov     al, dil
0x18001578d  jmp     short loc_1800157AA
0x18001578f  mov     rax, [rsp+38h+arg_20]
0x180015794  mov     r8d, edi
0x180015797  xor     r9d, r9d
0x18001579a  mov     dword ptr [rax], 1
0x1800157a0  call    wil_RtlStagingConfig_QueryFeatureState
0x1800157a5  test    eax, eax
0x1800157a7  setnz   al
0x1800157aa  mov     rbx, [rsp+38h+arg_0]
0x1800157af  mov     rbp, [rsp+38h+arg_8]
0x1800157b4  add     rsp, 20h
0x1800157b8  pop     r14
0x1800157ba  pop     rdi
0x1800157bb  pop     rsi
0x1800157bc  retn
```
