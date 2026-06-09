# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(void)

- ea: `0x1800166dc`
- end: `0x18001681c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018610`
- `0x180019404`

## callees

- `0x18000ddcc`
- `0x180016358`
- `0x1800166dc`
- `0x180016ab4`
- `0x1800194ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001679a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001679a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Profile_Service_ETW_Logging__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Profile_Service_ETW_Logging__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Profile_Service_ETW_Logging__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180029374
        || (v14[0] = 3,
            v14[1] = Feature_Profile_Service_ETW_Logging__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800293A8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Profile_Service_ETW_Logging__descriptor, 0xFFFFFFFB);
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
0x1800166dc  mov     [rsp+arg_10], rbx
0x1800166e1  mov     [rsp+arg_18], rbp
0x1800166e6  mov     [rsp+arg_0], rcx
0x1800166eb  push    rsi
0x1800166ec  push    rdi
0x1800166ed  push    r14
0x1800166ef  sub     rsp, 30h
0x1800166f3  mov     rsi, cs:Feature_Profile_Service_ETW_Logging__descriptor
0x1800166fa  mov     rdi, rdx
0x1800166fd  mov     qword ptr [rdx], 0
0x180016704  mov     eax, [rsi]
0x180016706  mov     [rdx], eax
0x180016708  and     eax, 6
0x18001670b  cmp     al, 6
0x18001670d  jz      loc_180016805
0x180016713  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016718  lea     r8, [rsp+48h+arg_0]
0x18001671d  mov     dword ptr [rsp+48h+arg_0], 0
0x180016725  lea     rdx, [rsp+48h+arg_8]
0x18001672a  mov     ebp, eax
0x18001672c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCurrentFeatureEnabledState(int *)
0x180016731  mov     eax, [rdi]
0x180016733  mov     rbx, [rsp+48h+arg_8]
0x180016738  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001673d  mov     edx, eax
0x18001673f  mov     [rdi], eax
0x180016741  mov     ecx, eax
0x180016743  jz      short loc_18001675E
0x180016745  test    dl, 2
0x180016748  jnz     short loc_18001675E
0x18001674a  and     ecx, 0FFFFF63Eh
0x180016750  mov     eax, ebx
0x180016752  and     eax, 9C1h
0x180016757  or      ecx, eax
0x180016759  or      ecx, 2
0x18001675c  mov     [rdi], ecx
0x18001675e  mov     r8d, edx
0x180016761  and     r8d, 4
0x180016765  jnz     short loc_180016779
0x180016767  btr     ecx, 0Ah
0x18001676b  mov     eax, ebx
0x18001676d  and     eax, 400h
0x180016772  or      ecx, eax
0x180016774  or      ecx, 4
0x180016777  mov     [rdi], ecx
0x180016779  mov     eax, edx
0x18001677b  lock cmpxchg [rsi], ecx
0x18001677f  jnz     short loc_180016738
0x180016781  test    r8d, r8d
0x180016784  jnz     short loc_1800167F0
0x180016786  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001678c  test    eax, eax
0x18001678e  jz      short loc_1800167F0
0x180016790  lea     r14, SRWLock
0x180016797  mov     rcx, r14; SRWLock
0x18001679a  call    cs:__imp_AcquireSRWLockExclusive
0x1800167a1  nop     dword ptr [rax+rax+00h]
0x1800167a6  mov     eax, cs:dword_180029374
0x1800167ac  mov     [rsp+48h+arg_8], r14
0x1800167b1  test    ebp, ebp
0x1800167b3  jz      short loc_1800167E2
0x1800167b5  cmp     ebp, eax
0x1800167b7  jnz     short loc_1800167E2
0x1800167b9  mov     r8d, 10h; unsigned __int64
0x1800167bf  mov     [rsp+48h+var_28], 3
0x1800167c8  lea     rdx, [rsp+48h+var_28]; void *
0x1800167cd  mov     [rsp+48h+var_20], rsi
0x1800167d2  lea     rcx, qword_1800293A8; this
0x1800167d9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800167de  test    al, al
0x1800167e0  jnz     short loc_1800167E6
0x1800167e2  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800167e6  lea     rcx, [rsp+48h+arg_8]
0x1800167eb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800167f0  mov     eax, [rdi]
0x1800167f2  test    al, 2
0x1800167f4  jnz     short loc_180016805
0x1800167f6  and     eax, 0FFFFF63Eh
0x1800167fb  and     ebx, 9C1h
0x180016801  or      eax, ebx
0x180016803  mov     [rdi], eax
0x180016805  mov     rbx, [rsp+48h+arg_10]
0x18001680a  mov     rax, rdi
0x18001680d  mov     rbp, [rsp+48h+arg_18]
0x180016812  add     rsp, 30h
0x180016816  pop     r14
0x180016818  pop     rdi
0x180016819  pop     rsi
0x18001681a  retn
```
