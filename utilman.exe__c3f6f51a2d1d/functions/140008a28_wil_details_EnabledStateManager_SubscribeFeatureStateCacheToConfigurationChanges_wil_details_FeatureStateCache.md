# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140008a28`
- end: `0x140008ac8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140006444`
- `0x140019910`
- `0x14001fe9c`

## callees

- `0x14000483c`
- `0x140008a28`
- `0x140009b7c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140008a53`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140008a53`

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
0x140008a28  mov     [rsp+arg_8], rbx
0x140008a2d  mov     [rsp+arg_10], rbp
0x140008a32  push    rsi
0x140008a33  push    rdi
0x140008a34  push    r14
0x140008a36  sub     rsp, 30h
0x140008a3a  mov     eax, [rcx]
0x140008a3c  mov     ebp, r9d
0x140008a3f  mov     edi, r8d
0x140008a42  mov     rsi, rdx
0x140008a45  mov     r14, rcx
0x140008a48  test    eax, eax
0x140008a4a  jz      short loc_140008AB4
0x140008a4c  lea     rbx, [rcx+8]
0x140008a50  mov     rcx, rbx; SRWLock
0x140008a53  call    cs:__imp_AcquireSRWLockExclusive
0x140008a5a  nop     dword ptr [rax+rax+00h]
0x140008a5f  mov     eax, [r14+1Ch]
0x140008a63  mov     [rsp+48h+arg_0], rbx
0x140008a68  test    ebp, ebp
0x140008a6a  jz      short loc_140008A99
0x140008a6c  cmp     ebp, eax
0x140008a6e  jnz     short loc_140008A99
0x140008a70  lea     rcx, [r14+50h]; this
0x140008a74  mov     [rsp+48h+var_24], 0
0x140008a7c  mov     r8d, 10h; unsigned __int64
0x140008a82  mov     [rsp+48h+var_28], edi
0x140008a86  lea     rdx, [rsp+48h+var_28]; void *
0x140008a8b  mov     [rsp+48h+var_20], rsi
0x140008a90  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140008a95  test    al, al
0x140008a97  jnz     short loc_140008AAA
0x140008a99  neg     edi
0x140008a9b  sbb     eax, eax
0x140008a9d  and     eax, 83Ah
0x140008aa2  add     eax, 0FFFFF7C1h
0x140008aa7  lock and [rsi], eax
0x140008aaa  lea     rcx, [rsp+48h+arg_0]
0x140008aaf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140008ab4  mov     rbx, [rsp+48h+arg_8]
0x140008ab9  mov     rbp, [rsp+48h+arg_10]
0x140008abe  add     rsp, 30h
0x140008ac2  pop     r14
0x140008ac4  pop     rdi
0x140008ac5  pop     rsi
0x140008ac6  retn
```
