# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaitItemPinsModule>::GetCachedFeatureEnabledState(void)

- ea: `0x18003183c`
- end: `0x180031976`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WaitItemPinsModule@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031a44`
- `0x180031ad4`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x18003183c`
- `0x18003197c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800318fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800318fa`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaitItemPinsModule>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_WaitItemPinsModule__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WaitItemPinsModule__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaitItemPinsModule>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_WaitItemPinsModule__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_WaitItemPinsModule__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_WaitItemPinsModule__descriptor, 0xFFFFFFFB);
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
0x18003183c  mov     [rsp+arg_10], rbx
0x180031841  mov     [rsp+arg_18], rbp
0x180031846  mov     [rsp+arg_0], rcx
0x18003184b  push    rsi
0x18003184c  push    rdi
0x18003184d  push    r14
0x18003184f  sub     rsp, 30h
0x180031853  mov     rsi, cs:Feature_WaitItemPinsModule__descriptor
0x18003185a  mov     rdi, rdx
0x18003185d  mov     qword ptr [rdx], 0
0x180031864  mov     eax, [rsi]
0x180031866  mov     [rdx], eax
0x180031868  and     eax, 6
0x18003186b  cmp     al, 6
0x18003186d  jz      loc_18003195F
0x180031873  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180031878  lea     r8, [rsp+48h+arg_0]
0x18003187d  mov     dword ptr [rsp+48h+arg_0], 0
0x180031885  lea     rdx, [rsp+48h+arg_8]
0x18003188a  mov     ebp, eax
0x18003188c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WaitItemPinsModule@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaitItemPinsModule>::GetCurrentFeatureEnabledState(int *)
0x180031891  mov     eax, [rdi]
0x180031893  mov     rbx, [rsp+48h+arg_8]
0x180031898  cmp     dword ptr [rsp+48h+arg_0], 0
0x18003189d  mov     edx, eax
0x18003189f  mov     [rdi], eax
0x1800318a1  mov     ecx, eax
0x1800318a3  jz      short loc_1800318BE
0x1800318a5  test    dl, 2
0x1800318a8  jnz     short loc_1800318BE
0x1800318aa  and     ecx, 0FFFFF63Eh
0x1800318b0  mov     eax, ebx
0x1800318b2  and     eax, 9C1h
0x1800318b7  or      ecx, eax
0x1800318b9  or      ecx, 2
0x1800318bc  mov     [rdi], ecx
0x1800318be  mov     r8d, edx
0x1800318c1  and     r8d, 4
0x1800318c5  jnz     short loc_1800318D9
0x1800318c7  btr     ecx, 0Ah
0x1800318cb  mov     eax, ebx
0x1800318cd  and     eax, 400h
0x1800318d2  or      ecx, eax
0x1800318d4  or      ecx, 4
0x1800318d7  mov     [rdi], ecx
0x1800318d9  mov     eax, edx
0x1800318db  lock cmpxchg [rsi], ecx
0x1800318df  jnz     short loc_180031898
0x1800318e1  test    r8d, r8d
0x1800318e4  jnz     short loc_18003194A
0x1800318e6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800318ec  test    eax, eax
0x1800318ee  jz      short loc_18003194A
0x1800318f0  lea     r14, SRWLock
0x1800318f7  mov     rcx, r14; SRWLock
0x1800318fa  call    cs:__imp_AcquireSRWLockExclusive
0x180031901  nop     dword ptr [rax+rax+00h]
0x180031906  mov     eax, cs:dword_18005A9E4
0x18003190c  mov     [rsp+48h+arg_8], r14
0x180031911  test    ebp, ebp
0x180031913  jz      short loc_18003193C
0x180031915  cmp     ebp, eax
0x180031917  jnz     short loc_18003193C
0x180031919  lea     rdx, [rsp+48h+Source]; Source
0x18003191e  mov     [rsp+48h+Source], 3
0x180031927  lea     rcx, qword_18005AA18; this
0x18003192e  mov     [rsp+48h+var_20], rsi
0x180031933  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180031938  test    al, al
0x18003193a  jnz     short loc_180031940
0x18003193c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180031940  lea     rcx, [rsp+48h+arg_8]
0x180031945  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003194a  mov     eax, [rdi]
0x18003194c  test    al, 2
0x18003194e  jnz     short loc_18003195F
0x180031950  and     eax, 0FFFFF63Eh
0x180031955  and     ebx, 9C1h
0x18003195b  or      eax, ebx
0x18003195d  mov     [rdi], eax
0x18003195f  mov     rbx, [rsp+48h+arg_10]
0x180031964  mov     rax, rdi
0x180031967  mov     rbp, [rsp+48h+arg_18]
0x18003196c  add     rsp, 30h
0x180031970  pop     r14
0x180031972  pop     rdi
0x180031973  pop     rsi
0x180031974  retn
```
