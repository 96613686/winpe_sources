# WdcExchangePropertyArray<IPerformanceCounterDataCollector>(HWND__ *,PROPERTY_EXCHANGE,ulong,IPerformanceCounterDataCollector *,long (IPerformanceCounterDataCollector::*)(tagSAFEARRAY * *),long (IPerformanceCounterDataCollector::*)(tagSAFEARRAY *),WdcValidation *,ushort *,ulong,long (*)(PROPERTY_EXCHANGE,tagLVITEMW *))

- ea: `0x18005bb50`
- end: `0x18005be10`
- name: `??$WdcExchangePropertyArray@UIPerformanceCounterDataCollector@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIPerformanceCounterDataCollector@@P82@EAAJPEAPEAUtagSAFEARRAY@@@ZP82@EAAJPEAU3@@ZPEAVWdcValidation@@PEAGKP6AJ1PEAUtagLVITEMW@@@Z@Z`
- size: `704`
- prototype: `__int64(HWND, __int16, unsigned int, __int64, SAFEARRAY *psa, _QWORD *ppvData, WdcValidation *, OLECHAR *, int, ...)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18005d760`
- `0x180061a28`

## callees

- `0x18000b854`
- `0x180026490`
- `0x18003b0ac`
- `0x180054bb4`
- `0x180054e00`
- `0x180054e20`
- `0x18005bb50`
- `0x1800685ac`
- `0x180069170`
- `0x18006a034`

## import_xrefs

- `USER32!EnableWindow` at `0x18005bbdf`
- `USER32!EnableWindow` at `0x18005bbdf`
- `USER32!SendMessageW` at `0x18005bc09`
- `USER32!SendMessageW` at `0x18005bcab`
- `USER32!SendMessageW` at `0x18005bc09`
- `USER32!SendMessageW` at `0x18005bcab`
- `USER32!GetDlgItem` at `0x18005bba0`
- `USER32!GetDlgItem` at `0x18005bba0`
- `OLEAUT32!__imp_SysAllocString` at `0x18005bcd6`
- `OLEAUT32!__imp_SysAllocString` at `0x18005bcd6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bcc5`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bcc5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005bc31`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005bc31`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005bdf4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005bdf4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005bc57`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005bc57`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005bd24`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005bde5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005bd24`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005bde5`

## pseudocode

```c
__int64 WdcExchangePropertyArray<IPerformanceCounterDataCollector>(
        HWND a1,
        __int16 a2,
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
  int v20; // esi
  SAFEARRAY *v21; // rax
  HRESULT v22; // eax
  int i; // ebx
  _QWORD *v24; // r14
  OLECHAR *v25; // r15
  OLECHAR *v26; // rcx
  BSTR v27; // rax
  int v28; // eax
  unsigned int v29; // edx
  int v31[4]; // [rsp+20h] [rbp-71h]
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
    v22 = WdcListSetup(v16, 0, 0);
    v13 = v22;
    if ( v22 >= 0 )
    {
      v22 =  IAlertDataCollector::`vcall'{272,{flat}}(a4, &psa);
      v13 = v22;
      if ( v22 >= 0 )
      {
        v31[1] = 0;
        v22 = WdcForEachElement<unsigned short *>(psa);
        v13 = v22;
        if ( v22 >= 0 )
          goto LABEL_28;
      }
    }
LABEL_26:
    v31[0] = v22;
    goto LABEL_27;
  }
  if ( (unsigned __int8)a2 != 2 )
    goto LABEL_28;
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
    v31[0] = -2147024882;
LABEL_27:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\dataexchange.cpp",
      "WdcExchangePropertyArray",
      0,
      L"FAILURE: 0x%08x",
      *(_QWORD *)v31);
    goto LABEL_28;
  }
  v22 = SafeArrayAccessData(v21, (void **)&ppvData);
  v13 = v22;
  if ( v22 < 0 )
    goto LABEL_26;
  for ( i = 0; i < v20; ++i )
  {
    memset_0(lParam, 0, 0x58u);
    psz = a8;
    lParam[0] = 5;
    lParam[1] = i;
    v34 = 1024;
    SendMessageW(v16, 0x104Bu, 0, (LPARAM)lParam);
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
  v28 =  IDataCollectorSet::`vcall'{280,{flat}}(a4, psa);
  v13 = v28;
  if ( v28 < 0 && (a2 & 0x200) != 0 )
    WdcShowErrorMessageEx(a1, v29, v28, v16, 0);
LABEL_28:
  if ( ppvData )
    SafeArrayUnaccessData(psa);
  if ( psa )
    SafeArrayDestroy(psa);
  return v13;
}

```

## disassembly

```asm
0x18005bb50  mov     [rsp-8+arg_18], r9
0x18005bb55  push    rbp
0x18005bb56  push    rbx
0x18005bb57  push    rsi
0x18005bb58  push    rdi
0x18005bb59  push    r12
0x18005bb5b  push    r13
0x18005bb5d  push    r14
0x18005bb5f  push    r15
0x18005bb61  lea     rbp, [rsp-7]
0x18005bb66  sub     rsp, 98h
0x18005bb6d  xor     edi, edi
0x18005bb6f  mov     esi, r8d
0x18005bb72  mov     r13d, edx
0x18005bb75  mov     r12, rcx
0x18005bb78  xor     edx, edx; Val
0x18005bb7a  lea     rcx, [rbp+3Fh+lParam]; void *
0x18005bb7e  mov     r15, r9
0x18005bb81  mov     ebx, edi
0x18005bb83  lea     r8d, [rdi+58h]; Size
0x18005bb87  call    memset_0
0x18005bb8c  mov     edx, esi; nIDDlgItem
0x18005bb8e  mov     qword ptr [rbp+3Fh+rgsabound.cElements], rdi
0x18005bb95  mov     rcx, r12; hDlg
0x18005bb98  mov     [rbp+3Fh+psa], rdi
0x18005bb9c  mov     [rbp+3Fh+ppvData], rdi
0x18005bba0  call    cs:__imp_GetDlgItem
0x18005bba6  mov     r14, [rbp+3Fh+arg_30]
0x18005bbaa  mov     rdi, rax
0x18005bbad  test    r14, r14
0x18005bbb0  jz      short loc_18005BBD7
0x18005bbb2  mov     edx, esi; unsigned int
0x18005bbb4  mov     rcx, r14; this
0x18005bbb7  call    ?Ignore@WdcValidation@@QEAAHI@Z; WdcValidation::Ignore(uint)
0x18005bbbc  cmp     [r14+8], ebx
0x18005bbc0  jz      short loc_18005BBCE
0x18005bbc2  mov     edx, esi; unsigned int
0x18005bbc4  mov     rcx, r12; HWND
0x18005bbc7  call    ?WdcSetReadOnly@@YAJPEAUHWND__@@K@Z; WdcSetReadOnly(HWND__ *,ulong)
0x18005bbcc  jmp     short loc_18005BBE5
0x18005bbce  xor     edx, edx
0x18005bbd0  test    eax, eax
0x18005bbd2  setz    dl
0x18005bbd5  jmp     short loc_18005BBDC
0x18005bbd7  mov     edx, 1; bEnable
0x18005bbdc  mov     rcx, rdi; hWnd
0x18005bbdf  call    cs:__imp_EnableWindow
0x18005bbe5  movzx   ecx, r13b
0x18005bbe9  sub     ecx, 1
0x18005bbec  jz      loc_18005BD6C
0x18005bbf2  cmp     ecx, 1
0x18005bbf5  jnz     loc_18005BDDA
0x18005bbfb  xor     r9d, r9d; lParam
0x18005bbfe  xor     r8d, r8d; wParam
0x18005bc01  mov     edx, 1004h; Msg
0x18005bc06  mov     rcx, rdi; hWnd
0x18005bc09  call    cs:__imp_SendMessageW
0x18005bc0f  mov     ecx, 8; vt
0x18005bc14  mov     [rbp+3Fh+rgsabound.lLbound], ebx
0x18005bc1a  lea     r8, [rbp+3Fh+rgsabound]; rgsabound
0x18005bc21  mov     [rbp+3Fh+arg_30], rax
0x18005bc25  mov     rsi, rax
0x18005bc28  mov     [rbp+3Fh+rgsabound.cElements], eax
0x18005bc2e  lea     edx, [rcx-7]; cDims
0x18005bc31  call    cs:__imp_SafeArrayCreate
0x18005bc37  mov     [rbp+3Fh+psa], rax
0x18005bc3b  test    rax, rax
0x18005bc3e  jnz     short loc_18005BC50
0x18005bc40  mov     edi, 8007000Eh
0x18005bc45  mov     ebx, edi
0x18005bc47  mov     [rsp+0D0h+var_B0], edi
0x18005bc4b  jmp     loc_18005BDBD
0x18005bc50  lea     rdx, [rbp+3Fh+ppvData]; ppvData
0x18005bc54  mov     rcx, rax; psa
0x18005bc57  call    cs:__imp_SafeArrayAccessData
0x18005bc5d  mov     ebx, eax
0x18005bc5f  test    eax, eax
0x18005bc61  js      loc_18005BDB9
0x18005bc67  xor     ebx, ebx
0x18005bc69  cmp     ebx, esi
0x18005bc6b  jge     loc_18005BD20
0x18005bc71  xor     edx, edx; Val
0x18005bc73  lea     rcx, [rbp+3Fh+lParam]; void *
0x18005bc77  lea     r8d, [rdx+58h]; Size
0x18005bc7b  call    memset_0
0x18005bc80  mov     rax, [rbp+3Fh+arg_38]
0x18005bc87  lea     r9, [rbp+3Fh+lParam]; lParam
0x18005bc8b  xor     r8d, r8d; wParam
0x18005bc8e  mov     [rbp+3Fh+psz], rax
0x18005bc92  mov     edx, 104Bh; Msg
0x18005bc97  mov     [rbp+3Fh+lParam], 5
0x18005bc9e  mov     rcx, rdi; hWnd
0x18005bca1  mov     [rbp+3Fh+lParam+4], ebx
0x18005bca4  mov     [rbp+3Fh+var_80], 400h
0x18005bcab  call    cs:__imp_SendMessageW
0x18005bcb1  mov     r14, [rbp+3Fh+ppvData]
0x18005bcb5  mov     r15, [rbp+3Fh+psz]
0x18005bcb9  movsxd  rsi, ebx
0x18005bcbc  mov     rcx, [r14+rsi*8]; bstrString
0x18005bcc0  test    rcx, rcx
0x18005bcc3  jz      short loc_18005BCD3
0x18005bcc5  call    cs:__imp_SysFreeString
0x18005bccb  mov     qword ptr [r14+rsi*8], 0
0x18005bcd3  mov     rcx, r15; psz
0x18005bcd6  call    cs:__imp_SysAllocString
0x18005bcdc  test    r15, r15
0x18005bcdf  jz      short loc_18005BCE6
0x18005bce1  test    rax, rax
0x18005bce4  jz      short loc_18005BCF5
0x18005bce6  mov     [r14+rsi*8], rax
0x18005bcea  mov     rsi, [rbp+3Fh+arg_30]
0x18005bcee  inc     ebx
0x18005bcf0  jmp     loc_18005BC69
0x18005bcf5  mov     edi, 8007000Eh
0x18005bcfa  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005bd01  xor     r8d, r8d; int
0x18005bd04  mov     [rsp+0D0h+var_B0], edi
0x18005bd08  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18005bd0f  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18005bd16  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005bd1b  jmp     loc_18005BC45
0x18005bd20  mov     rcx, [rbp+3Fh+psa]; psa
0x18005bd24  call    cs:__imp_SafeArrayUnaccessData
0x18005bd2a  mov     rdx, [rbp+3Fh+psa]
0x18005bd2e  mov     rcx, [rbp+3Fh+arg_18]
0x18005bd32  mov     [rbp+3Fh+ppvData], 0
0x18005bd3a  call    ??_9IDataCollectorSet@@$BBBI@AA; [thunk]: IDataCollectorSet::`vcall'{280,{flat}}
0x18005bd3f  mov     ebx, eax
0x18005bd41  test    eax, eax
0x18005bd43  jns     loc_18005BDDA
0x18005bd49  bt      r13d, 9
0x18005bd4e  jnb     loc_18005BDDA
0x18005bd54  mov     r9, rdi; HWND
0x18005bd57  mov     [rsp+0D0h+var_B0], 0; int
0x18005bd5f  mov     r8d, eax; int
0x18005bd62  mov     rcx, r12; HWND
0x18005bd65  call    ?WdcShowErrorMessageEx@@YAJPEAUHWND__@@KJ0H@Z; WdcShowErrorMessageEx(HWND__ *,ulong,long,HWND__ *,int)
0x18005bd6a  jmp     short loc_18005BDDA
0x18005bd6c  xor     r8d, r8d; unsigned int
0x18005bd6f  xor     edx, edx; struct tagLVCOLUMNW *
0x18005bd71  mov     rcx, rdi; hWnd
0x18005bd74  call    ?WdcListSetup@@YAJPEAUHWND__@@PEBUtagLVCOLUMNW@@I@Z; WdcListSetup(HWND__ *,tagLVCOLUMNW const *,uint)
0x18005bd79  mov     ebx, eax
0x18005bd7b  test    eax, eax
0x18005bd7d  js      short loc_18005BDB9
0x18005bd7f  lea     rdx, [rbp+3Fh+psa]
0x18005bd83  mov     rcx, r15
0x18005bd86  call    ??_9IAlertDataCollector@@$BBBA@AA; [thunk]: IAlertDataCollector::`vcall'{272,{flat}}
0x18005bd8b  mov     ebx, eax
0x18005bd8d  test    eax, eax
0x18005bd8f  js      short loc_18005BDB9
0x18005bd91  mov     rcx, [rbp+3Fh+psa]; psa
0x18005bd95  lea     rdx, ?WdcAddArrayItem@@YAJPEAU?$WDC_SAFEARRAY_CALL@PEAG@@@Z; WdcAddArrayItem(WDC_SAFEARRAY_CALL<ushort *> *)
0x18005bd9c  mov     r9, rdi
0x18005bd9f  mov     qword ptr [rsp+0D0h+var_B0], 0
0x18005bda8  mov     r8d, 2
0x18005bdae  call    ??$WdcForEachElement@PEAG@@YAJPEAUtagSAFEARRAY@@P6AJPEAU?$WDC_SAFEARRAY_CALL@PEAG@@@ZKZZ; WdcForEachElement<ushort *>(tagSAFEARRAY *,long (*)(WDC_SAFEARRAY_CALL<ushort *> *),ulong,...)
0x18005bdb3  mov     ebx, eax
0x18005bdb5  test    eax, eax
0x18005bdb7  jns     short loc_18005BDDA
0x18005bdb9  mov     [rsp+0D0h+var_B0], eax
0x18005bdbd  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005bdc4  xor     r8d, r8d; int
0x18005bdc7  lea     rdx, aWdcexchangepro_2; "WdcExchangePropertyArray"
0x18005bdce  lea     rcx, aBaseDiagnosisP_46; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18005bdd5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005bdda  cmp     [rbp+3Fh+ppvData], 0
0x18005bddf  jz      short loc_18005BDEB
0x18005bde1  mov     rcx, [rbp+3Fh+psa]; psa
0x18005bde5  call    cs:__imp_SafeArrayUnaccessData
0x18005bdeb  mov     rcx, [rbp+3Fh+psa]; psa
0x18005bdef  test    rcx, rcx
0x18005bdf2  jz      short loc_18005BDFA
0x18005bdf4  call    cs:__imp_SafeArrayDestroy
0x18005bdfa  mov     eax, ebx
0x18005bdfc  add     rsp, 98h
0x18005be03  pop     r15
0x18005be05  pop     r14
0x18005be07  pop     r13
0x18005be09  pop     r12
0x18005be0b  pop     rdi
0x18005be0c  pop     rsi
0x18005be0d  pop     rbx
0x18005be0e  pop     rbp
0x18005be0f  retn
```
