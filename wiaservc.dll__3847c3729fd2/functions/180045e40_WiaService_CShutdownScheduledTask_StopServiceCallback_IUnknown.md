# WiaService::CShutdownScheduledTask::StopServiceCallback(IUnknown *)

- ea: `0x180045e40`
- end: `0x1800461db`
- name: `?StopServiceCallback@CShutdownScheduledTask@WiaService@@SAXPEAUIUnknown@@@Z`
- size: `923`
- prototype: `void __fastcall(struct IUnknown *)`
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x18000f88c`
- `0x18000fc60`
- `0x180011a94`
- `0x1800174c4`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e72c`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180045e40`
- `0x18004b49c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x1800460f6`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x1800460f6`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x180045ec1`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x180045ec1`

## string_xrefs

- `0x180045fc7`: `WiaService`
- `0x180045e6c`: `Attempting to shutdown service`
- `0x180045e9e`: `Attempting to shutdown service`
- `0x180045e81`: `WiaService::CShutdownScheduledTask::StopServiceCallback`
- `0x180046021`: `WiaService::CShutdownScheduledTask::StopServiceCallback`
- `0x18004604f`: `WiaService::CShutdownScheduledTask::StopServiceCallback`
- `0x1800460ba`: `WiaService::CShutdownScheduledTask::StopServiceCallback`
- `0x1800460ea`: `WiaService::CShutdownScheduledTask::StopServiceCallback`
- `0x180046111`: `WiaService::CShutdownScheduledTask::StopServiceCallback`
- `0x180046141`: `WiaService::CShutdownScheduledTask::StopServiceCallback`
- `0x180045f24`: `Unable to perform shutdown of service - cannot get reference to DeviceListManager`
- `0x180045f48`: `Unable to perform shutdown of service - cannot get reference to DeviceListManager`
- `0x18004600d`: `Unable to shutdown service - cannot get reference to WiaService`
- `0x180046038`: `Unable to shutdown service - cannot get reference to WiaService`
- `0x180046100`: `Fatal error: Unable to resume COM connection to class objects, communication with server will probably be impossible`
- `0x180046128`: `Fatal error: Unable to resume COM connection to class objects, communication with server will probably be impossible`
- `0x180046179`: `Unable to suspend class object, service may continue when it should shut down`
- `0x18004619d`: `Unable to suspend class object, service may continue when it should shut down`

## pseudocode

```c
void __fastcall WiaService::CShutdownScheduledTask::StopServiceCallback(struct IUnknown *a1)
{
  char *v2; // rbx
  void *v3; // rdx
  void **lpMem; // rax
  void *v5; // rdx
  __int64 v6; // rcx
  DeviceListManager *v7; // rbx
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  bool v13; // di
  _DWORD *v14; // r14
  char *v15; // rcx
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  WiaService *v21; // rcx
  char *v22; // rbx
  void *v23; // rdx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  char *v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  int v38; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v39[16]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v40[24]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v41[34]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+170h] [rbp+70h]

  v2 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0x80000000LL, 0, "Attempting to shutdown service");
  WriteDbgTraceInfoWI("WiaService::CShutdownScheduledTask::StopServiceCallback", v2);
  WiaTrcLib::Free((WiaTrcLib *)v2, v3);
  lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(0x80000000LL, 0, "Attempting to shutdown service");
  WiaTrace_ProcessTrace_Ex(v6, v5, (void *)"WiaService::CShutdownScheduledTask::StopServiceCallback", 4, lpMem);
  if ( CoSuspendClassObjects() < 0 )
  {
    v33 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "Unable to suspend class object, service may continue when it should shut down");
    WriteDbgTraceWarningWI("WiaService::CShutdownScheduledTask::StopServiceCallback", v33);
    WiaTrcLib::Free((WiaTrcLib *)v33, v34);
    v35 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "Unable to suspend class object, service may continue when it should shut down");
    WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"WiaService::CShutdownScheduledTask::StopServiceCallback", 2, v35);
    return;
  }
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v40);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v41, L"DeviceListManager");
  v7 = (DeviceListManager *)ServiceComponentHolder::Get<DeviceListManager>(v40, v41);
  v41[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v41);
  v42 = 0;
  if ( v7 )
  {
    v38 = 0;
    v13 = 1;
    if ( (int)DeviceListManager::GetNumActiveDevices(v7, &v38) >= 0 )
      v13 = v38 == 0;
    v15 = (char *)v7 + *(int *)(*((_QWORD *)v7 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
    v14 = 0;
    if ( v13 )
    {
      ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v39);
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v41, L"WiaService");
      v14 = (_DWORD *)ServiceComponentHolder::Get<WiaService>(v39, v41);
      v41[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v41);
      v42 = 0;
      if ( !v14 )
      {
        v13 = 0;
        v16 = (char *)WiaTrace_TraceLogWithSubComp(1, "Unable to shutdown service - cannot get reference to WiaService");
        WriteDbgTraceWarningWI("WiaService::CShutdownScheduledTask::StopServiceCallback", v16);
        WiaTrcLib::Free((WiaTrcLib *)v16, v17);
        v18 = (void **)WiaTrace_TraceWithSubComp(1, "Unable to shutdown service - cannot get reference to WiaService");
        WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"WiaService::CShutdownScheduledTask::StopServiceCallback", 2, v18);
      }
      ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v39);
      if ( v13 && v14 )
      {
        if ( v14[4] )
          v13 = 0;
        else
          WiaService::Stop(v21);
      }
    }
  }
  else
  {
    v8 = (char *)WiaTrace_TraceLogWithSubComp(
                   1,
                   "Unable to perform shutdown of service - cannot get reference to DeviceListManager");
    WriteDbgTraceWarningWI("WiaService::CShutdownScheduledTask::StopServiceCallback", v8);
    WiaTrcLib::Free((WiaTrcLib *)v8, v9);
    v10 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "Unable to perform shutdown of service - cannot get reference to DeviceListManager");
    WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"WiaService::CShutdownScheduledTask::StopServiceCallback", 2, v10);
    v13 = 0;
    v14 = 0;
  }
  if ( a1 )
  {
    ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->Release)(a1);
    if ( !v13 )
    {
LABEL_19:
      if ( CoResumeClassObjects() < 0 )
      {
        v27 = (char *)WiaTrace_TraceLogWithSubComp(
                        1,
                        "Fatal error: Unable to resume COM connection to class objects, communication with server will pr"
                        "obably be impossible");
        WriteDbgTraceWarningWI("WiaService::CShutdownScheduledTask::StopServiceCallback", v27);
        WiaTrcLib::Free((WiaTrcLib *)v27, v28);
        v29 = (void **)WiaTrace_TraceWithSubComp(
                         1,
                         "Fatal error: Unable to resume COM connection to class objects, communication with server will p"
                         "robably be impossible");
        WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"WiaService::CShutdownScheduledTask::StopServiceCallback", 2, v29);
      }
    }
  }
  else if ( !v13 )
  {
    v22 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "Unable to release shutdown callback object in shutdown callback, NULL callback object received");
    WriteDbgTraceWarningWI("WiaService::CShutdownScheduledTask::StopServiceCallback", v22);
    WiaTrcLib::Free((WiaTrcLib *)v22, v23);
    v24 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "Unable to release shutdown callback object in shutdown callback, NULL callback object received");
    WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"WiaService::CShutdownScheduledTask::StopServiceCallback", 2, v24);
    goto LABEL_19;
  }
  if ( v14 )
  {
    v32 = (char *)v14 + *(int *)(*(_QWORD *)v14 + 4LL);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))(v32);
  }
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v40);
}

```

## disassembly

```asm
0x180045e40  push    rbp
0x180045e42  push    rbx
0x180045e43  push    rsi
0x180045e44  push    rdi
0x180045e45  push    r12
0x180045e47  push    r14
0x180045e49  lea     rbp, [rsp-0A8h]
0x180045e51  sub     rsp, 1A8h
0x180045e58  mov     rax, cs:__security_cookie
0x180045e5f  xor     rax, rsp
0x180045e62  mov     [rbp+0D0h+var_40], rax
0x180045e69  mov     r12, rcx
0x180045e6c  lea     r8, aAttemptingToSh; "Attempting to shutdown service"
0x180045e73  mov     edi, 80000000h
0x180045e78  xor     edx, edx
0x180045e7a  mov     ecx, edi
0x180045e7c  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180045e81  lea     r14, aWiaserviceCshu; "WiaService::CShutdownScheduledTask::Sto"...
0x180045e88  mov     rdx, rax; char *
0x180045e8b  mov     rcx, r14; char *
0x180045e8e  mov     rbx, rax
0x180045e91  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180045e96  mov     rcx, rbx; this
0x180045e99  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180045e9e  lea     r8, aAttemptingToSh; "Attempting to shutdown service"
0x180045ea5  xor     edx, edx
0x180045ea7  mov     ecx, edi
0x180045ea9  call    WiaTrace_TraceWithSubCompTraceLevel
0x180045eae  mov     r9d, 4; int
0x180045eb4  mov     [rsp+1D0h+lpMem], rax; lpMem
0x180045eb9  mov     r8, r14; int
0x180045ebc  call    WiaTrace_ProcessTrace_Ex
0x180045ec1  call    cs:__imp_CoSuspendClassObjects
0x180045ec7  test    eax, eax
0x180045ec9  js      loc_180046174
0x180045ecf  lea     rcx, [rsp+1D0h+var_188]; this
0x180045ed4  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x180045ed9  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x180045ee0  lea     rcx, [rsp+1D0h+var_170]
0x180045ee5  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180045eea  lea     rdx, [rsp+1D0h+var_170]
0x180045eef  lea     rcx, [rsp+1D0h+var_188]
0x180045ef4  call    ??$Get@VDeviceListManager@@@ServiceComponentHolder@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x180045ef9  mov     rbx, rax
0x180045efc  lea     rcx, [rsp+1D0h+var_170]
0x180045f01  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180045f08  mov     [rsp+1D0h+var_170], rax
0x180045f0d  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180045f12  mov     [rbp+0D0h+var_60], 0
0x180045f1a  mov     esi, 1
0x180045f1f  test    rbx, rbx
0x180045f22  jnz     short loc_180045F72
0x180045f24  lea     rdx, aUnableToPerfor; "Unable to perform shutdown of service -"...
0x180045f2b  mov     ecx, esi
0x180045f2d  call    WiaTrace_TraceLogWithSubComp
0x180045f32  mov     rdx, rax; char *
0x180045f35  mov     rcx, r14; char *
0x180045f38  mov     rbx, rax
0x180045f3b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180045f40  mov     rcx, rbx; this
0x180045f43  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180045f48  lea     rdx, aUnableToPerfor; "Unable to perform shutdown of service -"...
0x180045f4f  mov     ecx, esi
0x180045f51  call    WiaTrace_TraceWithSubComp
0x180045f56  lea     r9d, [rsi+1]; int
0x180045f5a  mov     [rsp+1D0h+lpMem], rax; lpMem
0x180045f5f  mov     r8, r14; int
0x180045f62  call    WiaTrace_ProcessTrace_Ex
0x180045f67  xor     dil, dil
0x180045f6a  xor     r14d, r14d
0x180045f6d  jmp     loc_180046080
0x180045f72  lea     rdx, [rsp+1D0h+var_1A0]; int *
0x180045f77  mov     [rsp+1D0h+var_1A0], 0
0x180045f7f  mov     rcx, rbx; this
0x180045f82  mov     edi, esi
0x180045f84  call    ?GetNumActiveDevices@DeviceListManager@@QEAAJPEAJ@Z; DeviceListManager::GetNumActiveDevices(long *)
0x180045f89  test    eax, eax
0x180045f8b  js      short loc_180045F96
0x180045f8d  xor     eax, eax
0x180045f8f  cmp     [rsp+1D0h+var_1A0], eax
0x180045f93  cmovnz  edi, eax
0x180045f96  mov     rax, [rbx+8]
0x180045f9a  movsxd  rcx, dword ptr [rax+4]
0x180045f9e  add     rcx, 8
0x180045fa2  add     rcx, rbx
0x180045fa5  mov     rax, [rcx]
0x180045fa8  mov     rax, [rax+10h]
0x180045fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fb1  xor     r14d, r14d
0x180045fb4  cmp     dil, sil
0x180045fb7  jnz     loc_180046080
0x180045fbd  lea     rcx, [rsp+1D0h+var_198]; this
0x180045fc2  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x180045fc7  lea     rdx, aWiaservice; "WiaService"
0x180045fce  lea     rcx, [rsp+1D0h+var_170]
0x180045fd3  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180045fd8  lea     rdx, [rsp+1D0h+var_170]
0x180045fdd  lea     rcx, [rsp+1D0h+var_198]
0x180045fe2  call    ??$Get@VWiaService@@@ServiceComponentHolder@@QEAAPEAVWiaService@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<WiaService>(CSimpleStringBase<ushort> const &)
0x180045fe7  mov     r14, rax
0x180045fea  lea     rcx, [rsp+1D0h+var_170]
0x180045fef  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180045ff6  mov     [rsp+1D0h+var_170], rax
0x180045ffb  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180046000  mov     [rbp+0D0h+var_60], 0
0x180046008  test    r14, r14
0x18004600b  jnz     short loc_18004605B
0x18004600d  lea     rdx, aUnableToShutdo; "Unable to shutdown service - cannot get"...
0x180046014  mov     ecx, esi
0x180046016  xor     dil, dil
0x180046019  call    WiaTrace_TraceLogWithSubComp
0x18004601e  mov     rdx, rax; char *
0x180046021  lea     rcx, aWiaserviceCshu; "WiaService::CShutdownScheduledTask::Sto"...
0x180046028  mov     rbx, rax
0x18004602b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180046030  mov     rcx, rbx; this
0x180046033  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180046038  lea     rdx, aUnableToShutdo; "Unable to shutdown service - cannot get"...
0x18004603f  mov     ecx, esi
0x180046041  call    WiaTrace_TraceWithSubComp
0x180046046  lea     r9d, [r14+2]; int
0x18004604a  mov     [rsp+1D0h+lpMem], rax; lpMem
0x18004604f  lea     r8, aWiaserviceCshu; "WiaService::CShutdownScheduledTask::Sto"...
0x180046056  call    WiaTrace_ProcessTrace_Ex
0x18004605b  lea     rcx, [rsp+1D0h+var_198]; this
0x180046060  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x180046065  cmp     dil, sil
0x180046068  jnz     short loc_180046080
0x18004606a  test    r14, r14
0x18004606d  jz      short loc_180046080
0x18004606f  cmp     dword ptr [r14+10h], 0
0x180046074  jz      short loc_18004607B
0x180046076  xor     dil, dil
0x180046079  jmp     short loc_180046080
0x18004607b  call    ?Stop@WiaService@@QEAAJXZ; WiaService::Stop(void)
0x180046080  test    r12, r12
0x180046083  jz      short loc_1800460A0
0x180046085  mov     rax, [r12]
0x180046089  mov     rcx, r12
0x18004608c  mov     rax, [rax+10h]
0x180046090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046095  test    dil, dil
0x180046098  jnz     loc_18004614D
0x18004609e  jmp     short loc_1800460F6
0x1800460a0  test    dil, dil
0x1800460a3  jnz     loc_18004614D
0x1800460a9  lea     rdx, aUnableToReleas_0; "Unable to release shutdown callback obj"...
0x1800460b0  mov     ecx, esi
0x1800460b2  call    WiaTrace_TraceLogWithSubComp
0x1800460b7  mov     rdx, rax; char *
0x1800460ba  lea     rcx, aWiaserviceCshu; "WiaService::CShutdownScheduledTask::Sto"...
0x1800460c1  mov     rbx, rax
0x1800460c4  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800460c9  mov     rcx, rbx; this
0x1800460cc  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800460d1  lea     rdx, aUnableToReleas_0; "Unable to release shutdown callback obj"...
0x1800460d8  mov     ecx, esi
0x1800460da  call    WiaTrace_TraceWithSubComp
0x1800460df  mov     r9d, 2; int
0x1800460e5  mov     [rsp+1D0h+lpMem], rax; lpMem
0x1800460ea  lea     r8, aWiaserviceCshu; "WiaService::CShutdownScheduledTask::Sto"...
0x1800460f1  call    WiaTrace_ProcessTrace_Ex
0x1800460f6  call    cs:__imp_CoResumeClassObjects
0x1800460fc  test    eax, eax
0x1800460fe  jns     short loc_18004614D
0x180046100  lea     rdx, aFatalErrorUnab; "Fatal error: Unable to resume COM conne"...
0x180046107  mov     ecx, esi
0x180046109  call    WiaTrace_TraceLogWithSubComp
0x18004610e  mov     rdx, rax; char *
0x180046111  lea     rcx, aWiaserviceCshu; "WiaService::CShutdownScheduledTask::Sto"...
0x180046118  mov     rbx, rax
0x18004611b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180046120  mov     rcx, rbx; this
0x180046123  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180046128  lea     rdx, aFatalErrorUnab; "Fatal error: Unable to resume COM conne"...
0x18004612f  mov     ecx, esi
0x180046131  call    WiaTrace_TraceWithSubComp
0x180046136  mov     r9d, 2; int
0x18004613c  mov     [rsp+1D0h+lpMem], rax; lpMem
0x180046141  lea     r8, aWiaserviceCshu; "WiaService::CShutdownScheduledTask::Sto"...
0x180046148  call    WiaTrace_ProcessTrace_Ex
0x18004614d  test    r14, r14
0x180046150  jz      short loc_180046168
0x180046152  mov     rax, [r14]
0x180046155  movsxd  rcx, dword ptr [rax+4]
0x180046159  add     rcx, r14
0x18004615c  mov     rax, [rcx]
0x18004615f  mov     rax, [rax+10h]
0x180046163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046168  lea     rcx, [rsp+1D0h+var_188]; this
0x18004616d  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x180046172  jmp     short loc_1800461BC
0x180046174  mov     esi, 1
0x180046179  lea     rdx, aUnableToSuspen; "Unable to suspend class object, service"...
0x180046180  mov     ecx, esi
0x180046182  call    WiaTrace_TraceLogWithSubComp
0x180046187  mov     rdx, rax; char *
0x18004618a  mov     rcx, r14; char *
0x18004618d  mov     rbx, rax
0x180046190  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180046195  mov     rcx, rbx; this
0x180046198  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004619d  lea     rdx, aUnableToSuspen; "Unable to suspend class object, service"...
0x1800461a4  mov     ecx, esi
0x1800461a6  call    WiaTrace_TraceWithSubComp
0x1800461ab  lea     r9d, [rsi+1]; int
0x1800461af  mov     [rsp+1D0h+lpMem], rax; lpMem
0x1800461b4  mov     r8, r14; int
0x1800461b7  call    WiaTrace_ProcessTrace_Ex
0x1800461bc  mov     rcx, [rbp+0D0h+var_40]
0x1800461c3  xor     rcx, rsp; StackCookie
0x1800461c6  call    __security_check_cookie
0x1800461cb  add     rsp, 1A8h
0x1800461d2  pop     r14
0x1800461d4  pop     r12
0x1800461d6  pop     rdi
0x1800461d7  pop     rsi
0x1800461d8  pop     rbx
0x1800461d9  pop     rbp
0x1800461da  retn
```
