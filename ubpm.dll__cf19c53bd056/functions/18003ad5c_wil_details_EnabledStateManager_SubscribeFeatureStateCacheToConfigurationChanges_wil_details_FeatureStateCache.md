# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18003ad5c`
- end: `0x18003adf5`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002f83c`
- `0x180037f50`
- `0x180038038`
- `0x18003819c`
- `0x180038300`
- `0x180038464`
- `0x1800385c0`
- `0x1800386a8`
- `0x180038790`
- `0x180038878`
- `0x180038960`
- `0x1800395a0`

## callees

- `0x18002fd9c`
- `0x18003ad5c`
- `0x18003b94c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ad87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ad87`

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
0x18003ad5c  mov     [rsp+arg_8], rbx
0x18003ad61  mov     [rsp+arg_10], rbp
0x18003ad66  push    rsi
0x18003ad67  push    rdi
0x18003ad68  push    r14
0x18003ad6a  sub     rsp, 30h
0x18003ad6e  mov     eax, [rcx]
0x18003ad70  mov     ebp, r9d
0x18003ad73  mov     edi, r8d
0x18003ad76  mov     rsi, rdx
0x18003ad79  mov     r14, rcx
0x18003ad7c  test    eax, eax
0x18003ad7e  jz      short loc_18003ADE2
0x18003ad80  lea     rbx, [rcx+8]
0x18003ad84  mov     rcx, rbx; SRWLock
0x18003ad87  call    cs:__imp_AcquireSRWLockExclusive
0x18003ad8d  mov     eax, [r14+1Ch]
0x18003ad91  mov     [rsp+48h+arg_0], rbx
0x18003ad96  test    ebp, ebp
0x18003ad98  jz      short loc_18003ADC7
0x18003ad9a  cmp     ebp, eax
0x18003ad9c  jnz     short loc_18003ADC7
0x18003ad9e  lea     rcx, [r14+40h]; this
0x18003ada2  mov     [rsp+48h+var_24], 0
0x18003adaa  mov     r8d, 10h; unsigned __int64
0x18003adb0  mov     [rsp+48h+var_28], edi
0x18003adb4  lea     rdx, [rsp+48h+var_28]; void *
0x18003adb9  mov     [rsp+48h+var_20], rsi
0x18003adbe  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003adc3  test    al, al
0x18003adc5  jnz     short loc_18003ADD8
0x18003adc7  neg     edi
0x18003adc9  sbb     eax, eax
0x18003adcb  and     eax, 83Ah
0x18003add0  add     eax, 0FFFFF7C1h
0x18003add5  lock and [rsi], eax
0x18003add8  lea     rcx, [rsp+48h+arg_0]
0x18003addd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003ade2  mov     rbx, [rsp+48h+arg_8]
0x18003ade7  mov     rbp, [rsp+48h+arg_10]
0x18003adec  add     rsp, 30h
0x18003adf0  pop     r14
0x18003adf2  pop     rdi
0x18003adf3  pop     rsi
0x18003adf4  retn
```
