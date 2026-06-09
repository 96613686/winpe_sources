# CWinBioSrvIdentify::Identify(std::shared_ptr<CBiometricUnit> &,_WINBIO_IDENTITY *,uchar *,ulong *,uchar * *,unsigned __int64 *,uchar * *,unsigned __int64 *,std::vector<uchar,wil::secure_allocator<uchar>> *,std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>> *)

- ea: `0x18004ac70`
- end: `0x18004b7e6`
- name: `?Identify@CWinBioSrvIdentify@@CAJAEAV?$shared_ptr@VCBiometricUnit@@@std@@PEAU_WINBIO_IDENTITY@@PEAEPEAKPEAPEAEPEA_K45PEAV?$vector@EU?$secure_allocator@E@wil@@@3@PEAV?$unique_ptr@U_WINBIO_RPC_NGC_AUTHORIZATION@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@3@@Z`
- size: `2934`
- prototype: `__int64 __fastcall(CBiometricUnit **, struct _WINBIO_IDENTITY *, UCHAR *, unsigned __int64, PUCHAR *, ULONG_PTR *, PUCHAR *, ULONG_PTR *, char, __int64)`
- caller_count: `1`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004a2f0`

## callees

- `0x1800058ec`
- `0x18001434c`
- `0x180014854`
- `0x18001ca14`
- `0x180023d88`
- `0x1800278f8`
- `0x180032f34`
- `0x180033798`
- `0x180035eec`
- `0x180038dd0`
- `0x18003a12c`
- `0x18003ddf8`
- `0x18003de18`
- `0x18003f2dc`
- `0x18003f5c4`
- `0x180043744`
- `0x18004ac70`
- `0x18005388c`
- `0x180055878`
- `0x1800559c8`
- `0x18005d544`
- `0x18005e1cc`
- `0x18005ef0c`
- `0x18005f4e8`
- `0x18005fd74`
- `0x180068f60`
- `0x18006e4c4`
- `0x180072d58`
- `0x18007bffc`
- `0x1800811f8`
- `0x18008e094`
- `0x1800914c4`
- `0x1800917d4`
- `0x180091adc`
- `0x180091c64`
- `0x1800b5604`
- `0x1800b5720`
- `0x1800bb15c`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ad01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ae5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004aeda`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b3a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b437`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b54c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b5aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ad01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ae5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004aeda`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b3a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b437`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b54c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b5aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004b6f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004b748`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004b6f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004b748`

## string_xrefs

- `0x18004ae19`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004aeff`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b075`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b132`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b203`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b315`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b426`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b4da`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b5cb`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b648`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b763`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18004b01f`: `WinBioIdentify::WbioStorageDeleteRecord`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CWinBioSrvIdentify::Identify(
        CBiometricUnit **a1,
        struct _WINBIO_IDENTITY *a2,
        UCHAR *a3,
        unsigned __int64 a4,
        PUCHAR *a5,
        ULONG_PTR *a6,
        PUCHAR *a7,
        ULONG_PTR *a8,
        char a9,
        __int64 a10)
{
  ULONG *RejectDetail; // r14
  __int64 v14; // rcx
  int IdentificationNonce; // esi
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64, LPWSTR, unsigned __int64, struct _WINBIO_IDENTITY *); // rax
  int v19; // eax
  unsigned int v20; // esi
  int v21; // esi
  struct _WINBIO_PIPELINE *v22; // r14
  HRESULT v23; // eax
  unsigned int v24; // esi
  __int64 v25; // rdx
  int AuthorizationNonce; // edi
  int v27; // edi
  int v28; // eax
  unsigned int v29; // esi
  int v30; // esi
  int v31; // r15d
  __int64 v32; // r14
  __int64 v33; // r12
  int v34; // eax
  int v35; // esi
  int v36; // eax
  unsigned int v37; // edi
  unsigned int v38; // esi
  int v39; // eax
  unsigned int v40; // edi
  void *v41; // rdx
  unsigned int v42; // r8d
  const char *v43; // r9
  struct CBioTraceLogging *v44; // rbx
  __int64 v45; // rax
  int PayloadBlobSize; // [rsp+20h] [rbp-378h]
  int PayloadBlobSizea; // [rsp+20h] [rbp-378h]
  PSIZE_T PayloadBlobSizeb; // [rsp+20h] [rbp-378h]
  char *v49; // [rsp+50h] [rbp-348h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-340h] BYREF
  unsigned int v51[2]; // [rsp+60h] [rbp-338h] BYREF
  PSIZE_T HashSize; // [rsp+68h] [rbp-330h] BYREF
  PUCHAR *PayloadBlob; // [rsp+70h] [rbp-328h] BYREF
  char *v54; // [rsp+78h] [rbp-320h] BYREF
  PSIZE_T v55; // [rsp+80h] [rbp-318h] BYREF
  PWINBIO_BIOMETRIC_SUBTYPE SubFactor; // [rsp+88h] [rbp-310h] BYREF
  PUCHAR *HashValue; // [rsp+90h] [rbp-308h] BYREF
  ULONGLONG v58; // [rsp+98h] [rbp-300h] BYREF
  ULONGLONG v59; // [rsp+A0h] [rbp-2F8h] BYREF
  void *v60; // [rsp+A8h] [rbp-2F0h] BYREF
  void *v61; // [rsp+B0h] [rbp-2E8h]
  unsigned __int64 p_PayloadBlob; // [rsp+B8h] [rbp-2E0h] BYREF
  char v63; // [rsp+C0h] [rbp-2D8h]
  _QWORD v64[6]; // [rsp+C8h] [rbp-2D0h] BYREF
  char v65; // [rsp+F8h] [rbp-2A0h]
  __int128 v66; // [rsp+100h] [rbp-298h] BYREF
  __int64 v67; // [rsp+110h] [rbp-288h]
  ULONGLONG TickCount64; // [rsp+118h] [rbp-280h] BYREF
  struct _WINBIO_RPC_NGC_AUTHORIZATION *v69[2]; // [rsp+120h] [rbp-278h] BYREF
  __int64 v70; // [rsp+130h] [rbp-268h]
  _BYTE v71[360]; // [rsp+140h] [rbp-258h] BYREF
  HRESULT v72; // [rsp+2A8h] [rbp-F0h]
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  RejectDetail = (ULONG *)a4;
  p_PayloadBlob = a4;
  SubFactor = a3;
  PayloadBlob = a5;
  v55 = a6;
  HashValue = a7;
  HashSize = a8;
  LODWORD(v49) = 0;
  TickCount64 = GetTickCount64();
  v58 = 0;
  v59 = 0;
  LODWORD(v54) = 0;
  v64[0] = a1;
  v64[1] = &v49;
  v64[2] = &v54;
  v64[3] = &TickCount64;
  v64[4] = &v59;
  v64[5] = &v58;
  v65 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    *((_DWORD *)CBioTraceLogging::Instance() + 36) = *((_DWORD *)*a1 + 20);
  if ( !CBiometricUnit::SupportsSecureConnection(*a1) )
  {
    *(_OWORD *)v69 = 0;
    v70 = 0;
    v66 = 0;
    v67 = 0;
    v28 = CBiometricUnit::OpenHmacSession(v14, v69, &v66);
    v29 = v28;
    LODWORD(v49) = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D2,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
        (const char *)(unsigned int)v28,
        PayloadBlobSize);
      std::vector<unsigned char>::_Tidy(&v66);
      std::vector<unsigned char>::_Tidy(v69);
      v65 = 0;
      lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
      return v29;
    }
    v30 = (int)v69[1];
    v31 = (int)v69[0];
    if ( v69[0] != v69[1] )
    {
      v32 = *((_QWORD *)&v66 + 1);
      v33 = v66;
      if ( (_QWORD)v66 != *((_QWORD *)&v66 + 1) )
      {
        HashSize = 0;
        HashValue = 0;
        v58 = GetTickCount64();
        v34 = WbioEngineIdentifyFeatureSetSecure(
                (unsigned int)*((_QWORD *)*a1 + 338) + 16,
                v31,
                v30 - v31,
                v33,
                v32 - v33,
                (__int64)a2,
                (__int64)SubFactor,
                p_PayloadBlob,
                (__int64)&HashSize,
                (__int64)&HashValue);
        v35 = v34;
        LODWORD(v49) = v34;
        if ( v34 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2E4,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
            (const char *)(unsigned int)v34,
            (int)PayloadBlobSizeb);
        v59 = GetTickCount64();
        if ( v35 == -2146860974 )
        {
          CBiometricUnit::ReProvisionAuthValue(*a1);
LABEL_36:
          std::vector<unsigned char>::_Tidy(&v66);
          std::vector<unsigned char>::_Tidy(v69);
          v65 = 0;
          lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
          return (unsigned int)v35;
        }
        if ( v35 < 0 )
          goto LABEL_36;
        v60 = HashSize;
        v61 = HashValue;
        if ( a2->Type == 3 )
        {
          v36 = CBiometricUnit::Authorize((unsigned int)*a1, (_DWORD)a2, (_DWORD)HashSize, (_DWORD)HashValue, a9);
          v37 = v36;
          LODWORD(v49) = v36;
          if ( v36 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2FA,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
              (const char *)(unsigned int)v36,
              (int)PayloadBlobSizeb);
            __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
            std::vector<unsigned char>::_Tidy(&v66);
            std::vector<unsigned char>::_Tidy(v69);
            v65 = 0;
            lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
            return v37;
          }
        }
        __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
LABEL_47:
        std::vector<unsigned char>::_Tidy(&v66);
        std::vector<unsigned char>::_Tidy(v69);
        goto LABEL_48;
      }
      RejectDetail = (ULONG *)p_PayloadBlob;
    }
    v58 = GetTickCount64();
    LODWORD(v49) = WbioEngineIdentifyFeatureSet(
                     (PWINBIO_PIPELINE)(*((_QWORD *)*a1 + 338) + 16LL),
                     a2,
                     SubFactor,
                     PayloadBlob,
                     v55,
                     HashValue,
                     HashSize,
                     RejectDetail);
    v59 = GetTickCount64();
    v38 = (unsigned int)v49;
    if ( (int)v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30A,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
        (const char *)(unsigned int)v49,
        (int)PayloadBlobSizeb);
      std::vector<unsigned char>::_Tidy(&v66);
      std::vector<unsigned char>::_Tidy(v69);
      v65 = 0;
      lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
      return v38;
    }
    if ( a2->Type == 3 )
    {
      v39 = CBiometricUnit::Authorize((unsigned int)*a1, (_DWORD)a2, 0, 0, a9);
      v40 = v39;
      LODWORD(v49) = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x312,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
          (const char *)(unsigned int)v39,
          (int)PayloadBlobSizeb);
        std::vector<unsigned char>::_Tidy(&v66);
        std::vector<unsigned char>::_Tidy(v69);
        v65 = 0;
        lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
        return v40;
      }
    }
    goto LABEL_47;
  }
  StringSid = 0;
  p_PayloadBlob = 0;
  v69[0] = (struct _WINBIO_RPC_NGC_AUTHORIZATION *)&StringSid;
  v69[1] = 0;
  LOBYTE(v70) = 1;
  IdentificationNonce = BioIsoGetIdentificationNonce(
                          *(void **)(v14 + 2920),
                          (unsigned __int8 **)&v69[1],
                          &p_PayloadBlob);
  LODWORD(v49) = IdentificationNonce;
  wil::details::out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>(v69);
  if ( IdentificationNonce < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x274,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
      (const char *)(unsigned int)IdentificationNonce,
      PayloadBlobSize);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&StringSid);
    v65 = 0;
    lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
    return (unsigned int)IdentificationNonce;
  }
  HashValue = 0;
  HashSize = 0;
  v58 = GetTickCount64();
  if ( *((_QWORD *)*a1 + 338) == -16 || (v17 = *(_QWORD *)(*((_QWORD *)*a1 + 338) + 48LL)) == 0 )
  {
    v19 = -2147467261;
  }
  else
  {
    v18 = *(__int64 (__fastcall **)(__int64, LPWSTR, unsigned __int64, struct _WINBIO_IDENTITY *))(v17 + 352);
    if ( v18 )
    {
      PayloadBlobSize = (int)a3;
      v19 = v18(*((_QWORD *)*a1 + 338) + 16LL, StringSid, p_PayloadBlob, a2);
    }
    else
    {
      v19 = -2147467263;
    }
  }
  LODWORD(v54) = v19;
  v59 = GetTickCount64();
  v20 = (unsigned int)v54;
  LODWORD(v49) = (_DWORD)v54;
  if ( (int)v54 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
      (const char *)(unsigned int)v54,
      PayloadBlobSize);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&StringSid);
    v65 = 0;
    lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
    return v20;
  }
  v60 = HashValue;
  v61 = HashSize;
  PayloadBlob = 0;
  v21 = BioIsoAuthenticateIdentification(
          *((void **)*a1 + 365),
          (void **)&PayloadBlob,
          (const unsigned __int8 *)StringSid,
          p_PayloadBlob,
          a2,
          (unsigned __int8 *)HashValue,
          (unsigned __int64)HashSize);
  LODWORD(v49) = v21;
  if ( v21 == -2146861025 )
  {
    v22 = (struct _WINBIO_PIPELINE *)(*((_QWORD *)*a1 + 338) + 16LL);
    if ( *((_QWORD *)*a1 + 338) != -16 )
    {
      CEtwEvent::CEtwEvent((CEtwEvent *)v71);
      CEtwEvent::CaptureSensorInfo((CEtwEvent *)v71, *a1);
      CEtwEvent::CaptureIdentityInfo((CEtwEvent *)v71, a2);
      v23 = WbioStorageDeleteRecord(v22, a2, *a3);
      v24 = v23;
      if ( v23 >= 0 )
      {
        v25 = 1015;
        LODWORD(v49) = -2146861053;
      }
      else
      {
        v72 = v23;
        v25 = 1014;
      }
      CEtwEvent::Write(v71, v25, 3);
      std::wstring::wstring(v69, L"WinBioIdentify::WbioStorageDeleteRecord");
      CBioTraceLogging::OnDeleteTemplate(v24, a1, v69);
      std::wstring::_Tidy_deallocate(v69);
      CEtwEvent::~CEtwEvent((CEtwEvent *)v71);
      v21 = (int)v49;
    }
  }
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
      (const char *)(unsigned int)v21,
      PayloadBlobSizea);
    __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&StringSid);
    v65 = 0;
    lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
    return (unsigned int)v21;
  }
  p_PayloadBlob = (unsigned __int64)&PayloadBlob;
  v63 = 1;
  v55 = 0;
  v51[0] = 0;
  v69[0] = (struct _WINBIO_RPC_NGC_AUTHORIZATION *)&v55;
  v69[1] = 0;
  LOBYTE(v70) = 1;
  AuthorizationNonce = NgcSecureBioGetAuthorizationNonce((unsigned __int8 **)&v69[1], v51);
  LODWORD(v49) = AuthorizationNonce;
  wil::details::out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>(v69);
  if ( AuthorizationNonce < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BF,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
      (const char *)(unsigned int)AuthorizationNonce,
      PayloadBlobSizea);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v55);
    BioIsoCloseKeyAuthorizationSession((void **)&PayloadBlob);
    __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&StringSid);
    v65 = 0;
    lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
    return (unsigned int)AuthorizationNonce;
  }
  SubFactor = 0;
  v69[0] = (struct _WINBIO_RPC_NGC_AUTHORIZATION *)&SubFactor;
  v69[1] = 0;
  LOBYTE(v70) = 1;
  PayloadBlobSizeb = (PSIZE_T)&v69[1];
  v27 = BioIsoAuthorizeKeyRelease(PayloadBlob, (const unsigned __int8 *)v55, v51[0], a2);
  LODWORD(v49) = v27;
  wil::details::out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>(v69);
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
      (const char *)(unsigned int)v27,
      (int)&v69[1]);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&SubFactor);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v55);
    BioIsoCloseKeyAuthorizationSession((void **)&PayloadBlob);
    __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&StringSid);
    v65 = 0;
    lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
    return (unsigned int)v27;
  }
  wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(a10, &SubFactor);
  std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&SubFactor);
  std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v55);
  BioIsoCloseKeyAuthorizationSession((void **)&PayloadBlob);
  __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
  std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&StringSid);
LABEL_48:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl)
    || a2->Type != 3 )
  {
    goto LABEL_57;
  }
  StringSid = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HandleUserSidRetrievalFailure>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_HandleUserSidRetrievalFailure>::GetImpl'::`2'::impl) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( !ConvertSidToStringSidW(a2->Value.AccountSid.Data, &StringSid) )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x325,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
        (const char *)1,
        (unsigned int)PayloadBlobSizeb);
    goto LABEL_55;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(a2->Value.AccountSid.Data, &StringSid) )
  {
LABEL_55:
    v44 = CBioTraceLogging::Instance();
    v45 = std::wstring::wstring(v69, StringSid);
    CBioTraceLogging::SetCurrentUserSid(v44, v45);
    goto LABEL_56;
  }
  wil::details::in1diag3::_Log_GetLastError(retaddr, v41, v42, v43);
LABEL_56:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
LABEL_57:
  v65 = 0;
  lambda_c9b04caa0fa38c0ee4922c4d98fbd795_::operator()(v64);
  return 0;
}

```

## disassembly

```asm
0x18004ac70  push    rbx
0x18004ac72  push    rsi
0x18004ac73  push    rdi
0x18004ac74  push    r12
0x18004ac76  push    r13
0x18004ac78  push    r14
0x18004ac7a  push    r15
0x18004ac7c  sub     rsp, 360h
0x18004ac83  mov     rax, cs:__security_cookie
0x18004ac8a  xor     rax, rsp
0x18004ac8d  mov     [rsp+398h+var_48], rax
0x18004ac95  mov     r14, r9
0x18004ac98  mov     [rsp+398h+var_2E0], r9
0x18004aca0  mov     r15, r8
0x18004aca3  mov     [rsp+398h+SubFactor], r8
0x18004acab  mov     rbx, rdx
0x18004acae  mov     rdi, rcx
0x18004acb1  mov     rax, [rsp+398h+arg_20]
0x18004acb9  mov     [rsp+398h+PayloadBlob], rax
0x18004acbe  mov     rax, [rsp+398h+arg_28]
0x18004acc6  mov     [rsp+398h+var_318], rax
0x18004acce  mov     rax, [rsp+398h+arg_30]
0x18004acd6  mov     [rsp+398h+var_308], rax
0x18004acde  mov     rax, [rsp+398h+arg_38]
0x18004ace6  mov     [rsp+398h+var_330], rax
0x18004aceb  mov     r13, qword ptr [rsp+398h+arg_40]
0x18004acf3  mov     r12, [rsp+398h+arg_48]
0x18004acfb  xor     esi, esi
0x18004acfd  mov     dword ptr [rsp+398h+var_348], esi
0x18004ad01  call    cs:__imp_GetTickCount64
0x18004ad07  mov     [rsp+398h+var_280], rax
0x18004ad0f  mov     [rsp+398h+var_300], rsi
0x18004ad17  mov     [rsp+398h+var_2F8], rsi
0x18004ad1f  mov     dword ptr [rsp+398h+var_320], esi
0x18004ad23  mov     [rsp+398h+var_2D0], rdi
0x18004ad2b  lea     rax, [rsp+398h+var_348]
0x18004ad30  mov     [rsp+398h+var_2C8], rax
0x18004ad38  lea     rax, [rsp+398h+var_320]
0x18004ad3d  mov     [rsp+398h+var_2C0], rax
0x18004ad45  lea     rax, [rsp+398h+var_280]
0x18004ad4d  mov     [rsp+398h+var_2B8], rax
0x18004ad55  lea     rax, [rsp+398h+var_2F8]
0x18004ad5d  mov     [rsp+398h+var_2B0], rax
0x18004ad65  lea     rax, [rsp+398h+var_300]
0x18004ad6d  mov     [rsp+398h+var_2A8], rax
0x18004ad75  mov     [rsp+398h+var_2A0], 1
0x18004ad7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x18004ad84  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18004ad89  test    al, al
0x18004ad8b  jz      short loc_18004AD9E
0x18004ad8d  call    ?Instance@CBioTraceLogging@@SAAEAV1@XZ; CBioTraceLogging::Instance(void)
0x18004ad92  mov     rcx, [rdi]
0x18004ad95  mov     edx, [rcx+50h]
0x18004ad98  mov     [rax+90h], edx
0x18004ad9e  mov     rcx, [rdi]; this
0x18004ada1  call    ?SupportsSecureConnection@CBiometricUnit@@QEBA_NXZ; CBiometricUnit::SupportsSecureConnection(void)
0x18004ada6  test    al, al
0x18004ada8  jz      loc_18004B2C6
0x18004adae  xor     r13d, r13d
0x18004adb1  mov     [rsp+398h+StringSid], r13
0x18004adb6  mov     [rsp+398h+var_2E0], r13
0x18004adbe  lea     rax, [rsp+398h+StringSid]
0x18004adc3  mov     [rsp+398h+var_278], rax
0x18004adcb  mov     [rsp+398h+var_278+8], r13
0x18004add3  mov     byte ptr [rsp+398h+var_268], 1
0x18004addb  lea     r8, [rsp+398h+var_2E0]; unsigned __int64 *
0x18004ade3  lea     rdx, [rsp+398h+var_278+8]; unsigned __int8 **
0x18004adeb  mov     rcx, [rcx+0B68h]; void *
0x18004adf2  call    ?BioIsoGetIdentificationNonce@@YAJPEAXPEAPEAEPEA_K@Z; BioIsoGetIdentificationNonce(void *,uchar * *,unsigned __int64 *)
0x18004adf7  mov     esi, eax
0x18004adf9  mov     dword ptr [rsp+398h+var_348], eax
0x18004adfd  lea     rcx, [rsp+398h+var_278]
0x18004ae05  call    ??1?$out_param_t@V?$unique_ptr@U_WINBIO_RPC_NGC_AUTHORIZATION@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>::~out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>(void)
0x18004ae0a  test    esi, esi
0x18004ae0c  jns     short loc_18004AE52
0x18004ae0e  mov     rcx, [rsp+398h]; this
0x18004ae16  mov     r9d, esi; char *
0x18004ae19  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\biometrics\\serv"...
0x18004ae20  mov     edx, 274h; void *
0x18004ae25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ae2a  nop
0x18004ae2b  lea     rcx, [rsp+398h+StringSid]
0x18004ae30  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004ae35  nop
0x18004ae36  mov     [rsp+398h+var_2A0], r13b
0x18004ae3e  lea     rcx, [rsp+398h+var_2D0]
0x18004ae46  call    _lambda_c9b04caa0fa38c0ee4922c4d98fbd795___operator__
0x18004ae4b  mov     eax, esi
0x18004ae4d  jmp     loc_18004B7C2
0x18004ae52  mov     [rsp+398h+var_308], r13
0x18004ae5a  mov     [rsp+398h+var_330], r13
0x18004ae5f  call    cs:__imp_GetTickCount64
0x18004ae65  mov     [rsp+398h+var_300], rax
0x18004ae6d  mov     rax, [rdi]
0x18004ae70  mov     rcx, [rax+0A90h]
0x18004ae77  add     rcx, 10h
0x18004ae7b  jz      short loc_18004AED1
0x18004ae7d  mov     rax, [rcx+20h]
0x18004ae81  test    rax, rax
0x18004ae84  jz      short loc_18004AED1
0x18004ae86  mov     rax, [rax+160h]
0x18004ae8d  test    rax, rax
0x18004ae90  jnz     short loc_18004AE99
0x18004ae92  mov     eax, 80004001h
0x18004ae97  jmp     short loc_18004AED6
0x18004ae99  lea     rdx, [rsp+398h+var_330]
0x18004ae9e  mov     [rsp+398h+RejectDetail], rdx
0x18004aea3  lea     rdx, [rsp+398h+var_308]
0x18004aeab  mov     [rsp+398h+HashSize], rdx
0x18004aeb0  mov     [rsp+398h+HashValue], r14
0x18004aeb5  mov     [rsp+398h+PayloadBlobSize], r15
0x18004aeba  mov     r9, rbx
0x18004aebd  mov     r8, [rsp+398h+var_2E0]
0x18004aec5  mov     rdx, [rsp+398h+StringSid]
0x18004aeca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aecf  jmp     short loc_18004AED6
0x18004aed1  mov     eax, 80004003h
0x18004aed6  mov     dword ptr [rsp+398h+var_320], eax
0x18004aeda  call    cs:__imp_GetTickCount64
0x18004aee0  mov     [rsp+398h+var_2F8], rax
0x18004aee8  mov     esi, dword ptr [rsp+398h+var_320]
0x18004aeec  mov     dword ptr [rsp+398h+var_348], esi
0x18004aef0  test    esi, esi
0x18004aef2  jns     short loc_18004AF38
0x18004aef4  mov     rcx, [rsp+398h]; this
0x18004aefc  mov     r9d, esi; char *
0x18004aeff  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\biometrics\\serv"...
0x18004af06  mov     edx, 283h; void *
0x18004af0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004af10  nop
0x18004af11  lea     rcx, [rsp+398h+StringSid]
0x18004af16  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004af1b  nop
0x18004af1c  mov     [rsp+398h+var_2A0], r13b
0x18004af24  lea     rcx, [rsp+398h+var_2D0]
0x18004af2c  call    _lambda_c9b04caa0fa38c0ee4922c4d98fbd795___operator__
0x18004af31  mov     eax, esi
0x18004af33  jmp     loc_18004B7C2
0x18004af38  mov     rdx, [rsp+398h+var_308]
0x18004af40  mov     rax, [rsp+398h+var_330]
0x18004af45  mov     [rsp+398h+var_2F0], rdx
0x18004af4d  mov     [rsp+398h+var_2E8], rax
0x18004af55  mov     [rsp+398h+PayloadBlob], r13
0x18004af5a  mov     rcx, [rdi]
0x18004af5d  mov     [rsp+398h+HashSize], rax; unsigned __int64
0x18004af62  mov     [rsp+398h+HashValue], rdx; unsigned __int8 *
0x18004af67  mov     [rsp+398h+PayloadBlobSize], rbx; int
0x18004af6c  mov     r9, [rsp+398h+var_2E0]; unsigned __int64
0x18004af74  mov     r8, [rsp+398h+StringSid]; unsigned __int8 *
0x18004af79  lea     rdx, [rsp+398h+PayloadBlob]; void **
0x18004af7e  mov     rcx, [rcx+0B68h]; void *
0x18004af85  call    ?BioIsoAuthenticateIdentification@@YAJPEAXPEAPEAXPEBE_KPEAU_WINBIO_IDENTITY@@PEAE3@Z; BioIsoAuthenticateIdentification(void *,void * *,uchar const *,unsigned __int64,_WINBIO_IDENTITY *,uchar *,unsigned __int64)
0x18004af8a  mov     esi, eax
0x18004af8c  mov     dword ptr [rsp+398h+var_348], eax
0x18004af90  cmp     eax, 8009801Fh
0x18004af95  jnz     loc_18004B066
0x18004af9b  mov     rax, [rdi]
0x18004af9e  mov     r14, [rax+0A90h]
0x18004afa5  add     r14, 10h
0x18004afa9  jz      loc_18004B066
0x18004afaf  lea     rcx, [rsp+398h+var_258]; this
0x18004afb7  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x18004afbc  nop
0x18004afbd  mov     rdx, [rdi]; struct CBiometricUnit *
0x18004afc0  lea     rcx, [rsp+398h+var_258]; this
0x18004afc8  call    ?CaptureSensorInfo@CEtwEvent@@QEAAXPEAVCBiometricUnit@@@Z; CEtwEvent::CaptureSensorInfo(CBiometricUnit *)
0x18004afcd  mov     rdx, rbx; struct _WINBIO_IDENTITY *
0x18004afd0  lea     rcx, [rsp+398h+var_258]; this
0x18004afd8  call    ?CaptureIdentityInfo@CEtwEvent@@QEAAXPEAU_WINBIO_IDENTITY@@@Z; CEtwEvent::CaptureIdentityInfo(_WINBIO_IDENTITY *)
0x18004afdd  mov     r8b, [r15]; SubFactor
0x18004afe0  mov     rdx, rbx; Identity
0x18004afe3  mov     rcx, r14; Pipeline
0x18004afe6  call    WbioStorageDeleteRecord
0x18004afeb  mov     esi, eax
0x18004afed  test    eax, eax
0x18004afef  jns     short loc_18004AFFF
0x18004aff1  mov     [rsp+398h+var_F0], eax
0x18004aff8  mov     edx, 3F6h
0x18004affd  jmp     short loc_18004B00C
0x18004afff  mov     edx, 3F7h
0x18004b004  mov     dword ptr [rsp+398h+var_348], 80098003h
0x18004b00c  mov     r8d, 3
0x18004b012  lea     rcx, [rsp+398h+var_258]
0x18004b01a  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x18004b01f  lea     rdx, aWinbioidentify; "WinBioIdentify::WbioStorageDeleteRecord"
0x18004b026  lea     rcx, [rsp+398h+var_278]
0x18004b02e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004b033  nop
0x18004b034  lea     r8, [rsp+398h+var_278]
0x18004b03c  mov     rdx, rdi
0x18004b03f  mov     ecx, esi
0x18004b041  call    ?OnDeleteTemplate@CBioTraceLogging@@SAXJAEAV?$shared_ptr@VCBiometricUnit@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; CBioTraceLogging::OnDeleteTemplate(long,std::shared_ptr<CBiometricUnit> &,std::wstring const &)
0x18004b046  nop
0x18004b047  lea     rcx, [rsp+398h+var_278]
0x18004b04f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b054  nop
0x18004b055  lea     rcx, [rsp+398h+var_258]; this
0x18004b05d  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18004b062  mov     esi, dword ptr [rsp+398h+var_348]
0x18004b066  test    esi, esi
0x18004b068  jns     short loc_18004B0BC
0x18004b06a  mov     rcx, [rsp+398h]; this
0x18004b072  mov     r9d, esi; char *
0x18004b075  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\biometrics\\serv"...
0x18004b07c  mov     edx, 2B4h; void *
0x18004b081  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b086  nop
0x18004b087  lea     rcx, [rsp+398h+var_2F0]
0x18004b08f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004b094  nop
0x18004b095  lea     rcx, [rsp+398h+StringSid]
0x18004b09a  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004b09f  nop
0x18004b0a0  mov     [rsp+398h+var_2A0], r13b
0x18004b0a8  lea     rcx, [rsp+398h+var_2D0]
0x18004b0b0  call    _lambda_c9b04caa0fa38c0ee4922c4d98fbd795___operator__
0x18004b0b5  mov     eax, esi
0x18004b0b7  jmp     loc_18004B7C2
0x18004b0bc  lea     rax, [rsp+398h+PayloadBlob]
0x18004b0c1  mov     [rsp+398h+var_2E0], rax
0x18004b0c9  mov     [rsp+398h+var_2D8], 1
0x18004b0d1  mov     [rsp+398h+var_318], r13
0x18004b0d9  mov     [rsp+398h+var_338], r13d
0x18004b0de  lea     rax, [rsp+398h+var_318]
0x18004b0e6  mov     [rsp+398h+var_278], rax
0x18004b0ee  mov     [rsp+398h+var_278+8], r13
0x18004b0f6  mov     byte ptr [rsp+398h+var_268], 1
0x18004b0fe  lea     rdx, [rsp+398h+var_338]; unsigned int *
0x18004b103  lea     rcx, [rsp+398h+var_278+8]; unsigned __int8 **
0x18004b10b  call    ?NgcSecureBioGetAuthorizationNonce@@YAJPEAPEAEPEAK@Z; NgcSecureBioGetAuthorizationNonce(uchar * *,ulong *)
0x18004b110  mov     edi, eax
0x18004b112  mov     dword ptr [rsp+398h+var_348], eax
0x18004b116  lea     rcx, [rsp+398h+var_278]
0x18004b11e  call    ??1?$out_param_t@V?$unique_ptr@U_WINBIO_RPC_NGC_AUTHORIZATION@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>::~out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>(void)
0x18004b123  test    edi, edi
0x18004b125  jns     short loc_18004B192
0x18004b127  mov     rcx, [rsp+398h]; this
0x18004b12f  mov     r9d, edi; char *
0x18004b132  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\biometrics\\serv"...
0x18004b139  mov     edx, 2BFh; void *
0x18004b13e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b143  nop
0x18004b144  lea     rcx, [rsp+398h+var_318]
0x18004b14c  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004b151  nop
0x18004b152  lea     rcx, [rsp+398h+PayloadBlob]; void **
0x18004b157  call    ?BioIsoCloseKeyAuthorizationSession@@YAJPEAPEAX@Z; BioIsoCloseKeyAuthorizationSession(void * *)
0x18004b15c  nop
0x18004b15d  lea     rcx, [rsp+398h+var_2F0]
0x18004b165  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004b16a  nop
0x18004b16b  lea     rcx, [rsp+398h+StringSid]
0x18004b170  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004b175  nop
0x18004b176  mov     [rsp+398h+var_2A0], r13b
0x18004b17e  lea     rcx, [rsp+398h+var_2D0]
0x18004b186  call    _lambda_c9b04caa0fa38c0ee4922c4d98fbd795___operator__
0x18004b18b  mov     eax, edi
0x18004b18d  jmp     loc_18004B7C2
0x18004b192  mov     [rsp+398h+SubFactor], r13
0x18004b19a  lea     rax, [rsp+398h+SubFactor]
0x18004b1a2  mov     [rsp+398h+var_278], rax
0x18004b1aa  mov     [rsp+398h+var_278+8], r13
0x18004b1b2  mov     byte ptr [rsp+398h+var_268], 1
0x18004b1ba  mov     r8d, [rsp+398h+var_338]; unsigned __int64
0x18004b1bf  lea     rax, [rsp+398h+var_278+8]
0x18004b1c7  mov     [rsp+398h+PayloadBlobSize], rax; int
0x18004b1cc  mov     r9, rbx; struct _WINBIO_IDENTITY *
0x18004b1cf  mov     rdx, [rsp+398h+var_318]; unsigned __int8 *
0x18004b1d7  mov     rcx, [rsp+398h+PayloadBlob]; void *
0x18004b1dc  call    ?BioIsoAuthorizeKeyRelease@@YAJPEAXPEBE_KQEAU_WINBIO_IDENTITY@@PEAPEAU_WINBIO_RPC_NGC_AUTHORIZATION@@@Z; BioIsoAuthorizeKeyRelease(void *,uchar const *,unsigned __int64,_WINBIO_IDENTITY * const,_WINBIO_RPC_NGC_AUTHORIZATION * *)
0x18004b1e1  mov     edi, eax
0x18004b1e3  mov     dword ptr [rsp+398h+var_348], eax
0x18004b1e7  lea     rcx, [rsp+398h+var_278]
0x18004b1ef  call    ??1?$out_param_t@V?$unique_ptr@U_WINBIO_RPC_NGC_AUTHORIZATION@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>::~out_param_t<std::unique_ptr<_WINBIO_RPC_NGC_AUTHORIZATION,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>(void)
0x18004b1f4  test    edi, edi
0x18004b1f6  jns     short loc_18004B271
0x18004b1f8  mov     rcx, [rsp+398h]; this
0x18004b200  mov     r9d, edi; char *
0x18004b203  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\biometrics\\serv"...
0x18004b20a  mov     edx, 2C7h; void *
0x18004b20f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b214  nop
0x18004b215  lea     rcx, [rsp+398h+SubFactor]
0x18004b21d  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004b222  nop
0x18004b223  lea     rcx, [rsp+398h+var_318]
0x18004b22b  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004b230  nop
0x18004b231  lea     rcx, [rsp+398h+PayloadBlob]; void **
0x18004b236  call    ?BioIsoCloseKeyAuthorizationSession@@YAJPEAPEAX@Z; BioIsoCloseKeyAuthorizationSession(void * *)
0x18004b23b  nop
0x18004b23c  lea     rcx, [rsp+398h+var_2F0]
0x18004b244  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004b249  nop
0x18004b24a  lea     rcx, [rsp+398h+StringSid]
0x18004b24f  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004b254  nop
0x18004b255  mov     [rsp+398h+var_2A0], r13b
0x18004b25d  lea     rcx, [rsp+398h+var_2D0]
  ... truncated ...
```
