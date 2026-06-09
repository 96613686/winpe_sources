# WdcExchangePropertyArray<IDataCollectorSet>(HWND__ *,PROPERTY_EXCHANGE,ulong,IDataCollectorSet *,long (IDataCollectorSet::*)(tagSAFEARRAY * *),long (IDataCollectorSet::*)(tagSAFEARRAY *),WdcValidation *,ushort *,ulong,long (*)(PROPERTY_EXCHANGE,tagLVITEMW *))

- ea: `0x180054320`
- end: `0x1800545de`
- name: `??$WdcExchangePropertyArray@UIDataCollectorSet@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIDataCollectorSet@@P82@EAAJPEAPEAUtagSAFEARRAY@@@ZP82@EAAJPEAU3@@ZPEAVWdcValidation@@PEAGKP6AJ1PEAUtagLVITEMW@@@Z@Z`
- size: `702`
- prototype: `__int64(HWND, __int16, __int64, __int64, SAFEARRAY *psa, OLECHAR *ppvData, WdcValidation *, OLECHAR *, int, ...)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800564a8`

## callees

- `0x18000b854`
- `0x180026490`
- `0x18003b0ac`
- `0x18004d2a0`
- `0x18004d2b8`
- `0x180054320`
- `0x180054bb4`
- `0x1800685ac`
- `0x180069170`
- `0x18006a034`

## import_xrefs

- `USER32!EnableWindow` at `0x1800543b8`
- `USER32!EnableWindow` at `0x1800543b8`
- `USER32!SendMessageW` at `0x1800543e2`
- `USER32!SendMessageW` at `0x180054486`
- `USER32!SendMessageW` at `0x1800543e2`
- `USER32!SendMessageW` at `0x180054486`
- `USER32!GetDlgItem` at `0x180054372`
- `USER32!GetDlgItem` at `0x180054372`
- `OLEAUT32!__imp_SysAllocString` at `0x1800544b1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800544b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800544a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800544a0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005440b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005440b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800545c2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800545c2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180054431`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180054431`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180054502`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800545b3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180054502`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800545b3`

## pseudocode

```c
__int64 WdcExchangePropertyArray<IDataCollectorSet>(
        HWND a1,
        __int16 a2,
        __int64 a3,
        __int64 a4,
        SAFEARRAY *psa,
        OLECHAR *ppvData,
        WdcValidation *a7,
        OLECHAR *a8,
        int a9,
        ...)
{
  OLECHAR *v9; // r15
  unsigned int v13; // ebx
  HWND DlgItem; // rax
  WdcValidation *v15; // rsi
  HWND v16; // rdi
  int v17; // eax
  BOOL v18; // edx
  WdcValidation *v19; // rax
  int v20; // esi
  SAFEARRAY *v21; // rax
  HRESULT v22; // eax
  int i; // ebx
  OLECHAR *v24; // r14
  OLECHAR *v25; // rcx
  BSTR v26; // rax
  int v27; // eax
  unsigned int v28; // edx
  int v30[4]; // [rsp+20h] [rbp-71h]
  _DWORD lParam[6]; // [rsp+30h] [rbp-61h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-49h]
  int v33; // [rsp+50h] [rbp-41h]
  SAFEARRAYBOUND rgsabound; // [rsp+128h] [rbp+97h] BYREF
  va_list rgsabounda; // [rsp+128h] [rbp+97h]
  va_list va1; // [rsp+130h] [rbp+9Fh] BYREF

  va_start(va1, a9);
  va_start(rgsabounda, a9);
  rgsabound = va_arg(va1, SAFEARRAYBOUND);
  v9 = 0;
  v13 = 0;
  memset_0(lParam, 0, 0x58u);
  rgsabound = 0;
  psa = 0;
  ppvData = 0;
  DlgItem = GetDlgItem(a1, 2002);
  v15 = a7;
  v16 = DlgItem;
  if ( a7 )
  {
    v17 = WdcValidation::Ignore(a7, 0x7D2u);
    if ( *((_DWORD *)v15 + 2) )
    {
      WdcSetReadOnly(a1, 0x7D2u);
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
      v22 =  IDataCollectorSet::`vcall'{128,{flat}}(a4, &psa);
      v13 = v22;
      if ( v22 >= 0 )
      {
        v30[1] = 0;
        v22 = WdcForEachElement<unsigned short *>(psa);
        v13 = v22;
        if ( v22 >= 0 )
          goto LABEL_28;
      }
    }
LABEL_26:
    v30[0] = v22;
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
    v30[0] = -2147024882;
LABEL_27:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\dataexchange.cpp",
      "WdcExchangePropertyArray",
      0,
      L"FAILURE: 0x%08x",
      *(_QWORD *)v30);
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
    v33 = 1024;
    SendMessageW(v16, 0x104Bu, 0, (LPARAM)lParam);
    v24 = ppvData;
    v9 = psz;
    v25 = *(OLECHAR **)&ppvData[4 * i];
    if ( v25 )
    {
      SysFreeString(v25);
      *(_QWORD *)&v24[4 * i] = 0;
    }
    v26 = SysAllocString(v9);
    if ( v9 )
    {
      v9 = 0;
      if ( !v26 )
      {
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
          "WdcAssignString",
          0,
          L"FAILURE: 0x%08x",
          -2147024882);
        goto LABEL_10;
      }
    }
    *(_QWORD *)&v24[4 * i] = v26;
    v20 = (int)a7;
  }
  SafeArrayUnaccessData(psa);
  ppvData = v9;
  v27 =  IDataCollectorSet::`vcall'{136,{flat}}(a4, psa);
  v13 = v27;
  if ( v27 < 0 && (a2 & 0x200) != 0 )
    WdcShowErrorMessageEx(a1, v28, v27, v16, (int)v9);
LABEL_28:
  if ( ppvData != v9 )
    SafeArrayUnaccessData(psa);
  if ( psa )
    SafeArrayDestroy(psa);
  return v13;
}

```

## disassembly

```asm
0x180054320  mov     [rsp-8+arg_18], r9
0x180054325  push    rbp
0x180054326  push    rbx
0x180054327  push    rsi
0x180054328  push    rdi
0x180054329  push    r12
0x18005432b  push    r13
0x18005432d  push    r14
0x18005432f  push    r15
0x180054331  lea     rbp, [rsp-7]
0x180054336  sub     rsp, 98h
0x18005433d  xor     r15d, r15d
0x180054340  mov     r13d, edx
0x180054343  mov     r12, rcx
0x180054346  xor     edx, edx; Val
0x180054348  lea     rcx, [rbp+3Fh+lParam]; void *
0x18005434c  mov     r14, r9
0x18005434f  mov     ebx, r15d
0x180054352  lea     r8d, [r15+58h]; Size
0x180054356  call    memset_0
0x18005435b  mov     edx, 7D2h; nIDDlgItem
0x180054360  mov     qword ptr [rbp+3Fh+rgsabound.cElements], r15
0x180054367  mov     rcx, r12; hDlg
0x18005436a  mov     [rbp+3Fh+psa], r15
0x18005436e  mov     [rbp+3Fh+ppvData], r15
0x180054372  call    cs:__imp_GetDlgItem
0x180054378  mov     rsi, [rbp+3Fh+arg_30]
0x18005437c  mov     rdi, rax
0x18005437f  test    rsi, rsi
0x180054382  jz      short loc_1800543B0
0x180054384  mov     edx, 7D2h; unsigned int
0x180054389  mov     rcx, rsi; this
0x18005438c  call    ?Ignore@WdcValidation@@QEAAHI@Z; WdcValidation::Ignore(uint)
0x180054391  cmp     [rsi+8], r15d
0x180054395  jz      short loc_1800543A6
0x180054397  mov     edx, 7D2h; unsigned int
0x18005439c  mov     rcx, r12; HWND
0x18005439f  call    ?WdcSetReadOnly@@YAJPEAUHWND__@@K@Z; WdcSetReadOnly(HWND__ *,ulong)
0x1800543a4  jmp     short loc_1800543BE
0x1800543a6  test    eax, eax
0x1800543a8  mov     edx, r15d
0x1800543ab  setz    dl
0x1800543ae  jmp     short loc_1800543B5
0x1800543b0  mov     edx, 1; bEnable
0x1800543b5  mov     rcx, rdi; hWnd
0x1800543b8  call    cs:__imp_EnableWindow
0x1800543be  movzx   ecx, r13b
0x1800543c2  sub     ecx, 1
0x1800543c5  jz      loc_18005453F
0x1800543cb  cmp     ecx, 1
0x1800543ce  jnz     loc_1800545A9
0x1800543d4  xor     r9d, r9d; lParam
0x1800543d7  xor     r8d, r8d; wParam
0x1800543da  mov     edx, 1004h; Msg
0x1800543df  mov     rcx, rdi; hWnd
0x1800543e2  call    cs:__imp_SendMessageW
0x1800543e8  mov     ecx, 8; vt
0x1800543ed  mov     [rbp+3Fh+rgsabound.lLbound], r15d
0x1800543f4  lea     r8, [rbp+3Fh+rgsabound]; rgsabound
0x1800543fb  mov     [rbp+3Fh+arg_30], rax
0x1800543ff  mov     rsi, rax
0x180054402  mov     [rbp+3Fh+rgsabound.cElements], eax
0x180054408  lea     edx, [rcx-7]; cDims
0x18005440b  call    cs:__imp_SafeArrayCreate
0x180054411  mov     [rbp+3Fh+psa], rax
0x180054415  test    rax, rax
0x180054418  jnz     short loc_18005442A
0x18005441a  mov     edi, 8007000Eh
0x18005441f  mov     ebx, edi
0x180054421  mov     [rsp+0D0h+var_B0], edi
0x180054425  jmp     loc_18005458C
0x18005442a  lea     rdx, [rbp+3Fh+ppvData]; ppvData
0x18005442e  mov     rcx, rax; psa
0x180054431  call    cs:__imp_SafeArrayAccessData
0x180054437  mov     ebx, eax
0x180054439  test    eax, eax
0x18005443b  js      loc_180054588
0x180054441  mov     ebx, r15d
0x180054444  cmp     ebx, esi
0x180054446  jge     loc_1800544FE
0x18005444c  xor     edx, edx; Val
0x18005444e  lea     rcx, [rbp+3Fh+lParam]; void *
0x180054452  lea     r8d, [rdx+58h]; Size
0x180054456  call    memset_0
0x18005445b  mov     rax, [rbp+3Fh+arg_38]
0x180054462  lea     r9, [rbp+3Fh+lParam]; lParam
0x180054466  xor     r8d, r8d; wParam
0x180054469  mov     [rbp+3Fh+psz], rax
0x18005446d  mov     edx, 104Bh; Msg
0x180054472  mov     [rbp+3Fh+lParam], 5
0x180054479  mov     rcx, rdi; hWnd
0x18005447c  mov     [rbp+3Fh+lParam+4], ebx
0x18005447f  mov     [rbp+3Fh+var_80], 400h
0x180054486  call    cs:__imp_SendMessageW
0x18005448c  mov     r14, [rbp+3Fh+ppvData]
0x180054490  mov     r15, [rbp+3Fh+psz]
0x180054494  movsxd  rsi, ebx
0x180054497  mov     rcx, [r14+rsi*8]; bstrString
0x18005449b  test    rcx, rcx
0x18005449e  jz      short loc_1800544AE
0x1800544a0  call    cs:__imp_SysFreeString
0x1800544a6  mov     qword ptr [r14+rsi*8], 0
0x1800544ae  mov     rcx, r15; psz
0x1800544b1  call    cs:__imp_SysAllocString
0x1800544b7  test    r15, r15
0x1800544ba  jz      short loc_1800544EF
0x1800544bc  xor     r15d, r15d
0x1800544bf  test    rax, rax
0x1800544c2  jnz     short loc_1800544EF
0x1800544c4  mov     edi, 8007000Eh
0x1800544c9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800544d0  xor     r8d, r8d; int
0x1800544d3  mov     [rsp+0D0h+var_B0], edi
0x1800544d7  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x1800544de  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x1800544e5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800544ea  jmp     loc_18005441F
0x1800544ef  mov     [r14+rsi*8], rax
0x1800544f3  mov     rsi, [rbp+3Fh+arg_30]
0x1800544f7  inc     ebx
0x1800544f9  jmp     loc_180054444
0x1800544fe  mov     rcx, [rbp+3Fh+psa]; psa
0x180054502  call    cs:__imp_SafeArrayUnaccessData
0x180054508  mov     rdx, [rbp+3Fh+psa]
0x18005450c  mov     rcx, [rbp+3Fh+arg_18]
0x180054510  mov     [rbp+3Fh+ppvData], r15
0x180054514  call    ??_9IDataCollectorSet@@$BII@AA; [thunk]: IDataCollectorSet::`vcall'{136,{flat}}
0x180054519  mov     ebx, eax
0x18005451b  test    eax, eax
0x18005451d  jns     loc_1800545A9
0x180054523  bt      r13d, 9
0x180054528  jnb     short loc_1800545A9
0x18005452a  mov     r9, rdi; HWND
0x18005452d  mov     [rsp+0D0h+var_B0], r15d; int
0x180054532  mov     r8d, eax; int
0x180054535  mov     rcx, r12; HWND
0x180054538  call    ?WdcShowErrorMessageEx@@YAJPEAUHWND__@@KJ0H@Z; WdcShowErrorMessageEx(HWND__ *,ulong,long,HWND__ *,int)
0x18005453d  jmp     short loc_1800545A9
0x18005453f  xor     r8d, r8d; unsigned int
0x180054542  xor     edx, edx; struct tagLVCOLUMNW *
0x180054544  mov     rcx, rdi; hWnd
0x180054547  call    ?WdcListSetup@@YAJPEAUHWND__@@PEBUtagLVCOLUMNW@@I@Z; WdcListSetup(HWND__ *,tagLVCOLUMNW const *,uint)
0x18005454c  mov     ebx, eax
0x18005454e  test    eax, eax
0x180054550  js      short loc_180054588
0x180054552  lea     rdx, [rbp+3Fh+psa]
0x180054556  mov     rcx, r14
0x180054559  call    ??_9IDataCollectorSet@@$BIA@AA; [thunk]: IDataCollectorSet::`vcall'{128,{flat}}
0x18005455e  mov     ebx, eax
0x180054560  test    eax, eax
0x180054562  js      short loc_180054588
0x180054564  mov     rcx, [rbp+3Fh+psa]; psa
0x180054568  lea     rdx, ?WdcAddArrayItem@@YAJPEAU?$WDC_SAFEARRAY_CALL@PEAG@@@Z; WdcAddArrayItem(WDC_SAFEARRAY_CALL<ushort *> *)
0x18005456f  mov     r9, rdi
0x180054572  mov     qword ptr [rsp+0D0h+var_B0], r15
0x180054577  mov     r8d, 2
0x18005457d  call    ??$WdcForEachElement@PEAG@@YAJPEAUtagSAFEARRAY@@P6AJPEAU?$WDC_SAFEARRAY_CALL@PEAG@@@ZKZZ; WdcForEachElement<ushort *>(tagSAFEARRAY *,long (*)(WDC_SAFEARRAY_CALL<ushort *> *),ulong,...)
0x180054582  mov     ebx, eax
0x180054584  test    eax, eax
0x180054586  jns     short loc_1800545A9
0x180054588  mov     [rsp+0D0h+var_B0], eax
0x18005458c  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180054593  xor     r8d, r8d; int
0x180054596  lea     rdx, aWdcexchangepro_2; "WdcExchangePropertyArray"
0x18005459d  lea     rcx, aBaseDiagnosisP_46; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x1800545a4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800545a9  cmp     [rbp+3Fh+ppvData], r15
0x1800545ad  jz      short loc_1800545B9
0x1800545af  mov     rcx, [rbp+3Fh+psa]; psa
0x1800545b3  call    cs:__imp_SafeArrayUnaccessData
0x1800545b9  mov     rcx, [rbp+3Fh+psa]; psa
0x1800545bd  test    rcx, rcx
0x1800545c0  jz      short loc_1800545C8
0x1800545c2  call    cs:__imp_SafeArrayDestroy
0x1800545c8  mov     eax, ebx
0x1800545ca  add     rsp, 98h
0x1800545d1  pop     r15
0x1800545d3  pop     r14
0x1800545d5  pop     r13
0x1800545d7  pop     r12
0x1800545d9  pop     rdi
0x1800545da  pop     rsi
0x1800545db  pop     rbx
0x1800545dc  pop     rbp
0x1800545dd  retn
```
