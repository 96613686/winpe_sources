# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180053180`
- end: `0x1800532b9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055ac4`
- `0x180056474`

## callees

- `0x18002d704`
- `0x18002dbe4`
- `0x180039f1c`
- `0x180053180`
- `0x18005372c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18005323e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18005323e`

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
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18009086C
        || (Source[0] = 3,
            Source[1] = Feature_TestAccPerf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180090890, Source, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
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
0x180053180  mov     [rsp+arg_10], rbx
0x180053185  mov     [rsp+arg_18], rbp
0x18005318a  mov     [rsp+arg_0], rcx
0x18005318f  push    rsi
0x180053190  push    rdi
0x180053191  push    r14
0x180053193  sub     rsp, 30h
0x180053197  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18005319e  mov     rdi, rdx
0x1800531a1  mov     qword ptr [rdx], 0
0x1800531a8  mov     eax, [rsi]
0x1800531aa  mov     [rdx], eax
0x1800531ac  and     eax, 6
0x1800531af  cmp     al, 6
0x1800531b1  jz      loc_1800532A3
0x1800531b7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800531bc  lea     r8, [rsp+48h+arg_0]
0x1800531c1  mov     dword ptr [rsp+48h+arg_0], 0
0x1800531c9  lea     rdx, [rsp+48h+arg_8]
0x1800531ce  mov     ebp, eax
0x1800531d0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x1800531d5  mov     eax, [rdi]
0x1800531d7  mov     rbx, [rsp+48h+arg_8]
0x1800531dc  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800531e1  mov     edx, eax
0x1800531e3  mov     [rdi], eax
0x1800531e5  mov     ecx, eax
0x1800531e7  jz      short loc_180053202
0x1800531e9  test    dl, 2
0x1800531ec  jnz     short loc_180053202
0x1800531ee  and     ecx, 0FFFFF63Eh
0x1800531f4  mov     eax, ebx
0x1800531f6  and     eax, 9C1h
0x1800531fb  or      ecx, eax
0x1800531fd  or      ecx, 2
0x180053200  mov     [rdi], ecx
0x180053202  mov     r8d, edx
0x180053205  and     r8d, 4
0x180053209  jnz     short loc_18005321D
0x18005320b  btr     ecx, 0Ah
0x18005320f  mov     eax, ebx
0x180053211  and     eax, 400h
0x180053216  or      ecx, eax
0x180053218  or      ecx, 4
0x18005321b  mov     [rdi], ecx
0x18005321d  mov     eax, edx
0x18005321f  lock cmpxchg [rsi], ecx
0x180053223  jnz     short loc_1800531DC
0x180053225  test    r8d, r8d
0x180053228  jnz     short loc_18005328E
0x18005322a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180053230  test    eax, eax
0x180053232  jz      short loc_18005328E
0x180053234  lea     r14, SRWLock
0x18005323b  mov     rcx, r14; SRWLock
0x18005323e  call    cs:__imp_AcquireSRWLockExclusive
0x180053244  mov     eax, cs:dword_18009086C
0x18005324a  mov     [rsp+48h+arg_8], r14
0x18005324f  test    ebp, ebp
0x180053251  jz      short loc_180053280
0x180053253  cmp     ebp, eax
0x180053255  jnz     short loc_180053280
0x180053257  mov     r8d, 10h; SourceSize
0x18005325d  mov     [rsp+48h+Source], 3
0x180053266  lea     rdx, [rsp+48h+Source]; Source
0x18005326b  mov     [rsp+48h+var_20], rsi
0x180053270  lea     rcx, qword_180090890; this
0x180053277  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18005327c  test    al, al
0x18005327e  jnz     short loc_180053284
0x180053280  lock and dword ptr [rsi], 0FFFFFFFBh
0x180053284  lea     rcx, [rsp+48h+arg_8]
0x180053289  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005328e  mov     eax, [rdi]
0x180053290  test    al, 2
0x180053292  jnz     short loc_1800532A3
0x180053294  and     eax, 0FFFFF63Eh
0x180053299  and     ebx, 9C1h
0x18005329f  or      eax, ebx
0x1800532a1  mov     [rdi], eax
0x1800532a3  mov     rbx, [rsp+48h+arg_10]
0x1800532a8  mov     rax, rdi
0x1800532ab  mov     rbp, [rsp+48h+arg_18]
0x1800532b0  add     rsp, 30h
0x1800532b4  pop     r14
0x1800532b6  pop     rdi
0x1800532b7  pop     rsi
0x1800532b8  retn
```
