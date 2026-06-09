# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800300d4`
- end: `0x18003020e`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800303f8`
- `0x180030484`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x1800300d4`
- `0x18003028c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030192`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030192`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  unsigned __int64 v13; // r8
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v16; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v17; // [rsp+58h] [rbp+10h] BYREF

  v16 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v17;
    do
    {
      v9 = (_DWORD)v16 == 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_TestAccPerf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800300d4  mov     [rsp+arg_10], rbx
0x1800300d9  mov     [rsp+arg_18], rbp
0x1800300de  mov     [rsp+arg_0], rcx
0x1800300e3  push    rsi
0x1800300e4  push    rdi
0x1800300e5  push    r14
0x1800300e7  sub     rsp, 30h
0x1800300eb  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x1800300f2  mov     rdi, rdx
0x1800300f5  mov     qword ptr [rdx], 0
0x1800300fc  mov     eax, [rsi]
0x1800300fe  mov     [rdx], eax
0x180030100  and     eax, 6
0x180030103  cmp     al, 6
0x180030105  jz      loc_1800301F7
0x18003010b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180030110  lea     r8, [rsp+48h+arg_0]
0x180030115  mov     dword ptr [rsp+48h+arg_0], 0
0x18003011d  lea     rdx, [rsp+48h+arg_8]
0x180030122  mov     ebp, eax
0x180030124  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180030129  mov     eax, [rdi]
0x18003012b  mov     rbx, [rsp+48h+arg_8]
0x180030130  cmp     dword ptr [rsp+48h+arg_0], 0
0x180030135  mov     edx, eax
0x180030137  mov     [rdi], eax
0x180030139  mov     ecx, eax
0x18003013b  jz      short loc_180030156
0x18003013d  test    dl, 2
0x180030140  jnz     short loc_180030156
0x180030142  and     ecx, 0FFFFF63Eh
0x180030148  mov     eax, ebx
0x18003014a  and     eax, 9C1h
0x18003014f  or      ecx, eax
0x180030151  or      ecx, 2
0x180030154  mov     [rdi], ecx
0x180030156  mov     r8d, edx
0x180030159  and     r8d, 4
0x18003015d  jnz     short loc_180030171
0x18003015f  btr     ecx, 0Ah
0x180030163  mov     eax, ebx
0x180030165  and     eax, 400h
0x18003016a  or      ecx, eax
0x18003016c  or      ecx, 4
0x18003016f  mov     [rdi], ecx
0x180030171  mov     eax, edx
0x180030173  lock cmpxchg [rsi], ecx
0x180030177  jnz     short loc_180030130
0x180030179  test    r8d, r8d
0x18003017c  jnz     short loc_1800301E2
0x18003017e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180030184  test    eax, eax
0x180030186  jz      short loc_1800301E2
0x180030188  lea     r14, SRWLock
0x18003018f  mov     rcx, r14; SRWLock
0x180030192  call    cs:__imp_AcquireSRWLockExclusive
0x180030199  nop     dword ptr [rax+rax+00h]
0x18003019e  mov     eax, cs:dword_18005A9E4
0x1800301a4  mov     [rsp+48h+arg_8], r14
0x1800301a9  test    ebp, ebp
0x1800301ab  jz      short loc_1800301D4
0x1800301ad  cmp     ebp, eax
0x1800301af  jnz     short loc_1800301D4
0x1800301b1  lea     rdx, [rsp+48h+Source]; Source
0x1800301b6  mov     [rsp+48h+Source], 3
0x1800301bf  lea     rcx, qword_18005AA18; this
0x1800301c6  mov     [rsp+48h+var_20], rsi
0x1800301cb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800301d0  test    al, al
0x1800301d2  jnz     short loc_1800301D8
0x1800301d4  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800301d8  lea     rcx, [rsp+48h+arg_8]
0x1800301dd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800301e2  mov     eax, [rdi]
0x1800301e4  test    al, 2
0x1800301e6  jnz     short loc_1800301F7
0x1800301e8  and     eax, 0FFFFF63Eh
0x1800301ed  and     ebx, 9C1h
0x1800301f3  or      eax, ebx
0x1800301f5  mov     [rdi], eax
0x1800301f7  mov     rbx, [rsp+48h+arg_10]
0x1800301fc  mov     rax, rdi
0x1800301ff  mov     rbp, [rsp+48h+arg_18]
0x180030204  add     rsp, 30h
0x180030208  pop     r14
0x18003020a  pop     rdi
0x18003020b  pop     rsi
0x18003020c  retn
```
