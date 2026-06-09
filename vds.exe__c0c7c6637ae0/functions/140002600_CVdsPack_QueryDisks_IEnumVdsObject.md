# CVdsPack::QueryDisks(IEnumVdsObject * *)

- ea: `0x140002600`
- end: `0x140002983`
- name: `?QueryDisks@CVdsPack@@UEAAJPEAPEAUIEnumVdsObject@@@Z`
- size: `899`
- prototype: `__int64 __fastcall(CVdsPack *__hidden this, struct IEnumVdsObject **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002600`
- `0x1400032a0`
- `0x140003710`
- `0x14000c110`
- `0x14000f98c`
- `0x140012c48`
- `0x140013298`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400026a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400026a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140002724`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140002923`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140002724`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140002923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400026b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400026e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002731`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002930`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400026b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400026e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002731`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002930`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000268a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002706`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002905`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000268a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002706`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400026bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400026bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000266f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000266f`
- `vdsutil!VdsTraceEx` at `0x14000281a`
- `vdsutil!VdsTraceEx` at `0x14000281a`
- `vdsutil!AcquireRundownProtection` at `0x140002653`
- `vdsutil!AcquireRundownProtection` at `0x140002653`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002634`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002784`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002634`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002784`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000274d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400027a1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400027be`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000284a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400028ba`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000294c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000274d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400027a1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400027be`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000284a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400028ba`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000294c`
- `vdsutil!ReleaseRundownProtection` at `0x140002742`
- `vdsutil!ReleaseRundownProtection` at `0x140002941`
- `vdsutil!ReleaseRundownProtection` at `0x140002742`
- `vdsutil!ReleaseRundownProtection` at `0x140002941`

## string_xrefs

- `0x140002774`: `VdsCreateInstance() (2)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CVdsPack::QueryDisks(CVdsPack *this, struct IEnumVdsObject **a2)
{
  int v4; // esi
  int v5; // edi
  signed int v6; // ebx
  int v7; // eax
  signed int LastError; // eax
  struct CVdsEnumObject *Instance; // rbx
  int v11; // eax
  unsigned int v12; // r14d
  void (*Release)(void); // rax
  signed int v14; // eax
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+38h] [rbp-28h]
  _BYTE v17[16]; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v18[16]; // [rsp+50h] [rbp-10h] BYREF
  struct CVdsEnumObject *v19; // [rsp+A8h] [rbp+48h] BYREF
  struct IEnumVdsObject *v20; // [rsp+B0h] [rbp+50h] BYREF

  v20 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsPack::QueryDisks()");
  *a2 = 0;
  v15 = 0;
  v4 = 0;
  v5 = 0;
  LODWORD(v16) = 0;
  if ( !(unsigned __int8)AcquireRundownProtection(&g_RundownRef) )
  {
    v6 = -2146959352;
    goto LABEL_10;
  }
  v5 = 1;
  LODWORD(v16) = 1;
  if ( g_dwThreadIdExclusiveLock == GetCurrentThreadId() )
    goto LABEL_20;
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
    HIDWORD(v15) = 1;
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
    if ( v4 )
    {
      EnterCriticalSection(&g_OpsInFlight);
      if ( !--g_lOperationsInFly )
        ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
      LeaveCriticalSection(&g_OpsInFlight);
    }
    if ( v5 )
      ReleaseRundownProtection(&g_RundownRef);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
    if ( v20 )
      ((void (__fastcall *)(struct IEnumVdsObject *))v20->lpVtbl->Release)(v20);
    return (unsigned int)v6;
  }
LABEL_20:
  v19 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v18, 0x5Eu, "VdsCreateInstance() (2)");
  Instance = (struct CVdsEnumObject *)VdsCreateInstance(0, VDS_OT_ENUM, 0);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
  v19 = Instance;
  if ( Instance )
  {
    *((_DWORD *)Instance + 23) = 13;
    v11 = (*(__int64 (__fastcall **)(_QWORD, struct IEnumVdsObject **))(**((_QWORD **)this + 11) + 48LL))(
            *((_QWORD *)this + 11),
            &v20);
    v12 = v11;
    if ( v20 )
    {
      if ( v11 >= 0 )
      {
        v14 = ConnectEnumWrapper(Instance, v20, *((struct CVdsService **)this + 10));
        v12 = v14;
        if ( v14 < 0 )
        {
          VdsLogError(0xC2000009, 0, 0, v14, 0x2070004u, 0, v15, v16);
          ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v19);
          CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v15);
          CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
          return v12;
        }
        v12 = (**(__int64 (__fastcall ***)(struct CVdsEnumObject *, GUID *, struct IEnumVdsObject **))Instance)(
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
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
      if ( !v20 )
        return v12;
      Release = (void (*)(void))v20->lpVtbl->Release;
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsPack::QueryDisks, 1, hr=%lX", v11);
      if ( !v12 )
        v12 = -2147212222;
      (*(void (__fastcall **)(struct CVdsEnumObject *))(*(_QWORD *)Instance + 16LL))(Instance);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v15);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
      if ( !v20 )
        return v12;
      Release = (void (*)(void))v20->lpVtbl->Release;
    }
    Release();
    return v12;
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v15);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  if ( v20 )
    ((void (__fastcall *)(struct IEnumVdsObject *))v20->lpVtbl->Release)(v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140002600  mov     [rsp-38h+arg_0], rbx
0x140002605  push    rbp
0x140002606  push    rsi
0x140002607  push    rdi
0x140002608  push    r12
0x14000260a  push    r13
0x14000260c  push    r14
0x14000260e  push    r15
0x140002610  mov     rbp, rsp
0x140002613  sub     rsp, 60h
0x140002617  mov     r15, rdx
0x14000261a  mov     r13, rcx
0x14000261d  xor     r12d, r12d
0x140002620  mov     [rbp+arg_10], r12
0x140002624  lea     r8, aCvdspackQueryd_0; "CVdsPack::QueryDisks()"
0x14000262b  mov     edx, 5Eh ; '^'
0x140002630  lea     rcx, [rbp+var_20]
0x140002634  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000263a  nop
0x14000263b  mov     [r15], r12
0x14000263e  mov     [rbp+var_30], r12
0x140002642  mov     esi, r12d
0x140002645  mov     edi, r12d
0x140002648  mov     dword ptr [rbp+var_28], r12d
0x14000264c  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140002653  call    cs:__imp_AcquireRundownProtection
0x140002659  test    al, al
0x14000265b  jnz     short loc_140002667
0x14000265d  mov     ebx, 80080008h
0x140002662  jmp     loc_1400026F7
0x140002667  mov     edi, 1
0x14000266c  mov     dword ptr [rbp+var_28], edi
0x14000266f  call    cs:__imp_GetCurrentThreadId
0x140002675  mov     ecx, cs:?g_dwThreadIdExclusiveLock@@3KC; ulong volatile g_dwThreadIdExclusiveLock
0x14000267b  cmp     ecx, eax
0x14000267d  jz      loc_140002770
0x140002683  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000268a  call    cs:__imp_EnterCriticalSection
0x140002690  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140002696  test    eax, eax
0x140002698  jnz     short loc_1400026DA
0x14000269a  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x14000269f  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hHandle
0x1400026a6  call    cs:__imp_WaitForSingleObject
0x1400026ac  test    eax, eax
0x1400026ae  jz      short loc_1400026D4
0x1400026b0  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400026b7  call    cs:__imp_LeaveCriticalSection
0x1400026bd  call    cs:__imp_GetLastError
0x1400026c3  mov     ebx, eax
0x1400026c5  test    eax, eax
0x1400026c7  jle     short loc_1400026F7
0x1400026c9  movzx   ebx, ax
0x1400026cc  or      ebx, 80070000h
0x1400026d2  jmp     short loc_1400026F7
0x1400026d4  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x1400026da  inc     eax
0x1400026dc  mov     cs:?g_lOperationsInFly@@3JA, eax; long g_lOperationsInFly
0x1400026e2  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400026e9  call    cs:__imp_LeaveCriticalSection
0x1400026ef  mov     ebx, r12d
0x1400026f2  mov     esi, edi
0x1400026f4  mov     dword ptr [rbp+var_30+4], edi
0x1400026f7  test    ebx, ebx
0x1400026f9  jns     short loc_140002770
0x1400026fb  test    esi, esi
0x1400026fd  jz      short loc_140002737
0x1400026ff  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002706  call    cs:__imp_EnterCriticalSection
0x14000270c  sub     cs:?g_lOperationsInFly@@3JA, 1; long g_lOperationsInFly
0x140002713  jnz     short loc_14000272A
0x140002715  xor     r8d, r8d; lpPreviousCount
0x140002718  mov     edx, 1; lReleaseCount
0x14000271d  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hSemaphore
0x140002724  call    cs:__imp_ReleaseSemaphore
0x14000272a  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002731  call    cs:__imp_LeaveCriticalSection
0x140002737  test    edi, edi
0x140002739  jz      short loc_140002749
0x14000273b  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140002742  call    cs:__imp_ReleaseRundownProtection
0x140002748  nop
0x140002749  lea     rcx, [rbp+var_20]
0x14000274d  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002753  nop
0x140002754  mov     rcx, [rbp+arg_10]
0x140002758  test    rcx, rcx
0x14000275b  jz      short loc_140002769
0x14000275d  mov     rax, [rcx]
0x140002760  mov     rax, [rax+10h]
0x140002764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002769  mov     eax, ebx
0x14000276b  jmp     loc_14000296B
0x140002770  mov     [rbp+arg_8], r12
0x140002774  lea     r8, aVdscreateinsta_1; "VdsCreateInstance() (2)"
0x14000277b  mov     edx, 5Eh ; '^'
0x140002780  lea     rcx, [rbp+var_10]
0x140002784  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000278a  nop
0x14000278b  xor     r8d, r8d; struct CVdsService *
0x14000278e  mov     edx, 65h ; 'e'; enum _VDS_OBJECT_TYPE
0x140002793  xor     ecx, ecx; struct IUnknown *
0x140002795  call    ?VdsCreateInstance@@YAPEAXPEAUIUnknown@@W4_VDS_OBJECT_TYPE@@PEAVCVdsService@@@Z; VdsCreateInstance(IUnknown *,_VDS_OBJECT_TYPE,CVdsService *)
0x14000279a  mov     rbx, rax
0x14000279d  lea     rcx, [rbp+var_10]
0x1400027a1  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400027a7  mov     [rbp+arg_8], rbx
0x1400027ab  test    rbx, rbx
0x1400027ae  jnz     short loc_1400027E4
0x1400027b0  lea     rcx, [rbp+var_30]; this
0x1400027b4  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400027b9  nop
0x1400027ba  lea     rcx, [rbp+var_20]
0x1400027be  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400027c4  nop
0x1400027c5  mov     rcx, [rbp+arg_10]
0x1400027c9  test    rcx, rcx
0x1400027cc  jz      short loc_1400027DA
0x1400027ce  mov     rax, [rcx]
0x1400027d1  mov     rax, [rax+10h]
0x1400027d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027da  mov     eax, 8007000Eh
0x1400027df  jmp     loc_14000296B
0x1400027e4  mov     dword ptr [rbx+5Ch], 0Dh
0x1400027eb  mov     rcx, [r13+58h]
0x1400027ef  mov     rax, [rcx]
0x1400027f2  lea     rdx, [rbp+arg_10]
0x1400027f6  mov     rax, [rax+30h]
0x1400027fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027ff  mov     r14d, eax
0x140002802  mov     rdx, [rbp+arg_10]; struct IEnumVdsObject *
0x140002806  test    rdx, rdx
0x140002809  jnz     short loc_14000286A
0x14000280b  mov     r9d, eax
0x14000280e  lea     r8, aCvdspackQueryd; "CVdsPack::QueryDisks, 1, hr=%lX"
0x140002815  mov     ecx, 5Eh ; '^'
0x14000281a  call    cs:__imp_VdsTraceEx
0x140002820  mov     eax, 80042442h
0x140002825  test    r14d, r14d
0x140002828  cmovz   r14d, eax
0x14000282c  mov     rax, [rbx]
0x14000282f  mov     rcx, rbx
0x140002832  mov     rax, [rax+10h]
0x140002836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000283b  nop
0x14000283c  lea     rcx, [rbp+var_30]; this
0x140002840  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140002845  nop
0x140002846  lea     rcx, [rbp+var_20]
0x14000284a  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002850  nop
0x140002851  mov     rcx, [rbp+arg_10]
0x140002855  test    rcx, rcx
0x140002858  jz      loc_140002968
0x14000285e  mov     rdx, [rcx]
0x140002861  mov     rax, [rdx+10h]
0x140002865  jmp     loc_140002963
0x14000286a  test    r14d, r14d
0x14000286d  js      short loc_1400028EA
0x14000286f  mov     r8, [r13+50h]; struct CVdsService *
0x140002873  mov     rcx, rbx; struct CVdsEnumObject *
0x140002876  call    ?ConnectEnumWrapper@@YAJPEAVCVdsEnumObject@@PEAUIEnumVdsObject@@PEAVCVdsService@@@Z; ConnectEnumWrapper(CVdsEnumObject *,IEnumVdsObject *,CVdsService *)
0x14000287b  mov     r14d, eax
0x14000287e  test    eax, eax
0x140002880  jns     short loc_1400028CF
0x140002882  mov     [rsp+60h+var_38], r12; unsigned __int16 *
0x140002887  mov     [rsp+60h+var_40], 2070004h; unsigned int
0x14000288f  mov     r9d, eax; unsigned int
0x140002892  xor     r8d, r8d; void *
0x140002895  xor     edx, edx; unsigned int
0x140002897  mov     ecx, 0C2000009h; unsigned int
0x14000289c  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400028a1  nop
0x1400028a2  lea     rcx, [rbp+arg_8]
0x1400028a6  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x1400028ab  nop
0x1400028ac  lea     rcx, [rbp+var_30]; this
0x1400028b0  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400028b5  nop
0x1400028b6  lea     rcx, [rbp+var_20]
0x1400028ba  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400028c0  nop
0x1400028c1  lea     rcx, [rbp+arg_10]
0x1400028c5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400028ca  jmp     loc_140002968
0x1400028cf  mov     rax, [rbx]
0x1400028d2  mov     r8, r15
0x1400028d5  lea     rdx, IID_IEnumVdsObject
0x1400028dc  mov     rcx, rbx
0x1400028df  mov     rax, [rax]
0x1400028e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028e7  mov     r14d, eax
0x1400028ea  mov     rax, [rbx]
0x1400028ed  mov     rcx, rbx
0x1400028f0  mov     rax, [rax+10h]
0x1400028f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028f9  nop
0x1400028fa  test    esi, esi
0x1400028fc  jz      short loc_140002936
0x1400028fe  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002905  call    cs:__imp_EnterCriticalSection
0x14000290b  sub     cs:?g_lOperationsInFly@@3JA, 1; long g_lOperationsInFly
0x140002912  jnz     short loc_140002929
0x140002914  xor     r8d, r8d; lpPreviousCount
0x140002917  mov     edx, 1; lReleaseCount
0x14000291c  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hSemaphore
0x140002923  call    cs:__imp_ReleaseSemaphore
0x140002929  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002930  call    cs:__imp_LeaveCriticalSection
0x140002936  test    edi, edi
0x140002938  jz      short loc_140002948
0x14000293a  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140002941  call    cs:__imp_ReleaseRundownProtection
0x140002947  nop
0x140002948  lea     rcx, [rbp+var_20]
0x14000294c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002952  nop
0x140002953  mov     rcx, [rbp+arg_10]
0x140002957  test    rcx, rcx
0x14000295a  jz      short loc_140002968
0x14000295c  mov     rax, [rcx]
0x14000295f  mov     rax, [rax+10h]
0x140002963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002968  mov     eax, r14d
0x14000296b  mov     rbx, [rsp+60h+arg_0]
0x140002973  add     rsp, 60h
0x140002977  pop     r15
0x140002979  pop     r14
0x14000297b  pop     r13
0x14000297d  pop     r12
0x14000297f  pop     rdi
0x140002980  pop     rsi
0x140002981  pop     rbp
0x140002982  retn
```
