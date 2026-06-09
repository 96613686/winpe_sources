# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x180041f34`
- end: `0x180041fd8`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `164`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180043ef0`

## callees

- `0x18000c90c`
- `0x18003fda8`
- `0x180041f34`
- `0x1800450d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180041fc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180041fc7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180041f80`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180041f80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180041fb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180041fb7`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  struct _TP_WAIT *v4; // rcx
  unsigned int v5; // edx
  PSRWLOCK SRWLock[3]; // [rsp+20h] [rbp-18h] BYREF

  SRWLock[0] = 0;
  wil::AcquireSRWLockExclusive(SRWLock, (char *)this + 152);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v4 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v4);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      SRWLock,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'(this, v5);
  }
  else if ( a2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
}

```

## disassembly

```asm
0x180041f34  mov     [rsp+arg_8], rbx
0x180041f39  push    rdi
0x180041f3a  sub     rsp, 30h
0x180041f3e  mov     dil, dl
0x180041f41  mov     [rsp+38h+SRWLock], 0
0x180041f4a  lea     rdx, [rcx+98h]
0x180041f51  mov     rbx, rcx
0x180041f54  lea     rcx, [rsp+38h+SRWLock]
0x180041f59  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180041f5e  or      eax, 0FFFFFFFFh
0x180041f61  lock xadd [rbx+94h], eax
0x180041f69  cmp     eax, 1
0x180041f6c  jnz     short loc_180041FA1
0x180041f6e  mov     rcx, [rbx+88h]; pwa
0x180041f75  mov     qword ptr [rbx+88h], 0
0x180041f80  call    cs:__imp_CloseThreadpoolWait
0x180041f86  xor     edx, edx
0x180041f88  lea     rcx, [rsp+38h+SRWLock]
0x180041f8d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180041f92  test    rbx, rbx
0x180041f95  jz      short loc_180041FBD
0x180041f97  mov     rcx, rbx; this
0x180041f9a  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180041f9f  jmp     short loc_180041FBD
0x180041fa1  test    dil, dil
0x180041fa4  jz      short loc_180041FBD
0x180041fa6  mov     rdx, [rbx+80h]; h
0x180041fad  xor     r8d, r8d; pftTimeout
0x180041fb0  mov     rcx, [rbx+88h]; pwa
0x180041fb7  call    cs:__imp_SetThreadpoolWait
0x180041fbd  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x180041fc2  test    rcx, rcx
0x180041fc5  jz      short loc_180041FCD
0x180041fc7  call    cs:__imp_ReleaseSRWLockExclusive
0x180041fcd  mov     rbx, [rsp+38h+arg_8]
0x180041fd2  add     rsp, 30h
0x180041fd6  pop     rdi
0x180041fd7  retn
```
