# WdcDataCollectorSetFolder::CommandDataCollectorSetWizard(WdcConsoleManager *,IXMLDOMDocument *,WDC_WIZARD_MODE)

- ea: `0x180053124`
- end: `0x180053570`
- name: `?CommandDataCollectorSetWizard@WdcDataCollectorSetFolder@@QEAAJPEAVWdcConsoleManager@@PEAUIXMLDOMDocument@@W4WDC_WIZARD_MODE@@@Z`
- size: `1100`
- prototype: `__int64 __fastcall(__int64, WdcConsoleManager *, struct IDataCollectorSet *, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053960`

## callees

- `0x18000b854`
- `0x1800329f8`
- `0x18003a7cc`
- `0x180049054`
- `0x1800497f0`
- `0x180049cec`
- `0x18004bcc0`
- `0x18004befc`
- `0x18004e348`
- `0x180053124`
- `0x180054230`
- `0x1800571b4`
- `0x1800596bc`
- `0x18005a714`
- `0x180068f70`
- `0x18006af2c`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005316c`
- `OLEAUT32!__imp_SysFreeString` at `0x180053511`
- `OLEAUT32!__imp_SysFreeString` at `0x18005316c`
- `OLEAUT32!__imp_SysFreeString` at `0x180053511`

## string_xrefs

- `0x18005320f`: `WdcDataCollectorSetFolder::CommandDataCollectorSetWizard`
- `0x1800534f5`: `WdcDataCollectorSetFolder::CommandDataCollectorSetWizard`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetFolder::CommandDataCollectorSetWizard(
        __int64 a1,
        WdcConsoleManager *a2,
        struct IDataCollectorSet *a3,
        unsigned int a4)
{
  OLECHAR *v5; // rcx
  WdcWizard *v8; // rsi
  int MainWindow; // eax
  unsigned int Child; // ebx
  _QWORD *v11; // r14
  WdcDataCollectorSetNode *v12; // rbx
  int DataSet; // eax
  void *v14; // rax
  __int64 v15; // rcx
  WdcDataCollectorSetNode *v16; // rax
  WdcDataCollectorSetNode *v17; // rax
  WdcDataCollectorSetNode *v18; // r14
  _QWORD *v19; // rdx
  _QWORD *v20; // rax
  _WORD *v21; // rcx
  struct IDataCollectorSet *v23; // [rsp+20h] [rbp-40h]
  BSTR bstrString; // [rsp+40h] [rbp-20h] BYREF
  struct IConsoleNameSpace2 *v25; // [rsp+48h] [rbp-18h] BYREF
  struct WdcDataCollectorSetNode *v26; // [rsp+50h] [rbp-10h] BYREF
  HWND v27; // [rsp+A0h] [rbp+40h] BYREF
  struct IDataCollectorSet *v28; // [rsp+B0h] [rbp+50h] BYREF

  v28 = a3;
  v5 = *(OLECHAR **)(a1 + 56);
  v27 = 0;
  bstrString = 0;
  v8 = 0;
  v26 = 0;
  v28 = 0;
  v25 = 0;
  if ( v5 )
  {
    SysFreeString(v5);
    *(_QWORD *)(a1 + 56) = 0;
  }
  MainWindow = WdcConsoleManager::Select(a2, (struct WdcBaseNode *)a1);
  Child = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_49;
  if ( !a4 )
  {
    v11 = *(_QWORD **)(a1 + 72);
    while ( (_QWORD *)(a1 + 72) != v11 )
    {
      v12 = (WdcDataCollectorSetNode *)(v11 - 1);
      v11 = (_QWORD *)*v11;
      if ( (*((_BYTE *)v12 + 108) & 1) != 0 )
      {
        if ( v28 )
        {
          ((void (__fastcall *)(struct IDataCollectorSet *))v28->lpVtbl->Release)(v28);
          v28 = 0;
        }
        DataSet = WdcDataCollectorSetNode::GetDataSet(v12, 0, &v28);
        Child = DataSet;
        if ( DataSet < 0
          || (DataSet = (*(__int64 (__fastcall **)(_QWORD, struct IDataCollectorSet *))(**(_QWORD **)(a1 + 472) + 80LL))(
                          *(_QWORD *)(a1 + 472),
                          v28),
              Child = DataSet,
              DataSet < 0) )
        {
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetfolder.cpp",
            "WdcDataCollectorSetFolder::CommandDataCollectorSetWizard",
            0,
            L"FAILURE: 0x%08x",
            DataSet);
          goto LABEL_51;
        }
      }
    }
  }
  v14 = operator new(0x240u);
  v8 = (WdcWizard *)WdcDataCollectorSetWizard::WdcDataCollectorSetWizard(
                      (__int64)v14,
                      *(const unsigned __int16 **)(a1 + 48),
                      *(const OLECHAR **)(a1 + 448),
                      0,
                      a4,
                      *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 472));
  if ( !v8 )
    goto LABEL_14;
  MainWindow = WdcConsoleManager::GetMainWindow(a2, &v27);
  Child = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_49;
  MainWindow = WdcWizard::ShowWizard(v8, v27);
  Child = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_49;
  if ( MainWindow == 1 )
  {
    Child = 0;
    goto LABEL_51;
  }
  if ( !a4 )
  {
    if ( v28 )
    {
      ((void (__fastcall *)(struct IDataCollectorSet *))v28->lpVtbl->Release)(v28);
      v28 = 0;
    }
    MainWindow = WdcDataCollectorSetWizard::GetDataSet(v8, &v28);
    Child = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_49;
    MainWindow = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR *))v28->lpVtbl->get_Name)(v28, &bstrString);
    Child = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_49;
    Child = WdcDataCollectorSetFolder::FindChild((WdcDataCollectorSetFolder *)a1, bstrString, &v26);
    if ( !Child )
    {
      WdcShowErrorMessage(v27, 0x327u, -2144337737);
      goto LABEL_51;
    }
  }
  MainWindow = (*(__int64 (__fastcall **)(WdcWizard *, __int64))(*(_QWORD *)v8 + 8LL))(v8, a1 + 56);
  Child = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_49;
  if ( *(_DWORD *)(a1 + 480) )
  {
    MainWindow = WdcBaseNode::SetDirty((WdcBaseNode *)a1, 1);
  }
  else
  {
    MainWindow = WdcConsoleManager::QueryNameSpace(a2, &v25);
    Child = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_49;
    MainWindow = WdcBaseNode::SetDirty((WdcBaseNode *)a1, 1);
    Child = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_49;
    MainWindow = MainWindow == 1
               ? ((__int64 (__fastcall *)(struct IConsoleNameSpace2 *, _QWORD))v25->lpVtbl->Expand)(
                   v25,
                   *(_QWORD *)(a1 + 112))
               : (*(unsigned __int64 (__fastcall **)(__int64, struct IConsoleNameSpace2 *, WdcConsoleManager *, _QWORD))(*(_QWORD *)a1 + 168LL))(
                   v15,
                   v25,
                   a2,
                   *(_QWORD *)(a1 + 112));
    Child = MainWindow;
    if ( MainWindow < 0 )
      goto LABEL_49;
    MainWindow = WdcDataCollectorSetFolder::SyncReports((WdcDataCollectorSetFolder *)a1, a2);
  }
  Child = MainWindow;
  if ( MainWindow < 0 )
    goto LABEL_49;
  if ( a4 )
    goto LABEL_48;
  if ( v28 )
  {
    ((void (__fastcall *)(struct IDataCollectorSet *))v28->lpVtbl->Release)(v28);
    v28 = 0;
  }
  MainWindow = WdcDataCollectorSetWizard::GetDataSet(v8, &v28);
  Child = MainWindow;
  if ( MainWindow < 0 )
  {
LABEL_49:
    LODWORD(v23) = MainWindow;
    goto LABEL_50;
  }
  v16 = (WdcDataCollectorSetNode *)operator new(0x228u);
  v17 = WdcDataCollectorSetNode::WdcDataCollectorSetNode(
          v16,
          *(const unsigned __int16 **)(a1 + 48),
          *(const unsigned __int16 **)(a1 + 448),
          (struct WdcDataCollectorSetFolder *)a1,
          v28,
          *(_DWORD *)(a1 + 480),
          1);
  v18 = v17;
  if ( v17 )
  {
    *((_DWORD *)v17 + 6) = 11;
    v19 = *(_QWORD **)(a1 + 80);
    if ( *v19 != a1 + 72 )
      __fastfail(3u);
    v20 = (_QWORD *)((char *)v17 + 8);
    v20[1] = v19;
    *v20 = a1 + 72;
    *v19 = v20;
    *(_QWORD *)(a1 + 80) = v20;
    MainWindow = (*(__int64 (__fastcall **)(WdcDataCollectorSetNode *, WdcConsoleManager *))(*(_QWORD *)v18 + 208LL))(
                   v18,
                   a2);
    Child = MainWindow;
    if ( MainWindow >= 0 )
    {
      v21 = *(_WORD **)(a1 + 56);
      if ( v21 && *v21 )
        *(_QWORD *)(a1 + 64) = v18;
LABEL_48:
      MainWindow = (*(__int64 (__fastcall **)(WdcWizard *, HWND))(*(_QWORD *)v8 + 16LL))(v8, v27);
      Child = MainWindow;
      if ( MainWindow >= 0 )
        goto LABEL_51;
      goto LABEL_49;
    }
    goto LABEL_49;
  }
LABEL_14:
  Child = -2147024882;
  LODWORD(v23) = -2147024882;
LABEL_50:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetfolder.cpp",
    "WdcDataCollectorSetFolder::CommandDataCollectorSetWizard",
    0,
    L"FAILURE: 0x%08x",
    v23);
LABEL_51:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v28 )
  {
    ((void (__fastcall *)(struct IDataCollectorSet *))v28->lpVtbl->Release)(v28);
    v28 = 0;
  }
  if ( v8 )
    WdcDataPortal::Release(v8);
  if ( v25 )
    ((void (__fastcall *)(struct IConsoleNameSpace2 *))v25->lpVtbl->Release)(v25);
  return Child;
}

```

## disassembly

```asm
0x180053124  mov     [rsp-38h+arg_8], rbx
0x180053129  mov     [rsp-38h+arg_10], r8
0x18005312e  push    rbp
0x18005312f  push    rsi
0x180053130  push    rdi
0x180053131  push    r12
0x180053133  push    r13
0x180053135  push    r14
0x180053137  push    r15
0x180053139  mov     rbp, rsp
0x18005313c  sub     rsp, 60h
0x180053140  xor     r15d, r15d
0x180053143  mov     rdi, rcx
0x180053146  mov     rcx, [rcx+38h]; bstrString
0x18005314a  mov     r12d, r9d
0x18005314d  mov     [rbp+arg_0], r15
0x180053151  mov     r13, rdx
0x180053154  mov     [rbp+bstrString], r15
0x180053158  mov     esi, r15d
0x18005315b  mov     [rbp+var_10], r15
0x18005315f  mov     [rbp+arg_10], r15
0x180053163  mov     [rbp+var_18], r15
0x180053167  test    rcx, rcx
0x18005316a  jz      short loc_180053176
0x18005316c  call    cs:__imp_SysFreeString
0x180053172  mov     [rdi+38h], r15
0x180053176  mov     rdx, rdi; struct WdcBaseNode *
0x180053179  mov     rcx, r13; this
0x18005317c  call    ?Select@WdcConsoleManager@@QEAAJPEAVWdcBaseNode@@@Z; WdcConsoleManager::Select(WdcBaseNode *)
0x180053181  mov     ebx, eax
0x180053183  test    eax, eax
0x180053185  js      loc_1800534E7
0x18005318b  mov     r14d, 1
0x180053191  test    r12d, r12d
0x180053194  jnz     loc_180053231
0x18005319a  lea     r15, [rdi+48h]
0x18005319e  mov     r14, [r15]
0x1800531a1  cmp     r15, r14
0x1800531a4  jz      loc_18005322A
0x1800531aa  lea     rbx, [r14-8]
0x1800531ae  mov     r14, [r14]
0x1800531b1  test    byte ptr [rbx+6Ch], 1
0x1800531b5  jz      short loc_1800531A1
0x1800531b7  mov     rcx, [rbp+arg_10]
0x1800531bb  test    rcx, rcx
0x1800531be  jz      short loc_1800531D0
0x1800531c0  mov     rax, [rcx]
0x1800531c3  mov     rax, [rax+10h]
0x1800531c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531cc  mov     [rbp+arg_10], rsi
0x1800531d0  lea     r8, [rbp+arg_10]; struct IDataCollectorSet **
0x1800531d4  xor     edx, edx; int
0x1800531d6  mov     rcx, rbx; this
0x1800531d9  call    ?GetDataSet@WdcDataCollectorSetNode@@IEAAJHPEAPEAUIDataCollectorSet@@@Z; WdcDataCollectorSetNode::GetDataSet(int,IDataCollectorSet * *)
0x1800531de  mov     ebx, eax
0x1800531e0  test    eax, eax
0x1800531e2  js      short loc_180053201
0x1800531e4  mov     rcx, [rdi+1D8h]
0x1800531eb  mov     rdx, [rbp+arg_10]
0x1800531ef  mov     rax, [rcx]
0x1800531f2  mov     rax, [rax+50h]
0x1800531f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531fb  mov     ebx, eax
0x1800531fd  test    eax, eax
0x1800531ff  jns     short loc_1800531A1
0x180053201  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180053208  mov     dword ptr [rsp+60h+var_40], eax
0x18005320c  xor     r8d, r8d; int
0x18005320f  lea     rdx, aWdcdatacollect_81; "WdcDataCollectorSetFolder::CommandDataC"...
0x180053216  lea     rcx, aBaseDiagnosisP_1; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18005321d  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180053222  xor     r15d, r15d
0x180053225  jmp     loc_180053508
0x18005322a  xor     r15d, r15d
0x18005322d  lea     r14d, [r15+1]
0x180053231  mov     ecx, 240h; Size
0x180053236  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005323b  mov     r8, [rdi+1C0h]
0x180053242  mov     rcx, rax
0x180053245  mov     rax, [rdi+1D8h]
0x18005324c  xor     r9d, r9d
0x18005324f  mov     rdx, [rdi+30h]
0x180053253  mov     qword ptr [rsp+60h+var_38], rax
0x180053258  mov     dword ptr [rsp+60h+var_40], r12d
0x18005325d  call    ??0WdcDataCollectorSetWizard@@QEAA@PEBG0PEAUIXMLDOMDocument@@W4WDC_WIZARD_MODE@@PEAUIDataCollectorSetCollection@@@Z; WdcDataCollectorSetWizard::WdcDataCollectorSetWizard(ushort const *,ushort const *,IXMLDOMDocument *,WDC_WIZARD_MODE,IDataCollectorSetCollection *)
0x180053262  mov     rsi, rax
0x180053265  test    rax, rax
0x180053268  jnz     short loc_18005327A
0x18005326a  mov     ecx, 8007000Eh
0x18005326f  mov     ebx, ecx
0x180053271  mov     dword ptr [rsp+60h+var_40], ecx
0x180053275  jmp     loc_1800534EB
0x18005327a  lea     rdx, [rbp+arg_0]; HWND *
0x18005327e  mov     rcx, r13; this
0x180053281  call    ?GetMainWindow@WdcConsoleManager@@QEAAJPEAPEAUHWND__@@@Z; WdcConsoleManager::GetMainWindow(HWND__ * *)
0x180053286  mov     ebx, eax
0x180053288  test    eax, eax
0x18005328a  js      loc_1800534E7
0x180053290  mov     rdx, [rbp+arg_0]; HWND
0x180053294  mov     rcx, rsi; this
0x180053297  call    ?ShowWizard@WdcWizard@@QEAAJPEAUHWND__@@@Z; WdcWizard::ShowWizard(HWND__ *)
0x18005329c  mov     ebx, eax
0x18005329e  test    eax, eax
0x1800532a0  js      loc_1800534E7
0x1800532a6  cmp     eax, r14d
0x1800532a9  jnz     short loc_1800532B3
0x1800532ab  mov     ebx, r15d
0x1800532ae  jmp     loc_180053508
0x1800532b3  test    r12d, r12d
0x1800532b6  jnz     short loc_180053337
0x1800532b8  mov     rcx, [rbp+arg_10]
0x1800532bc  test    rcx, rcx
0x1800532bf  jz      short loc_1800532D1
0x1800532c1  mov     rax, [rcx]
0x1800532c4  mov     rax, [rax+10h]
0x1800532c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532cd  mov     [rbp+arg_10], r15
0x1800532d1  lea     rdx, [rbp+arg_10]; struct IDataCollectorSet **
0x1800532d5  mov     rcx, rsi; this
0x1800532d8  call    ?GetDataSet@WdcDataCollectorSetWizard@@QEAAJPEAPEAUIDataCollectorSet@@@Z; WdcDataCollectorSetWizard::GetDataSet(IDataCollectorSet * *)
0x1800532dd  mov     ebx, eax
0x1800532df  test    eax, eax
0x1800532e1  js      loc_1800534E7
0x1800532e7  mov     rcx, [rbp+arg_10]
0x1800532eb  lea     rdx, [rbp+bstrString]
0x1800532ef  mov     rax, [rcx]
0x1800532f2  mov     rax, [rax+0A0h]
0x1800532f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532fe  mov     ebx, eax
0x180053300  test    eax, eax
0x180053302  js      loc_1800534E7
0x180053308  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18005330c  lea     r8, [rbp+var_10]; struct WdcDataCollectorSetNode **
0x180053310  mov     rcx, rdi; this
0x180053313  call    ?FindChild@WdcDataCollectorSetFolder@@QEAAJPEBGPEAPEAVWdcDataCollectorSetNode@@@Z; WdcDataCollectorSetFolder::FindChild(ushort const *,WdcDataCollectorSetNode * *)
0x180053318  mov     ebx, eax
0x18005331a  test    eax, eax
0x18005331c  jnz     short loc_180053337
0x18005331e  mov     rcx, [rbp+arg_0]; HWND
0x180053322  mov     edx, 327h; unsigned int
0x180053327  mov     r8d, 803000B7h; int
0x18005332d  call    ?WdcShowErrorMessage@@YAJPEAUHWND__@@KJ@Z; WdcShowErrorMessage(HWND__ *,ulong,long)
0x180053332  jmp     loc_180053508
0x180053337  mov     rax, [rsi]
0x18005333a  lea     rdx, [rdi+38h]
0x18005333e  mov     rcx, rsi
0x180053341  mov     rax, [rax+8]
0x180053345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005334a  mov     ebx, eax
0x18005334c  test    eax, eax
0x18005334e  js      loc_1800534E7
0x180053354  cmp     [rdi+1E0h], r15d
0x18005335b  jnz     loc_18005347E
0x180053361  lea     rdx, [rbp+var_18]; struct IConsoleNameSpace2 **
0x180053365  mov     rcx, r13; this
0x180053368  call    ?QueryNameSpace@WdcConsoleManager@@QEAAJPEAPEAUIConsoleNameSpace2@@@Z; WdcConsoleManager::QueryNameSpace(IConsoleNameSpace2 * *)
0x18005336d  mov     ebx, eax
0x18005336f  test    eax, eax
0x180053371  js      loc_1800534E7
0x180053377  mov     edx, r14d; int
0x18005337a  mov     rcx, rdi; this
0x18005337d  call    ?SetDirty@WdcBaseNode@@QEAAJH@Z; WdcBaseNode::SetDirty(int)
0x180053382  mov     ebx, eax
0x180053384  test    eax, eax
0x180053386  js      loc_1800534E7
0x18005338c  cmp     eax, r14d
0x18005338f  jz      loc_180053465
0x180053395  mov     rax, [rdi]
0x180053398  mov     r8, r13
0x18005339b  mov     r9, [rdi+70h]
0x18005339f  mov     rdx, [rbp+var_18]
0x1800533a3  mov     rax, [rax+0A8h]
0x1800533aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533af  mov     ebx, eax
0x1800533b1  test    eax, eax
0x1800533b3  js      loc_1800534E7
0x1800533b9  mov     rdx, r13; struct WdcConsoleManager *
0x1800533bc  mov     rcx, rdi; this
0x1800533bf  call    ?SyncReports@WdcDataCollectorSetFolder@@QEAAJPEAVWdcConsoleManager@@@Z; WdcDataCollectorSetFolder::SyncReports(WdcConsoleManager *)
0x1800533c4  mov     ebx, eax
0x1800533c6  test    eax, eax
0x1800533c8  js      loc_1800534E7
0x1800533ce  test    r12d, r12d
0x1800533d1  jnz     loc_1800534CE
0x1800533d7  mov     rcx, [rbp+arg_10]
0x1800533db  test    rcx, rcx
0x1800533de  jz      short loc_1800533F0
0x1800533e0  mov     rax, [rcx]
0x1800533e3  mov     rax, [rax+10h]
0x1800533e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533ec  mov     [rbp+arg_10], r15
0x1800533f0  lea     rdx, [rbp+arg_10]; struct IDataCollectorSet **
0x1800533f4  mov     rcx, rsi; this
0x1800533f7  call    ?GetDataSet@WdcDataCollectorSetWizard@@QEAAJPEAPEAUIDataCollectorSet@@@Z; WdcDataCollectorSetWizard::GetDataSet(IDataCollectorSet * *)
0x1800533fc  mov     ebx, eax
0x1800533fe  test    eax, eax
0x180053400  js      loc_1800534E7
0x180053406  mov     ecx, 228h; Size
0x18005340b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053410  mov     ecx, [rdi+1E0h]
0x180053416  mov     r9, rdi; struct WdcDataCollectorSetFolder *
0x180053419  mov     r8, [rdi+1C0h]; unsigned __int16 *
0x180053420  mov     rdx, [rdi+30h]; unsigned __int16 *
0x180053424  mov     [rsp+60h+var_30], r14d; int
0x180053429  mov     [rsp+60h+var_38], ecx; int
0x18005342d  mov     rcx, [rbp+arg_10]
0x180053431  mov     [rsp+60h+var_40], rcx; struct IDataCollectorSet *
0x180053436  mov     rcx, rax; this
0x180053439  call    ??0WdcDataCollectorSetNode@@QEAA@PEBG0PEAVWdcDataCollectorSetFolder@@PEAUIDataCollectorSet@@HH@Z; WdcDataCollectorSetNode::WdcDataCollectorSetNode(ushort const *,ushort const *,WdcDataCollectorSetFolder *,IDataCollectorSet *,int,int)
0x18005343e  mov     r14, rax
0x180053441  test    rax, rax
0x180053444  jz      loc_18005326A
0x18005344a  lea     rcx, [rdi+48h]
0x18005344e  mov     dword ptr [rax+18h], 0Bh
0x180053455  mov     rdx, [rcx+8]
0x180053459  cmp     [rdx], rcx
0x18005345c  jz      short loc_18005348E
0x18005345e  mov     ecx, 3
0x180053463  int     29h; Win8: RtlFailFast(ecx)
0x180053465  mov     rcx, [rbp+var_18]
0x180053469  mov     rdx, [rdi+70h]
0x18005346d  mov     rax, [rcx]
0x180053470  mov     rax, [rax+50h]
0x180053474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053479  jmp     loc_1800533AF
0x18005347e  mov     edx, r14d; int
0x180053481  mov     rcx, rdi; this
0x180053484  call    ?SetDirty@WdcBaseNode@@QEAAJH@Z; WdcBaseNode::SetDirty(int)
0x180053489  jmp     loc_1800533C4
0x18005348e  add     rax, 8
0x180053492  mov     [rax+8], rdx
0x180053496  mov     [rax], rcx
0x180053499  mov     [rdx], rax
0x18005349c  mov     rdx, r13
0x18005349f  mov     [rcx+8], rax
0x1800534a3  mov     rcx, r14
0x1800534a6  mov     rax, [r14]
0x1800534a9  mov     rax, [rax+0D0h]
0x1800534b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534b5  mov     ebx, eax
0x1800534b7  test    eax, eax
0x1800534b9  js      short loc_1800534E7
0x1800534bb  mov     rcx, [rdi+38h]
0x1800534bf  test    rcx, rcx
0x1800534c2  jz      short loc_1800534CE
0x1800534c4  cmp     r15w, [rcx]
0x1800534c8  jz      short loc_1800534CE
0x1800534ca  mov     [rdi+40h], r14
0x1800534ce  mov     rax, [rsi]
0x1800534d1  mov     rcx, rsi
0x1800534d4  mov     rdx, [rbp+arg_0]
0x1800534d8  mov     rax, [rax+10h]
0x1800534dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534e1  mov     ebx, eax
0x1800534e3  test    eax, eax
0x1800534e5  jns     short loc_180053508
0x1800534e7  mov     dword ptr [rsp+60h+var_40], eax
0x1800534eb  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800534f2  xor     r8d, r8d; int
0x1800534f5  lea     rdx, aWdcdatacollect_81; "WdcDataCollectorSetFolder::CommandDataC"...
0x1800534fc  lea     rcx, aBaseDiagnosisP_1; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180053503  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180053508  mov     rcx, [rbp+bstrString]; bstrString
0x18005350c  test    rcx, rcx
0x18005350f  jz      short loc_18005351B
0x180053511  call    cs:__imp_SysFreeString
0x180053517  mov     [rbp+bstrString], r15
0x18005351b  mov     rcx, [rbp+arg_10]
0x18005351f  test    rcx, rcx
0x180053522  jz      short loc_180053534
0x180053524  mov     rax, [rcx]
0x180053527  mov     rax, [rax+10h]
0x18005352b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053530  mov     [rbp+arg_10], r15
0x180053534  test    rsi, rsi
0x180053537  jz      short loc_180053541
0x180053539  mov     rcx, rsi; this
0x18005353c  call    ?Release@WdcDataPortal@@QEAAXXZ; WdcDataPortal::Release(void)
0x180053541  mov     rcx, [rbp+var_18]
0x180053545  test    rcx, rcx
0x180053548  jz      short loc_180053556
0x18005354a  mov     rax, [rcx]
0x18005354d  mov     rax, [rax+10h]
0x180053551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053556  mov     eax, ebx
0x180053558  mov     rbx, [rsp+60h+arg_8]
0x180053560  add     rsp, 60h
0x180053564  pop     r15
0x180053566  pop     r14
0x180053568  pop     r13
0x18005356a  pop     r12
0x18005356c  pop     rdi
0x18005356d  pop     rsi
0x18005356e  pop     rbp
0x18005356f  retn
```
