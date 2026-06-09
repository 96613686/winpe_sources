# wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCachedFeatureEnabledState(void)

- ea: `0x1800250dc`
- end: `0x18002520f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60011020@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026f40`

## callees

- `0x18000f89c`
- `0x180010104`
- `0x1800121f4`
- `0x1800250dc`
- `0x180025cdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002519a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002519a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_60011020__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_60011020__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_60011020__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_1800579AC
        || (Source[0] = 3,
            Source[1] = Feature_60011020__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800579D0, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_60011020__descriptor, 0xFFFFFFFB);
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
0x1800250dc  mov     [rsp+arg_10], rbx
0x1800250e1  mov     [rsp+arg_18], rbp
0x1800250e6  mov     [rsp+arg_0], rcx
0x1800250eb  push    rsi
0x1800250ec  push    rdi
0x1800250ed  push    r14
0x1800250ef  sub     rsp, 30h
0x1800250f3  mov     rsi, cs:Feature_60011020__descriptor
0x1800250fa  mov     rdi, rdx
0x1800250fd  mov     qword ptr [rdx], 0
0x180025104  mov     eax, [rsi]
0x180025106  mov     [rdx], eax
0x180025108  and     eax, 6
0x18002510b  cmp     al, 6
0x18002510d  jz      loc_1800251F9
0x180025113  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180025118  lea     r8, [rsp+48h+arg_0]
0x18002511d  mov     dword ptr [rsp+48h+arg_0], 0
0x180025125  lea     rdx, [rsp+48h+arg_8]
0x18002512a  mov     ebp, eax
0x18002512c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60011020@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCurrentFeatureEnabledState(int *)
0x180025131  mov     eax, [rdi]
0x180025133  mov     rbx, [rsp+48h+arg_8]
0x180025138  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002513d  mov     edx, eax
0x18002513f  mov     [rdi], eax
0x180025141  mov     ecx, eax
0x180025143  jz      short loc_18002515E
0x180025145  test    dl, 2
0x180025148  jnz     short loc_18002515E
0x18002514a  and     ecx, 0FFFFF63Eh
0x180025150  mov     eax, ebx
0x180025152  and     eax, 9C1h
0x180025157  or      ecx, eax
0x180025159  or      ecx, 2
0x18002515c  mov     [rdi], ecx
0x18002515e  mov     r8d, edx
0x180025161  and     r8d, 4
0x180025165  jnz     short loc_180025179
0x180025167  btr     ecx, 0Ah
0x18002516b  mov     eax, ebx
0x18002516d  and     eax, 400h
0x180025172  or      ecx, eax
0x180025174  or      ecx, 4
0x180025177  mov     [rdi], ecx
0x180025179  mov     eax, edx
0x18002517b  lock cmpxchg [rsi], ecx
0x18002517f  jnz     short loc_180025138
0x180025181  test    r8d, r8d
0x180025184  jnz     short loc_1800251E4
0x180025186  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002518c  test    eax, eax
0x18002518e  jz      short loc_1800251E4
0x180025190  lea     r14, SRWLock
0x180025197  mov     rcx, r14; SRWLock
0x18002519a  call    cs:__imp_AcquireSRWLockExclusive
0x1800251a0  mov     eax, cs:dword_1800579AC
0x1800251a6  mov     [rsp+48h+arg_8], r14
0x1800251ab  test    ebp, ebp
0x1800251ad  jz      short loc_1800251D6
0x1800251af  cmp     ebp, eax
0x1800251b1  jnz     short loc_1800251D6
0x1800251b3  lea     rdx, [rsp+48h+Source]; Source
0x1800251b8  mov     [rsp+48h+Source], 3
0x1800251c1  lea     rcx, qword_1800579D0; this
0x1800251c8  mov     [rsp+48h+var_20], rsi
0x1800251cd  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800251d2  test    al, al
0x1800251d4  jnz     short loc_1800251DA
0x1800251d6  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800251da  lea     rcx, [rsp+48h+arg_8]
0x1800251df  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800251e4  mov     eax, [rdi]
0x1800251e6  test    al, 2
0x1800251e8  jnz     short loc_1800251F9
0x1800251ea  and     eax, 0FFFFF63Eh
0x1800251ef  and     ebx, 9C1h
0x1800251f5  or      eax, ebx
0x1800251f7  mov     [rdi], eax
0x1800251f9  mov     rbx, [rsp+48h+arg_10]
0x1800251fe  mov     rax, rdi
0x180025201  mov     rbp, [rsp+48h+arg_18]
0x180025206  add     rsp, 30h
0x18002520a  pop     r14
0x18002520c  pop     rdi
0x18002520d  pop     rsi
0x18002520e  retn
```
