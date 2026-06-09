# WdcDataCollectorSetNode::CommandCreateTraceSession(WdcConsoleManager *)

- ea: `0x1800559ac`
- end: `0x180055cfa`
- name: `?CommandCreateTraceSession@WdcDataCollectorSetNode@@AEAAJPEAVWdcConsoleManager@@@Z`
- size: `846`
- prototype: `__int64 __fastcall(WdcDataCollectorSetNode *__hidden this, struct WdcConsoleManager *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180057a60`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x180049054`
- `0x180049cec`
- `0x18004befc`
- `0x1800559ac`
- `0x1800571b4`
- `0x180057760`
- `0x180066e18`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180055b24`
- `OLEAUT32!__imp_SysAllocString` at `0x180055b24`
- `OLEAUT32!__imp_SysFreeString` at `0x180055b17`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180055b17`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c8e`
- `ole32!CoCreateInstance` at `0x180055aa4`
- `ole32!CoCreateInstance` at `0x180055aa4`

## string_xrefs

- `0x180055a06`: `WdcDataCollectorSetNode::CommandCreateTraceSession`
- `0x180055a3e`: `WdcDataCollectorSetNode::CommandCreateTraceSession`
- `0x180055c5b`: `WdcDataCollectorSetNode::CommandCreateTraceSession`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetNode::CommandCreateTraceSession(
        WdcDataCollectorSetNode *this,
        struct WdcConsoleManager *a2)
{
  int MainWindow; // eax
  unsigned int v5; // ebx
  HRESULT Name; // eax
  const char *v7; // rdx
  int v8; // r8d
  unsigned __int16 *v9; // rax
  OLECHAR *v10; // rsi
  int v11; // eax
  OLECHAR *v12; // rax
  OLECHAR *v13; // r14
  const char *v14; // rdx
  int v15; // r8d
  __int64 v16; // rcx
  WdcBaseNode *v17; // rcx
  struct WdcBaseNode *v18; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-30h]
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  BSTR v22; // [rsp+38h] [rbp-18h] BYREF
  struct IDataCollectorSet *v23; // [rsp+40h] [rbp-10h] BYREF
  HWND v24; // [rsp+48h] [rbp-8h] BYREF
  struct IUnknown *v25; // [rsp+90h] [rbp+40h] BYREF
  __int64 v26; // [rsp+98h] [rbp+48h] BYREF

  v24 = 0;
  bstrString = 0;
  v22 = 0;
  v26 = 0;
  v23 = 0;
  v25 = 0;
  MainWindow = WdcConsoleManager::GetMainWindow(a2, &v24);
  v5 = MainWindow;
  if ( MainWindow < 0 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
      "WdcDataCollectorSetNode::CommandCreateTraceSession",
      0,
      L"FAILURE: 0x%08x",
      MainWindow);
    goto LABEL_34;
  }
  Name = WdcDataCollectorSetNode::GetName(this, &bstrString);
  v5 = Name;
  if ( Name < 0 )
    goto LABEL_4;
  Name = WdcDataCollectorSetNode::GetDataSet(this, 0, &v23);
  v5 = Name;
  if ( Name < 0
    || (Name = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR *))v23->lpVtbl->get_Xml)(v23, &v22),
        v5 = Name,
        Name < 0)
    || (Name = CoCreateInstance(&CLSID_DataCollectorSet, 0, 0x15u, &IID_IDataCollectorSet, (LPVOID *)&v25),
        v5 = Name,
        Name < 0)
    || (Name = WdcCoSetSecurity(v25), v5 = Name, Name < 0) )
  {
LABEL_4:
    LODWORD(ppv) = Name;
LABEL_5:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
      "WdcDataCollectorSetNode::CommandCreateTraceSession",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_32;
  }
  v9 = (unsigned __int16 *)WdcAlloc(0x800u, v7, v8);
  v10 = v9;
  if ( !v9 )
  {
    v5 = -2147024882;
    LODWORD(ppv) = -2147024882;
    goto LABEL_5;
  }
  *v9 = 0;
  v11 = StringCchPrintfW(v9, 0x400u, L"session\\%s", *((_QWORD *)this + 68));
  v5 = v11;
  if ( v11 < 0 )
    goto LABEL_29;
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v12 = SysAllocString(v10);
  v13 = v12;
  if ( !v12 )
  {
    LODWORD(ppv) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", ppv);
    v5 = -2147024882;
    LODWORD(ppv) = -2147024882;
LABEL_30:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
      "WdcDataCollectorSetNode::CommandCreateTraceSession",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_31;
  }
  bstrString = v12;
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, __int64 *))v25->lpVtbl[21].AddRef)(v25, v22, &v26);
  v5 = v11;
  if ( v11 < 0 )
    goto LABEL_29;
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *, _QWORD, __int64, __int64 *))v25->lpVtbl[20].QueryInterface)(
          v25,
          v13,
          *((_QWORD *)this + 6),
          1,
          &v26);
  v5 = v11;
  if ( v11 < 0
    || (v11 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v25->lpVtbl[20].Release)(v25, 0), v5 = v11, v11 < 0) )
  {
LABEL_29:
    LODWORD(ppv) = v11;
    goto LABEL_30;
  }
  v16 = *(_QWORD *)(*((_QWORD *)this + 57) + 440LL);
  if ( v16 )
  {
    v17 = *(WdcBaseNode **)(v16 + 448);
    if ( v17 )
    {
      v11 = WdcBaseNode::SetDirty(v17, 1);
      v5 = v11;
      if ( v11 >= 0 )
      {
        v11 = WdcConsoleManager::Select(a2, v18);
        v5 = v11;
        if ( v11 >= 0 )
          goto LABEL_31;
      }
      goto LABEL_29;
    }
  }
  v5 = 0;
LABEL_31:
  WdcFree(v10, v14, v15);
LABEL_32:
  if ( bstrString )
    SysFreeString(bstrString);
LABEL_34:
  if ( v22 )
  {
    SysFreeString(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    ((void (__fastcall *)(struct IDataCollectorSet *))v23->lpVtbl->Release)(v23);
    v23 = 0;
  }
  if ( v25 )
  {
    ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
    v25 = 0;
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return v5;
}

```

## disassembly

```asm
0x1800559ac  mov     [rsp-28h+arg_0], rbx
0x1800559b1  mov     [rsp-28h+arg_8], rsi
0x1800559b6  push    rbp
0x1800559b7  push    rdi
0x1800559b8  push    r12
0x1800559ba  push    r14
0x1800559bc  push    r15
0x1800559be  mov     rbp, rsp
0x1800559c1  sub     rsp, 50h
0x1800559c5  xor     r12d, r12d
0x1800559c8  mov     r15, rdx
0x1800559cb  mov     rdi, rcx
0x1800559ce  mov     [rbp+var_8], r12
0x1800559d2  mov     rcx, r15; this
0x1800559d5  mov     [rbp+bstrString], r12
0x1800559d9  lea     rdx, [rbp+var_8]; HWND *
0x1800559dd  mov     [rbp+var_18], r12
0x1800559e1  mov     [rbp+arg_18], r12
0x1800559e5  mov     [rbp+var_10], r12
0x1800559e9  mov     [rbp+arg_10], r12
0x1800559ed  call    ?GetMainWindow@WdcConsoleManager@@QEAAJPEAPEAUHWND__@@@Z; WdcConsoleManager::GetMainWindow(HWND__ * *)
0x1800559f2  mov     ebx, eax
0x1800559f4  test    eax, eax
0x1800559f6  jns     short loc_180055A1E
0x1800559f8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800559ff  mov     dword ptr [rsp+50h+ppv], eax
0x180055a03  xor     r8d, r8d; int
0x180055a06  lea     rdx, aWdcdatacollect_137; "WdcDataCollectorSetNode::CommandCreateT"...
0x180055a0d  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180055a14  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180055a19  jmp     loc_180055C85
0x180055a1e  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180055a22  mov     rcx, rdi; this
0x180055a25  call    ?GetName@WdcDataCollectorSetNode@@IEAAJPEAPEAG@Z; WdcDataCollectorSetNode::GetName(ushort * *)
0x180055a2a  mov     ebx, eax
0x180055a2c  test    eax, eax
0x180055a2e  jns     short loc_180055A56
0x180055a30  mov     dword ptr [rsp+50h+ppv], eax
0x180055a34  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180055a3b  xor     r8d, r8d; int
0x180055a3e  lea     rdx, aWdcdatacollect_137; "WdcDataCollectorSetNode::CommandCreateT"...
0x180055a45  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180055a4c  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180055a51  jmp     loc_180055C76
0x180055a56  lea     r8, [rbp+var_10]; struct IDataCollectorSet **
0x180055a5a  xor     edx, edx; int
0x180055a5c  mov     rcx, rdi; this
0x180055a5f  call    ?GetDataSet@WdcDataCollectorSetNode@@IEAAJHPEAPEAUIDataCollectorSet@@@Z; WdcDataCollectorSetNode::GetDataSet(int,IDataCollectorSet * *)
0x180055a64  mov     ebx, eax
0x180055a66  test    eax, eax
0x180055a68  js      short loc_180055A30
0x180055a6a  mov     rcx, [rbp+var_10]
0x180055a6e  lea     rdx, [rbp+var_18]
0x180055a72  mov     rax, [rcx]
0x180055a75  mov     rax, [rax+1A0h]
0x180055a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a81  mov     ebx, eax
0x180055a83  test    eax, eax
0x180055a85  js      short loc_180055A30
0x180055a87  xor     edx, edx; pUnkOuter
0x180055a89  lea     rax, [rbp+arg_10]
0x180055a8d  lea     r9, IID_IDataCollectorSet; riid
0x180055a94  mov     [rsp+50h+ppv], rax; ppv
0x180055a99  lea     rcx, CLSID_DataCollectorSet; rclsid
0x180055aa0  lea     r8d, [rdx+15h]; dwClsContext
0x180055aa4  call    cs:__imp_CoCreateInstance
0x180055aaa  mov     ebx, eax
0x180055aac  test    eax, eax
0x180055aae  js      short loc_180055A30
0x180055ab0  mov     rcx, [rbp+arg_10]; struct IUnknown *
0x180055ab4  call    ?WdcCoSetSecurity@@YAJPEAUIUnknown@@@Z; WdcCoSetSecurity(IUnknown *)
0x180055ab9  mov     ebx, eax
0x180055abb  test    eax, eax
0x180055abd  js      loc_180055A30
0x180055ac3  mov     ecx, 800h; dwBytes
0x180055ac8  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180055acd  mov     rsi, rax
0x180055ad0  test    rax, rax
0x180055ad3  jnz     short loc_180055AE5
0x180055ad5  mov     edi, 8007000Eh
0x180055ada  mov     ebx, edi
0x180055adc  mov     dword ptr [rsp+50h+ppv], edi
0x180055ae0  jmp     loc_180055A34
0x180055ae5  mov     [rax], r12w
0x180055ae9  lea     r8, aSessionS; "session\\%s"
0x180055af0  mov     r9, [rdi+220h]
0x180055af7  mov     edx, 400h; unsigned __int64
0x180055afc  mov     rcx, rsi; unsigned __int16 *
0x180055aff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055b04  mov     ebx, eax
0x180055b06  test    eax, eax
0x180055b08  js      loc_180055C4D
0x180055b0e  mov     rcx, [rbp+bstrString]; bstrString
0x180055b12  test    rcx, rcx
0x180055b15  jz      short loc_180055B21
0x180055b17  call    cs:__imp_SysFreeString
0x180055b1d  mov     [rbp+bstrString], r12
0x180055b21  mov     rcx, rsi; psz
0x180055b24  call    cs:__imp_SysAllocString
0x180055b2a  mov     r14, rax
0x180055b2d  test    rax, rax
0x180055b30  jnz     short loc_180055B63
0x180055b32  mov     edi, 8007000Eh
0x180055b37  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180055b3e  xor     r8d, r8d; int
0x180055b41  mov     dword ptr [rsp+50h+ppv], edi
0x180055b45  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180055b4c  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180055b53  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180055b58  mov     ebx, edi
0x180055b5a  mov     dword ptr [rsp+50h+ppv], edi
0x180055b5e  jmp     loc_180055C51
0x180055b63  mov     [rbp+bstrString], r14
0x180055b67  mov     rcx, [rbp+arg_18]
0x180055b6b  test    rcx, rcx
0x180055b6e  jz      short loc_180055B80
0x180055b70  mov     rax, [rcx]
0x180055b73  mov     rax, [rax+10h]
0x180055b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b7c  mov     [rbp+arg_18], r12
0x180055b80  mov     rcx, [rbp+arg_10]
0x180055b84  lea     r8, [rbp+arg_18]
0x180055b88  mov     rdx, [rbp+var_18]
0x180055b8c  mov     rax, [rcx]
0x180055b8f  mov     rax, [rax+200h]
0x180055b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b9b  mov     ebx, eax
0x180055b9d  test    eax, eax
0x180055b9f  js      loc_180055C4D
0x180055ba5  mov     rcx, [rbp+arg_18]
0x180055ba9  test    rcx, rcx
0x180055bac  jz      short loc_180055BBE
0x180055bae  mov     rax, [rcx]
0x180055bb1  mov     rax, [rax+10h]
0x180055bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055bba  mov     [rbp+arg_18], r12
0x180055bbe  mov     rcx, [rbp+arg_10]
0x180055bc2  lea     rdx, [rbp+arg_18]
0x180055bc6  mov     r8, [rdi+30h]
0x180055bca  mov     r9d, 1
0x180055bd0  mov     [rsp+50h+ppv], rdx
0x180055bd5  mov     rdx, r14
0x180055bd8  mov     rax, [rcx]
0x180055bdb  mov     rax, [rax+1E0h]
0x180055be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055be7  mov     ebx, eax
0x180055be9  test    eax, eax
0x180055beb  js      short loc_180055C4D
0x180055bed  mov     rcx, [rbp+arg_10]
0x180055bf1  xor     edx, edx
0x180055bf3  mov     rax, [rcx]
0x180055bf6  mov     rax, [rax+1F0h]
0x180055bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c02  mov     ebx, eax
0x180055c04  test    eax, eax
0x180055c06  js      short loc_180055C4D
0x180055c08  mov     rax, [rdi+1C8h]
0x180055c0f  mov     rcx, [rax+1B8h]
0x180055c16  test    rcx, rcx
0x180055c19  jnz     short loc_180055C20
0x180055c1b  mov     ebx, r12d
0x180055c1e  jmp     short loc_180055C6E
0x180055c20  mov     rcx, [rcx+1C0h]; this
0x180055c27  test    rcx, rcx
0x180055c2a  jz      short loc_180055C1B
0x180055c2c  mov     edx, 1; int
0x180055c31  call    ?SetDirty@WdcBaseNode@@QEAAJH@Z; WdcBaseNode::SetDirty(int)
0x180055c36  mov     ebx, eax
0x180055c38  test    eax, eax
0x180055c3a  js      short loc_180055C4D
0x180055c3c  mov     rdx, rcx; struct WdcBaseNode *
0x180055c3f  mov     rcx, r15; this
0x180055c42  call    ?Select@WdcConsoleManager@@QEAAJPEAVWdcBaseNode@@@Z; WdcConsoleManager::Select(WdcBaseNode *)
0x180055c47  mov     ebx, eax
0x180055c49  test    eax, eax
0x180055c4b  jns     short loc_180055C6E
0x180055c4d  mov     dword ptr [rsp+50h+ppv], eax
0x180055c51  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180055c58  xor     r8d, r8d; int
0x180055c5b  lea     rdx, aWdcdatacollect_137; "WdcDataCollectorSetNode::CommandCreateT"...
0x180055c62  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180055c69  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180055c6e  mov     rcx, rsi; void *
0x180055c71  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180055c76  mov     rcx, [rbp+bstrString]; bstrString
0x180055c7a  test    rcx, rcx
0x180055c7d  jz      short loc_180055C85
0x180055c7f  call    cs:__imp_SysFreeString
0x180055c85  mov     rcx, [rbp+var_18]; bstrString
0x180055c89  test    rcx, rcx
0x180055c8c  jz      short loc_180055C98
0x180055c8e  call    cs:__imp_SysFreeString
0x180055c94  mov     [rbp+var_18], r12
0x180055c98  mov     rcx, [rbp+var_10]
0x180055c9c  test    rcx, rcx
0x180055c9f  jz      short loc_180055CB1
0x180055ca1  mov     rax, [rcx]
0x180055ca4  mov     rax, [rax+10h]
0x180055ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055cad  mov     [rbp+var_10], r12
0x180055cb1  mov     rcx, [rbp+arg_10]
0x180055cb5  test    rcx, rcx
0x180055cb8  jz      short loc_180055CCA
0x180055cba  mov     rax, [rcx]
0x180055cbd  mov     rax, [rax+10h]
0x180055cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055cc6  mov     [rbp+arg_10], r12
0x180055cca  mov     rcx, [rbp+arg_18]
0x180055cce  test    rcx, rcx
0x180055cd1  jz      short loc_180055CDF
0x180055cd3  mov     rax, [rcx]
0x180055cd6  mov     rax, [rax+10h]
0x180055cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055cdf  lea     r11, [rsp+50h+var_s0]
0x180055ce4  mov     eax, ebx
0x180055ce6  mov     rbx, [r11+30h]
0x180055cea  mov     rsi, [r11+38h]
0x180055cee  mov     rsp, r11
0x180055cf1  pop     r15
0x180055cf3  pop     r14
0x180055cf5  pop     r12
0x180055cf7  pop     rdi
0x180055cf8  pop     rbp
0x180055cf9  retn
```
