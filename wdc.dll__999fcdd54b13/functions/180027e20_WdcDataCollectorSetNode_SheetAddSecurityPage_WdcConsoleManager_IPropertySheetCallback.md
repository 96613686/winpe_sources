# WdcDataCollectorSetNode::SheetAddSecurityPage(WdcConsoleManager *,IPropertySheetCallback *)

- ea: `0x180027e20`
- end: `0x1800280a8`
- name: `?SheetAddSecurityPage@WdcDataCollectorSetNode@@UEAAJPEAVWdcConsoleManager@@PEAUIPropertySheetCallback@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(WdcDataCollectorSetNode *__hidden this, struct WdcConsoleManager *, struct IPropertySheetCallback *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b854`
- `0x180027e20`
- `0x18003a7cc`
- `0x180049054`
- `0x1800571b4`
- `0x180057a34`
- `0x1800669e8`
- `0x180068f70`
- `0x180086010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180027f6f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180027f6f`
- `KERNEL32!GetLastError` at `0x180027fcb`
- `KERNEL32!GetLastError` at `0x180027fcb`
- `OLEAUT32!__imp_SysAllocString` at `0x180027f11`
- `OLEAUT32!__imp_SysAllocString` at `0x180027f11`
- `OLEAUT32!__imp_SysFreeString` at `0x180027f00`
- `OLEAUT32!__imp_SysFreeString` at `0x18002804b`
- `OLEAUT32!__imp_SysFreeString` at `0x180028062`
- `OLEAUT32!__imp_SysFreeString` at `0x180027f00`
- `OLEAUT32!__imp_SysFreeString` at `0x18002804b`
- `OLEAUT32!__imp_SysFreeString` at `0x180028062`
- `ACLUI!__imp_CreateSecurityPage` at `0x180027fbd`
- `ACLUI!__imp_CreateSecurityPage` at `0x180027fbd`

## string_xrefs

- `0x18002801e`: `WdcDataCollectorSetNode::SheetAddSecurityPage`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetNode::SheetAddSecurityPage(
        WdcDataCollectorSetNode *this,
        struct WdcConsoleManager *a2,
        struct IPropertySheetCallback *a3)
{
  ISecurityInformation *v3; // r14
  signed int MainWindow; // ebx
  __int64 v7; // rax
  __int64 v8; // rcx
  OLECHAR *v9; // rax
  WdcSecurityObject *v10; // rdi
  BOOL v11; // ebx
  int IsTraceSession; // eax
  ISecurityInformation *v13; // rax
  HPROPSHEETPAGE SecurityPage; // rax
  HPROPSHEETPAGE v15; // rdi
  signed int LastError; // eax
  unsigned __int16 *v18; // [rsp+20h] [rbp-48h]
  BSTR v19; // [rsp+40h] [rbp-28h] BYREF
  struct IDataCollectorSet *v20; // [rsp+48h] [rbp-20h] BYREF
  HWND v21; // [rsp+50h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp+50h] BYREF

  v3 = 0;
  v19 = 0;
  bstrString = 0;
  v21 = 0;
  v20 = 0;
  MainWindow = WdcConsoleManager::GetMainWindow(a2, &v21);
  if ( MainWindow < 0 )
    goto LABEL_26;
  v7 = *((_QWORD *)this + 57);
  *((_DWORD *)this + 108) = -1;
  v8 = *(_QWORD *)(v7 + 440);
  if ( v8 && *(_DWORD *)(v8 + 432) )
  {
    MainWindow = 1;
    goto LABEL_27;
  }
  MainWindow = WdcDataCollectorSetNode::GetDataSet(this, 0, &v20);
  if ( MainWindow < 0 )
    goto LABEL_26;
  MainWindow = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR *))v20->lpVtbl->get_Name)(v20, &v19);
  if ( MainWindow < 0 )
    goto LABEL_26;
  MainWindow = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR *))v20->lpVtbl->get_Security)(v20, &bstrString);
  if ( MainWindow < 0 )
    goto LABEL_26;
  if ( bstrString )
  {
    if ( *bstrString )
      goto LABEL_15;
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
  }
  v9 = SysAllocString(&pszTargetName);
  if ( !v9 )
  {
    MainWindow = -2147024882;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
      "WdcAssignString",
      0,
      L"FAILURE: 0x%08x",
      -2147024882);
    goto LABEL_26;
  }
  bstrString = v9;
LABEL_15:
  v10 = (WdcSecurityObject *)operator new(0x50u);
  v11 = _o__wcsnicmp(L"syst", *((_QWORD *)this + 67), 4) == 0;
  IsTraceSession = WdcDataCollectorSetNode::IsTraceSession(this);
  v13 = (ISecurityInformation *)WdcSecurityObject::WdcSecurityObject(
                                  v10,
                                  (__int64)this,
                                  (int (*)(__int64, unsigned __int16 *))WdcDataCollectorSetNode::SecurityCallback,
                                  bstrString,
                                  v19,
                                  IsTraceSession,
                                  v11);
  v3 = v13;
  if ( v13 )
  {
    SecurityPage = CreateSecurityPage(v13);
    v15 = SecurityPage;
    if ( !SecurityPage || SecurityPage == (HPROPSHEETPAGE)-1LL )
    {
      LastError = GetLastError();
      MainWindow = LastError;
      if ( !LastError )
      {
        MainWindow = -2147467259;
        goto LABEL_26;
      }
      if ( LastError > 0 )
        MainWindow = (unsigned __int16)LastError | 0x80070000;
      if ( MainWindow < 0 )
        goto LABEL_26;
    }
    MainWindow = ((__int64 (__fastcall *)(struct IPropertySheetCallback *, HPROPSHEETPAGE))a3->lpVtbl->AddPage)(a3, v15);
    if ( MainWindow >= 0 )
      goto LABEL_27;
    goto LABEL_26;
  }
  MainWindow = -2147024882;
LABEL_26:
  LODWORD(v18) = MainWindow;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
    "WdcDataCollectorSetNode::SheetAddSecurityPage",
    0,
    L"FAILURE: 0x%08x",
    v18);
  WdcShowErrorMessage(v21, 0x32Cu, MainWindow);
LABEL_27:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v19 )
  {
    SysFreeString(v19);
    v19 = 0;
  }
  if ( v3 )
    ((void (__fastcall *)(ISecurityInformation *))v3->lpVtbl->Release)(v3);
  if ( v20 )
    ((void (__fastcall *)(struct IDataCollectorSet *))v20->lpVtbl->Release)(v20);
  return (unsigned int)MainWindow;
}

```

## disassembly

```asm
0x180027e20  push    rbp
0x180027e22  push    rbx
0x180027e23  push    rsi
0x180027e24  push    rdi
0x180027e25  push    r14
0x180027e27  push    r15
0x180027e29  mov     rbp, rsp
0x180027e2c  sub     rsp, 68h
0x180027e30  xor     r14d, r14d
0x180027e33  mov     rax, rdx
0x180027e36  mov     rsi, rcx
0x180027e39  mov     [rbp+var_28], r14
0x180027e3d  mov     rcx, rax; this
0x180027e40  mov     [rbp+bstrString], r14
0x180027e44  lea     rdx, [rbp+var_18]; HWND *
0x180027e48  mov     [rbp+var_18], r14
0x180027e4c  mov     r15, r8
0x180027e4f  mov     [rbp+var_20], r14
0x180027e53  call    ?GetMainWindow@WdcConsoleManager@@QEAAJPEAPEAUHWND__@@@Z; WdcConsoleManager::GetMainWindow(HWND__ * *)
0x180027e58  mov     ebx, eax
0x180027e5a  test    eax, eax
0x180027e5c  js      loc_18002800D
0x180027e62  mov     rax, [rsi+1C8h]
0x180027e69  mov     dword ptr [rsi+1B0h], 0FFFFFFFFh
0x180027e73  mov     rcx, [rax+1B8h]
0x180027e7a  test    rcx, rcx
0x180027e7d  jz      short loc_180027E91
0x180027e7f  cmp     [rcx+1B0h], r14d
0x180027e86  jz      short loc_180027E91
0x180027e88  lea     ebx, [r14+1]
0x180027e8c  jmp     loc_180028042
0x180027e91  lea     r8, [rbp+var_20]; struct IDataCollectorSet **
0x180027e95  xor     edx, edx; int
0x180027e97  mov     rcx, rsi; this
0x180027e9a  call    ?GetDataSet@WdcDataCollectorSetNode@@IEAAJHPEAPEAUIDataCollectorSet@@@Z; WdcDataCollectorSetNode::GetDataSet(int,IDataCollectorSet * *)
0x180027e9f  mov     ebx, eax
0x180027ea1  test    eax, eax
0x180027ea3  js      loc_18002800D
0x180027ea9  mov     rcx, [rbp+var_20]
0x180027ead  lea     rdx, [rbp+var_28]
0x180027eb1  mov     rax, [rcx]
0x180027eb4  mov     rax, [rax+0A0h]
0x180027ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ec0  mov     ebx, eax
0x180027ec2  test    eax, eax
0x180027ec4  js      loc_18002800D
0x180027eca  mov     rcx, [rbp+var_20]
0x180027ece  lea     rdx, [rbp+bstrString]
0x180027ed2  mov     rax, [rcx]
0x180027ed5  mov     rax, [rax+1A8h]
0x180027edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ee1  mov     ebx, eax
0x180027ee3  test    eax, eax
0x180027ee5  js      loc_18002800D
0x180027eeb  mov     rcx, [rbp+bstrString]; bstrString
0x180027eef  test    rcx, rcx
0x180027ef2  jz      short loc_180027F0A
0x180027ef4  xor     eax, eax
0x180027ef6  cmp     ax, [rcx]
0x180027ef9  jnz     short loc_180027F4E
0x180027efb  test    rcx, rcx
0x180027efe  jz      short loc_180027F0A
0x180027f00  call    cs:__imp_SysFreeString
0x180027f06  mov     [rbp+bstrString], r14
0x180027f0a  lea     rcx, pszTargetName; psz
0x180027f11  call    cs:__imp_SysAllocString
0x180027f17  test    rax, rax
0x180027f1a  jnz     short loc_180027F4A
0x180027f1c  lea     rdi, aFailure0x08x; "FAILURE: 0x%08x"
0x180027f23  mov     ebx, 8007000Eh
0x180027f28  mov     r9, rdi; unsigned __int16 *
0x180027f2b  mov     dword ptr [rsp+68h+var_48], ebx
0x180027f2f  xor     r8d, r8d; int
0x180027f32  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180027f39  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180027f40  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180027f45  jmp     loc_180028014
0x180027f4a  mov     [rbp+bstrString], rax
0x180027f4e  mov     ecx, 50h ; 'P'; Size
0x180027f53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027f58  mov     rdx, [rsi+218h]
0x180027f5f  lea     rcx, aSyst; "syst"
0x180027f66  mov     r8d, 4
0x180027f6c  mov     rdi, rax
0x180027f6f  call    cs:__imp__o__wcsnicmp
0x180027f75  xor     ebx, ebx
0x180027f77  mov     rcx, rsi; this
0x180027f7a  test    eax, eax
0x180027f7c  setz    bl
0x180027f7f  call    ?IsTraceSession@WdcDataCollectorSetNode@@QEAAHXZ; WdcDataCollectorSetNode::IsTraceSession(void)
0x180027f84  mov     rcx, [rbp+var_28]
0x180027f88  lea     r8, ?SecurityCallback@WdcDataCollectorSetNode@@SAJ_JPEAG@Z; int (*)(__int64, unsigned __int16 *)
0x180027f8f  mov     r9, [rbp+bstrString]; unsigned __int16 *
0x180027f93  mov     rdx, rsi; __int64
0x180027f96  mov     [rsp+68h+var_38], ebx; int
0x180027f9a  mov     [rsp+68h+var_40], eax; int
0x180027f9e  mov     [rsp+68h+var_48], rcx; unsigned __int16 *
0x180027fa3  mov     rcx, rdi; this
0x180027fa6  call    ??0WdcSecurityObject@@QEAA@_JP6AJ0PEAG@Z11HH@Z; WdcSecurityObject::WdcSecurityObject(__int64,long (*)(__int64,ushort *),ushort *,ushort *,int,int)
0x180027fab  mov     r14, rax
0x180027fae  test    rax, rax
0x180027fb1  jnz     short loc_180027FBA
0x180027fb3  mov     ebx, 8007000Eh
0x180027fb8  jmp     short loc_18002800D
0x180027fba  mov     rcx, rax; psi
0x180027fbd  call    cs:__imp_CreateSecurityPage
0x180027fc3  mov     rdi, rax
0x180027fc6  test    rax, rax
0x180027fc9  jnz     short loc_180027FEF
0x180027fcb  call    cs:__imp_GetLastError
0x180027fd1  mov     ebx, eax
0x180027fd3  test    eax, eax
0x180027fd5  jz      short loc_180027FE8
0x180027fd7  jle     short loc_180027FE2
0x180027fd9  movzx   ebx, ax
0x180027fdc  or      ebx, 80070000h
0x180027fe2  test    ebx, ebx
0x180027fe4  jns     short loc_180027FF5
0x180027fe6  jmp     short loc_18002800D
0x180027fe8  mov     ebx, 80004005h
0x180027fed  jmp     short loc_18002800D
0x180027fef  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180027ff3  jz      short loc_180027FCB
0x180027ff5  mov     rax, [r15]
0x180027ff8  mov     rdx, rdi
0x180027ffb  mov     rcx, r15
0x180027ffe  mov     rax, [rax+18h]
0x180028002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028007  mov     ebx, eax
0x180028009  test    eax, eax
0x18002800b  jns     short loc_180028042
0x18002800d  lea     rdi, aFailure0x08x; "FAILURE: 0x%08x"
0x180028014  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18002801b  xor     r8d, r8d; int
0x18002801e  lea     rdx, aWdcdatacollect_70; "WdcDataCollectorSetNode::SheetAddSecuri"...
0x180028025  mov     r9, rdi; unsigned __int16 *
0x180028028  mov     dword ptr [rsp+68h+var_48], ebx
0x18002802c  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028031  mov     rcx, [rbp+var_18]; HWND
0x180028035  mov     r8d, ebx; int
0x180028038  mov     edx, 32Ch; unsigned int
0x18002803d  call    ?WdcShowErrorMessage@@YAJPEAUHWND__@@KJ@Z; WdcShowErrorMessage(HWND__ *,ulong,long)
0x180028042  mov     rcx, [rbp+bstrString]; bstrString
0x180028046  test    rcx, rcx
0x180028049  jz      short loc_180028059
0x18002804b  call    cs:__imp_SysFreeString
0x180028051  mov     [rbp+bstrString], 0
0x180028059  mov     rcx, [rbp+var_28]; bstrString
0x18002805d  test    rcx, rcx
0x180028060  jz      short loc_180028070
0x180028062  call    cs:__imp_SysFreeString
0x180028068  mov     [rbp+var_28], 0
0x180028070  test    r14, r14
0x180028073  jz      short loc_180028084
0x180028075  mov     rax, [r14]
0x180028078  mov     rcx, r14
0x18002807b  mov     rax, [rax+10h]
0x18002807f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028084  mov     rcx, [rbp+var_20]
0x180028088  test    rcx, rcx
0x18002808b  jz      short loc_180028099
0x18002808d  mov     rax, [rcx]
0x180028090  mov     rax, [rax+10h]
0x180028094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028099  mov     eax, ebx
0x18002809b  add     rsp, 68h
0x18002809f  pop     r15
0x1800280a1  pop     r14
0x1800280a3  pop     rdi
0x1800280a4  pop     rsi
0x1800280a5  pop     rbx
0x1800280a6  pop     rbp
0x1800280a7  retn
```
