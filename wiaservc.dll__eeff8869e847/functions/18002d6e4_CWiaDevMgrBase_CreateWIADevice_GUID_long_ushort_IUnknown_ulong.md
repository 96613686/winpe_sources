# CWiaDevMgrBase::CreateWIADevice(_GUID,long,ushort *,IUnknown * *,ulong)

- ea: `0x18002d6e4`
- end: `0x18002d9d3`
- name: `?CreateWIADevice@CWiaDevMgrBase@@IEAAJU_GUID@@JPEAGPEAPEAUIUnknown@@K@Z`
- size: `751`
- prototype: `__int64 __fastcall(CWiaDevMgrBase *this, struct _GUID *, int, unsigned __int16 *, struct IUnknown **, unsigned int)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005ac00`
- `0x18005b560`

## callees

- `0x18000645c`
- `0x1800085b0`
- `0x18000a974`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x18000fc60`
- `0x180011a94`
- `0x1800174c4`
- `0x18002d6e4`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x1800552bc`
- `0x180056aa4`
- `0x1800775fc`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002d9a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d9a0`

## string_xrefs

- `0x18002d78c`: `invalid CLASSID`
- `0x18002d7ae`: `invalid CLASSID`
- `0x18002d716`: `CWiaDevMgrBase::CreateWIADevice`
- `0x18002d8a1`: `could not create device on (%ws) because we could not find the internal DeviceListManager`
- `0x18002d8c6`: `could not create device on (%ws) because we could not find the internal DeviceListManager`

## pseudocode

```c
__int64 __fastcall CWiaDevMgrBase::CreateWIADevice(
        CWiaDevMgrBase *this,
        struct _GUID *a2,
        int a3,
        unsigned __int16 *a4,
        struct IUnknown **a5,
        unsigned int a6)
{
  struct tagWiaTraceData_Type *v9; // rax
  char *v10; // rdx
  unsigned int v11; // r8d
  CWiaDevMgrBase *v12; // rcx
  char *v13; // rbx
  void *v14; // rdx
  void *v15; // rax
  int v16; // edx
  int v17; // ecx
  char *v18; // rbx
  void *v19; // rdx
  DeviceListManager *v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // r8
  char *v23; // rcx
  CWiaDevMgrBase *v24; // rcx
  char *v25; // rbx
  void *v26; // rdx
  void *v27; // rax
  int v28; // edx
  int v29; // ecx
  unsigned int MatchingDevice; // ebx
  char *v31; // rbx
  void *v32; // rdx
  void *v33; // rax
  int v34; // edx
  int v35; // ecx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  struct IWiaPropertyStorage *v38[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID v39; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v40[80]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v41[38]; // [rsp+A0h] [rbp-60h] BYREF

  v9 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaDevMgrBase::CreateWIADevice");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v40, v10, v11, "CWiaDevMgrBase::CreateWIADevice", lpMem, v9);
  v38[0] = 0;
  if ( !a4 || !a5 )
  {
    v18 = (char *)WiaTrace_TraceLog("invalid arguments");
    WriteDbgTraceErrorWI("CWiaDevMgrBase::CreateWIADevice", v18);
    WiaTrcLib::Free((WiaTrcLib *)v18, v19);
    v15 = (void *)WiaTrace_Trace("invalid arguments");
    goto LABEL_9;
  }
  if ( memcmp_0(a2, &CLSID_WiaDevMgr, 0x10u) && memcmp_0(a2, &CLSID_WiaDevMgr2, 0x10u) )
  {
    v13 = (char *)WiaTrace_TraceLog("invalid CLASSID");
    WriteDbgTraceErrorWI("CWiaDevMgrBase::CreateWIADevice", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v15 = (void *)WiaTrace_Trace("invalid CLASSID");
LABEL_9:
    WiaTrace_ProcessTrace_Ex(v17, v16, (int)"CWiaDevMgrBase::CreateWIADevice", 1, v15);
    goto LABEL_10;
  }
  *a5 = 0;
  if ( !CWiaDevMgrBase::FindMatchingDevice(v12, a4, v38, a6) )
  {
LABEL_16:
    v39 = *a2;
    MatchingDevice = CreateLocalDevice(&v39, a4, v38[0], a3, a5);
    goto LABEL_17;
  }
LABEL_10:
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)&v39);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v41, L"DeviceListManager");
  v20 = (DeviceListManager *)ServiceComponentHolder::Get<DeviceListManager>(&v39, v41);
  v41[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v41);
  v41[34] = 0;
  if ( v20 )
  {
    DeviceListManager::Enumerate(v20, 1);
    DeviceListManager::LoadUnloadDrivers(v20, v21, v22);
    v23 = (char *)v20 + *(int *)(*((_QWORD *)v20 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  else
  {
    v25 = (char *)WiaTrace_TraceLog("could not create device on (%ws) because we could not find the internal DeviceListManager");
    WriteDbgTraceErrorWI("CWiaDevMgrBase::CreateWIADevice", v25);
    WiaTrcLib::Free((WiaTrcLib *)v25, v26);
    v27 = (void *)WiaTrace_Trace(
                    "could not create device on (%ws) because we could not find the internal DeviceListManager",
                    a4);
    WiaTrace_ProcessTrace_Ex(v29, v28, (int)"CWiaDevMgrBase::CreateWIADevice", 1, v27);
  }
  MatchingDevice = CWiaDevMgrBase::FindMatchingDevice(v24, a4, v38, a6);
  if ( MatchingDevice )
  {
    v31 = (char *)WiaTrace_TraceLog("Failed to find device: %ls");
    WriteDbgTraceErrorWI("CWiaDevMgrBase::CreateWIADevice", v31);
    WiaTrcLib::Free((WiaTrcLib *)v31, v32);
    v33 = (void *)WiaTrace_Trace("Failed to find device: %ls", a4);
    WiaTrace_ProcessTrace_Ex(v35, v34, (int)"CWiaDevMgrBase::CreateWIADevice", 1, v33);
    MatchingDevice = -2145320939;
  }
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)&v39);
  if ( !MatchingDevice )
    goto LABEL_16;
LABEL_17:
  if ( v38[0] )
  {
    ((void (__fastcall *)(struct IWiaPropertyStorage *))v38[0]->lpVtbl->Release)(v38[0]);
    v38[0] = 0;
  }
  SysFreeString(0);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v40);
  return MatchingDevice;
}

```

## disassembly

```asm
0x18002d6e4  push    rbp
0x18002d6e6  push    rbx
0x18002d6e7  push    rsi
0x18002d6e8  push    rdi
0x18002d6e9  push    r13
0x18002d6eb  push    r14
0x18002d6ed  push    r15
0x18002d6ef  lea     rbp, [rsp-0E0h]
0x18002d6f7  sub     rsp, 1E0h
0x18002d6fe  mov     rax, cs:__security_cookie
0x18002d705  xor     rax, rsp
0x18002d708  mov     [rbp+110h+var_40], rax
0x18002d70f  mov     rsi, [rbp+110h+arg_20]
0x18002d716  lea     r13, aCwiadevmgrbase_1; "CWiaDevMgrBase::CreateWIADevice"
0x18002d71d  mov     rcx, r13
0x18002d720  mov     rdi, r9
0x18002d723  mov     r15d, r8d
0x18002d726  mov     r14, rdx
0x18002d729  call    WiaTrace_Trace
0x18002d72e  mov     r9, r13; char *
0x18002d731  mov     [rsp+210h+var_1E8], rax; struct tagWiaTraceData_Type *
0x18002d736  lea     rcx, [rsp+210h+var_1C0]; this
0x18002d73b  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18002d740  mov     [rsp+210h+var_1E0], 0
0x18002d749  test    rdi, rdi
0x18002d74c  jz      loc_18002D7DC
0x18002d752  test    rsi, rsi
0x18002d755  jz      loc_18002D7DC
0x18002d75b  mov     ebx, 10h
0x18002d760  lea     rdx, CLSID_WiaDevMgr; Buf2
0x18002d767  mov     r8d, ebx; Size
0x18002d76a  mov     rcx, r14; Buf1
0x18002d76d  call    memcmp_0
0x18002d772  test    eax, eax
0x18002d774  jz      short loc_18002D7B7
0x18002d776  mov     r8d, ebx; Size
0x18002d779  lea     rdx, CLSID_WiaDevMgr2; Buf2
0x18002d780  mov     rcx, r14; Buf1
0x18002d783  call    memcmp_0
0x18002d788  test    eax, eax
0x18002d78a  jz      short loc_18002D7B7
0x18002d78c  lea     rcx, aInvalidClassid; "invalid CLASSID"
0x18002d793  call    WiaTrace_TraceLog
0x18002d798  mov     rdx, rax; char *
0x18002d79b  mov     rcx, r13; char *
0x18002d79e  mov     rbx, rax
0x18002d7a1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d7a6  mov     rcx, rbx; this
0x18002d7a9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d7ae  lea     rcx, aInvalidClassid; "invalid CLASSID"
0x18002d7b5  jmp     short loc_18002D805
0x18002d7b7  mov     r9d, [rbp+110h+arg_28]; unsigned int
0x18002d7be  lea     r8, [rsp+210h+var_1E0]; struct IWiaPropertyStorage **
0x18002d7c3  mov     rdx, rdi; unsigned __int16 *
0x18002d7c6  mov     qword ptr [rsi], 0
0x18002d7cd  call    ?FindMatchingDevice@CWiaDevMgrBase@@IEAAJPEAGPEAPEAUIWiaPropertyStorage@@K@Z; CWiaDevMgrBase::FindMatchingDevice(ushort *,IWiaPropertyStorage * *,ulong)
0x18002d7d2  test    eax, eax
0x18002d7d4  jz      loc_18002D959
0x18002d7da  jmp     short loc_18002D81D
0x18002d7dc  lea     rcx, aInvalidArgumen_1; "invalid arguments"
0x18002d7e3  call    WiaTrace_TraceLog
0x18002d7e8  mov     rdx, rax; char *
0x18002d7eb  mov     rcx, r13; char *
0x18002d7ee  mov     rbx, rax
0x18002d7f1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d7f6  mov     rcx, rbx; this
0x18002d7f9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d7fe  lea     rcx, aInvalidArgumen_1; "invalid arguments"
0x18002d805  call    WiaTrace_Trace
0x18002d80a  mov     r9d, 1; int
0x18002d810  mov     [rsp+210h+lpMem], rax; lpMem
0x18002d815  mov     r8, r13; int
0x18002d818  call    WiaTrace_ProcessTrace_Ex
0x18002d81d  lea     rcx, [rsp+210h+var_1D0]; this
0x18002d822  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18002d827  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x18002d82e  lea     rcx, [rbp+110h+var_170]
0x18002d832  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18002d837  lea     rdx, [rbp+110h+var_170]
0x18002d83b  lea     rcx, [rsp+210h+var_1D0]
0x18002d840  call    ??$Get@VDeviceListManager@@@ServiceComponentHolder@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x18002d845  mov     rbx, rax
0x18002d848  lea     rcx, [rbp+110h+var_170]
0x18002d84c  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18002d853  mov     [rbp+110h+var_170], rax
0x18002d857  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18002d85c  mov     [rbp+110h+var_60], 0
0x18002d867  test    rbx, rbx
0x18002d86a  jz      short loc_18002D89E
0x18002d86c  mov     edx, 1; int
0x18002d871  mov     rcx, rbx; this
0x18002d874  call    ?Enumerate@DeviceListManager@@QEAAJJ@Z; DeviceListManager::Enumerate(long)
0x18002d879  mov     rcx, rbx; this
0x18002d87c  call    ?LoadUnloadDrivers@DeviceListManager@@QEAAJJ@Z; DeviceListManager::LoadUnloadDrivers(long)
0x18002d881  mov     rcx, [rbx+8]
0x18002d885  movsxd  rcx, dword ptr [rcx+4]
0x18002d889  add     rcx, 8
0x18002d88d  add     rcx, rbx
0x18002d890  mov     rax, [rcx]
0x18002d893  mov     rax, [rax+10h]
0x18002d897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d89c  jmp     short loc_18002D8E5
0x18002d89e  mov     rdx, rdi
0x18002d8a1  lea     rcx, aCouldNotCreate; "could not create device on (%ws) becaus"...
0x18002d8a8  call    WiaTrace_TraceLog
0x18002d8ad  mov     rdx, rax; char *
0x18002d8b0  mov     rcx, r13; char *
0x18002d8b3  mov     rbx, rax
0x18002d8b6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d8bb  mov     rcx, rbx; this
0x18002d8be  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d8c3  mov     rdx, rdi
0x18002d8c6  lea     rcx, aCouldNotCreate; "could not create device on (%ws) becaus"...
0x18002d8cd  call    WiaTrace_Trace
0x18002d8d2  mov     r9d, 1; int
0x18002d8d8  mov     [rsp+210h+lpMem], rax; lpMem
0x18002d8dd  mov     r8, r13; int
0x18002d8e0  call    WiaTrace_ProcessTrace_Ex
0x18002d8e5  mov     r9d, [rbp+110h+arg_28]; unsigned int
0x18002d8ec  lea     r8, [rsp+210h+var_1E0]; struct IWiaPropertyStorage **
0x18002d8f1  mov     rdx, rdi; unsigned __int16 *
0x18002d8f4  call    ?FindMatchingDevice@CWiaDevMgrBase@@IEAAJPEAGPEAPEAUIWiaPropertyStorage@@K@Z; CWiaDevMgrBase::FindMatchingDevice(ushort *,IWiaPropertyStorage * *,ulong)
0x18002d8f9  mov     ebx, eax
0x18002d8fb  test    eax, eax
0x18002d8fd  jz      short loc_18002D94B
0x18002d8ff  mov     rdx, rdi
0x18002d902  lea     rcx, aFailedToFindDe; "Failed to find device: %ls"
0x18002d909  call    WiaTrace_TraceLog
0x18002d90e  mov     rdx, rax; char *
0x18002d911  mov     rcx, r13; char *
0x18002d914  mov     rbx, rax
0x18002d917  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d91c  mov     rcx, rbx; this
0x18002d91f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d924  mov     rdx, rdi
0x18002d927  lea     rcx, aFailedToFindDe; "Failed to find device: %ls"
0x18002d92e  call    WiaTrace_Trace
0x18002d933  mov     r9d, 1; int
0x18002d939  mov     [rsp+210h+lpMem], rax; lpMem
0x18002d93e  mov     r8, r13; int
0x18002d941  call    WiaTrace_ProcessTrace_Ex
0x18002d946  mov     ebx, 80210015h
0x18002d94b  lea     rcx, [rsp+210h+var_1D0]; this
0x18002d950  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x18002d955  test    ebx, ebx
0x18002d957  jnz     short loc_18002D97F
0x18002d959  movaps  xmm0, xmmword ptr [r14]
0x18002d95d  lea     rcx, [rsp+210h+var_1D0]; struct _GUID *
0x18002d962  mov     r8, [rsp+210h+var_1E0]; struct IWiaPropertyStorage *
0x18002d967  mov     r9d, r15d; int
0x18002d96a  mov     rdx, rdi; unsigned __int16 *
0x18002d96d  movdqa  xmmword ptr [rsp+210h+var_1D0.Data1], xmm0
0x18002d973  mov     [rsp+210h+lpMem], rsi; struct IUnknown **
0x18002d978  call    ?CreateLocalDevice@@YAJU_GUID@@PEAGPEAUIWiaPropertyStorage@@JPEAPEAUIUnknown@@@Z; CreateLocalDevice(_GUID,ushort *,IWiaPropertyStorage *,long,IUnknown * *)
0x18002d97d  mov     ebx, eax
0x18002d97f  mov     rcx, [rsp+210h+var_1E0]
0x18002d984  test    rcx, rcx
0x18002d987  jz      short loc_18002D99E
0x18002d989  mov     rax, [rcx]
0x18002d98c  mov     rax, [rax+10h]
0x18002d990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d995  mov     [rsp+210h+var_1E0], 0
0x18002d99e  xor     ecx, ecx; bstrString
0x18002d9a0  call    cs:__imp_SysFreeString
0x18002d9a6  lea     rcx, [rsp+210h+var_1C0]; this
0x18002d9ab  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18002d9b0  mov     eax, ebx
0x18002d9b2  mov     rcx, [rbp+110h+var_40]
0x18002d9b9  xor     rcx, rsp; StackCookie
0x18002d9bc  call    __security_check_cookie
0x18002d9c1  add     rsp, 1E0h
0x18002d9c8  pop     r15
0x18002d9ca  pop     r14
0x18002d9cc  pop     r13
0x18002d9ce  pop     rdi
0x18002d9cf  pop     rsi
0x18002d9d0  pop     rbx
0x18002d9d1  pop     rbp
0x18002d9d2  retn
```
