# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetCachedFeatureEnabledState(void)

- ea: `0x180025a68`
- end: `0x180025b9b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027384`
- `0x180027984`

## callees

- `0x18000f89c`
- `0x180010104`
- `0x1800121f4`
- `0x180025a68`
- `0x1800261e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025b26`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025b26`

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
        || v5 != dword_1800579AC
        || (Source[0] = 3,
            Source[1] = Feature_WTSActiveSessionExistsRPCBug__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800579D0, Source, v13)) )
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
0x180025a68  mov     [rsp+arg_10], rbx
0x180025a6d  mov     [rsp+arg_18], rbp
0x180025a72  mov     [rsp+arg_0], rcx
0x180025a77  push    rsi
0x180025a78  push    rdi
0x180025a79  push    r14
0x180025a7b  sub     rsp, 30h
0x180025a7f  mov     rsi, cs:Feature_WTSActiveSessionExistsRPCBug__descriptor
0x180025a86  mov     rdi, rdx
0x180025a89  mov     qword ptr [rdx], 0
0x180025a90  mov     eax, [rsi]
0x180025a92  mov     [rdx], eax
0x180025a94  and     eax, 6
0x180025a97  cmp     al, 6
0x180025a99  jz      loc_180025B85
0x180025a9f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180025aa4  lea     r8, [rsp+48h+arg_0]
0x180025aa9  mov     dword ptr [rsp+48h+arg_0], 0
0x180025ab1  lea     rdx, [rsp+48h+arg_8]
0x180025ab6  mov     ebp, eax
0x180025ab8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetCurrentFeatureEnabledState(int *)
0x180025abd  mov     eax, [rdi]
0x180025abf  mov     rbx, [rsp+48h+arg_8]
0x180025ac4  cmp     dword ptr [rsp+48h+arg_0], 0
0x180025ac9  mov     edx, eax
0x180025acb  mov     [rdi], eax
0x180025acd  mov     ecx, eax
0x180025acf  jz      short loc_180025AEA
0x180025ad1  test    dl, 2
0x180025ad4  jnz     short loc_180025AEA
0x180025ad6  and     ecx, 0FFFFF63Eh
0x180025adc  mov     eax, ebx
0x180025ade  and     eax, 9C1h
0x180025ae3  or      ecx, eax
0x180025ae5  or      ecx, 2
0x180025ae8  mov     [rdi], ecx
0x180025aea  mov     r8d, edx
0x180025aed  and     r8d, 4
0x180025af1  jnz     short loc_180025B05
0x180025af3  btr     ecx, 0Ah
0x180025af7  mov     eax, ebx
0x180025af9  and     eax, 400h
0x180025afe  or      ecx, eax
0x180025b00  or      ecx, 4
0x180025b03  mov     [rdi], ecx
0x180025b05  mov     eax, edx
0x180025b07  lock cmpxchg [rsi], ecx
0x180025b0b  jnz     short loc_180025AC4
0x180025b0d  test    r8d, r8d
0x180025b10  jnz     short loc_180025B70
0x180025b12  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180025b18  test    eax, eax
0x180025b1a  jz      short loc_180025B70
0x180025b1c  lea     r14, SRWLock
0x180025b23  mov     rcx, r14; SRWLock
0x180025b26  call    cs:__imp_AcquireSRWLockExclusive
0x180025b2c  mov     eax, cs:dword_1800579AC
0x180025b32  mov     [rsp+48h+arg_8], r14
0x180025b37  test    ebp, ebp
0x180025b39  jz      short loc_180025B62
0x180025b3b  cmp     ebp, eax
0x180025b3d  jnz     short loc_180025B62
0x180025b3f  lea     rdx, [rsp+48h+Source]; Source
0x180025b44  mov     [rsp+48h+Source], 3
0x180025b4d  lea     rcx, qword_1800579D0; this
0x180025b54  mov     [rsp+48h+var_20], rsi
0x180025b59  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180025b5e  test    al, al
0x180025b60  jnz     short loc_180025B66
0x180025b62  lock and dword ptr [rsi], 0FFFFFFFBh
0x180025b66  lea     rcx, [rsp+48h+arg_8]
0x180025b6b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025b70  mov     eax, [rdi]
0x180025b72  test    al, 2
0x180025b74  jnz     short loc_180025B85
0x180025b76  and     eax, 0FFFFF63Eh
0x180025b7b  and     ebx, 9C1h
0x180025b81  or      eax, ebx
0x180025b83  mov     [rdi], eax
0x180025b85  mov     rbx, [rsp+48h+arg_10]
0x180025b8a  mov     rax, rdi
0x180025b8d  mov     rbp, [rsp+48h+arg_18]
0x180025b92  add     rsp, 30h
0x180025b96  pop     r14
0x180025b98  pop     rdi
0x180025b99  pop     rsi
0x180025b9a  retn
```
