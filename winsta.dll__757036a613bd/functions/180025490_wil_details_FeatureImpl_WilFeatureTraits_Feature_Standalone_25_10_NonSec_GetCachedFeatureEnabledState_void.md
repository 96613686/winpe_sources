# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180025490`
- end: `0x1800255c3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800270e8`

## callees

- `0x18000f89c`
- `0x180010104`
- `0x1800121f4`
- `0x180025490`
- `0x180025eec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002554e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002554e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_1800579AC
        || (Source[0] = 3,
            Source[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800579D0, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
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
0x180025490  mov     [rsp+arg_10], rbx
0x180025495  mov     [rsp+arg_18], rbp
0x18002549a  mov     [rsp+arg_0], rcx
0x18002549f  push    rsi
0x1800254a0  push    rdi
0x1800254a1  push    r14
0x1800254a3  sub     rsp, 30h
0x1800254a7  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800254ae  mov     rdi, rdx
0x1800254b1  mov     qword ptr [rdx], 0
0x1800254b8  mov     eax, [rsi]
0x1800254ba  mov     [rdx], eax
0x1800254bc  and     eax, 6
0x1800254bf  cmp     al, 6
0x1800254c1  jz      loc_1800255AD
0x1800254c7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800254cc  lea     r8, [rsp+48h+arg_0]
0x1800254d1  mov     dword ptr [rsp+48h+arg_0], 0
0x1800254d9  lea     rdx, [rsp+48h+arg_8]
0x1800254de  mov     ebp, eax
0x1800254e0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800254e5  mov     eax, [rdi]
0x1800254e7  mov     rbx, [rsp+48h+arg_8]
0x1800254ec  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800254f1  mov     edx, eax
0x1800254f3  mov     [rdi], eax
0x1800254f5  mov     ecx, eax
0x1800254f7  jz      short loc_180025512
0x1800254f9  test    dl, 2
0x1800254fc  jnz     short loc_180025512
0x1800254fe  and     ecx, 0FFFFF63Eh
0x180025504  mov     eax, ebx
0x180025506  and     eax, 9C1h
0x18002550b  or      ecx, eax
0x18002550d  or      ecx, 2
0x180025510  mov     [rdi], ecx
0x180025512  mov     r8d, edx
0x180025515  and     r8d, 4
0x180025519  jnz     short loc_18002552D
0x18002551b  btr     ecx, 0Ah
0x18002551f  mov     eax, ebx
0x180025521  and     eax, 400h
0x180025526  or      ecx, eax
0x180025528  or      ecx, 4
0x18002552b  mov     [rdi], ecx
0x18002552d  mov     eax, edx
0x18002552f  lock cmpxchg [rsi], ecx
0x180025533  jnz     short loc_1800254EC
0x180025535  test    r8d, r8d
0x180025538  jnz     short loc_180025598
0x18002553a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180025540  test    eax, eax
0x180025542  jz      short loc_180025598
0x180025544  lea     r14, SRWLock
0x18002554b  mov     rcx, r14; SRWLock
0x18002554e  call    cs:__imp_AcquireSRWLockExclusive
0x180025554  mov     eax, cs:dword_1800579AC
0x18002555a  mov     [rsp+48h+arg_8], r14
0x18002555f  test    ebp, ebp
0x180025561  jz      short loc_18002558A
0x180025563  cmp     ebp, eax
0x180025565  jnz     short loc_18002558A
0x180025567  lea     rdx, [rsp+48h+Source]; Source
0x18002556c  mov     [rsp+48h+Source], 3
0x180025575  lea     rcx, qword_1800579D0; this
0x18002557c  mov     [rsp+48h+var_20], rsi
0x180025581  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180025586  test    al, al
0x180025588  jnz     short loc_18002558E
0x18002558a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002558e  lea     rcx, [rsp+48h+arg_8]
0x180025593  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025598  mov     eax, [rdi]
0x18002559a  test    al, 2
0x18002559c  jnz     short loc_1800255AD
0x18002559e  and     eax, 0FFFFF63Eh
0x1800255a3  and     ebx, 9C1h
0x1800255a9  or      eax, ebx
0x1800255ab  mov     [rdi], eax
0x1800255ad  mov     rbx, [rsp+48h+arg_10]
0x1800255b2  mov     rax, rdi
0x1800255b5  mov     rbp, [rsp+48h+arg_18]
0x1800255ba  add     rsp, 30h
0x1800255be  pop     r14
0x1800255c0  pop     rdi
0x1800255c1  pop     rsi
0x1800255c2  retn
```
