# WorkThreadManager::CThread::RunCurrentTaskUnderLock(void)

- ea: `0x180019840`
- end: `0x180019910`
- name: `?RunCurrentTaskUnderLock@CThread@WorkThreadManager@@QEAAXXZ`
- size: `208`
- prototype: `void __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180019474`

## callees

- `0x180019840`
- `0x1800377e0`
- `0x1800415e4`
- `0x18006d924`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019857`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019857`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800198d4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800198d4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800198f4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800198f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800198e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800198e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WorkThreadManager::CThread::RunCurrentTaskUnderLock(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  __int64 v3; // rcx
  const struct wil::wob_ticket *v4; // rdx
  PVOID Ptr; // rcx
  HANDLE CurrentThread; // rax
  _DWORD v7[2]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+28h] [rbp-10h]
  RTL_SRWLOCK *v9; // [rsp+40h] [rbp+8h] BYREF

  v2 = this + 28;
  AcquireSRWLockShared(this + 28);
  v9 = v2;
  if ( this[24].Ptr )
  {
    WorkThreadManager::CThread::AdjustThreadPriority(v3, (__int64)v7, HIDWORD(this[18].Ptr));
    wil::set_wob_ticket((wil *)&this[21], v4);
    LODWORD(this[16].Ptr) = (HIDWORD(this[9].Ptr) | (LODWORD(this[9].Ptr) << 24) | 0x800000) + 1;
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)this[24].Ptr + 24LL))(this[24].Ptr);
    LODWORD(this[16].Ptr) = (HIDWORD(this[9].Ptr) | (LODWORD(this[9].Ptr) << 24)) + 1;
    Ptr = this[20].Ptr;
    if ( Ptr )
      SetEvent(Ptr);
    if ( v8 && v7[0] )
    {
      CurrentThread = GetCurrentThread();
      SetThreadPriority(CurrentThread, v7[1]);
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v9);
}

```

## disassembly

```asm
0x180019840  mov     [rsp+arg_8], rbx
0x180019845  push    rdi
0x180019846  sub     rsp, 30h
0x18001984a  mov     rdi, rcx
0x18001984d  lea     rbx, [rcx+0E0h]
0x180019854  mov     rcx, rbx; SRWLock
0x180019857  call    cs:__imp_AcquireSRWLockShared
0x18001985d  mov     [rsp+38h+arg_0], rbx
0x180019862  xor     ebx, ebx
0x180019864  cmp     [rdi+0C0h], rbx
0x18001986b  jz      loc_1800198FB
0x180019871  mov     r8d, [rdi+94h]
0x180019878  lea     rdx, [rsp+38h+var_18]
0x18001987d  call    ?AdjustThreadPriority@CThread@WorkThreadManager@@QEAA@W4TaskOptions@Internal@Windows@@@Z; WorkThreadManager::CThread::AdjustThreadPriority(Windows::Internal::TaskOptions)
0x180019882  nop
0x180019883  lea     rcx, [rdi+0A8h]; this
0x18001988a  call    ?set_wob_ticket@wil@@YA_NAEBUwob_ticket@1@@Z; wil::set_wob_ticket(wil::wob_ticket const &)
0x18001988f  mov     eax, [rdi+48h]
0x180019892  shl     eax, 18h
0x180019895  or      eax, [rdi+4Ch]
0x180019898  bts     eax, 17h
0x18001989c  inc     eax
0x18001989e  mov     [rdi+80h], eax
0x1800198a4  mov     rcx, [rdi+0C0h]
0x1800198ab  mov     rax, [rcx]
0x1800198ae  mov     rax, [rax+18h]
0x1800198b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198b7  mov     eax, [rdi+48h]
0x1800198ba  shl     eax, 18h
0x1800198bd  or      eax, [rdi+4Ch]
0x1800198c0  inc     eax
0x1800198c2  mov     [rdi+80h], eax
0x1800198c8  mov     rcx, [rdi+0A0h]; hEvent
0x1800198cf  test    rcx, rcx
0x1800198d2  jz      short loc_1800198DB
0x1800198d4  call    cs:__imp_SetEvent
0x1800198da  nop
0x1800198db  cmp     [rsp+38h+var_10], bl
0x1800198df  jz      short loc_1800198FB
0x1800198e1  cmp     [rsp+38h+var_18], ebx
0x1800198e5  jz      short loc_1800198FB
0x1800198e7  call    cs:__imp_GetCurrentThread
0x1800198ed  mov     edx, [rsp+38h+nPriority]; nPriority
0x1800198f1  mov     rcx, rax; hThread
0x1800198f4  call    cs:__imp_SetThreadPriority
0x1800198fa  nop
0x1800198fb  lea     rcx, [rsp+38h+arg_0]
0x180019900  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180019905  mov     rbx, [rsp+38h+arg_8]
0x18001990a  add     rsp, 30h
0x18001990e  pop     rdi
0x18001990f  retn
```
