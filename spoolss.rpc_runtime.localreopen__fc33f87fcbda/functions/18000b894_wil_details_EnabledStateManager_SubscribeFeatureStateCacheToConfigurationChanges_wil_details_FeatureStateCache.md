# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000b894`
- end: `0x18000b934`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009458`

## callees

- `0x1800047ac`
- `0x18000b894`
- `0x18000c63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8bf`

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
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[10], v11, 0x10u)) )
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
0x18000b894  mov     [rsp+arg_8], rbx
0x18000b899  mov     [rsp+arg_10], rbp
0x18000b89e  push    rsi
0x18000b89f  push    rdi
0x18000b8a0  push    r14
0x18000b8a2  sub     rsp, 30h
0x18000b8a6  mov     eax, [rcx]
0x18000b8a8  mov     ebp, r9d
0x18000b8ab  mov     edi, r8d
0x18000b8ae  mov     rsi, rdx
0x18000b8b1  mov     r14, rcx
0x18000b8b4  test    eax, eax
0x18000b8b6  jz      short loc_18000B920
0x18000b8b8  lea     rbx, [rcx+8]
0x18000b8bc  mov     rcx, rbx; SRWLock
0x18000b8bf  call    cs:__imp_AcquireSRWLockExclusive
0x18000b8c6  nop     dword ptr [rax+rax+00h]
0x18000b8cb  mov     eax, [r14+1Ch]
0x18000b8cf  mov     [rsp+48h+arg_0], rbx
0x18000b8d4  test    ebp, ebp
0x18000b8d6  jz      short loc_18000B905
0x18000b8d8  cmp     ebp, eax
0x18000b8da  jnz     short loc_18000B905
0x18000b8dc  lea     rcx, [r14+50h]; this
0x18000b8e0  mov     [rsp+48h+var_24], 0
0x18000b8e8  mov     r8d, 10h; unsigned __int64
0x18000b8ee  mov     [rsp+48h+var_28], edi
0x18000b8f2  lea     rdx, [rsp+48h+var_28]; void *
0x18000b8f7  mov     [rsp+48h+var_20], rsi
0x18000b8fc  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b901  test    al, al
0x18000b903  jnz     short loc_18000B916
0x18000b905  neg     edi
0x18000b907  sbb     eax, eax
0x18000b909  and     eax, 83Ah
0x18000b90e  add     eax, 0FFFFF7C1h
0x18000b913  lock and [rsi], eax
0x18000b916  lea     rcx, [rsp+48h+arg_0]
0x18000b91b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b920  mov     rbx, [rsp+48h+arg_8]
0x18000b925  mov     rbp, [rsp+48h+arg_10]
0x18000b92a  add     rsp, 30h
0x18000b92e  pop     r14
0x18000b930  pop     rdi
0x18000b931  pop     rsi
0x18000b932  retn
```
