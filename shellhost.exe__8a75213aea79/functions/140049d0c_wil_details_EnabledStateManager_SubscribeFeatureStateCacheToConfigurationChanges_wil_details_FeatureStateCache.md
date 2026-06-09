# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140049d0c`
- end: `0x140049da5`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `15`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140047ac0`
- `0x140055514`
- `0x1400556bc`
- `0x1400557a4`
- `0x14005588c`
- `0x1400559f4`
- `0x140055adc`
- `0x140055bc4`
- `0x140055cac`
- `0x140055d94`
- `0x140055e7c`
- `0x140055f64`
- `0x14005604c`
- `0x1400561ac`
- `0x140056294`

## callees

- `0x14000a814`
- `0x140049d0c`
- `0x14004aec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140049d37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140049d37`

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
0x140049d0c  mov     [rsp+arg_8], rbx
0x140049d11  mov     [rsp+arg_10], rbp
0x140049d16  push    rsi
0x140049d17  push    rdi
0x140049d18  push    r14
0x140049d1a  sub     rsp, 30h
0x140049d1e  mov     eax, [rcx]
0x140049d20  mov     ebp, r9d
0x140049d23  mov     edi, r8d
0x140049d26  mov     rsi, rdx
0x140049d29  mov     r14, rcx
0x140049d2c  test    eax, eax
0x140049d2e  jz      short loc_140049D92
0x140049d30  lea     rbx, [rcx+8]
0x140049d34  mov     rcx, rbx; SRWLock
0x140049d37  call    cs:__imp_AcquireSRWLockExclusive
0x140049d3d  mov     eax, [r14+1Ch]
0x140049d41  mov     [rsp+48h+arg_0], rbx
0x140049d46  test    ebp, ebp
0x140049d48  jz      short loc_140049D77
0x140049d4a  cmp     ebp, eax
0x140049d4c  jnz     short loc_140049D77
0x140049d4e  lea     rcx, [r14+40h]; this
0x140049d52  mov     [rsp+48h+var_24], 0
0x140049d5a  mov     r8d, 10h; unsigned __int64
0x140049d60  mov     [rsp+48h+var_28], edi
0x140049d64  lea     rdx, [rsp+48h+var_28]; void *
0x140049d69  mov     [rsp+48h+var_20], rsi
0x140049d6e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140049d73  test    al, al
0x140049d75  jnz     short loc_140049D88
0x140049d77  neg     edi
0x140049d79  sbb     eax, eax
0x140049d7b  and     eax, 83Ah
0x140049d80  add     eax, 0FFFFF7C1h
0x140049d85  lock and [rsi], eax
0x140049d88  lea     rcx, [rsp+48h+arg_0]
0x140049d8d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140049d92  mov     rbx, [rsp+48h+arg_8]
0x140049d97  mov     rbp, [rsp+48h+arg_10]
0x140049d9c  add     rsp, 30h
0x140049da0  pop     r14
0x140049da2  pop     rdi
0x140049da3  pop     rsi
0x140049da4  retn
```
