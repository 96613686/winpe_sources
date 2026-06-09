# CVdsService::GetVolumeId(ushort *,_GUID *,int *)

- ea: `0x140006a80`
- end: `0x140006e55`
- name: `?GetVolumeId@CVdsService@@SAJPEAGPEAU_GUID@@PEAH@Z`
- size: `981`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *, int *)`
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400066a0`
- `0x14000cd7c`
- `0x14000fd1c`
- `0x140023620`
- `0x140028340`
- `0x14002ec40`

## callees

- `0x140003710`
- `0x140006a80`
- `0x140012c48`
- `0x140013298`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140006c37`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140006c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140006deb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140006deb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006c48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006c7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006df8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006c48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006c7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006df8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006c1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006dcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006c1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006c00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006c00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006b7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006b7a`
- `vdsutil!OpenDevice` at `0x140006af6`
- `vdsutil!OpenDevice` at `0x140006af6`
- `vdsutil!GetDeviceName` at `0x140006b63`
- `vdsutil!GetDeviceName` at `0x140006b63`
- `vdsutil!VdsTraceEx` at `0x140006b16`
- `vdsutil!VdsTraceEx` at `0x140006b9d`
- `vdsutil!VdsTraceEx` at `0x140006d77`
- `vdsutil!VdsTraceEx` at `0x140006b16`
- `vdsutil!VdsTraceEx` at `0x140006b9d`
- `vdsutil!VdsTraceEx` at `0x140006d77`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140006cb2`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140006cb2`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140006ccb`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140006ccb`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140006cf9`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140006cf9`
- `vdsutil!AcquireRundownProtection` at `0x140006be3`
- `vdsutil!AcquireRundownProtection` at `0x140006be3`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140006d9d`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140006d9d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140006ac5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140006ac5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140006b45`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140006bc0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140006e2c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140006b45`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140006bc0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140006e2c`
- `vdsutil!ReleaseRundownProtection` at `0x140006e09`
- `vdsutil!ReleaseRundownProtection` at `0x140006e09`

## string_xrefs

- `0x140006ab4`: `CVdsService::GetVolumeId()`
- `0x140006b05`: `CVdsService::GetVolumeId, 1, error=%ld`
- `0x140006b8c`: `CVdsService::GetVolumeId, 2, error=%ld`
- `0x140006d69`: `CVdsService::GetVolumeId: unexpected error from provider: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVdsService::GetVolumeId(unsigned __int16 *a1, struct _GUID *a2, int *a3)
{
  signed int v6; // eax
  signed int v7; // ebx
  signed int DeviceName; // ebx
  int v10; // edi
  int v11; // ebx
  signed int v12; // esi
  int v13; // eax
  signed int LastError; // eax
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  signed int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h]
  __int128 Buf1; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 Buf2; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v27[560]; // [rsp+A0h] [rbp-60h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v24, 0x5Eu, "CVdsService::GetVolumeId()");
  v19 = 0;
  Buf1 = 0;
  hObject = 0;
  *a2 = GUID_NULL;
  v6 = OpenDevice(a1, 0, &hObject);
  v7 = v6;
  if ( v6 )
  {
    VdsTraceEx(94, 1, "CVdsService::GetVolumeId, 1, error=%ld", v6);
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
    return (unsigned int)v7;
  }
  DeviceName = GetDeviceName(hObject, 0, 274, v27);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( DeviceName )
  {
    VdsTraceEx(94, 1, "CVdsService::GetVolumeId, 2, error=%ld", DeviceName);
    if ( DeviceName > 0 )
      DeviceName = (unsigned __int16)DeviceName | 0x80070000;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
    return (unsigned int)DeviceName;
  }
  v21 = 0;
  v10 = 0;
  v11 = 0;
  v22 = 0;
  if ( !(unsigned __int8)AcquireRundownProtection(&g_RundownRef) )
  {
    v12 = -2146959352;
    goto LABEL_22;
  }
  v11 = 1;
  v22 = 1;
  if ( g_dwThreadIdExclusiveLock != GetCurrentThreadId() )
  {
    EnterCriticalSection(&g_OpsInFlight);
    v13 = g_lOperationsInFly;
    if ( !g_lOperationsInFly )
    {
      if ( WaitForSingleObject(g_hExclusiveOperationSem, 0xFFFFFFFF) )
      {
        LeaveCriticalSection(&g_OpsInFlight);
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_22:
        if ( v12 < 0 )
        {
          CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v21);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
          goto LABEL_45;
        }
        goto LABEL_24;
      }
      v13 = g_lOperationsInFly;
    }
    g_lOperationsInFly = v13 + 1;
    LeaveCriticalSection(&g_OpsInFlight);
    v12 = 0;
    v10 = 1;
    HIDWORD(v21) = 1;
    goto LABEL_22;
  }
LABEL_24:
  for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
        ;
        CRtlListIter::Next((CRtlListIter *)&Buf1) )
  {
    Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v26);
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
    {
      v12 = 1;
      goto LABEL_37;
    }
    EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
    v16 = (**EntryPointer)(EntryPointer, &IID_IVdsSwProviderPrivate, &v19);
    if ( v16 < 0 )
    {
      VdsLogError(0xC2000009, 0, 0, v16, 0x2000016u, 0);
      continue;
    }
    v17 = (*(__int64 (__fastcall **)(__int64, _BYTE *, struct _GUID *))(*(_QWORD *)v19 + 40LL))(v19, v27, a2);
    if ( v17 >= 0 )
      break;
    if ( v17 != -2147212283 )
      VdsTraceEx(94, 0, "CVdsService::GetVolumeId: unexpected error from provider: %X", v17);
    v18 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  v12 = 0;
  if ( a3 )
    *a3 = v17 == 0;
LABEL_37:
  if ( v10 )
  {
    EnterCriticalSection(&g_OpsInFlight);
    if ( !--g_lOperationsInFly )
      ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
    LeaveCriticalSection(&g_OpsInFlight);
  }
  if ( v11 )
    ReleaseRundownProtection(&g_RundownRef);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_45:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140006a80  push    rbp
0x140006a82  push    rbx
0x140006a83  push    rsi
0x140006a84  push    rdi
0x140006a85  push    r12
0x140006a87  push    r14
0x140006a89  push    r15
0x140006a8b  lea     rbp, [rsp-1E0h]
0x140006a93  sub     rsp, 2E0h
0x140006a9a  mov     rax, cs:__security_cookie
0x140006aa1  xor     rax, rsp
0x140006aa4  mov     [rbp+210h+var_40], rax
0x140006aab  mov     r15, r8
0x140006aae  mov     r14, rdx
0x140006ab1  mov     rbx, rcx
0x140006ab4  lea     r8, aCvdsserviceGet_71; "CVdsService::GetVolumeId()"
0x140006abb  mov     edx, 5Eh ; '^'
0x140006ac0  lea     rcx, [rsp+310h+var_2B0]
0x140006ac5  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140006acb  nop
0x140006acc  xor     r12d, r12d
0x140006acf  mov     [rsp+310h+var_2E0], r12
0x140006ad4  xorps   xmm0, xmm0
0x140006ad7  movups  [rsp+310h+Buf1], xmm0
0x140006adc  mov     [rsp+310h+hObject], r12
0x140006ae1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140006ae8  movups  xmmword ptr [r14], xmm0
0x140006aec  lea     r8, [rsp+310h+hObject]
0x140006af1  xor     edx, edx
0x140006af3  mov     rcx, rbx
0x140006af6  call    cs:__imp_OpenDevice
0x140006afc  mov     ebx, eax
0x140006afe  test    eax, eax
0x140006b00  jz      short loc_140006B52
0x140006b02  mov     r9d, eax
0x140006b05  lea     r8, aCvdsserviceGet_29; "CVdsService::GetVolumeId, 1, error=%ld"
0x140006b0c  mov     edx, 1
0x140006b11  mov     ecx, 5Eh ; '^'
0x140006b16  call    cs:__imp_VdsTraceEx
0x140006b1c  test    ebx, ebx
0x140006b1e  jle     short loc_140006B29
0x140006b20  movzx   ebx, bx
0x140006b23  or      ebx, 80070000h
0x140006b29  mov     rcx, [rsp+310h+var_2E0]
0x140006b2e  test    rcx, rcx
0x140006b31  jz      short loc_140006B40
0x140006b33  mov     rdx, [rcx]
0x140006b36  mov     rax, [rdx+10h]
0x140006b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b3f  nop
0x140006b40  lea     rcx, [rsp+310h+var_2B0]
0x140006b45  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140006b4b  mov     eax, ebx
0x140006b4d  jmp     loc_140006E34
0x140006b52  lea     r9, [rbp+210h+var_270]
0x140006b56  xor     edx, edx
0x140006b58  mov     r8d, 112h
0x140006b5e  mov     rcx, [rsp+310h+hObject]
0x140006b63  call    cs:__imp_GetDeviceName
0x140006b69  mov     ebx, eax
0x140006b6b  mov     rcx, [rsp+310h+hObject]; hObject
0x140006b70  lea     rax, [rcx-1]
0x140006b74  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006b78  ja      short loc_140006B85
0x140006b7a  call    cs:__imp_CloseHandle
0x140006b80  mov     [rsp+310h+hObject], r12
0x140006b85  test    ebx, ebx
0x140006b87  jz      short loc_140006BCD
0x140006b89  mov     r9d, ebx
0x140006b8c  lea     r8, aCvdsserviceGet_87; "CVdsService::GetVolumeId, 2, error=%ld"
0x140006b93  mov     edx, 1
0x140006b98  mov     ecx, 5Eh ; '^'
0x140006b9d  call    cs:__imp_VdsTraceEx
0x140006ba3  test    ebx, ebx
0x140006ba5  jle     short loc_140006BB0
0x140006ba7  movzx   ebx, bx
0x140006baa  or      ebx, 80070000h
0x140006bb0  lea     rcx, [rsp+310h+var_2E0]
0x140006bb5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140006bba  nop
0x140006bbb  lea     rcx, [rsp+310h+var_2B0]
0x140006bc0  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140006bc6  mov     eax, ebx
0x140006bc8  jmp     loc_140006E34
0x140006bcd  mov     [rsp+310h+var_2D0], r12
0x140006bd2  mov     edi, r12d
0x140006bd5  mov     ebx, r12d
0x140006bd8  mov     [rsp+310h+var_2C8], ebx
0x140006bdc  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140006be3  call    cs:__imp_AcquireRundownProtection
0x140006be9  test    al, al
0x140006beb  jnz     short loc_140006BF7
0x140006bed  mov     esi, 80080008h
0x140006bf2  jmp     loc_140006C89
0x140006bf7  mov     ebx, 1
0x140006bfc  mov     [rsp+310h+var_2C8], ebx
0x140006c00  call    cs:__imp_GetCurrentThreadId
0x140006c06  mov     ecx, cs:?g_dwThreadIdExclusiveLock@@3KC; ulong volatile g_dwThreadIdExclusiveLock
0x140006c0c  cmp     ecx, eax
0x140006c0e  jz      loc_140006CA7
0x140006c14  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006c1b  call    cs:__imp_EnterCriticalSection
0x140006c21  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140006c27  test    eax, eax
0x140006c29  jnz     short loc_140006C6B
0x140006c2b  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140006c30  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hHandle
0x140006c37  call    cs:__imp_WaitForSingleObject
0x140006c3d  test    eax, eax
0x140006c3f  jz      short loc_140006C65
0x140006c41  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006c48  call    cs:__imp_LeaveCriticalSection
0x140006c4e  call    cs:__imp_GetLastError
0x140006c54  mov     esi, eax
0x140006c56  test    eax, eax
0x140006c58  jle     short loc_140006C89
0x140006c5a  movzx   esi, ax
0x140006c5d  or      esi, 80070000h
0x140006c63  jmp     short loc_140006C89
0x140006c65  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140006c6b  inc     eax
0x140006c6d  mov     cs:?g_lOperationsInFly@@3JA, eax; long g_lOperationsInFly
0x140006c73  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006c7a  call    cs:__imp_LeaveCriticalSection
0x140006c80  mov     esi, r12d
0x140006c83  mov     edi, ebx
0x140006c85  mov     dword ptr [rsp+310h+var_2D0+4], ebx
0x140006c89  test    esi, esi
0x140006c8b  jns     short loc_140006CA7
0x140006c8d  lea     rcx, [rsp+310h+var_2D0]; this
0x140006c92  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140006c97  nop
0x140006c98  lea     rcx, [rsp+310h+var_2E0]
0x140006c9d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140006ca2  jmp     loc_140006E27
0x140006ca7  lea     rdx, [rbp+210h+Buf2]
0x140006cab  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140006cb2  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x140006cb8  movups  xmm0, xmmword ptr [rax]
0x140006cbb  movups  [rsp+310h+Buf1], xmm0
0x140006cc0  lea     rdx, [rbp+210h+var_280]
0x140006cc4  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140006ccb  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x140006cd1  movups  xmm0, xmmword ptr [rax]
0x140006cd4  movaps  [rbp+210h+Buf2], xmm0
0x140006cd8  mov     r8d, 10h; Size
0x140006cde  lea     rdx, [rbp+210h+Buf2]; Buf2
0x140006ce2  lea     rcx, [rsp+310h+Buf1]; Buf1
0x140006ce7  call    memcmp_0
0x140006cec  test    eax, eax
0x140006cee  jz      loc_140006DBD
0x140006cf4  lea     rcx, [rsp+310h+Buf1]
0x140006cf9  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x140006cff  mov     r9, rax
0x140006d02  mov     rcx, [rax]
0x140006d05  mov     rax, [rcx]
0x140006d08  lea     r8, [rsp+310h+var_2E0]
0x140006d0d  lea     rdx, IID_IVdsSwProviderPrivate
0x140006d14  mov     rcx, r9
0x140006d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d1c  test    eax, eax
0x140006d1e  jns     short loc_140006D41
0x140006d20  mov     [rsp+310h+var_2E8], r12; unsigned __int16 *
0x140006d25  mov     [rsp+310h+var_2F0], 2000016h; unsigned int
0x140006d2d  mov     r9d, eax; unsigned int
0x140006d30  xor     r8d, r8d; void *
0x140006d33  xor     edx, edx; unsigned int
0x140006d35  mov     ecx, 0C2000009h; unsigned int
0x140006d3a  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140006d3f  jmp     short loc_140006D98
0x140006d41  mov     rcx, [rsp+310h+var_2E0]
0x140006d46  mov     rax, [rcx]
0x140006d49  mov     r8, r14
0x140006d4c  lea     rdx, [rbp+210h+var_270]
0x140006d50  mov     rax, [rax+28h]
0x140006d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d59  mov     ecx, eax
0x140006d5b  test    eax, eax
0x140006d5d  jns     short loc_140006DA8
0x140006d5f  cmp     eax, 80042405h
0x140006d64  jz      short loc_140006D7D
0x140006d66  mov     r9d, eax
0x140006d69  lea     r8, aCvdsserviceGet_51; "CVdsService::GetVolumeId: unexpected er"...
0x140006d70  xor     edx, edx
0x140006d72  mov     ecx, 5Eh ; '^'
0x140006d77  call    cs:__imp_VdsTraceEx
0x140006d7d  mov     rcx, [rsp+310h+var_2E0]
0x140006d82  test    rcx, rcx
0x140006d85  jz      short loc_140006D98
0x140006d87  mov     [rsp+310h+var_2E0], r12
0x140006d8c  mov     rax, [rcx]
0x140006d8f  mov     rax, [rax+10h]
0x140006d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d98  lea     rcx, [rsp+310h+Buf1]
0x140006d9d  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x140006da3  jmp     loc_140006CC0
0x140006da8  mov     esi, r12d
0x140006dab  test    r15, r15
0x140006dae  jz      short loc_140006DC2
0x140006db0  mov     eax, r12d
0x140006db3  test    ecx, ecx
0x140006db5  setz    al
0x140006db8  mov     [r15], eax
0x140006dbb  jmp     short loc_140006DC2
0x140006dbd  mov     esi, 1
0x140006dc2  test    edi, edi
0x140006dc4  jz      short loc_140006DFE
0x140006dc6  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006dcd  call    cs:__imp_EnterCriticalSection
0x140006dd3  sub     cs:?g_lOperationsInFly@@3JA, 1; long g_lOperationsInFly
0x140006dda  jnz     short loc_140006DF1
0x140006ddc  xor     r8d, r8d; lpPreviousCount
0x140006ddf  mov     edx, 1; lReleaseCount
0x140006de4  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hSemaphore
0x140006deb  call    cs:__imp_ReleaseSemaphore
0x140006df1  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006df8  call    cs:__imp_LeaveCriticalSection
0x140006dfe  test    ebx, ebx
0x140006e00  jz      short loc_140006E10
0x140006e02  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140006e09  call    cs:__imp_ReleaseRundownProtection
0x140006e0f  nop
0x140006e10  mov     rcx, [rsp+310h+var_2E0]
0x140006e15  test    rcx, rcx
0x140006e18  jz      short loc_140006E27
0x140006e1a  mov     rdx, [rcx]
0x140006e1d  mov     rax, [rdx+10h]
0x140006e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e26  nop
0x140006e27  lea     rcx, [rsp+310h+var_2B0]
0x140006e2c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140006e32  mov     eax, esi
0x140006e34  mov     rcx, [rbp+210h+var_40]
0x140006e3b  xor     rcx, rsp; StackCookie
0x140006e3e  call    __security_check_cookie
0x140006e43  add     rsp, 2E0h
0x140006e4a  pop     r15
0x140006e4c  pop     r14
0x140006e4e  pop     r12
0x140006e50  pop     rdi
0x140006e51  pop     rsi
0x140006e52  pop     rbx
0x140006e53  pop     rbp
0x140006e54  retn
```
