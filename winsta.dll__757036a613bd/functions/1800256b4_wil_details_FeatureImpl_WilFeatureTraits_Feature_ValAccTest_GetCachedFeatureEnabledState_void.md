# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800256b4`
- end: `0x1800257e7`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800271f0`
- `0x18002790c`

## callees

- `0x18000f89c`
- `0x180010104`
- `0x1800121f4`
- `0x1800256b4`
- `0x180025fd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025772`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025772`

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
        || v5 != dword_1800579AC
        || (Source[0] = 3,
            Source[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800579D0, Source, v13)) )
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
0x1800256b4  mov     [rsp+arg_10], rbx
0x1800256b9  mov     [rsp+arg_18], rbp
0x1800256be  mov     [rsp+arg_0], rcx
0x1800256c3  push    rsi
0x1800256c4  push    rdi
0x1800256c5  push    r14
0x1800256c7  sub     rsp, 30h
0x1800256cb  mov     rsi, cs:Feature_ValAccTest__descriptor
0x1800256d2  mov     rdi, rdx
0x1800256d5  mov     qword ptr [rdx], 0
0x1800256dc  mov     eax, [rsi]
0x1800256de  mov     [rdx], eax
0x1800256e0  and     eax, 6
0x1800256e3  cmp     al, 6
0x1800256e5  jz      loc_1800257D1
0x1800256eb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800256f0  lea     r8, [rsp+48h+arg_0]
0x1800256f5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800256fd  lea     rdx, [rsp+48h+arg_8]
0x180025702  mov     ebp, eax
0x180025704  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180025709  mov     eax, [rdi]
0x18002570b  mov     rbx, [rsp+48h+arg_8]
0x180025710  cmp     dword ptr [rsp+48h+arg_0], 0
0x180025715  mov     edx, eax
0x180025717  mov     [rdi], eax
0x180025719  mov     ecx, eax
0x18002571b  jz      short loc_180025736
0x18002571d  test    dl, 2
0x180025720  jnz     short loc_180025736
0x180025722  and     ecx, 0FFFFF63Eh
0x180025728  mov     eax, ebx
0x18002572a  and     eax, 9C1h
0x18002572f  or      ecx, eax
0x180025731  or      ecx, 2
0x180025734  mov     [rdi], ecx
0x180025736  mov     r8d, edx
0x180025739  and     r8d, 4
0x18002573d  jnz     short loc_180025751
0x18002573f  btr     ecx, 0Ah
0x180025743  mov     eax, ebx
0x180025745  and     eax, 400h
0x18002574a  or      ecx, eax
0x18002574c  or      ecx, 4
0x18002574f  mov     [rdi], ecx
0x180025751  mov     eax, edx
0x180025753  lock cmpxchg [rsi], ecx
0x180025757  jnz     short loc_180025710
0x180025759  test    r8d, r8d
0x18002575c  jnz     short loc_1800257BC
0x18002575e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180025764  test    eax, eax
0x180025766  jz      short loc_1800257BC
0x180025768  lea     r14, SRWLock
0x18002576f  mov     rcx, r14; SRWLock
0x180025772  call    cs:__imp_AcquireSRWLockExclusive
0x180025778  mov     eax, cs:dword_1800579AC
0x18002577e  mov     [rsp+48h+arg_8], r14
0x180025783  test    ebp, ebp
0x180025785  jz      short loc_1800257AE
0x180025787  cmp     ebp, eax
0x180025789  jnz     short loc_1800257AE
0x18002578b  lea     rdx, [rsp+48h+Source]; Source
0x180025790  mov     [rsp+48h+Source], 3
0x180025799  lea     rcx, qword_1800579D0; this
0x1800257a0  mov     [rsp+48h+var_20], rsi
0x1800257a5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800257aa  test    al, al
0x1800257ac  jnz     short loc_1800257B2
0x1800257ae  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800257b2  lea     rcx, [rsp+48h+arg_8]
0x1800257b7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800257bc  mov     eax, [rdi]
0x1800257be  test    al, 2
0x1800257c0  jnz     short loc_1800257D1
0x1800257c2  and     eax, 0FFFFF63Eh
0x1800257c7  and     ebx, 9C1h
0x1800257cd  or      eax, ebx
0x1800257cf  mov     [rdi], eax
0x1800257d1  mov     rbx, [rsp+48h+arg_10]
0x1800257d6  mov     rax, rdi
0x1800257d9  mov     rbp, [rsp+48h+arg_18]
0x1800257de  add     rsp, 30h
0x1800257e2  pop     r14
0x1800257e4  pop     rdi
0x1800257e5  pop     rsi
0x1800257e6  retn
```
