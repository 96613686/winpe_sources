# WdcDataCollectorNode::UpdateAlertTaskSample(HWND__ *,ulong)

- ea: `0x180064d74`
- end: `0x180065498`
- name: `?UpdateAlertTaskSample@WdcDataCollectorNode@@AEAAJPEAUHWND__@@K@Z`
- size: `1828`
- prototype: `int(WdcDataCollectorNode *__hidden this, HWND, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800644c0`
- `0x1800647c0`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x1800122f0`
- `0x18001cb20`
- `0x18001ef84`
- `0x18003a3c0`
- `0x180040730`
- `0x180064d74`
- `0x180066e18`
- `0x18006a034`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800651c0`
- `KERNEL32!GetLastError` at `0x180065249`
- `KERNEL32!GetLastError` at `0x1800651c0`
- `KERNEL32!GetLastError` at `0x180065249`
- `KERNEL32!GetTimeFormatW` at `0x18006523f`
- `KERNEL32!GetTimeFormatW` at `0x18006523f`
- `KERNEL32!GetDateFormatW` at `0x1800651b6`
- `KERNEL32!GetDateFormatW` at `0x1800651b6`
- `KERNEL32!GetLocalTime` at `0x180065198`
- `KERNEL32!GetLocalTime` at `0x180065198`
- `USER32!GetWindowTextW` at `0x1800652f1`
- `USER32!GetWindowTextW` at `0x180065356`
- `USER32!GetWindowTextW` at `0x1800652f1`
- `USER32!GetWindowTextW` at `0x180065356`
- `USER32!SetWindowTextW` at `0x180065425`
- `USER32!SetWindowTextW` at `0x180065425`
- `USER32!GetDlgItem` at `0x1800652e2`
- `USER32!GetDlgItem` at `0x180065347`
- `USER32!GetDlgItem` at `0x180065419`
- `USER32!GetDlgItem` at `0x1800652e2`
- `USER32!GetDlgItem` at `0x180065347`
- `USER32!GetDlgItem` at `0x180065419`
- `USER32!LoadStringW` at `0x180064fbd`
- `USER32!LoadStringW` at `0x180065090`
- `USER32!LoadStringW` at `0x180064fbd`
- `USER32!LoadStringW` at `0x180065090`
- `OLEAUT32!__imp_SysAllocString` at `0x180064f0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180064f4c`
- `OLEAUT32!__imp_SysAllocString` at `0x180064fd9`
- `OLEAUT32!__imp_SysAllocString` at `0x180064ffc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800650ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800650cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18006513c`
- `OLEAUT32!__imp_SysAllocString` at `0x18006515f`
- `OLEAUT32!__imp_SysAllocString` at `0x180065282`
- `OLEAUT32!__imp_SysAllocString` at `0x1800652a5`
- `OLEAUT32!__imp_SysAllocString` at `0x18006530d`
- `OLEAUT32!__imp_SysAllocString` at `0x180065372`
- `OLEAUT32!__imp_SysAllocString` at `0x180064f0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180064f4c`
- `OLEAUT32!__imp_SysAllocString` at `0x180064fd9`
- `OLEAUT32!__imp_SysAllocString` at `0x180064ffc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800650ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800650cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18006513c`
- `OLEAUT32!__imp_SysAllocString` at `0x18006515f`
- `OLEAUT32!__imp_SysAllocString` at `0x180065282`
- `OLEAUT32!__imp_SysAllocString` at `0x1800652a5`
- `OLEAUT32!__imp_SysAllocString` at `0x18006530d`
- `OLEAUT32!__imp_SysAllocString` at `0x180065372`
- `OLEAUT32!__imp_SysFreeString` at `0x180064efe`
- `OLEAUT32!__imp_SysFreeString` at `0x180064fcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180064fef`
- `OLEAUT32!__imp_SysFreeString` at `0x18006509f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800650c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006512f`
- `OLEAUT32!__imp_SysFreeString` at `0x180065152`
- `OLEAUT32!__imp_SysFreeString` at `0x180065275`
- `OLEAUT32!__imp_SysFreeString` at `0x180065298`
- `OLEAUT32!__imp_SysFreeString` at `0x180065300`
- `OLEAUT32!__imp_SysFreeString` at `0x180065365`
- `OLEAUT32!__imp_SysFreeString` at `0x1800653d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18006543d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006544c`
- `OLEAUT32!__imp_SysFreeString` at `0x180064efe`
- `OLEAUT32!__imp_SysFreeString` at `0x180064fcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180064fef`
- `OLEAUT32!__imp_SysFreeString` at `0x18006509f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800650c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006512f`
- `OLEAUT32!__imp_SysFreeString` at `0x180065152`
- `OLEAUT32!__imp_SysFreeString` at `0x180065275`
- `OLEAUT32!__imp_SysFreeString` at `0x180065298`
- `OLEAUT32!__imp_SysFreeString` at `0x180065300`
- `OLEAUT32!__imp_SysFreeString` at `0x180065365`
- `OLEAUT32!__imp_SysFreeString` at `0x1800653d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18006543d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006544c`
- `OLEAUT32!__imp_VariantInit` at `0x180064dd5`
- `OLEAUT32!__imp_VariantInit` at `0x180064dd5`
- `OLEAUT32!__imp_VariantClear` at `0x18006542f`
- `OLEAUT32!__imp_VariantClear` at `0x18006542f`
- `ole32!CoCreateInstance` at `0x180064e15`
- `ole32!CoCreateInstance` at `0x180064e15`
- `PLA!PlaExpandTaskArguments` at `0x1800653fd`
- `PLA!PlaExpandTaskArguments` at `0x1800653fd`

## string_xrefs

- `0x180064e2f`: `WdcDataCollectorNode::UpdateAlertTaskSample`
- `0x18006503e`: `WdcDataCollectorNode::UpdateAlertTaskSample`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorNode::UpdateAlertTaskSample(WdcDataCollectorNode *this, HWND a2, int a3)
{
  OLECHAR *v4; // r14
  unsigned __int16 *v5; // rsi
  const char *v8; // rdx
  int v9; // r8d
  int v10; // ebx
  signed int v11; // edi
  struct IUnknown **v12; // rbx
  HRESULT Instance; // eax
  unsigned __int16 *v14; // rax
  OLECHAR *v15; // rax
  BSTR v16; // rax
  OLECHAR *v17; // rax
  BSTR v18; // rax
  OLECHAR *v19; // rax
  BSTR v20; // rax
  OLECHAR *v21; // rax
  BSTR v22; // rax
  signed int LastError; // eax
  signed int v24; // eax
  OLECHAR *v25; // rax
  BSTR v26; // rax
  HWND DlgItem; // rax
  OLECHAR *v28; // rax
  HWND v29; // rax
  OLECHAR *v30; // rax
  const WCHAR *v31; // rbx
  HWND v32; // rax
  const char *v33; // rdx
  int v34; // r8d
  LPVOID *ppv; // [rsp+20h] [rbp-69h]
  LPVOID *ppva; // [rsp+20h] [rbp-69h]
  unsigned int cchDate; // [rsp+28h] [rbp-61h]
  BSTR bstrString; // [rsp+30h] [rbp-59h] BYREF
  int cchTime; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int64 v41; // [rsp+40h] [rbp-49h] BYREF
  LPWSTR lpTimeStr; // [rsp+48h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-39h] BYREF
  VARIANT vDataSet; // [rsp+70h] [rbp-19h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp+7h] BYREF

  bstrString = 0;
  lpTimeStr = 0;
  v41 = 0;
  v4 = 0;
  cchTime = 0;
  v5 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  SystemTime = 0;
  VariantInit(&pvarg);
  v10 = a3 - 4602;
  if ( v10 && v10 != 2 )
  {
    v11 = 0;
    goto LABEL_55;
  }
  v12 = (struct IUnknown **)((char *)this + 488);
  if ( !*((_QWORD *)this + 61) )
  {
    Instance = CoCreateInstance(&CLSID_DataCollectorSet, 0, 0x15u, &IID_IDataCollectorSet, (LPVOID *)this + 61);
    v11 = Instance;
    if ( Instance < 0 )
      goto LABEL_6;
    Instance = WdcCoSetSecurity(*v12);
    v11 = Instance;
    if ( Instance < 0 )
      goto LABEL_6;
  }
  v14 = (unsigned __int16 *)WdcAlloc(0x800u, v8, v9);
  v5 = v14;
  if ( !v14 )
  {
LABEL_10:
    v11 = -2147024882;
    LODWORD(ppv) = -2147024882;
    goto LABEL_7;
  }
  *v14 = 0;
  Instance = StringCchCopyW(v14, 0x400u, *(const unsigned __int16 **)(*((_QWORD *)this + 57) + 544LL));
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  if ( !(unsigned int)WdcValidation::Ignore(*((WdcValidation **)this + 58), 0x836u) )
  {
    Instance = StringCchCatW(v5, 0x400u, L"/");
    v11 = Instance;
    if ( Instance < 0 )
      goto LABEL_6;
    Instance = StringCchCatW(v5, 0x400u, *((const unsigned __int16 **)this + 62));
    v11 = Instance;
    if ( Instance < 0 )
      goto LABEL_6;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v15 = SysAllocString(v5);
  if ( !v15 )
    goto LABEL_18;
  bstrString = v15;
  v16 = SysAllocString(L"name");
  v4 = v16;
  if ( !v16 )
  {
    LODWORD(ppv) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", ppv);
    v4 = 0;
    goto LABEL_10;
  }
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, BSTR))(*v12)->lpVtbl[21].Release)(*v12, v16, bstrString);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  LoadStringW(g_hInstance, 0x1Bu, v5, 1024);
  SysFreeString(bstrString);
  bstrString = 0;
  v17 = SysAllocString(v5);
  if ( !v17 )
    goto LABEL_18;
  bstrString = v17;
  SysFreeString(v4);
  v18 = SysAllocString(L"counter");
  v4 = v18;
  if ( !v18 )
  {
LABEL_24:
    LODWORD(ppv) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", ppv);
    LODWORD(ppva) = -2147024882;
    v11 = -2147024882;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectornode.cpp",
      "WdcDataCollectorNode::UpdateAlertTaskSample",
      0,
      L"FAILURE: 0x%08x",
      ppva);
    v4 = 0;
    goto LABEL_55;
  }
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, BSTR))(*v12)->lpVtbl[21].Release)(*v12, v18, bstrString);
  v11 = Instance;
  if ( Instance < 0 )
  {
LABEL_6:
    LODWORD(ppv) = Instance;
LABEL_7:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectornode.cpp",
      "WdcDataCollectorNode::UpdateAlertTaskSample",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_55;
  }
  LoadStringW(g_hInstance, 0x48u, v5, 1024);
  SysFreeString(bstrString);
  bstrString = 0;
  v19 = SysAllocString(v5);
  if ( !v19 )
  {
LABEL_18:
    LODWORD(ppv) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", ppv);
    goto LABEL_10;
  }
  bstrString = v19;
  SysFreeString(v4);
  v20 = SysAllocString(L"threshold");
  v4 = v20;
  if ( !v20 )
    goto LABEL_24;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, BSTR))(*v12)->lpVtbl[21].Release)(*v12, v20, bstrString);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  Instance = StringCchPrintfW(v5, 0x400u, L"%d", 55);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  SysFreeString(bstrString);
  bstrString = 0;
  v21 = SysAllocString(v5);
  if ( !v21 )
    goto LABEL_18;
  bstrString = v21;
  SysFreeString(v4);
  v22 = SysAllocString(L"value");
  v4 = v22;
  if ( !v22 )
    goto LABEL_24;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, BSTR))(*v12)->lpVtbl[21].Release)(*v12, v22, bstrString);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  GetLocalTime(&SystemTime);
  if ( GetDateFormatW(0x400u, 1u, &SystemTime, 0, v5, 1024) <= 0 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( !LastError )
      goto LABEL_62;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
      goto LABEL_63;
  }
  Instance = StringCchCatExW(v5, 0x400u, L" - ", &lpTimeStr, &v41, cchDate);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  Instance = UIntPtrToInt(v41, &cchTime);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  if ( GetTimeFormatW(0x400u, 0, &SystemTime, 0, lpTimeStr, cchTime) <= 0 )
  {
    v24 = GetLastError();
    v11 = v24;
    if ( v24 )
    {
      if ( v24 > 0 )
        v11 = (unsigned __int16)v24 | 0x80070000;
      if ( v11 >= 0 )
        goto LABEL_45;
LABEL_63:
      Instance = v11;
      goto LABEL_6;
    }
LABEL_62:
    v11 = -2147467259;
    goto LABEL_63;
  }
LABEL_45:
  SysFreeString(bstrString);
  bstrString = 0;
  v25 = SysAllocString(v5);
  if ( !v25 )
    goto LABEL_18;
  bstrString = v25;
  SysFreeString(v4);
  v26 = SysAllocString(L"date");
  v4 = v26;
  if ( !v26 )
    goto LABEL_24;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, BSTR))(*v12)->lpVtbl[21].Release)(*v12, v26, bstrString);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  DlgItem = GetDlgItem(a2, 4602);
  GetWindowTextW(DlgItem, v5, 1024);
  SysFreeString(bstrString);
  bstrString = 0;
  v28 = SysAllocString(v5);
  if ( !v28 )
    goto LABEL_18;
  bstrString = v28;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *))(*v12)->lpVtbl[15].QueryInterface)(*v12, v28);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  v29 = GetDlgItem(a2, 4604);
  GetWindowTextW(v29, v5, 1024);
  SysFreeString(bstrString);
  bstrString = 0;
  v30 = SysAllocString(v5);
  if ( !v30 )
    goto LABEL_18;
  bstrString = v30;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *))(*v12)->lpVtbl[15].Release)(*v12, v30);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, CY *))(*v12)->lpVtbl->QueryInterface)(
               *v12,
               &IID_IDispatch,
               &pvarg.cyVal);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  pvarg.vt = 9;
  SysFreeString(bstrString);
  bstrString = 0;
  vDataSet = pvarg;
  Instance = PlaExpandTaskArguments(&vDataSet, &bstrString);
  v11 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  v31 = bstrString;
  v32 = GetDlgItem(a2, 4605);
  SetWindowTextW(v32, v31);
LABEL_55:
  VariantClear(&pvarg);
  if ( v4 )
    SysFreeString(v4);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v5 )
    WdcFree(v5, v33, v34);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180064d74  mov     [rsp-8+arg_10], rbx
0x180064d79  push    rbp
0x180064d7a  push    rsi
0x180064d7b  push    rdi
0x180064d7c  push    r12
0x180064d7e  push    r13
0x180064d80  push    r14
0x180064d82  push    r15
0x180064d84  lea     rbp, [rsp-27h]
0x180064d89  sub     rsp, 0B0h
0x180064d90  mov     rax, cs:__security_cookie
0x180064d97  xor     rax, rsp
0x180064d9a  mov     [rbp+57h+var_40], rax
0x180064d9e  xor     r13d, r13d
0x180064da1  xorps   xmm0, xmm0
0x180064da4  mov     r15, rcx
0x180064da7  mov     [rbp+57h+bstrString], r13
0x180064dab  xor     eax, eax
0x180064dad  mov     [rbp+57h+lpTimeStr], r13
0x180064db1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180064db5  mov     [rbp+57h+var_A0], r13
0x180064db9  mov     r14d, r13d
0x180064dbc  mov     [rbp+57h+cchTime], r13d
0x180064dc0  mov     esi, r13d
0x180064dc3  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180064dc7  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180064dcb  mov     ebx, r8d
0x180064dce  mov     r12, rdx
0x180064dd1  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180064dd5  call    cs:__imp_VariantInit
0x180064ddb  sub     ebx, 11FAh
0x180064de1  jz      short loc_180064DF0
0x180064de3  cmp     ebx, 2
0x180064de6  jz      short loc_180064DF0
0x180064de8  mov     edi, r13d
0x180064deb  jmp     loc_18006542B
0x180064df0  lea     rbx, [r15+1E8h]
0x180064df7  cmp     [rbx], r13
0x180064dfa  jnz     short loc_180064E55
0x180064dfc  xor     edx, edx; pUnkOuter
0x180064dfe  mov     [rsp+0E0h+ppv], rbx; ppv
0x180064e03  lea     r9, IID_IDataCollectorSet; riid
0x180064e0a  lea     rcx, CLSID_DataCollectorSet; rclsid
0x180064e11  lea     r8d, [rdx+15h]; dwClsContext
0x180064e15  call    cs:__imp_CoCreateInstance
0x180064e1b  mov     edi, eax
0x180064e1d  test    eax, eax
0x180064e1f  jns     short loc_180064E47
0x180064e21  mov     dword ptr [rsp+0E0h+ppv], eax
0x180064e25  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180064e2c  xor     r8d, r8d; int
0x180064e2f  lea     rdx, aWdcdatacollect_90; "WdcDataCollectorNode::UpdateAlertTaskSa"...
0x180064e36  lea     rcx, aBaseDiagnosisP_17; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180064e3d  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180064e42  jmp     loc_18006542B
0x180064e47  mov     rcx, [rbx]; struct IUnknown *
0x180064e4a  call    ?WdcCoSetSecurity@@YAJPEAUIUnknown@@@Z; WdcCoSetSecurity(IUnknown *)
0x180064e4f  mov     edi, eax
0x180064e51  test    eax, eax
0x180064e53  js      short loc_180064E21
0x180064e55  mov     ecx, 800h; dwBytes
0x180064e5a  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180064e5f  mov     rsi, rax
0x180064e62  test    rax, rax
0x180064e65  jnz     short loc_180064E74
0x180064e67  mov     ebx, 8007000Eh
0x180064e6c  mov     edi, ebx
0x180064e6e  mov     dword ptr [rsp+0E0h+ppv], ebx
0x180064e72  jmp     short loc_180064E25
0x180064e74  mov     [rax], r13w
0x180064e78  mov     edx, 400h; unsigned __int64
0x180064e7d  mov     r8, [r15+1C8h]
0x180064e84  mov     rcx, rsi; unsigned __int16 *
0x180064e87  mov     r8, [r8+220h]; unsigned __int16 *
0x180064e8e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180064e93  mov     edi, eax
0x180064e95  test    eax, eax
0x180064e97  js      short loc_180064E21
0x180064e99  mov     rcx, [r15+1D0h]; this
0x180064ea0  mov     edx, 836h; unsigned int
0x180064ea5  call    ?Ignore@WdcValidation@@QEAAHI@Z; WdcValidation::Ignore(uint)
0x180064eaa  test    eax, eax
0x180064eac  jnz     short loc_180064EEF
0x180064eae  lea     r8, asc_180090628; "/"
0x180064eb5  mov     edx, 400h; unsigned __int64
0x180064eba  mov     rcx, rsi; unsigned __int16 *
0x180064ebd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180064ec2  mov     edi, eax
0x180064ec4  test    eax, eax
0x180064ec6  js      loc_180064E21
0x180064ecc  mov     r8, [r15+1F0h]; unsigned __int16 *
0x180064ed3  mov     rcx, rsi; unsigned __int16 *
0x180064ed6  mov     r15d, 400h
0x180064edc  mov     edx, r15d; unsigned __int64
0x180064edf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180064ee4  mov     edi, eax
0x180064ee6  test    eax, eax
0x180064ee8  jns     short loc_180064EF5
0x180064eea  jmp     loc_180064E21
0x180064eef  mov     r15d, 400h
0x180064ef5  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180064ef9  test    rcx, rcx
0x180064efc  jz      short loc_180064F08
0x180064efe  call    cs:__imp_SysFreeString
0x180064f04  mov     [rbp+57h+bstrString], r13
0x180064f08  mov     rcx, rsi; psz
0x180064f0b  call    cs:__imp_SysAllocString
0x180064f11  test    rax, rax
0x180064f14  jnz     short loc_180064F41
0x180064f16  mov     ebx, 8007000Eh
0x180064f1b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180064f22  xor     r8d, r8d; int
0x180064f25  mov     dword ptr [rsp+0E0h+ppv], ebx
0x180064f29  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180064f30  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180064f37  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180064f3c  jmp     loc_180064E6C
0x180064f41  mov     [rbp+57h+bstrString], rax
0x180064f45  lea     rcx, aName_0; "name"
0x180064f4c  call    cs:__imp_SysAllocString
0x180064f52  mov     r14, rax
0x180064f55  test    rax, rax
0x180064f58  jnz     short loc_180064F88
0x180064f5a  mov     ebx, 8007000Eh
0x180064f5f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180064f66  xor     r8d, r8d; int
0x180064f69  mov     dword ptr [rsp+0E0h+ppv], ebx
0x180064f6d  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180064f74  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180064f7b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180064f80  mov     r14, r13
0x180064f83  jmp     loc_180064E6C
0x180064f88  mov     rcx, [rbx]
0x180064f8b  mov     rdx, r14
0x180064f8e  mov     r8, [rbp+57h+bstrString]
0x180064f92  mov     rax, [rcx]
0x180064f95  mov     rax, [rax+208h]
0x180064f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064fa1  mov     edi, eax
0x180064fa3  test    eax, eax
0x180064fa5  js      loc_180064E21
0x180064fab  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180064fb2  mov     r9d, r15d; cchBufferMax
0x180064fb5  mov     r8, rsi; lpBuffer
0x180064fb8  mov     edx, 1Bh; uID
0x180064fbd  call    cs:__imp_LoadStringW
0x180064fc3  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180064fc7  test    rcx, rcx
0x180064fca  jz      short loc_180064FD6
0x180064fcc  call    cs:__imp_SysFreeString
0x180064fd2  mov     [rbp+57h+bstrString], r13
0x180064fd6  mov     rcx, rsi; psz
0x180064fd9  call    cs:__imp_SysAllocString
0x180064fdf  test    rax, rax
0x180064fe2  jz      loc_180064F16
0x180064fe8  mov     [rbp+57h+bstrString], rax
0x180064fec  mov     rcx, r14; bstrString
0x180064fef  call    cs:__imp_SysFreeString
0x180064ff5  lea     rcx, aCounter_0; "counter"
0x180064ffc  call    cs:__imp_SysAllocString
0x180065002  mov     r14, rax
0x180065005  test    rax, rax
0x180065008  jnz     short loc_18006505B
0x18006500a  mov     ebx, 8007000Eh
0x18006500f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180065016  xor     r8d, r8d; int
0x180065019  mov     dword ptr [rsp+0E0h+ppv], ebx
0x18006501d  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180065024  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18006502b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180065030  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180065037  mov     dword ptr [rsp+0E0h+ppv], ebx
0x18006503b  xor     r8d, r8d; int
0x18006503e  lea     rdx, aWdcdatacollect_90; "WdcDataCollectorNode::UpdateAlertTaskSa"...
0x180065045  lea     rcx, aBaseDiagnosisP_17; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18006504c  mov     edi, ebx
0x18006504e  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180065053  mov     r14, r13
0x180065056  jmp     loc_18006542B
0x18006505b  mov     rcx, [rbx]
0x18006505e  mov     rdx, r14
0x180065061  mov     r8, [rbp+57h+bstrString]
0x180065065  mov     rax, [rcx]
0x180065068  mov     rax, [rax+208h]
0x18006506f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065074  mov     edi, eax
0x180065076  test    eax, eax
0x180065078  js      loc_180064E21
0x18006507e  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180065085  mov     r9d, r15d; cchBufferMax
0x180065088  mov     r8, rsi; lpBuffer
0x18006508b  mov     edx, 48h ; 'H'; uID
0x180065090  call    cs:__imp_LoadStringW
0x180065096  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18006509a  test    rcx, rcx
0x18006509d  jz      short loc_1800650A9
0x18006509f  call    cs:__imp_SysFreeString
0x1800650a5  mov     [rbp+57h+bstrString], r13
0x1800650a9  mov     rcx, rsi; psz
0x1800650ac  call    cs:__imp_SysAllocString
0x1800650b2  test    rax, rax
0x1800650b5  jz      loc_180064F16
0x1800650bb  mov     [rbp+57h+bstrString], rax
0x1800650bf  mov     rcx, r14; bstrString
0x1800650c2  call    cs:__imp_SysFreeString
0x1800650c8  lea     rcx, aThreshold; "threshold"
0x1800650cf  call    cs:__imp_SysAllocString
0x1800650d5  mov     r14, rax
0x1800650d8  test    rax, rax
0x1800650db  jz      loc_18006500A
0x1800650e1  mov     rcx, [rbx]
0x1800650e4  mov     rdx, r14
0x1800650e7  mov     r8, [rbp+57h+bstrString]
0x1800650eb  mov     rax, [rcx]
0x1800650ee  mov     rax, [rax+208h]
0x1800650f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800650fa  mov     edi, eax
0x1800650fc  test    eax, eax
0x1800650fe  js      loc_180064E21
0x180065104  mov     r9d, 37h ; '7'
0x18006510a  lea     r8, aD; "%d"
0x180065111  mov     rdx, r15; unsigned __int64
0x180065114  mov     rcx, rsi; unsigned __int16 *
0x180065117  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006511c  mov     edi, eax
0x18006511e  test    eax, eax
0x180065120  js      loc_180064E21
0x180065126  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18006512a  test    rcx, rcx
0x18006512d  jz      short loc_180065139
0x18006512f  call    cs:__imp_SysFreeString
0x180065135  mov     [rbp+57h+bstrString], r13
0x180065139  mov     rcx, rsi; psz
0x18006513c  call    cs:__imp_SysAllocString
0x180065142  test    rax, rax
0x180065145  jz      loc_180064F16
0x18006514b  mov     [rbp+57h+bstrString], rax
0x18006514f  mov     rcx, r14; bstrString
0x180065152  call    cs:__imp_SysFreeString
0x180065158  lea     rcx, aValue; "value"
0x18006515f  call    cs:__imp_SysAllocString
0x180065165  mov     r14, rax
0x180065168  test    rax, rax
0x18006516b  jz      loc_18006500A
0x180065171  mov     rcx, [rbx]
0x180065174  mov     rdx, r14
0x180065177  mov     r8, [rbp+57h+bstrString]
0x18006517b  mov     rax, [rcx]
0x18006517e  mov     rax, [rax+208h]
0x180065185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006518a  mov     edi, eax
0x18006518c  test    eax, eax
0x18006518e  js      loc_180064E21
0x180065194  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180065198  call    cs:__imp_GetLocalTime
0x18006519e  xor     r9d, r9d; lpFormat
0x1800651a1  mov     [rsp+0E0h+cchDate], r15d; unsigned int
0x1800651a6  lea     r8, [rbp+57h+SystemTime]; lpDate
0x1800651aa  mov     [rsp+0E0h+ppv], rsi; lpDateStr
0x1800651af  mov     ecx, r15d; Locale
0x1800651b2  lea     edx, [r9+1]; dwFlags
0x1800651b6  call    cs:__imp_GetDateFormatW
0x1800651bc  test    eax, eax
0x1800651be  jg      short loc_1800651E3
0x1800651c0  call    cs:__imp_GetLastError
0x1800651c6  mov     edi, eax
0x1800651c8  test    eax, eax
0x1800651ca  jz      loc_18006548C
0x1800651d0  jle     short loc_1800651DB
0x1800651d2  movzx   edi, ax
0x1800651d5  or      edi, 80070000h
0x1800651db  test    edi, edi
0x1800651dd  js      loc_180065491
0x1800651e3  lea     rax, [rbp+57h+var_A0]
0x1800651e7  mov     rdx, r15; unsigned __int64
0x1800651ea  lea     r9, [rbp+57h+lpTimeStr]; unsigned __int16 **
0x1800651ee  mov     [rsp+0E0h+ppv], rax; unsigned __int64 *
0x1800651f3  lea     r8, asc_180094540; " - "
0x1800651fa  mov     rcx, rsi; unsigned __int16 *
0x1800651fd  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180065202  mov     edi, eax
0x180065204  test    eax, eax
0x180065206  js      loc_180064E21
0x18006520c  mov     rcx, [rbp+57h+var_A0]; unsigned __int64
0x180065210  lea     rdx, [rbp+57h+cchTime]; int *
0x180065214  call    ?UIntPtrToInt@@YAJ_KPEAH@Z; UIntPtrToInt(unsigned __int64,int *)
0x180065219  mov     edi, eax
0x18006521b  test    eax, eax
0x18006521d  js      loc_180064E21
0x180065223  mov     eax, [rbp+57h+cchTime]
0x180065226  lea     r8, [rbp+57h+SystemTime]; lpTime
0x18006522a  mov     [rsp+0E0h+cchDate], eax; cchTime
0x18006522e  xor     r9d, r9d; lpFormat
0x180065231  mov     rax, [rbp+57h+lpTimeStr]
0x180065235  xor     edx, edx; dwFlags
0x180065237  mov     ecx, r15d; Locale
0x18006523a  mov     [rsp+0E0h+ppv], rax; lpTimeStr
0x18006523f  call    cs:__imp_GetTimeFormatW
0x180065245  test    eax, eax
0x180065247  jg      short loc_18006526C
  ... truncated ...
```
