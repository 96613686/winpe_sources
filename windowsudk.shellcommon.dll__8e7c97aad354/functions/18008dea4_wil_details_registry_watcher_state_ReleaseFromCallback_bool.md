# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x18008dea4`
- end: `0x18008df50`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `172`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18008ddf0`
- `0x18045fa90`

## callees

- `0x180010c44`
- `0x18008dea4`
- `0x1800a1b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008dec3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008dec3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008df3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008df3a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18008df2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18008df2c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18008def0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18008def0`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  RTL_SRWLOCK *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  unsigned int v6; // edx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  SRWLock = v2;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &SRWLock,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'(this, v6);
    v2 = SRWLock;
  }
  else if ( a2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x18008dea4  mov     [rsp+arg_8], rbx
0x18008dea9  mov     [rsp+arg_10], rsi
0x18008deae  push    rdi
0x18008deaf  sub     rsp, 20h
0x18008deb3  lea     rbx, [rcx+98h]
0x18008deba  mov     rdi, rcx
0x18008debd  mov     rcx, rbx; SRWLock
0x18008dec0  mov     sil, dl
0x18008dec3  call    cs:__imp_AcquireSRWLockExclusive
0x18008dec9  or      eax, 0FFFFFFFFh
0x18008decc  mov     [rsp+28h+SRWLock], rbx
0x18008ded1  lock xadd [rdi+94h], eax
0x18008ded9  cmp     eax, 1
0x18008dedc  jnz     short loc_18008DF16
0x18008dede  mov     rcx, [rdi+88h]; pwa
0x18008dee5  mov     qword ptr [rdi+88h], 0
0x18008def0  call    cs:__imp_CloseThreadpoolWait
0x18008def6  xor     edx, edx
0x18008def8  lea     rcx, [rsp+28h+SRWLock]
0x18008defd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18008df02  test    rdi, rdi
0x18008df05  jz      short loc_18008DF0F
0x18008df07  mov     rcx, rdi; this
0x18008df0a  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18008df0f  mov     rbx, [rsp+28h+SRWLock]
0x18008df14  jmp     short loc_18008DF32
0x18008df16  test    sil, sil
0x18008df19  jz      short loc_18008DF32
0x18008df1b  mov     rdx, [rdi+80h]; h
0x18008df22  xor     r8d, r8d; pftTimeout
0x18008df25  mov     rcx, [rdi+88h]; pwa
0x18008df2c  call    cs:__imp_SetThreadpoolWait
0x18008df32  test    rbx, rbx
0x18008df35  jz      short loc_18008DF40
0x18008df37  mov     rcx, rbx; SRWLock
0x18008df3a  call    cs:__imp_ReleaseSRWLockExclusive
0x18008df40  mov     rbx, [rsp+28h+arg_8]
0x18008df45  mov     rsi, [rsp+28h+arg_10]
0x18008df4a  add     rsp, 20h
0x18008df4e  pop     rdi
0x18008df4f  retn
```
