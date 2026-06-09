# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180011240`
- end: `0x1800112d3`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `147`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f7b8`
- `0x18000f8a0`
- `0x18000f9fc`
- `0x1800112e0`
- `0x1800128d0`

## callees

- `0x18000bf4c`
- `0x180011240`
- `0x180011fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001126b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001126b`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        RTL_SRWLOCK *a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  __int64 result; // rax
  unsigned int *v9; // rbx
  unsigned __int64 v10; // r8
  unsigned int Ptr_high; // eax
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v13; // [rsp+28h] [rbp-20h]
  unsigned int *v14; // [rsp+50h] [rbp+8h] BYREF

  result = LODWORD(a1->Ptr);
  if ( (_DWORD)result )
  {
    v9 = (unsigned int *)&a1[1];
    AcquireSRWLockExclusive(a1 + 1);
    Ptr_high = HIDWORD(a1[3].Ptr);
    v14 = v9;
    if ( !a4
      || a4 != Ptr_high
      || (Source[1] = 0,
          Source[0] = a3,
          v13 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[8], Source, v10)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  }
  return result;
}

```

## disassembly

```asm
0x180011240  mov     [rsp+arg_8], rbx
0x180011245  mov     [rsp+arg_10], rbp
0x18001124a  push    rsi
0x18001124b  push    rdi
0x18001124c  push    r14
0x18001124e  sub     rsp, 30h
0x180011252  mov     eax, [rcx]
0x180011254  mov     ebp, r9d
0x180011257  mov     edi, r8d
0x18001125a  mov     rsi, rdx
0x18001125d  mov     r14, rcx
0x180011260  test    eax, eax
0x180011262  jz      short loc_1800112C0
0x180011264  lea     rbx, [rcx+8]
0x180011268  mov     rcx, rbx; SRWLock
0x18001126b  call    cs:__imp_AcquireSRWLockExclusive
0x180011271  mov     eax, [r14+1Ch]
0x180011275  mov     [rsp+48h+arg_0], rbx
0x18001127a  test    ebp, ebp
0x18001127c  jz      short loc_1800112A5
0x18001127e  cmp     ebp, eax
0x180011280  jnz     short loc_1800112A5
0x180011282  lea     rcx, [r14+40h]; this
0x180011286  mov     [rsp+48h+var_24], 0
0x18001128e  lea     rdx, [rsp+48h+Source]; Source
0x180011293  mov     [rsp+48h+Source], edi
0x180011297  mov     [rsp+48h+var_20], rsi
0x18001129c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800112a1  test    al, al
0x1800112a3  jnz     short loc_1800112B6
0x1800112a5  neg     edi
0x1800112a7  sbb     eax, eax
0x1800112a9  and     eax, 83Ah
0x1800112ae  add     eax, 0FFFFF7C1h
0x1800112b3  lock and [rsi], eax
0x1800112b6  lea     rcx, [rsp+48h+arg_0]
0x1800112bb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800112c0  mov     rbx, [rsp+48h+arg_8]
0x1800112c5  mov     rbp, [rsp+48h+arg_10]
0x1800112ca  add     rsp, 30h
0x1800112ce  pop     r14
0x1800112d0  pop     rdi
0x1800112d1  pop     rsi
0x1800112d2  retn
```
