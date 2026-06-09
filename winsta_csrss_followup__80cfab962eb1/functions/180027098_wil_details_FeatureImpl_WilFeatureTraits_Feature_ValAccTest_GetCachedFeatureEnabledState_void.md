# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180027098`
- end: `0x1800271d2`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028c88`
- `0x1800293d4`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x180027098`
- `0x1800279dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027156`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027156`

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
  int v12; // r8d
  unsigned __int64 v13; // r8
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v16; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v17; // [rsp+58h] [rbp+10h] BYREF

  v16 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x180027098  mov     [rsp+arg_10], rbx
0x18002709d  mov     [rsp+arg_18], rbp
0x1800270a2  mov     [rsp+arg_0], rcx
0x1800270a7  push    rsi
0x1800270a8  push    rdi
0x1800270a9  push    r14
0x1800270ab  sub     rsp, 30h
0x1800270af  mov     rsi, cs:Feature_ValAccTest__descriptor
0x1800270b6  mov     rdi, rdx
0x1800270b9  mov     qword ptr [rdx], 0
0x1800270c0  mov     eax, [rsi]
0x1800270c2  mov     [rdx], eax
0x1800270c4  and     eax, 6
0x1800270c7  cmp     al, 6
0x1800270c9  jz      loc_1800271BB
0x1800270cf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800270d4  lea     r8, [rsp+48h+arg_0]
0x1800270d9  mov     dword ptr [rsp+48h+arg_0], 0
0x1800270e1  lea     rdx, [rsp+48h+arg_8]
0x1800270e6  mov     ebp, eax
0x1800270e8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x1800270ed  mov     eax, [rdi]
0x1800270ef  mov     rbx, [rsp+48h+arg_8]
0x1800270f4  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800270f9  mov     edx, eax
0x1800270fb  mov     [rdi], eax
0x1800270fd  mov     ecx, eax
0x1800270ff  jz      short loc_18002711A
0x180027101  test    dl, 2
0x180027104  jnz     short loc_18002711A
0x180027106  and     ecx, 0FFFFF63Eh
0x18002710c  mov     eax, ebx
0x18002710e  and     eax, 9C1h
0x180027113  or      ecx, eax
0x180027115  or      ecx, 2
0x180027118  mov     [rdi], ecx
0x18002711a  mov     r8d, edx
0x18002711d  and     r8d, 4
0x180027121  jnz     short loc_180027135
0x180027123  btr     ecx, 0Ah
0x180027127  mov     eax, ebx
0x180027129  and     eax, 400h
0x18002712e  or      ecx, eax
0x180027130  or      ecx, 4
0x180027133  mov     [rdi], ecx
0x180027135  mov     eax, edx
0x180027137  lock cmpxchg [rsi], ecx
0x18002713b  jnz     short loc_1800270F4
0x18002713d  test    r8d, r8d
0x180027140  jnz     short loc_1800271A6
0x180027142  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180027148  test    eax, eax
0x18002714a  jz      short loc_1800271A6
0x18002714c  lea     r14, SRWLock
0x180027153  mov     rcx, r14; SRWLock
0x180027156  call    cs:__imp_AcquireSRWLockExclusive
0x18002715d  nop     dword ptr [rax+rax+00h]
0x180027162  mov     eax, cs:dword_18005A9E4
0x180027168  mov     [rsp+48h+arg_8], r14
0x18002716d  test    ebp, ebp
0x18002716f  jz      short loc_180027198
0x180027171  cmp     ebp, eax
0x180027173  jnz     short loc_180027198
0x180027175  lea     rdx, [rsp+48h+Source]; Source
0x18002717a  mov     [rsp+48h+Source], 3
0x180027183  lea     rcx, qword_18005AA18; this
0x18002718a  mov     [rsp+48h+var_20], rsi
0x18002718f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180027194  test    al, al
0x180027196  jnz     short loc_18002719C
0x180027198  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002719c  lea     rcx, [rsp+48h+arg_8]
0x1800271a1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800271a6  mov     eax, [rdi]
0x1800271a8  test    al, 2
0x1800271aa  jnz     short loc_1800271BB
0x1800271ac  and     eax, 0FFFFF63Eh
0x1800271b1  and     ebx, 9C1h
0x1800271b7  or      eax, ebx
0x1800271b9  mov     [rdi], eax
0x1800271bb  mov     rbx, [rsp+48h+arg_10]
0x1800271c0  mov     rax, rdi
0x1800271c3  mov     rbp, [rsp+48h+arg_18]
0x1800271c8  add     rsp, 30h
0x1800271cc  pop     r14
0x1800271ce  pop     rdi
0x1800271cf  pop     rsi
0x1800271d0  retn
```
