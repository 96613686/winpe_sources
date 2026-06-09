# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180004628`
- end: `0x1800046c1`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004288`
- `0x1800043e4`

## callees

- `0x180004628`
- `0x1800067dc`
- `0x1800086b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004653`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004653`

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
  unsigned int Ptr_high; // eax
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v12; // [rsp+28h] [rbp-20h]
  unsigned int *v13; // [rsp+50h] [rbp+8h] BYREF

  result = LODWORD(a1->Ptr);
  if ( (_DWORD)result )
  {
    v9 = (unsigned int *)&a1[1];
    AcquireSRWLockExclusive(a1 + 1);
    Ptr_high = HIDWORD(a1[3].Ptr);
    v13 = v9;
    if ( !a4
      || a4 != Ptr_high
      || (Source[1] = 0,
          Source[0] = a3,
          v12 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[8], Source, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
  return result;
}

```

## disassembly

```asm
0x180004628  mov     [rsp+arg_8], rbx
0x18000462d  mov     [rsp+arg_10], rbp
0x180004632  push    rsi
0x180004633  push    rdi
0x180004634  push    r14
0x180004636  sub     rsp, 30h
0x18000463a  mov     eax, [rcx]
0x18000463c  mov     ebp, r9d
0x18000463f  mov     edi, r8d
0x180004642  mov     rsi, rdx
0x180004645  mov     r14, rcx
0x180004648  test    eax, eax
0x18000464a  jz      short loc_1800046AE
0x18000464c  lea     rbx, [rcx+8]
0x180004650  mov     rcx, rbx; SRWLock
0x180004653  call    cs:__imp_AcquireSRWLockExclusive
0x180004659  mov     eax, [r14+1Ch]
0x18000465d  mov     [rsp+48h+arg_0], rbx
0x180004662  test    ebp, ebp
0x180004664  jz      short loc_180004693
0x180004666  cmp     ebp, eax
0x180004668  jnz     short loc_180004693
0x18000466a  lea     rcx, [r14+40h]; this
0x18000466e  mov     [rsp+48h+var_24], 0
0x180004676  mov     r8d, 10h; SourceSize
0x18000467c  mov     [rsp+48h+Source], edi
0x180004680  lea     rdx, [rsp+48h+Source]; Source
0x180004685  mov     [rsp+48h+var_20], rsi
0x18000468a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000468f  test    al, al
0x180004691  jnz     short loc_1800046A4
0x180004693  neg     edi
0x180004695  sbb     eax, eax
0x180004697  and     eax, 83Ah
0x18000469c  add     eax, 0FFFFF7C1h
0x1800046a1  lock and [rsi], eax
0x1800046a4  lea     rcx, [rsp+48h+arg_0]
0x1800046a9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800046ae  mov     rbx, [rsp+48h+arg_8]
0x1800046b3  mov     rbp, [rsp+48h+arg_10]
0x1800046b8  add     rsp, 30h
0x1800046bc  pop     r14
0x1800046be  pop     rdi
0x1800046bf  pop     rsi
0x1800046c0  retn
```
