# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCachedFeatureEnabledState(void)

- ea: `0x180025354`
- end: `0x180025487`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59399909@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002705c`
- `0x1800278d0`

## callees

- `0x18000f89c`
- `0x180010104`
- `0x1800121f4`
- `0x180025354`
- `0x180025e24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025412`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025412`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID59399909__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID59399909__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID59399909__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_1800579AC
        || (Source[0] = 3,
            Source[1] = Feature_ID59399909__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800579D0, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID59399909__descriptor, 0xFFFFFFFB);
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
0x180025354  mov     [rsp+arg_10], rbx
0x180025359  mov     [rsp+arg_18], rbp
0x18002535e  mov     [rsp+arg_0], rcx
0x180025363  push    rsi
0x180025364  push    rdi
0x180025365  push    r14
0x180025367  sub     rsp, 30h
0x18002536b  mov     rsi, cs:Feature_ID59399909__descriptor
0x180025372  mov     rdi, rdx
0x180025375  mov     qword ptr [rdx], 0
0x18002537c  mov     eax, [rsi]
0x18002537e  mov     [rdx], eax
0x180025380  and     eax, 6
0x180025383  cmp     al, 6
0x180025385  jz      loc_180025471
0x18002538b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180025390  lea     r8, [rsp+48h+arg_0]
0x180025395  mov     dword ptr [rsp+48h+arg_0], 0
0x18002539d  lea     rdx, [rsp+48h+arg_8]
0x1800253a2  mov     ebp, eax
0x1800253a4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59399909@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCurrentFeatureEnabledState(int *)
0x1800253a9  mov     eax, [rdi]
0x1800253ab  mov     rbx, [rsp+48h+arg_8]
0x1800253b0  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800253b5  mov     edx, eax
0x1800253b7  mov     [rdi], eax
0x1800253b9  mov     ecx, eax
0x1800253bb  jz      short loc_1800253D6
0x1800253bd  test    dl, 2
0x1800253c0  jnz     short loc_1800253D6
0x1800253c2  and     ecx, 0FFFFF63Eh
0x1800253c8  mov     eax, ebx
0x1800253ca  and     eax, 9C1h
0x1800253cf  or      ecx, eax
0x1800253d1  or      ecx, 2
0x1800253d4  mov     [rdi], ecx
0x1800253d6  mov     r8d, edx
0x1800253d9  and     r8d, 4
0x1800253dd  jnz     short loc_1800253F1
0x1800253df  btr     ecx, 0Ah
0x1800253e3  mov     eax, ebx
0x1800253e5  and     eax, 400h
0x1800253ea  or      ecx, eax
0x1800253ec  or      ecx, 4
0x1800253ef  mov     [rdi], ecx
0x1800253f1  mov     eax, edx
0x1800253f3  lock cmpxchg [rsi], ecx
0x1800253f7  jnz     short loc_1800253B0
0x1800253f9  test    r8d, r8d
0x1800253fc  jnz     short loc_18002545C
0x1800253fe  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180025404  test    eax, eax
0x180025406  jz      short loc_18002545C
0x180025408  lea     r14, SRWLock
0x18002540f  mov     rcx, r14; SRWLock
0x180025412  call    cs:__imp_AcquireSRWLockExclusive
0x180025418  mov     eax, cs:dword_1800579AC
0x18002541e  mov     [rsp+48h+arg_8], r14
0x180025423  test    ebp, ebp
0x180025425  jz      short loc_18002544E
0x180025427  cmp     ebp, eax
0x180025429  jnz     short loc_18002544E
0x18002542b  lea     rdx, [rsp+48h+Source]; Source
0x180025430  mov     [rsp+48h+Source], 3
0x180025439  lea     rcx, qword_1800579D0; this
0x180025440  mov     [rsp+48h+var_20], rsi
0x180025445  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002544a  test    al, al
0x18002544c  jnz     short loc_180025452
0x18002544e  lock and dword ptr [rsi], 0FFFFFFFBh
0x180025452  lea     rcx, [rsp+48h+arg_8]
0x180025457  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002545c  mov     eax, [rdi]
0x18002545e  test    al, 2
0x180025460  jnz     short loc_180025471
0x180025462  and     eax, 0FFFFF63Eh
0x180025467  and     ebx, 9C1h
0x18002546d  or      eax, ebx
0x18002546f  mov     [rdi], eax
0x180025471  mov     rbx, [rsp+48h+arg_10]
0x180025476  mov     rax, rdi
0x180025479  mov     rbp, [rsp+48h+arg_18]
0x18002547e  add     rsp, 30h
0x180025482  pop     r14
0x180025484  pop     rdi
0x180025485  pop     rsi
0x180025486  retn
```
