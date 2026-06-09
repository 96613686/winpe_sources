# p9fs::CoroutineIoIssuer::Callback(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x1800293c0`
- end: `0x180029467`
- name: `?Callback@CoroutineIoIssuer@p9fs@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `167`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800030b0`
- `0x1800030d0`
- `0x180004120`
- `0x18000c3e8`
- `0x18000c4bc`
- `0x1800293c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x1800293fc`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x1800293fc`

## pseudocode

```c
void __fastcall p9fs::CoroutineIoIssuer::Callback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        _DWORD *Overlapped,
        ULONG IoResult,
        ULONG_PTR NumberOfBytesTransferred)
{
  char v5; // di
  char v6; // al

  v5 = 1;
  Overlapped[9] = NumberOfBytesTransferred;
  Overlapped[8] = IoResult;
  v6 = *((_BYTE *)Overlapped + 48);
  *((_BYTE *)Overlapped + 48) = 1;
  if ( v6 )
  {
    DisassociateCurrentThreadFromCallback(Instance);
    Smtx_lock_exclusive(&p9fs::g_Scheduler);
    if ( byte_180041818 )
      v5 = 0;
    else
      byte_180041818 = 1;
    Smtx_unlock_exclusive(&p9fs::g_Scheduler);
    p9fs::Scheduler::Schedule(&p9fs::g_Scheduler);
    if ( v5 )
      p9fs::Scheduler::RunAndRelease(&p9fs::g_Scheduler);
  }
}

```

## disassembly

```asm
0x1800293c0  mov     [rsp+arg_8], rbx
0x1800293c5  mov     [rsp+arg_18], rsi
0x1800293ca  push    rdi
0x1800293cb  sub     rsp, 30h
0x1800293cf  mov     rax, cs:__security_cookie
0x1800293d6  xor     rax, rsp
0x1800293d9  mov     [rsp+38h+var_18], rax
0x1800293de  mov     eax, dword ptr [rsp+38h+NumberOfBytesTransferred]
0x1800293e2  mov     edi, 1
0x1800293e7  mov     [r8+24h], eax
0x1800293eb  mov     rbx, r8
0x1800293ee  mov     eax, edi
0x1800293f0  mov     [r8+20h], r9d
0x1800293f4  xchg    al, [r8+30h]
0x1800293f8  test    al, al
0x1800293fa  jz      short loc_18002944A
0x1800293fc  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x180029402  mov     rbx, [rbx+28h]
0x180029406  lea     rsi, ?g_Scheduler@p9fs@@3VScheduler@1@A; p9fs::Scheduler p9fs::g_Scheduler
0x18002940d  mov     rcx, rsi; _Smtx_t *
0x180029410  call    _Smtx_lock_exclusive
0x180029415  cmp     cs:byte_180041818, 0
0x18002941c  mov     rcx, rsi; _Smtx_t *
0x18002941f  jz      short loc_180029426
0x180029421  xor     dil, dil
0x180029424  jmp     short loc_18002942D
0x180029426  mov     cs:byte_180041818, dil
0x18002942d  call    _Smtx_unlock_exclusive
0x180029432  mov     rdx, rbx
0x180029435  mov     rcx, rsi; _Smtx_t *
0x180029438  call    ?Schedule@Scheduler@p9fs@@QEAAXU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Scheduler::Schedule(std::experimental::coroutine_handle<void>)
0x18002943d  test    dil, dil
0x180029440  jz      short loc_18002944A
0x180029442  mov     rcx, rsi; this
0x180029445  call    ?RunAndRelease@Scheduler@p9fs@@AEAAXXZ; p9fs::Scheduler::RunAndRelease(void)
0x18002944a  mov     rcx, [rsp+38h+var_18]
0x18002944f  xor     rcx, rsp; StackCookie
0x180029452  call    __security_check_cookie
0x180029457  mov     rbx, [rsp+38h+arg_8]
0x18002945c  mov     rsi, [rsp+38h+arg_18]
0x180029461  add     rsp, 30h
0x180029465  pop     rdi
0x180029466  retn
```
