# WiaService::Initialize(long)

- ea: `0x1800459d8`
- end: `0x180045cce`
- name: `?Initialize@WiaService@@QEAAJJ@Z`
- size: `758`
- prototype: `__int64 __fastcall(WiaService *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038de0`

## callees

- `0x1800028f4`
- `0x18000645c`
- `0x180006b88`
- `0x1800085b0`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000f4fc`
- `0x18000fc60`
- `0x180011a94`
- `0x1800150c8`
- `0x1800174c4`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x18003b438`
- `0x1800459d8`
- `0x180050c60`
- `0x180078010`

## string_xrefs

- `0x180045a31`: `WiaService`
- `0x180045a89`: `ServiceStatus`
- `0x180045ac3`: `Failed to get a reference to ServiceStatus object!`
- `0x180045ae5`: `Failed to get a reference to ServiceStatus object!`
- `0x180045a72`: `WiaService::Initialize`
- `0x180045c22`: `WiaService::Initialize`
- `0x180045b82`: `The WiaService object could not find the DeviceListManager`
- `0x180045ba7`: `The WiaService object could not find the DeviceListManager`
- `0x180045c16`: `Failed to InitializeNTSecurity for the STI RPC Server...aborting service initialization`
- `0x180045c3f`: `Failed to InitializeNTSecurity for the STI RPC Server...aborting service initialization`
- `0x180045c66`: `Internal errors encountered during initialization, cannot start the WIA Service`
- `0x180045c88`: `Internal errors encountered during initialization, cannot start the WIA Service`

## pseudocode

```c
__int64 __fastcall WiaService::Initialize(WiaService *this)
{
  char *v2; // rbx
  int v3; // edi
  char *v4; // rbx
  void *v5; // rdx
  void *lpMem; // rax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rax
  DeviceListManager *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  CEventNotifier *v13; // rcx
  char *v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  void *v17; // rax
  int v18; // edx
  int v19; // ecx
  char *v20; // rbx
  void *v21; // rdx
  char *v22; // rbx
  void *v23; // rdx
  void *v24; // rax
  int v25; // edx
  int v26; // ecx
  char *v27; // rbx
  void *v28; // rdx
  void *v29; // rax
  int v30; // edx
  int v31; // ecx
  _BYTE v33[16]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v34[38]; // [rsp+40h] [rbp-C0h] BYREF

  if ( !(unsigned int)InitializeNTSecurity() )
  {
    v22 = (char *)WiaTrace_TraceLog("Failed to InitializeNTSecurity for the STI RPC Server...aborting service initialization");
    WriteDbgTraceErrorWI("WiaService::Initialize", v22);
    WiaTrcLib::Free((WiaTrcLib *)v22, v23);
    v24 = (void *)WiaTrace_Trace("Failed to InitializeNTSecurity for the STI RPC Server...aborting service initialization");
    WiaTrace_ProcessTrace_Ex(v26, v25, (int)"WiaService::Initialize", 1, v24);
    v3 = -2147418113;
    goto LABEL_17;
  }
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v33);
  if ( this )
    v2 = (char *)this + *(int *)(*(_QWORD *)this + 4LL);
  else
    v2 = 0;
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v34, L"WiaService");
  ServiceComponentHolder::Set(v33, v34, v2, this);
  v34[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v34);
  v3 = DoGlobalInit();
  if ( v3 < 0 )
    goto LABEL_12;
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v34, L"ServiceStatus");
  *((_QWORD *)this + 4) = ServiceComponentHolder::Get<ServiceStatus>(v33, v34);
  v34[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v34);
  if ( !*((_QWORD *)this + 4) )
  {
    v4 = (char *)WiaTrace_TraceLog("Failed to get a reference to ServiceStatus object!");
    WriteDbgTraceErrorWI("WiaService::Initialize", v4);
    WiaTrcLib::Free((WiaTrcLib *)v4, v5);
    lpMem = (void *)WiaTrace_Trace("Failed to get a reference to ServiceStatus object!");
    WiaTrace_ProcessTrace_Ex(v8, v7, (int)"WiaService::Initialize", 1, lpMem);
    v3 = -2147467259;
  }
  if ( v3 < 0 )
  {
LABEL_12:
    v20 = (char *)WiaTrace_TraceLogWithSubComp(1, "Global initialization failed");
    WriteDbgTraceWarningWI("WiaService::Initialize", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v17 = (void *)WiaTrace_TraceWithSubComp(1, "Global initialization failed");
  }
  else
  {
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v34, L"DeviceListManager");
    v9 = ServiceComponentHolder::Get<DeviceListManager>(v33, v34);
    v34[0] = &CSimpleStringBase<unsigned short>::`vftable';
    v10 = (DeviceListManager *)v9;
    CSimpleStringBase<unsigned short>::DeleteStorage(v34);
    v34[34] = 0;
    if ( v10 )
    {
      DeviceListManager::Enumerate(v10, 1);
      DeviceListManager::LoadUnloadDrivers(v10, v11, v12);
      CEventNotifier::RestoreAllPersistentCBs(v13);
      v14 = (char *)v10 + *(int *)(*((_QWORD *)v10 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))(v14);
      goto LABEL_14;
    }
    v15 = (char *)WiaTrace_TraceLogWithSubComp(1, "The WiaService object could not find the DeviceListManager");
    WriteDbgTraceWarningWI("WiaService::Initialize", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v17 = (void *)WiaTrace_TraceWithSubComp(1, "The WiaService object could not find the DeviceListManager");
  }
  WiaTrace_ProcessTrace_Ex(v19, v18, (int)"WiaService::Initialize", 2, v17);
  v3 = -2147418113;
LABEL_14:
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v33);
  if ( v3 < 0 )
  {
LABEL_17:
    v27 = (char *)WiaTrace_TraceLog("Internal errors encountered during initialization, cannot start the WIA Service");
    WriteDbgTraceErrorWI("WiaService::Initialize", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v29 = (void *)WiaTrace_Trace("Internal errors encountered during initialization, cannot start the WIA Service");
    WiaTrace_ProcessTrace_Ex(v31, v30, (int)"WiaService::Initialize", 1, v29);
    return (unsigned int)v3;
  }
  *((_DWORD *)this + 2) = 1231255123;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800459d8  mov     [rsp-8+arg_8], rbx
0x1800459dd  mov     [rsp-8+arg_10], rsi
0x1800459e2  push    rbp
0x1800459e3  push    rdi
0x1800459e4  push    r12
0x1800459e6  push    r14
0x1800459e8  push    r15
0x1800459ea  lea     rbp, [rsp-80h]
0x1800459ef  sub     rsp, 180h
0x1800459f6  mov     rax, cs:__security_cookie
0x1800459fd  xor     rax, rsp
0x180045a00  mov     [rbp+0A0h+var_30], rax
0x180045a04  mov     rsi, rcx
0x180045a07  call    ?InitializeNTSecurity@@YAHXZ; InitializeNTSecurity(void)
0x180045a0c  test    eax, eax
0x180045a0e  jz      loc_180045C16
0x180045a14  lea     rcx, [rsp+1A0h+var_170]; this
0x180045a19  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x180045a1e  test    rsi, rsi
0x180045a21  jnz     short loc_180045A27
0x180045a23  xor     ebx, ebx
0x180045a25  jmp     short loc_180045A31
0x180045a27  mov     rax, [rsi]
0x180045a2a  movsxd  rbx, dword ptr [rax+4]
0x180045a2e  add     rbx, rsi
0x180045a31  lea     rdx, aWiaservice; "WiaService"
0x180045a38  lea     rcx, [rsp+1A0h+var_160]
0x180045a3d  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180045a42  mov     r9, rsi
0x180045a45  lea     rdx, [rsp+1A0h+var_160]
0x180045a4a  mov     r8, rbx
0x180045a4d  lea     rcx, [rsp+1A0h+var_170]
0x180045a52  call    ?Set@ServiceComponentHolder@@QEAAXAEBV?$CSimpleStringBase@G@@PEAVCSimpleRefCount@@PEAX@Z; ServiceComponentHolder::Set(CSimpleStringBase<ushort> const &,CSimpleRefCount *,void *)
0x180045a57  lea     r12, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180045a5e  lea     rcx, [rsp+1A0h+var_160]
0x180045a63  mov     [rsp+1A0h+var_160], r12
0x180045a68  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180045a6d  call    ?DoGlobalInit@@YAJXZ; DoGlobalInit(void)
0x180045a72  lea     r14, aWiaserviceInit; "WiaService::Initialize"
0x180045a79  mov     edi, eax
0x180045a7b  mov     r15d, 1
0x180045a81  test    eax, eax
0x180045a83  js      loc_180045BB0
0x180045a89  lea     rdx, aServicestatus; "ServiceStatus"
0x180045a90  lea     rcx, [rsp+1A0h+var_160]
0x180045a95  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180045a9a  lea     rdx, [rsp+1A0h+var_160]
0x180045a9f  lea     rcx, [rsp+1A0h+var_170]
0x180045aa4  call    ??$Get@VServiceStatus@@@ServiceComponentHolder@@QEAAPEAVServiceStatus@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<ServiceStatus>(CSimpleStringBase<ushort> const &)
0x180045aa9  lea     rcx, [rsp+1A0h+var_160]
0x180045aae  mov     [rsi+20h], rax
0x180045ab2  mov     [rsp+1A0h+var_160], r12
0x180045ab7  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180045abc  cmp     qword ptr [rsi+20h], 0
0x180045ac1  jnz     short loc_180045B06
0x180045ac3  lea     rcx, aFailedToGetARe; "Failed to get a reference to ServiceSta"...
0x180045aca  call    WiaTrace_TraceLog
0x180045acf  mov     rdx, rax; char *
0x180045ad2  mov     rcx, r14; char *
0x180045ad5  mov     rbx, rax
0x180045ad8  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180045add  mov     rcx, rbx; this
0x180045ae0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180045ae5  lea     rcx, aFailedToGetARe; "Failed to get a reference to ServiceSta"...
0x180045aec  call    WiaTrace_Trace
0x180045af1  mov     r9d, r15d; int
0x180045af4  mov     [rsp+1A0h+lpMem], rax; lpMem
0x180045af9  mov     r8, r14; int
0x180045afc  call    WiaTrace_ProcessTrace_Ex
0x180045b01  mov     edi, 80004005h
0x180045b06  test    edi, edi
0x180045b08  js      loc_180045BB0
0x180045b0e  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x180045b15  lea     rcx, [rsp+1A0h+var_160]
0x180045b1a  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180045b1f  lea     rdx, [rsp+1A0h+var_160]
0x180045b24  lea     rcx, [rsp+1A0h+var_170]
0x180045b29  call    ??$Get@VDeviceListManager@@@ServiceComponentHolder@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x180045b2e  lea     rcx, [rsp+1A0h+var_160]
0x180045b33  mov     [rsp+1A0h+var_160], r12
0x180045b38  mov     rbx, rax
0x180045b3b  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180045b40  mov     [rbp+0A0h+var_50], 0
0x180045b48  test    rbx, rbx
0x180045b4b  jz      short loc_180045B82
0x180045b4d  mov     edx, r15d; int
0x180045b50  mov     rcx, rbx; this
0x180045b53  call    ?Enumerate@DeviceListManager@@QEAAJJ@Z; DeviceListManager::Enumerate(long)
0x180045b58  mov     rcx, rbx; this
0x180045b5b  call    ?LoadUnloadDrivers@DeviceListManager@@QEAAJJ@Z; DeviceListManager::LoadUnloadDrivers(long)
0x180045b60  call    ?RestoreAllPersistentCBs@CEventNotifier@@QEAAJXZ; CEventNotifier::RestoreAllPersistentCBs(void)
0x180045b65  mov     rcx, [rbx+8]
0x180045b69  movsxd  rcx, dword ptr [rcx+4]
0x180045b6d  add     rcx, 8
0x180045b71  add     rcx, rbx
0x180045b74  mov     rax, [rcx]
0x180045b77  mov     rax, [rax+10h]
0x180045b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b80  jmp     short loc_180045BFC
0x180045b82  lea     rdx, aTheWiaserviceO_0; "The WiaService object could not find th"...
0x180045b89  mov     ecx, r15d
0x180045b8c  call    WiaTrace_TraceLogWithSubComp
0x180045b91  mov     rdx, rax; char *
0x180045b94  mov     rcx, r14; char *
0x180045b97  mov     rbx, rax
0x180045b9a  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180045b9f  mov     rcx, rbx; this
0x180045ba2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180045ba7  lea     rdx, aTheWiaserviceO_0; "The WiaService object could not find th"...
0x180045bae  jmp     short loc_180045BDC
0x180045bb0  lea     rdx, aGlobalInitiali; "Global initialization failed"
0x180045bb7  mov     ecx, r15d
0x180045bba  call    WiaTrace_TraceLogWithSubComp
0x180045bbf  mov     rdx, rax; char *
0x180045bc2  mov     rcx, r14; char *
0x180045bc5  mov     rbx, rax
0x180045bc8  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180045bcd  mov     rcx, rbx; this
0x180045bd0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180045bd5  lea     rdx, aGlobalInitiali; "Global initialization failed"
0x180045bdc  mov     ecx, r15d
0x180045bdf  call    WiaTrace_TraceWithSubComp
0x180045be4  mov     r9d, 2; int
0x180045bea  mov     [rsp+1A0h+lpMem], rax; lpMem
0x180045bef  mov     r8, r14; int
0x180045bf2  call    WiaTrace_ProcessTrace_Ex
0x180045bf7  mov     edi, 8000FFFFh
0x180045bfc  lea     rcx, [rsp+1A0h+var_170]; this
0x180045c01  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x180045c06  test    edi, edi
0x180045c08  js      short loc_180045C66
0x180045c0a  mov     dword ptr [rsi+8], 49637653h
0x180045c11  jmp     loc_180045CA4
0x180045c16  lea     rcx, aFailedToInitia_2; "Failed to InitializeNTSecurity for the "...
0x180045c1d  call    WiaTrace_TraceLog
0x180045c22  lea     r14, aWiaserviceInit; "WiaService::Initialize"
0x180045c29  mov     rdx, rax; char *
0x180045c2c  mov     rcx, r14; char *
0x180045c2f  mov     rbx, rax
0x180045c32  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180045c37  mov     rcx, rbx; this
0x180045c3a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180045c3f  lea     rcx, aFailedToInitia_2; "Failed to InitializeNTSecurity for the "...
0x180045c46  call    WiaTrace_Trace
0x180045c4b  mov     r15d, 1
0x180045c51  mov     [rsp+1A0h+lpMem], rax; lpMem
0x180045c56  mov     r9d, r15d; int
0x180045c59  mov     r8, r14; int
0x180045c5c  call    WiaTrace_ProcessTrace_Ex
0x180045c61  mov     edi, 8000FFFFh
0x180045c66  lea     rcx, aInternalErrors; "Internal errors encountered during init"...
0x180045c6d  call    WiaTrace_TraceLog
0x180045c72  mov     rdx, rax; char *
0x180045c75  mov     rcx, r14; char *
0x180045c78  mov     rbx, rax
0x180045c7b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180045c80  mov     rcx, rbx; this
0x180045c83  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180045c88  lea     rcx, aInternalErrors; "Internal errors encountered during init"...
0x180045c8f  call    WiaTrace_Trace
0x180045c94  mov     r9d, r15d; int
0x180045c97  mov     [rsp+1A0h+lpMem], rax; lpMem
0x180045c9c  mov     r8, r14; int
0x180045c9f  call    WiaTrace_ProcessTrace_Ex
0x180045ca4  mov     eax, edi
0x180045ca6  mov     rcx, [rbp+0A0h+var_30]
0x180045caa  xor     rcx, rsp; StackCookie
0x180045cad  call    __security_check_cookie
0x180045cb2  lea     r11, [rsp+1A0h+var_20]
0x180045cba  mov     rbx, [r11+38h]
0x180045cbe  mov     rsi, [r11+40h]
0x180045cc2  mov     rsp, r11
0x180045cc5  pop     r15
0x180045cc7  pop     r14
0x180045cc9  pop     r12
0x180045ccb  pop     rdi
0x180045ccc  pop     rbp
0x180045ccd  retn
```
