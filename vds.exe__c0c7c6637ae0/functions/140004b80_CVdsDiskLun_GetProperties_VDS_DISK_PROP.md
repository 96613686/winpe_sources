# CVdsDiskLun::GetProperties(_VDS_DISK_PROP *)

- ea: `0x140004b80`
- end: `0x140004d72`
- name: `?GetProperties@CVdsDiskLun@@UEAAJPEAU_VDS_DISK_PROP@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, struct _VDS_DISK_PROP *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003710`
- `0x140004b80`
- `0x140005630`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004c1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004c1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140004d2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140004d2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004c2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004cfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004d3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004c2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004cfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004d3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004c00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004c87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004d0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004c00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004c87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004be5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004be5`
- `vdsutil!VdsTraceEx` at `0x140004cad`
- `vdsutil!VdsTraceEx` at `0x140004cef`
- `vdsutil!VdsTraceEx` at `0x140004cad`
- `vdsutil!VdsTraceEx` at `0x140004cef`
- `vdsutil!AcquireRundownProtection` at `0x140004bc8`
- `vdsutil!AcquireRundownProtection` at `0x140004bc8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140004ba9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140004ba9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140004d57`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140004d57`
- `vdsutil!ReleaseRundownProtection` at `0x140004d4b`
- `vdsutil!ReleaseRundownProtection` at `0x140004d4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::GetProperties(CVdsDiskLun *this, struct _VDS_DISK_PROP *a2)
{
  int v4; // esi
  int v5; // edi
  signed int v6; // ebx
  int v7; // eax
  signed int LastError; // eax
  int v9; // eax
  int v10; // eax
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h]
  _BYTE v14[56]; // [rsp+30h] [rbp-38h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v14, 0x5Eu, "CVdsDiskLun::GetProperties() (IVdsDisk)");
  v12 = 0;
  v4 = 0;
  v5 = 0;
  v13 = 0;
  if ( !(unsigned __int8)AcquireRundownProtection(&g_RundownRef) )
  {
    v6 = -2146959352;
    goto LABEL_10;
  }
  v5 = 1;
  v13 = 1;
  if ( g_dwThreadIdExclusiveLock == GetCurrentThreadId() )
    goto LABEL_12;
  EnterCriticalSection(&g_OpsInFlight);
  v7 = g_lOperationsInFly;
  if ( g_lOperationsInFly )
    goto LABEL_9;
  if ( !WaitForSingleObject(g_hExclusiveOperationSem, 0xFFFFFFFF) )
  {
    v7 = g_lOperationsInFly;
LABEL_9:
    g_lOperationsInFly = v7 + 1;
    LeaveCriticalSection(&g_OpsInFlight);
    v6 = 0;
    v4 = 1;
    HIDWORD(v12) = 1;
    goto LABEL_10;
  }
  LeaveCriticalSection(&g_OpsInFlight);
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
  if ( v6 < 0 )
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v12);
    goto LABEL_23;
  }
LABEL_12:
  EnterCriticalSection(&g_GlobalCriticalSection);
  v9 = CVdsDiskLun::ValidateDiskInterfaces(this);
  v6 = v9;
  if ( v9 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct _VDS_DISK_PROP *))(**((_QWORD **)this + 28) + 24LL))(
            *((_QWORD *)this + 28),
            a2);
    v6 = v10;
    if ( v10 < 0 )
      VdsTraceEx(94, 0, "CVdsDiskLun::GetProperties, 2, hr=%lX", v10);
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::GetProperties, 1, hr=%lX", v9);
    if ( v6 == -2147212283 )
      v6 = -2147212277;
  }
  LeaveCriticalSection(&g_GlobalCriticalSection);
  if ( v4 )
  {
    EnterCriticalSection(&g_OpsInFlight);
    if ( !--g_lOperationsInFly )
      ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
    LeaveCriticalSection(&g_OpsInFlight);
  }
  if ( v5 )
    ReleaseRundownProtection(&g_RundownRef);
LABEL_23:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140004b80  mov     [rsp+arg_0], rbx
0x140004b85  mov     [rsp+arg_8], rbp
0x140004b8a  push    rsi
0x140004b8b  push    rdi
0x140004b8c  push    r14
0x140004b8e  sub     rsp, 50h
0x140004b92  mov     r14, rdx
0x140004b95  mov     rbp, rcx
0x140004b98  lea     r8, aCvdsdisklunGet_28; "CVdsDiskLun::GetProperties() (IVdsDisk)"
0x140004b9f  mov     edx, 5Eh ; '^'
0x140004ba4  lea     rcx, [rsp+68h+var_38]
0x140004ba9  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140004baf  nop
0x140004bb0  mov     [rsp+68h+var_48], 0
0x140004bb9  xor     esi, esi
0x140004bbb  xor     edi, edi
0x140004bbd  mov     [rsp+68h+var_40], edi
0x140004bc1  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140004bc8  call    cs:__imp_AcquireRundownProtection
0x140004bce  test    al, al
0x140004bd0  jnz     short loc_140004BDC
0x140004bd2  mov     ebx, 80080008h
0x140004bd7  jmp     loc_140004C6D
0x140004bdc  mov     edi, 1
0x140004be1  mov     [rsp+68h+var_40], edi
0x140004be5  call    cs:__imp_GetCurrentThreadId
0x140004beb  mov     ecx, cs:?g_dwThreadIdExclusiveLock@@3KC; ulong volatile g_dwThreadIdExclusiveLock
0x140004bf1  cmp     ecx, eax
0x140004bf3  jz      loc_140004C80
0x140004bf9  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004c00  call    cs:__imp_EnterCriticalSection
0x140004c06  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140004c0c  test    eax, eax
0x140004c0e  jnz     short loc_140004C50
0x140004c10  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140004c15  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hHandle
0x140004c1c  call    cs:__imp_WaitForSingleObject
0x140004c22  test    eax, eax
0x140004c24  jz      short loc_140004C4A
0x140004c26  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004c2d  call    cs:__imp_LeaveCriticalSection
0x140004c33  call    cs:__imp_GetLastError
0x140004c39  mov     ebx, eax
0x140004c3b  test    eax, eax
0x140004c3d  jle     short loc_140004C6D
0x140004c3f  movzx   ebx, ax
0x140004c42  or      ebx, 80070000h
0x140004c48  jmp     short loc_140004C6D
0x140004c4a  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140004c50  inc     eax
0x140004c52  mov     cs:?g_lOperationsInFly@@3JA, eax; long g_lOperationsInFly
0x140004c58  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004c5f  call    cs:__imp_LeaveCriticalSection
0x140004c65  xor     ebx, ebx
0x140004c67  mov     esi, edi
0x140004c69  mov     dword ptr [rsp+68h+var_48+4], edi
0x140004c6d  test    ebx, ebx
0x140004c6f  jns     short loc_140004C80
0x140004c71  lea     rcx, [rsp+68h+var_48]; this
0x140004c76  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140004c7b  jmp     loc_140004D52
0x140004c80  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004c87  call    cs:__imp_EnterCriticalSection
0x140004c8d  nop
0x140004c8e  mov     rcx, rbp; this
0x140004c91  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140004c96  mov     ebx, eax
0x140004c98  test    eax, eax
0x140004c9a  jns     short loc_140004CC2
0x140004c9c  mov     r9d, eax
0x140004c9f  lea     r8, aCvdsdisklunGet_18; "CVdsDiskLun::GetProperties, 1, hr=%lX"
0x140004ca6  xor     edx, edx
0x140004ca8  mov     ecx, 5Eh ; '^'
0x140004cad  call    cs:__imp_VdsTraceEx
0x140004cb3  cmp     ebx, 80042405h
0x140004cb9  jnz     short loc_140004CF6
0x140004cbb  mov     ebx, 8004240Bh
0x140004cc0  jmp     short loc_140004CF6
0x140004cc2  mov     rcx, [rbp+0E0h]
0x140004cc9  mov     rax, [rcx]
0x140004ccc  mov     rdx, r14
0x140004ccf  mov     rax, [rax+18h]
0x140004cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004cd8  mov     ebx, eax
0x140004cda  test    eax, eax
0x140004cdc  jns     short loc_140004CF6
0x140004cde  mov     r9d, eax
0x140004ce1  lea     r8, aCvdsdisklunGet_104; "CVdsDiskLun::GetProperties, 2, hr=%lX"
0x140004ce8  xor     edx, edx
0x140004cea  mov     ecx, 5Eh ; '^'
0x140004cef  call    cs:__imp_VdsTraceEx
0x140004cf5  nop
0x140004cf6  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004cfd  call    cs:__imp_LeaveCriticalSection
0x140004d03  nop
0x140004d04  test    esi, esi
0x140004d06  jz      short loc_140004D40
0x140004d08  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004d0f  call    cs:__imp_EnterCriticalSection
0x140004d15  sub     cs:?g_lOperationsInFly@@3JA, 1; long g_lOperationsInFly
0x140004d1c  jnz     short loc_140004D33
0x140004d1e  xor     r8d, r8d; lpPreviousCount
0x140004d21  mov     edx, 1; lReleaseCount
0x140004d26  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hSemaphore
0x140004d2d  call    cs:__imp_ReleaseSemaphore
0x140004d33  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004d3a  call    cs:__imp_LeaveCriticalSection
0x140004d40  test    edi, edi
0x140004d42  jz      short loc_140004D52
0x140004d44  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140004d4b  call    cs:__imp_ReleaseRundownProtection
0x140004d51  nop
0x140004d52  lea     rcx, [rsp+68h+var_38]
0x140004d57  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140004d5d  mov     eax, ebx
0x140004d5f  mov     rbx, [rsp+68h+arg_0]
0x140004d64  mov     rbp, [rsp+68h+arg_8]
0x140004d69  add     rsp, 50h
0x140004d6d  pop     r14
0x140004d6f  pop     rdi
0x140004d70  pop     rsi
0x140004d71  retn
```
