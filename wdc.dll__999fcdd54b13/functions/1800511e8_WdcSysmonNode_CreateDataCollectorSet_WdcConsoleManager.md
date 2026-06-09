# WdcSysmonNode::CreateDataCollectorSet(WdcConsoleManager *)

- ea: `0x1800511e8`
- end: `0x180051774`
- name: `?CreateDataCollectorSet@WdcSysmonNode@@AEAAJPEAVWdcConsoleManager@@@Z`
- size: `1420`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct WdcConsoleManager *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180052410`

## callees

- `0x18000b854`
- `0x18002aa2c`
- `0x18003a7cc`
- `0x180049054`
- `0x18004bcc0`
- `0x180050b9c`
- `0x1800511e8`
- `0x180051ecc`
- `0x1800596bc`
- `0x180066e18`
- `0x18006af2c`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800513e6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800514c0`
- `OLEAUT32!__imp_SysAllocString` at `0x180051528`
- `OLEAUT32!__imp_SysAllocString` at `0x1800515dd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800513e6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800514c0`
- `OLEAUT32!__imp_SysAllocString` at `0x180051528`
- `OLEAUT32!__imp_SysAllocString` at `0x1800515dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800514b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005151b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800515d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800516cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800514b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005151b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800515d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800516cb`
- `OLEAUT32!__imp_VariantInit` at `0x180051245`
- `OLEAUT32!__imp_VariantInit` at `0x180051245`
- `OLEAUT32!__imp_VariantClear` at `0x18005136f`
- `OLEAUT32!__imp_VariantClear` at `0x1800516bd`
- `OLEAUT32!__imp_VariantClear` at `0x18005136f`
- `OLEAUT32!__imp_VariantClear` at `0x1800516bd`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800513b0`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800513cf`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800513b0`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800513cf`
- `ole32!CoCreateInstance` at `0x180051282`
- `ole32!CoCreateInstance` at `0x1800515aa`
- `ole32!CoCreateInstance` at `0x180051282`
- `ole32!CoCreateInstance` at `0x1800515aa`

## string_xrefs

- `0x18005161e`: `service`
- `0x180051428`: `WdcSysmonNode::CreateDataCollectorSet`
- `0x1800516a6`: `WdcSysmonNode::CreateDataCollectorSet`
- `0x1800512dc`: `SYSMON.XML`
- `0x1800515d6`: `service\*`

## pseudocode

```c
__int64 __fastcall WdcSysmonNode::CreateDataCollectorSet(const unsigned __int16 **this, struct WdcConsoleManager *a2)
{
  OLECHAR *v3; // rdi
  WdcWizard *v4; // rsi
  HRESULT SystemMonitor; // eax
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // r8
  __int64 v9; // rax
  BSTR v10; // rax
  void *v11; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-59h]
  LPVOID *ppva; // [rsp+20h] [rbp-59h]
  __int64 v15; // [rsp+30h] [rbp-49h] BYREF
  struct IUnknown *v16; // [rsp+38h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-39h] BYREF
  __int64 v18; // [rsp+58h] [rbp-21h] BYREF
  struct IStream *v19; // [rsp+60h] [rbp-19h] BYREF
  struct ISystemMonitor2 *v20; // [rsp+68h] [rbp-11h] BYREF
  HWND v21; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG v22; // [rsp+80h] [rbp+7h] BYREF
  __int16 v23; // [rsp+F0h] [rbp+77h] BYREF
  LPVOID v24; // [rsp+F8h] [rbp+7Fh] BYREF

  v19 = 0;
  v23 = 0;
  v3 = 0;
  v21 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v4 = 0;
  v18 = 0;
  v15 = 0;
  v24 = 0;
  v20 = 0;
  v16 = 0;
  VariantInit(&pvarg);
  SystemMonitor = WdcSysmonNode::GetSystemMonitor((WdcSysmonNode *)this, a2, &v20);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = CoCreateInstance(&CLSID_FreeThreadedDOMDocument, 0, 0x15u, &IID_IXMLDOMDocument, &v24);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v24 + 576LL))(v24, 0xFFFFFFFFLL);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v24 + 504LL))(v24, 0);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = WdcCreateStreamFromResource(g_hInstance, L"SYSMON.XML", v8, &v19);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = (**(__int64 (__fastcall ***)(struct IStream *, GUID *, ULONG *))v19)(
                    v19,
                    &IID_IUnknown,
                    (ULONG *)&pvarg.cyVal);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  pvarg.vt = 13;
  v9 = *(_QWORD *)v24;
  v22 = pvarg;
  SystemMonitor = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v9 + 464))(v24, &v22, &v23);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  if ( !v23 )
  {
    v7 = -2147467259;
LABEL_10:
    LODWORD(ppv) = v7;
LABEL_40:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\sysmonnode.cpp",
      "WdcSysmonNode::CreateDataCollectorSet",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_41;
  }
  VariantClear(&pvarg);
  SystemMonitor = ((__int64 (__fastcall *)(struct ISystemMonitor2 *, ULONG *))v20->lpVtbl->get_UpdateInterval)(
                    v20,
                    &pvarg.decVal.Lo32);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  pvarg.vt = 4;
  SystemMonitor = VariantChangeType(&pvarg, &pvarg, 4u, 3u);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = VariantChangeType(&pvarg, &pvarg, 4u, 8u);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  v3 = SysAllocString(L"//SampleInterval");
  if ( !v3 )
  {
LABEL_15:
    v7 = -2147024882;
    LODWORD(ppv) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", ppv);
    LODWORD(ppva) = -2147024882;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\sysmonnode.cpp",
      "WdcSysmonNode::CreateDataCollectorSet",
      0,
      L"FAILURE: 0x%08x",
      ppva);
    v3 = 0;
    goto LABEL_41;
  }
  SystemMonitor = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)v24 + 296LL))(v24, v3, &v15);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  if ( SystemMonitor == 1 )
  {
LABEL_18:
    v7 = -2147467259;
    goto LABEL_41;
  }
  SystemMonitor = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v15 + 216LL))(v15, pvarg.llVal);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SysFreeString(v3);
  v3 = SysAllocString(L"//PerformanceCounterDataCollector");
  if ( !v3 )
    goto LABEL_15;
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  SystemMonitor = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)v24 + 296LL))(v24, v3, &v15);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  if ( SystemMonitor == 1 )
    goto LABEL_18;
  SysFreeString(v3);
  v3 = SysAllocString(L"Counter");
  if ( !v3 )
    goto LABEL_15;
  SystemMonitor = ((__int64 (__fastcall *)(struct ISystemMonitor2 *, __int64 *))v20->lpVtbl->get_Counters)(v20, &v18);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = WdcForEach<DICounterItem,ICounters>(v18, WdcSysmonNode::AddTemplateCounter, 3, v24, v15, v3);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = CoCreateInstance(
                    &CLSID_DataCollectorSetCollection,
                    0,
                    0x15u,
                    &IID_IDataCollectorSetCollection,
                    (LPVOID *)&v16);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = WdcCoSetSecurity(v16);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SysFreeString(v3);
  v10 = SysAllocString(L"service\\*");
  v3 = v10;
  if ( !v10 )
    goto LABEL_15;
  SystemMonitor = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int16 *, BSTR))v16->lpVtbl[4].Release)(
                    v16,
                    this[6],
                    v10);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  v11 = operator new(0x240u);
  v4 = (WdcWizard *)WdcDataCollectorSetWizard::WdcDataCollectorSetWizard(
                      (__int64)v11,
                      this[6],
                      L"service",
                      (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))v24,
                      3u,
                      v16);
  if ( !v4 )
  {
    v7 = -2147024882;
    goto LABEL_10;
  }
  SystemMonitor = WdcConsoleManager::GetMainWindow(a2, &v21);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  SystemMonitor = WdcWizard::ShowWizard(v4, v21);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
    goto LABEL_39;
  if ( SystemMonitor == 1 )
  {
    v7 = 0;
    goto LABEL_41;
  }
  SystemMonitor = (*(__int64 (__fastcall **)(WdcWizard *, HWND))(*(_QWORD *)v4 + 16LL))(v4, v21);
  v7 = SystemMonitor;
  if ( SystemMonitor < 0 )
  {
LABEL_39:
    LODWORD(ppv) = SystemMonitor;
    goto LABEL_40;
  }
LABEL_41:
  VariantClear(&pvarg);
  if ( v3 )
    SysFreeString(v3);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v4 )
    WdcDataPortal::Release(v4);
  if ( v16 )
    ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
  return v7;
}

```

## disassembly

```asm
0x1800511e8  mov     [rsp-8+arg_0], rbx
0x1800511ed  push    rbp
0x1800511ee  push    rsi
0x1800511ef  push    rdi
0x1800511f0  push    r12
0x1800511f2  push    r13
0x1800511f4  push    r14
0x1800511f6  push    r15
0x1800511f8  lea     rbp, [rsp-27h]
0x1800511fd  sub     rsp, 0A0h
0x180051204  xor     r12d, r12d
0x180051207  mov     r14, rcx
0x18005120a  xorps   xmm0, xmm0
0x18005120d  mov     [rbp+57h+var_70], r12
0x180051211  xor     eax, eax
0x180051213  mov     [rbp+57h+arg_10], r12w
0x180051218  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005121c  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180051220  mov     edi, r12d
0x180051223  mov     [rbp+57h+var_60], r12
0x180051227  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18005122b  mov     esi, r12d
0x18005122e  mov     [rbp+57h+var_78], r12
0x180051232  mov     [rbp+57h+var_A0], r12
0x180051236  mov     r15, rdx
0x180051239  mov     [rbp+57h+arg_18], r12
0x18005123d  mov     [rbp+57h+var_68], r12
0x180051241  mov     [rbp+57h+var_98], r12
0x180051245  call    cs:__imp_VariantInit
0x18005124b  lea     r8, [rbp+57h+var_68]; struct ISystemMonitor2 **
0x18005124f  mov     rdx, r15; struct WdcConsoleManager *
0x180051252  mov     rcx, r14; this
0x180051255  call    ?GetSystemMonitor@WdcSysmonNode@@QEAAJPEAVWdcConsoleManager@@PEAPEAUISystemMonitor2@@@Z; WdcSysmonNode::GetSystemMonitor(WdcConsoleManager *,ISystemMonitor2 * *)
0x18005125a  mov     ebx, eax
0x18005125c  test    eax, eax
0x18005125e  js      loc_180051698
0x180051264  lea     rax, [rbp+57h+arg_18]
0x180051268  xor     edx, edx; pUnkOuter
0x18005126a  lea     r9, IID_IXMLDOMDocument; riid
0x180051271  mov     [rsp+0D0h+ppv], rax; ppv
0x180051276  lea     r8d, [r12+15h]; dwClsContext
0x18005127b  lea     rcx, CLSID_FreeThreadedDOMDocument; rclsid
0x180051282  call    cs:__imp_CoCreateInstance
0x180051288  mov     ebx, eax
0x18005128a  test    eax, eax
0x18005128c  js      loc_180051698
0x180051292  mov     rcx, [rbp+57h+arg_18]
0x180051296  or      edx, 0FFFFFFFFh
0x180051299  mov     rax, [rcx]
0x18005129c  mov     rax, [rax+240h]
0x1800512a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512a8  mov     ebx, eax
0x1800512aa  test    eax, eax
0x1800512ac  js      loc_180051698
0x1800512b2  mov     rcx, [rbp+57h+arg_18]
0x1800512b6  xor     edx, edx
0x1800512b8  mov     rax, [rcx]
0x1800512bb  mov     rax, [rax+1F8h]
0x1800512c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512c7  mov     ebx, eax
0x1800512c9  test    eax, eax
0x1800512cb  js      loc_180051698
0x1800512d1  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800512d8  lea     r9, [rbp+57h+var_70]; struct IStream **
0x1800512dc  lea     rdx, aSysmonXml; "SYSMON.XML"
0x1800512e3  call    ?WdcCreateStreamFromResource@@YAJPEAUHINSTANCE__@@PEBG1PEAPEAUIStream@@@Z; WdcCreateStreamFromResource(HINSTANCE__ *,ushort const *,ushort const *,IStream * *)
0x1800512e8  mov     ebx, eax
0x1800512ea  test    eax, eax
0x1800512ec  js      loc_180051698
0x1800512f2  mov     rcx, [rbp+57h+var_70]
0x1800512f6  lea     r8, [rbp+57h+pvarg+8]
0x1800512fa  lea     rdx, IID_IUnknown
0x180051301  mov     rax, [rcx]
0x180051304  mov     rax, [rax]
0x180051307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005130c  mov     ebx, eax
0x18005130e  test    eax, eax
0x180051310  js      loc_180051698
0x180051316  mov     rcx, [rbp+57h+arg_18]
0x18005131a  lea     eax, [r12+0Dh]
0x18005131f  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180051324  lea     r8, [rbp+57h+arg_10]
0x180051328  mov     word ptr [rbp+57h+pvarg], ax
0x18005132c  lea     rdx, [rbp+57h+var_50]
0x180051330  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180051334  mov     rax, [rcx]
0x180051337  movsd   [rbp+57h+var_40], xmm1
0x18005133c  movaps  [rbp+57h+var_50], xmm0
0x180051340  mov     rax, [rax+1D0h]
0x180051347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005134c  mov     ebx, eax
0x18005134e  test    eax, eax
0x180051350  js      loc_180051698
0x180051356  cmp     r12w, [rbp+57h+arg_10]
0x18005135b  jnz     short loc_18005136B
0x18005135d  mov     ebx, 80004005h
0x180051362  mov     dword ptr [rsp+0D0h+ppv], ebx
0x180051366  jmp     loc_18005169C
0x18005136b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005136f  call    cs:__imp_VariantClear
0x180051375  mov     rcx, [rbp+57h+var_68]
0x180051379  lea     rdx, [rbp+57h+pvarg+8]
0x18005137d  mov     rax, [rcx]
0x180051380  mov     rax, [rax+0E8h]
0x180051387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005138c  mov     ebx, eax
0x18005138e  test    eax, eax
0x180051390  js      loc_180051698
0x180051396  mov     r13d, 4
0x18005139c  lea     rdx, [rbp+57h+pvarg]; pvarSrc
0x1800513a0  mov     r8d, r13d; wFlags
0x1800513a3  mov     word ptr [rbp+57h+pvarg], r13w
0x1800513a8  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x1800513ac  lea     r9d, [r13-1]; vt
0x1800513b0  call    cs:__imp_VariantChangeType
0x1800513b6  mov     ebx, eax
0x1800513b8  test    eax, eax
0x1800513ba  js      loc_180051698
0x1800513c0  lea     r9d, [r13+4]; vt
0x1800513c4  mov     r8d, r13d; wFlags
0x1800513c7  lea     rdx, [rbp+57h+pvarg]; pvarSrc
0x1800513cb  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x1800513cf  call    cs:__imp_VariantChangeType
0x1800513d5  mov     ebx, eax
0x1800513d7  test    eax, eax
0x1800513d9  js      loc_180051698
0x1800513df  lea     rcx, aSampleinterval; "//SampleInterval"
0x1800513e6  call    cs:__imp_SysAllocString
0x1800513ec  mov     rdi, rax
0x1800513ef  test    rax, rax
0x1800513f2  jnz     short loc_180051443
0x1800513f4  mov     ebx, 8007000Eh
0x1800513f9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180051400  xor     r8d, r8d; int
0x180051403  mov     dword ptr [rsp+0D0h+ppv], ebx
0x180051407  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18005140e  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180051415  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005141a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180051421  mov     dword ptr [rsp+0D0h+ppv], ebx
0x180051425  xor     r8d, r8d; int
0x180051428  lea     rdx, aWdcsysmonnodeC; "WdcSysmonNode::CreateDataCollectorSet"
0x18005142f  lea     rcx, aBaseDiagnosisP_9; "base\\diagnosis\\pdui\\perfmon\\mmc\\sy"...
0x180051436  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005143b  mov     rdi, r12
0x18005143e  jmp     loc_1800516B9
0x180051443  mov     rcx, [rbp+57h+var_A0]
0x180051447  test    rcx, rcx
0x18005144a  jz      short loc_18005145C
0x18005144c  mov     rax, [rcx]
0x18005144f  mov     rax, [rax+10h]
0x180051453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051458  mov     [rbp+57h+var_A0], r12
0x18005145c  mov     rcx, [rbp+57h+arg_18]
0x180051460  lea     r8, [rbp+57h+var_A0]
0x180051464  mov     rdx, rdi
0x180051467  mov     rax, [rcx]
0x18005146a  mov     rax, [rax+128h]
0x180051471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051476  mov     ebx, eax
0x180051478  test    eax, eax
0x18005147a  js      loc_180051698
0x180051480  cmp     eax, 1
0x180051483  jnz     short loc_18005148F
0x180051485  mov     ebx, 80004005h
0x18005148a  jmp     loc_1800516B9
0x18005148f  mov     rcx, [rbp+57h+var_A0]
0x180051493  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x180051497  mov     rax, [rcx]
0x18005149a  mov     rax, [rax+0D8h]
0x1800514a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514a6  mov     ebx, eax
0x1800514a8  test    eax, eax
0x1800514aa  js      loc_180051698
0x1800514b0  mov     rcx, rdi; bstrString
0x1800514b3  call    cs:__imp_SysFreeString
0x1800514b9  lea     rcx, aPerformancecou_0; "//PerformanceCounterDataCollector"
0x1800514c0  call    cs:__imp_SysAllocString
0x1800514c6  mov     rdi, rax
0x1800514c9  test    rax, rax
0x1800514cc  jz      loc_1800513F4
0x1800514d2  mov     rcx, [rbp+57h+var_A0]
0x1800514d6  test    rcx, rcx
0x1800514d9  jz      short loc_1800514EB
0x1800514db  mov     rax, [rcx]
0x1800514de  mov     rax, [rax+10h]
0x1800514e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514e7  mov     [rbp+57h+var_A0], r12
0x1800514eb  mov     rcx, [rbp+57h+arg_18]
0x1800514ef  lea     r8, [rbp+57h+var_A0]
0x1800514f3  mov     rdx, rdi
0x1800514f6  mov     rax, [rcx]
0x1800514f9  mov     rax, [rax+128h]
0x180051500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051505  mov     ebx, eax
0x180051507  test    eax, eax
0x180051509  js      loc_180051698
0x18005150f  cmp     eax, 1
0x180051512  jz      loc_180051485
0x180051518  mov     rcx, rdi; bstrString
0x18005151b  call    cs:__imp_SysFreeString
0x180051521  lea     rcx, aCounter; "Counter"
0x180051528  call    cs:__imp_SysAllocString
0x18005152e  mov     rdi, rax
0x180051531  test    rax, rax
0x180051534  jz      loc_1800513F4
0x18005153a  mov     rcx, [rbp+57h+var_68]
0x18005153e  lea     rdx, [rbp+57h+var_78]
0x180051542  mov     rax, [rcx]
0x180051545  mov     rax, [rax+68h]
0x180051549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005154e  mov     ebx, eax
0x180051550  test    eax, eax
0x180051552  js      loc_180051698
0x180051558  mov     rax, [rbp+57h+var_A0]
0x18005155c  lea     rdx, ?AddTemplateCounter@WdcSysmonNode@@SAJPEAU_WDC_ENUM_CALL@@@Z; WdcSysmonNode::AddTemplateCounter(_WDC_ENUM_CALL *)
0x180051563  mov     r9, [rbp+57h+arg_18]
0x180051567  mov     r13d, 3
0x18005156d  mov     rcx, [rbp+57h+var_78]
0x180051571  mov     r8d, r13d
0x180051574  mov     [rsp+0D0h+var_A8], rdi
0x180051579  mov     [rsp+0D0h+ppv], rax
0x18005157e  call    ??$WdcForEach@UDICounterItem@@UICounters@@@@YAJPEAUICounters@@P6AJPEAU_WDC_ENUM_CALL@@@ZKZZ; WdcForEach<DICounterItem,ICounters>(ICounters *,long (*)(_WDC_ENUM_CALL *),ulong,...)
0x180051583  mov     ebx, eax
0x180051585  test    eax, eax
0x180051587  js      loc_180051698
0x18005158d  lea     rax, [rbp+57h+var_98]
0x180051591  xor     edx, edx; pUnkOuter
0x180051593  lea     r9, IID_IDataCollectorSetCollection; riid
0x18005159a  mov     [rsp+0D0h+ppv], rax; ppv
0x18005159f  lea     r8d, [r13+12h]; dwClsContext
0x1800515a3  lea     rcx, CLSID_DataCollectorSetCollection; rclsid
0x1800515aa  call    cs:__imp_CoCreateInstance
0x1800515b0  mov     ebx, eax
0x1800515b2  test    eax, eax
0x1800515b4  js      loc_180051698
0x1800515ba  mov     rcx, [rbp+57h+var_98]; struct IUnknown *
0x1800515be  call    ?WdcCoSetSecurity@@YAJPEAUIUnknown@@@Z; WdcCoSetSecurity(IUnknown *)
0x1800515c3  mov     ebx, eax
0x1800515c5  test    eax, eax
0x1800515c7  js      loc_180051698
0x1800515cd  mov     rcx, rdi; bstrString
0x1800515d0  call    cs:__imp_SysFreeString
0x1800515d6  lea     rcx, aService_0; "service\\*"
0x1800515dd  call    cs:__imp_SysAllocString
0x1800515e3  mov     rdi, rax
0x1800515e6  test    rax, rax
0x1800515e9  jz      loc_1800513F4
0x1800515ef  mov     rcx, [rbp+57h+var_98]
0x1800515f3  mov     r8, rdi
0x1800515f6  mov     rdx, [r14+30h]
0x1800515fa  mov     rax, [rcx]
0x1800515fd  mov     rax, [rax+70h]
0x180051601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051606  mov     ebx, eax
0x180051608  test    eax, eax
0x18005160a  js      loc_180051698
0x180051610  mov     ecx, 240h; Size
0x180051615  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005161a  mov     r9, [rbp+57h+arg_18]
0x18005161e  lea     r8, aService; "service"
0x180051625  mov     rdx, [r14+30h]
0x180051629  mov     rcx, rax
0x18005162c  mov     rax, [rbp+57h+var_98]
0x180051630  mov     [rsp+0D0h+var_A8], rax
0x180051635  mov     dword ptr [rsp+0D0h+ppv], r13d
0x18005163a  call    ??0WdcDataCollectorSetWizard@@QEAA@PEBG0PEAUIXMLDOMDocument@@W4WDC_WIZARD_MODE@@PEAUIDataCollectorSetCollection@@@Z; WdcDataCollectorSetWizard::WdcDataCollectorSetWizard(ushort const *,ushort const *,IXMLDOMDocument *,WDC_WIZARD_MODE,IDataCollectorSetCollection *)
0x18005163f  mov     rsi, rax
0x180051642  test    rax, rax
0x180051645  jnz     short loc_180051651
0x180051647  mov     ebx, 8007000Eh
0x18005164c  jmp     loc_180051362
0x180051651  lea     rdx, [rbp+57h+var_60]; HWND *
0x180051655  mov     rcx, r15; this
0x180051658  call    ?GetMainWindow@WdcConsoleManager@@QEAAJPEAPEAUHWND__@@@Z; WdcConsoleManager::GetMainWindow(HWND__ * *)
0x18005165d  mov     ebx, eax
0x18005165f  test    eax, eax
0x180051661  js      short loc_180051698
0x180051663  mov     rdx, [rbp+57h+var_60]; HWND
0x180051667  mov     rcx, rsi; this
0x18005166a  call    ?ShowWizard@WdcWizard@@QEAAJPEAUHWND__@@@Z; WdcWizard::ShowWizard(HWND__ *)
0x18005166f  mov     ebx, eax
0x180051671  test    eax, eax
0x180051673  js      short loc_180051698
0x180051675  cmp     eax, 1
0x180051678  jnz     short loc_18005167F
0x18005167a  mov     ebx, r12d
0x18005167d  jmp     short loc_1800516B9
0x18005167f  mov     rax, [rsi]
0x180051682  mov     rcx, rsi
0x180051685  mov     rdx, [rbp+57h+var_60]
0x180051689  mov     rax, [rax+10h]
0x18005168d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051692  mov     ebx, eax
0x180051694  test    eax, eax
0x180051696  jns     short loc_1800516B9
0x180051698  mov     dword ptr [rsp+0D0h+ppv], eax
0x18005169c  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800516a3  xor     r8d, r8d; int
0x1800516a6  lea     rdx, aWdcsysmonnodeC; "WdcSysmonNode::CreateDataCollectorSet"
  ... truncated ...
```
