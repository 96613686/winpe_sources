# WdcExchangePropertyArray<IAlertDataCollector>(HWND__ *,PROPERTY_EXCHANGE,ulong,IAlertDataCollector *,long (IAlertDataCollector::*)(tagSAFEARRAY * *),long (IAlertDataCollector::*)(tagSAFEARRAY *),WdcValidation *,ushort *,ulong,long (*)(PROPERTY_EXCHANGE,tagLVITEMW *))

- ea: `0x18005b594`
- end: `0x18005b86e`
- name: `??$WdcExchangePropertyArray@UIAlertDataCollector@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIAlertDataCollector@@P82@EAAJPEAPEAUtagSAFEARRAY@@@ZP82@EAAJPEAU3@@ZPEAVWdcValidation@@PEAGKP6AJ1PEAUtagLVITEMW@@@Z@Z`
- size: `730`
- prototype: `__int64(HWND, unsigned int, unsigned int, __int64, SAFEARRAY *psa, _QWORD *ppvData, WdcValidation *, OLECHAR *, int, ...)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18005d50c`
- `0x180060ef0`

## callees

- `0x18000b854`
- `0x180026490`
- `0x18003b0ac`
- `0x180054bb4`
- `0x18005b594`
- `0x18005c6f0`
- `0x18005c710`
- `0x1800627d0`
- `0x1800685ac`
- `0x180069170`
- `0x18006a034`

## import_xrefs

- `USER32!EnableWindow` at `0x18005b623`
- `USER32!EnableWindow` at `0x18005b623`
- `USER32!SendMessageW` at `0x18005b64d`
- `USER32!SendMessageW` at `0x18005b6f0`
- `USER32!SendMessageW` at `0x18005b64d`
- `USER32!SendMessageW` at `0x18005b6f0`
- `USER32!GetDlgItem` at `0x18005b5e4`
- `USER32!GetDlgItem` at `0x18005b5e4`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b731`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b731`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b720`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b720`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005b675`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005b675`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005b852`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005b852`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005b69b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005b69b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b77f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b843`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b77f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b843`

## pseudocode

```c
__int64 WdcExchangePropertyArray<IAlertDataCollector>(
        HWND a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        SAFEARRAY *psa,
        _QWORD *ppvData,
        WdcValidation *a7,
        OLECHAR *a8,
        int a9,
        ...)
{
  unsigned int v13; // ebx
  HWND DlgItem; // rax
  WdcValidation *v15; // r14
  HWND v16; // rdi
  int v17; // eax
  BOOL v18; // edx
  WdcValidation *v19; // rax
  int v20; // r14d
  SAFEARRAY *v21; // rax
  HRESULT AlertItem; // eax
  int i; // esi
  _QWORD *v24; // r14
  OLECHAR *v25; // r15
  OLECHAR *v26; // rcx
  BSTR v27; // rax
  int v28; // eax
  unsigned int v29; // edx
  __int64 (__fastcall *v31)(_QWORD, _QWORD); // [rsp+20h] [rbp-71h]
  _DWORD lParam[6]; // [rsp+30h] [rbp-61h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-49h]
  int v34; // [rsp+50h] [rbp-41h]
  SAFEARRAYBOUND rgsabound; // [rsp+128h] [rbp+97h] BYREF
  va_list rgsabounda; // [rsp+128h] [rbp+97h]
  va_list va1; // [rsp+130h] [rbp+9Fh] BYREF

  va_start(va1, a9);
  va_start(rgsabounda, a9);
  rgsabound = va_arg(va1, SAFEARRAYBOUND);
  v13 = 0;
  memset_0(lParam, 0, 0x58u);
  rgsabound = 0;
  psa = 0;
  ppvData = 0;
  DlgItem = GetDlgItem(a1, a3);
  v15 = a7;
  v16 = DlgItem;
  if ( a7 )
  {
    v17 = WdcValidation::Ignore(a7, a3);
    if ( *((_DWORD *)v15 + 2) )
    {
      WdcSetReadOnly(a1, a3);
      goto LABEL_7;
    }
    v18 = v17 == 0;
  }
  else
  {
    v18 = 1;
  }
  EnableWindow(v16, v18);
LABEL_7:
  if ( (unsigned __int8)a2 == 1 )
  {
    AlertItem = WdcListSetup(v16, 0, 0);
    v13 = AlertItem;
    if ( AlertItem >= 0 )
    {
      AlertItem =  IAlertDataCollector::`vcall'{256,{flat}}(a4, &psa);
      v13 = AlertItem;
      if ( AlertItem >= 0 )
      {
        v31 = WdcDataCollectorNode::GetAlertItem;
        AlertItem = WdcForEachElement<unsigned short *>(psa);
        v13 = AlertItem;
        if ( AlertItem >= 0 )
          goto LABEL_29;
      }
    }
LABEL_27:
    LODWORD(v31) = AlertItem;
    goto LABEL_28;
  }
  if ( (unsigned __int8)a2 != 2 )
    goto LABEL_29;
  v19 = (WdcValidation *)SendMessageW(v16, 0x1004u, 0, 0);
  rgsabound.lLbound = 0;
  a7 = v19;
  v20 = (int)v19;
  rgsabound.cElements = (unsigned int)v19;
  v21 = SafeArrayCreate(8u, 1u, (SAFEARRAYBOUND *)rgsabounda);
  psa = v21;
  if ( !v21 )
  {
LABEL_10:
    v13 = -2147024882;
    LODWORD(v31) = -2147024882;
LABEL_28:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\dataexchange.cpp",
      "WdcExchangePropertyArray",
      0,
      L"FAILURE: 0x%08x",
      v31);
    goto LABEL_29;
  }
  AlertItem = SafeArrayAccessData(v21, (void **)&ppvData);
  v13 = AlertItem;
  if ( AlertItem < 0 )
    goto LABEL_27;
  for ( i = 0; i < v20; ++i )
  {
    memset_0(lParam, 0, 0x58u);
    psz = a8;
    lParam[0] = 5;
    lParam[1] = i;
    v34 = 1024;
    SendMessageW(v16, 0x104Bu, 0, (LPARAM)lParam);
    AlertItem = WdcDataCollectorNode::GetAlertItem(a2, lParam);
    v13 = AlertItem;
    if ( AlertItem < 0 )
      goto LABEL_27;
    v24 = ppvData;
    v25 = psz;
    v26 = (OLECHAR *)ppvData[i];
    if ( v26 )
    {
      SysFreeString(v26);
      v24[i] = 0;
    }
    v27 = SysAllocString(v25);
    if ( v25 && !v27 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      goto LABEL_10;
    }
    v24[i] = v27;
    v20 = (int)a7;
  }
  SafeArrayUnaccessData(psa);
  ppvData = 0;
  v28 =  IAlertDataCollector::`vcall'{264,{flat}}(a4, psa);
  v13 = v28;
  if ( v28 < 0 && (a2 & 0x200) != 0 )
    WdcShowErrorMessageEx(a1, v29, v28, v16, 0);
LABEL_29:
  if ( ppvData )
    SafeArrayUnaccessData(psa);
  if ( psa )
    SafeArrayDestroy(psa);
  return v13;
}

```

## disassembly

```asm
0x18005b594  mov     [rsp-8+arg_18], r9
0x18005b599  push    rbp
0x18005b59a  push    rbx
0x18005b59b  push    rsi
0x18005b59c  push    rdi
0x18005b59d  push    r12
0x18005b59f  push    r13
0x18005b5a1  push    r14
0x18005b5a3  push    r15
0x18005b5a5  lea     rbp, [rsp-7]
0x18005b5aa  sub     rsp, 98h
0x18005b5b1  xor     edi, edi
0x18005b5b3  mov     esi, r8d
0x18005b5b6  mov     r12d, edx
0x18005b5b9  mov     r13, rcx
0x18005b5bc  xor     edx, edx; Val
0x18005b5be  lea     rcx, [rbp+3Fh+lParam]; void *
0x18005b5c2  mov     r15, r9
0x18005b5c5  mov     ebx, edi
0x18005b5c7  lea     r8d, [rdi+58h]; Size
0x18005b5cb  call    memset_0
0x18005b5d0  mov     edx, esi; nIDDlgItem
0x18005b5d2  mov     qword ptr [rbp+3Fh+rgsabound.cElements], rdi
0x18005b5d9  mov     rcx, r13; hDlg
0x18005b5dc  mov     [rbp+3Fh+psa], rdi
0x18005b5e0  mov     [rbp+3Fh+ppvData], rdi
0x18005b5e4  call    cs:__imp_GetDlgItem
0x18005b5ea  mov     r14, [rbp+3Fh+arg_30]
0x18005b5ee  mov     rdi, rax
0x18005b5f1  test    r14, r14
0x18005b5f4  jz      short loc_18005B61B
0x18005b5f6  mov     edx, esi; unsigned int
0x18005b5f8  mov     rcx, r14; this
0x18005b5fb  call    ?Ignore@WdcValidation@@QEAAHI@Z; WdcValidation::Ignore(uint)
0x18005b600  cmp     [r14+8], ebx
0x18005b604  jz      short loc_18005B612
0x18005b606  mov     edx, esi; unsigned int
0x18005b608  mov     rcx, r13; HWND
0x18005b60b  call    ?WdcSetReadOnly@@YAJPEAUHWND__@@K@Z; WdcSetReadOnly(HWND__ *,ulong)
0x18005b610  jmp     short loc_18005B629
0x18005b612  xor     edx, edx
0x18005b614  test    eax, eax
0x18005b616  setz    dl
0x18005b619  jmp     short loc_18005B620
0x18005b61b  mov     edx, 1; bEnable
0x18005b620  mov     rcx, rdi; hWnd
0x18005b623  call    cs:__imp_EnableWindow
0x18005b629  movzx   ecx, r12b
0x18005b62d  sub     ecx, 1
0x18005b630  jz      loc_18005B7C7
0x18005b636  cmp     ecx, 1
0x18005b639  jnz     loc_18005B838
0x18005b63f  xor     r9d, r9d; lParam
0x18005b642  xor     r8d, r8d; wParam
0x18005b645  mov     edx, 1004h; Msg
0x18005b64a  mov     rcx, rdi; hWnd
0x18005b64d  call    cs:__imp_SendMessageW
0x18005b653  mov     ecx, 8; vt
0x18005b658  mov     [rbp+3Fh+rgsabound.lLbound], ebx
0x18005b65e  lea     r8, [rbp+3Fh+rgsabound]; rgsabound
0x18005b665  mov     [rbp+3Fh+arg_30], rax
0x18005b669  mov     r14, rax
0x18005b66c  mov     [rbp+3Fh+rgsabound.cElements], eax
0x18005b672  lea     edx, [rcx-7]; cDims
0x18005b675  call    cs:__imp_SafeArrayCreate
0x18005b67b  mov     [rbp+3Fh+psa], rax
0x18005b67f  test    rax, rax
0x18005b682  jnz     short loc_18005B694
0x18005b684  mov     edi, 8007000Eh
0x18005b689  mov     ebx, edi
0x18005b68b  mov     [rsp+0D0h+var_B0], edi
0x18005b68f  jmp     loc_18005B81B
0x18005b694  lea     rdx, [rbp+3Fh+ppvData]; ppvData
0x18005b698  mov     rcx, rax; psa
0x18005b69b  call    cs:__imp_SafeArrayAccessData
0x18005b6a1  mov     ebx, eax
0x18005b6a3  test    eax, eax
0x18005b6a5  js      loc_18005B817
0x18005b6ab  xor     esi, esi
0x18005b6ad  cmp     esi, r14d
0x18005b6b0  jge     loc_18005B77B
0x18005b6b6  xor     edx, edx; Val
0x18005b6b8  lea     rcx, [rbp+3Fh+lParam]; void *
0x18005b6bc  lea     r8d, [rdx+58h]; Size
0x18005b6c0  call    memset_0
0x18005b6c5  mov     rax, [rbp+3Fh+arg_38]
0x18005b6cc  lea     r9, [rbp+3Fh+lParam]; lParam
0x18005b6d0  xor     r8d, r8d; wParam
0x18005b6d3  mov     [rbp+3Fh+psz], rax
0x18005b6d7  mov     edx, 104Bh; Msg
0x18005b6dc  mov     [rbp+3Fh+lParam], 5
0x18005b6e3  mov     rcx, rdi; hWnd
0x18005b6e6  mov     [rbp+3Fh+lParam+4], esi
0x18005b6e9  mov     [rbp+3Fh+var_80], 400h
0x18005b6f0  call    cs:__imp_SendMessageW
0x18005b6f6  lea     rdx, [rbp+3Fh+lParam]
0x18005b6fa  mov     ecx, r12d
0x18005b6fd  call    ?GetAlertItem@WdcDataCollectorNode@@CAJW4PROPERTY_EXCHANGE@@PEAUtagLVITEMW@@@Z; WdcDataCollectorNode::GetAlertItem(PROPERTY_EXCHANGE,tagLVITEMW *)
0x18005b702  mov     ebx, eax
0x18005b704  test    eax, eax
0x18005b706  js      loc_18005B817
0x18005b70c  mov     r14, [rbp+3Fh+ppvData]
0x18005b710  mov     r15, [rbp+3Fh+psz]
0x18005b714  movsxd  rbx, esi
0x18005b717  mov     rcx, [r14+rbx*8]; bstrString
0x18005b71b  test    rcx, rcx
0x18005b71e  jz      short loc_18005B72E
0x18005b720  call    cs:__imp_SysFreeString
0x18005b726  mov     qword ptr [r14+rbx*8], 0
0x18005b72e  mov     rcx, r15; psz
0x18005b731  call    cs:__imp_SysAllocString
0x18005b737  test    r15, r15
0x18005b73a  jz      short loc_18005B741
0x18005b73c  test    rax, rax
0x18005b73f  jz      short loc_18005B750
0x18005b741  mov     [r14+rbx*8], rax
0x18005b745  mov     r14, [rbp+3Fh+arg_30]
0x18005b749  inc     esi
0x18005b74b  jmp     loc_18005B6AD
0x18005b750  mov     edi, 8007000Eh
0x18005b755  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005b75c  xor     r8d, r8d; int
0x18005b75f  mov     [rsp+0D0h+var_B0], edi
0x18005b763  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18005b76a  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18005b771  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005b776  jmp     loc_18005B689
0x18005b77b  mov     rcx, [rbp+3Fh+psa]; psa
0x18005b77f  call    cs:__imp_SafeArrayUnaccessData
0x18005b785  mov     rdx, [rbp+3Fh+psa]
0x18005b789  mov     rcx, [rbp+3Fh+arg_18]
0x18005b78d  mov     [rbp+3Fh+ppvData], 0
0x18005b795  call    ??_9IAlertDataCollector@@$BBAI@AA; [thunk]: IAlertDataCollector::`vcall'{264,{flat}}
0x18005b79a  mov     ebx, eax
0x18005b79c  test    eax, eax
0x18005b79e  jns     loc_18005B838
0x18005b7a4  bt      r12d, 9
0x18005b7a9  jnb     loc_18005B838
0x18005b7af  mov     r9, rdi; HWND
0x18005b7b2  mov     [rsp+0D0h+var_B0], 0; int
0x18005b7ba  mov     r8d, eax; int
0x18005b7bd  mov     rcx, r13; HWND
0x18005b7c0  call    ?WdcShowErrorMessageEx@@YAJPEAUHWND__@@KJ0H@Z; WdcShowErrorMessageEx(HWND__ *,ulong,long,HWND__ *,int)
0x18005b7c5  jmp     short loc_18005B838
0x18005b7c7  xor     r8d, r8d; unsigned int
0x18005b7ca  xor     edx, edx; struct tagLVCOLUMNW *
0x18005b7cc  mov     rcx, rdi; hWnd
0x18005b7cf  call    ?WdcListSetup@@YAJPEAUHWND__@@PEBUtagLVCOLUMNW@@I@Z; WdcListSetup(HWND__ *,tagLVCOLUMNW const *,uint)
0x18005b7d4  mov     ebx, eax
0x18005b7d6  test    eax, eax
0x18005b7d8  js      short loc_18005B817
0x18005b7da  lea     rdx, [rbp+3Fh+psa]
0x18005b7de  mov     rcx, r15
0x18005b7e1  call    ??_9IAlertDataCollector@@$BBAA@AA; [thunk]: IAlertDataCollector::`vcall'{256,{flat}}
0x18005b7e6  mov     ebx, eax
0x18005b7e8  test    eax, eax
0x18005b7ea  js      short loc_18005B817
0x18005b7ec  mov     rcx, [rbp+3Fh+psa]; psa
0x18005b7f0  lea     rax, ?GetAlertItem@WdcDataCollectorNode@@CAJW4PROPERTY_EXCHANGE@@PEAUtagLVITEMW@@@Z; WdcDataCollectorNode::GetAlertItem(PROPERTY_EXCHANGE,tagLVITEMW *)
0x18005b7f7  mov     r9, rdi
0x18005b7fa  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18005b7ff  mov     r8d, 2
0x18005b805  lea     rdx, ?WdcAddArrayItem@@YAJPEAU?$WDC_SAFEARRAY_CALL@PEAG@@@Z; WdcAddArrayItem(WDC_SAFEARRAY_CALL<ushort *> *)
0x18005b80c  call    ??$WdcForEachElement@PEAG@@YAJPEAUtagSAFEARRAY@@P6AJPEAU?$WDC_SAFEARRAY_CALL@PEAG@@@ZKZZ; WdcForEachElement<ushort *>(tagSAFEARRAY *,long (*)(WDC_SAFEARRAY_CALL<ushort *> *),ulong,...)
0x18005b811  mov     ebx, eax
0x18005b813  test    eax, eax
0x18005b815  jns     short loc_18005B838
0x18005b817  mov     [rsp+0D0h+var_B0], eax
0x18005b81b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005b822  xor     r8d, r8d; int
0x18005b825  lea     rdx, aWdcexchangepro_2; "WdcExchangePropertyArray"
0x18005b82c  lea     rcx, aBaseDiagnosisP_46; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18005b833  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005b838  cmp     [rbp+3Fh+ppvData], 0
0x18005b83d  jz      short loc_18005B849
0x18005b83f  mov     rcx, [rbp+3Fh+psa]; psa
0x18005b843  call    cs:__imp_SafeArrayUnaccessData
0x18005b849  mov     rcx, [rbp+3Fh+psa]; psa
0x18005b84d  test    rcx, rcx
0x18005b850  jz      short loc_18005B858
0x18005b852  call    cs:__imp_SafeArrayDestroy
0x18005b858  mov     eax, ebx
0x18005b85a  add     rsp, 98h
0x18005b861  pop     r15
0x18005b863  pop     r14
0x18005b865  pop     r13
0x18005b867  pop     r12
0x18005b869  pop     rdi
0x18005b86a  pop     rsi
0x18005b86b  pop     rbx
0x18005b86c  pop     rbp
0x18005b86d  retn
```
