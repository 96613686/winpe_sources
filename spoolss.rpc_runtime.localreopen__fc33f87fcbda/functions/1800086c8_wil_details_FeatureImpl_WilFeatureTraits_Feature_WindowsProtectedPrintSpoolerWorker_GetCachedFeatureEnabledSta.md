# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCachedFeatureEnabledState(void)

- ea: `0x1800086c8`
- end: `0x180008808`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a8e4`
- `0x18000c4c0`

## callees

- `0x1800047ac`
- `0x180007f30`
- `0x1800086c8`
- `0x180008b58`
- `0x18000c63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008786`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008786`

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
        || v5 != dword_180022304
        || (v14[0] = 3,
            v14[1] = Feature_WindowsProtectedPrintSpoolerWorker__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180022338, v14, 0x10u)) )
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
0x1800086c8  mov     [rsp+arg_10], rbx
0x1800086cd  mov     [rsp+arg_18], rbp
0x1800086d2  mov     [rsp+arg_0], rcx
0x1800086d7  push    rsi
0x1800086d8  push    rdi
0x1800086d9  push    r14
0x1800086db  sub     rsp, 30h
0x1800086df  mov     rsi, cs:Feature_WindowsProtectedPrintSpoolerWorker__descriptor
0x1800086e6  mov     rdi, rdx
0x1800086e9  mov     qword ptr [rdx], 0
0x1800086f0  mov     eax, [rsi]
0x1800086f2  mov     [rdx], eax
0x1800086f4  and     eax, 6
0x1800086f7  cmp     al, 6
0x1800086f9  jz      loc_1800087F1
0x1800086ff  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008704  lea     r8, [rsp+48h+arg_0]
0x180008709  mov     dword ptr [rsp+48h+arg_0], 0
0x180008711  lea     rdx, [rsp+48h+arg_8]
0x180008716  mov     ebp, eax
0x180008718  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCurrentFeatureEnabledState(int *)
0x18000871d  mov     eax, [rdi]
0x18000871f  mov     rbx, [rsp+48h+arg_8]
0x180008724  cmp     dword ptr [rsp+48h+arg_0], 0
0x180008729  mov     edx, eax
0x18000872b  mov     [rdi], eax
0x18000872d  mov     ecx, eax
0x18000872f  jz      short loc_18000874A
0x180008731  test    dl, 2
0x180008734  jnz     short loc_18000874A
0x180008736  and     ecx, 0FFFFF63Eh
0x18000873c  mov     eax, ebx
0x18000873e  and     eax, 9C1h
0x180008743  or      ecx, eax
0x180008745  or      ecx, 2
0x180008748  mov     [rdi], ecx
0x18000874a  mov     r8d, edx
0x18000874d  and     r8d, 4
0x180008751  jnz     short loc_180008765
0x180008753  btr     ecx, 0Ah
0x180008757  mov     eax, ebx
0x180008759  and     eax, 400h
0x18000875e  or      ecx, eax
0x180008760  or      ecx, 4
0x180008763  mov     [rdi], ecx
0x180008765  mov     eax, edx
0x180008767  lock cmpxchg [rsi], ecx
0x18000876b  jnz     short loc_180008724
0x18000876d  test    r8d, r8d
0x180008770  jnz     short loc_1800087DC
0x180008772  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008778  test    eax, eax
0x18000877a  jz      short loc_1800087DC
0x18000877c  lea     r14, SRWLock
0x180008783  mov     rcx, r14; SRWLock
0x180008786  call    cs:__imp_AcquireSRWLockExclusive
0x18000878d  nop     dword ptr [rax+rax+00h]
0x180008792  mov     eax, cs:dword_180022304
0x180008798  mov     [rsp+48h+arg_8], r14
0x18000879d  test    ebp, ebp
0x18000879f  jz      short loc_1800087CE
0x1800087a1  cmp     ebp, eax
0x1800087a3  jnz     short loc_1800087CE
0x1800087a5  mov     r8d, 10h; unsigned __int64
0x1800087ab  mov     [rsp+48h+var_28], 3
0x1800087b4  lea     rdx, [rsp+48h+var_28]; void *
0x1800087b9  mov     [rsp+48h+var_20], rsi
0x1800087be  lea     rcx, qword_180022338; this
0x1800087c5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800087ca  test    al, al
0x1800087cc  jnz     short loc_1800087D2
0x1800087ce  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800087d2  lea     rcx, [rsp+48h+arg_8]
0x1800087d7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800087dc  mov     eax, [rdi]
0x1800087de  test    al, 2
0x1800087e0  jnz     short loc_1800087F1
0x1800087e2  and     eax, 0FFFFF63Eh
0x1800087e7  and     ebx, 9C1h
0x1800087ed  or      eax, ebx
0x1800087ef  mov     [rdi], eax
0x1800087f1  mov     rbx, [rsp+48h+arg_10]
0x1800087f6  mov     rax, rdi
0x1800087f9  mov     rbp, [rsp+48h+arg_18]
0x1800087fe  add     rsp, 30h
0x180008802  pop     r14
0x180008804  pop     rdi
0x180008805  pop     rsi
0x180008806  retn
```
