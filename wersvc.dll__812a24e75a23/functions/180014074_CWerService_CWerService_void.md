# CWerService::~CWerService(void)

- ea: `0x180014074`
- end: `0x18001417c`
- name: `??1CWerService@@QEAA@XZ`
- size: `264`
- prototype: `void __fastcall(CWerService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1800352d0`

## callees

- `0x1800029f4`
- `0x180013e9c`
- `0x180014074`
- `0x1800244c0`
- `0x18002dccc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014167`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014167`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014175`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001409a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001412b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001409a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001412b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014142`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180014154`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180014154`
- `ntdll!NtClose` at `0x1800140c3`
- `ntdll!NtClose` at `0x1800140c3`

## pseudocode

```c
void __fastcall CWerService::~CWerService(CWerService *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  struct _TP_CLEANUP_GROUP *v10; // rcx

  CHangrepServer::~CHangrepServer((struct _RTL_CRITICAL_SECTION *)((char *)this + 416));
  v2 = (void *)*((_QWORD *)this + 51);
  if ( (unsigned __int64)v2 + 1 > 1 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 50);
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 49);
  if ( v4 )
    NtClose(v4);
  v5 = *((_QWORD *)this + 45);
  if ( v5 != -1 )
  {
    v6 = *((_QWORD *)this + 46) - v5;
    *((_QWORD *)this + 46) = v5;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(
      (__int64)v4,
      v5,
      v6 >> 3);
    operator delete(*((void **)this + 45), (const struct std::nothrow_t *)&std::nothrow);
  }
  v7 = (void *)*((_QWORD *)this + 44);
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  v8 = (void *)*((_QWORD *)this + 43);
  if ( (unsigned __int64)v8 + 1 > 1 )
    CloseHandle(v8);
  v9 = (void *)*((_QWORD *)this + 41);
  if ( (unsigned __int64)v9 + 1 > 1 )
    CloseHandle(v9);
  v10 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 28);
  if ( v10 )
    CloseThreadpoolCleanupGroup(v10);
  CHandleMonitor::~CHandleMonitor((CWerService *)((char *)this + 80));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180014074  push    rbx
0x180014076  sub     rsp, 20h
0x18001407a  mov     rbx, rcx
0x18001407d  add     rcx, 1A0h; this
0x180014084  call    ??1CHangrepServer@@QEAA@XZ; CHangrepServer::~CHangrepServer(void)
0x180014089  mov     rcx, [rbx+198h]; hObject
0x180014090  lea     rax, [rcx+1]
0x180014094  cmp     rax, 1
0x180014098  jbe     short loc_1800140A0
0x18001409a  call    cs:__imp_CloseHandle
0x1800140a0  mov     rcx, [rbx+190h]; hObject
0x1800140a7  lea     rax, [rcx+1]
0x1800140ab  cmp     rax, 1
0x1800140af  jbe     short loc_1800140B7
0x1800140b1  call    cs:__imp_CloseHandle
0x1800140b7  mov     rcx, [rbx+188h]; Handle
0x1800140be  test    rcx, rcx
0x1800140c1  jz      short loc_1800140C9
0x1800140c3  call    cs:__imp_NtClose
0x1800140c9  mov     rdx, [rbx+168h]
0x1800140d0  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800140d4  jz      short loc_180014103
0x1800140d6  mov     r8, [rbx+170h]
0x1800140dd  sub     r8, rdx
0x1800140e0  mov     [rbx+170h], rdx
0x1800140e7  sar     r8, 3
0x1800140eb  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@0@PEAV?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>> &,utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>> *,unsigned __int64)
0x1800140f0  mov     rcx, [rbx+168h]; void *
0x1800140f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800140fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014103  mov     rcx, [rbx+160h]; hObject
0x18001410a  lea     rax, [rcx+1]
0x18001410e  cmp     rax, 1
0x180014112  jbe     short loc_18001411A
0x180014114  call    cs:__imp_CloseHandle
0x18001411a  mov     rcx, [rbx+158h]; hObject
0x180014121  lea     rax, [rcx+1]
0x180014125  cmp     rax, 1
0x180014129  jbe     short loc_180014131
0x18001412b  call    cs:__imp_CloseHandle
0x180014131  mov     rcx, [rbx+148h]; hObject
0x180014138  lea     rax, [rcx+1]
0x18001413c  cmp     rax, 1
0x180014140  jbe     short loc_180014148
0x180014142  call    cs:__imp_CloseHandle
0x180014148  mov     rcx, [rbx+0E0h]; ptpcg
0x18001414f  test    rcx, rcx
0x180014152  jz      short loc_18001415A
0x180014154  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001415a  lea     rcx, [rbx+50h]; this
0x18001415e  call    ??1CHandleMonitor@@QEAA@XZ; CHandleMonitor::~CHandleMonitor(void)
0x180014163  lea     rcx, [rbx+28h]; lpCriticalSection
0x180014167  call    cs:__imp_DeleteCriticalSection
0x18001416d  mov     rcx, rbx
0x180014170  add     rsp, 20h
0x180014174  pop     rbx
0x180014175  jmp     cs:__imp_DeleteCriticalSection
```
