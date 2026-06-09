# wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x140014674`
- end: `0x14001475e`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014764`
- `0x140014800`

## callees

- `0x140005090`
- `0x140005154`
- `0x140014554`
- `0x140014674`
- `0x14001aa60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  __int64 v13; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+28h] [rbp-30h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) != 6 )
  {
    v14 = 0;
    v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v13,
      &v14);
    v7 = *(_DWORD *)a2;
    v8 = v13;
    do
    {
      v9 = v14 == 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)a1, 64, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140014674  mov     [rsp+arg_10], rbx
0x140014679  push    rbp
0x14001467a  push    rsi
0x14001467b  push    rdi
0x14001467c  sub     rsp, 40h
0x140014680  mov     rax, cs:__security_cookie
0x140014687  xor     rax, rsp
0x14001468a  mov     [rsp+58h+var_28], rax
0x14001468f  mov     qword ptr [rdx], 0
0x140014696  mov     rdi, rdx
0x140014699  mov     eax, [rcx]
0x14001469b  mov     rsi, rcx
0x14001469e  mov     [rdx], eax
0x1400146a0  and     eax, 6
0x1400146a3  cmp     al, 6
0x1400146a5  jz      loc_140014741
0x1400146ab  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400146b0  lea     r8, [rsp+58h+var_30]
0x1400146b5  mov     [rsp+58h+var_30], 0
0x1400146bd  lea     rdx, [rsp+58h+var_38]
0x1400146c2  mov     ebp, eax
0x1400146c4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x1400146c9  mov     eax, [rdi]
0x1400146cb  mov     rbx, [rsp+58h+var_38]
0x1400146d0  cmp     [rsp+58h+var_30], 0
0x1400146d5  mov     edx, eax
0x1400146d7  mov     [rdi], eax
0x1400146d9  mov     ecx, eax
0x1400146db  jz      short loc_1400146F6
0x1400146dd  test    dl, 2
0x1400146e0  jnz     short loc_1400146F6
0x1400146e2  and     ecx, 0FFFFF63Eh
0x1400146e8  mov     eax, ebx
0x1400146ea  and     eax, 9C1h
0x1400146ef  or      ecx, eax
0x1400146f1  or      ecx, 2
0x1400146f4  mov     [rdi], ecx
0x1400146f6  test    dl, 4
0x1400146f9  jnz     short loc_14001470D
0x1400146fb  btr     ecx, 0Ah
0x1400146ff  mov     eax, ebx
0x140014701  and     eax, 400h
0x140014706  or      ecx, eax
0x140014708  or      ecx, 4
0x14001470b  mov     [rdi], ecx
0x14001470d  mov     eax, edx
0x14001470f  lock cmpxchg [rsi], ecx
0x140014713  jnz     short loc_1400146D0
0x140014715  test    dl, 4
0x140014718  jnz     short loc_14001472A
0x14001471a  mov     r8d, ebp
0x14001471d  mov     edx, 40h ; '@'
0x140014722  mov     rcx, rsi
0x140014725  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14001472a  mov     ecx, [rdi]
0x14001472c  test    cl, 2
0x14001472f  jnz     short loc_140014741
0x140014731  and     ecx, 0FFFFF63Eh
0x140014737  and     ebx, 9C1h
0x14001473d  or      ecx, ebx
0x14001473f  mov     [rdi], ecx
0x140014741  mov     rax, rdi
0x140014744  mov     rcx, [rsp+58h+var_28]
0x140014749  xor     rcx, rsp; StackCookie
0x14001474c  call    __security_check_cookie
0x140014751  mov     rbx, [rsp+58h+arg_10]
0x140014756  add     rsp, 40h
0x14001475a  pop     rdi
0x14001475b  pop     rsi
0x14001475c  pop     rbp
0x14001475d  retn
```
