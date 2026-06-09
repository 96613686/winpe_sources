# WdcSysmonNode::LoadView(WdcConsoleManager *,IDataCollectorSet *)

- ea: `0x180052168`
- end: `0x180052407`
- name: `?LoadView@WdcSysmonNode@@QEAAJPEAVWdcConsoleManager@@PEAUIDataCollectorSet@@@Z`
- size: `671`
- prototype: `__int64 __fastcall(WdcSysmonNode *__hidden this, struct WdcConsoleManager *, struct IDataCollectorSet *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180051f68`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18002a7dc`
- `0x1800373f0`
- `0x18003b0ac`
- `0x180049054`
- `0x180051ecc`
- `0x180052168`
- `0x18006796c`
- `0x180086010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18005237a`
- `KERNEL32!DeleteFileW` at `0x18005237a`
- `OLEAUT32!__imp_SysAllocString` at `0x180052214`
- `OLEAUT32!__imp_SysAllocString` at `0x1800522fd`
- `OLEAUT32!__imp_SysAllocString` at `0x180052214`
- `OLEAUT32!__imp_SysAllocString` at `0x1800522fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800522ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800523c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800523d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800522ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800523c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800523d1`

## pseudocode

```c
__int64 __fastcall WdcSysmonNode::LoadView(
        WdcSysmonNode *this,
        struct WdcConsoleManager *a2,
        struct IDataCollectorSet *a3)
{
  unsigned __int16 *v4; // rdi
  OLECHAR *v7; // r14
  int MainWindow; // eax
  int SystemMonitor; // ebx
  const char *v10; // rdx
  int v11; // r8d
  BSTR v12; // rax
  const char *v13; // rdx
  int v14; // r8d
  unsigned __int16 *v15; // rax
  const char *v16; // rdx
  int v17; // r8d
  int TempFileName; // eax
  OLECHAR *v19; // rax
  __int64 v21; // [rsp+20h] [rbp-30h]
  struct ISystemMonitor2 *v22; // [rsp+30h] [rbp-20h] BYREF
  struct IXMLDOMDocument *v23; // [rsp+38h] [rbp-18h] BYREF
  HWND v24; // [rsp+40h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+48h] BYREF

  v24 = 0;
  v4 = 0;
  bstrString = 0;
  v22 = 0;
  v23 = 0;
  v7 = 0;
  MainWindow = WdcConsoleManager::GetMainWindow(a2, &v24);
  SystemMonitor = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_2;
  SystemMonitor = WdcSysmonNode::GetSystemMonitor(this, a2, &v22);
  if ( SystemMonitor >= 0 )
  {
    MainWindow = ((__int64 (__fastcall *)(struct ISystemMonitor2 *))v22->lpVtbl->Reset)(v22);
    SystemMonitor = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_2;
    v12 = SysAllocString(L"PerformanceMonitorView");
    v7 = v12;
    if ( !v12 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
LABEL_8:
      SystemMonitor = -2147024882;
      LODWORD(v21) = -2147024882;
      goto LABEL_3;
    }
    if ( ((int (__fastcall *)(struct IDataCollectorSet *, BSTR, BSTR *))a3->lpVtbl->GetValue)(a3, v12, &bstrString) < 0 )
    {
      SystemMonitor = 1;
      goto LABEL_23;
    }
    MainWindow = WdcCreateXmlDocumentEx(&v23, 0, bstrString, v24);
    SystemMonitor = MainWindow;
    if ( MainWindow < 0 )
    {
LABEL_2:
      LODWORD(v21) = MainWindow;
LABEL_3:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\sysmonnode.cpp",
        "WdcSysmonNode::LoadView",
        0,
        L"FAILURE: 0x%08x",
        v21);
      goto LABEL_23;
    }
    v15 = (unsigned __int16 *)WdcAlloc(0x800u, v13, v14);
    v4 = v15;
    if ( !v15 )
      goto LABEL_8;
    memset_0(v15, 0, 0x800u);
    TempFileName = WdcGetTempFileName(v4, v16, v17);
    SystemMonitor = TempFileName;
    if ( TempFileName >= 0 )
    {
      TempFileName = WdcSaveXmlDocument(v23, v4);
      SystemMonitor = TempFileName;
      if ( TempFileName >= 0 )
      {
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        v19 = SysAllocString(v4);
        if ( !v19 )
        {
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
            "WdcAssignString",
            0,
            L"FAILURE: 0x%08x",
            -2147024882);
          SystemMonitor = -2147024882;
          LODWORD(v21) = -2147024882;
LABEL_21:
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\sysmonnode.cpp",
            "WdcSysmonNode::LoadView",
            0,
            L"FAILURE: 0x%08x",
            v21);
          goto LABEL_22;
        }
        bstrString = v19;
        TempFileName = ((__int64 (__fastcall *)(struct ISystemMonitor2 *))v22->lpVtbl->LoadSettings)(v22);
        SystemMonitor = TempFileName;
        if ( TempFileName >= 0 )
        {
LABEL_22:
          DeleteFileW(v4);
          goto LABEL_23;
        }
      }
    }
    LODWORD(v21) = TempFileName;
    goto LABEL_21;
  }
LABEL_23:
  if ( v22 )
  {
    ((void (__fastcall *)(struct ISystemMonitor2 *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))v23->lpVtbl->Release)(v23);
    v23 = 0;
  }
  if ( v7 )
    SysFreeString(v7);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v4 )
    WdcFree(v4, v10, v11);
  return (unsigned int)SystemMonitor;
}

```

## disassembly

```asm
0x180052168  mov     [rsp-28h+arg_0], rbx
0x18005216d  mov     [rsp-28h+arg_8], rsi
0x180052172  push    rbp
0x180052173  push    rdi
0x180052174  push    r12
0x180052176  push    r14
0x180052178  push    r15
0x18005217a  mov     rbp, rsp
0x18005217d  sub     rsp, 50h
0x180052181  mov     rsi, rdx
0x180052184  mov     [rbp+var_10], 0
0x18005218c  xor     edi, edi
0x18005218e  lea     rdx, [rbp+var_10]; HWND *
0x180052192  mov     r12, rcx
0x180052195  mov     [rbp+bstrString], rdi
0x180052199  mov     rcx, rsi; this
0x18005219c  mov     [rbp+var_20], rdi
0x1800521a0  mov     r15, r8
0x1800521a3  mov     [rbp+var_18], rdi
0x1800521a7  xor     r14d, r14d
0x1800521aa  call    ?GetMainWindow@WdcConsoleManager@@QEAAJPEAPEAUHWND__@@@Z; WdcConsoleManager::GetMainWindow(HWND__ * *)
0x1800521af  mov     ebx, eax
0x1800521b1  test    eax, eax
0x1800521b3  jns     short loc_1800521DB
0x1800521b5  mov     [rsp+50h+var_30], eax
0x1800521b9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800521c0  xor     r8d, r8d; int
0x1800521c3  lea     rdx, aWdcsysmonnodeL; "WdcSysmonNode::LoadView"
0x1800521ca  lea     rcx, aBaseDiagnosisP_9; "base\\diagnosis\\pdui\\perfmon\\mmc\\sy"...
0x1800521d1  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800521d6  jmp     loc_180052380
0x1800521db  lea     r8, [rbp+var_20]; struct ISystemMonitor2 **
0x1800521df  mov     rdx, rsi; struct WdcConsoleManager *
0x1800521e2  mov     rcx, r12; this
0x1800521e5  call    ?GetSystemMonitor@WdcSysmonNode@@QEAAJPEAVWdcConsoleManager@@PEAPEAUISystemMonitor2@@@Z; WdcSysmonNode::GetSystemMonitor(WdcConsoleManager *,ISystemMonitor2 * *)
0x1800521ea  mov     ebx, eax
0x1800521ec  test    eax, eax
0x1800521ee  js      loc_180052380
0x1800521f4  mov     rcx, [rbp+var_20]
0x1800521f8  mov     rax, [rcx]
0x1800521fb  mov     rax, [rax+1F8h]
0x180052202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052207  mov     ebx, eax
0x180052209  test    eax, eax
0x18005220b  js      short loc_1800521B5
0x18005220d  lea     rcx, aPerformancemon; "PerformanceMonitorView"
0x180052214  call    cs:__imp_SysAllocString
0x18005221a  mov     r14, rax
0x18005221d  test    rax, rax
0x180052220  jnz     short loc_180052253
0x180052222  mov     esi, 8007000Eh
0x180052227  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005222e  xor     r8d, r8d; int
0x180052231  mov     [rsp+50h+var_30], esi
0x180052235  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18005223c  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180052243  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180052248  mov     ebx, esi
0x18005224a  mov     [rsp+50h+var_30], esi
0x18005224e  jmp     loc_1800521B9
0x180052253  mov     rax, [r15]
0x180052256  lea     r8, [rbp+bstrString]
0x18005225a  mov     rdx, r14
0x18005225d  mov     rcx, r15
0x180052260  mov     rax, [rax+210h]
0x180052267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005226c  test    eax, eax
0x18005226e  jns     short loc_18005227A
0x180052270  mov     ebx, 1
0x180052275  jmp     loc_180052380
0x18005227a  mov     r9, [rbp+var_10]; HWND
0x18005227e  lea     rcx, [rbp+var_18]; struct IXMLDOMDocument **
0x180052282  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x180052286  xor     edx, edx; struct tagVARIANT *
0x180052288  call    ?WdcCreateXmlDocumentEx@@YAJPEAPEAUIXMLDOMDocument@@PEAUtagVARIANT@@PEAGPEAUHWND__@@@Z; WdcCreateXmlDocumentEx(IXMLDOMDocument * *,tagVARIANT *,ushort *,HWND__ *)
0x18005228d  mov     ebx, eax
0x18005228f  test    eax, eax
0x180052291  js      loc_1800521B5
0x180052297  mov     ebx, 800h
0x18005229c  mov     ecx, ebx; dwBytes
0x18005229e  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800522a3  mov     rdi, rax
0x1800522a6  test    rax, rax
0x1800522a9  jnz     short loc_1800522B2
0x1800522ab  mov     esi, 8007000Eh
0x1800522b0  jmp     short loc_180052248
0x1800522b2  mov     r8, rbx; Size
0x1800522b5  xor     edx, edx; Val
0x1800522b7  mov     rcx, rdi; void *
0x1800522ba  call    memset_0
0x1800522bf  mov     rcx, rdi; unsigned __int16 *
0x1800522c2  call    ?WdcGetTempFileName@@YAJPEAGK@Z; WdcGetTempFileName(ushort *,ulong)
0x1800522c7  mov     ebx, eax
0x1800522c9  test    eax, eax
0x1800522cb  js      loc_180052356
0x1800522d1  mov     rcx, [rbp+var_18]; struct IXMLDOMDocument *
0x1800522d5  mov     rdx, rdi; unsigned __int16 *
0x1800522d8  call    ?WdcSaveXmlDocument@@YAJPEAUIXMLDOMDocument@@PEBG@Z; WdcSaveXmlDocument(IXMLDOMDocument *,ushort const *)
0x1800522dd  mov     ebx, eax
0x1800522df  test    eax, eax
0x1800522e1  js      short loc_180052356
0x1800522e3  mov     rcx, [rbp+bstrString]; bstrString
0x1800522e7  test    rcx, rcx
0x1800522ea  jz      short loc_1800522FA
0x1800522ec  call    cs:__imp_SysFreeString
0x1800522f2  mov     [rbp+bstrString], 0
0x1800522fa  mov     rcx, rdi; psz
0x1800522fd  call    cs:__imp_SysAllocString
0x180052303  mov     rdx, rax
0x180052306  test    rax, rax
0x180052309  jnz     short loc_180052339
0x18005230b  mov     esi, 8007000Eh
0x180052310  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180052317  xor     r8d, r8d; int
0x18005231a  mov     [rsp+50h+var_30], esi
0x18005231e  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180052325  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18005232c  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180052331  mov     ebx, esi
0x180052333  mov     [rsp+50h+var_30], esi
0x180052337  jmp     short loc_18005235A
0x180052339  mov     [rbp+bstrString], rdx
0x18005233d  mov     rcx, [rbp+var_20]
0x180052341  mov     rax, [rcx]
0x180052344  mov     rax, [rax+310h]
0x18005234b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052350  mov     ebx, eax
0x180052352  test    eax, eax
0x180052354  jns     short loc_180052377
0x180052356  mov     [rsp+50h+var_30], eax
0x18005235a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180052361  xor     r8d, r8d; int
0x180052364  lea     rdx, aWdcsysmonnodeL; "WdcSysmonNode::LoadView"
0x18005236b  lea     rcx, aBaseDiagnosisP_9; "base\\diagnosis\\pdui\\perfmon\\mmc\\sy"...
0x180052372  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180052377  mov     rcx, rdi; lpFileName
0x18005237a  call    cs:__imp_DeleteFileW
0x180052380  mov     rcx, [rbp+var_20]
0x180052384  test    rcx, rcx
0x180052387  jz      short loc_18005239D
0x180052389  mov     rax, [rcx]
0x18005238c  mov     rax, [rax+10h]
0x180052390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052395  mov     [rbp+var_20], 0
0x18005239d  mov     rcx, [rbp+var_18]
0x1800523a1  test    rcx, rcx
0x1800523a4  jz      short loc_1800523BA
0x1800523a6  mov     rax, [rcx]
0x1800523a9  mov     rax, [rax+10h]
0x1800523ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523b2  mov     [rbp+var_18], 0
0x1800523ba  test    r14, r14
0x1800523bd  jz      short loc_1800523C8
0x1800523bf  mov     rcx, r14; bstrString
0x1800523c2  call    cs:__imp_SysFreeString
0x1800523c8  mov     rcx, [rbp+bstrString]; bstrString
0x1800523cc  test    rcx, rcx
0x1800523cf  jz      short loc_1800523DF
0x1800523d1  call    cs:__imp_SysFreeString
0x1800523d7  mov     [rbp+bstrString], 0
0x1800523df  test    rdi, rdi
0x1800523e2  jz      short loc_1800523EC
0x1800523e4  mov     rcx, rdi; void *
0x1800523e7  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x1800523ec  lea     r11, [rsp+50h+var_s0]
0x1800523f1  mov     eax, ebx
0x1800523f3  mov     rbx, [r11+30h]
0x1800523f7  mov     rsi, [r11+38h]
0x1800523fb  mov     rsp, r11
0x1800523fe  pop     r15
0x180052400  pop     r14
0x180052402  pop     r12
0x180052404  pop     rdi
0x180052405  pop     rbp
0x180052406  retn
```
