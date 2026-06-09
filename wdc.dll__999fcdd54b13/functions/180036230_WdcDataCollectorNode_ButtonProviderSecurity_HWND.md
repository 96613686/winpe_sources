# WdcDataCollectorNode::ButtonProviderSecurity(HWND__ *)

- ea: `0x180036230`
- end: `0x1800364fd`
- name: `?ButtonProviderSecurity@WdcDataCollectorNode@@AEAAJPEAUHWND__@@@Z`
- size: `717`
- prototype: `__int64 __fastcall(OLECHAR *this, HWND)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064020`

## callees

- `0x1800044ac`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x180036230`
- `0x18003a7cc`
- `0x18003b0ac`
- `0x180063090`
- `0x180065d78`
- `0x1800669e8`
- `0x180068f70`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800363a9`
- `KERNEL32!GetLastError` at `0x1800363d6`
- `KERNEL32!GetLastError` at `0x1800363a9`
- `KERNEL32!GetLastError` at `0x1800363d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003645c`
- `OLEAUT32!__imp_SysFreeString` at `0x180036473`
- `OLEAUT32!__imp_SysFreeString` at `0x18003645c`
- `OLEAUT32!__imp_SysFreeString` at `0x180036473`
- `ACLUI!__imp_CreateSecurityPage` at `0x18003639a`
- `ACLUI!__imp_CreateSecurityPage` at `0x18003639a`

## string_xrefs

- `0x1800364d5`: `WdcDataCollectorNode::ButtonProviderSecurity`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorNode::ButtonProviderSecurity(OLECHAR *this, HWND a2)
{
  unsigned __int16 *v3; // rsi
  WCHAR *v4; // rdi
  int SelectedProvider; // eax
  const char *v6; // rdx
  int v7; // r8d
  signed int v8; // ebx
  const char *v9; // rdx
  int v10; // r8d
  WdcSecurityObject *v11; // rax
  ISecurityInformation *v12; // rax
  HPROPSHEETPAGE SecurityPage; // rax
  signed int LastError; // eax
  signed int v15; // eax
  unsigned __int16 *v17; // [rsp+20h] [rbp-59h]
  struct _PSP *v18; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v19[2]; // [rsp+50h] [rbp-29h] BYREF
  HWND v20; // [rsp+58h] [rbp-21h]
  HINSTANCE v21; // [rsp+60h] [rbp-19h]
  __int64 v22; // [rsp+68h] [rbp-11h]
  unsigned __int16 *v23; // [rsp+70h] [rbp-9h]
  int v24; // [rsp+78h] [rbp-1h]
  struct _PSP **v25; // [rsp+88h] [rbp+Fh]
  BSTR v26; // [rsp+E0h] [rbp+67h] BYREF
  struct ITraceDataProvider *v27; // [rsp+F0h] [rbp+77h] BYREF
  BSTR bstrString; // [rsp+F8h] [rbp+7Fh] BYREF

  v26 = this;
  v18 = 0;
  memset_0(v19, 0, 0x60u);
  v3 = 0;
  v26 = 0;
  v27 = 0;
  bstrString = 0;
  v4 = 0;
  SelectedProvider = WdcDataCollectorNode::GetSelectedProvider(a2, 0x961u, &v27);
  v8 = SelectedProvider;
  if ( SelectedProvider < 0 )
    goto LABEL_37;
  if ( SelectedProvider == 1 )
  {
LABEL_23:
    v8 = 1;
    goto LABEL_24;
  }
  v4 = (WCHAR *)WdcAlloc(0x800u, v6, v7);
  if ( v4 )
  {
    *v4 = 0;
    v3 = (unsigned __int16 *)WdcAlloc(0x800u, v9, v10);
    if ( v3 )
    {
      *v3 = 0;
      SelectedProvider = WdcLoadString(0x5Bu, v4, 0x400u);
      v8 = SelectedProvider;
      if ( SelectedProvider < 0 )
        goto LABEL_37;
      SelectedProvider = ((__int64 (__fastcall *)(struct ITraceDataProvider *, BSTR *))v27->lpVtbl->get_DisplayName)(
                           v27,
                           &v26);
      v8 = SelectedProvider;
      if ( SelectedProvider < 0 )
        goto LABEL_37;
      SelectedProvider = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64, BSTR *))v27->lpVtbl->GetSecurity)(
                           v27,
                           15,
                           &bstrString);
      v8 = SelectedProvider;
      if ( SelectedProvider < 0 )
        goto LABEL_37;
      SelectedProvider = StringCchPrintfW(v3, 0x400u, v4, v26);
      v8 = SelectedProvider;
      if ( SelectedProvider < 0 )
        goto LABEL_37;
      v11 = (WdcSecurityObject *)operator new(0x50u);
      v12 = (ISecurityInformation *)WdcSecurityObject::WdcSecurityObject(
                                      v11,
                                      (__int64)v27,
                                      (int (*)(__int64, unsigned __int16 *))WdcDataCollectorNode::SetProviderSecurity,
                                      bstrString,
                                      v26,
                                      1,
                                      0);
      if ( v12 )
      {
        SecurityPage = CreateSecurityPage(v12);
        v18 = SecurityPage;
        if ( !SecurityPage )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( !LastError )
          {
LABEL_35:
            v8 = -2147467259;
LABEL_36:
            SelectedProvider = v8;
            goto LABEL_37;
          }
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          if ( v8 < 0 )
            goto LABEL_36;
          SecurityPage = v18;
        }
        if ( SecurityPage != (HPROPSHEETPAGE)-1LL )
          goto LABEL_22;
        v15 = GetLastError();
        v8 = v15;
        if ( v15 )
        {
          if ( v15 > 0 )
            v8 = (unsigned __int16)v15 | 0x80070000;
          if ( v8 >= 0 )
          {
LABEL_22:
            memset_0(v19, 0, 0x60u);
            v21 = g_hInstance;
            v25 = &v18;
            v19[0] = 96;
            v19[1] = 4;
            v20 = a2;
            v24 = 1;
            v22 = 108;
            v23 = v3;
            if ( IsolationAwarePropertySheetW(v19) > 0 )
              goto LABEL_24;
            goto LABEL_23;
          }
          goto LABEL_36;
        }
        goto LABEL_35;
      }
    }
  }
  SelectedProvider = -2147024882;
  v8 = -2147024882;
LABEL_37:
  LODWORD(v17) = SelectedProvider;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectornode.cpp",
    "WdcDataCollectorNode::ButtonProviderSecurity",
    0,
    L"FAILURE: 0x%08x",
    v17);
  WdcShowErrorMessage(a2, 0x32Du, v8);
LABEL_24:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v26 )
  {
    SysFreeString(v26);
    v26 = 0;
  }
  if ( v3 )
    WdcFree(v3, v6, v7);
  if ( v4 )
    WdcFree(v4, v6, v7);
  if ( v27 )
    ((void (__fastcall *)(struct ITraceDataProvider *))v27->lpVtbl->Release)(v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180036230  mov     [rsp-8+arg_0], rcx
0x180036235  push    rbp
0x180036236  push    rbx
0x180036237  push    rsi
0x180036238  push    rdi
0x180036239  push    r14
0x18003623b  lea     rbp, [rsp-37h]
0x180036240  sub     rsp, 0B0h
0x180036247  mov     r14, rdx
0x18003624a  mov     [rbp+57h+var_90], 0
0x180036252  xor     edx, edx; Val
0x180036254  lea     rcx, [rbp+57h+var_80]; void *
0x180036258  lea     r8d, [rdx+60h]; Size
0x18003625c  call    memset_0
0x180036261  xor     esi, esi
0x180036263  mov     [rbp+57h+arg_0], 0
0x18003626b  lea     r8, [rbp+57h+arg_10]; struct ITraceDataProvider **
0x18003626f  mov     [rbp+57h+arg_10], rsi
0x180036273  mov     edx, 961h; nIDDlgItem
0x180036278  mov     [rbp+57h+bstrString], 0
0x180036280  mov     rcx, r14; hDlg
0x180036283  xor     edi, edi
0x180036285  call    ?GetSelectedProvider@WdcDataCollectorNode@@CAJPEAUHWND__@@KPEAPEAUITraceDataProvider@@@Z; WdcDataCollectorNode::GetSelectedProvider(HWND__ *,ulong,ITraceDataProvider * *)
0x18003628a  mov     ebx, eax
0x18003628c  test    eax, eax
0x18003628e  js      loc_1800364C7
0x180036294  cmp     eax, 1
0x180036297  jz      loc_18003644E
0x18003629d  mov     ebx, 800h
0x1800362a2  mov     ecx, ebx; dwBytes
0x1800362a4  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800362a9  mov     rdi, rax
0x1800362ac  test    rax, rax
0x1800362af  jnz     short loc_1800362BD
0x1800362b1  mov     eax, 8007000Eh
0x1800362b6  mov     ebx, eax
0x1800362b8  jmp     loc_1800364C7
0x1800362bd  xor     eax, eax
0x1800362bf  mov     rcx, rbx; dwBytes
0x1800362c2  mov     [rdi], ax
0x1800362c5  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800362ca  mov     rsi, rax
0x1800362cd  test    rax, rax
0x1800362d0  jz      short loc_1800362B1
0x1800362d2  xor     eax, eax
0x1800362d4  mov     r8d, 400h; cchBufferMax
0x1800362da  mov     rdx, rdi; lpBuffer
0x1800362dd  mov     [rsi], ax
0x1800362e0  lea     ecx, [rax+5Bh]; uID
0x1800362e3  call    ?WdcLoadString@@YAJKPEAG_K@Z; WdcLoadString(ulong,ushort *,unsigned __int64)
0x1800362e8  mov     ebx, eax
0x1800362ea  test    eax, eax
0x1800362ec  js      loc_1800364C7
0x1800362f2  mov     rcx, [rbp+57h+arg_10]
0x1800362f6  lea     rdx, [rbp+57h+arg_0]
0x1800362fa  mov     rax, [rcx]
0x1800362fd  mov     rax, [rax+38h]
0x180036301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036306  mov     ebx, eax
0x180036308  test    eax, eax
0x18003630a  js      loc_1800364C7
0x180036310  mov     rcx, [rbp+57h+arg_10]
0x180036314  lea     r8, [rbp+57h+bstrString]
0x180036318  mov     edx, 0Fh
0x18003631d  mov     rax, [rcx]
0x180036320  mov     rax, [rax+0C0h]
0x180036327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003632c  mov     ebx, eax
0x18003632e  test    eax, eax
0x180036330  js      loc_1800364C7
0x180036336  mov     r9, [rbp+57h+arg_0]
0x18003633a  mov     r8, rdi; unsigned __int16 *
0x18003633d  mov     edx, 400h; unsigned __int64
0x180036342  mov     rcx, rsi; unsigned __int16 *
0x180036345  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003634a  mov     ebx, eax
0x18003634c  test    eax, eax
0x18003634e  js      loc_1800364C7
0x180036354  mov     ecx, 50h ; 'P'; Size
0x180036359  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003635e  mov     rcx, [rbp+57h+arg_0]
0x180036362  lea     r8, ?SetProviderSecurity@WdcDataCollectorNode@@CAJ_JPEAG@Z; int (*)(__int64, unsigned __int16 *)
0x180036369  mov     r9, [rbp+57h+bstrString]; unsigned __int16 *
0x18003636d  mov     rdx, [rbp+57h+arg_10]; __int64
0x180036371  mov     [rsp+0D0h+var_A0], 0; int
0x180036379  mov     [rsp+0D0h+var_A8], 1; int
0x180036381  mov     [rsp+0D0h+var_B0], rcx; unsigned __int16 *
0x180036386  mov     rcx, rax; this
0x180036389  call    ??0WdcSecurityObject@@QEAA@_JP6AJ0PEAG@Z11HH@Z; WdcSecurityObject::WdcSecurityObject(__int64,long (*)(__int64,ushort *),ushort *,ushort *,int,int)
0x18003638e  test    rax, rax
0x180036391  jz      loc_1800362B1
0x180036397  mov     rcx, rax; psi
0x18003639a  call    cs:__imp_CreateSecurityPage
0x1800363a0  mov     [rbp+57h+var_90], rax
0x1800363a4  test    rax, rax
0x1800363a7  jnz     short loc_1800363D0
0x1800363a9  call    cs:__imp_GetLastError
0x1800363af  mov     ebx, eax
0x1800363b1  test    eax, eax
0x1800363b3  jz      loc_1800364C0
0x1800363b9  jle     short loc_1800363C4
0x1800363bb  movzx   ebx, ax
0x1800363be  or      ebx, 80070000h
0x1800363c4  test    ebx, ebx
0x1800363c6  js      loc_1800364C5
0x1800363cc  mov     rax, [rbp+57h+var_90]
0x1800363d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800363d4  jnz     short loc_1800363F9
0x1800363d6  call    cs:__imp_GetLastError
0x1800363dc  mov     ebx, eax
0x1800363de  test    eax, eax
0x1800363e0  jz      loc_1800364C0
0x1800363e6  jle     short loc_1800363F1
0x1800363e8  movzx   ebx, ax
0x1800363eb  or      ebx, 80070000h
0x1800363f1  test    ebx, ebx
0x1800363f3  js      loc_1800364C5
0x1800363f9  xor     edx, edx; Val
0x1800363fb  lea     rcx, [rbp+57h+var_80]; void *
0x1800363ff  lea     r8d, [rdx+60h]; Size
0x180036403  call    memset_0
0x180036408  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18003640f  lea     rcx, [rbp+57h+var_80]
0x180036413  mov     [rbp+57h+var_70], rax
0x180036417  lea     rax, [rbp+57h+var_90]
0x18003641b  mov     [rbp+57h+var_48], rax
0x18003641f  mov     [rbp+57h+var_80], 60h ; '`'
0x180036426  mov     [rbp+57h+var_7C], 4
0x18003642d  mov     [rbp+57h+var_78], r14
0x180036431  mov     [rbp+57h+var_58], 1
0x180036438  mov     [rbp+57h+var_68], 6Ch ; 'l'
0x180036440  mov     [rbp+57h+var_60], rsi
0x180036444  call    IsolationAwarePropertySheetW
0x180036449  test    rax, rax
0x18003644c  jg      short loc_180036453
0x18003644e  mov     ebx, 1
0x180036453  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180036457  test    rcx, rcx
0x18003645a  jz      short loc_18003646A
0x18003645c  call    cs:__imp_SysFreeString
0x180036462  mov     [rbp+57h+bstrString], 0
0x18003646a  mov     rcx, [rbp+57h+arg_0]; bstrString
0x18003646e  test    rcx, rcx
0x180036471  jz      short loc_180036481
0x180036473  call    cs:__imp_SysFreeString
0x180036479  mov     [rbp+57h+arg_0], 0
0x180036481  test    rsi, rsi
0x180036484  jz      short loc_18003648E
0x180036486  mov     rcx, rsi; void *
0x180036489  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18003648e  test    rdi, rdi
0x180036491  jz      short loc_18003649B
0x180036493  mov     rcx, rdi; void *
0x180036496  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18003649b  mov     rcx, [rbp+57h+arg_10]
0x18003649f  test    rcx, rcx
0x1800364a2  jz      short loc_1800364B0
0x1800364a4  mov     rax, [rcx]
0x1800364a7  mov     rax, [rax+10h]
0x1800364ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364b0  mov     eax, ebx
0x1800364b2  add     rsp, 0B0h
0x1800364b9  pop     r14
0x1800364bb  pop     rdi
0x1800364bc  pop     rsi
0x1800364bd  pop     rbx
0x1800364be  pop     rbp
0x1800364bf  retn
0x1800364c0  mov     ebx, 80004005h
0x1800364c5  mov     eax, ebx
0x1800364c7  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800364ce  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800364d2  xor     r8d, r8d; int
0x1800364d5  lea     rdx, aWdcdatacollect_105; "WdcDataCollectorNode::ButtonProviderSec"...
0x1800364dc  lea     rcx, aBaseDiagnosisP_17; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x1800364e3  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800364e8  mov     r8d, ebx; int
0x1800364eb  mov     edx, 32Dh; unsigned int
0x1800364f0  mov     rcx, r14; HWND
0x1800364f3  call    ?WdcShowErrorMessage@@YAJPEAUHWND__@@KJ@Z; WdcShowErrorMessage(HWND__ *,ulong,long)
0x1800364f8  jmp     loc_180036453
```
