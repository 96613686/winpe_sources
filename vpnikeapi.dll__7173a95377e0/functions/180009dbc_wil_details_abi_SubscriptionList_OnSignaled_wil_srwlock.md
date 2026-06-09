# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180009dbc`
- end: `0x180009e82`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `198`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006c60`
- `0x180006c90`
- `0x180008788`

## callees

- `0x180007b24`
- `0x180007b44`
- `0x180007b64`
- `0x180009dbc`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009e05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009e05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009dd5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009dd5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e13`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // rbp
  __int64 v7; // r15
  unsigned __int64 v8; // rax
  WORD *v9; // rcx
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  LPCRITICAL_SECTION v11; // [rsp+58h] [rbp+10h] BYREF

  AcquireSRWLockShared(SRWLock);
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  v10 = SRWLock;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    v11 = lpCriticalSection;
    AcquireSRWLockExclusive(SRWLock);
    v10 = SRWLock;
    if ( v5 < v4 )
    {
      while ( 1 )
      {
        v8 = v5 + 1;
        v9 = &lpCriticalSection[1].DebugInfo->Type + 8 * v5++;
        if ( *(_QWORD *)v9 )
          break;
        if ( v8 >= v4 )
          goto LABEL_7;
      }
      v6 = *(void (__fastcall **)(__int64))v9;
      v7 = *((_QWORD *)v9 + 1);
    }
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    if ( v6 )
      v6(v7);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180009dbc  mov     [rsp+arg_10], rbx
0x180009dc1  push    rbp
0x180009dc2  push    rsi
0x180009dc3  push    rdi
0x180009dc4  push    r14
0x180009dc6  push    r15
0x180009dc8  sub     rsp, 20h
0x180009dcc  mov     rsi, rcx
0x180009dcf  mov     r14, rdx
0x180009dd2  mov     rcx, rdx; SRWLock
0x180009dd5  call    cs:__imp_AcquireSRWLockShared
0x180009ddb  mov     rdi, [rsi+30h]
0x180009ddf  lea     rcx, [rsp+48h+arg_0]
0x180009de4  sub     rdi, [rsi+28h]
0x180009de8  shr     rdi, 4
0x180009dec  mov     [rsp+48h+arg_0], r14
0x180009df1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009df6  xor     ebx, ebx
0x180009df8  test    rdi, rdi
0x180009dfb  jz      short loc_180009E71
0x180009dfd  mov     rcx, rsi; lpCriticalSection
0x180009e00  xor     ebp, ebp
0x180009e02  xor     r15d, r15d
0x180009e05  call    cs:__imp_EnterCriticalSection
0x180009e0b  mov     rcx, r14; SRWLock
0x180009e0e  mov     [rsp+48h+arg_8], rsi
0x180009e13  call    cs:__imp_AcquireSRWLockExclusive
0x180009e19  mov     [rsp+48h+arg_0], r14
0x180009e1e  cmp     rbx, rdi
0x180009e21  jnb     short loc_180009E48
0x180009e23  mov     rdx, [rsi+28h]
0x180009e27  lea     rax, [rbx+1]
0x180009e2b  add     rbx, rbx
0x180009e2e  lea     rcx, [rdx+rbx*8]
0x180009e32  mov     rbx, rax
0x180009e35  cmp     [rcx], rbp
0x180009e38  jnz     short loc_180009E41
0x180009e3a  cmp     rax, rdi
0x180009e3d  jb      short loc_180009E27
0x180009e3f  jmp     short loc_180009E48
0x180009e41  mov     rbp, [rcx]
0x180009e44  mov     r15, [rcx+8]
0x180009e48  lea     rcx, [rsp+48h+arg_0]
0x180009e4d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009e52  test    rbp, rbp
0x180009e55  jz      short loc_180009E62
0x180009e57  mov     rcx, r15
0x180009e5a  mov     rax, rbp
0x180009e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e62  lea     rcx, [rsp+48h+arg_8]
0x180009e67  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180009e6c  cmp     rbx, rdi
0x180009e6f  jb      short loc_180009DFD
0x180009e71  mov     rbx, [rsp+48h+arg_10]
0x180009e76  add     rsp, 20h
0x180009e7a  pop     r15
0x180009e7c  pop     r14
0x180009e7e  pop     rdi
0x180009e7f  pop     rsi
0x180009e80  pop     rbp
0x180009e81  retn
```
