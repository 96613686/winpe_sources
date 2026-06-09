# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x140009eb4`
- end: `0x140009f96`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000bde0`

## callees

- `0x140009698`
- `0x140009eb4`
- `0x14000b9b0`
- `0x14000c718`

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
0x140009eb4  mov     [rsp+arg_0], rbx
0x140009eb9  mov     [rsp+arg_8], rbp
0x140009ebe  push    rsi
0x140009ebf  push    rdi
0x140009ec0  push    r14
0x140009ec2  sub     rsp, 30h
0x140009ec6  test    r9d, r9d
0x140009ec9  movzx   edi, r8b
0x140009ecd  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x140009ed4  mov     esi, edx
0x140009ed6  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x140009edd  mov     rbp, rcx
0x140009ee0  cmovnz  rbx, rax
0x140009ee4  mov     r9d, [rbx]
0x140009ee7  mov     eax, r9d
0x140009eea  and     al, 3
0x140009eec  cmp     al, 2
0x140009eee  jnz     short loc_140009EF7
0x140009ef0  xor     al, al
0x140009ef2  jmp     loc_140009F83
0x140009ef7  test    r9b, 2
0x140009efb  jnz     short loc_140009F63
0x140009efd  mov     [rsp+48h+arg_18], 1
0x140009f05  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009f0a  mov     rcx, [rsp+48h+arg_20]
0x140009f0f  mov     r14d, eax
0x140009f12  mov     [rsp+48h+var_20], rcx
0x140009f17  lea     rax, [rsp+48h+arg_18]
0x140009f1c  mov     rcx, rbp
0x140009f1f  mov     [rsp+48h+var_28], rax
0x140009f24  mov     r8d, edi
0x140009f27  mov     edx, esi
0x140009f29  call    wil_QueryFeatureState
0x140009f2e  mov     edx, [rsp+48h+arg_18]
0x140009f32  test    eax, eax
0x140009f34  mov     ecx, edx
0x140009f36  setnz   dil
0x140009f3a  neg     ecx
0x140009f3c  sbb     r8d, r8d
0x140009f3f  neg     r8d
0x140009f42  add     r8d, 6
0x140009f46  xchg    r8d, [rbx]
0x140009f49  test    edx, edx
0x140009f4b  jnz     short loc_140009F5E
0x140009f4d  test    r8b, 4
0x140009f51  jnz     short loc_140009F5E
0x140009f53  mov     r8d, r14d
0x140009f56  mov     rcx, rbx
0x140009f59  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009f5e  mov     al, dil
0x140009f61  jmp     short loc_140009F83
0x140009f63  mov     rax, [rsp+48h+arg_20]
0x140009f68  mov     r8d, edi
0x140009f6b  mov     [rsp+48h+var_20], rax
0x140009f70  mov     [rsp+48h+var_28], 0
0x140009f79  call    wil_QueryFeatureState
0x140009f7e  test    eax, eax
0x140009f80  setnz   al
0x140009f83  mov     rbx, [rsp+48h+arg_0]
0x140009f88  mov     rbp, [rsp+48h+arg_8]
0x140009f8d  add     rsp, 30h
0x140009f91  pop     r14
0x140009f93  pop     rdi
0x140009f94  pop     rsi
0x140009f95  retn
```
