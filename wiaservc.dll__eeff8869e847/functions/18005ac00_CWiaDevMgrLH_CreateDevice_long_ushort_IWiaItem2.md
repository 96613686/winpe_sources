# CWiaDevMgrLH::CreateDevice(long,ushort *,IWiaItem2 * *)

- ea: `0x18005ac00`
- end: `0x18005aead`
- name: `?CreateDevice@CWiaDevMgrLH@@EEAAJJPEAGPEAPEAUIWiaItem2@@@Z`
- size: `685`
- prototype: `__int64 __fastcall(CWiaDevMgrLH *this, int, unsigned __int16 *, struct IWiaItem2 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x180027590`
- `0x18002d6e4`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x18005ac00`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18005ac6a`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ac6a`

## string_xrefs

- `0x18005ae17`: `CWiaDevMgrLH::CreateDevice, Invalid argument`
- `0x18005ae39`: `CWiaDevMgrLH::CreateDevice, Invalid argument`
- `0x18005acbd`: `CWiaDevMgrLH::CreateDevice, unable to find active STI USD device object`
- `0x18005acdf`: `CWiaDevMgrLH::CreateDevice, unable to find active STI USD device object`
- `0x18005ac2b`: `CWiaDevMgrLH::CreateDevice`
- `0x18005acf4`: `CWiaDevMgrLH::CreateDevice`
- `0x18005ad71`: `CWiaDevMgrLH::CreateDevice`
- `0x18005ad97`: `CWiaDevMgrLH::CreateDevice`
- `0x18005ae50`: `CWiaDevMgrLH::CreateDevice`
- `0x18005ad21`: `CWiaDevMgrLH::CreateDevice, unable to get information about the active STI USD device object`
- `0x18005ad43`: `CWiaDevMgrLH::CreateDevice, unable to get information about the active STI USD device object`
- `0x18005ad62`: `CWiaDevMgrLH::CreateDevice failed, not a scanner device (WIA_S_NO_DEVICE_AVAILABLE)`
- `0x18005ad88`: `CWiaDevMgrLH::CreateDevice failed, not a scanner device (WIA_S_NO_DEVICE_AVAILABLE)`

## pseudocode

```c
__int64 __fastcall CWiaDevMgrLH::CreateDevice(CWiaDevMgrLH *this, int a2, unsigned __int16 *a3, struct IWiaItem2 **a4)
{
  struct tagWiaTraceData_Type *v7; // rax
  char *v8; // rdx
  unsigned int v9; // r8d
  __int64 v10; // rcx
  __int64 USDWrapperFromDeviceList; // rsi
  char *v12; // rbx
  void *v13; // rdx
  void *v14; // rax
  int v15; // edx
  int v16; // ecx
  int v17; // ebx
  __int64 v18; // rax
  char *v19; // rbx
  void *v20; // rdx
  void *v21; // rax
  int v22; // edx
  int v23; // ecx
  char *v24; // rbx
  void *v25; // rdx
  CWiaDevMgrBase *v26; // rcx
  char *v27; // rbx
  void *v28; // rdx
  void *v29; // rax
  int v30; // edx
  int v31; // ecx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  struct IUnknown *v34; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID v35; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v36[80]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v37[38]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaDevMgrLH::CreateDevice");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v36, v8, v9, "CWiaDevMgrLH::CreateDevice", lpMem, v7);
  v34 = 0;
  if ( !a3 || !SysStringLen(a3) || !a4 )
  {
    v27 = (char *)WiaTrace_TraceLog("CWiaDevMgrLH::CreateDevice, Invalid argument");
    WriteDbgTraceErrorWI("CWiaDevMgrLH::CreateDevice", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v29 = (void *)WiaTrace_Trace("CWiaDevMgrLH::CreateDevice, Invalid argument");
    WiaTrace_ProcessTrace_Ex(v31, v30, (int)"CWiaDevMgrLH::CreateDevice", 1, v29);
    v17 = -2147024809;
    goto LABEL_15;
  }
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v37, a3);
  USDWrapperFromDeviceList = GetUSDWrapperFromDeviceList(v10, v37);
  v37[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v37);
  v37[34] = 0;
  if ( !USDWrapperFromDeviceList )
  {
    v12 = (char *)WiaTrace_TraceLog("CWiaDevMgrLH::CreateDevice, unable to find active STI USD device object");
    WriteDbgTraceErrorWI("CWiaDevMgrLH::CreateDevice", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void *)WiaTrace_Trace("CWiaDevMgrLH::CreateDevice, unable to find active STI USD device object");
    WiaTrace_ProcessTrace_Ex(v16, v15, (int)"CWiaDevMgrLH::CreateDevice", 1, v14);
    v17 = -2145320939;
    goto LABEL_15;
  }
  v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)USDWrapperFromDeviceList + 152LL))(USDWrapperFromDeviceList);
  if ( !v18 )
  {
    v19 = (char *)WiaTrace_TraceLog("CWiaDevMgrLH::CreateDevice, unable to get information about the active STI USD device object");
    WriteDbgTraceErrorWI("CWiaDevMgrLH::CreateDevice", v19);
    WiaTrcLib::Free((WiaTrcLib *)v19, v20);
    v21 = (void *)WiaTrace_Trace("CWiaDevMgrLH::CreateDevice, unable to get information about the active STI USD device object");
LABEL_10:
    WiaTrace_ProcessTrace_Ex(v23, v22, (int)"CWiaDevMgrLH::CreateDevice", 1, v21);
    v17 = -2145320939;
    goto LABEL_11;
  }
  v17 = 0;
  if ( *(_WORD *)(v18 + 42) != 1 )
  {
    v24 = (char *)WiaTrace_TraceLog("CWiaDevMgrLH::CreateDevice failed, not a scanner device (WIA_S_NO_DEVICE_AVAILABLE)");
    WriteDbgTraceErrorWI("CWiaDevMgrLH::CreateDevice", v24);
    WiaTrcLib::Free((WiaTrcLib *)v24, v25);
    v21 = (void *)WiaTrace_Trace("CWiaDevMgrLH::CreateDevice failed, not a scanner device (WIA_S_NO_DEVICE_AVAILABLE)");
    goto LABEL_10;
  }
LABEL_11:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)USDWrapperFromDeviceList + 16LL))(USDWrapperFromDeviceList);
  if ( v17 >= 0 )
  {
    v35 = CLSID_WiaDevMgr2;
    v17 = CWiaDevMgrBase::CreateWIADevice(v26, &v35, a2, a3, &v34, 0);
    if ( v17 >= 0 )
      v17 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IWiaItem2 **))v34->lpVtbl->QueryInterface)(
              v34,
              &IID_IWiaItem2,
              a4);
  }
LABEL_15:
  if ( v34 )
  {
    ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
    v34 = 0;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v36);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18005ac00  push    rbp
0x18005ac02  push    rbx
0x18005ac03  push    rsi
0x18005ac04  push    rdi
0x18005ac05  push    r12
0x18005ac07  push    r14
0x18005ac09  push    r15
0x18005ac0b  lea     rbp, [rsp-0E0h]
0x18005ac13  sub     rsp, 1E0h
0x18005ac1a  mov     rax, cs:__security_cookie
0x18005ac21  xor     rax, rsp
0x18005ac24  mov     [rbp+110h+var_40], rax
0x18005ac2b  lea     rdi, aCwiadevmgrlhCr; "CWiaDevMgrLH::CreateDevice"
0x18005ac32  mov     r15, r9
0x18005ac35  mov     rcx, rdi
0x18005ac38  mov     r14, r8
0x18005ac3b  mov     r12d, edx
0x18005ac3e  call    WiaTrace_Trace
0x18005ac43  mov     r9, rdi; char *
0x18005ac46  mov     [rsp+210h+var_1E8], rax; struct tagWiaTraceData_Type *
0x18005ac4b  lea     rcx, [rsp+210h+var_1C0]; this
0x18005ac50  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18005ac55  mov     [rsp+210h+var_1E0], 0
0x18005ac5e  test    r14, r14
0x18005ac61  jz      loc_18005AE17
0x18005ac67  mov     rcx, r14; pbstr
0x18005ac6a  call    cs:__imp_SysStringLen
0x18005ac70  test    eax, eax
0x18005ac72  jz      loc_18005AE17
0x18005ac78  test    r15, r15
0x18005ac7b  jz      loc_18005AE17
0x18005ac81  mov     rdx, r14
0x18005ac84  lea     rcx, [rbp+110h+var_170]
0x18005ac88  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18005ac8d  lea     rdx, [rbp+110h+var_170]
0x18005ac91  call    ?GetUSDWrapperFromDeviceList@@YAPEAVUSDWrapper@@JAEBV?$CSimpleStringBase@G@@@Z; GetUSDWrapperFromDeviceList(long,CSimpleStringBase<ushort> const &)
0x18005ac96  mov     rsi, rax
0x18005ac99  lea     rcx, [rbp+110h+var_170]
0x18005ac9d  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18005aca4  mov     [rbp+110h+var_170], rax
0x18005aca8  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18005acad  mov     [rbp+110h+var_60], 0
0x18005acb8  test    rsi, rsi
0x18005acbb  jnz     short loc_18005AD0A
0x18005acbd  lea     rcx, aCwiadevmgrlhCr_1; "CWiaDevMgrLH::CreateDevice, unable to f"...
0x18005acc4  call    WiaTrace_TraceLog
0x18005acc9  mov     rdx, rax; char *
0x18005accc  mov     rcx, rdi; char *
0x18005accf  mov     rbx, rax
0x18005acd2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005acd7  mov     rcx, rbx; this
0x18005acda  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005acdf  lea     rcx, aCwiadevmgrlhCr_1; "CWiaDevMgrLH::CreateDevice, unable to f"...
0x18005ace6  call    WiaTrace_Trace
0x18005aceb  lea     r9d, [rsi+1]; int
0x18005acef  mov     [rsp+210h+lpMem], rax; lpMem
0x18005acf4  lea     r8, aCwiadevmgrlhCr; "CWiaDevMgrLH::CreateDevice"
0x18005acfb  call    WiaTrace_ProcessTrace_Ex
0x18005ad00  mov     ebx, 80210015h
0x18005ad05  jmp     loc_18005AE61
0x18005ad0a  mov     rax, [rsi]
0x18005ad0d  mov     rcx, rsi
0x18005ad10  mov     rax, [rax+98h]
0x18005ad17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad1c  test    rax, rax
0x18005ad1f  jnz     short loc_18005AD57
0x18005ad21  lea     rcx, aCwiadevmgrlhCr_6; "CWiaDevMgrLH::CreateDevice, unable to g"...
0x18005ad28  call    WiaTrace_TraceLog
0x18005ad2d  mov     rdx, rax; char *
0x18005ad30  mov     rcx, rdi; char *
0x18005ad33  mov     rbx, rax
0x18005ad36  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ad3b  mov     rcx, rbx; this
0x18005ad3e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ad43  lea     rcx, aCwiadevmgrlhCr_6; "CWiaDevMgrLH::CreateDevice, unable to g"...
0x18005ad4a  call    WiaTrace_Trace
0x18005ad4f  mov     r9d, 1
0x18005ad55  jmp     short loc_18005AD97
0x18005ad57  xor     ebx, ebx
0x18005ad59  lea     edi, [rbx+1]
0x18005ad5c  cmp     di, [rax+2Ah]
0x18005ad60  jz      short loc_18005ADAD
0x18005ad62  lea     rcx, aCwiadevmgrlhCr_3; "CWiaDevMgrLH::CreateDevice failed, not "...
0x18005ad69  call    WiaTrace_TraceLog
0x18005ad6e  mov     rdx, rax; char *
0x18005ad71  lea     rcx, aCwiadevmgrlhCr; "CWiaDevMgrLH::CreateDevice"
0x18005ad78  mov     rbx, rax
0x18005ad7b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ad80  mov     rcx, rbx; this
0x18005ad83  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ad88  lea     rcx, aCwiadevmgrlhCr_3; "CWiaDevMgrLH::CreateDevice failed, not "...
0x18005ad8f  call    WiaTrace_Trace
0x18005ad94  mov     r9d, edi; int
0x18005ad97  lea     r8, aCwiadevmgrlhCr; "CWiaDevMgrLH::CreateDevice"
0x18005ad9e  mov     [rsp+210h+lpMem], rax; lpMem
0x18005ada3  call    WiaTrace_ProcessTrace_Ex
0x18005ada8  mov     ebx, 80210015h
0x18005adad  mov     rax, [rsi]
0x18005adb0  mov     rcx, rsi
0x18005adb3  mov     rax, [rax+10h]
0x18005adb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005adbc  test    ebx, ebx
0x18005adbe  js      loc_18005AE61
0x18005adc4  movups  xmm0, xmmword ptr cs:CLSID_WiaDevMgr2.Data1
0x18005adcb  lea     rax, [rsp+210h+var_1E0]
0x18005add0  mov     dword ptr [rsp+210h+var_1E8], 0; unsigned int
0x18005add8  mov     r9, r14; unsigned __int16 *
0x18005addb  mov     [rsp+210h+lpMem], rax; struct IUnknown **
0x18005ade0  mov     r8d, r12d; int
0x18005ade3  lea     rdx, [rsp+210h+var_1D0]; struct _GUID
0x18005ade8  movdqu  xmmword ptr [rsp+210h+var_1D0.Data1], xmm0
0x18005adee  call    ?CreateWIADevice@CWiaDevMgrBase@@IEAAJU_GUID@@JPEAGPEAPEAUIUnknown@@K@Z; CWiaDevMgrBase::CreateWIADevice(_GUID,long,ushort *,IUnknown * *,ulong)
0x18005adf3  mov     ebx, eax
0x18005adf5  test    eax, eax
0x18005adf7  js      short loc_18005AE61
0x18005adf9  mov     rcx, [rsp+210h+var_1E0]
0x18005adfe  lea     rdx, IID_IWiaItem2
0x18005ae05  mov     r8, r15
0x18005ae08  mov     rax, [rcx]
0x18005ae0b  mov     rax, [rax]
0x18005ae0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae13  mov     ebx, eax
0x18005ae15  jmp     short loc_18005AE61
0x18005ae17  lea     rcx, aCwiadevmgrlhCr_7; "CWiaDevMgrLH::CreateDevice, Invalid arg"...
0x18005ae1e  call    WiaTrace_TraceLog
0x18005ae23  mov     rdx, rax; char *
0x18005ae26  mov     rcx, rdi; char *
0x18005ae29  mov     rbx, rax
0x18005ae2c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ae31  mov     rcx, rbx; this
0x18005ae34  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ae39  lea     rcx, aCwiadevmgrlhCr_7; "CWiaDevMgrLH::CreateDevice, Invalid arg"...
0x18005ae40  call    WiaTrace_Trace
0x18005ae45  mov     r9d, 1; int
0x18005ae4b  mov     [rsp+210h+lpMem], rax; lpMem
0x18005ae50  lea     r8, aCwiadevmgrlhCr; "CWiaDevMgrLH::CreateDevice"
0x18005ae57  call    WiaTrace_ProcessTrace_Ex
0x18005ae5c  mov     ebx, 80070057h
0x18005ae61  mov     rcx, [rsp+210h+var_1E0]
0x18005ae66  test    rcx, rcx
0x18005ae69  jz      short loc_18005AE80
0x18005ae6b  mov     rax, [rcx]
0x18005ae6e  mov     rax, [rax+10h]
0x18005ae72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae77  mov     [rsp+210h+var_1E0], 0
0x18005ae80  lea     rcx, [rsp+210h+var_1C0]; this
0x18005ae85  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18005ae8a  mov     eax, ebx
0x18005ae8c  mov     rcx, [rbp+110h+var_40]
0x18005ae93  xor     rcx, rsp; StackCookie
0x18005ae96  call    __security_check_cookie
0x18005ae9b  add     rsp, 1E0h
0x18005aea2  pop     r15
0x18005aea4  pop     r14
0x18005aea6  pop     r12
0x18005aea8  pop     rdi
0x18005aea9  pop     rsi
0x18005aeaa  pop     rbx
0x18005aeab  pop     rbp
0x18005aeac  retn
```
