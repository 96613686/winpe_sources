# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000af90`
- end: `0x18000b029`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008d48`

## callees

- `0x180004490`
- `0x18000af90`
- `0x18000bcac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000afbb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000afbb`

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
  _DWORD v11[2]; // [rsp+20h] [rbp-28h] BYREF
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
      || (v11[1] = 0,
          v11[0] = a3,
          v12 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[8], v11, 0x10u)) )
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
0x18000af90  mov     [rsp+arg_8], rbx
0x18000af95  mov     [rsp+arg_10], rbp
0x18000af9a  push    rsi
0x18000af9b  push    rdi
0x18000af9c  push    r14
0x18000af9e  sub     rsp, 30h
0x18000afa2  mov     eax, [rcx]
0x18000afa4  mov     ebp, r9d
0x18000afa7  mov     edi, r8d
0x18000afaa  mov     rsi, rdx
0x18000afad  mov     r14, rcx
0x18000afb0  test    eax, eax
0x18000afb2  jz      short loc_18000B016
0x18000afb4  lea     rbx, [rcx+8]
0x18000afb8  mov     rcx, rbx; SRWLock
0x18000afbb  call    cs:__imp_AcquireSRWLockExclusive
0x18000afc1  mov     eax, [r14+1Ch]
0x18000afc5  mov     [rsp+48h+arg_0], rbx
0x18000afca  test    ebp, ebp
0x18000afcc  jz      short loc_18000AFFB
0x18000afce  cmp     ebp, eax
0x18000afd0  jnz     short loc_18000AFFB
0x18000afd2  lea     rcx, [r14+40h]; this
0x18000afd6  mov     [rsp+48h+var_24], 0
0x18000afde  mov     r8d, 10h; unsigned __int64
0x18000afe4  mov     [rsp+48h+var_28], edi
0x18000afe8  lea     rdx, [rsp+48h+var_28]; void *
0x18000afed  mov     [rsp+48h+var_20], rsi
0x18000aff2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000aff7  test    al, al
0x18000aff9  jnz     short loc_18000B00C
0x18000affb  neg     edi
0x18000affd  sbb     eax, eax
0x18000afff  and     eax, 83Ah
0x18000b004  add     eax, 0FFFFF7C1h
0x18000b009  lock and [rsi], eax
0x18000b00c  lea     rcx, [rsp+48h+arg_0]
0x18000b011  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b016  mov     rbx, [rsp+48h+arg_8]
0x18000b01b  mov     rbp, [rsp+48h+arg_10]
0x18000b020  add     rsp, 30h
0x18000b024  pop     r14
0x18000b026  pop     rdi
0x18000b027  pop     rsi
0x18000b028  retn
```
