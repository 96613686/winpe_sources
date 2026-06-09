# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x180046898`
- end: `0x18004695d`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `197`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002bd80`

## callees

- `0x1800083a4`
- `0x180046898`
- `0x18006fb14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046940`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046940`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800468b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800468b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800468ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800468ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004692c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004692c`

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
0x180046898  mov     [rsp+arg_8], rbx
0x18004689d  mov     [rsp+arg_10], rsi
0x1800468a2  push    rdi
0x1800468a3  sub     rsp, 20h
0x1800468a7  lea     rbx, [rcx+98h]
0x1800468ae  mov     rdi, rcx
0x1800468b1  mov     rcx, rbx; SRWLock
0x1800468b4  mov     sil, dl
0x1800468b7  call    cs:__imp_AcquireSRWLockExclusive
0x1800468be  nop     dword ptr [rax+rax+00h]
0x1800468c3  or      eax, 0FFFFFFFFh
0x1800468c6  mov     [rsp+28h+SRWLock], rbx
0x1800468cb  lock xadd [rdi+94h], eax
0x1800468d3  cmp     eax, 1
0x1800468d6  jnz     short loc_180046916
0x1800468d8  mov     rcx, [rdi+88h]; pwa
0x1800468df  mov     qword ptr [rdi+88h], 0
0x1800468ea  call    cs:__imp_CloseThreadpoolWait
0x1800468f1  nop     dword ptr [rax+rax+00h]
0x1800468f6  xor     edx, edx
0x1800468f8  lea     rcx, [rsp+28h+SRWLock]
0x1800468fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180046902  test    rdi, rdi
0x180046905  jz      short loc_18004690F
0x180046907  mov     rcx, rdi; this
0x18004690a  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18004690f  mov     rbx, [rsp+28h+SRWLock]
0x180046914  jmp     short loc_180046938
0x180046916  test    sil, sil
0x180046919  jz      short loc_180046938
0x18004691b  mov     rdx, [rdi+80h]; h
0x180046922  xor     r8d, r8d; pftTimeout
0x180046925  mov     rcx, [rdi+88h]; pwa
0x18004692c  call    cs:__imp_SetThreadpoolWait
0x180046933  nop     dword ptr [rax+rax+00h]
0x180046938  test    rbx, rbx
0x18004693b  jz      short loc_18004694C
0x18004693d  mov     rcx, rbx; SRWLock
0x180046940  call    cs:__imp_ReleaseSRWLockExclusive
0x180046947  nop     dword ptr [rax+rax+00h]
0x18004694c  mov     rbx, [rsp+28h+arg_8]
0x180046951  mov     rsi, [rsp+28h+arg_10]
0x180046956  add     rsp, 20h
0x18004695a  pop     rdi
0x18004695b  retn
```
