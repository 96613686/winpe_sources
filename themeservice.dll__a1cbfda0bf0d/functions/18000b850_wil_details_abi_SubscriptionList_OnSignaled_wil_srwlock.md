# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000b850`
- end: `0x18000b90f`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `191`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000a4e0`
- `0x18000a510`
- `0x18000b364`

## callees

- `0x180007050`
- `0x18000a7d8`
- `0x18000a7f8`
- `0x18000b850`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b869`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b869`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b899`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b899`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // rsi
  __int64 v7; // r15
  char *v8; // rdx
  RTL_SRWLOCK *v9; // [rsp+50h] [rbp+8h] BYREF
  LPCRITICAL_SECTION v10; // [rsp+58h] [rbp+10h] BYREF

  AcquireSRWLockShared(SRWLock);
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  v9 = SRWLock;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    v10 = lpCriticalSection;
    AcquireSRWLockExclusive(SRWLock);
    v9 = SRWLock;
    while ( v5 < v4 )
    {
      v8 = (char *)lpCriticalSection[1].DebugInfo + 16 * v5++;
      if ( *(_QWORD *)v8 )
      {
        v6 = *(void (__fastcall **)(__int64))v8;
        v7 = *((_QWORD *)v8 + 1);
        break;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    if ( v6 )
      v6(v7);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18000b850  mov     [rsp+arg_10], rbx
0x18000b855  push    rbp
0x18000b856  push    rsi
0x18000b857  push    rdi
0x18000b858  push    r14
0x18000b85a  push    r15
0x18000b85c  sub     rsp, 20h
0x18000b860  mov     rbp, rcx
0x18000b863  mov     r14, rdx
0x18000b866  mov     rcx, rdx; SRWLock
0x18000b869  call    cs:__imp_AcquireSRWLockShared
0x18000b86f  mov     rdi, [rbp+30h]
0x18000b873  lea     rcx, [rsp+48h+arg_0]
0x18000b878  sub     rdi, [rbp+28h]
0x18000b87c  shr     rdi, 4
0x18000b880  mov     [rsp+48h+arg_0], r14
0x18000b885  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b88a  xor     ebx, ebx
0x18000b88c  test    rdi, rdi
0x18000b88f  jz      short loc_18000B8FE
0x18000b891  mov     rcx, rbp; lpCriticalSection
0x18000b894  xor     esi, esi
0x18000b896  xor     r15d, r15d
0x18000b899  call    cs:__imp_EnterCriticalSection
0x18000b89f  mov     rcx, r14; SRWLock
0x18000b8a2  mov     [rsp+48h+arg_8], rbp
0x18000b8a7  call    cs:__imp_AcquireSRWLockExclusive
0x18000b8ad  mov     [rsp+48h+arg_0], r14
0x18000b8b2  cmp     rbx, rdi
0x18000b8b5  jnb     short loc_18000B8D5
0x18000b8b7  mov     rdx, [rbp+28h]
0x18000b8bb  lea     rcx, [rbx+1]
0x18000b8bf  shl     rbx, 4
0x18000b8c3  add     rdx, rbx
0x18000b8c6  mov     rbx, rcx
0x18000b8c9  cmp     [rdx], rsi
0x18000b8cc  jz      short loc_18000B8B2
0x18000b8ce  mov     rsi, [rdx]
0x18000b8d1  mov     r15, [rdx+8]
0x18000b8d5  lea     rcx, [rsp+48h+arg_0]
0x18000b8da  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b8df  test    rsi, rsi
0x18000b8e2  jz      short loc_18000B8EF
0x18000b8e4  mov     rcx, r15
0x18000b8e7  mov     rax, rsi
0x18000b8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8ef  lea     rcx, [rsp+48h+arg_8]
0x18000b8f4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000b8f9  cmp     rbx, rdi
0x18000b8fc  jb      short loc_18000B891
0x18000b8fe  mov     rbx, [rsp+48h+arg_10]
0x18000b903  add     rsp, 20h
0x18000b907  pop     r15
0x18000b909  pop     r14
0x18000b90b  pop     rdi
0x18000b90c  pop     rsi
0x18000b90d  pop     rbp
0x18000b90e  retn
```
