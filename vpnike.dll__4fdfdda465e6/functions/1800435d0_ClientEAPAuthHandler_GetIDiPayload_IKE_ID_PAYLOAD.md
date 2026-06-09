# ClientEAPAuthHandler::GetIDiPayload(_IKE_ID_PAYLOAD * *)

- ea: `0x1800435d0`
- end: `0x180044ac4`
- name: `?GetIDiPayload@ClientEAPAuthHandler@@QEAAKPEAPEAU_IKE_ID_PAYLOAD@@@Z`
- size: `5364`
- prototype: `__int64 __fastcall(ClientEAPAuthHandler *this, struct _IKE_ID_PAYLOAD **)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800516d0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180008a7c`
- `0x18000a0d0`
- `0x180042ad8`
- `0x1800435d0`
- `0x18006aa00`
- `0x18006b1d0`
- `0x18006b780`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `msvcrt!strchr` at `0x1800440d8`
- `msvcrt!strchr` at `0x1800440d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004489d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800449f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004489d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800449f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004488f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800449e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004488f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800449e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004450f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800445ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800448d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004450f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800445ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800448d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180043a17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180043a17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043a87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044854`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043a87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044854`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800438eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800438eb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180044257`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180044257`
- `CRYPT32!CertOpenStore` at `0x18004447c`
- `CRYPT32!CertOpenStore` at `0x18004447c`
- `CRYPT32!CertFindCertificateInStore` at `0x180044558`
- `CRYPT32!CertFindCertificateInStore` at `0x180044558`
- `CRYPT32!CertFreeCertificateContext` at `0x1800448ab`
- `CRYPT32!CertFreeCertificateContext` at `0x1800448ab`
- `CRYPT32!CertCloseStore` at `0x1800448c2`
- `CRYPT32!CertCloseStore` at `0x1800448c2`
- `eappcfg!EapHostPeerFreeMemory` at `0x180044871`
- `eappcfg!EapHostPeerFreeMemory` at `0x180044880`
- `eappcfg!EapHostPeerFreeMemory` at `0x180044871`
- `eappcfg!EapHostPeerFreeMemory` at `0x180044880`
- `eappcfg!EapHostPeerInvokeIdentityUI` at `0x180043d23`
- `eappcfg!EapHostPeerInvokeIdentityUI` at `0x180043d23`

## string_xrefs

- `0x1800438dd`: `System\CurrentControlSet\Services\rasman\IKEv2`
- `0x18004397e`: `System\CurrentControlSet\Services\rasman\IKEv2`
- `0x180043da8`: `StringCopyWtoAAlloc failed: %d`
- `0x180043985`: `ClientEAPAuthHandler::GetIDiPayload: RegOpenKeyEx failed for %s, Error:0X%x`
- `0x1800447ce`: `ClientEAPAuthHandler::GetIDiPayload: Either DWORD registry value %s is not present or present with with value 0`
- `0x1800442ff`: `ImpersonateLoggedOnUser(%d) failed and returned 0x%x`
- `0x180044515`: `Failed to access the certificate store: 0x%x.`

## pseudocode

```c
__int64 __fastcall ClientEAPAuthHandler::GetIDiPayload(ClientEAPAuthHandler *this, struct _IKE_ID_PAYLOAD **a2)
{
  struct _IKE_ID_PAYLOAD **v2; // rdi
  unsigned int v4; // r15d
  char v5; // al
  void **v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  __int128 *v12; // r9
  HCERTSTORE v13; // r13
  const CERT_CONTEXT *v14; // r12
  __int64 v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int128 *v19; // r9
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  char *v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rcx
  __int128 *v29; // r9
  __int64 *v30; // rdx
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  _QWORD *v37; // rax
  __int64 v38; // rcx
  __int128 *v39; // r9
  __int64 v40; // rcx
  unsigned int EapMethodTypeFromEapType; // eax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // r8
  __int64 v47; // rdx
  DWORD v48; // eax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rcx
  _QWORD *v53; // rax
  __int64 v54; // rcx
  __int128 *v55; // r9
  char *v56; // rbx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  _QWORD *v64; // rax
  const wchar_t *v65; // r8
  __int64 v66; // rdi
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rcx
  _QWORD *v72; // rax
  __int64 v73; // rcx
  __int128 *v74; // r9
  const wchar_t *v75; // r8
  unsigned int IDObject; // eax
  __int64 v77; // rcx
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rcx
  _QWORD *v82; // rax
  _DWORD *v83; // rax
  void *v84; // rcx
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rdx
  DWORD LastError; // eax
  __int64 v89; // rcx
  _QWORD *v90; // rax
  _DWORD *CertificateHashFromEapUserBlob; // rbx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // rcx
  _QWORD *v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rdx
  DWORD v100; // eax
  const struct _CERT_CONTEXT *CertificateInStore; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rdx
  DWORD v105; // eax
  unsigned int IDFromCert; // eax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rdx
  __int64 v110; // r8
  __int64 v111; // rax
  __int64 v112; // rax
  __int64 v113; // rdx
  __int64 v114; // rcx
  _QWORD *v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rcx
  _QWORD *v120; // rax
  char *v121; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v123; // ebx
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rcx
  _QWORD *v127; // rax
  __int64 v128; // rcx
  __int128 *v129; // r9
  struct _IKE_ID_PAYLOAD *v130; // rbx
  HANDLE v131; // rax
  unsigned int v132; // eax
  unsigned int v133; // ebx
  unsigned int v135; // [rsp+70h] [rbp-90h] BYREF
  struct _IKE_ID_PAYLOAD **v136; // [rsp+78h] [rbp-88h]
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type; // [rsp+84h] [rbp-7Ch] BYREF
  BYTE Data[4]; // [rsp+88h] [rbp-78h] BYREF
  DWORD pdwSizeOfUserDataOut; // [rsp+8Ch] [rbp-74h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+A0h] [rbp-60h] BYREF
  int v143; // [rsp+B0h] [rbp-50h]
  LPWSTR ppwszIdentity; // [rsp+B8h] [rbp-48h] BYREF
  char *Str; // [rsp+C0h] [rbp-40h]
  EAP_ERROR *pEapError; // [rsp+C8h] [rbp-38h] BYREF
  BYTE *pData; // [rsp+D0h] [rbp-30h] BYREF
  __int128 pvFindPara; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v149; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v150; // [rsp+F0h] [rbp-10h]
  __int128 v151; // [rsp+100h] [rbp+0h]
  __int64 v152; // [rsp+110h] [rbp+10h]
  int v153; // [rsp+118h] [rbp+18h]
  int v154; // [rsp+11Ch] [rbp+1Ch]
  __int128 v155; // [rsp+120h] [rbp+20h] BYREF
  int v156; // [rsp+130h] [rbp+30h] BYREF
  __int128 v157; // [rsp+134h] [rbp+34h]
  __int128 v158; // [rsp+144h] [rbp+44h]
  int v159; // [rsp+154h] [rbp+54h]
  int v160; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v161[2044]; // [rsp+164h] [rbp+64h] BYREF

  v2 = a2;
  v136 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
  }
  v135 = 0;
  pvFindPara = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  Str = 0;
  pData = 0;
  pdwSizeOfUserDataOut = 0;
  pEapError = 0;
  eapMethodType.eapType.type = 0;
  *(_WORD *)(&eapMethodType.eapType.type + 1) = 0;
  *(&eapMethodType.eapType.type + 3) = 0;
  *(_QWORD *)&eapMethodType.eapType.dwVendorId = 0;
  eapMethodType.dwAuthorId = 0;
  ppwszIdentity = 0;
  Type = 0;
  v160 = 0;
  memset_0(v161, 0, sizeof(v161));
  v156 = 0;
  v157 = 0;
  v158 = 0;
  v159 = 0;
  v155 = 0;
  v150 = 0;
  v149 = 0;
  v151 = 0;
  v152 = 0;
  v4 = -1;
  v153 = -1;
  v154 = 0;
  v5 = byte_1800AA941;
  v6 = (void **)((char *)this + 560);
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v149,
      L"ClientEAPAuthHandler::GetIDiPayload",
      &v135,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      *v6);
    v5 = byte_1800AA941;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v156) = 0;
      v6 = (void **)((char *)this + 560);
      v7 = *((_QWORD *)this + 70);
      if ( v7 && (v8 = *(_QWORD *)(v7 + 112)) != 0 && *(_QWORD *)(v8 + 16) )
        v9 = *(unsigned int *)(v8 + 16);
      else
        v9 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v156, v9);
      v5 = byte_1800AA941;
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v10 = (char *)*v6 + 112;
        if ( *v6 )
        {
          if ( *v10 )
          {
            v11 = *v10 + 2686LL;
            goto LABEL_18;
          }
          if ( *v6 )
          {
            v11 = 0;
LABEL_18:
            if ( *v10 )
            {
              v12 = (__int128 *)(*v10 + 2120LL);
LABEL_22:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceInfo,
                (unsigned int)L"ClientEAPAuthHandler::GetIDiPayload is called.",
                (_DWORD)v12,
                v11,
                (__int64)&v156);
              v5 = byte_1800AA941;
              goto LABEL_23;
            }
LABEL_21:
            v12 = &v155;
            goto LABEL_22;
          }
        }
        v11 = 0;
        goto LABEL_21;
      }
    }
  }
LABEL_23:
  v13 = 0;
  v14 = 0;
  if ( !v2 )
  {
    if ( (v5 & 4) == 0
      || ((LOWORD(v156) = 0, !*v6) || (v15 = *((_QWORD *)*v6 + 14)) == 0 || !*(_QWORD *)(v15 + 16)
        ? (v16 = 0xFFFFFFFFLL)
        : (v16 = *(unsigned int *)(v15 + 16)),
          ConvertPortNoToString(&v156, v16),
          (byte_1800AA941 & 4) == 0) )
    {
LABEL_41:
      v135 = 87;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 76;
        v22 = 87;
LABEL_45:
        WPP_SF_d(v20[2], v21, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v22);
        goto LABEL_358;
      }
      goto LABEL_358;
    }
    v17 = (char *)*v6 + 112;
    if ( *v6 )
    {
      if ( *v17 )
      {
        v18 = *v17 + 2686LL;
        goto LABEL_36;
      }
      if ( *v6 )
      {
        v18 = 0;
LABEL_36:
        if ( *v17 )
        {
          v19 = (__int128 *)(*v17 + 2120LL);
LABEL_40:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)L"Invalid Parameter",
            (_DWORD)v19,
            v18,
            (__int64)&v156);
          goto LABEL_41;
        }
LABEL_39:
        v19 = &v155;
        goto LABEL_40;
      }
    }
    v18 = 0;
    goto LABEL_39;
  }
  v23 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 1u, &hKey);
  v135 = v23;
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v23);
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_358;
    LOWORD(v160) = 0;
    LOWORD(v156) = 0;
    if ( *v6 && (v24 = *((_QWORD *)*v6 + 14)) != 0 && *(_QWORD *)(v24 + 16) )
      v25 = *(unsigned int *)(v24 + 16);
    else
      v25 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v156, v25);
    FormatRRASErrorString(
      &v160,
      L"ClientEAPAuthHandler::GetIDiPayload: RegOpenKeyEx failed for %s, Error:0X%x",
      "System\\CurrentControlSet\\Services\\rasman\\IKEv2",
      v135);
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_358;
    v26 = (char *)*v6;
LABEL_59:
    v27 = v26 + 112;
    if ( v26 )
    {
      if ( *v27 )
        v28 = *v27 + 2686LL;
      else
        v28 = 0;
      if ( *v27 )
      {
        v29 = (__int128 *)(*v27 + 2120LL);
LABEL_67:
        v30 = RasVpnIkeParamTraceError;
LABEL_356:
        v65 = (const wchar_t *)&v160;
        goto LABEL_357;
      }
    }
    else
    {
      v28 = 0;
    }
    v29 = &v155;
    goto LABEL_67;
  }
  cbData = 4;
  v31 = RegQueryValueExA(hKey, "ExtendedIDiSupport", 0, &Type, Data, &cbData);
  v135 = v31;
  if ( v31
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v31);
  }
  if ( v135 || Type != 4 || !*(_DWORD *)Data )
  {
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_358;
    LOWORD(v160) = 0;
    LOWORD(v156) = 0;
    v116 = *((_QWORD *)this + 70);
    if ( v116 && (v117 = *(_QWORD *)(v116 + 112)) != 0 && *(_QWORD *)(v117 + 16) )
      v118 = *(unsigned int *)(v117 + 16);
    else
      v118 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v156, v118);
    FormatRRASErrorString(
      &v160,
      L"ClientEAPAuthHandler::GetIDiPayload: Either DWORD registry value %s is not present or present with with value 0",
      "ExtendedIDiSupport");
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_358;
    v119 = *((_QWORD *)this + 70);
    v120 = (_QWORD *)(v119 + 112);
    if ( v119 )
    {
      if ( *v120 )
        v28 = *v120 + 2686LL;
      else
        v28 = 0;
      if ( *v120 )
      {
        v29 = (__int128 *)(*v120 + 2120LL);
LABEL_355:
        v30 = RasVpnIkeParamTraceInfo;
        goto LABEL_356;
      }
    }
    else
    {
      v28 = 0;
    }
    v29 = &v155;
    goto LABEL_355;
  }
  RegCloseKey(hKey);
  hKey = 0;
  if ( !*((_BYTE *)this + 568) )
  {
    v32 = (*(__int64 (__fastcall **)(ClientEAPAuthHandler *))(*(_QWORD *)this + 64LL))(this);
    v135 = v32;
    if ( v32 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v32);
      }
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_99;
      LOWORD(v160) = 0;
      LOWORD(v156) = 0;
      v33 = *((_QWORD *)this + 70);
      if ( v33 && (v34 = *(_QWORD *)(v33 + 112)) != 0 && *(_QWORD *)(v34 + 16) )
        v35 = *(unsigned int *)(v34 + 16);
      else
        v35 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v156, v35);
      FormatRRASErrorString(&v160, L"AuthBegin() failed: %d", v135);
      goto LABEL_89;
    }
    *((_BYTE *)this + 568) = 1;
  }
  v40 = 25;
  if ( *((_DWORD *)this + 422) != 25 || *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 4440LL) != 2 )
  {
    v56 = (char *)this + 281;
LABEL_176:
    v66 = -1;
    if ( *v56 == 64 )
    {
      v67 = -1;
      do
        ++v67;
      while ( v56[v67] );
      if ( v67 == 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
        }
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_201;
        LOWORD(v156) = 0;
        v68 = *((_QWORD *)this + 70);
        if ( v68 && (v69 = *(_QWORD *)(v68 + 112)) != 0 && *(_QWORD *)(v69 + 16) )
          v70 = *(unsigned int *)(v69 + 16);
        else
          v70 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v156, v70);
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_201;
        v71 = *((_QWORD *)this + 70);
        v72 = (_QWORD *)(v71 + 112);
        if ( v71 )
        {
          if ( *v72 )
            v73 = *v72 + 2686LL;
          else
            v73 = 0;
          if ( *v72 )
          {
            v74 = (__int128 *)(*v72 + 2120LL);
LABEL_199:
            v75 = L"Identity specified by user is invalid.";
LABEL_200:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (_DWORD)v75,
              (_DWORD)v74,
              v73,
              (__int64)&v156);
            goto LABEL_201;
          }
        }
        else
        {
          v73 = 0;
        }
        v74 = &v155;
        goto LABEL_199;
      }
      LOBYTE(v40) = 2;
      ++v56;
      do
LABEL_205:
        ++v66;
      while ( v56[v66] );
      IDObject = CreateIDObject(v40, (unsigned int)v66, v56, v136);
      v135 = IDObject;
      if ( IDObject
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, IDObject);
      }
      goto LABEL_201;
    }
    if ( strchr(v56, 64) )
    {
      LOBYTE(v40) = 3;
      goto LABEL_205;
    }
    v77 = *(_QWORD *)(*((_QWORD *)this + 70) + 112LL);
    if ( *(_DWORD *)(v77 + 4440) == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
      }
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_201;
      LOWORD(v156) = 0;
      v78 = *((_QWORD *)this + 70);
      if ( v78 && (v79 = *(_QWORD *)(v78 + 112)) != 0 && *(_QWORD *)(v79 + 16) )
        v80 = *(unsigned int *)(v79 + 16);
      else
        v80 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v156, v80);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_201;
      v81 = *((_QWORD *)this + 70);
      v82 = (_QWORD *)(v81 + 112);
      if ( v81 )
      {
        if ( *v82 )
          v73 = *v82 + 2686LL;
        else
          v73 = 0;
        if ( *v82 )
        {
          v74 = (__int128 *)(*v82 + 2120LL);
LABEL_231:
          v75 = L"Username specified by user is not in e-mail format.";
          goto LABEL_200;
        }
      }
      else
      {
        v73 = 0;
      }
      v74 = &v155;
      goto LABEL_231;
    }
    v83 = *(_DWORD **)(*((_QWORD *)this + 72) + 344LL);
    if ( v83 && *v83 && v83 != (_DWORD *)-4LL )
    {
      v84 = *(void **)(v77 + 64);
      if ( v84 && !ImpersonateLoggedOnUser(v84) )
      {
        if ( v135
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v135);
        }
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_201;
        LOWORD(v160) = 0;
        LOWORD(v156) = 0;
        v85 = *((_QWORD *)this + 70);
        if ( v85 && (v86 = *(_QWORD *)(v85 + 112)) != 0 && *(_QWORD *)(v86 + 16) )
          v87 = *(unsigned int *)(v86 + 16);
        else
          v87 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v156, v87);
        LastError = GetLastError();
        FormatRRASErrorString(
          &v160,
          L"ImpersonateLoggedOnUser(%d) failed and returned 0x%x",
          *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 70) + 112LL) + 64LL),
          LastError);
        goto LABEL_249;
      }
      CertificateHashFromEapUserBlob = (_DWORD *)GetCertificateHashFromEapUserBlob(
                                                   *((unsigned int *)this + 422),
                                                   *(_QWORD *)(*((_QWORD *)this + 72) + 344LL) + 4LL);
      if ( CertificateHashFromEapUserBlob )
      {
        v13 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x18000u, L"MY");
        if ( v13 )
        {
          LODWORD(pvFindPara) = *CertificateHashFromEapUserBlob;
          *((_QWORD *)&pvFindPara + 1) = CertificateHashFromEapUserBlob + 1;
          CertificateInStore = CertFindCertificateInStore(v13, 1u, 0, 0x10000u, &pvFindPara, 0);
          v14 = CertificateInStore;
          if ( CertificateInStore )
          {
            v2 = v136;
            IDFromCert = ClientEAPAuthHandler::GetIDFromCert(this, CertificateInStore, v136);
            v135 = IDFromCert;
            if ( !IDFromCert )
              goto LABEL_358;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                92,
                &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids,
                IDFromCert);
            }
            if ( (byte_1800AA941 & 4) == 0 )
              goto LABEL_358;
            LOWORD(v160) = 0;
            LOWORD(v156) = 0;
            v107 = *((_QWORD *)this + 70);
            if ( v107 && (v108 = *(_QWORD *)(v107 + 112)) != 0 && *(_QWORD *)(v108 + 16) )
              v109 = *(unsigned int *)(v108 + 16);
            else
              v109 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v156, v109);
            v110 = GetLastError();
            FormatRRASErrorString(&v160, L"GetIDFromCert Failed: 0x%x.", v110);
            goto LABEL_115;
          }
          if ( v135
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v135);
          }
          if ( (byte_1800AA941 & 4) == 0 )
          {
LABEL_201:
            v2 = v136;
            goto LABEL_358;
          }
          LOWORD(v160) = 0;
          LOWORD(v156) = 0;
          v102 = *((_QWORD *)this + 70);
          if ( v102 && (v103 = *(_QWORD *)(v102 + 112)) != 0 && *(_QWORD *)(v103 + 16) )
            v104 = *(unsigned int *)(v103 + 16);
          else
            v104 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v156, v104);
          v105 = GetLastError();
          FormatRRASErrorString(&v160, L"CertFindCertificateInStore Failed: 0x%x.", v105);
        }
        else
        {
          if ( v135
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v135);
          }
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_201;
          LOWORD(v160) = 0;
          LOWORD(v156) = 0;
          v97 = *((_QWORD *)this + 70);
          if ( v97 && (v98 = *(_QWORD *)(v97 + 112)) != 0 && *(_QWORD *)(v98 + 16) )
            v99 = *(unsigned int *)(v98 + 16);
          else
            v99 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v156, v99);
          v100 = GetLastError();
          FormatRRASErrorString(&v160, L"Failed to access the certificate store: 0x%x.", v100);
        }
LABEL_249:
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_201;
        v89 = *((_QWORD *)this + 70);
        v90 = (_QWORD *)(v89 + 112);
        if ( v89 )
        {
          if ( *v90 )
            v73 = *v90 + 2686LL;
          else
            v73 = 0;
          if ( *v90 )
          {
            v74 = (__int128 *)(*v90 + 2120LL);
LABEL_258:
            v75 = (const wchar_t *)&v160;
            goto LABEL_200;
          }
        }
        else
        {
          v73 = 0;
        }
        v74 = &v155;
        goto LABEL_258;
      }
      if ( v135
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v135);
      }
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_201;
      LOWORD(v156) = 0;
      v92 = *((_QWORD *)this + 70);
      if ( v92 && (v93 = *(_QWORD *)(v92 + 112)) != 0 && *(_QWORD *)(v93 + 16) )
        v94 = *(unsigned int *)(v93 + 16);
      else
        v94 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v156, v94);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_201;
      v95 = *((_QWORD *)this + 70);
      v96 = (_QWORD *)(v95 + 112);
      if ( v95 )
      {
        if ( *v96 )
          v73 = *v96 + 2686LL;
        else
          v73 = 0;
        if ( *v96 )
        {
          v74 = (__int128 *)(*v96 + 2120LL);
LABEL_280:
          v75 = L"Failed to get the certificate hash for the user.";
          goto LABEL_200;
        }
      }
      else
      {
        v73 = 0;
      }
      v74 = &v155;
      goto LABEL_280;
    }
    if ( v135
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v135);
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_201;
    LOWORD(v156) = 0;
    v111 = *((_QWORD *)this + 70);
    if ( v111 && (v112 = *(_QWORD *)(v111 + 112)) != 0 && *(_QWORD *)(v112 + 16) )
      v113 = *(unsigned int *)(v112 + 16);
    else
      v113 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v156, v113);
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_201;
    v114 = *((_QWORD *)this + 70);
    v115 = (_QWORD *)(v114 + 112);
    if ( v114 )
    {
      if ( *v115 )
        v73 = *v115 + 2686LL;
      else
        v73 = 0;
      if ( *v115 )
      {
        v74 = (__int128 *)(*v115 + 2120LL);
LABEL_339:
        v75 = L"Unable to get user EAP data";
        goto LABEL_200;
      }
    }
    else
    {
      v73 = 0;
    }
    v74 = &v155;
    goto LABEL_339;
  }
  EapMethodTypeFromEapType = RasGetEapMethodTypeFromEapType(25, &eapMethodType);
  v135 = EapMethodTypeFromEapType;
  if ( EapMethodTypeFromEapType )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids,
        EapMethodTypeFromEapType);
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_358;
    LOWORD(v160) = 0;
    LOWORD(v156) = 0;
    v42 = *((_QWORD *)this + 70);
    if ( v42 && (v43 = *(_QWORD *)(v42 + 112)) != 0 && *(_QWORD *)(v43 + 16) )
      v44 = *(unsigned int *)(v43 + 16);
    else
      v44 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v156, v44);
    FormatRRASErrorString(&v160, L"RasGetEapMethodTypeFromEapType failed: %d", v135);
LABEL_115:
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_358;
    v26 = (char *)*((_QWORD *)this + 70);
    goto LABEL_59;
  }
  v45 = *((_QWORD *)this + 72);
  v46 = *(_QWORD *)(v45 + 344);
  if ( !v46 || (v47 = *(_QWORD *)(v45 + 336)) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_358;
    LOWORD(v156) = 0;
    v60 = *((_QWORD *)this + 70);
    if ( v60 && (v61 = *(_QWORD *)(v60 + 112)) != 0 && *(_QWORD *)(v61 + 16) )
      v62 = *(unsigned int *)(v61 + 16);
    else
      v62 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v156, v62);
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_358;
    v63 = *((_QWORD *)this + 70);
    v64 = (_QWORD *)(v63 + 112);
    if ( v63 )
    {
      if ( *v64 )
        v28 = *v64 + 2686LL;
      else
        v28 = 0;
      if ( *v64 )
      {
        v29 = (__int128 *)(*v64 + 2120LL);
LABEL_174:
        v65 = L"ClientEAPAuthHandler::GetIDiPayload: No user data or connection data available.";
        v30 = RasVpnIkeParamTraceError;
LABEL_357:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v30,
          (_DWORD)v65,
          (_DWORD)v29,
          v28,
          (__int64)&v156);
        goto LABEL_358;
      }
    }
    else
    {
      v28 = 0;
    }
    v29 = &v155;
    goto LABEL_174;
  }
  v48 = EapHostPeerInvokeIdentityUI(
          0,
          &eapMethodType,
          2u,
          0,
          *(_DWORD *)v47,
          (const BYTE *)(v47 + 4),
          *(_DWORD *)v46,
          (const BYTE *)(v46 + 4),
          &pdwSizeOfUserDataOut,
          &pData,
          &ppwszIdentity,
          &pEapError,
          0);
  v135 = v48;
  if ( v48 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v48);
    }
    goto LABEL_148;
  }
  if ( !pdwSizeOfUserDataOut )
  {
LABEL_148:
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_99;
    LOWORD(v160) = 0;
    LOWORD(v156) = 0;
    v57 = *((_QWORD *)this + 70);
    if ( v57 && (v58 = *(_QWORD *)(v57 + 112)) != 0 && *(_QWORD *)(v58 + 16) )
      v59 = *(unsigned int *)(v58 + 16);
    else
      v59 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v156, v59);
    FormatRRASErrorString(&v160, L"EapHostPeerInvokeIdentityUI failed: %d", v135);
LABEL_89:
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_99:
      v135 = 0;
      goto LABEL_358;
    }
    v36 = *((_QWORD *)this + 70);
    v37 = (_QWORD *)(v36 + 112);
    if ( v36 )
    {
      if ( *v37 )
        v38 = *v37 + 2686LL;
      else
        v38 = 0;
      if ( *v37 )
      {
        v39 = (__int128 *)(*v37 + 2120LL);
LABEL_98:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v160,
          (_DWORD)v39,
          v38,
          (__int64)&v156);
        goto LABEL_99;
      }
    }
    else
    {
      v38 = 0;
    }
    v39 = &v155;
    goto LABEL_98;
  }
  v143 = 0;
  v135 = StringCopyWtoAAlloc(ppwszIdentity);
  if ( !v135 )
  {
    v56 = Str;
    goto LABEL_176;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v160) = 0;
    LOWORD(v156) = 0;
    v49 = *((_QWORD *)this + 70);
    if ( v49 && (v50 = *(_QWORD *)(v49 + 112)) != 0 && *(_QWORD *)(v50 + 16) )
      v51 = *(unsigned int *)(v50 + 16);
    else
      v51 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v156, v51);
    FormatRRASErrorString(&v160, L"StringCopyWtoAAlloc failed: %d", v135);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v52 = *((_QWORD *)this + 70);
      v53 = (_QWORD *)(v52 + 112);
      if ( v52 )
      {
        if ( *v53 )
          v54 = *v53 + 2686LL;
        else
          v54 = 0;
        if ( *v53 )
        {
          v55 = (__int128 *)(*v53 + 2120LL);
LABEL_137:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v160,
            (_DWORD)v55,
            v54,
            (__int64)&v156);
          goto LABEL_138;
        }
      }
      else
      {
        v54 = 0;
      }
      v55 = &v155;
      goto LABEL_137;
    }
  }
LABEL_138:
  if ( v135 != 8 )
    goto LABEL_99;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = 83;
    v22 = 8;
    goto LABEL_45;
  }
LABEL_358:
  if ( hKey )
    RegCloseKey(hKey);
  if ( pEapError )
    RasFreeEapConfigErrorMemory(pEapError);
  if ( pData )
    EapHostPeerFreeMemory(pData);
  if ( ppwszIdentity )
    EapHostPeerFreeMemory((BYTE *)ppwszIdentity);
  v121 = Str;
  if ( Str )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v121);
  }
  if ( v14 )
    CertFreeCertificateContext(v14);
  if ( v13 && !CertCloseStore(v13, 0) )
  {
    v123 = GetLastError();
    if ( v123
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v123);
    }
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v160) = 0;
      LOWORD(v156) = 0;
      v124 = *((_QWORD *)this + 70);
      if ( v124 )
      {
        v125 = *(_QWORD *)(v124 + 112);
        if ( v125 )
        {
          if ( *(_QWORD *)(v125 + 16) )
            v4 = *(_DWORD *)(v125 + 16);
        }
      }
      ConvertPortNoToString(&v156, v4);
      FormatRRASErrorString(&v160, L"CertCloseStore failed and returned 0x%x", v123);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v126 = *((_QWORD *)this + 70);
        v127 = (_QWORD *)(v126 + 112);
        if ( v126 )
        {
          if ( *v127 )
            v128 = *v127 + 2686LL;
          else
            v128 = 0;
          if ( *v127 )
          {
            v129 = (__int128 *)(*v127 + 2120LL);
LABEL_391:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v160,
              (_DWORD)v129,
              v128,
              (__int64)&v156);
            goto LABEL_392;
          }
        }
        else
        {
          v128 = 0;
        }
        v129 = &v155;
        goto LABEL_391;
      }
    }
  }
LABEL_392:
  if ( v135 && (v130 = *v2) != 0 )
  {
    v131 = GetProcessHeap();
    HeapFree(v131, 0, v130);
    *v2 = 0;
  }
  else if ( !*v2 )
  {
    v132 = CreateIDObject(0, 0, 0, v2);
    v135 = v132;
    if ( v132 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_405;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v132);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v135);
  }
LABEL_405:
  v133 = v135;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v149);
  return v133;
}

```

## disassembly

```asm
0x1800435d0  mov     [rsp-8+arg_10], rbx
0x1800435d5  push    rbp
0x1800435d6  push    rsi
0x1800435d7  push    rdi
0x1800435d8  push    r12
0x1800435da  push    r13
0x1800435dc  push    r14
0x1800435de  push    r15
0x1800435e0  lea     rbp, [rsp-870h]
0x1800435e8  sub     rsp, 970h
0x1800435ef  mov     rax, cs:__security_cookie
0x1800435f6  xor     rax, rsp
0x1800435f9  mov     [rbp+8A0h+var_40], rax
0x180043600  mov     rdi, rdx
0x180043603  mov     [rsp+9A0h+var_928], rdx
0x180043608  mov     rsi, rcx
0x18004360b  lea     rax, WPP_GLOBAL_Control
0x180043612  mov     rcx, cs:WPP_GLOBAL_Control
0x180043619  cmp     rcx, rax
0x18004361c  jz      short loc_18004363F
0x18004361e  test    byte ptr [rcx+1Ch], 1
0x180043622  jz      short loc_18004363F
0x180043624  cmp     byte ptr [rcx+19h], 6
0x180043628  jb      short loc_18004363F
0x18004362a  mov     edx, 4Bh ; 'K'
0x18004362f  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x180043636  mov     rcx, [rcx+10h]
0x18004363a  call    WPP_SF_
0x18004363f  xor     r14d, r14d
0x180043642  mov     [rsp+9A0h+var_930], r14d
0x180043647  xorps   xmm0, xmm0
0x18004364a  movups  [rbp+8A0h+pvFindPara], xmm0
0x18004364e  mov     [rbp+8A0h+hKey], r14
0x180043652  mov     dword ptr [rbp+8A0h+Data], r14d
0x180043656  mov     [rbp+8A0h+cbData], r14d
0x18004365a  mov     [rbp+8A0h+Str], r14
0x18004365e  mov     [rbp+8A0h+pData], r14
0x180043662  mov     [rbp+8A0h+var_914], r14d
0x180043666  mov     [rbp+8A0h+pEapError], r14
0x18004366a  mov     [rbp+8A0h+eapMethodType.eapType.type], r14b
0x18004366e  xor     eax, eax
0x180043670  mov     word ptr [rbp+8A0h+eapMethodType.eapType+1], ax
0x180043674  mov     byte ptr [rbp+8A0h+eapMethodType.eapType+3], al
0x180043677  mov     qword ptr [rbp+8A0h+eapMethodType.eapType.dwVendorId], rax
0x18004367b  mov     [rbp+8A0h+eapMethodType.dwAuthorId], eax
0x18004367e  mov     [rbp+8A0h+var_8E8], r14
0x180043682  mov     [rbp+8A0h+Type], r14d
0x180043686  mov     [rbp+8A0h+var_840], r14d
0x18004368a  xor     edx, edx; Val
0x18004368c  mov     r8d, 7FCh; Size
0x180043692  lea     rcx, [rbp+8A0h+var_83C]; void *
0x180043696  call    memset_0
0x18004369b  mov     [rbp+8A0h+var_870], r14d
0x18004369f  xorps   xmm0, xmm0
0x1800436a2  xor     eax, eax
0x1800436a4  movups  [rbp+8A0h+var_86C], xmm0
0x1800436a8  movups  [rbp+8A0h+var_85C], xmm0
0x1800436ac  mov     [rbp+8A0h+var_84C], eax
0x1800436af  movups  [rbp+8A0h+var_880], xmm0
0x1800436b3  xorps   xmm1, xmm1
0x1800436b6  movdqu  [rbp+8A0h+var_8B0], xmm1
0x1800436bb  mov     [rbp+8A0h+var_8B8], r14
0x1800436bf  movdqu  [rbp+8A0h+var_8A0], xmm0
0x1800436c4  mov     [rbp+8A0h+var_890], r14
0x1800436c8  or      r15d, 0FFFFFFFFh
0x1800436cc  mov     [rbp+8A0h+var_888], r15d
0x1800436d0  mov     [rbp+8A0h+var_884], r14d
0x1800436d4  mov     al, cs:byte_1800AA941
0x1800436da  lea     rbx, [rsi+230h]
0x1800436e1  test    al, 8
0x1800436e3  jz      loc_1800437C4
0x1800436e9  mov     rax, [rbx]
0x1800436ec  mov     [rsp+9A0h+phkResult], rax; void *
0x1800436f1  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800436f8  lea     r8, [rsp+9A0h+var_930]; unsigned int *
0x1800436fd  lea     rdx, aClienteapauthh_9; "ClientEAPAuthHandler::GetIDiPayload"
0x180043704  lea     rcx, [rbp+8A0h+var_8B8]; this
0x180043708  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18004370d  mov     al, cs:byte_1800AA941
0x180043713  test    al, 8
0x180043715  jz      loc_1800437C4
0x18004371b  mov     word ptr [rbp+8A0h+var_870], r14w
0x180043720  lea     rbx, [rsi+230h]
0x180043727  mov     rax, [rbx]
0x18004372a  test    rax, rax
0x18004372d  jz      short loc_180043743
0x18004372f  mov     rax, [rax+70h]
0x180043733  test    rax, rax
0x180043736  jz      short loc_180043743
0x180043738  cmp     [rax+10h], r14
0x18004373c  jz      short loc_180043743
0x18004373e  mov     edx, [rax+10h]
0x180043741  jmp     short loc_180043746
0x180043743  mov     edx, r15d
0x180043746  lea     rcx, [rbp+8A0h+var_870]
0x18004374a  call    ConvertPortNoToString
0x18004374f  mov     al, cs:byte_1800AA941
0x180043755  test    al, 8
0x180043757  jz      short loc_1800437C4
0x180043759  mov     rcx, [rbx]
0x18004375c  lea     rax, [rcx+70h]
0x180043760  test    rcx, rcx
0x180043763  jz      short loc_18004378F
0x180043765  mov     rdx, [rax]
0x180043768  test    rdx, rdx
0x18004376b  jz      short loc_180043776
0x18004376d  lea     rcx, [rdx+0A7Eh]
0x180043774  jmp     short loc_18004377E
0x180043776  test    rcx, rcx
0x180043779  jz      short loc_18004378F
0x18004377b  mov     rcx, r14
0x18004377e  mov     rdx, [rax]
0x180043781  test    rdx, rdx
0x180043784  jz      short loc_180043792
0x180043786  lea     r9, [rdx+848h]
0x18004378d  jmp     short loc_180043796
0x18004378f  mov     rcx, r14
0x180043792  lea     r9, [rbp+8A0h+var_880]
0x180043796  lea     rax, [rbp+8A0h+var_870]
0x18004379a  mov     [rsp+9A0h+lpcbData], rax
0x18004379f  mov     [rsp+9A0h+phkResult], rcx
0x1800437a4  lea     r8, aClienteapauthh_5; "ClientEAPAuthHandler::GetIDiPayload is "...
0x1800437ab  lea     rdx, RasVpnIkeParamTraceInfo
0x1800437b2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800437b9  call    McTemplateU0zjzz_EventWriteTransfer
0x1800437be  mov     al, cs:byte_1800AA941
0x1800437c4  mov     r13, r14
0x1800437c7  mov     r12, r14
0x1800437ca  test    rdi, rdi
0x1800437cd  jnz     loc_1800438CB
0x1800437d3  lea     r14d, [rdi+4]
0x1800437d7  test    r14b, al
0x1800437da  jz      loc_18004387A
0x1800437e0  xor     eax, eax
0x1800437e2  mov     word ptr [rbp+8A0h+var_870], ax
0x1800437e6  mov     rax, [rbx]
0x1800437e9  test    rax, rax
0x1800437ec  jz      short loc_180043802
0x1800437ee  mov     rax, [rax+70h]
0x1800437f2  test    rax, rax
0x1800437f5  jz      short loc_180043802
0x1800437f7  cmp     [rax+10h], r12
0x1800437fb  jz      short loc_180043802
0x1800437fd  mov     edx, [rax+10h]
0x180043800  jmp     short loc_180043805
0x180043802  mov     edx, r15d
0x180043805  lea     rcx, [rbp+8A0h+var_870]
0x180043809  call    ConvertPortNoToString
0x18004380e  test    cs:byte_1800AA941, r14b
0x180043815  jz      short loc_18004387A
0x180043817  mov     rcx, [rbx]
0x18004381a  lea     rax, [rcx+70h]
0x18004381e  test    rcx, rcx
0x180043821  jz      short loc_18004384C
0x180043823  mov     rdx, [rax]
0x180043826  test    rdx, rdx
0x180043829  jz      short loc_180043834
0x18004382b  lea     rcx, [rdx+0A7Eh]
0x180043832  jmp     short loc_18004383B
0x180043834  test    rcx, rcx
0x180043837  jz      short loc_18004384C
0x180043839  xor     ecx, ecx
0x18004383b  mov     rdx, [rax]
0x18004383e  test    rdx, rdx
0x180043841  jz      short loc_18004384E
0x180043843  lea     r9, [rdx+848h]
0x18004384a  jmp     short loc_180043852
0x18004384c  xor     ecx, ecx
0x18004384e  lea     r9, [rbp+8A0h+var_880]
0x180043852  lea     rax, [rbp+8A0h+var_870]
0x180043856  mov     [rsp+9A0h+lpcbData], rax
0x18004385b  mov     [rsp+9A0h+phkResult], rcx
0x180043860  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x180043867  lea     rdx, RasVpnIkeParamTraceError
0x18004386e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180043875  call    McTemplateU0zjzz_EventWriteTransfer
0x18004387a  mov     [rsp+9A0h+var_930], 57h ; 'W'
0x180043882  mov     rcx, cs:WPP_GLOBAL_Control
0x180043889  lea     rbx, WPP_GLOBAL_Control
0x180043890  cmp     rcx, rbx
0x180043893  jz      loc_18004484B
0x180043899  test    byte ptr [rcx+1Ch], 1
0x18004389d  jz      loc_18004484B
0x1800438a3  cmp     byte ptr [rcx+19h], 2
0x1800438a7  jb      loc_18004484B
0x1800438ad  mov     edx, 4Ch ; 'L'
0x1800438b2  lea     r9d, [rdx+0Bh]
0x1800438b6  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x1800438bd  mov     rcx, [rcx+10h]
0x1800438c1  call    WPP_SF_d
0x1800438c6  jmp     loc_18004484B
0x1800438cb  lea     rax, [rbp+8A0h+hKey]
0x1800438cf  mov     [rsp+9A0h+phkResult], rax; phkResult
0x1800438d4  mov     r9d, 1; samDesired
0x1800438da  xor     r8d, r8d; ulOptions
0x1800438dd  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x1800438e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800438eb  call    cs:__imp_RegOpenKeyExA
0x1800438f1  mov     [rsp+9A0h+var_930], eax
0x1800438f5  test    eax, eax
0x1800438f7  jz      loc_1800439E9
0x1800438fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180043904  lea     rdx, WPP_GLOBAL_Control
0x18004390b  cmp     rcx, rdx
0x18004390e  jz      short loc_180043934
0x180043910  test    byte ptr [rcx+1Ch], 1
0x180043914  jz      short loc_180043934
0x180043916  cmp     byte ptr [rcx+19h], 2
0x18004391a  jb      short loc_180043934
0x18004391c  mov     edx, 4Dh ; 'M'
0x180043921  mov     r9d, eax
0x180043924  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x18004392b  mov     rcx, [rcx+10h]
0x18004392f  call    WPP_SF_d
0x180043934  mov     r14d, 4
0x18004393a  test    cs:byte_1800AA941, r14b
0x180043941  jz      loc_18004484B
0x180043947  xor     eax, eax
0x180043949  mov     word ptr [rbp+8A0h+var_840], ax
0x18004394d  mov     word ptr [rbp+8A0h+var_870], ax
0x180043951  mov     rax, [rbx]
0x180043954  test    rax, rax
0x180043957  jz      short loc_18004396D
0x180043959  mov     rax, [rax+70h]
0x18004395d  test    rax, rax
0x180043960  jz      short loc_18004396D
0x180043962  cmp     [rax+10h], r12
0x180043966  jz      short loc_18004396D
0x180043968  mov     edx, [rax+10h]
0x18004396b  jmp     short loc_180043970
0x18004396d  mov     edx, r15d
0x180043970  lea     rcx, [rbp+8A0h+var_870]
0x180043974  call    ConvertPortNoToString
0x180043979  mov     r9d, [rsp+9A0h+var_930]
0x18004397e  lea     r8, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x180043985  lea     rdx, aClienteapauthh_6; "ClientEAPAuthHandler::GetIDiPayload: Re"...
0x18004398c  lea     rcx, [rbp+8A0h+var_840]
0x180043990  call    FormatRRASErrorString
0x180043995  test    cs:byte_1800AA941, r14b
0x18004399c  jz      loc_18004484B
0x1800439a2  mov     rcx, [rbx]
0x1800439a5  lea     rax, [rcx+70h]
0x1800439a9  test    rcx, rcx
0x1800439ac  jz      short loc_1800439D7
0x1800439ae  mov     rdx, [rax]
0x1800439b1  test    rdx, rdx
0x1800439b4  jz      short loc_1800439BF
0x1800439b6  lea     rcx, [rdx+0A7Eh]
0x1800439bd  jmp     short loc_1800439C6
0x1800439bf  test    rcx, rcx
0x1800439c2  jz      short loc_1800439D7
0x1800439c4  xor     ecx, ecx
0x1800439c6  mov     rdx, [rax]
0x1800439c9  test    rdx, rdx
0x1800439cc  jz      short loc_1800439D9
0x1800439ce  lea     r9, [rdx+848h]
0x1800439d5  jmp     short loc_1800439DD
0x1800439d7  xor     ecx, ecx
0x1800439d9  lea     r9, [rbp+8A0h+var_880]
0x1800439dd  lea     rdx, RasVpnIkeParamTraceError
0x1800439e4  jmp     loc_18004482D
0x1800439e9  mov     r14d, 4
0x1800439ef  mov     [rbp+8A0h+cbData], r14d
0x1800439f3  lea     rax, [rbp+8A0h+cbData]
0x1800439f7  mov     [rsp+9A0h+lpcbData], rax; lpcbData
0x1800439fc  lea     rax, [rbp+8A0h+Data]
0x180043a00  mov     [rsp+9A0h+phkResult], rax; lpData
0x180043a05  lea     r9, [rbp+8A0h+Type]; lpType
0x180043a09  xor     r8d, r8d; lpReserved
0x180043a0c  lea     rdx, aExtendedidisup; "ExtendedIDiSupport"
0x180043a13  mov     rcx, [rbp+8A0h+hKey]; hKey
0x180043a17  call    cs:__imp_RegQueryValueExA
0x180043a1d  mov     [rsp+9A0h+var_930], eax
0x180043a21  test    eax, eax
0x180043a23  jz      short loc_180043A5D
0x180043a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a2c  lea     rbx, WPP_GLOBAL_Control
0x180043a33  cmp     rcx, rbx
0x180043a36  jz      short loc_180043A64
0x180043a38  test    byte ptr [rcx+1Ch], 1
0x180043a3c  jz      short loc_180043A64
0x180043a3e  cmp     byte ptr [rcx+19h], 2
0x180043a42  jb      short loc_180043A64
0x180043a44  lea     edx, [r14+4Ah]
0x180043a48  mov     r9d, eax
0x180043a4b  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x180043a52  mov     rcx, [rcx+10h]
0x180043a56  call    WPP_SF_d
0x180043a5b  jmp     short loc_180043A64
0x180043a5d  lea     rbx, WPP_GLOBAL_Control
0x180043a64  cmp     [rsp+9A0h+var_930], r12d
0x180043a69  jnz     loc_180044784
0x180043a6f  cmp     [rbp+8A0h+Type], r14d
0x180043a73  jnz     loc_180044784
0x180043a79  cmp     dword ptr [rbp+8A0h+Data], r12d
0x180043a7d  jz      loc_180044784
0x180043a83  mov     rcx, [rbp+8A0h+hKey]; hKey
0x180043a87  call    cs:__imp_RegCloseKey
0x180043a8d  mov     [rbp+8A0h+hKey], r12
0x180043a91  cmp     [rsi+238h], r12b
  ... truncated ...
```
