# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCachedFeatureEnabledState(void)

- ea: `0x180025218`
- end: `0x18002534b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026fc4`
- `0x180027890`
- `0x180029724`

## callees

- `0x18000f89c`
- `0x180010104`
- `0x1800121f4`
- `0x180025218`
- `0x180025d50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800252d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800252d6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID56916126__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID56916126__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID56916126__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_1800579AC
        || (Source[0] = 3,
            Source[1] = Feature_ID56916126__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800579D0, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID56916126__descriptor, 0xFFFFFFFB);
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
0x180025218  mov     [rsp+arg_10], rbx
0x18002521d  mov     [rsp+arg_18], rbp
0x180025222  mov     [rsp+arg_0], rcx
0x180025227  push    rsi
0x180025228  push    rdi
0x180025229  push    r14
0x18002522b  sub     rsp, 30h
0x18002522f  mov     rsi, cs:Feature_ID56916126__descriptor
0x180025236  mov     rdi, rdx
0x180025239  mov     qword ptr [rdx], 0
0x180025240  mov     eax, [rsi]
0x180025242  mov     [rdx], eax
0x180025244  and     eax, 6
0x180025247  cmp     al, 6
0x180025249  jz      loc_180025335
0x18002524f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180025254  lea     r8, [rsp+48h+arg_0]
0x180025259  mov     dword ptr [rsp+48h+arg_0], 0
0x180025261  lea     rdx, [rsp+48h+arg_8]
0x180025266  mov     ebp, eax
0x180025268  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCurrentFeatureEnabledState(int *)
0x18002526d  mov     eax, [rdi]
0x18002526f  mov     rbx, [rsp+48h+arg_8]
0x180025274  cmp     dword ptr [rsp+48h+arg_0], 0
0x180025279  mov     edx, eax
0x18002527b  mov     [rdi], eax
0x18002527d  mov     ecx, eax
0x18002527f  jz      short loc_18002529A
0x180025281  test    dl, 2
0x180025284  jnz     short loc_18002529A
0x180025286  and     ecx, 0FFFFF63Eh
0x18002528c  mov     eax, ebx
0x18002528e  and     eax, 9C1h
0x180025293  or      ecx, eax
0x180025295  or      ecx, 2
0x180025298  mov     [rdi], ecx
0x18002529a  mov     r8d, edx
0x18002529d  and     r8d, 4
0x1800252a1  jnz     short loc_1800252B5
0x1800252a3  btr     ecx, 0Ah
0x1800252a7  mov     eax, ebx
0x1800252a9  and     eax, 400h
0x1800252ae  or      ecx, eax
0x1800252b0  or      ecx, 4
0x1800252b3  mov     [rdi], ecx
0x1800252b5  mov     eax, edx
0x1800252b7  lock cmpxchg [rsi], ecx
0x1800252bb  jnz     short loc_180025274
0x1800252bd  test    r8d, r8d
0x1800252c0  jnz     short loc_180025320
0x1800252c2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800252c8  test    eax, eax
0x1800252ca  jz      short loc_180025320
0x1800252cc  lea     r14, SRWLock
0x1800252d3  mov     rcx, r14; SRWLock
0x1800252d6  call    cs:__imp_AcquireSRWLockExclusive
0x1800252dc  mov     eax, cs:dword_1800579AC
0x1800252e2  mov     [rsp+48h+arg_8], r14
0x1800252e7  test    ebp, ebp
0x1800252e9  jz      short loc_180025312
0x1800252eb  cmp     ebp, eax
0x1800252ed  jnz     short loc_180025312
0x1800252ef  lea     rdx, [rsp+48h+Source]; Source
0x1800252f4  mov     [rsp+48h+Source], 3
0x1800252fd  lea     rcx, qword_1800579D0; this
0x180025304  mov     [rsp+48h+var_20], rsi
0x180025309  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002530e  test    al, al
0x180025310  jnz     short loc_180025316
0x180025312  lock and dword ptr [rsi], 0FFFFFFFBh
0x180025316  lea     rcx, [rsp+48h+arg_8]
0x18002531b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025320  mov     eax, [rdi]
0x180025322  test    al, 2
0x180025324  jnz     short loc_180025335
0x180025326  and     eax, 0FFFFF63Eh
0x18002532b  and     ebx, 9C1h
0x180025331  or      eax, ebx
0x180025333  mov     [rdi], eax
0x180025335  mov     rbx, [rsp+48h+arg_10]
0x18002533a  mov     rax, rdi
0x18002533d  mov     rbp, [rsp+48h+arg_18]
0x180025342  add     rsp, 30h
0x180025346  pop     r14
0x180025348  pop     rdi
0x180025349  pop     rsi
0x18002534a  retn
```
