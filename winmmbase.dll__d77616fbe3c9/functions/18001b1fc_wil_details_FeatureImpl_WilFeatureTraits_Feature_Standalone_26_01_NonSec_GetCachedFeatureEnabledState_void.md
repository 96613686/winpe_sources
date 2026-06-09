# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b1fc`
- end: `0x18001b2d5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c420`

## callees

- `0x18001403c`
- `0x180016068`
- `0x18001b1fc`
- `0x18001bb7c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001b1fc  mov     [rsp+arg_10], rbx
0x18001b201  mov     [rsp+arg_0], rcx
0x18001b206  push    rbp
0x18001b207  push    rsi
0x18001b208  push    rdi
0x18001b209  sub     rsp, 20h
0x18001b20d  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18001b214  mov     rdi, rdx
0x18001b217  mov     qword ptr [rdx], 0
0x18001b21e  mov     eax, [rsi]
0x18001b220  mov     [rdx], eax
0x18001b222  and     eax, 6
0x18001b225  cmp     al, 6
0x18001b227  jz      loc_18001B2C5
0x18001b22d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b232  lea     r8, [rsp+38h+arg_0]
0x18001b237  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b23f  lea     rdx, [rsp+38h+arg_8]
0x18001b244  mov     ebp, eax
0x18001b246  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001b24b  mov     eax, [rdi]
0x18001b24d  mov     rbx, [rsp+38h+arg_8]
0x18001b252  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001b257  mov     edx, eax
0x18001b259  mov     [rdi], eax
0x18001b25b  mov     ecx, eax
0x18001b25d  jz      short loc_18001B278
0x18001b25f  test    dl, 2
0x18001b262  jnz     short loc_18001B278
0x18001b264  and     ecx, 0FFFFF63Eh
0x18001b26a  mov     eax, ebx
0x18001b26c  and     eax, 9C1h
0x18001b271  or      ecx, eax
0x18001b273  or      ecx, 2
0x18001b276  mov     [rdi], ecx
0x18001b278  mov     r8d, edx
0x18001b27b  and     r8d, 4
0x18001b27f  jnz     short loc_18001B293
0x18001b281  btr     ecx, 0Ah
0x18001b285  mov     eax, ebx
0x18001b287  and     eax, 400h
0x18001b28c  or      ecx, eax
0x18001b28e  or      ecx, 4
0x18001b291  mov     [rdi], ecx
0x18001b293  mov     eax, edx
0x18001b295  lock cmpxchg [rsi], ecx
0x18001b299  jnz     short loc_18001B252
0x18001b29b  test    r8d, r8d
0x18001b29e  jnz     short loc_18001B2B0
0x18001b2a0  mov     r8d, ebp
0x18001b2a3  mov     edx, 3
0x18001b2a8  mov     rcx, rsi
0x18001b2ab  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b2b0  mov     eax, [rdi]
0x18001b2b2  test    al, 2
0x18001b2b4  jnz     short loc_18001B2C5
0x18001b2b6  and     eax, 0FFFFF63Eh
0x18001b2bb  and     ebx, 9C1h
0x18001b2c1  or      eax, ebx
0x18001b2c3  mov     [rdi], eax
0x18001b2c5  mov     rbx, [rsp+38h+arg_10]
0x18001b2ca  mov     rax, rdi
0x18001b2cd  add     rsp, 20h
0x18001b2d1  pop     rdi
0x18001b2d2  pop     rsi
0x18001b2d3  pop     rbp
0x18001b2d4  retn
```
