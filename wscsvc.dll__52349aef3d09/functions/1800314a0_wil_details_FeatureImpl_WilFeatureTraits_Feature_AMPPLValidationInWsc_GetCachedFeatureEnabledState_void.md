# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetCachedFeatureEnabledState(void)

- ea: `0x1800314a0`
- end: `0x1800315d9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AMPPLValidationInWsc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800319ec`
- `0x1800326f0`

## callees

- `0x180022240`
- `0x180027404`
- `0x180028b1c`
- `0x1800314a0`
- `0x180031830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003155e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003155e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AMPPLValidationInWsc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AMPPLValidationInWsc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_AMPPLValidationInWsc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800544EC
        || (Source[0] = 3,
            Source[1] = Feature_AMPPLValidationInWsc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180054510, Source, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_AMPPLValidationInWsc__descriptor, 0xFFFFFFFB);
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
0x1800314a0  mov     [rsp+arg_10], rbx
0x1800314a5  mov     [rsp+arg_18], rbp
0x1800314aa  mov     [rsp+arg_0], rcx
0x1800314af  push    rsi
0x1800314b0  push    rdi
0x1800314b1  push    r14
0x1800314b3  sub     rsp, 30h
0x1800314b7  mov     rsi, cs:Feature_AMPPLValidationInWsc__descriptor
0x1800314be  mov     rdi, rdx
0x1800314c1  mov     qword ptr [rdx], 0
0x1800314c8  mov     eax, [rsi]
0x1800314ca  mov     [rdx], eax
0x1800314cc  and     eax, 6
0x1800314cf  cmp     al, 6
0x1800314d1  jz      loc_1800315C3
0x1800314d7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800314dc  lea     r8, [rsp+48h+arg_0]
0x1800314e1  mov     dword ptr [rsp+48h+arg_0], 0
0x1800314e9  lea     rdx, [rsp+48h+arg_8]
0x1800314ee  mov     ebp, eax
0x1800314f0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AMPPLValidationInWsc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetCurrentFeatureEnabledState(int *)
0x1800314f5  mov     eax, [rdi]
0x1800314f7  mov     rbx, [rsp+48h+arg_8]
0x1800314fc  cmp     dword ptr [rsp+48h+arg_0], 0
0x180031501  mov     edx, eax
0x180031503  mov     [rdi], eax
0x180031505  mov     ecx, eax
0x180031507  jz      short loc_180031522
0x180031509  test    dl, 2
0x18003150c  jnz     short loc_180031522
0x18003150e  and     ecx, 0FFFFF63Eh
0x180031514  mov     eax, ebx
0x180031516  and     eax, 9C1h
0x18003151b  or      ecx, eax
0x18003151d  or      ecx, 2
0x180031520  mov     [rdi], ecx
0x180031522  mov     r8d, edx
0x180031525  and     r8d, 4
0x180031529  jnz     short loc_18003153D
0x18003152b  btr     ecx, 0Ah
0x18003152f  mov     eax, ebx
0x180031531  and     eax, 400h
0x180031536  or      ecx, eax
0x180031538  or      ecx, 4
0x18003153b  mov     [rdi], ecx
0x18003153d  mov     eax, edx
0x18003153f  lock cmpxchg [rsi], ecx
0x180031543  jnz     short loc_1800314FC
0x180031545  test    r8d, r8d
0x180031548  jnz     short loc_1800315AE
0x18003154a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180031550  test    eax, eax
0x180031552  jz      short loc_1800315AE
0x180031554  lea     r14, SRWLock
0x18003155b  mov     rcx, r14; SRWLock
0x18003155e  call    cs:__imp_AcquireSRWLockExclusive
0x180031564  mov     eax, cs:dword_1800544EC
0x18003156a  mov     [rsp+48h+arg_8], r14
0x18003156f  test    ebp, ebp
0x180031571  jz      short loc_1800315A0
0x180031573  cmp     ebp, eax
0x180031575  jnz     short loc_1800315A0
0x180031577  mov     r8d, 10h; SourceSize
0x18003157d  mov     [rsp+48h+Source], 3
0x180031586  lea     rdx, [rsp+48h+Source]; Source
0x18003158b  mov     [rsp+48h+var_20], rsi
0x180031590  lea     rcx, qword_180054510; this
0x180031597  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003159c  test    al, al
0x18003159e  jnz     short loc_1800315A4
0x1800315a0  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800315a4  lea     rcx, [rsp+48h+arg_8]
0x1800315a9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800315ae  mov     eax, [rdi]
0x1800315b0  test    al, 2
0x1800315b2  jnz     short loc_1800315C3
0x1800315b4  and     eax, 0FFFFF63Eh
0x1800315b9  and     ebx, 9C1h
0x1800315bf  or      eax, ebx
0x1800315c1  mov     [rdi], eax
0x1800315c3  mov     rbx, [rsp+48h+arg_10]
0x1800315c8  mov     rax, rdi
0x1800315cb  mov     rbp, [rsp+48h+arg_18]
0x1800315d0  add     rsp, 30h
0x1800315d4  pop     r14
0x1800315d6  pop     rdi
0x1800315d7  pop     rsi
0x1800315d8  retn
```
