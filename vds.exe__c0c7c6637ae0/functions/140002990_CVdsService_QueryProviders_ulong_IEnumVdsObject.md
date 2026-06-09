# CVdsService::QueryProviders(ulong,IEnumVdsObject * *)

- ea: `0x140002990`
- end: `0x140002ee5`
- name: `?QueryProviders@CVdsService@@UEAAJKPEAPEAUIEnumVdsObject@@@Z`
- size: `1365`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, unsigned int, struct IEnumVdsObject **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002990`
- `0x1400032a0`
- `0x14000f98c`
- `0x140012c48`
- `0x140013298`
- `0x14001af78`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002ada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002d3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002dfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002ea6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002ada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002d3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002dfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002ea6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002a82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002a82`
- `vdsutil!?Append@CPrvEnumObject@@QEAAJPEAUIUnknown@@@Z` at `0x140002bb7`
- `vdsutil!?Append@CPrvEnumObject@@QEAAJPEAUIUnknown@@@Z` at `0x140002c29`
- `vdsutil!?Append@CPrvEnumObject@@QEAAJPEAUIUnknown@@@Z` at `0x140002c9b`
- `vdsutil!?Append@CPrvEnumObject@@QEAAJPEAUIUnknown@@@Z` at `0x140002bb7`
- `vdsutil!?Append@CPrvEnumObject@@QEAAJPEAUIUnknown@@@Z` at `0x140002c29`
- `vdsutil!?Append@CPrvEnumObject@@QEAAJPEAUIUnknown@@@Z` at `0x140002c9b`
- `vdsutil!?Clear@CPrvEnumObject@@QEAAXXZ` at `0x140002cb6`
- `vdsutil!?Clear@CPrvEnumObject@@QEAAXXZ` at `0x140002cb6`
- `vdsutil!VdsTraceEx` at `0x1400029ee`
- `vdsutil!VdsTraceEx` at `0x140002a26`
- `vdsutil!VdsTraceEx` at `0x140002d1c`
- `vdsutil!VdsTraceEx` at `0x140002db5`
- `vdsutil!VdsTraceEx` at `0x1400029ee`
- `vdsutil!VdsTraceEx` at `0x140002a26`
- `vdsutil!VdsTraceEx` at `0x140002d1c`
- `vdsutil!VdsTraceEx` at `0x140002db5`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002b72`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002be4`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002c56`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002b72`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002be4`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002c56`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002b83`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002bf5`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002c67`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002b83`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002bf5`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140002c67`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140002bab`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140002c1d`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140002c8f`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140002bab`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140002c1d`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140002c8f`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140002bcb`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140002c39`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140002cab`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140002bcb`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140002c39`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140002cab`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400029cc`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002a9d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002b16`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002d76`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400029cc`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002a9d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002b16`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140002d76`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400029f9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002a31`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002a64`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002aba`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002ae5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002b3e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002cd1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002cf7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002d49`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002dc0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002e08`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002e6e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002eb1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400029f9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002a31`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002a64`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002aba`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002ae5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002b3e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002cd1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002cf7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002d49`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002dc0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002e08`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002e6e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002eb1`

## string_xrefs

- `0x1400029bc`: `CVdsService::QueryProviders()`
- `0x140002a8d`: `VdsCreateInstance() (2)`
- `0x140002d0e`: `CVdsService::QueryProviders, 3, hr=%lX`
- `0x140002b06`: `CVdsService::InternalQueryProviders()`
- `0x1400029e0`: `CVdsService::QueryProviders, 1`
- `0x140002a18`: `CVdsService::QueryProviders, 2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CVdsService::QueryProviders(CVdsService *this, int a2, struct IEnumVdsObject **a3)
{
  int v7; // ebx
  _DWORD *Instance; // rsi
  CPrvEnumObject *v9; // rdi
  CPrvEnumObject *v10; // r12
  int v11; // ebx
  unsigned int v12; // r14d
  struct IUnknown *EntryPointer; // rax
  struct IUnknown *v14; // rax
  struct IUnknown *v15; // rax
  int v16; // eax
  unsigned int v17; // ebx
  CPrvEnumObject *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rcx
  _DWORD *v21; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v22[16]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE Buf1[16]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v24[24]; // [rsp+58h] [rbp-21h] BYREF
  __int128 Buf2; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v26[80]; // [rsp+80h] [rbp+7h] BYREF
  CPrvEnumObject *v27; // [rsp+F0h] [rbp+77h] BYREF
  CPrvEnumObject *v28; // [rsp+F8h] [rbp+7Fh] BYREF

  v27 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v22, 0x5Eu, "CVdsService::QueryProviders()");
  *a3 = 0;
  if ( (a2 & 0xFFFFFFF8) != 0 )
  {
    VdsTraceEx(94, 0, "CVdsService::QueryProviders, 1");
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
    return 2147755372LL;
  }
  if ( !a2 )
  {
    VdsTraceEx(94, 0, "CVdsService::QueryProviders, 2");
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
    return 2147755372LL;
  }
  v7 = (*(__int64 (__fastcall **)(CVdsService *))(*(_QWORD *)this + 32LL))(this);
  if ( v7 < 0 )
  {
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
    return (unsigned int)v7;
  }
  EnterCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)Buf1, 0x5Eu, "VdsCreateInstance() (2)");
  Instance = VdsCreateInstance(0, VDS_OT_ENUM, 0);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)Buf1);
  v21 = Instance;
  if ( !Instance )
  {
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v21);
    LeaveCriticalSection(&g_GlobalCriticalSection);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
    return 2147942414LL;
  }
  Instance[23] = 1;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v24, 0x5Eu, "CVdsService::InternalQueryProviders()");
  v9 = 0;
  v27 = 0;
  v28 = 0;
  ATL::CComObject<CPrvEnumObject>::CreateInstance(&v28);
  v10 = v28;
  if ( !v28 )
  {
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
    v11 = -2147024882;
    v12 = -2147024882;
LABEL_29:
    VdsTraceEx(94, 0, "CVdsService::QueryProviders, 3, hr=%lX", v11);
    if ( !v11 )
      v12 = -2147212216;
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v21);
    LeaveCriticalSection(&g_GlobalCriticalSection);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
    return v12;
  }
  (*(void (__fastcall **)(CPrvEnumObject *))(*(_QWORD *)v28 + 8LL))(v28);
  if ( (a2 & 1) != 0 )
  {
    CRtlList::Begin(CVdsService::m_lstSoftwareProviders, Buf1);
    while ( 1 )
    {
      Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v26);
      if ( !memcmp_0(Buf1, &Buf2, 0x10u) )
        break;
      EntryPointer = (struct IUnknown *)CRtlListIter::GetEntryPointer((CRtlListIter *)Buf1);
      v11 = CPrvEnumObject::Append(v10, EntryPointer);
      if ( v11 < 0 )
      {
LABEL_26:
        CPrvEnumObject::Clear(v10);
        (*(void (__fastcall **)(CPrvEnumObject *))(*(_QWORD *)v10 + 16LL))(v10);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
        goto LABEL_28;
      }
      CRtlListIter::Next((CRtlListIter *)Buf1);
    }
  }
  if ( (a2 & 2) != 0 )
  {
    CRtlList::Begin(CVdsService::m_lstHardwareProviders, Buf1);
    while ( 1 )
    {
      Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstHardwareProviders, v26);
      if ( !memcmp_0(Buf1, &Buf2, 0x10u) )
        break;
      v14 = (struct IUnknown *)CRtlListIter::GetEntryPointer((CRtlListIter *)Buf1);
      v11 = CPrvEnumObject::Append(v10, v14);
      if ( v11 < 0 )
        goto LABEL_26;
      CRtlListIter::Next((CRtlListIter *)Buf1);
    }
  }
  if ( (a2 & 4) != 0 )
  {
    CRtlList::Begin(CVdsService::m_lstVirtualDiskProviders, Buf1);
    while ( 1 )
    {
      Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstVirtualDiskProviders, v26);
      if ( !memcmp_0(Buf1, &Buf2, 0x10u) )
        break;
      v15 = (struct IUnknown *)CRtlListIter::GetEntryPointer((CRtlListIter *)Buf1);
      v11 = CPrvEnumObject::Append(v10, v15);
      if ( v11 < 0 )
        goto LABEL_26;
      CRtlListIter::Next((CRtlListIter *)Buf1);
    }
  }
  (*(void (__fastcall **)(CPrvEnumObject *))(*(_QWORD *)v10 + 40LL))(v10);
  v9 = v10;
  v27 = v10;
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
  v11 = 0;
LABEL_28:
  v12 = v11;
  if ( !v9 )
    goto LABEL_29;
  if ( v11 >= 0 )
  {
    CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)Buf1, 0x5Eu, "ConnectEnumWrapper()");
    v28 = 0;
    v16 = (**(__int64 (__fastcall ***)(CPrvEnumObject *, GUID *, CPrvEnumObject **))v9)(v9, &IID_IUnknown, &v28);
    v17 = v16;
    if ( v16 < 0 )
    {
      VdsTraceEx(94, 0, "ConnectEnumWrapper, 1, hr=%lX", v16);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)Buf1);
      VdsLogError(0xC2000009, 0, 0, v17, 0x200001Du, 0, v21);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)Instance + 16LL))(Instance);
      LeaveCriticalSection(&g_GlobalCriticalSection);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
      (*(void (__fastcall **)(CPrvEnumObject *))(*(_QWORD *)v9 + 16LL))(v9);
      return v17;
    }
    v18 = v28;
    v19 = *((_QWORD *)Instance + 8);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    *((_QWORD *)Instance + 8) = v18;
    (*(void (__fastcall **)(CVdsService *))(*(_QWORD *)this + 8LL))(this);
    v20 = *((_QWORD *)Instance + 9);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    *((_QWORD *)Instance + 9) = this;
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)Buf1);
    v12 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IEnumVdsObject **))Instance)(
            Instance,
            &IID_IEnumVdsObject,
            a3);
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)Instance + 16LL))(Instance);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
  (*(void (__fastcall **)(CPrvEnumObject *))(*(_QWORD *)v9 + 16LL))(v9);
  return v12;
}

```

## disassembly

```asm
0x140002990  mov     [rsp-8+arg_0], rbx
0x140002995  push    rbp
0x140002996  push    rsi
0x140002997  push    rdi
0x140002998  push    r12
0x14000299a  push    r13
0x14000299c  push    r14
0x14000299e  push    r15
0x1400029a0  lea     rbp, [rsp-27h]
0x1400029a5  sub     rsp, 0A0h
0x1400029ac  mov     r13, r8
0x1400029af  mov     r14d, edx
0x1400029b2  mov     r15, rcx
0x1400029b5  xor     r12d, r12d
0x1400029b8  mov     [rbp+57h+arg_10], r12
0x1400029bc  lea     r8, aCvdsserviceQue_9; "CVdsService::QueryProviders()"
0x1400029c3  mov     edx, 5Eh ; '^'
0x1400029c8  lea     rcx, [rbp+57h+var_98]
0x1400029cc  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400029d2  nop
0x1400029d3  mov     [r13+0], r12
0x1400029d7  test    r14d, 0FFFFFFF8h
0x1400029de  jz      short loc_140002A13
0x1400029e0  lea     r8, aCvdsserviceQue_18; "CVdsService::QueryProviders, 1"
0x1400029e7  xor     edx, edx
0x1400029e9  mov     ecx, 5Eh ; '^'
0x1400029ee  call    cs:__imp_VdsTraceEx
0x1400029f4  nop
0x1400029f5  lea     rcx, [rbp+57h+var_98]
0x1400029f9  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400029ff  nop
0x140002a00  lea     rcx, [rbp+57h+arg_10]
0x140002a04  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140002a09  mov     eax, 8004256Ch
0x140002a0e  jmp     loc_140002ECA
0x140002a13  test    r14d, r14d
0x140002a16  jnz     short loc_140002A4B
0x140002a18  lea     r8, aCvdsserviceQue_11; "CVdsService::QueryProviders, 2"
0x140002a1f  xor     edx, edx
0x140002a21  mov     ecx, 5Eh ; '^'
0x140002a26  call    cs:__imp_VdsTraceEx
0x140002a2c  nop
0x140002a2d  lea     rcx, [rbp+57h+var_98]
0x140002a31  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002a37  nop
0x140002a38  lea     rcx, [rbp+57h+arg_10]
0x140002a3c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140002a41  mov     eax, 8004256Ch
0x140002a46  jmp     loc_140002ECA
0x140002a4b  mov     rax, [r15]
0x140002a4e  mov     rcx, r15
0x140002a51  mov     rax, [rax+20h]
0x140002a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a5a  mov     ebx, eax
0x140002a5c  test    eax, eax
0x140002a5e  jns     short loc_140002A7B
0x140002a60  lea     rcx, [rbp+57h+var_98]
0x140002a64  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002a6a  nop
0x140002a6b  lea     rcx, [rbp+57h+arg_10]
0x140002a6f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140002a74  mov     eax, ebx
0x140002a76  jmp     loc_140002ECA
0x140002a7b  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002a82  call    cs:__imp_EnterCriticalSection
0x140002a88  nop
0x140002a89  mov     [rbp+57h+var_A0], r12
0x140002a8d  lea     r8, aVdscreateinsta_1; "VdsCreateInstance() (2)"
0x140002a94  mov     edx, 5Eh ; '^'
0x140002a99  lea     rcx, [rbp+57h+Buf1]
0x140002a9d  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140002aa3  nop
0x140002aa4  xor     r8d, r8d; struct CVdsService *
0x140002aa7  mov     edx, 65h ; 'e'; enum _VDS_OBJECT_TYPE
0x140002aac  xor     ecx, ecx; struct IUnknown *
0x140002aae  call    ?VdsCreateInstance@@YAPEAXPEAUIUnknown@@W4_VDS_OBJECT_TYPE@@PEAVCVdsService@@@Z; VdsCreateInstance(IUnknown *,_VDS_OBJECT_TYPE,CVdsService *)
0x140002ab3  mov     rsi, rax
0x140002ab6  lea     rcx, [rbp+57h+Buf1]
0x140002aba  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002ac0  mov     [rbp+57h+var_A0], rsi
0x140002ac4  test    rsi, rsi
0x140002ac7  jnz     short loc_140002AFF
0x140002ac9  lea     rcx, [rbp+57h+var_A0]
0x140002acd  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140002ad2  nop
0x140002ad3  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002ada  call    cs:__imp_LeaveCriticalSection
0x140002ae0  nop
0x140002ae1  lea     rcx, [rbp+57h+var_98]
0x140002ae5  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002aeb  nop
0x140002aec  lea     rcx, [rbp+57h+arg_10]
0x140002af0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140002af5  mov     eax, 8007000Eh
0x140002afa  jmp     loc_140002ECA
0x140002aff  mov     dword ptr [rsi+5Ch], 1
0x140002b06  lea     r8, aCvdsserviceInt_2; "CVdsService::InternalQueryProviders()"
0x140002b0d  mov     edx, 5Eh ; '^'
0x140002b12  lea     rcx, [rbp+57h+var_78]
0x140002b16  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140002b1c  nop
0x140002b1d  mov     rdi, r12
0x140002b20  mov     [rbp+57h+arg_10], r12
0x140002b24  mov     [rbp+57h+arg_18], r12
0x140002b28  lea     rcx, [rbp+57h+arg_18]
0x140002b2c  call    ?CreateInstance@?$CComObject@VCPrvEnumObject@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPrvEnumObject>::CreateInstance(ATL::CComObject<CPrvEnumObject> * *)
0x140002b31  mov     r12, [rbp+57h+arg_18]
0x140002b35  test    r12, r12
0x140002b38  jnz     short loc_140002B51
0x140002b3a  lea     rcx, [rbp+57h+var_78]
0x140002b3e  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002b44  mov     ebx, 8007000Eh
0x140002b49  mov     r14d, ebx
0x140002b4c  jmp     loc_140002D0B
0x140002b51  mov     rax, [r12]
0x140002b55  mov     rcx, r12
0x140002b58  mov     rax, [rax+8]
0x140002b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b61  test    r14b, 1
0x140002b65  jz      short loc_140002BD3
0x140002b67  lea     rdx, [rbp+57h+Buf1]
0x140002b6b  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140002b72  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x140002b78  lea     rdx, [rbp+57h+var_50]
0x140002b7c  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140002b83  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x140002b89  movups  xmm0, xmmword ptr [rax]
0x140002b8c  movaps  [rbp+57h+Buf2], xmm0
0x140002b90  mov     r8d, 10h; Size
0x140002b96  lea     rdx, [rbp+57h+Buf2]; Buf2
0x140002b9a  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140002b9e  call    memcmp_0
0x140002ba3  test    eax, eax
0x140002ba5  jz      short loc_140002BD3
0x140002ba7  lea     rcx, [rbp+57h+Buf1]
0x140002bab  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x140002bb1  mov     rdx, rax
0x140002bb4  mov     rcx, r12
0x140002bb7  call    cs:__imp_?Append@CPrvEnumObject@@QEAAJPEAUIUnknown@@@Z; CPrvEnumObject::Append(IUnknown *)
0x140002bbd  mov     ebx, eax
0x140002bbf  test    eax, eax
0x140002bc1  js      loc_140002CB3
0x140002bc7  lea     rcx, [rbp+57h+Buf1]
0x140002bcb  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x140002bd1  jmp     short loc_140002B78
0x140002bd3  test    r14b, 2
0x140002bd7  jz      short loc_140002C41
0x140002bd9  lea     rdx, [rbp+57h+Buf1]
0x140002bdd  lea     rcx, ?m_lstHardwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstHardwareProviders
0x140002be4  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x140002bea  lea     rdx, [rbp+57h+var_50]
0x140002bee  lea     rcx, ?m_lstHardwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstHardwareProviders
0x140002bf5  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x140002bfb  movups  xmm0, xmmword ptr [rax]
0x140002bfe  movaps  [rbp+57h+Buf2], xmm0
0x140002c02  mov     r8d, 10h; Size
0x140002c08  lea     rdx, [rbp+57h+Buf2]; Buf2
0x140002c0c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140002c10  call    memcmp_0
0x140002c15  test    eax, eax
0x140002c17  jz      short loc_140002C41
0x140002c19  lea     rcx, [rbp+57h+Buf1]
0x140002c1d  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x140002c23  mov     rdx, rax
0x140002c26  mov     rcx, r12
0x140002c29  call    cs:__imp_?Append@CPrvEnumObject@@QEAAJPEAUIUnknown@@@Z; CPrvEnumObject::Append(IUnknown *)
0x140002c2f  mov     ebx, eax
0x140002c31  test    eax, eax
0x140002c33  js      short loc_140002CB3
0x140002c35  lea     rcx, [rbp+57h+Buf1]
0x140002c39  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x140002c3f  jmp     short loc_140002BEA
0x140002c41  test    r14b, 4
0x140002c45  jz      loc_140002CDC
0x140002c4b  lea     rdx, [rbp+57h+Buf1]
0x140002c4f  lea     rcx, ?m_lstVirtualDiskProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstVirtualDiskProviders
0x140002c56  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x140002c5c  lea     rdx, [rbp+57h+var_50]
0x140002c60  lea     rcx, ?m_lstVirtualDiskProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstVirtualDiskProviders
0x140002c67  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x140002c6d  movups  xmm0, xmmword ptr [rax]
0x140002c70  movaps  [rbp+57h+Buf2], xmm0
0x140002c74  mov     r8d, 10h; Size
0x140002c7a  lea     rdx, [rbp+57h+Buf2]; Buf2
0x140002c7e  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140002c82  call    memcmp_0
0x140002c87  test    eax, eax
0x140002c89  jz      short loc_140002CDC
0x140002c8b  lea     rcx, [rbp+57h+Buf1]
0x140002c8f  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x140002c95  mov     rdx, rax
0x140002c98  mov     rcx, r12
0x140002c9b  call    cs:__imp_?Append@CPrvEnumObject@@QEAAJPEAUIUnknown@@@Z; CPrvEnumObject::Append(IUnknown *)
0x140002ca1  mov     ebx, eax
0x140002ca3  test    eax, eax
0x140002ca5  js      short loc_140002CB3
0x140002ca7  lea     rcx, [rbp+57h+Buf1]
0x140002cab  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x140002cb1  jmp     short loc_140002C5C
0x140002cb3  mov     rcx, r12
0x140002cb6  call    cs:__imp_?Clear@CPrvEnumObject@@QEAAXXZ; CPrvEnumObject::Clear(void)
0x140002cbc  mov     rax, [r12]
0x140002cc0  mov     rcx, r12
0x140002cc3  mov     rax, [rax+10h]
0x140002cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ccc  nop
0x140002ccd  lea     rcx, [rbp+57h+var_78]
0x140002cd1  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002cd7  xor     r12d, r12d
0x140002cda  jmp     short loc_140002D03
0x140002cdc  mov     rax, [r12]
0x140002ce0  mov     rcx, r12
0x140002ce3  mov     rax, [rax+28h]
0x140002ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cec  mov     rdi, r12
0x140002cef  mov     [rbp+57h+arg_10], r12
0x140002cf3  lea     rcx, [rbp+57h+var_78]
0x140002cf7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002cfd  xor     r12d, r12d
0x140002d00  mov     ebx, r12d
0x140002d03  mov     r14d, ebx
0x140002d06  test    rdi, rdi
0x140002d09  jnz     short loc_140002D5E
0x140002d0b  mov     r9d, ebx
0x140002d0e  lea     r8, aCvdsserviceQue_0; "CVdsService::QueryProviders, 3, hr=%lX"
0x140002d15  xor     edx, edx
0x140002d17  mov     ecx, 5Eh ; '^'
0x140002d1c  call    cs:__imp_VdsTraceEx
0x140002d22  mov     eax, 80042448h
0x140002d27  test    ebx, ebx
0x140002d29  cmovz   r14d, eax
0x140002d2d  lea     rcx, [rbp+57h+var_A0]
0x140002d31  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140002d36  nop
0x140002d37  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002d3e  call    cs:__imp_LeaveCriticalSection
0x140002d44  nop
0x140002d45  lea     rcx, [rbp+57h+var_98]
0x140002d49  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002d4f  nop
0x140002d50  lea     rcx, [rbp+57h+arg_10]
0x140002d54  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140002d59  jmp     loc_140002EC7
0x140002d5e  test    ebx, ebx
0x140002d60  js      loc_140002E8F
0x140002d66  lea     r8, aConnectenumwra_0; "ConnectEnumWrapper()"
0x140002d6d  mov     edx, 5Eh ; '^'
0x140002d72  lea     rcx, [rbp+57h+Buf1]
0x140002d76  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140002d7c  nop
0x140002d7d  mov     [rbp+57h+arg_18], r12
0x140002d81  mov     rax, [rdi]
0x140002d84  lea     r8, [rbp+57h+arg_18]
0x140002d88  lea     rdx, IID_IUnknown
0x140002d8f  mov     rcx, rdi
0x140002d92  mov     rax, [rax]
0x140002d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d9a  mov     ebx, eax
0x140002d9c  test    eax, eax
0x140002d9e  jns     loc_140002E25
0x140002da4  mov     r9d, eax
0x140002da7  lea     r8, aConnectenumwra; "ConnectEnumWrapper, 1, hr=%lX"
0x140002dae  xor     edx, edx
0x140002db0  mov     ecx, 5Eh ; '^'
0x140002db5  call    cs:__imp_VdsTraceEx
0x140002dbb  nop
0x140002dbc  lea     rcx, [rbp+57h+Buf1]
0x140002dc0  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002dc6  mov     [rsp+0D0h+var_A8], r12; unsigned __int16 *
0x140002dcb  mov     [rsp+0D0h+var_B0], 200001Dh; unsigned int
0x140002dd3  mov     r9d, ebx; unsigned int
0x140002dd6  xor     r8d, r8d; void *
0x140002dd9  xor     edx, edx; unsigned int
0x140002ddb  mov     ecx, 0C2000009h; unsigned int
0x140002de0  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140002de5  nop
0x140002de6  mov     rax, [rsi]
0x140002de9  mov     rcx, rsi
0x140002dec  mov     rax, [rax+10h]
0x140002df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002df5  nop
0x140002df6  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140002dfd  call    cs:__imp_LeaveCriticalSection
0x140002e03  nop
0x140002e04  lea     rcx, [rbp+57h+var_98]
0x140002e08  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140002e0e  nop
0x140002e0f  mov     rax, [rdi]
0x140002e12  mov     rcx, rdi
0x140002e15  mov     rax, [rax+10h]
0x140002e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e1e  mov     eax, ebx
0x140002e20  jmp     loc_140002ECA
0x140002e25  mov     rbx, [rbp+57h+arg_18]
0x140002e29  mov     rcx, [rsi+40h]
0x140002e2d  test    rcx, rcx
0x140002e30  jz      short loc_140002E3E
0x140002e32  mov     rax, [rcx]
0x140002e35  mov     rax, [rax+10h]
0x140002e39  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
