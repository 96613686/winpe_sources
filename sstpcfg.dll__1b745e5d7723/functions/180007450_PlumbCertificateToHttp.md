# PlumbCertificateToHttp

- ea: `0x180007450`
- end: `0x180008635`
- name: `PlumbCertificateToHttp`
- size: `4581`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002518`

## callees

- `0x180003510`
- `0x180003820`
- `0x180003e10`
- `0x180004000`
- `0x1800044a0`
- `0x180004c30`
- `0x180004f10`
- `0x180005370`
- `0x180006b6c`
- `0x180007450`
- `0x180008968`
- `0x180008be4`
- `0x180009550`
- `0x180009b34`
- `0x180009ee4`
- `0x18000a014`
- `0x18000a044`
- `0x18000a178`
- `0x18000a414`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007712`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000772f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000798f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007712`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000772f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000798f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007720`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000773d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000799e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007720`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000773d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000799e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a94`
- `CRYPT32!CertFreeCertificateContext` at `0x1800076dc`
- `CRYPT32!CertFreeCertificateContext` at `0x1800076ea`
- `CRYPT32!CertFreeCertificateContext` at `0x1800076f9`
- `CRYPT32!CertFreeCertificateContext` at `0x180007707`
- `CRYPT32!CertFreeCertificateContext` at `0x1800076dc`
- `CRYPT32!CertFreeCertificateContext` at `0x1800076ea`
- `CRYPT32!CertFreeCertificateContext` at `0x1800076f9`
- `CRYPT32!CertFreeCertificateContext` at `0x180007707`
- `rtutils!RouterLogEventStringW` at `0x180008566`
- `rtutils!RouterLogEventStringW` at `0x180008566`
- `rtutils!RouterLogEventW` at `0x1800082c7`
- `rtutils!RouterLogEventW` at `0x1800082c7`

## string_xrefs

- `0x180007629`: `Hash parameters configured are invalid. Bailing out with error: %d.`
- `0x1800085f1`: `Hash parameters configured are invalid. Bailing out with error: %d.`
- `0x180007818`: `Remove Certificate Status: %d.`
- `0x18000789a`: `Attempting removal of certificates bound to port: %d.`
- `0x180007d79`: `Admin has configured the Hash, tring to use them`
- `0x180008298`: `Unable to find certificates corresponds to configuration`
- `0x180007e09`: `Found certificate correspond to the configuration`
- `0x180007ebd`: `Found certificates corresponds to configuration, %ws, %ws`
- `0x180007f70`: `Unable to use the configured certificate, bail out`
- `0x1800076a5`: `PlumbCertificateToHttp completed with status: %d`

## pseudocode

```c
__int64 __fastcall PlumbCertificateToHttp(__int64 a1, char *a2, HKEY a3, __int64 a4)
{
  int v6; // ecx
  char v7; // al
  unsigned int v8; // r13d
  bool v9; // zf
  bool v10; // r12
  unsigned __int8 v11; // r15
  int v12; // edx
  unsigned int CryptoBindingInfo; // eax
  __int64 v14; // r8
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  __int64 v19; // rdx
  const wchar_t *v20; // r8
  void *v21; // r13
  const CERT_CONTEXT *v22; // r14
  const CERT_CONTEXT *v23; // r15
  HANDLE v24; // rax
  void *v25; // rdi
  HANDLE v26; // rax
  _QWORD *v28; // rcx
  _BYTE *v29; // rcx
  int CertificateBindingFromAddress; // eax
  __int64 v31; // rcx
  __int64 v32; // r15
  __int64 v33; // r14
  unsigned int v34; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v36; // eax
  __int64 v37; // rdx
  const wchar_t *v38; // r8
  HANDLE v39; // rax
  __int64 v40; // rcx
  LPVOID v41; // r15
  unsigned int CertificateFromSslInfo; // eax
  unsigned int v43; // eax
  unsigned int CertificateFromHash; // eax
  int v45; // r8d
  _QWORD *v46; // rcx
  const wchar_t *v47; // rbx
  PCCERT_CONTEXT v48; // r12
  __int64 v49; // rcx
  const wchar_t *v50; // rax
  const wchar_t *v51; // r9
  const wchar_t *v52; // r9
  __int64 v53; // rdx
  const wchar_t *v54; // r8
  __int64 v55; // rdx
  unsigned __int16 v56; // r14
  __int64 v57; // rdx
  PCCERT_CONTEXT v58; // r14
  PCCERT_CONTEXT v59; // r12
  const wchar_t *v60; // rbx
  const wchar_t *v61; // rax
  const wchar_t *v62; // r9
  const wchar_t *v63; // r9
  unsigned int SslCertificateToConfigure; // eax
  __int64 v65; // rdx
  __int64 v66; // r8
  PCCERT_CONTEXT v67; // r15
  unsigned int v68; // ebx
  unsigned int v69; // eax
  __int64 v70; // r8
  const wchar_t *v71; // rdx
  DWORD dwErrorCode; // eax
  __int64 v73; // rdx
  __int64 v74; // r8
  _BYTE v75[8]; // [rsp+50h] [rbp-B0h] BYREF
  PCCERT_CONTEXT v76; // [rsp+58h] [rbp-A8h]
  PCCERT_CONTEXT v77; // [rsp+60h] [rbp-A0h] BYREF
  char v78; // [rsp+68h] [rbp-98h] BYREF
  char v79; // [rsp+69h] [rbp-97h] BYREF
  _BYTE v80[2]; // [rsp+6Ah] [rbp-96h] BYREF
  __int16 v81; // [rsp+6Ch] [rbp-94h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  ULONG v83; // [rsp+78h] [rbp-88h] BYREF
  ULONG v84; // [rsp+7Ch] [rbp-84h] BYREF
  int v85; // [rsp+80h] [rbp-80h]
  PCCERT_CONTEXT v86; // [rsp+88h] [rbp-78h] BYREF
  int v87; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v88; // [rsp+98h] [rbp-68h] BYREF
  __int64 v89; // [rsp+A0h] [rbp-60h]
  __int64 v90; // [rsp+A8h] [rbp-58h]
  PCCERT_CONTEXT pCertContext; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v92; // [rsp+B8h] [rbp-48h]
  __int64 v93; // [rsp+C0h] [rbp-40h]
  HKEY hKey; // [rsp+C8h] [rbp-38h]
  __int128 v95; // [rsp+D0h] [rbp-30h] BYREF
  int v96; // [rsp+E0h] [rbp-20h]
  _OWORD v97[2]; // [rsp+E8h] [rbp-18h] BYREF
  int v98; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v99[2044]; // [rsp+114h] [rbp+14h] BYREF

  hKey = a3;
  v92 = a1;
  v75[0] = 0;
  v77 = 0;
  v86 = 0;
  pCertContext = 0;
  v96 = 0;
  v76 = 0;
  v87 = 0;
  v95 = 0;
  v88 = 0;
  memset(v97, 0, sizeof(v97));
  lpMem = 0;
  v84 = 0;
  v83 = 0;
  v98 = 0;
  v93 = a4;
  v78 = 1;
  v89 = 0x458BCD49BA195980LL;
  v90 = 0x75CDADE04EC8239ELL;
  memset_0(v99, 0, sizeof(v99));
  LOWORD(v6) = 443;
  v85 = 443;
  if ( !*(_WORD *)(a1 + 2) )
  {
    if ( *(_BYTE *)a1 )
      *(_WORD *)(a1 + 2) = 443;
    else
      *(_WORD *)(a1 + 2) = 80;
  }
  if ( *((_WORD *)a2 + 1) )
  {
    v6 = *((unsigned __int16 *)a2 + 1);
    goto LABEL_10;
  }
  if ( !*a2 )
  {
    *((_WORD *)a2 + 1) = 80;
    v6 = 80;
LABEL_10:
    v85 = v6;
    goto LABEL_11;
  }
  *((_WORD *)a2 + 1) = 443;
LABEL_11:
  v7 = *a2;
  v8 = *(unsigned __int16 *)(a1 + 2);
  v9 = *a2 == 0;
  v81 = *(_WORD *)(a1 + 2);
  v10 = !v9;
  if ( !*(_BYTE *)a1 )
    goto LABEL_16;
  if ( !v7 )
  {
    v11 = 1;
    goto LABEL_17;
  }
  if ( (_WORD)v8 == (_WORD)v6 )
  {
LABEL_16:
    v11 = 0;
    goto LABEL_17;
  }
  v11 = 1;
  v10 = 1;
LABEL_17:
  GetCryptoBindingSupportedAlgoInfo(0, v75);
  LOBYTE(v12) = v75[0];
  CryptoBindingInfo = GetCryptoBindingInfo(0, v12, (unsigned int)&v78, 0, (__int64)&v87, (__int64)&v95, (__int64)v97);
  v15 = CryptoBindingInfo;
  if ( CryptoBindingInfo || v87 == 1 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, v14, CryptoBindingInfo);
      v16 = WPP_GLOBAL_Control;
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v98) = 0;
      FormatRRASErrorString(&v98, L"Hash parameters configured are invalid. Bailing out with error: %d.", v15);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v98);
      v16 = WPP_GLOBAL_Control;
    }
    if ( !v15 )
      v15 = 87;
    goto LABEL_30;
  }
  if ( v87 == 2 && !*a2 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, v14, 0);
      v16 = WPP_GLOBAL_Control;
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_30;
    v17 = 0;
    v18 = L"Hash parameters configured are invalid. Bailing out with error: %d.";
    goto LABEL_27;
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, v14, v10);
      v28 = WPP_GLOBAL_Control;
    }
    if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 0x40) != 0 && *((_BYTE *)v28 + 25) >= 3u )
      WPP_SF_d(v28[2], 105, v14, v11);
  }
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
  {
    LOWORD(v98) = 0;
    FormatRRASErrorString(&v98, L"Check for Certificate Status: %d.", v10);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      &v98);
    if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
    {
      LOWORD(v98) = 0;
      FormatRRASErrorString(&v98, L"Remove Certificate Status: %d.", v11);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        *((_QWORD *)&xmmword_1800146E0 + 1),
        &v98);
    }
  }
  v29 = (_BYTE *)v92;
  *(_WORD *)(v92 + 2) = *((_WORD *)a2 + 1);
  *v29 = *a2;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, v14, v8);
    }
    if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
    {
      LOWORD(v98) = 0;
      FormatRRASErrorString(&v98, L"Attempting removal of certificates bound to port: %d.", v8);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        *((_QWORD *)&xmmword_1800146E0 + 1),
        &v98);
    }
    CertificateBindingFromAddress = GetCertificateBindingFromAddress(2, v8, &v88, &v84);
    v32 = v90;
    v33 = v89;
    if ( !CertificateBindingFromAddress && v88 && *((_QWORD *)v88 + 3) == v89 && *((_QWORD *)v88 + 4) == v90 )
    {
      LOBYTE(v31) = 1;
      v34 = UnbindSslCertificate(v31, v88, v84);
      v15 = v34;
      if ( v34 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, v14, v34);
          v16 = WPP_GLOBAL_Control;
        }
        if ( !*((_QWORD *)&xmmword_1800146E0 + 1) )
          goto LABEL_30;
        LOWORD(v98) = 0;
        FormatRRASErrorString(&v98, L"UnbindSslCertificate for IPv4 returned: %d.", v15);
        v19 = *((_QWORD *)&xmmword_1800146E0 + 1);
        goto LABEL_28;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v88);
      v88 = 0;
    }
    if ( !(unsigned int)GetCertificateBindingFromAddress(23, v8, &lpMem, &v83) )
    {
      v21 = lpMem;
      if ( lpMem )
      {
        if ( *((_QWORD *)lpMem + 3) == v33 && *((_QWORD *)lpMem + 4) == v32 )
        {
          v36 = UnbindSslCertificate(0, lpMem, v83);
          v15 = v36;
          if ( v36 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, v14, v36);
              v16 = WPP_GLOBAL_Control;
            }
            if ( !*((_QWORD *)&xmmword_1800146E0 + 1) )
              goto LABEL_31;
            LOWORD(v98) = 0;
            FormatRRASErrorString(&v98, L"UnbindSslCertificate for IPv6 returned: %d.", v15);
            v37 = *((_QWORD *)&xmmword_1800146E0 + 1);
            v38 = (const wchar_t *)&v98;
            goto LABEL_93;
          }
          v39 = GetProcessHeap();
          HeapFree(v39, 0, v21);
          lpMem = 0;
        }
      }
    }
    LOWORD(v8) = v81;
    v15 = 0;
  }
  if ( !v10 )
  {
    v21 = lpMem;
    goto LABEL_293;
  }
  v15 = GetCertificateBindingFromAddress(2, v8, &v88, &v84);
  if ( v15 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, v14, (unsigned __int16)v8);
      v16 = WPP_GLOBAL_Control;
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_30;
    v17 = (unsigned __int16)v8;
    v18 = L"Unable to get cert binding for V4 port: %d.";
    goto LABEL_27;
  }
  v41 = v88;
  if ( v88 )
  {
    LOBYTE(v40) = 1;
    CertificateFromSslInfo = GetCertificateFromSslInfo(v40, v88, &v77);
    v15 = CertificateFromSslInfo;
    if ( CertificateFromSslInfo == -2146885628 )
    {
      v15 = UnbindSslCertificate(0, v41, v84);
      if ( v15 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110);
          v16 = WPP_GLOBAL_Control;
        }
        v19 = *((_QWORD *)&xmmword_1800146E0 + 1);
        if ( !*((_QWORD *)&xmmword_1800146E0 + 1) )
          goto LABEL_30;
        v20 = L"Failed to unplumb V4 SSL binding, bail out";
        goto LABEL_29;
      }
    }
    else if ( CertificateFromSslInfo )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111);
        v16 = WPP_GLOBAL_Control;
      }
      v19 = xmmword_1800146E0;
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_30;
      v20 = L"Unable to get cert for v4";
      goto LABEL_29;
    }
  }
  v15 = GetCertificateBindingFromAddress(23, v8, &lpMem, &v83);
  if ( v15 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, v14, (unsigned __int16)v8);
      v16 = WPP_GLOBAL_Control;
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_30;
    v17 = (unsigned __int16)v8;
    v18 = L"Unable to get cert binding for V6 port: %d.";
LABEL_27:
    LOWORD(v98) = 0;
    FormatRRASErrorString(&v98, v18, v17);
    v19 = xmmword_1800146E0;
LABEL_28:
    v20 = (const wchar_t *)&v98;
LABEL_29:
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v19, v20);
    v16 = WPP_GLOBAL_Control;
LABEL_30:
    v21 = lpMem;
LABEL_31:
    v22 = v77;
LABEL_32:
    v23 = v76;
    goto LABEL_33;
  }
  v21 = lpMem;
  if ( lpMem )
  {
    v43 = GetCertificateFromSslInfo(0, lpMem, &v86);
    v15 = v43;
    if ( v43 == -2146885628 )
    {
      v15 = UnbindSslCertificate(0, v21, v83);
      if ( v15 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113);
          v16 = WPP_GLOBAL_Control;
        }
        v37 = *((_QWORD *)&xmmword_1800146E0 + 1);
        if ( !*((_QWORD *)&xmmword_1800146E0 + 1) )
          goto LABEL_31;
        v38 = L"Failed to unplumb V4 SSL binding, bail out";
        goto LABEL_93;
      }
    }
    else if ( v43 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114);
        v16 = WPP_GLOBAL_Control;
      }
      v37 = xmmword_1800146E0;
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_31;
      v38 = L"Unable to get cert for v6";
LABEL_93:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v37, v38);
LABEL_94:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_31;
    }
  }
  if ( !v78 )
  {
    v58 = v77;
    v59 = v86;
    if ( v77 || v86 )
    {
      v60 = L"Exist";
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v61 = L"Exist";
        v62 = L"Exist";
        if ( !v86 )
          v61 = L"Not Exist";
        if ( !v77 )
          v62 = L"Not Exist";
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, v14, (_DWORD)v62, (__int64)v61);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v98) = 0;
        v63 = L"Exist";
        if ( !v59 )
          v63 = L"Not Exist";
        if ( !v58 )
          v60 = L"Not Exist";
        FormatRRASErrorString(&v98, L"Currently SSL binding for V4 %ws and V6 %ws", v60, v63);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v98);
      }
      v15 = HandleV4V6CertMismatch(v85, (_DWORD)v41, v84, (_DWORD)v58, (__int64)v21, v83, (__int64)v59);
      if ( v15
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129);
      }
      if ( (_QWORD)xmmword_1800146E0 )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          xmmword_1800146E0,
          L"Unable to oonfigure certificate, bail out");
      goto LABEL_293;
    }
    SslCertificateToConfigure = GetSslCertificateToConfigure(&pCertContext);
    v67 = pCertContext;
    v15 = SslCertificateToConfigure;
    if ( SslCertificateToConfigure || !pCertContext )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, v66, SslCertificateToConfigure);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_287;
      v71 = L"Unable to get suaitable certificate for SSL binding, bail out, error: %d.";
    }
    else
    {
      v68 = (unsigned __int16)v85;
      SetSslCertificateToHttpV4((unsigned __int16)v85, pCertContext);
      v69 = SetSslCertificateToHttpV6(v68, v67);
      v15 = v69;
      if ( !v69 )
        goto LABEL_287;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, v70, v69);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_287;
      v71 = L"Unable to plumb certificate to HTTP, error: %d.";
    }
    LOWORD(v98) = 0;
    FormatRRASErrorString(&v98, v71, v15);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v98);
LABEL_287:
    if ( !v15 && v67 )
    {
      LOBYTE(v65) = 3;
      dwErrorCode = GetHashFromCertificate(v67, v65, &v95, v97);
      v15 = dwErrorCode;
      if ( dwErrorCode )
        RouterLogEventStringW(EventSource, 1u, 0x15u, 0, 0, dwErrorCode, 0);
      else
        StoreCertHash(0, v73, v74, (const BYTE *)&v95, (BYTE *)v97, 0);
    }
    goto LABEL_293;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115);
  }
  if ( (_QWORD)xmmword_1800146E0 )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      xmmword_1800146E0,
      L"Admin has configured the Hash, tring to use them");
  if ( (v75[0] & 1) != 0 )
    CertificateFromHash = GetCertificateFromHash(0);
  else
    CertificateFromHash = GetCertificateFromSha256Hash(0);
  v15 = CertificateFromHash;
  if ( CertificateFromHash || !v76 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116);
    }
    if ( (_QWORD)xmmword_1800146E0 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        xmmword_1800146E0,
        L"Unable to find certificates corresponds to configuration");
    RouterLogEventW(EventSource, 1u, 0x19u, 0, 0, 0);
    goto LABEL_94;
  }
  v46 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117);
    v46 = WPP_GLOBAL_Control;
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      xmmword_1800146E0,
      L"Found certificate correspond to the configuration");
    v46 = WPP_GLOBAL_Control;
  }
  v80[0] = 0;
  LOBYTE(v81) = 0;
  v75[0] = 0;
  v79 = 0;
  v47 = L"V4 Binding Exist";
  if ( v46 == &WPP_GLOBAL_Control || (*((_BYTE *)v46 + 28) & 0x40) == 0 )
  {
    v22 = v77;
    v48 = v86;
  }
  else
  {
    v48 = v86;
    v22 = v77;
    if ( *((_BYTE *)v46 + 25) >= 3u )
    {
      v49 = v46[2];
      v50 = L"V4 Binding Exist";
      v51 = L"V4 Binding Exist";
      if ( !v86 )
        v50 = L"V4 Binding Not Exist";
      if ( !v77 )
        v51 = L"V4 Binding Not Exist";
      WPP_SF_SS(v49, 118, v45, (_DWORD)v51, (__int64)v50);
    }
  }
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
  {
    LOWORD(v98) = 0;
    v52 = L"V4 Binding Exist";
    if ( !v48 )
      v52 = L"V4 Binding Not Exist";
    if ( !v22 )
      v47 = L"V4 Binding Not Exist";
    FormatRRASErrorString(&v98, L"Found certificates corresponds to configuration, %ws, %ws", v47, v52);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      &v98);
  }
  v15 = handleV4V6RegCertMismatch(
          (__int64)v76,
          (__int64)v22,
          (__int64)v41,
          (__int64)v48,
          (__int64)v21,
          v80,
          &v81,
          v75,
          &v79);
  if ( v15 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119);
      v16 = WPP_GLOBAL_Control;
    }
    v53 = xmmword_1800146E0;
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_32;
    v54 = L"Unable to use the configured certificate, bail out";
LABEL_184:
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v53, v54);
    v16 = WPP_GLOBAL_Control;
    goto LABEL_32;
  }
  if ( v75[0] )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120);
    }
    if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        *((_QWORD *)&xmmword_1800146E0 + 1),
        L"Unplumb V4 SSL binding");
    v15 = UnbindSslCertificate(0, v41, v84);
    if ( v15 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_198;
      }
      v55 = 121;
LABEL_197:
      WPP_SF_(v16[2], v55);
      v16 = WPP_GLOBAL_Control;
LABEL_198:
      v53 = *((_QWORD *)&xmmword_1800146E0 + 1);
      if ( !*((_QWORD *)&xmmword_1800146E0 + 1) )
        goto LABEL_32;
      v54 = L"Failed to unplumb V4 SSL binding, bail out";
      goto LABEL_184;
    }
  }
  if ( v79 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122);
    }
    if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        *((_QWORD *)&xmmword_1800146E0 + 1),
        L"Unplumb V6 SSL binding");
    v15 = UnbindSslCertificate(0, v21, v83);
    if ( v15 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_198;
      }
      v55 = 123;
      goto LABEL_197;
    }
  }
  if ( !v80[0] )
  {
    v56 = v85;
    v23 = v76;
    goto LABEL_229;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124);
  }
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      L"Plumb V4 SSL binding");
  v23 = v76;
  v56 = v85;
  v15 = SetSslCertificateToHttpV4((unsigned __int16)v85, v76);
  if ( !v15 )
  {
LABEL_229:
    if ( (_BYTE)v81 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126);
      }
      if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          *((_QWORD *)&xmmword_1800146E0 + 1),
          L"Plumb V6 SSL binding");
      v15 = SetSslCertificateToHttpV6(v56, v23);
      if ( v15 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_225;
        }
        v57 = 127;
        goto LABEL_224;
      }
    }
LABEL_293:
    SetSstpServerConfig(hKey);
    goto LABEL_94;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
  {
    goto LABEL_225;
  }
  v57 = 125;
LABEL_224:
  WPP_SF_(v16[2], v57);
  v16 = WPP_GLOBAL_Control;
LABEL_225:
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      L"Failed to unplumb V4 SSL binding, bail out");
    v16 = WPP_GLOBAL_Control;
  }
  v22 = v77;
LABEL_33:
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 0x40) != 0 && *((_BYTE *)v16 + 25) >= 3u )
    WPP_SF_d(v16[2], 132, v14, v15);
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
  {
    LOWORD(v98) = 0;
    FormatRRASErrorString(&v98, L"PlumbCertificateToHttp completed with status: %d", v15);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      &v98);
  }
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v22 )
    CertFreeCertificateContext(v22);
  if ( v86 )
    CertFreeCertificateContext(v86);
  if ( v23 )
    CertFreeCertificateContext(v23);
  if ( v21 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v21);
  }
  v25 = v88;
  if ( v88 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v25);
  }
  return v15;
}

```

## disassembly

```asm
0x180007450  push    rbp
0x180007452  push    rbx
0x180007453  push    rsi
0x180007454  push    rdi
0x180007455  push    r12
0x180007457  push    r13
0x180007459  push    r14
0x18000745b  push    r15
0x18000745d  lea     rbp, [rsp-828h]
0x180007465  sub     rsp, 928h
0x18000746c  mov     rax, cs:__security_cookie
0x180007473  xor     rax, rsp
0x180007476  mov     [rbp+860h+var_50], rax
0x18000747d  xor     edi, edi
0x18000747f  mov     [rbp+860h+hKey], r8
0x180007483  xorps   xmm1, xmm1
0x180007486  mov     [rbp+860h+var_8A8], rcx
0x18000748a  mov     r14, rdx
0x18000748d  mov     [rsp+960h+var_910], dil
0x180007492  mov     rbx, rcx
0x180007495  mov     [rsp+960h+var_900], rdi
0x18000749a  xorps   xmm0, xmm0
0x18000749d  mov     [rbp+860h+var_8D8], rdi
0x1800074a1  xor     eax, eax
0x1800074a3  mov     [rbp+860h+pCertContext], rdi
0x1800074a7  xor     edx, edx; Val
0x1800074a9  mov     [rbp+860h+var_880], eax
0x1800074ac  mov     r8d, 7FCh; Size
0x1800074b2  mov     [rsp+960h+var_908], rdi
0x1800074b7  lea     rcx, [rbp+860h+var_84C]; void *
0x1800074bb  mov     [rbp+860h+var_8D0], edi
0x1800074be  movups  [rbp+860h+var_890], xmm0
0x1800074c2  mov     [rbp+860h+var_8C8], rdi
0x1800074c6  movups  [rbp+860h+var_878], xmm1
0x1800074ca  mov     [rsp+960h+lpMem], rdi
0x1800074cf  movups  [rbp+860h+var_868], xmm1
0x1800074d3  mov     [rsp+960h+var_8E4], edi
0x1800074d7  mov     [rsp+960h+var_8E8], edi
0x1800074db  mov     [rbp+860h+var_850], edi
0x1800074de  mov     [rbp+860h+var_8A0], r9
0x1800074e2  mov     [rsp+960h+var_8F8], 1
0x1800074e7  mov     dword ptr [rbp+860h+var_8C0], 0BA195980h
0x1800074ee  mov     dword ptr [rbp+860h+var_8C0+4], 458BCD49h
0x1800074f5  mov     dword ptr [rbp+860h+var_8B8], 4EC8239Eh
0x1800074fc  mov     dword ptr [rbp+860h+var_8B8+4], 75CDADE0h
0x180007503  call    memset_0
0x180007508  lea     edx, [rdi+50h]
0x18000750b  mov     ecx, 1BBh
0x180007510  mov     [rbp+860h+var_8E0], ecx
0x180007513  cmp     di, [rbx+2]
0x180007517  jnz     short loc_180007528
0x180007519  cmp     [rbx], dil
0x18000751c  jz      short loc_180007524
0x18000751e  mov     [rbx+2], cx
0x180007522  jmp     short loc_180007528
0x180007524  mov     [rbx+2], dx
0x180007528  cmp     di, [r14+2]
0x18000752d  jnz     short loc_180007545
0x18000752f  cmp     [r14], dil
0x180007532  jz      short loc_18000753B
0x180007534  mov     [r14+2], cx
0x180007539  jmp     short loc_18000754D
0x18000753b  mov     [r14+2], dx
0x180007540  movzx   ecx, dx
0x180007543  jmp     short loc_18000754A
0x180007545  movzx   ecx, word ptr [r14+2]
0x18000754a  mov     [rbp+860h+var_8E0], ecx
0x18000754d  mov     al, [r14]
0x180007550  movzx   r13d, word ptr [rbx+2]
0x180007555  test    al, al
0x180007557  mov     [rsp+960h+var_8F4], r13w
0x18000755d  setnz   r12b
0x180007561  cmp     [rbx], dil
0x180007564  jz      short loc_18000757E
0x180007566  test    al, al
0x180007568  jz      short loc_180007578
0x18000756a  cmp     r13w, cx
0x18000756e  jz      short loc_18000757E
0x180007570  mov     r15b, 1
0x180007573  mov     r12b, r15b
0x180007576  jmp     short loc_180007581
0x180007578  setz    r15b
0x18000757c  jmp     short loc_180007581
0x18000757e  mov     r15b, dil
0x180007581  lea     rdx, [rsp+960h+var_910]
0x180007586  xor     ecx, ecx
0x180007588  call    GetCryptoBindingSupportedAlgoInfo
0x18000758d  mov     dl, [rsp+960h+var_910]
0x180007591  lea     rax, [rbp+860h+var_878]
0x180007595  mov     qword ptr [rsp+960h+dwErrorIndex], rax
0x18000759a  lea     r8, [rsp+960h+var_8F8]
0x18000759f  lea     rax, [rbp+860h+var_890]
0x1800075a3  xor     r9d, r9d
0x1800075a6  mov     qword ptr [rsp+960h+dwErrorCode], rax
0x1800075ab  xor     ecx, ecx
0x1800075ad  lea     rax, [rbp+860h+var_8D0]
0x1800075b1  mov     [rsp+960h+plpszSubStringArray], rax
0x1800075b6  call    GetCryptoBindingInfo
0x1800075bb  mov     ebx, eax
0x1800075bd  test    eax, eax
0x1800075bf  jnz     loc_1800085A3
0x1800075c5  cmp     [rbp+860h+var_8D0], 1
0x1800075c9  jz      loc_1800085A3
0x1800075cf  cmp     [rbp+860h+var_8D0], 2
0x1800075d3  jnz     loc_180007768
0x1800075d9  cmp     [r14], dil
0x1800075dc  jnz     loc_180007768
0x1800075e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075e9  lea     rsi, WPP_GLOBAL_Control
0x1800075f0  mov     dil, 40h ; '@'
0x1800075f3  cmp     rcx, rsi
0x1800075f6  jz      short loc_18000761A
0x1800075f8  test    [rcx+1Ch], dil
0x1800075fc  jz      short loc_18000761A
0x1800075fe  cmp     byte ptr [rcx+19h], 1
0x180007602  jb      short loc_18000761A
0x180007604  mov     rcx, [rcx+10h]
0x180007608  lea     edx, [rax+67h]
0x18000760b  xor     r9d, r9d
0x18000760e  call    WPP_SF_d
0x180007613  mov     rcx, cs:WPP_GLOBAL_Control
0x18000761a  xor     r12d, r12d
0x18000761d  cmp     qword ptr cs:xmmword_1800146E0, r12
0x180007624  jz      short loc_180007663
0x180007626  xor     r8d, r8d
0x180007629  lea     rdx, aHashParameters; "Hash parameters configured are invalid."...
0x180007630  lea     rcx, [rbp+860h+var_850]
0x180007634  mov     word ptr [rbp+860h+var_850], r12w
0x180007639  call    FormatRRASErrorString
0x18000763e  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180007645  lea     r8, [rbp+860h+var_850]
0x180007649  mov     rcx, cs:gSstpCfgEtwContext
0x180007650  mov     rax, cs:gSstpCfgTemplateFunc
0x180007657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000765c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007663  mov     r13, [rsp+960h+lpMem]
0x180007668  mov     r14, [rsp+960h+var_900]
0x18000766d  mov     r15, [rsp+960h+var_908]
0x180007672  cmp     rcx, rsi
0x180007675  jz      short loc_180007694
0x180007677  test    [rcx+1Ch], dil
0x18000767b  jz      short loc_180007694
0x18000767d  cmp     byte ptr [rcx+19h], 3
0x180007681  jb      short loc_180007694
0x180007683  mov     rcx, [rcx+10h]
0x180007687  mov     edx, 84h
0x18000768c  mov     r9d, ebx
0x18000768f  call    WPP_SF_d
0x180007694  cmp     qword ptr cs:xmmword_1800146E0+8, r12
0x18000769b  jz      short loc_1800076D3
0x18000769d  mov     r8d, ebx
0x1800076a0  mov     word ptr [rbp+860h+var_850], r12w
0x1800076a5  lea     rdx, aPlumbcertifica; "PlumbCertificateToHttp completed with s"...
0x1800076ac  lea     rcx, [rbp+860h+var_850]
0x1800076b0  call    FormatRRASErrorString
0x1800076b5  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x1800076bc  lea     r8, [rbp+860h+var_850]
0x1800076c0  mov     rcx, cs:gSstpCfgEtwContext
0x1800076c7  mov     rax, cs:gSstpCfgTemplateFunc
0x1800076ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d3  mov     rcx, [rbp+860h+pCertContext]; pCertContext
0x1800076d7  test    rcx, rcx
0x1800076da  jz      short loc_1800076E2
0x1800076dc  call    cs:__imp_CertFreeCertificateContext
0x1800076e2  test    r14, r14
0x1800076e5  jz      short loc_1800076F0
0x1800076e7  mov     rcx, r14; pCertContext
0x1800076ea  call    cs:__imp_CertFreeCertificateContext
0x1800076f0  mov     rcx, [rbp+860h+var_8D8]; pCertContext
0x1800076f4  test    rcx, rcx
0x1800076f7  jz      short loc_1800076FF
0x1800076f9  call    cs:__imp_CertFreeCertificateContext
0x1800076ff  test    r15, r15
0x180007702  jz      short loc_18000770D
0x180007704  mov     rcx, r15; pCertContext
0x180007707  call    cs:__imp_CertFreeCertificateContext
0x18000770d  test    r13, r13
0x180007710  jz      short loc_180007726
0x180007712  call    cs:__imp_GetProcessHeap
0x180007718  mov     r8, r13; lpMem
0x18000771b  xor     edx, edx; dwFlags
0x18000771d  mov     rcx, rax; hHeap
0x180007720  call    cs:__imp_HeapFree
0x180007726  mov     rdi, [rbp+860h+var_8C8]
0x18000772a  test    rdi, rdi
0x18000772d  jz      short loc_180007743
0x18000772f  call    cs:__imp_GetProcessHeap
0x180007735  mov     r8, rdi; lpMem
0x180007738  xor     edx, edx; dwFlags
0x18000773a  mov     rcx, rax; hHeap
0x18000773d  call    cs:__imp_HeapFree
0x180007743  mov     eax, ebx
0x180007745  mov     rcx, [rbp+860h+var_50]
0x18000774c  xor     rcx, rsp; StackCookie
0x18000774f  call    __security_check_cookie
0x180007754  add     rsp, 928h
0x18000775b  pop     r15
0x18000775d  pop     r14
0x18000775f  pop     r13
0x180007761  pop     r12
0x180007763  pop     rdi
0x180007764  pop     rsi
0x180007765  pop     rbx
0x180007766  pop     rbp
0x180007767  retn
0x180007768  mov     rcx, cs:WPP_GLOBAL_Control
0x18000776f  lea     rsi, WPP_GLOBAL_Control
0x180007776  mov     dil, 40h ; '@'
0x180007779  cmp     rcx, rsi
0x18000777c  jz      short loc_1800077C6
0x18000777e  test    [rcx+1Ch], dil
0x180007782  jz      short loc_1800077A3
0x180007784  cmp     byte ptr [rcx+19h], 3
0x180007788  jb      short loc_1800077A3
0x18000778a  mov     rcx, [rcx+10h]
0x18000778e  mov     edx, 68h ; 'h'
0x180007793  movzx   r9d, r12b
0x180007797  call    WPP_SF_d
0x18000779c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077a3  cmp     rcx, rsi
0x1800077a6  jz      short loc_1800077C6
0x1800077a8  test    [rcx+1Ch], dil
0x1800077ac  jz      short loc_1800077C6
0x1800077ae  cmp     byte ptr [rcx+19h], 3
0x1800077b2  jb      short loc_1800077C6
0x1800077b4  mov     rcx, [rcx+10h]
0x1800077b8  mov     edx, 69h ; 'i'
0x1800077bd  movzx   r9d, r15b
0x1800077c1  call    WPP_SF_d
0x1800077c6  cmp     qword ptr cs:xmmword_1800146E0+8, 0
0x1800077ce  jz      short loc_18000784A
0x1800077d0  xor     eax, eax
0x1800077d2  movzx   r8d, r12b
0x1800077d6  lea     rdx, aCheckForCertif; "Check for Certificate Status: %d."
0x1800077dd  mov     word ptr [rbp+860h+var_850], ax
0x1800077e1  lea     rcx, [rbp+860h+var_850]
0x1800077e5  call    FormatRRASErrorString
0x1800077ea  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x1800077f1  lea     r8, [rbp+860h+var_850]
0x1800077f5  mov     rcx, cs:gSstpCfgEtwContext
0x1800077fc  mov     rax, cs:gSstpCfgTemplateFunc
0x180007803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007808  cmp     qword ptr cs:xmmword_1800146E0+8, 0
0x180007810  jz      short loc_18000784A
0x180007812  xor     eax, eax
0x180007814  movzx   r8d, r15b
0x180007818  lea     rdx, aRemoveCertific; "Remove Certificate Status: %d."
0x18000781f  mov     word ptr [rbp+860h+var_850], ax
0x180007823  lea     rcx, [rbp+860h+var_850]
0x180007827  call    FormatRRASErrorString
0x18000782c  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x180007833  lea     r8, [rbp+860h+var_850]
0x180007837  mov     rcx, cs:gSstpCfgEtwContext
0x18000783e  mov     rax, cs:gSstpCfgTemplateFunc
0x180007845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000784a  movzx   eax, word ptr [r14+2]
0x18000784f  mov     rcx, [rbp+860h+var_8A8]
0x180007853  mov     [rcx+2], ax
0x180007857  mov     al, [r14]
0x18000785a  mov     [rcx], al
0x18000785c  test    r15b, r15b
0x18000785f  jz      loc_180007AAA
0x180007865  mov     rcx, cs:WPP_GLOBAL_Control
0x18000786c  cmp     rcx, rsi
0x18000786f  jz      short loc_18000788E
0x180007871  test    [rcx+1Ch], dil
0x180007875  jz      short loc_18000788E
0x180007877  cmp     byte ptr [rcx+19h], 3
0x18000787b  jb      short loc_18000788E
0x18000787d  mov     rcx, [rcx+10h]
0x180007881  mov     r9d, r13d
0x180007884  mov     edx, 6Ah ; 'j'
0x180007889  call    WPP_SF_d
0x18000788e  cmp     qword ptr cs:xmmword_1800146E0+8, 0
0x180007896  jz      short loc_1800078CF
0x180007898  xor     eax, eax
0x18000789a  lea     rdx, aAttemptingRemo; "Attempting removal of certificates boun"...
0x1800078a1  mov     r8d, r13d
0x1800078a4  mov     word ptr [rbp+860h+var_850], ax
0x1800078a8  lea     rcx, [rbp+860h+var_850]
0x1800078ac  call    FormatRRASErrorString
0x1800078b1  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x1800078b8  lea     r8, [rbp+860h+var_850]
0x1800078bc  mov     rcx, cs:gSstpCfgEtwContext
0x1800078c3  mov     rax, cs:gSstpCfgTemplateFunc
0x1800078ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078cf  mov     ecx, 2
0x1800078d4  lea     r9, [rsp+960h+var_8E4]
0x1800078d9  lea     r8, [rbp+860h+var_8C8]
0x1800078dd  mov     edx, r13d
0x1800078e0  call    GetCertificateBindingFromAddress
0x1800078e5  mov     r15, [rbp+860h+var_8B8]
0x1800078e9  mov     r14, [rbp+860h+var_8C0]
0x1800078ed  test    eax, eax
0x1800078ef  jnz     loc_1800079AA
0x1800078f5  mov     rbx, [rbp+860h+var_8C8]
0x1800078f9  test    rbx, rbx
0x1800078fc  jz      loc_1800079AA
0x180007902  cmp     [rbx+18h], r14
0x180007906  jnz     loc_1800079AA
  ... truncated ...
```
