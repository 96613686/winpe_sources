# WdcReportFolder::CommitView(WdcConsoleManager *,WdcSysmonNode *)

- ea: `0x180026b48`
- end: `0x180026f3b`
- name: `?CommitView@WdcReportFolder@@QEAAJPEAVWdcConsoleManager@@PEAVWdcSysmonNode@@@Z`
- size: `1011`
- prototype: `__int64 __fastcall(unsigned __int16 **this, struct WdcConsoleManager *, struct WdcSysmonNode *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004f980`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x180026b48`
- `0x1800373f0`
- `0x180049054`
- `0x18004befc`
- `0x180051ecc`
- `0x1800571b4`
- `0x180066ed8`
- `0x180067730`
- `0x180068f70`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026d94`
- `KERNEL32!GetLastError` at `0x180026d94`
- `KERNEL32!DeleteFileW` at `0x180026d8a`
- `KERNEL32!DeleteFileW` at `0x180026e57`
- `KERNEL32!DeleteFileW` at `0x180026d8a`
- `KERNEL32!DeleteFileW` at `0x180026e57`
- `OLEAUT32!__imp_SysAllocString` at `0x180026c1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180026d22`
- `OLEAUT32!__imp_SysAllocString` at `0x180026c1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180026d22`
- `OLEAUT32!__imp_SysFreeString` at `0x180026eb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180026ec8`
- `OLEAUT32!__imp_SysFreeString` at `0x180026eb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180026ec8`
- `OLEAUT32!__imp_VariantInit` at `0x180026b9d`
- `OLEAUT32!__imp_VariantInit` at `0x180026b9d`
- `OLEAUT32!__imp_VariantClear` at `0x180026c12`
- `OLEAUT32!__imp_VariantClear` at `0x180026e96`
- `OLEAUT32!__imp_VariantClear` at `0x180026c12`
- `OLEAUT32!__imp_VariantClear` at `0x180026e96`

## string_xrefs

- `0x180026e05`: `WdcReportFolder::CommitView`
- `0x180026e3e`: `WdcReportFolder::CommitView`

## pseudocode

```c
__int64 __fastcall WdcReportFolder::CommitView(
        unsigned __int16 **this,
        struct WdcConsoleManager *a2,
        struct WdcSysmonNode *a3)
{
  unsigned __int16 *v6; // rsi
  OLECHAR *v7; // r15
  int MainWindow; // eax
  signed int DataSet; // ebx
  const char *v10; // rdx
  int v11; // r8d
  const char *v12; // rdx
  int v13; // r8d
  BSTR v14; // rax
  int v15; // eax
  BSTR v16; // rax
  signed int LastError; // eax
  _QWORD **v18; // rdi
  _QWORD *v19; // r8
  _QWORD *v20; // rcx
  const char *v21; // rdx
  int v22; // r8d
  unsigned __int16 *v24; // [rsp+20h] [rbp-39h]
  unsigned __int16 *v25; // [rsp+20h] [rbp-39h]
  int v26; // [rsp+40h] [rbp-19h]
  struct ISystemMonitor2 *v27; // [rsp+50h] [rbp-9h] BYREF
  struct IXMLDOMDocument *v28; // [rsp+58h] [rbp-1h] BYREF
  struct IDataCollectorSet *v29; // [rsp+60h] [rbp+7h] BYREF
  HWND v30; // [rsp+68h] [rbp+Fh] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp+17h] BYREF
  BSTR bstrString; // [rsp+D8h] [rbp+7Fh] BYREF

  v30 = 0;
  bstrString = 0;
  v27 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v28 = 0;
  v29 = 0;
  v6 = 0;
  v7 = 0;
  VariantInit(&pvarg);
  MainWindow = WdcConsoleManager::GetMainWindow(a2, &v30);
  DataSet = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_22;
  MainWindow = WdcSysmonNode::GetSystemMonitor(a3, a2, &v27);
  DataSet = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_22;
  v6 = (unsigned __int16 *)WdcAlloc(0x800u, v10, v11);
  if ( !v6 )
  {
    DataSet = -2147024882;
    LODWORD(v24) = -2147024882;
LABEL_23:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\reportnode.cpp",
      "WdcReportFolder::CommitView",
      0,
      L"FAILURE: 0x%08x",
      v24);
    goto LABEL_24;
  }
  *v6 = 0;
  MainWindow = WdcGetTempFileName(v6, v12, v13);
  DataSet = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_22;
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  v14 = SysAllocString(v6);
  if ( !v14 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
      "WdcAssignString",
      0,
      L"FAILURE: 0x%08x",
      -2147024882);
    LODWORD(v25) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", v25);
    LODWORD(v24) = -2147024882;
    DataSet = -2147024882;
    goto LABEL_23;
  }
  pvarg.llVal = (LONGLONG)v14;
  pvarg.vt = 8;
  v15 = ((__int64 (__fastcall *)(struct ISystemMonitor2 *, BSTR, __int64))v27->lpVtbl->SaveAs)(v27, v14, 1);
  DataSet = v15;
  if ( v15 < 0 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\reportnode.cpp",
      "WdcReportFolder::CommitView",
      0,
      L"FAILURE: 0x%08x",
      v15);
LABEL_24:
    WdcShowErrorMessage(v30, 0x32Eu, DataSet);
    goto LABEL_32;
  }
  DataSet = WdcCreateXmlDocument(&v28, &pvarg, 0, 0);
  if ( DataSet < 0
    || (DataSet = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, BSTR *))v28->lpVtbl->get_xml)(v28, &bstrString),
        DataSet < 0)
    || (DataSet = WdcDataCollectorSetNode::GetDataSet((WdcDataCollectorSetNode *)this, 0, &v29), DataSet < 0) )
  {
LABEL_26:
    LODWORD(v24) = DataSet;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\reportnode.cpp",
      "WdcReportFolder::CommitView",
      0,
      L"FAILURE: 0x%08x",
      v24);
    DeleteFileW(v6);
    goto LABEL_24;
  }
  v16 = SysAllocString(L"PerformanceMonitorView");
  v7 = v16;
  if ( !v16 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
      "WdcAssignString",
      0,
      L"FAILURE: 0x%08x",
      -2147024882);
    DataSet = -2147024882;
    goto LABEL_26;
  }
  DataSet = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR, BSTR))v29->lpVtbl->SetValue)(
              v29,
              v16,
              bstrString);
  if ( DataSet < 0 )
    goto LABEL_26;
  if ( !DeleteFileW(v6) )
  {
    LastError = GetLastError();
    DataSet = LastError;
    if ( !LastError )
    {
      DataSet = -2147467259;
      goto LABEL_26;
    }
    if ( LastError > 0 )
      DataSet = (unsigned __int16)LastError | 0x80070000;
    if ( DataSet < 0 )
      goto LABEL_26;
  }
  MainWindow = WdcCommitDataSet(v30, v29, this[67], this[68], this[6], 0, 0, plaModify, v26);
  DataSet = MainWindow;
  if ( MainWindow < 0 )
  {
LABEL_22:
    LODWORD(v24) = MainWindow;
    goto LABEL_23;
  }
  v18 = (_QWORD **)(this + 9);
  v19 = *v18;
  while ( v18 != v19 )
  {
    v20 = v19;
    v19 = (_QWORD *)*v19;
    if ( *((_DWORD *)v20 + 106) == 1 )
      WdcBaseNode::SetDirty((WdcBaseNode *)v20[132], 1);
  }
LABEL_32:
  VariantClear(&pvarg);
  if ( v6 )
    WdcFree(v6, v21, v22);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v7 )
    SysFreeString(v7);
  if ( v27 )
  {
    ((void (__fastcall *)(struct ISystemMonitor2 *))v27->lpVtbl->Release)(v27);
    v27 = 0;
  }
  if ( v28 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))v28->lpVtbl->Release)(v28);
    v28 = 0;
  }
  if ( v29 )
    ((void (__fastcall *)(struct IDataCollectorSet *))v29->lpVtbl->Release)(v29);
  return (unsigned int)DataSet;
}

```

## disassembly

```asm
0x180026b48  mov     [rsp-8+arg_0], rbx
0x180026b4d  mov     [rsp-8+arg_8], rsi
0x180026b52  push    rbp
0x180026b53  push    rdi
0x180026b54  push    r12
0x180026b56  push    r14
0x180026b58  push    r15
0x180026b5a  lea     rbp, [rsp-37h]
0x180026b5f  sub     rsp, 90h
0x180026b66  xor     eax, eax
0x180026b68  mov     [rbp+57h+var_48], 0
0x180026b70  mov     rdi, rcx
0x180026b73  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180026b77  xorps   xmm0, xmm0
0x180026b7a  mov     [rbp+57h+bstrString], rax
0x180026b7e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180026b82  mov     [rbp+57h+var_60], rax
0x180026b86  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180026b8a  mov     [rbp+57h+var_58], rax
0x180026b8e  mov     r12, r8
0x180026b91  mov     [rbp+57h+var_50], rax
0x180026b95  mov     r14, rdx
0x180026b98  xor     esi, esi
0x180026b9a  xor     r15d, r15d
0x180026b9d  call    cs:__imp_VariantInit
0x180026ba3  lea     rdx, [rbp+57h+var_48]; HWND *
0x180026ba7  mov     rcx, r14; this
0x180026baa  call    ?GetMainWindow@WdcConsoleManager@@QEAAJPEAPEAUHWND__@@@Z; WdcConsoleManager::GetMainWindow(HWND__ * *)
0x180026baf  mov     ebx, eax
0x180026bb1  test    eax, eax
0x180026bb3  js      loc_180026DF7
0x180026bb9  lea     r8, [rbp+57h+var_60]; struct ISystemMonitor2 **
0x180026bbd  mov     rdx, r14; struct WdcConsoleManager *
0x180026bc0  mov     rcx, r12; this
0x180026bc3  call    ?GetSystemMonitor@WdcSysmonNode@@QEAAJPEAVWdcConsoleManager@@PEAPEAUISystemMonitor2@@@Z; WdcSysmonNode::GetSystemMonitor(WdcConsoleManager *,ISystemMonitor2 * *)
0x180026bc8  mov     ebx, eax
0x180026bca  test    eax, eax
0x180026bcc  js      loc_180026DF7
0x180026bd2  mov     ecx, 800h; dwBytes
0x180026bd7  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180026bdc  mov     rsi, rax
0x180026bdf  test    rax, rax
0x180026be2  jnz     short loc_180026BF7
0x180026be4  mov     r14d, 8007000Eh
0x180026bea  mov     ebx, r14d
0x180026bed  mov     dword ptr [rsp+0B0h+var_90], r14d
0x180026bf2  jmp     loc_180026DFB
0x180026bf7  xor     eax, eax
0x180026bf9  mov     rcx, rsi; unsigned __int16 *
0x180026bfc  mov     [rsi], ax
0x180026bff  call    ?WdcGetTempFileName@@YAJPEAGK@Z; WdcGetTempFileName(ushort *,ulong)
0x180026c04  mov     ebx, eax
0x180026c06  test    eax, eax
0x180026c08  js      loc_180026DF7
0x180026c0e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180026c12  call    cs:__imp_VariantClear
0x180026c18  mov     rcx, rsi; psz
0x180026c1b  mov     qword ptr [rbp+57h+pvarg+8], r15
0x180026c1f  call    cs:__imp_SysAllocString
0x180026c25  mov     rdx, rax
0x180026c28  test    rax, rax
0x180026c2b  jnz     short loc_180026C86
0x180026c2d  lea     rdi, aFailure0x08x; "FAILURE: 0x%08x"
0x180026c34  mov     r14d, 8007000Eh
0x180026c3a  mov     r9, rdi; unsigned __int16 *
0x180026c3d  mov     dword ptr [rsp+0B0h+var_90], r14d
0x180026c42  xor     r8d, r8d; int
0x180026c45  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180026c4c  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180026c53  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180026c58  mov     r9, rdi; unsigned __int16 *
0x180026c5b  mov     dword ptr [rsp+0B0h+var_90], r14d
0x180026c60  xor     r8d, r8d; int
0x180026c63  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180026c6a  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180026c71  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180026c76  mov     r9, rdi
0x180026c79  mov     dword ptr [rsp+0B0h+var_90], r14d
0x180026c7e  mov     ebx, r14d
0x180026c81  jmp     loc_180026E02
0x180026c86  mov     qword ptr [rbp+57h+pvarg+8], rdx
0x180026c8a  mov     eax, 8
0x180026c8f  mov     word ptr [rbp+57h+pvarg], ax
0x180026c93  mov     rcx, [rbp+57h+var_60]
0x180026c97  mov     r14d, 1
0x180026c9d  mov     r8d, r14d
0x180026ca0  mov     rax, [rcx]
0x180026ca3  mov     rax, [rax+2D0h]
0x180026caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026caf  xor     r8d, r8d; unsigned __int16 *
0x180026cb2  mov     ebx, eax
0x180026cb4  test    eax, eax
0x180026cb6  jns     short loc_180026CC8
0x180026cb8  mov     dword ptr [rsp+0B0h+var_90], eax
0x180026cbc  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180026cc3  jmp     loc_180026E05
0x180026cc8  xor     r9d, r9d; struct IXMLDOMParseError **
0x180026ccb  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180026ccf  lea     rcx, [rbp+57h+var_58]; struct IXMLDOMDocument **
0x180026cd3  call    ?WdcCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@PEAUtagVARIANT@@PEAGPEAPEAUIXMLDOMParseError@@@Z; WdcCreateXmlDocument(IXMLDOMDocument * *,tagVARIANT *,ushort *,IXMLDOMParseError * *)
0x180026cd8  mov     ebx, eax
0x180026cda  test    eax, eax
0x180026cdc  js      loc_180026E30
0x180026ce2  mov     rcx, [rbp+57h+var_58]
0x180026ce6  lea     rdx, [rbp+57h+bstrString]
0x180026cea  mov     rax, [rcx]
0x180026ced  mov     rax, [rax+110h]
0x180026cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cf9  mov     ebx, eax
0x180026cfb  test    eax, eax
0x180026cfd  js      loc_180026E30
0x180026d03  lea     r8, [rbp+57h+var_50]; struct IDataCollectorSet **
0x180026d07  xor     edx, edx; int
0x180026d09  mov     rcx, rdi; this
0x180026d0c  call    ?GetDataSet@WdcDataCollectorSetNode@@IEAAJHPEAPEAUIDataCollectorSet@@@Z; WdcDataCollectorSetNode::GetDataSet(int,IDataCollectorSet * *)
0x180026d11  mov     ebx, eax
0x180026d13  test    eax, eax
0x180026d15  js      loc_180026E30
0x180026d1b  lea     rcx, aPerformancemon; "PerformanceMonitorView"
0x180026d22  call    cs:__imp_SysAllocString
0x180026d28  mov     r15, rax
0x180026d2b  test    rax, rax
0x180026d2e  jnz     short loc_180026D63
0x180026d30  lea     rdi, aFailure0x08x; "FAILURE: 0x%08x"
0x180026d37  mov     r14d, 8007000Eh
0x180026d3d  mov     r9, rdi; unsigned __int16 *
0x180026d40  mov     dword ptr [rsp+0B0h+var_90], r14d
0x180026d45  xor     r8d, r8d; int
0x180026d48  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180026d4f  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180026d56  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180026d5b  mov     ebx, r14d
0x180026d5e  jmp     loc_180026E37
0x180026d63  mov     rcx, [rbp+57h+var_50]
0x180026d67  mov     rdx, r15
0x180026d6a  mov     r8, [rbp+57h+bstrString]
0x180026d6e  mov     rax, [rcx]
0x180026d71  mov     rax, [rax+208h]
0x180026d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d7d  mov     ebx, eax
0x180026d7f  test    eax, eax
0x180026d81  js      loc_180026E30
0x180026d87  mov     rcx, rsi; lpFileName
0x180026d8a  call    cs:__imp_DeleteFileW
0x180026d90  test    eax, eax
0x180026d92  jnz     short loc_180026DB3
0x180026d94  call    cs:__imp_GetLastError
0x180026d9a  mov     ebx, eax
0x180026d9c  test    eax, eax
0x180026d9e  jz      loc_180026E2B
0x180026da4  jle     short loc_180026DAF
0x180026da6  movzx   ebx, ax
0x180026da9  or      ebx, 80070000h
0x180026daf  test    ebx, ebx
0x180026db1  js      short loc_180026E30
0x180026db3  mov     rax, [rdi+30h]
0x180026db7  mov     r9, [rdi+220h]; unsigned __int16 *
0x180026dbe  mov     r8, [rdi+218h]; unsigned __int16 *
0x180026dc5  mov     rdx, [rbp+57h+var_50]; struct IDataCollectorSet *
0x180026dc9  mov     rcx, [rbp+57h+var_48]; HWND
0x180026dcd  mov     [rsp+0B0h+var_78], 2; enum __MIDL___MIDL_itf_pla_0001_0043_0007
0x180026dd5  mov     [rsp+0B0h+var_80], 0; unsigned __int16 **
0x180026dde  mov     [rsp+0B0h+var_88], 0; unsigned __int16 **
0x180026de7  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x180026dec  call    ?WdcCommitDataSet@@YAJPEAUHWND__@@PEAUIDataCollectorSet@@PEAG22PEAPEAG3W4__MIDL___MIDL_itf_pla_0001_0043_0007@@H@Z; WdcCommitDataSet(HWND__ *,IDataCollectorSet *,ushort *,ushort *,ushort *,ushort * *,ushort * *,__MIDL___MIDL_itf_pla_0001_0043_0007,int)
0x180026df1  mov     ebx, eax
0x180026df3  test    eax, eax
0x180026df5  jns     short loc_180026E63
0x180026df7  mov     dword ptr [rsp+0B0h+var_90], eax
0x180026dfb  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180026e02  xor     r8d, r8d; int
0x180026e05  lea     rdx, aWdcreportfolde_23; "WdcReportFolder::CommitView"
0x180026e0c  lea     rcx, aBaseDiagnosisP_40; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x180026e13  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180026e18  mov     rcx, [rbp+57h+var_48]; HWND
0x180026e1c  mov     r8d, ebx; int
0x180026e1f  mov     edx, 32Eh; unsigned int
0x180026e24  call    ?WdcShowErrorMessage@@YAJPEAUHWND__@@KJ@Z; WdcShowErrorMessage(HWND__ *,ulong,long)
0x180026e29  jmp     short loc_180026E92
0x180026e2b  mov     ebx, 80004005h
0x180026e30  lea     rdi, aFailure0x08x; "FAILURE: 0x%08x"
0x180026e37  xor     r8d, r8d; int
0x180026e3a  mov     dword ptr [rsp+0B0h+var_90], ebx
0x180026e3e  lea     rdx, aWdcreportfolde_23; "WdcReportFolder::CommitView"
0x180026e45  mov     r9, rdi; unsigned __int16 *
0x180026e48  lea     rcx, aBaseDiagnosisP_40; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x180026e4f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180026e54  mov     rcx, rsi; lpFileName
0x180026e57  call    cs:__imp_DeleteFileW
0x180026e5d  test    ebx, ebx
0x180026e5f  jns     short loc_180026E92
0x180026e61  jmp     short loc_180026E18
0x180026e63  add     rdi, 48h ; 'H'
0x180026e67  mov     r8, [rdi]
0x180026e6a  cmp     rdi, r8
0x180026e6d  jz      short loc_180026E92
0x180026e6f  lea     rcx, [r8]
0x180026e72  mov     r8, [r8]
0x180026e75  cmp     [rcx+1A8h], r14d
0x180026e7c  jnz     short loc_180026E8D
0x180026e7e  mov     rcx, [rcx+420h]; this
0x180026e85  mov     edx, r14d; int
0x180026e88  call    ?SetDirty@WdcBaseNode@@QEAAJH@Z; WdcBaseNode::SetDirty(int)
0x180026e8d  cmp     rdi, r8
0x180026e90  jnz     short loc_180026E6F
0x180026e92  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180026e96  call    cs:__imp_VariantClear
0x180026e9c  test    rsi, rsi
0x180026e9f  jz      short loc_180026EA9
0x180026ea1  mov     rcx, rsi; void *
0x180026ea4  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180026ea9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180026ead  test    rcx, rcx
0x180026eb0  jz      short loc_180026EC0
0x180026eb2  call    cs:__imp_SysFreeString
0x180026eb8  mov     [rbp+57h+bstrString], 0
0x180026ec0  test    r15, r15
0x180026ec3  jz      short loc_180026ECE
0x180026ec5  mov     rcx, r15; bstrString
0x180026ec8  call    cs:__imp_SysFreeString
0x180026ece  mov     rcx, [rbp+57h+var_60]
0x180026ed2  test    rcx, rcx
0x180026ed5  jz      short loc_180026EEB
0x180026ed7  mov     rax, [rcx]
0x180026eda  mov     rax, [rax+10h]
0x180026ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ee3  mov     [rbp+57h+var_60], 0
0x180026eeb  mov     rcx, [rbp+57h+var_58]
0x180026eef  test    rcx, rcx
0x180026ef2  jz      short loc_180026F08
0x180026ef4  mov     rax, [rcx]
0x180026ef7  mov     rax, [rax+10h]
0x180026efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f00  mov     [rbp+57h+var_58], 0
0x180026f08  mov     rcx, [rbp+57h+var_50]
0x180026f0c  test    rcx, rcx
0x180026f0f  jz      short loc_180026F1D
0x180026f11  mov     rax, [rcx]
0x180026f14  mov     rax, [rax+10h]
0x180026f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f1d  lea     r11, [rsp+0B0h+var_20]
0x180026f25  mov     eax, ebx
0x180026f27  mov     rbx, [r11+30h]
0x180026f2b  mov     rsi, [r11+38h]
0x180026f2f  mov     rsp, r11
0x180026f32  pop     r15
0x180026f34  pop     r14
0x180026f36  pop     r12
0x180026f38  pop     rdi
0x180026f39  pop     rbp
0x180026f3a  retn
```
