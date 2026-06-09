# CVdsProvider::QueryPacks(IEnumVdsObject * *)

- ea: `0x140002ef0`
- end: `0x140003297`
- name: `?QueryPacks@CVdsProvider@@UEAAJPEAPEAUIEnumVdsObject@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(CVdsProvider *__hidden this, struct IEnumVdsObject **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002ef0`
- `0x1400032a0`
- `0x140003710`
- `0x14000c110`
- `0x14000f98c`
- `0x140012c48`
- `0x140013298`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400030be`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400030be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x14000305c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003120`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x14000305c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003120`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002f93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003069`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400030d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000312d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002f93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003069`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400030d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000312d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002f70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000303e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003102`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002f70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000303e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400030d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400030d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002f59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002f59`
- `vdsutil!VdsTraceEx` at `0x1400031d7`
- `vdsutil!VdsTraceEx` at `0x1400031d7`
- `vdsutil!AcquireRundownProtection` at `0x140002f43`
- `vdsutil!AcquireRundownProtection` at `0x140002f43`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002f24`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002fbd`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002f24`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002fbd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002fda`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000307b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000313b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400031ac`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140003201`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140003261`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002fda`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000307b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000313b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400031ac`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140003201`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140003261`
- `vdsutil!ReleaseRundownProtection` at `0x140003165`
- `vdsutil!ReleaseRundownProtection` at `0x140003182`
- `vdsutil!ReleaseRundownProtection` at `0x140003165`
- `vdsutil!ReleaseRundownProtection` at `0x140003182`

## string_xrefs

- `0x140002fad`: `VdsCreateInstance() (2)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CVdsProvider::QueryPacks(CVdsProvider *this, struct IEnumVdsObject **a2)
{
  int v4; // esi
  int v5; // edi
  int v6; // eax
  signed int v7; // ebx
  struct CVdsEnumObject *Instance; // rbx
  int v9; // eax
  unsigned int v10; // r14d
  signed int LastError; // eax
  signed int v13; // eax
  __int64 v14; // [rsp+30h] [rbp-30h] BYREF
  __int64 v15; // [rsp+38h] [rbp-28h]
  _BYTE v16[16]; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v17[16]; // [rsp+50h] [rbp-10h] BYREF
  struct CVdsEnumObject *v18; // [rsp+A8h] [rbp+48h] BYREF
  struct IEnumVdsObject *v19; // [rsp+B0h] [rbp+50h] BYREF

  v19 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v16, 0x5Eu, "CVdsProvider::QueryPacks()");
  *a2 = 0;
  v14 = 0;
  v4 = 0;
  v5 = 0;
  LODWORD(v15) = 0;
  if ( (unsigned __int8)AcquireRundownProtection(&g_RundownRef) )
  {
    v5 = 1;
    LODWORD(v15) = 1;
    if ( g_dwThreadIdExclusiveLock == GetCurrentThreadId() )
      goto LABEL_6;
    EnterCriticalSection(&g_OpsInFlight);
    v6 = g_lOperationsInFly;
    if ( g_lOperationsInFly )
      goto LABEL_4;
    if ( !WaitForSingleObject(g_hExclusiveOperationSem, 0xFFFFFFFF) )
    {
      v6 = g_lOperationsInFly;
LABEL_4:
      g_lOperationsInFly = v6 + 1;
      LeaveCriticalSection(&g_OpsInFlight);
      v7 = 0;
      v4 = 1;
      HIDWORD(v14) = 1;
      goto LABEL_5;
    }
    LeaveCriticalSection(&g_OpsInFlight);
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v7 = -2146959352;
  }
LABEL_5:
  if ( v7 < 0 )
  {
    if ( v4 )
    {
      EnterCriticalSection(&g_OpsInFlight);
      if ( !--g_lOperationsInFly )
        ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
      LeaveCriticalSection(&g_OpsInFlight);
    }
    if ( v5 )
      ReleaseRundownProtection(&g_RundownRef);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
    if ( v19 )
      ((void (__fastcall *)(struct IEnumVdsObject *))v19->lpVtbl->Release)(v19);
    return (unsigned int)v7;
  }
LABEL_6:
  v18 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "VdsCreateInstance() (2)");
  Instance = (struct CVdsEnumObject *)VdsCreateInstance(0, VDS_OT_ENUM, 0);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  v18 = Instance;
  if ( Instance )
  {
    *((_DWORD *)Instance + 23) = 10;
    v9 = (*(__int64 (__fastcall **)(_QWORD, struct IEnumVdsObject **))(**((_QWORD **)this + 17) + 24LL))(
           *((_QWORD *)this + 17),
           &v19);
    v10 = v9;
    if ( !v19 )
    {
      VdsTraceEx(94, 0, "CVdsProvider::QueryPacks, 1, hr=%lX", v9);
      if ( !v10 )
        v10 = -2147212222;
      ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v18);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v14);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
      return v10;
    }
    if ( v9 >= 0 )
    {
      v13 = ConnectEnumWrapper(Instance, v19, *((struct CVdsService **)this + 14));
      v10 = v13;
      if ( v13 < 0 )
      {
        VdsLogError(0xC2000009, 0, 0, v13, 0x2080000u, 0, v14, v15);
        ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v18);
        CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v14);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
        return v10;
      }
      v10 = (**(__int64 (__fastcall ***)(struct CVdsEnumObject *, GUID *, struct IEnumVdsObject **))Instance)(
              Instance,
              &IID_IEnumVdsObject,
              a2);
    }
    (*(void (__fastcall **)(struct CVdsEnumObject *))(*(_QWORD *)Instance + 16LL))(Instance);
    if ( v4 )
    {
      EnterCriticalSection(&g_OpsInFlight);
      if ( !--g_lOperationsInFly )
        ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
      LeaveCriticalSection(&g_OpsInFlight);
    }
    if ( v5 )
      ReleaseRundownProtection(&g_RundownRef);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
    if ( v19 )
      ((void (__fastcall *)(struct IEnumVdsObject *))v19->lpVtbl->Release)(v19);
    return v10;
  }
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v18);
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v14);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140002ef0  mov     [rsp-38h+arg_0], rbx
0x140002ef5  push    rbp
0x140002ef6  push    rsi
0x140002ef7  push    rdi
0x140002ef8  push    r12
0x140002efa  push    r13
0x140002efc  push    r14
0x140002efe  push    r15
0x140002f00  mov     rbp, rsp
0x140002f03  sub     rsp, 60h
0x140002f07  mov     r15, rdx
0x140002f0a  mov     r13, rcx
0x140002f0d  xor     r12d, r12d
0x140002f10  mov     [rbp+arg_10], r12
0x140002f14  lea     r8, aCvdsproviderQu_11; "CVdsProvider::QueryPacks()"
0x140002f1b  mov     edx, 5Eh ; '^'
0x140002f20  lea     rcx, [rbp+var_20]
0x140002f24  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140002f2a  nop
0x140002f2b  mov     [r15], r12
0x140002f2e  mov     [rbp+var_30], r12
0x140002f32  mov     esi, r12d
0x140002f35  mov     edi, r12d
0x140002f38  mov     dword ptr [rbp+var_28], r12d
0x140002f3c  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140002f43  call    cs:__imp_AcquireRundownProtection
0x140002f49  test    al, al
0x140002f4b  jz      loc_14000318A
0x140002f51  mov     edi, 1
0x140002f56  mov     dword ptr [rbp+var_28], edi
0x140002f59  call    cs:__imp_GetCurrentThreadId
0x140002f5f  mov     ecx, cs:?g_dwThreadIdExclusiveLock@@3KC; ulong volatile g_dwThreadIdExclusiveLock
0x140002f65  cmp     ecx, eax
0x140002f67  jz      short loc_140002FA9
0x140002f69  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002f70  call    cs:__imp_EnterCriticalSection
0x140002f76  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140002f7c  test    eax, eax
0x140002f7e  jz      loc_1400030B2
0x140002f84  inc     eax
0x140002f86  mov     cs:?g_lOperationsInFly@@3JA, eax; long g_lOperationsInFly
0x140002f8c  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002f93  call    cs:__imp_LeaveCriticalSection
0x140002f99  mov     ebx, r12d
0x140002f9c  mov     esi, edi
0x140002f9e  mov     dword ptr [rbp+var_30+4], edi
0x140002fa1  test    ebx, ebx
0x140002fa3  js      loc_1400030F7
0x140002fa9  mov     [rbp+arg_8], r12
0x140002fad  lea     r8, aVdscreateinsta_1; "VdsCreateInstance() (2)"
0x140002fb4  mov     edx, 5Eh ; '^'
0x140002fb9  lea     rcx, [rbp+var_10]
0x140002fbd  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140002fc3  nop
0x140002fc4  xor     r8d, r8d; struct CVdsService *
0x140002fc7  mov     edx, 65h ; 'e'; enum _VDS_OBJECT_TYPE
0x140002fcc  xor     ecx, ecx; struct IUnknown *
0x140002fce  call    ?VdsCreateInstance@@YAPEAXPEAUIUnknown@@W4_VDS_OBJECT_TYPE@@PEAVCVdsService@@@Z; VdsCreateInstance(IUnknown *,_VDS_OBJECT_TYPE,CVdsService *)
0x140002fd3  mov     rbx, rax
0x140002fd6  lea     rcx, [rbp+var_10]
0x140002fda  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002fe0  mov     [rbp+arg_8], rbx
0x140002fe4  test    rbx, rbx
0x140002fe7  jz      loc_140003194
0x140002fed  mov     dword ptr [rbx+5Ch], 0Ah
0x140002ff4  mov     rcx, [r13+88h]
0x140002ffb  mov     rax, [rcx]
0x140002ffe  lea     rdx, [rbp+arg_10]
0x140003002  mov     rax, [rax+18h]
0x140003006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000300b  mov     r14d, eax
0x14000300e  mov     rdx, [rbp+arg_10]; struct IEnumVdsObject *
0x140003012  test    rdx, rdx
0x140003015  jz      loc_1400031C6
0x14000301b  test    eax, eax
0x14000301d  jns     loc_140003216
0x140003023  mov     rax, [rbx]
0x140003026  mov     rcx, rbx
0x140003029  mov     rax, [rax+10h]
0x14000302d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003032  nop
0x140003033  test    esi, esi
0x140003035  jz      short loc_14000306F
0x140003037  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000303e  call    cs:__imp_EnterCriticalSection
0x140003044  sub     cs:?g_lOperationsInFly@@3JA, 1; long g_lOperationsInFly
0x14000304b  jnz     short loc_140003062
0x14000304d  xor     r8d, r8d; lpPreviousCount
0x140003050  mov     edx, 1; lReleaseCount
0x140003055  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hSemaphore
0x14000305c  call    cs:__imp_ReleaseSemaphore
0x140003062  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140003069  call    cs:__imp_LeaveCriticalSection
0x14000306f  test    edi, edi
0x140003071  jnz     loc_14000315E
0x140003077  lea     rcx, [rbp+var_20]
0x14000307b  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140003081  nop
0x140003082  mov     rcx, [rbp+arg_10]
0x140003086  test    rcx, rcx
0x140003089  jz      short loc_140003097
0x14000308b  mov     rax, [rcx]
0x14000308e  mov     rax, [rax+10h]
0x140003092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003097  mov     eax, r14d
0x14000309a  mov     rbx, [rsp+60h+arg_0]
0x1400030a2  add     rsp, 60h
0x1400030a6  pop     r15
0x1400030a8  pop     r14
0x1400030aa  pop     r13
0x1400030ac  pop     r12
0x1400030ae  pop     rdi
0x1400030af  pop     rsi
0x1400030b0  pop     rbp
0x1400030b1  retn
0x1400030b2  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1400030b7  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hHandle
0x1400030be  call    cs:__imp_WaitForSingleObject
0x1400030c4  test    eax, eax
0x1400030c6  jz      loc_140003170
0x1400030cc  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400030d3  call    cs:__imp_LeaveCriticalSection
0x1400030d9  call    cs:__imp_GetLastError
0x1400030df  mov     ebx, eax
0x1400030e1  test    eax, eax
0x1400030e3  jle     loc_140002FA1
0x1400030e9  movzx   ebx, ax
0x1400030ec  or      ebx, 80070000h
0x1400030f2  jmp     loc_140002FA1
0x1400030f7  test    esi, esi
0x1400030f9  jz      short loc_140003133
0x1400030fb  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140003102  call    cs:__imp_EnterCriticalSection
0x140003108  sub     cs:?g_lOperationsInFly@@3JA, 1; long g_lOperationsInFly
0x14000310f  jnz     short loc_140003126
0x140003111  xor     r8d, r8d; lpPreviousCount
0x140003114  mov     edx, 1; lReleaseCount
0x140003119  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hSemaphore
0x140003120  call    cs:__imp_ReleaseSemaphore
0x140003126  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000312d  call    cs:__imp_LeaveCriticalSection
0x140003133  test    edi, edi
0x140003135  jnz     short loc_14000317B
0x140003137  lea     rcx, [rbp+var_20]
0x14000313b  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140003141  nop
0x140003142  mov     rcx, [rbp+arg_10]
0x140003146  test    rcx, rcx
0x140003149  jz      short loc_140003157
0x14000314b  mov     rax, [rcx]
0x14000314e  mov     rax, [rax+10h]
0x140003152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003157  mov     eax, ebx
0x140003159  jmp     loc_14000309A
0x14000315e  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140003165  call    cs:__imp_ReleaseRundownProtection
0x14000316b  jmp     loc_140003077
0x140003170  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140003176  jmp     loc_140002F84
0x14000317b  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140003182  call    cs:__imp_ReleaseRundownProtection
0x140003188  jmp     short loc_140003137
0x14000318a  mov     ebx, 80080008h
0x14000318f  jmp     loc_140002FA1
0x140003194  lea     rcx, [rbp+arg_8]
0x140003198  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14000319d  nop
0x14000319e  lea     rcx, [rbp+var_30]; this
0x1400031a2  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400031a7  nop
0x1400031a8  lea     rcx, [rbp+var_20]
0x1400031ac  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400031b2  nop
0x1400031b3  lea     rcx, [rbp+arg_10]
0x1400031b7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400031bc  mov     eax, 8007000Eh
0x1400031c1  jmp     loc_14000309A
0x1400031c6  mov     r9d, r14d
0x1400031c9  lea     r8, aCvdsproviderQu; "CVdsProvider::QueryPacks, 1, hr=%lX"
0x1400031d0  xor     edx, edx
0x1400031d2  mov     ecx, 5Eh ; '^'
0x1400031d7  call    cs:__imp_VdsTraceEx
0x1400031dd  mov     eax, 80042442h
0x1400031e2  test    r14d, r14d
0x1400031e5  cmovz   r14d, eax
0x1400031e9  lea     rcx, [rbp+arg_8]
0x1400031ed  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x1400031f2  nop
0x1400031f3  lea     rcx, [rbp+var_30]; this
0x1400031f7  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400031fc  nop
0x1400031fd  lea     rcx, [rbp+var_20]
0x140003201  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140003207  nop
0x140003208  lea     rcx, [rbp+arg_10]
0x14000320c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140003211  jmp     loc_140003097
0x140003216  mov     r8, [r13+70h]; struct CVdsService *
0x14000321a  mov     rcx, rbx; struct CVdsEnumObject *
0x14000321d  call    ?ConnectEnumWrapper@@YAJPEAVCVdsEnumObject@@PEAUIEnumVdsObject@@PEAVCVdsService@@@Z; ConnectEnumWrapper(CVdsEnumObject *,IEnumVdsObject *,CVdsService *)
0x140003222  mov     r14d, eax
0x140003225  test    eax, eax
0x140003227  jns     short loc_140003276
0x140003229  mov     [rsp+60h+var_38], r12; unsigned __int16 *
0x14000322e  mov     [rsp+60h+var_40], 2080000h; unsigned int
0x140003236  mov     r9d, eax; unsigned int
0x140003239  xor     r8d, r8d; void *
0x14000323c  xor     edx, edx; unsigned int
0x14000323e  mov     ecx, 0C2000009h; unsigned int
0x140003243  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140003248  nop
0x140003249  lea     rcx, [rbp+arg_8]
0x14000324d  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140003252  nop
0x140003253  lea     rcx, [rbp+var_30]; this
0x140003257  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14000325c  nop
0x14000325d  lea     rcx, [rbp+var_20]
0x140003261  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140003267  nop
0x140003268  lea     rcx, [rbp+arg_10]
0x14000326c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140003271  jmp     loc_140003097
0x140003276  mov     rax, [rbx]
0x140003279  mov     r8, r15
0x14000327c  lea     rdx, IID_IEnumVdsObject
0x140003283  mov     rcx, rbx
0x140003286  mov     rax, [rax]
0x140003289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000328e  mov     r14d, eax
0x140003291  jmp     loc_140003023
```
