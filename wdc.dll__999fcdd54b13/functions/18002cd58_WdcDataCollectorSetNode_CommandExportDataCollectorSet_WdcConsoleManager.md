# WdcDataCollectorSetNode::CommandExportDataCollectorSet(WdcConsoleManager *)

- ea: `0x18002cd58`
- end: `0x18002d1e0`
- name: `?CommandExportDataCollectorSet@WdcDataCollectorSetNode@@AEAAJPEAVWdcConsoleManager@@@Z`
- size: `1160`
- prototype: `__int64 __fastcall(WdcDataCollectorSetNode *__hidden this, struct WdcConsoleManager *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057a60`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18002a7dc`
- `0x18002cd58`
- `0x18003b0ac`
- `0x180045170`
- `0x180049054`
- `0x1800571b4`
- `0x180067730`
- `0x18006796c`
- `0x180084e04`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002cfab`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d148`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cfab`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d148`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ceea`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cefd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ceea`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cefd`
- `OLEAUT32!__imp_VariantInit` at `0x18002cdb0`
- `OLEAUT32!__imp_VariantInit` at `0x18002cdb0`
- `OLEAUT32!__imp_VariantClear` at `0x18002cece`
- `OLEAUT32!__imp_VariantClear` at `0x18002cf9e`
- `OLEAUT32!__imp_VariantClear` at `0x18002d137`
- `OLEAUT32!__imp_VariantClear` at `0x18002cece`
- `OLEAUT32!__imp_VariantClear` at `0x18002cf9e`
- `OLEAUT32!__imp_VariantClear` at `0x18002d137`

## string_xrefs

- `0x18002d13d`: `<Templates/>`
- `0x18002ceb7`: `WdcDataCollectorSetNode::CommandExportDataCollectorSet`
- `0x18002d076`: `Templates`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetNode::CommandExportDataCollectorSet(
        WdcDataCollectorSetNode *this,
        struct WdcConsoleManager *a2)
{
  int MainWindow; // eax
  const char *v5; // rdx
  int v6; // r8d
  unsigned int v7; // ebx
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rax
  int v10; // r8d
  const char *v11; // rdx
  int v12; // r8d
  BSTR v14; // rax
  bool v15; // zf
  HRESULT (__stdcall *get_documentElement)(IXMLDOMDocument *, IXMLDOMElement **); // rax
  int v17; // eax
  unsigned __int16 *bstrVal; // rax
  unsigned __int16 *v19; // [rsp+20h] [rbp-39h]
  unsigned __int16 *v20; // [rsp+20h] [rbp-39h]
  unsigned __int64 v21; // [rsp+28h] [rbp-31h]
  __int64 v22; // [rsp+50h] [rbp-9h] BYREF
  __int64 v23; // [rsp+58h] [rbp-1h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+7h] BYREF
  BSTR String1; // [rsp+68h] [rbp+Fh] BYREF
  struct IDataCollectorSet *v26; // [rsp+70h] [rbp+17h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp+1Fh] BYREF
  HWND v28; // [rsp+90h] [rbp+37h] BYREF
  struct IXMLDOMDocument *v29; // [rsp+98h] [rbp+3Fh] BYREF
  __int64 v30; // [rsp+D0h] [rbp+77h] BYREF
  struct IXMLDOMDocument *v31; // [rsp+D8h] [rbp+7Fh] BYREF

  v28 = 0;
  LODWORD(v30) = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  bstrString = 0;
  String1 = 0;
  v22 = 0;
  v23 = 0;
  v29 = 0;
  v31 = 0;
  v26 = 0;
  VariantInit(&pvarg);
  MainWindow = WdcConsoleManager::GetMainWindow(a2, &v28);
  v7 = MainWindow;
  if ( MainWindow < 0 )
  {
    v8 = 0;
LABEL_14:
    LODWORD(v19) = MainWindow;
    goto LABEL_15;
  }
  v9 = (unsigned __int16 *)WdcAlloc(0x800u, v5, v6);
  v8 = v9;
  if ( !v9 )
  {
LABEL_4:
    v7 = -2147024882;
    LODWORD(v19) = -2147024882;
LABEL_15:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
      "WdcDataCollectorSetNode::CommandExportDataCollectorSet",
      0,
      L"FAILURE: 0x%08x",
      v19);
    goto LABEL_16;
  }
  memset_0(v9, 0, 0x800u);
  MainWindow = WdcFileBrowser(
                 v28,
                 0,
                 v10,
                 64,
                 v8,
                 v21,
                 (unsigned __int64 (*)(HWND, unsigned int, unsigned __int64, __int64))WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback,
                 (__int64)&v30,
                 0x800u);
  v7 = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_14;
  if ( MainWindow == 1 )
  {
LABEL_7:
    v7 = 0;
    goto LABEL_16;
  }
  MainWindow = WdcDataCollectorSetNode::GetDataSet(this, 0, &v26);
  v7 = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_14;
  MainWindow = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR *))v26->lpVtbl->get_Xml)(v26, &bstrString);
  v7 = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_14;
  if ( (_DWORD)v30 == 20026 )
  {
    VariantClear(&pvarg);
    pvarg.llVal = 0;
    v14 = SysAllocString(v8);
    if ( !v14 )
    {
LABEL_34:
      LODWORD(v19) = -2147024882;
      WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", v19);
      LODWORD(v20) = -2147024882;
      WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", v20);
      goto LABEL_4;
    }
    pvarg.llVal = (LONGLONG)v14;
    pvarg.vt = 8;
    MainWindow = WdcCreateXmlDocumentEx(&v31, &pvarg, 0, v28);
    v7 = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_14;
    if ( MainWindow == 1 )
      goto LABEL_7;
    MainWindow = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))v31->lpVtbl->get_documentElement)(
                   v31,
                   &v23);
    v7 = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_14;
    MainWindow = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v23 + 56LL))(v23, &String1);
    v7 = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_14;
    v15 = wcscmp_0(String1, L"Templates") == 0;
    get_documentElement = v31->lpVtbl->get_documentElement;
    if ( v15 )
    {
      MainWindow = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))get_documentElement)(v31, &v23);
    }
    else
    {
      MainWindow = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))get_documentElement)(v31, &v22);
      v7 = MainWindow;
      if ( MainWindow < 0 )
        goto LABEL_14;
      VariantClear(&pvarg);
      pvarg.llVal = 0;
      bstrVal = SysAllocString(L"<Templates/>");
      if ( !bstrVal )
        goto LABEL_34;
      pvarg.llVal = (LONGLONG)bstrVal;
      pvarg.vt = 8;
      if ( v31 )
      {
        ((void (__fastcall *)(struct IXMLDOMDocument *))v31->lpVtbl->Release)(v31);
        bstrVal = pvarg.bstrVal;
        v31 = 0;
      }
      MainWindow = WdcCreateXmlDocument(&v31, 0, bstrVal, 0);
      v7 = MainWindow;
      if ( MainWindow < 0 )
        goto LABEL_14;
      v17 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))v31->lpVtbl->get_documentElement)(v31, &v23);
      v7 = v17;
      if ( v17 < 0 )
      {
LABEL_53:
        LODWORD(v19) = v17;
        goto LABEL_15;
      }
      MainWindow = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v23 + 168LL))(v23, v22, 0);
    }
    v7 = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_14;
    MainWindow = WdcCreateXmlDocument(&v29, 0, bstrString, 0);
    v7 = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_14;
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v22 = 0;
    }
    v17 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))v29->lpVtbl->get_documentElement)(v29, &v22);
    v7 = v17;
    if ( v17 >= 0 )
    {
      MainWindow = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v23 + 168LL))(v23, v22, 0);
      goto LABEL_12;
    }
    goto LABEL_53;
  }
  MainWindow = WdcCreateXmlDocument(&v31, 0, bstrString, 0);
LABEL_12:
  v7 = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_14;
  MainWindow = WdcSaveXmlDocument(v31, v8);
  v7 = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_14;
LABEL_16:
  VariantClear(&pvarg);
  if ( v8 )
    WdcFree(v8, v11, v12);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( v26 )
  {
    ((void (__fastcall *)(struct IDataCollectorSet *))v26->lpVtbl->Release)(v26);
    v26 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v31 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))v31->lpVtbl->Release)(v31);
    v31 = 0;
  }
  if ( v29 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v29->lpVtbl->Release)(v29);
  return v7;
}

```

## disassembly

```asm
0x18002cd58  mov     [rsp-8+arg_0], rbx
0x18002cd5d  mov     [rsp-8+arg_8], rsi
0x18002cd62  push    rbp
0x18002cd63  push    rdi
0x18002cd64  push    r14
0x18002cd66  lea     rbp, [rsp-47h]
0x18002cd6b  sub     rsp, 0A0h
0x18002cd72  xor     r14d, r14d
0x18002cd75  mov     rsi, rcx
0x18002cd78  xorps   xmm0, xmm0
0x18002cd7b  mov     [rbp+57h+var_20], r14
0x18002cd7f  xor     eax, eax
0x18002cd81  mov     dword ptr [rbp+57h+arg_10], r14d
0x18002cd85  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002cd89  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002cd8d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002cd91  mov     [rbp+57h+bstrString], r14
0x18002cd95  mov     rbx, rdx
0x18002cd98  mov     [rbp+57h+String1], r14
0x18002cd9c  mov     [rbp+57h+var_60], r14
0x18002cda0  mov     [rbp+57h+var_58], r14
0x18002cda4  mov     [rbp+57h+var_18], r14
0x18002cda8  mov     [rbp+57h+arg_18], r14
0x18002cdac  mov     [rbp+57h+var_40], r14
0x18002cdb0  call    cs:__imp_VariantInit
0x18002cdb6  lea     rdx, [rbp+57h+var_20]; HWND *
0x18002cdba  mov     rcx, rbx; this
0x18002cdbd  call    ?GetMainWindow@WdcConsoleManager@@QEAAJPEAPEAUHWND__@@@Z; WdcConsoleManager::GetMainWindow(HWND__ * *)
0x18002cdc2  mov     ebx, eax
0x18002cdc4  test    eax, eax
0x18002cdc6  jns     short loc_18002CDD0
0x18002cdc8  mov     edi, r14d
0x18002cdcb  jmp     loc_18002CEA9
0x18002cdd0  mov     ebx, 800h
0x18002cdd5  mov     ecx, ebx; dwBytes
0x18002cdd7  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002cddc  mov     rdi, rax
0x18002cddf  test    rax, rax
0x18002cde2  jnz     short loc_18002CDF4
0x18002cde4  mov     esi, 8007000Eh
0x18002cde9  mov     ebx, esi
0x18002cdeb  mov     dword ptr [rsp+0B0h+var_90], esi
0x18002cdef  jmp     loc_18002CEAD
0x18002cdf4  mov     r8, rbx; Size
0x18002cdf7  xor     edx, edx; Val
0x18002cdf9  mov     rcx, rdi; void *
0x18002cdfc  call    memset_0
0x18002ce01  mov     rcx, [rbp+57h+var_20]; HWND
0x18002ce05  lea     rax, [rbp+57h+arg_10]
0x18002ce09  mov     [rsp+0B0h+var_70], ebx; unsigned int
0x18002ce0d  xor     edx, edx; int
0x18002ce0f  mov     [rsp+0B0h+var_78], rax; __int64
0x18002ce14  lea     rax, ?CommandExportDataCollectorSetCallback@WdcDataCollectorSetNode@@CA_KPEAUHWND__@@I_K_J@Z; WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback(HWND__ *,uint,unsigned __int64,__int64)
0x18002ce1b  mov     [rsp+0B0h+var_80], rax; unsigned __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x18002ce20  mov     [rsp+0B0h+var_90], rdi; unsigned __int16 *
0x18002ce25  lea     r9d, [rdx+40h]; int
0x18002ce29  call    ?WdcFileBrowser@@YAJPEAUHWND__@@HHHPEAG_KP6A_K0I2_J@Z3K@Z; WdcFileBrowser(HWND__ *,int,int,int,ushort *,unsigned __int64,unsigned __int64 (*)(HWND__ *,uint,unsigned __int64,__int64),__int64,ulong)
0x18002ce2e  mov     ebx, eax
0x18002ce30  test    eax, eax
0x18002ce32  js      short loc_18002CEA9
0x18002ce34  cmp     eax, 1
0x18002ce37  jnz     short loc_18002CE41
0x18002ce39  mov     ebx, r14d
0x18002ce3c  jmp     loc_18002CECA
0x18002ce41  lea     r8, [rbp+57h+var_40]; struct IDataCollectorSet **
0x18002ce45  xor     edx, edx; int
0x18002ce47  mov     rcx, rsi; this
0x18002ce4a  call    ?GetDataSet@WdcDataCollectorSetNode@@IEAAJHPEAPEAUIDataCollectorSet@@@Z; WdcDataCollectorSetNode::GetDataSet(int,IDataCollectorSet * *)
0x18002ce4f  mov     ebx, eax
0x18002ce51  test    eax, eax
0x18002ce53  js      short loc_18002CEA9
0x18002ce55  mov     rcx, [rbp+57h+var_40]
0x18002ce59  lea     rdx, [rbp+57h+bstrString]
0x18002ce5d  mov     rax, [rcx]
0x18002ce60  mov     rax, [rax+1A0h]
0x18002ce67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce6c  mov     ebx, eax
0x18002ce6e  test    eax, eax
0x18002ce70  js      short loc_18002CEA9
0x18002ce72  cmp     dword ptr [rbp+57h+arg_10], 4E3Ah
0x18002ce79  jz      loc_18002CF9A
0x18002ce7f  mov     r8, [rbp+57h+bstrString]; unsigned __int16 *
0x18002ce83  lea     rcx, [rbp+57h+arg_18]; struct IXMLDOMDocument **
0x18002ce87  xor     r9d, r9d; struct IXMLDOMParseError **
0x18002ce8a  xor     edx, edx; struct tagVARIANT *
0x18002ce8c  call    ?WdcCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@PEAUtagVARIANT@@PEAGPEAPEAUIXMLDOMParseError@@@Z; WdcCreateXmlDocument(IXMLDOMDocument * *,tagVARIANT *,ushort *,IXMLDOMParseError * *)
0x18002ce91  mov     ebx, eax
0x18002ce93  test    eax, eax
0x18002ce95  js      short loc_18002CEA9
0x18002ce97  mov     rcx, [rbp+57h+arg_18]; struct IXMLDOMDocument *
0x18002ce9b  mov     rdx, rdi; unsigned __int16 *
0x18002ce9e  call    ?WdcSaveXmlDocument@@YAJPEAUIXMLDOMDocument@@PEBG@Z; WdcSaveXmlDocument(IXMLDOMDocument *,ushort const *)
0x18002cea3  mov     ebx, eax
0x18002cea5  test    eax, eax
0x18002cea7  jns     short loc_18002CECA
0x18002cea9  mov     dword ptr [rsp+0B0h+var_90], eax
0x18002cead  xor     r8d, r8d; int
0x18002ceb0  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002ceb7  lea     rdx, aWdcdatacollect_129; "WdcDataCollectorSetNode::CommandExportD"...
0x18002cebe  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18002cec5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002ceca  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002cece  call    cs:__imp_VariantClear
0x18002ced4  test    rdi, rdi
0x18002ced7  jz      short loc_18002CEE1
0x18002ced9  mov     rcx, rdi; void *
0x18002cedc  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002cee1  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002cee5  test    rcx, rcx
0x18002cee8  jz      short loc_18002CEF4
0x18002ceea  call    cs:__imp_SysFreeString
0x18002cef0  mov     [rbp+57h+bstrString], r14
0x18002cef4  mov     rcx, [rbp+57h+String1]; bstrString
0x18002cef8  test    rcx, rcx
0x18002cefb  jz      short loc_18002CF07
0x18002cefd  call    cs:__imp_SysFreeString
0x18002cf03  mov     [rbp+57h+String1], r14
0x18002cf07  mov     rcx, [rbp+57h+var_40]
0x18002cf0b  test    rcx, rcx
0x18002cf0e  jz      short loc_18002CF20
0x18002cf10  mov     rax, [rcx]
0x18002cf13  mov     rax, [rax+10h]
0x18002cf17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf1c  mov     [rbp+57h+var_40], r14
0x18002cf20  mov     rcx, [rbp+57h+var_60]
0x18002cf24  test    rcx, rcx
0x18002cf27  jz      short loc_18002CF39
0x18002cf29  mov     rax, [rcx]
0x18002cf2c  mov     rax, [rax+10h]
0x18002cf30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf35  mov     [rbp+57h+var_60], r14
0x18002cf39  mov     rcx, [rbp+57h+var_58]
0x18002cf3d  test    rcx, rcx
0x18002cf40  jz      short loc_18002CF52
0x18002cf42  mov     rax, [rcx]
0x18002cf45  mov     rax, [rax+10h]
0x18002cf49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf4e  mov     [rbp+57h+var_58], r14
0x18002cf52  mov     rcx, [rbp+57h+arg_18]
0x18002cf56  test    rcx, rcx
0x18002cf59  jz      short loc_18002CF6B
0x18002cf5b  mov     rax, [rcx]
0x18002cf5e  mov     rax, [rax+10h]
0x18002cf62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf67  mov     [rbp+57h+arg_18], r14
0x18002cf6b  mov     rcx, [rbp+57h+var_18]
0x18002cf6f  test    rcx, rcx
0x18002cf72  jz      short loc_18002CF80
0x18002cf74  mov     rax, [rcx]
0x18002cf77  mov     rax, [rax+10h]
0x18002cf7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf80  lea     r11, [rsp+0B0h+var_10]
0x18002cf88  mov     eax, ebx
0x18002cf8a  mov     rbx, [r11+20h]
0x18002cf8e  mov     rsi, [r11+28h]
0x18002cf92  mov     rsp, r11
0x18002cf95  pop     r14
0x18002cf97  pop     rdi
0x18002cf98  pop     rbp
0x18002cf99  retn
0x18002cf9a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002cf9e  call    cs:__imp_VariantClear
0x18002cfa4  mov     rcx, rdi; psz
0x18002cfa7  mov     qword ptr [rbp+57h+pvarg+8], r14
0x18002cfab  call    cs:__imp_SysAllocString
0x18002cfb1  xor     r8d, r8d; unsigned __int16 *
0x18002cfb4  test    rax, rax
0x18002cfb7  jnz     short loc_18002D002
0x18002cfb9  mov     esi, 8007000Eh
0x18002cfbe  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002cfc5  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18002cfcc  mov     dword ptr [rsp+0B0h+var_90], esi
0x18002cfd0  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18002cfd7  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002cfdc  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002cfe3  mov     dword ptr [rsp+0B0h+var_90], esi
0x18002cfe7  xor     r8d, r8d; int
0x18002cfea  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18002cff1  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18002cff8  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002cffd  jmp     loc_18002CDE9
0x18002d002  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18002d006  mov     esi, 8
0x18002d00b  mov     word ptr [rbp+57h+pvarg], si
0x18002d00f  mov     r9, [rbp+57h+var_20]; HWND
0x18002d013  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18002d017  lea     rcx, [rbp+57h+arg_18]; struct IXMLDOMDocument **
0x18002d01b  call    ?WdcCreateXmlDocumentEx@@YAJPEAPEAUIXMLDOMDocument@@PEAUtagVARIANT@@PEAGPEAUHWND__@@@Z; WdcCreateXmlDocumentEx(IXMLDOMDocument * *,tagVARIANT *,ushort *,HWND__ *)
0x18002d020  mov     ebx, eax
0x18002d022  test    eax, eax
0x18002d024  js      loc_18002CEA9
0x18002d02a  cmp     eax, 1
0x18002d02d  jz      loc_18002CE39
0x18002d033  mov     rcx, [rbp+57h+arg_18]
0x18002d037  lea     rdx, [rbp+57h+var_58]
0x18002d03b  mov     rax, [rcx]
0x18002d03e  mov     rax, [rax+168h]
0x18002d045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d04a  mov     ebx, eax
0x18002d04c  test    eax, eax
0x18002d04e  js      loc_18002CEA9
0x18002d054  mov     rcx, [rbp+57h+var_58]
0x18002d058  lea     rdx, [rbp+57h+String1]
0x18002d05c  mov     rax, [rcx]
0x18002d05f  mov     rax, [rax+38h]
0x18002d063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d068  mov     ebx, eax
0x18002d06a  test    eax, eax
0x18002d06c  js      loc_18002CEA9
0x18002d072  mov     rcx, [rbp+57h+String1]; String1
0x18002d076  lea     rdx, aTemplates; "Templates"
0x18002d07d  call    wcscmp_0
0x18002d082  mov     rcx, [rbp+57h+arg_18]
0x18002d086  test    eax, eax
0x18002d088  mov     rax, [rcx]
0x18002d08b  mov     rax, [rax+168h]
0x18002d092  jnz     loc_18002D120
0x18002d098  lea     rdx, [rbp+57h+var_58]
0x18002d09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0a1  mov     ebx, eax
0x18002d0a3  test    eax, eax
0x18002d0a5  js      loc_18002CEA9
0x18002d0ab  mov     r8, [rbp+57h+bstrString]; unsigned __int16 *
0x18002d0af  lea     rcx, [rbp+57h+var_18]; struct IXMLDOMDocument **
0x18002d0b3  xor     r9d, r9d; struct IXMLDOMParseError **
0x18002d0b6  xor     edx, edx; struct tagVARIANT *
0x18002d0b8  call    ?WdcCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@PEAUtagVARIANT@@PEAGPEAPEAUIXMLDOMParseError@@@Z; WdcCreateXmlDocument(IXMLDOMDocument * *,tagVARIANT *,ushort *,IXMLDOMParseError * *)
0x18002d0bd  mov     ebx, eax
0x18002d0bf  test    eax, eax
0x18002d0c1  js      loc_18002CEA9
0x18002d0c7  mov     rcx, [rbp+57h+var_60]
0x18002d0cb  test    rcx, rcx
0x18002d0ce  jz      short loc_18002D0E0
0x18002d0d0  mov     rax, [rcx]
0x18002d0d3  mov     rax, [rax+10h]
0x18002d0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0dc  mov     [rbp+57h+var_60], r14
0x18002d0e0  mov     rcx, [rbp+57h+var_18]
0x18002d0e4  lea     rdx, [rbp+57h+var_60]
0x18002d0e8  mov     rax, [rcx]
0x18002d0eb  mov     rax, [rax+168h]
0x18002d0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0f7  xor     r8d, r8d
0x18002d0fa  mov     ebx, eax
0x18002d0fc  test    eax, eax
0x18002d0fe  js      loc_18002D1BB
0x18002d104  mov     rcx, [rbp+57h+var_58]
0x18002d108  mov     rdx, [rbp+57h+var_60]
0x18002d10c  mov     rax, [rcx]
0x18002d10f  mov     rax, [rax+0A8h]
0x18002d116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d11b  jmp     loc_18002CE91
0x18002d120  lea     rdx, [rbp+57h+var_60]
0x18002d124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d129  mov     ebx, eax
0x18002d12b  test    eax, eax
0x18002d12d  js      loc_18002CEA9
0x18002d133  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002d137  call    cs:__imp_VariantClear
0x18002d13d  lea     rcx, aTemplates_0; "<Templates/>"
0x18002d144  mov     qword ptr [rbp+57h+pvarg+8], r14
0x18002d148  call    cs:__imp_SysAllocString
0x18002d14e  test    rax, rax
0x18002d151  jnz     short loc_18002D15B
0x18002d153  xor     r8d, r8d
0x18002d156  jmp     loc_18002CFB9
0x18002d15b  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18002d15f  mov     word ptr [rbp+57h+pvarg], si
0x18002d163  mov     rcx, [rbp+57h+arg_18]
0x18002d167  test    rcx, rcx
0x18002d16a  jz      short loc_18002D180
0x18002d16c  mov     rax, [rcx]
0x18002d16f  mov     rax, [rax+10h]
0x18002d173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d178  mov     rax, qword ptr [rbp+57h+pvarg+8]
0x18002d17c  mov     [rbp+57h+arg_18], r14
0x18002d180  xor     r9d, r9d; struct IXMLDOMParseError **
0x18002d183  lea     rcx, [rbp+57h+arg_18]; struct IXMLDOMDocument **
0x18002d187  mov     r8, rax; unsigned __int16 *
0x18002d18a  xor     edx, edx; struct tagVARIANT *
0x18002d18c  call    ?WdcCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@PEAUtagVARIANT@@PEAGPEAPEAUIXMLDOMParseError@@@Z; WdcCreateXmlDocument(IXMLDOMDocument * *,tagVARIANT *,ushort *,IXMLDOMParseError * *)
0x18002d191  mov     ebx, eax
0x18002d193  test    eax, eax
0x18002d195  js      loc_18002CEA9
0x18002d19b  mov     rcx, [rbp+57h+arg_18]
0x18002d19f  lea     rdx, [rbp+57h+var_58]
0x18002d1a3  mov     rax, [rcx]
0x18002d1a6  mov     rax, [rax+168h]
0x18002d1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1b2  xor     r8d, r8d
0x18002d1b5  mov     ebx, eax
0x18002d1b7  test    eax, eax
0x18002d1b9  jns     short loc_18002D1C4
0x18002d1bb  mov     dword ptr [rsp+0B0h+var_90], eax
0x18002d1bf  jmp     loc_18002CEB0
0x18002d1c4  mov     rcx, [rbp+57h+var_58]
0x18002d1c8  mov     rdx, [rbp+57h+var_60]
0x18002d1cc  mov     rax, [rcx]
0x18002d1cf  mov     rax, [rax+0A8h]
0x18002d1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
