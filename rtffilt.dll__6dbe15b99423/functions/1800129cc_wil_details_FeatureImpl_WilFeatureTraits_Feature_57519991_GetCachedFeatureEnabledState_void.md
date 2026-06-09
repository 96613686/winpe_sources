# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::GetCachedFeatureEnabledState(void)

- ea: `0x1800129cc`
- end: `0x180012aa5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014e68`
- `0x1800155c4`
- `0x180015604`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x1800129cc`
- `0x1800136e4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // eax
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
  v3 = *(_DWORD *)Feature_57519991__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57519991__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57519991__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_57519991__descriptor,
        3u,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800129cc  mov     [rsp+arg_10], rbx
0x1800129d1  mov     [rsp+arg_0], rcx
0x1800129d6  push    rbp
0x1800129d7  push    rsi
0x1800129d8  push    rdi
0x1800129d9  sub     rsp, 20h
0x1800129dd  mov     rsi, cs:Feature_57519991__descriptor
0x1800129e4  mov     rdi, rdx
0x1800129e7  mov     qword ptr [rdx], 0
0x1800129ee  mov     eax, [rsi]
0x1800129f0  mov     [rdx], eax
0x1800129f2  and     eax, 6
0x1800129f5  cmp     al, 6
0x1800129f7  jz      loc_180012A95
0x1800129fd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012a02  lea     r8, [rsp+38h+arg_0]
0x180012a07  mov     dword ptr [rsp+38h+arg_0], 0
0x180012a0f  lea     rdx, [rsp+38h+arg_8]
0x180012a14  mov     ebp, eax
0x180012a16  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::GetCurrentFeatureEnabledState(int *)
0x180012a1b  mov     eax, [rdi]
0x180012a1d  mov     rbx, [rsp+38h+arg_8]
0x180012a22  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012a27  mov     edx, eax
0x180012a29  mov     [rdi], eax
0x180012a2b  mov     ecx, eax
0x180012a2d  jz      short loc_180012A48
0x180012a2f  test    dl, 2
0x180012a32  jnz     short loc_180012A48
0x180012a34  and     ecx, 0FFFFF63Eh
0x180012a3a  mov     eax, ebx
0x180012a3c  and     eax, 9C1h
0x180012a41  or      ecx, eax
0x180012a43  or      ecx, 2
0x180012a46  mov     [rdi], ecx
0x180012a48  mov     r8d, edx
0x180012a4b  and     r8d, 4
0x180012a4f  jnz     short loc_180012A63
0x180012a51  btr     ecx, 0Ah
0x180012a55  mov     eax, ebx
0x180012a57  and     eax, 400h
0x180012a5c  or      ecx, eax
0x180012a5e  or      ecx, 4
0x180012a61  mov     [rdi], ecx
0x180012a63  mov     eax, edx
0x180012a65  lock cmpxchg [rsi], ecx
0x180012a69  jnz     short loc_180012A22
0x180012a6b  test    r8d, r8d
0x180012a6e  jnz     short loc_180012A80
0x180012a70  mov     r8d, ebp
0x180012a73  mov     edx, 3
0x180012a78  mov     rcx, rsi
0x180012a7b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012a80  mov     eax, [rdi]
0x180012a82  test    al, 2
0x180012a84  jnz     short loc_180012A95
0x180012a86  and     eax, 0FFFFF63Eh
0x180012a8b  and     ebx, 9C1h
0x180012a91  or      eax, ebx
0x180012a93  mov     [rdi], eax
0x180012a95  mov     rbx, [rsp+38h+arg_10]
0x180012a9a  mov     rax, rdi
0x180012a9d  add     rsp, 20h
0x180012aa1  pop     rdi
0x180012aa2  pop     rsi
0x180012aa3  pop     rbp
0x180012aa4  retn
```
