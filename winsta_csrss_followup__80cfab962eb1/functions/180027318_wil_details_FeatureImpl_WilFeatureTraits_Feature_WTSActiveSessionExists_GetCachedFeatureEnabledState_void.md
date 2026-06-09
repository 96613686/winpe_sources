# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExists>::GetCachedFeatureEnabledState(void)

- ea: `0x180027318`
- end: `0x180027452`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExists@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028d98`
- `0x180029410`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x180027318`
- `0x180027b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800273d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800273d6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExists>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_WTSActiveSessionExists__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WTSActiveSessionExists__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExists>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_WTSActiveSessionExists__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_WTSActiveSessionExists__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_WTSActiveSessionExists__descriptor, 0xFFFFFFFB);
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
0x180027318  mov     [rsp+arg_10], rbx
0x18002731d  mov     [rsp+arg_18], rbp
0x180027322  mov     [rsp+arg_0], rcx
0x180027327  push    rsi
0x180027328  push    rdi
0x180027329  push    r14
0x18002732b  sub     rsp, 30h
0x18002732f  mov     rsi, cs:Feature_WTSActiveSessionExists__descriptor
0x180027336  mov     rdi, rdx
0x180027339  mov     qword ptr [rdx], 0
0x180027340  mov     eax, [rsi]
0x180027342  mov     [rdx], eax
0x180027344  and     eax, 6
0x180027347  cmp     al, 6
0x180027349  jz      loc_18002743B
0x18002734f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180027354  lea     r8, [rsp+48h+arg_0]
0x180027359  mov     dword ptr [rsp+48h+arg_0], 0
0x180027361  lea     rdx, [rsp+48h+arg_8]
0x180027366  mov     ebp, eax
0x180027368  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExists@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExists>::GetCurrentFeatureEnabledState(int *)
0x18002736d  mov     eax, [rdi]
0x18002736f  mov     rbx, [rsp+48h+arg_8]
0x180027374  cmp     dword ptr [rsp+48h+arg_0], 0
0x180027379  mov     edx, eax
0x18002737b  mov     [rdi], eax
0x18002737d  mov     ecx, eax
0x18002737f  jz      short loc_18002739A
0x180027381  test    dl, 2
0x180027384  jnz     short loc_18002739A
0x180027386  and     ecx, 0FFFFF63Eh
0x18002738c  mov     eax, ebx
0x18002738e  and     eax, 9C1h
0x180027393  or      ecx, eax
0x180027395  or      ecx, 2
0x180027398  mov     [rdi], ecx
0x18002739a  mov     r8d, edx
0x18002739d  and     r8d, 4
0x1800273a1  jnz     short loc_1800273B5
0x1800273a3  btr     ecx, 0Ah
0x1800273a7  mov     eax, ebx
0x1800273a9  and     eax, 400h
0x1800273ae  or      ecx, eax
0x1800273b0  or      ecx, 4
0x1800273b3  mov     [rdi], ecx
0x1800273b5  mov     eax, edx
0x1800273b7  lock cmpxchg [rsi], ecx
0x1800273bb  jnz     short loc_180027374
0x1800273bd  test    r8d, r8d
0x1800273c0  jnz     short loc_180027426
0x1800273c2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800273c8  test    eax, eax
0x1800273ca  jz      short loc_180027426
0x1800273cc  lea     r14, SRWLock
0x1800273d3  mov     rcx, r14; SRWLock
0x1800273d6  call    cs:__imp_AcquireSRWLockExclusive
0x1800273dd  nop     dword ptr [rax+rax+00h]
0x1800273e2  mov     eax, cs:dword_18005A9E4
0x1800273e8  mov     [rsp+48h+arg_8], r14
0x1800273ed  test    ebp, ebp
0x1800273ef  jz      short loc_180027418
0x1800273f1  cmp     ebp, eax
0x1800273f3  jnz     short loc_180027418
0x1800273f5  lea     rdx, [rsp+48h+Source]; Source
0x1800273fa  mov     [rsp+48h+Source], 3
0x180027403  lea     rcx, qword_18005AA18; this
0x18002740a  mov     [rsp+48h+var_20], rsi
0x18002740f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180027414  test    al, al
0x180027416  jnz     short loc_18002741C
0x180027418  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002741c  lea     rcx, [rsp+48h+arg_8]
0x180027421  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180027426  mov     eax, [rdi]
0x180027428  test    al, 2
0x18002742a  jnz     short loc_18002743B
0x18002742c  and     eax, 0FFFFF63Eh
0x180027431  and     ebx, 9C1h
0x180027437  or      eax, ebx
0x180027439  mov     [rdi], eax
0x18002743b  mov     rbx, [rsp+48h+arg_10]
0x180027440  mov     rax, rdi
0x180027443  mov     rbp, [rsp+48h+arg_18]
0x180027448  add     rsp, 30h
0x18002744c  pop     r14
0x18002744e  pop     rdi
0x18002744f  pop     rsi
0x180027450  retn
```
