# WdcExchangePropertyArray<IConfigurationDataCollector>(HWND__ *,PROPERTY_EXCHANGE,ulong,IConfigurationDataCollector *,long (IConfigurationDataCollector::*)(tagSAFEARRAY * *),long (IConfigurationDataCollector::*)(tagSAFEARRAY *),WdcValidation *,ushort *,ulong,long (*)(PROPERTY_EXCHANGE,tagLVITEMW *))

- ea: `0x18005b874`
- end: `0x18005bb48`
- name: `??$WdcExchangePropertyArray@UIConfigurationDataCollector@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIConfigurationDataCollector@@P82@EAAJPEAPEAUtagSAFEARRAY@@@ZP82@EAAJPEAU3@@ZPEAVWdcValidation@@PEAGKP6AJ1PEAUtagLVITEMW@@@Z@Z`
- size: `724`
- prototype: `__int64(HWND, __int16, unsigned int, __int64, __int64 (__fastcall *)(__int64, SAFEARRAY **), __int64 (__fastcall *)(__int64, SAFEARRAY *), WdcValidation *, OLECHAR *, int, ...)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18005d628`
- `0x1800613b4`
- `0x1800616d0`
- `0x18006187c`

## callees

- `0x18000b854`
- `0x180026490`
- `0x18003b0ac`
- `0x180054bb4`
- `0x18005b874`
- `0x1800685ac`
- `0x180069170`
- `0x18006a034`
- `0x180086010`

## import_xrefs

- `USER32!EnableWindow` at `0x18005b903`
- `USER32!EnableWindow` at `0x18005b903`
- `USER32!SendMessageW` at `0x18005b92d`
- `USER32!SendMessageW` at `0x18005b9c9`
- `USER32!SendMessageW` at `0x18005b92d`
- `USER32!SendMessageW` at `0x18005b9c9`
- `USER32!GetDlgItem` at `0x18005b8c4`
- `USER32!GetDlgItem` at `0x18005b8c4`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b9f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b9f4`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b9e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b9e3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005b94c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005b94c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005bb2c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005bb2c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005b975`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005b975`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005ba45`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005bb1a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005ba45`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005bb1a`

## pseudocode

```c
__int64 WdcExchangePropertyArray<IConfigurationDataCollector>(
        HWND a1,
        __int16 a2,
        unsigned int a3,
        __int64 a4,
        __int64 (__fastcall *a5)(__int64, SAFEARRAY **),
        __int64 (__fastcall *a6)(__int64, SAFEARRAY *),
        WdcValidation *a7,
        OLECHAR *a8,
        int a9,
        ...)
{
  unsigned int v13; // ebx
  HWND DlgItem; // rdi
  int v15; // eax
  BOOL v16; // edx
  signed int v17; // esi
  SAFEARRAY *v18; // rax
  HRESULT v19; // eax
  signed int i; // ebx
  _QWORD *v21; // r14
  OLECHAR *v22; // r15
  OLECHAR *v23; // rcx
  BSTR v24; // rax
  int v25; // eax
  unsigned int v26; // edx
  int v28[4]; // [rsp+20h] [rbp-81h]
  void *ppvData; // [rsp+30h] [rbp-71h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-69h] BYREF
  _DWORD lParam[6]; // [rsp+40h] [rbp-61h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-49h]
  int v33; // [rsp+60h] [rbp-41h]
  ULONG v35; // [rsp+120h] [rbp+7Fh]
  SAFEARRAY *psa; // [rsp+138h] [rbp+97h] BYREF
  va_list psaa; // [rsp+138h] [rbp+97h]
  va_list va1; // [rsp+140h] [rbp+9Fh] BYREF

  va_start(va1, a9);
  va_start(psaa, a9);
  psa = va_arg(va1, SAFEARRAY *);
  v13 = 0;
  memset_0(lParam, 0, 0x58u);
  rgsabound = 0;
  psa = 0;
  ppvData = 0;
  DlgItem = GetDlgItem(a1, a3);
  if ( a7 )
  {
    v15 = WdcValidation::Ignore(a7, a3);
    if ( *((_DWORD *)a7 + 2) )
    {
      WdcSetReadOnly(a1, a3);
      goto LABEL_7;
    }
    v16 = v15 == 0;
  }
  else
  {
    v16 = 1;
  }
  EnableWindow(DlgItem, v16);
LABEL_7:
  if ( (unsigned __int8)a2 == 1 )
  {
    v19 = WdcListSetup(DlgItem, 0, 0);
    v13 = v19;
    if ( v19 >= 0 )
    {
      v19 = a5(a4, (SAFEARRAY **)psaa);
      v13 = v19;
      if ( v19 >= 0 )
      {
        v28[1] = 0;
        v19 = WdcForEachElement<unsigned short *>(psa);
        v13 = v19;
        if ( v19 >= 0 )
          goto LABEL_28;
      }
    }
LABEL_26:
    v28[0] = v19;
    goto LABEL_27;
  }
  if ( (unsigned __int8)a2 != 2 )
    goto LABEL_28;
  rgsabound.lLbound = 0;
  v35 = SendMessageW(DlgItem, 0x1004u, 0, 0);
  v17 = v35;
  rgsabound.cElements = v35;
  v18 = SafeArrayCreate(8u, 1u, &rgsabound);
  psa = v18;
  if ( !v18 )
  {
LABEL_10:
    v13 = -2147024882;
    v28[0] = -2147024882;
LABEL_27:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\dataexchange.cpp",
      "WdcExchangePropertyArray",
      0,
      L"FAILURE: 0x%08x",
      *(_QWORD *)v28);
    goto LABEL_28;
  }
  v19 = SafeArrayAccessData(v18, &ppvData);
  v13 = v19;
  if ( v19 < 0 )
    goto LABEL_26;
  for ( i = 0; i < v17; ++i )
  {
    memset_0(lParam, 0, 0x58u);
    psz = a8;
    lParam[0] = 5;
    lParam[1] = i;
    v33 = 1024;
    SendMessageW(DlgItem, 0x104Bu, 0, (LPARAM)lParam);
    v21 = ppvData;
    v22 = psz;
    v23 = (OLECHAR *)*((_QWORD *)ppvData + i);
    if ( v23 )
    {
      SysFreeString(v23);
      v21[i] = 0;
    }
    v24 = SysAllocString(v22);
    if ( v22 && !v24 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      goto LABEL_10;
    }
    v21[i] = v24;
    v17 = v35;
  }
  SafeArrayUnaccessData(psa);
  ppvData = 0;
  v25 = a6(a4, psa);
  v13 = v25;
  if ( v25 < 0 && (a2 & 0x200) != 0 )
    WdcShowErrorMessageEx(a1, v26, v25, DlgItem, 0);
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
0x18005b874  mov     [rsp-8+arg_18], r9
0x18005b879  push    rbp
0x18005b87a  push    rbx
0x18005b87b  push    rsi
0x18005b87c  push    rdi
0x18005b87d  push    r12
0x18005b87f  push    r13
0x18005b881  push    r14
0x18005b883  push    r15
0x18005b885  lea     rbp, [rsp-7]
0x18005b88a  sub     rsp, 0A8h
0x18005b891  xor     edi, edi
0x18005b893  mov     esi, r8d
0x18005b896  mov     r13d, edx
0x18005b899  mov     r12, rcx
0x18005b89c  xor     edx, edx; Val
0x18005b89e  lea     rcx, [rbp+3Fh+lParam]; void *
0x18005b8a2  mov     r15, r9
0x18005b8a5  mov     ebx, edi
0x18005b8a7  lea     r8d, [rdi+58h]; Size
0x18005b8ab  call    memset_0
0x18005b8b0  mov     edx, esi; nIDDlgItem
0x18005b8b2  mov     qword ptr [rbp+3Fh+rgsabound.cElements], rdi
0x18005b8b6  mov     rcx, r12; hDlg
0x18005b8b9  mov     [rbp+3Fh+psa], rdi
0x18005b8c0  mov     [rbp+3Fh+ppvData], rdi
0x18005b8c4  call    cs:__imp_GetDlgItem
0x18005b8ca  mov     r14, [rbp+3Fh+arg_30]
0x18005b8ce  mov     rdi, rax
0x18005b8d1  test    r14, r14
0x18005b8d4  jz      short loc_18005B8FB
0x18005b8d6  mov     edx, esi; unsigned int
0x18005b8d8  mov     rcx, r14; this
0x18005b8db  call    ?Ignore@WdcValidation@@QEAAHI@Z; WdcValidation::Ignore(uint)
0x18005b8e0  cmp     [r14+8], ebx
0x18005b8e4  jz      short loc_18005B8F2
0x18005b8e6  mov     edx, esi; unsigned int
0x18005b8e8  mov     rcx, r12; HWND
0x18005b8eb  call    ?WdcSetReadOnly@@YAJPEAUHWND__@@K@Z; WdcSetReadOnly(HWND__ *,ulong)
0x18005b8f0  jmp     short loc_18005B909
0x18005b8f2  xor     edx, edx
0x18005b8f4  test    eax, eax
0x18005b8f6  setz    dl
0x18005b8f9  jmp     short loc_18005B900
0x18005b8fb  mov     edx, 1; bEnable
0x18005b900  mov     rcx, rdi; hWnd
0x18005b903  call    cs:__imp_EnableWindow
0x18005b909  movzx   ecx, r13b
0x18005b90d  sub     ecx, 1
0x18005b910  jz      loc_18005BA94
0x18005b916  cmp     ecx, 1
0x18005b919  jnz     loc_18005BB0C
0x18005b91f  xor     r9d, r9d; lParam
0x18005b922  xor     r8d, r8d; wParam
0x18005b925  mov     edx, 1004h; Msg
0x18005b92a  mov     rcx, rdi; hWnd
0x18005b92d  call    cs:__imp_SendMessageW
0x18005b933  mov     ecx, 8; vt
0x18005b938  mov     [rbp+3Fh+rgsabound.lLbound], ebx
0x18005b93b  lea     r8, [rbp+3Fh+rgsabound]; rgsabound
0x18005b93f  mov     [rbp+3Fh+arg_30], rax
0x18005b943  mov     rsi, rax
0x18005b946  mov     [rbp+3Fh+rgsabound.cElements], eax
0x18005b949  lea     edx, [rcx-7]; cDims
0x18005b94c  call    cs:__imp_SafeArrayCreate
0x18005b952  mov     [rbp+3Fh+psa], rax
0x18005b959  test    rax, rax
0x18005b95c  jnz     short loc_18005B96E
0x18005b95e  mov     edi, 8007000Eh
0x18005b963  mov     ebx, edi
0x18005b965  mov     [rsp+0E0h+var_C0], edi
0x18005b969  jmp     loc_18005BAEF
0x18005b96e  lea     rdx, [rbp+3Fh+ppvData]; ppvData
0x18005b972  mov     rcx, rax; psa
0x18005b975  call    cs:__imp_SafeArrayAccessData
0x18005b97b  mov     ebx, eax
0x18005b97d  test    eax, eax
0x18005b97f  js      loc_18005BAEB
0x18005b985  xor     ebx, ebx
0x18005b987  cmp     ebx, esi
0x18005b989  jge     loc_18005BA3E
0x18005b98f  xor     edx, edx; Val
0x18005b991  lea     rcx, [rbp+3Fh+lParam]; void *
0x18005b995  lea     r8d, [rdx+58h]; Size
0x18005b999  call    memset_0
0x18005b99e  mov     rax, [rbp+3Fh+arg_38]
0x18005b9a5  lea     r9, [rbp+3Fh+lParam]; lParam
0x18005b9a9  xor     r8d, r8d; wParam
0x18005b9ac  mov     [rbp+3Fh+psz], rax
0x18005b9b0  mov     edx, 104Bh; Msg
0x18005b9b5  mov     [rbp+3Fh+lParam], 5
0x18005b9bc  mov     rcx, rdi; hWnd
0x18005b9bf  mov     [rbp+3Fh+lParam+4], ebx
0x18005b9c2  mov     [rbp+3Fh+var_80], 400h
0x18005b9c9  call    cs:__imp_SendMessageW
0x18005b9cf  mov     r14, [rbp+3Fh+ppvData]
0x18005b9d3  mov     r15, [rbp+3Fh+psz]
0x18005b9d7  movsxd  rsi, ebx
0x18005b9da  mov     rcx, [r14+rsi*8]; bstrString
0x18005b9de  test    rcx, rcx
0x18005b9e1  jz      short loc_18005B9F1
0x18005b9e3  call    cs:__imp_SysFreeString
0x18005b9e9  mov     qword ptr [r14+rsi*8], 0
0x18005b9f1  mov     rcx, r15; psz
0x18005b9f4  call    cs:__imp_SysAllocString
0x18005b9fa  test    r15, r15
0x18005b9fd  jz      short loc_18005BA04
0x18005b9ff  test    rax, rax
0x18005ba02  jz      short loc_18005BA13
0x18005ba04  mov     [r14+rsi*8], rax
0x18005ba08  mov     rsi, [rbp+3Fh+arg_30]
0x18005ba0c  inc     ebx
0x18005ba0e  jmp     loc_18005B987
0x18005ba13  mov     edi, 8007000Eh
0x18005ba18  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005ba1f  xor     r8d, r8d; int
0x18005ba22  mov     [rsp+0E0h+var_C0], edi
0x18005ba26  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18005ba2d  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18005ba34  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005ba39  jmp     loc_18005B963
0x18005ba3e  mov     rcx, [rbp+3Fh+psa]; psa
0x18005ba45  call    cs:__imp_SafeArrayUnaccessData
0x18005ba4b  mov     rdx, [rbp+3Fh+psa]
0x18005ba52  mov     rcx, [rbp+3Fh+arg_18]
0x18005ba56  mov     rax, [rbp+3Fh+arg_28]
0x18005ba5a  mov     [rbp+3Fh+ppvData], 0
0x18005ba62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba67  mov     ebx, eax
0x18005ba69  test    eax, eax
0x18005ba6b  jns     loc_18005BB0C
0x18005ba71  bt      r13d, 9
0x18005ba76  jnb     loc_18005BB0C
0x18005ba7c  mov     r9, rdi; HWND
0x18005ba7f  mov     [rsp+0E0h+var_C0], 0; int
0x18005ba87  mov     r8d, eax; int
0x18005ba8a  mov     rcx, r12; HWND
0x18005ba8d  call    ?WdcShowErrorMessageEx@@YAJPEAUHWND__@@KJ0H@Z; WdcShowErrorMessageEx(HWND__ *,ulong,long,HWND__ *,int)
0x18005ba92  jmp     short loc_18005BB0C
0x18005ba94  xor     r8d, r8d; unsigned int
0x18005ba97  xor     edx, edx; struct tagLVCOLUMNW *
0x18005ba99  mov     rcx, rdi; hWnd
0x18005ba9c  call    ?WdcListSetup@@YAJPEAUHWND__@@PEBUtagLVCOLUMNW@@I@Z; WdcListSetup(HWND__ *,tagLVCOLUMNW const *,uint)
0x18005baa1  mov     ebx, eax
0x18005baa3  test    eax, eax
0x18005baa5  js      short loc_18005BAEB
0x18005baa7  mov     rax, [rbp+3Fh+arg_20]
0x18005baab  lea     rdx, [rbp+3Fh+psa]
0x18005bab2  mov     rcx, r15
0x18005bab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005baba  mov     ebx, eax
0x18005babc  test    eax, eax
0x18005babe  js      short loc_18005BAEB
0x18005bac0  mov     rcx, [rbp+3Fh+psa]; psa
0x18005bac7  lea     rdx, ?WdcAddArrayItem@@YAJPEAU?$WDC_SAFEARRAY_CALL@PEAG@@@Z; WdcAddArrayItem(WDC_SAFEARRAY_CALL<ushort *> *)
0x18005bace  mov     r9, rdi
0x18005bad1  mov     qword ptr [rsp+0E0h+var_C0], 0
0x18005bada  mov     r8d, 2
0x18005bae0  call    ??$WdcForEachElement@PEAG@@YAJPEAUtagSAFEARRAY@@P6AJPEAU?$WDC_SAFEARRAY_CALL@PEAG@@@ZKZZ; WdcForEachElement<ushort *>(tagSAFEARRAY *,long (*)(WDC_SAFEARRAY_CALL<ushort *> *),ulong,...)
0x18005bae5  mov     ebx, eax
0x18005bae7  test    eax, eax
0x18005bae9  jns     short loc_18005BB0C
0x18005baeb  mov     [rsp+0E0h+var_C0], eax
0x18005baef  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005baf6  xor     r8d, r8d; int
0x18005baf9  lea     rdx, aWdcexchangepro_2; "WdcExchangePropertyArray"
0x18005bb00  lea     rcx, aBaseDiagnosisP_46; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18005bb07  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005bb0c  cmp     [rbp+3Fh+ppvData], 0
0x18005bb11  jz      short loc_18005BB20
0x18005bb13  mov     rcx, [rbp+3Fh+psa]; psa
0x18005bb1a  call    cs:__imp_SafeArrayUnaccessData
0x18005bb20  mov     rcx, [rbp+3Fh+psa]; psa
0x18005bb27  test    rcx, rcx
0x18005bb2a  jz      short loc_18005BB32
0x18005bb2c  call    cs:__imp_SafeArrayDestroy
0x18005bb32  mov     eax, ebx
0x18005bb34  add     rsp, 0A8h
0x18005bb3b  pop     r15
0x18005bb3d  pop     r14
0x18005bb3f  pop     r13
0x18005bb41  pop     r12
0x18005bb43  pop     rdi
0x18005bb44  pop     rsi
0x18005bb45  pop     rbx
0x18005bb46  pop     rbp
0x18005bb47  retn
```
