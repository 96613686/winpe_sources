# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetCachedFeatureEnabledState(void)

- ea: `0x180027458`
- end: `0x180027592`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028e24`
- `0x18002944c`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x180027458`
- `0x180027bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027516`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027516`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_WTSActiveSessionExistsRPCBug__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WTSActiveSessionExistsRPCBug__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetCurrentFeatureEnabledState(
      v6,
      &v17,
      &v16);
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_WTSActiveSessionExistsRPCBug__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_WTSActiveSessionExistsRPCBug__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_WTSActiveSessionExistsRPCBug__descriptor, 0xFFFFFFFB);
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
0x180027458  mov     [rsp+arg_10], rbx
0x18002745d  mov     [rsp+arg_18], rbp
0x180027462  mov     [rsp+arg_0], rcx
0x180027467  push    rsi
0x180027468  push    rdi
0x180027469  push    r14
0x18002746b  sub     rsp, 30h
0x18002746f  mov     rsi, cs:Feature_WTSActiveSessionExistsRPCBug__descriptor
0x180027476  mov     rdi, rdx
0x180027479  mov     qword ptr [rdx], 0
0x180027480  mov     eax, [rsi]
0x180027482  mov     [rdx], eax
0x180027484  and     eax, 6
0x180027487  cmp     al, 6
0x180027489  jz      loc_18002757B
0x18002748f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180027494  lea     r8, [rsp+48h+arg_0]
0x180027499  mov     dword ptr [rsp+48h+arg_0], 0
0x1800274a1  lea     rdx, [rsp+48h+arg_8]
0x1800274a6  mov     ebp, eax
0x1800274a8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetCurrentFeatureEnabledState(int *)
0x1800274ad  mov     eax, [rdi]
0x1800274af  mov     rbx, [rsp+48h+arg_8]
0x1800274b4  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800274b9  mov     edx, eax
0x1800274bb  mov     [rdi], eax
0x1800274bd  mov     ecx, eax
0x1800274bf  jz      short loc_1800274DA
0x1800274c1  test    dl, 2
0x1800274c4  jnz     short loc_1800274DA
0x1800274c6  and     ecx, 0FFFFF63Eh
0x1800274cc  mov     eax, ebx
0x1800274ce  and     eax, 9C1h
0x1800274d3  or      ecx, eax
0x1800274d5  or      ecx, 2
0x1800274d8  mov     [rdi], ecx
0x1800274da  mov     r8d, edx
0x1800274dd  and     r8d, 4
0x1800274e1  jnz     short loc_1800274F5
0x1800274e3  btr     ecx, 0Ah
0x1800274e7  mov     eax, ebx
0x1800274e9  and     eax, 400h
0x1800274ee  or      ecx, eax
0x1800274f0  or      ecx, 4
0x1800274f3  mov     [rdi], ecx
0x1800274f5  mov     eax, edx
0x1800274f7  lock cmpxchg [rsi], ecx
0x1800274fb  jnz     short loc_1800274B4
0x1800274fd  test    r8d, r8d
0x180027500  jnz     short loc_180027566
0x180027502  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180027508  test    eax, eax
0x18002750a  jz      short loc_180027566
0x18002750c  lea     r14, SRWLock
0x180027513  mov     rcx, r14; SRWLock
0x180027516  call    cs:__imp_AcquireSRWLockExclusive
0x18002751d  nop     dword ptr [rax+rax+00h]
0x180027522  mov     eax, cs:dword_18005A9E4
0x180027528  mov     [rsp+48h+arg_8], r14
0x18002752d  test    ebp, ebp
0x18002752f  jz      short loc_180027558
0x180027531  cmp     ebp, eax
0x180027533  jnz     short loc_180027558
0x180027535  lea     rdx, [rsp+48h+Source]; Source
0x18002753a  mov     [rsp+48h+Source], 3
0x180027543  lea     rcx, qword_18005AA18; this
0x18002754a  mov     [rsp+48h+var_20], rsi
0x18002754f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180027554  test    al, al
0x180027556  jnz     short loc_18002755C
0x180027558  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002755c  lea     rcx, [rsp+48h+arg_8]
0x180027561  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180027566  mov     eax, [rdi]
0x180027568  test    al, 2
0x18002756a  jnz     short loc_18002757B
0x18002756c  and     eax, 0FFFFF63Eh
0x180027571  and     ebx, 9C1h
0x180027577  or      eax, ebx
0x180027579  mov     [rdi], eax
0x18002757b  mov     rbx, [rsp+48h+arg_10]
0x180027580  mov     rax, rdi
0x180027583  mov     rbp, [rsp+48h+arg_18]
0x180027588  add     rsp, 30h
0x18002758c  pop     r14
0x18002758e  pop     rdi
0x18002758f  pop     rsi
0x180027590  retn
```
