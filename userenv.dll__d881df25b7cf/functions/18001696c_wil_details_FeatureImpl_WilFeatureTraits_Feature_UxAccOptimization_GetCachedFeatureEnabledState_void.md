# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18001696c`
- end: `0x180016aac`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018724`
- `0x180019440`

## callees

- `0x18000ddcc`
- `0x180016358`
- `0x18001696c`
- `0x180016bec`
- `0x1800194ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a2a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
  int v12; // r8d
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v16;
    do
    {
      v9 = (_DWORD)v15 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180029374
        || (v14[0] = 3,
            v14[1] = Feature_UxAccOptimization__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800293A8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001696c  mov     [rsp+arg_10], rbx
0x180016971  mov     [rsp+arg_18], rbp
0x180016976  mov     [rsp+arg_0], rcx
0x18001697b  push    rsi
0x18001697c  push    rdi
0x18001697d  push    r14
0x18001697f  sub     rsp, 30h
0x180016983  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18001698a  mov     rdi, rdx
0x18001698d  mov     qword ptr [rdx], 0
0x180016994  mov     eax, [rsi]
0x180016996  mov     [rdx], eax
0x180016998  and     eax, 6
0x18001699b  cmp     al, 6
0x18001699d  jz      loc_180016A95
0x1800169a3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800169a8  lea     r8, [rsp+48h+arg_0]
0x1800169ad  mov     dword ptr [rsp+48h+arg_0], 0
0x1800169b5  lea     rdx, [rsp+48h+arg_8]
0x1800169ba  mov     ebp, eax
0x1800169bc  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x1800169c1  mov     eax, [rdi]
0x1800169c3  mov     rbx, [rsp+48h+arg_8]
0x1800169c8  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800169cd  mov     edx, eax
0x1800169cf  mov     [rdi], eax
0x1800169d1  mov     ecx, eax
0x1800169d3  jz      short loc_1800169EE
0x1800169d5  test    dl, 2
0x1800169d8  jnz     short loc_1800169EE
0x1800169da  and     ecx, 0FFFFF63Eh
0x1800169e0  mov     eax, ebx
0x1800169e2  and     eax, 9C1h
0x1800169e7  or      ecx, eax
0x1800169e9  or      ecx, 2
0x1800169ec  mov     [rdi], ecx
0x1800169ee  mov     r8d, edx
0x1800169f1  and     r8d, 4
0x1800169f5  jnz     short loc_180016A09
0x1800169f7  btr     ecx, 0Ah
0x1800169fb  mov     eax, ebx
0x1800169fd  and     eax, 400h
0x180016a02  or      ecx, eax
0x180016a04  or      ecx, 4
0x180016a07  mov     [rdi], ecx
0x180016a09  mov     eax, edx
0x180016a0b  lock cmpxchg [rsi], ecx
0x180016a0f  jnz     short loc_1800169C8
0x180016a11  test    r8d, r8d
0x180016a14  jnz     short loc_180016A80
0x180016a16  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016a1c  test    eax, eax
0x180016a1e  jz      short loc_180016A80
0x180016a20  lea     r14, SRWLock
0x180016a27  mov     rcx, r14; SRWLock
0x180016a2a  call    cs:__imp_AcquireSRWLockExclusive
0x180016a31  nop     dword ptr [rax+rax+00h]
0x180016a36  mov     eax, cs:dword_180029374
0x180016a3c  mov     [rsp+48h+arg_8], r14
0x180016a41  test    ebp, ebp
0x180016a43  jz      short loc_180016A72
0x180016a45  cmp     ebp, eax
0x180016a47  jnz     short loc_180016A72
0x180016a49  mov     r8d, 10h; unsigned __int64
0x180016a4f  mov     [rsp+48h+var_28], 3
0x180016a58  lea     rdx, [rsp+48h+var_28]; void *
0x180016a5d  mov     [rsp+48h+var_20], rsi
0x180016a62  lea     rcx, qword_1800293A8; this
0x180016a69  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180016a6e  test    al, al
0x180016a70  jnz     short loc_180016A76
0x180016a72  lock and dword ptr [rsi], 0FFFFFFFBh
0x180016a76  lea     rcx, [rsp+48h+arg_8]
0x180016a7b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016a80  mov     eax, [rdi]
0x180016a82  test    al, 2
0x180016a84  jnz     short loc_180016A95
0x180016a86  and     eax, 0FFFFF63Eh
0x180016a8b  and     ebx, 9C1h
0x180016a91  or      eax, ebx
0x180016a93  mov     [rdi], eax
0x180016a95  mov     rbx, [rsp+48h+arg_10]
0x180016a9a  mov     rax, rdi
0x180016a9d  mov     rbp, [rsp+48h+arg_18]
0x180016aa2  add     rsp, 30h
0x180016aa6  pop     r14
0x180016aa8  pop     rdi
0x180016aa9  pop     rsi
0x180016aaa  retn
```
