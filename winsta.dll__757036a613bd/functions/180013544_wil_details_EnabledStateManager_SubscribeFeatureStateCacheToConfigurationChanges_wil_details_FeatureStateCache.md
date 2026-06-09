# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180013544`
- end: `0x1800135d7`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800255cc`
- `0x1800290a4`

## callees

- `0x18000f89c`
- `0x180010104`
- `0x180013544`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001356f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001356f`

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
0x180013544  mov     [rsp+arg_8], rbx
0x180013549  mov     [rsp+arg_10], rbp
0x18001354e  push    rsi
0x18001354f  push    rdi
0x180013550  push    r14
0x180013552  sub     rsp, 30h
0x180013556  mov     eax, [rcx]
0x180013558  mov     ebp, r9d
0x18001355b  mov     edi, r8d
0x18001355e  mov     rsi, rdx
0x180013561  mov     r14, rcx
0x180013564  test    eax, eax
0x180013566  jz      short loc_1800135C4
0x180013568  lea     rbx, [rcx+8]
0x18001356c  mov     rcx, rbx; SRWLock
0x18001356f  call    cs:__imp_AcquireSRWLockExclusive
0x180013575  mov     eax, [r14+1Ch]
0x180013579  mov     [rsp+48h+arg_0], rbx
0x18001357e  test    ebp, ebp
0x180013580  jz      short loc_1800135A9
0x180013582  cmp     ebp, eax
0x180013584  jnz     short loc_1800135A9
0x180013586  lea     rcx, [r14+40h]; this
0x18001358a  mov     [rsp+48h+var_24], 0
0x180013592  lea     rdx, [rsp+48h+Source]; Source
0x180013597  mov     [rsp+48h+Source], edi
0x18001359b  mov     [rsp+48h+var_20], rsi
0x1800135a0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800135a5  test    al, al
0x1800135a7  jnz     short loc_1800135BA
0x1800135a9  neg     edi
0x1800135ab  sbb     eax, eax
0x1800135ad  and     eax, 83Ah
0x1800135b2  add     eax, 0FFFFF7C1h
0x1800135b7  lock and [rsi], eax
0x1800135ba  lea     rcx, [rsp+48h+arg_0]
0x1800135bf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800135c4  mov     rbx, [rsp+48h+arg_8]
0x1800135c9  mov     rbp, [rsp+48h+arg_10]
0x1800135ce  add     rsp, 30h
0x1800135d2  pop     r14
0x1800135d4  pop     rdi
0x1800135d5  pop     rsi
0x1800135d6  retn
```
