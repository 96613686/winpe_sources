# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCachedFeatureEnabledState(void)

- ea: `0x180008118`
- end: `0x180008251`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a07c`
- `0x18000bb44`

## callees

- `0x180004490`
- `0x180007af4`
- `0x180008118`
- `0x180008488`
- `0x18000bcac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081d6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_WindowsProtectedPrintSpoolerWorker__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WindowsProtectedPrintSpoolerWorker__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_WindowsProtectedPrintSpoolerWorker__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180021304
        || (v14[0] = 3,
            v14[1] = Feature_WindowsProtectedPrintSpoolerWorker__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180021328, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_WindowsProtectedPrintSpoolerWorker__descriptor, 0xFFFFFFFB);
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
0x180008118  mov     [rsp+arg_10], rbx
0x18000811d  mov     [rsp+arg_18], rbp
0x180008122  mov     [rsp+arg_0], rcx
0x180008127  push    rsi
0x180008128  push    rdi
0x180008129  push    r14
0x18000812b  sub     rsp, 30h
0x18000812f  mov     rsi, cs:Feature_WindowsProtectedPrintSpoolerWorker__descriptor
0x180008136  mov     rdi, rdx
0x180008139  mov     qword ptr [rdx], 0
0x180008140  mov     eax, [rsi]
0x180008142  mov     [rdx], eax
0x180008144  and     eax, 6
0x180008147  cmp     al, 6
0x180008149  jz      loc_18000823B
0x18000814f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008154  lea     r8, [rsp+48h+arg_0]
0x180008159  mov     dword ptr [rsp+48h+arg_0], 0
0x180008161  lea     rdx, [rsp+48h+arg_8]
0x180008166  mov     ebp, eax
0x180008168  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCurrentFeatureEnabledState(int *)
0x18000816d  mov     eax, [rdi]
0x18000816f  mov     rbx, [rsp+48h+arg_8]
0x180008174  cmp     dword ptr [rsp+48h+arg_0], 0
0x180008179  mov     edx, eax
0x18000817b  mov     [rdi], eax
0x18000817d  mov     ecx, eax
0x18000817f  jz      short loc_18000819A
0x180008181  test    dl, 2
0x180008184  jnz     short loc_18000819A
0x180008186  and     ecx, 0FFFFF63Eh
0x18000818c  mov     eax, ebx
0x18000818e  and     eax, 9C1h
0x180008193  or      ecx, eax
0x180008195  or      ecx, 2
0x180008198  mov     [rdi], ecx
0x18000819a  mov     r8d, edx
0x18000819d  and     r8d, 4
0x1800081a1  jnz     short loc_1800081B5
0x1800081a3  btr     ecx, 0Ah
0x1800081a7  mov     eax, ebx
0x1800081a9  and     eax, 400h
0x1800081ae  or      ecx, eax
0x1800081b0  or      ecx, 4
0x1800081b3  mov     [rdi], ecx
0x1800081b5  mov     eax, edx
0x1800081b7  lock cmpxchg [rsi], ecx
0x1800081bb  jnz     short loc_180008174
0x1800081bd  test    r8d, r8d
0x1800081c0  jnz     short loc_180008226
0x1800081c2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800081c8  test    eax, eax
0x1800081ca  jz      short loc_180008226
0x1800081cc  lea     r14, SRWLock
0x1800081d3  mov     rcx, r14; SRWLock
0x1800081d6  call    cs:__imp_AcquireSRWLockExclusive
0x1800081dc  mov     eax, cs:dword_180021304
0x1800081e2  mov     [rsp+48h+arg_8], r14
0x1800081e7  test    ebp, ebp
0x1800081e9  jz      short loc_180008218
0x1800081eb  cmp     ebp, eax
0x1800081ed  jnz     short loc_180008218
0x1800081ef  mov     r8d, 10h; unsigned __int64
0x1800081f5  mov     [rsp+48h+var_28], 3
0x1800081fe  lea     rdx, [rsp+48h+var_28]; void *
0x180008203  mov     [rsp+48h+var_20], rsi
0x180008208  lea     rcx, qword_180021328; this
0x18000820f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180008214  test    al, al
0x180008216  jnz     short loc_18000821C
0x180008218  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000821c  lea     rcx, [rsp+48h+arg_8]
0x180008221  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008226  mov     eax, [rdi]
0x180008228  test    al, 2
0x18000822a  jnz     short loc_18000823B
0x18000822c  and     eax, 0FFFFF63Eh
0x180008231  and     ebx, 9C1h
0x180008237  or      eax, ebx
0x180008239  mov     [rdi], eax
0x18000823b  mov     rbx, [rsp+48h+arg_10]
0x180008240  mov     rax, rdi
0x180008243  mov     rbp, [rsp+48h+arg_18]
0x180008248  add     rsp, 30h
0x18000824c  pop     r14
0x18000824e  pop     rdi
0x18000824f  pop     rsi
0x180008250  retn
```
