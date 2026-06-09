# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180016e30`
- end: `0x180016f6f`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018ed0`

## callees

- `0x18000ddcc`
- `0x180016358`
- `0x180016e30`
- `0x1800194ac`
- `0x180019b54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016edf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016edf`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // esi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  int v13; // edx
  bool v14; // si
  char v15; // al
  RTL_SRWLOCK *v16; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v17[6]; // [rsp+28h] [rbp-30h] BYREF
  int v18; // [rsp+78h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v18 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v18);
    v13 = v18;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v18 != 0) + 6);
    if ( !v13 && (v15 & 4) == 0 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v11
        || v11 != dword_180029374
        || (v17[0] = 0,
            v17[1] = v7,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800293A8, v17, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)v7, 0xFFFFF7C1);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x180016e30  mov     [rsp+arg_0], rbx
0x180016e35  mov     [rsp+arg_8], rbp
0x180016e3a  push    rsi
0x180016e3b  push    rdi
0x180016e3c  push    r14
0x180016e3e  sub     rsp, 40h
0x180016e42  test    r9d, r9d
0x180016e45  movzx   esi, r8b
0x180016e49  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180016e50  mov     ebp, edx
0x180016e52  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180016e59  mov     r14, rcx
0x180016e5c  cmovnz  rbx, rax
0x180016e60  mov     r9d, [rbx]
0x180016e63  mov     eax, r9d
0x180016e66  and     al, 3
0x180016e68  cmp     al, 2
0x180016e6a  jnz     short loc_180016E73
0x180016e6c  xor     al, al
0x180016e6e  jmp     loc_180016F5B
0x180016e73  test    r9b, 2
0x180016e77  jnz     loc_180016F3D
0x180016e7d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016e82  mov     rcx, [rsp+58h+arg_20]
0x180016e8a  lea     r9, [rsp+58h+arg_18]
0x180016e8f  mov     r8d, esi
0x180016e92  mov     [rsp+58h+arg_18], 0
0x180016e9a  mov     edx, ebp
0x180016e9c  mov     edi, eax
0x180016e9e  mov     dword ptr [rcx], 1
0x180016ea4  mov     rcx, r14
0x180016ea7  call    wil_RtlStagingConfig_QueryFeatureState
0x180016eac  mov     edx, [rsp+58h+arg_18]
0x180016eb0  test    eax, eax
0x180016eb2  mov     ecx, edx
0x180016eb4  setnz   sil
0x180016eb8  neg     ecx
0x180016eba  sbb     eax, eax
0x180016ebc  neg     eax
0x180016ebe  add     eax, 6
0x180016ec1  xchg    eax, [rbx]
0x180016ec3  test    edx, edx
0x180016ec5  jnz     short loc_180016F38
0x180016ec7  test    al, 4
0x180016ec9  jnz     short loc_180016F38
0x180016ecb  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016ed1  test    eax, eax
0x180016ed3  jz      short loc_180016F38
0x180016ed5  lea     rbp, SRWLock
0x180016edc  mov     rcx, rbp; SRWLock
0x180016edf  call    cs:__imp_AcquireSRWLockExclusive
0x180016ee6  nop     dword ptr [rax+rax+00h]
0x180016eeb  mov     eax, cs:dword_180029374
0x180016ef1  mov     [rsp+58h+var_38], rbp
0x180016ef6  test    edi, edi
0x180016ef8  jz      short loc_180016F27
0x180016efa  cmp     edi, eax
0x180016efc  jnz     short loc_180016F27
0x180016efe  mov     r8d, 10h; unsigned __int64
0x180016f04  mov     [rsp+58h+var_30], 0
0x180016f0d  lea     rdx, [rsp+58h+var_30]; void *
0x180016f12  mov     [rsp+58h+var_28], rbx
0x180016f17  lea     rcx, qword_1800293A8; this
0x180016f1e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180016f23  test    al, al
0x180016f25  jnz     short loc_180016F2E
0x180016f27  lock and dword ptr [rbx], 0FFFFF7C1h
0x180016f2e  lea     rcx, [rsp+58h+var_38]
0x180016f33  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016f38  mov     al, sil
0x180016f3b  jmp     short loc_180016F5B
0x180016f3d  mov     rax, [rsp+58h+arg_20]
0x180016f45  mov     r8d, esi
0x180016f48  xor     r9d, r9d
0x180016f4b  mov     dword ptr [rax], 1
0x180016f51  call    wil_RtlStagingConfig_QueryFeatureState
0x180016f56  test    eax, eax
0x180016f58  setnz   al
0x180016f5b  mov     rbx, [rsp+58h+arg_0]
0x180016f60  mov     rbp, [rsp+58h+arg_8]
0x180016f65  add     rsp, 40h
0x180016f69  pop     r14
0x180016f6b  pop     rdi
0x180016f6c  pop     rsi
0x180016f6d  retn
```
