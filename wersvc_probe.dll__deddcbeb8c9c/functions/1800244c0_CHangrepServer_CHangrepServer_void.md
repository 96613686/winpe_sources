# CHangrepServer::~CHangrepServer(void)

- ea: `0x1800244c0`
- end: `0x1800245bb`
- name: `??1CHangrepServer@@QEAA@XZ`
- size: `251`
- prototype: `void __fastcall(CHangrepServer *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014074`

## callees

- `0x180003d6c`
- `0x180006900`
- `0x180013df4`
- `0x1800244c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18002451a`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180024534`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18002451a`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180024534`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800245b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002455d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002455d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800244ed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800244ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180024500`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002456c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180024500`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002456c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHangrepServer::~CHangrepServer(struct _RTL_CRITICAL_SECTION *this)
{
  struct _TP_WAIT *OwningThread; // rcx
  struct _TP_WAIT *v3; // rcx
  REGHANDLE v4; // rcx
  REGHANDLE v5; // rcx
  __int64 v6; // rcx
  HANDLE LockSemaphore; // rcx
  struct _TP_WAIT *v8; // rcx
  char *v9; // rcx
  char *v10; // rbx

  if ( this[1].LockSemaphore != (HANDLE)-1LL && this[1].LockSemaphore != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  OwningThread = (struct _TP_WAIT *)this[1].OwningThread;
  if ( OwningThread )
  {
    WaitForThreadpoolWaitCallbacks(OwningThread, 1);
    v3 = (struct _TP_WAIT *)this[1].OwningThread;
    this[1].OwningThread = 0;
    if ( v3 )
      CloseThreadpoolWait(v3);
  }
  v4 = qword_1800470E8;
  dword_1800470C8 = 0;
  qword_1800470E8 = 0;
  EventUnregister(v4);
  v5 = qword_180047120;
  dword_180047100 = 0;
  qword_180047120 = 0;
  EventUnregister(v5);
  if ( LODWORD(this[1].DebugInfo) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( *(_QWORD *)&this[1].LockCount )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  LockSemaphore = this[1].LockSemaphore;
  if ( (unsigned __int64)LockSemaphore + 1 > 1 )
    CloseHandle(LockSemaphore);
  v8 = (struct _TP_WAIT *)this[1].OwningThread;
  if ( v8 )
    CloseThreadpoolWait(v8);
  v9 = *(char **)&this[1].LockCount;
  if ( v9 )
  {
    v10 = v9 - 8;
    `eh vector destructor iterator'(v9, 0x998u, *((_QWORD *)v9 - 1), (void (*)(void *))CHungApp::~CHungApp);
    operator delete[](v10, (const struct std::nothrow_t *)(2456LL * *(_QWORD *)v10 + 8));
  }
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800244c0  mov     [rsp+arg_0], rbx
0x1800244c5  push    rdi
0x1800244c6  sub     rsp, 20h
0x1800244ca  mov     rdi, rcx
0x1800244cd  mov     rax, [rcx+40h]
0x1800244d1  inc     rax
0x1800244d4  cmp     rax, 1
0x1800244d8  jbe     short loc_1800244DF
0x1800244da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800244df  mov     rcx, [rdi+38h]; pwa
0x1800244e3  xor     ebx, ebx
0x1800244e5  test    rcx, rcx
0x1800244e8  jz      short loc_180024506
0x1800244ea  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x1800244ed  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800244f3  mov     rcx, [rdi+38h]; pwa
0x1800244f7  mov     [rdi+38h], rbx
0x1800244fb  test    rcx, rcx
0x1800244fe  jz      short loc_180024506
0x180024500  call    cs:__imp_CloseThreadpoolWait
0x180024506  mov     rcx, cs:qword_1800470E8; RegHandle
0x18002450d  mov     cs:dword_1800470C8, ebx
0x180024513  mov     cs:qword_1800470E8, rbx
0x18002451a  call    cs:__imp_EventUnregister
0x180024520  mov     rcx, cs:qword_180047120; RegHandle
0x180024527  mov     cs:dword_180047100, ebx
0x18002452d  mov     cs:qword_180047120, rbx
0x180024534  call    cs:__imp_EventUnregister
0x18002453a  cmp     [rdi+28h], ebx
0x18002453d  jz      short loc_180024544
0x18002453f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024544  cmp     [rdi+30h], rbx
0x180024548  jz      short loc_18002454F
0x18002454a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002454f  mov     rcx, [rdi+40h]; hObject
0x180024553  lea     rax, [rcx+1]
0x180024557  cmp     rax, 1
0x18002455b  jbe     short loc_180024563
0x18002455d  call    cs:__imp_CloseHandle
0x180024563  mov     rcx, [rdi+38h]; pwa
0x180024567  test    rcx, rcx
0x18002456a  jz      short loc_180024572
0x18002456c  call    cs:__imp_CloseThreadpoolWait
0x180024572  mov     rcx, [rdi+30h]; void *
0x180024576  test    rcx, rcx
0x180024579  jz      short loc_1800245A7
0x18002457b  lea     rbx, [rcx-8]
0x18002457f  lea     r9, ??1CHungApp@@QEAA@XZ; void (*)(void *)
0x180024586  mov     r8, [rbx]; unsigned __int64
0x180024589  mov     edx, 998h; unsigned __int64
0x18002458e  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180024593  imul    rdx, [rbx], 998h
0x18002459a  add     rdx, 8; struct std::nothrow_t *
0x18002459e  mov     rcx, rbx; void *
0x1800245a1  call    ??_V@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete[](void *,std::nothrow_t const &)
0x1800245a6  nop
0x1800245a7  mov     rcx, rdi
0x1800245aa  mov     rbx, [rsp+28h+arg_0]
0x1800245af  add     rsp, 20h
0x1800245b3  pop     rdi
0x1800245b4  jmp     cs:__imp_DeleteCriticalSection
```
