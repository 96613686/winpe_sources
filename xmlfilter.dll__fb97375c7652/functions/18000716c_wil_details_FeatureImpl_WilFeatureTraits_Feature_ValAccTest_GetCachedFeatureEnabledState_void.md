# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000716c`
- end: `0x180007245`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d604`

## callees

- `0x180005dd0`
- `0x18000716c`
- `0x180007c40`
- `0x18000c3f0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValAccTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000716c  mov     [rsp+arg_10], rbx
0x180007171  mov     [rsp+arg_0], rcx
0x180007176  push    rbp
0x180007177  push    rsi
0x180007178  push    rdi
0x180007179  sub     rsp, 20h
0x18000717d  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180007184  mov     rdi, rdx
0x180007187  mov     qword ptr [rdx], 0
0x18000718e  mov     eax, [rsi]
0x180007190  mov     [rdx], eax
0x180007192  and     eax, 6
0x180007195  cmp     al, 6
0x180007197  jz      loc_180007235
0x18000719d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800071a2  lea     r8, [rsp+38h+arg_0]
0x1800071a7  mov     dword ptr [rsp+38h+arg_0], 0
0x1800071af  lea     rdx, [rsp+38h+arg_8]
0x1800071b4  mov     ebp, eax
0x1800071b6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x1800071bb  mov     eax, [rdi]
0x1800071bd  mov     rbx, [rsp+38h+arg_8]
0x1800071c2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800071c7  mov     edx, eax
0x1800071c9  mov     [rdi], eax
0x1800071cb  mov     ecx, eax
0x1800071cd  jz      short loc_1800071E8
0x1800071cf  test    dl, 2
0x1800071d2  jnz     short loc_1800071E8
0x1800071d4  and     ecx, 0FFFFF63Eh
0x1800071da  mov     eax, ebx
0x1800071dc  and     eax, 9C1h
0x1800071e1  or      ecx, eax
0x1800071e3  or      ecx, 2
0x1800071e6  mov     [rdi], ecx
0x1800071e8  mov     r8d, edx
0x1800071eb  and     r8d, 4
0x1800071ef  jnz     short loc_180007203
0x1800071f1  btr     ecx, 0Ah
0x1800071f5  mov     eax, ebx
0x1800071f7  and     eax, 400h
0x1800071fc  or      ecx, eax
0x1800071fe  or      ecx, 4
0x180007201  mov     [rdi], ecx
0x180007203  mov     eax, edx
0x180007205  lock cmpxchg [rsi], ecx
0x180007209  jnz     short loc_1800071C2
0x18000720b  test    r8d, r8d
0x18000720e  jnz     short loc_180007220
0x180007210  mov     r8d, ebp
0x180007213  mov     edx, 3
0x180007218  mov     rcx, rsi
0x18000721b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007220  mov     eax, [rdi]
0x180007222  test    al, 2
0x180007224  jnz     short loc_180007235
0x180007226  and     eax, 0FFFFF63Eh
0x18000722b  and     ebx, 9C1h
0x180007231  or      eax, ebx
0x180007233  mov     [rdi], eax
0x180007235  mov     rbx, [rsp+38h+arg_10]
0x18000723a  mov     rax, rdi
0x18000723d  add     rsp, 20h
0x180007241  pop     rdi
0x180007242  pop     rsi
0x180007243  pop     rbp
0x180007244  retn
```
