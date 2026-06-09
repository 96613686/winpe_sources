# CWinBioSrvEnrollCommit::Execute(std::shared_ptr<CBiometricUnit> &,thread_inside_functions const &)

- ea: `0x18008f340`
- end: `0x180090131`
- name: `?Execute@CWinBioSrvEnrollCommit@@UEAA?AW4_EXECUTE_STATUS@CAsyncWorkItem@@AEAV?$shared_ptr@VCBiometricUnit@@@std@@AEBVthread_inside_functions@@@Z`
- size: `3569`
- prototype: `__int64 __fastcall(CAsyncWorkItem *this, struct CBiometricUnit **, __int128 *)`
- caller_count: `0`
- callee_count: `56`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800023fc`
- `0x1800058ec`
- `0x18000b760`
- `0x18000eed0`
- `0x18000f090`
- `0x1800118d4`
- `0x18001434c`
- `0x18001ade0`
- `0x18001ca14`
- `0x18001e5c0`
- `0x180021db4`
- `0x18002269c`
- `0x180023b10`
- `0x180023d88`
- `0x180028478`
- `0x1800288b4`
- `0x1800297e0`
- `0x18002d258`
- `0x180032f34`
- `0x180033798`
- `0x18003ddf8`
- `0x18003e014`
- `0x18003f2dc`
- `0x18003f5c4`
- `0x180043744`
- `0x180043d50`
- `0x180046664`
- `0x180054720`
- `0x180055878`
- `0x1800559c8`
- `0x18006561c`
- `0x180068f60`
- `0x180069cc8`
- `0x18006e4c4`
- `0x180072410`
- `0x18007f574`
- `0x1800813bc`
- `0x18008c160`
- `0x18008df08`
- `0x18008e270`
- `0x18008f340`
- `0x180091360`
- `0x1800914c4`
- `0x180091adc`
- `0x180091be4`
- `0x180091c30`
- `0x180091c94`
- `0x180094450`
- `0x18009448c`
- `0x1800944c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fcf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fcf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fdff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fdff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18008fcd6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18008fcd6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008fced`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008fced`
- `RPCRT4!UuidCreate` at `0x18008f99a`
- `RPCRT4!UuidCreate` at `0x18008f99a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18008fd3c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18008fd3c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18008fd48`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18008fd48`

## string_xrefs

- `0x18008f7e3`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18008f8c1`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18008fb4d`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18008fbe8`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18008fd93`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18008fdc7`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18008fe73`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18008fed5`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x18008f3a4`: `CWinBioSrvEnrollCommit::Execute`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWinBioSrvEnrollCommit::Execute(CAsyncWorkItem *this, struct CBiometricUnit **a2, __int128 *a3)
{
  CClientSession *v6; // r14
  bool v7; // bl
  char *v8; // r15
  int v9; // ebx
  Binding *v10; // rdi
  __int64 v11; // r8
  struct _WINBIO_PIPELINE *v12; // r13
  PWINBIO_ENGINE_INTERFACE EngineInterface; // rax
  __int64 (__fastcall *CheckForDuplicate)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  __int64 v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  __int64 v17; // r8
  const unsigned __int8 *v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  int v21; // ebx
  WINBIO_IDENTITY *p_Identity; // r15
  unsigned __int8 v23; // al
  PWINBIO_ENGINE_INTERFACE v24; // rax
  __int64 (__fastcall *GetEnrollmentHash)(struct _WINBIO_PIPELINE *, unsigned __int8 **, struct _FILETIME *); // rax
  unsigned __int64 v26; // rbx
  unsigned __int8 *v27; // rdi
  unsigned __int8 v28; // al
  SIZE_T Data1; // rbx
  UCHAR *v30; // rdi
  WINBIO_BIOMETRIC_SUBTYPE v31; // al
  __int64 v32; // rdx
  int v33; // eax
  WINBIO_BIOMETRIC_SUBTYPE v34; // al
  int v35; // eax
  int v36; // r8d
  int v37; // r9d
  signed int LastError; // eax
  unsigned __int64 v39; // rdi
  int v40; // r15d
  DWORD active; // eax
  int v42; // eax
  int v43; // eax
  struct CBioTraceLogging *v44; // rbx
  __int64 v45; // rax
  int v46; // eax
  _OWORD *v47; // rax
  int updated; // eax
  __int64 v49; // rdx
  __int64 v50; // r8
  Binding **v51; // rax
  char v52; // di
  int v53; // ebx
  struct _SYSTEMTIME *PayloadBlobSize; // [rsp+20h] [rbp-E0h]
  int ActiveDatabase; // [rsp+50h] [rbp-B0h] BYREF
  bool v57; // [rsp+54h] [rbp-ACh] BYREF
  char v58; // [rsp+55h] [rbp-ABh] BYREF
  char v59; // [rsp+56h] [rbp-AAh] BYREF
  char v60; // [rsp+57h] [rbp-A9h] BYREF
  char v61[8]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 *v62; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME FileTime; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v64; // [rsp+70h] [rbp-90h] BYREF
  Binding *v65; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v66; // [rsp+80h] [rbp-80h]
  void *phToken; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v68[3]; // [rsp+90h] [rbp-70h] BYREF
  char v69; // [rsp+A8h] [rbp-58h]
  int v70; // [rsp+B0h] [rbp-50h] BYREF
  int v71; // [rsp+B4h] [rbp-4Ch]
  CClientSession *v72; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base *v73; // [rsp+C0h] [rbp-40h]
  _QWORD v74[3]; // [rsp+C8h] [rbp-38h] BYREF
  char v75[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v76; // [rsp+100h] [rbp+0h]
  __int128 v77; // [rsp+110h] [rbp+10h]
  __int128 v78; // [rsp+120h] [rbp+20h]
  __int128 v79; // [rsp+130h] [rbp+30h]
  __int128 v80; // [rsp+140h] [rbp+40h]
  __int128 v81; // [rsp+150h] [rbp+50h]
  __int128 v82; // [rsp+160h] [rbp+60h]
  __int128 v83; // [rsp+170h] [rbp+70h]
  UUID Uuid; // [rsp+180h] [rbp+80h] BYREF
  struct _WINBIO_IDENTITY v85; // [rsp+190h] [rbp+90h] BYREF
  WINBIO_IDENTITY Identity; // [rsp+1E0h] [rbp+E0h] BYREF
  int v87; // [rsp+230h] [rbp+130h] BYREF
  UUID v88; // [rsp+234h] [rbp+134h]
  _BYTE v89[80]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v90[360]; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v91; // [rsp+438h] [rbp+338h]
  struct _SYSTEMTIME SystemTime; // [rsp+4E0h] [rbp+3E0h] BYREF
  char v93[32]; // [rsp+500h] [rbp+400h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  v71 = 0;
  ActiveDatabase = 0;
  v58 = 0;
  v68[0] = a2;
  v68[1] = &ActiveDatabase;
  v68[2] = &v58;
  v69 = 1;
  v70 = 0;
  strcpy(v93, "CWinBioSrvEnrollCommit::Execute");
  v74[0] = v93;
  v74[1] = &v70;
  v74[2] = &ActiveDatabase;
  lambda_ba70c506923d725df71d3a84c5f14ef8_::operator()(v74);
  v70 = 1;
  v64 = v74;
  memset_0(&v85, 0, sizeof(v85));
  memset_0(&v87, 0, 0x4Cu);
  memset_0(&Identity, 0, sizeof(Identity));
  memset_0(v89, 0, 0x4Cu);
  v60 = 0;
  v59 = 0;
  CEtwEvent::CEtwEvent((CEtwEvent *)v90);
  v76 = *a3;
  v77 = a3[1];
  v78 = a3[2];
  v79 = a3[3];
  v80 = a3[4];
  v81 = a3[5];
  v82 = a3[6];
  v83 = a3[7];
  std::weak_ptr<CBiometricUnit>::lock((char *)this + 8, &v72);
  v6 = v72;
  if ( !v72 || (_m_prefetchw((char *)v72 + 200), _InterlockedOr((volatile signed __int32 *)v72 + 50, 0)) )
  {
    CAsyncWorkItem::CompleteRequest(this, -2146861052);
    if ( v73 )
      std::_Ref_count_base::_Decref(v73);
LABEL_138:
    CEtwEvent::~CEtwEvent((CEtwEvent *)v90);
    WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____::_WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____(&v64);
    if ( v69 )
    {
      v69 = 0;
      goto LABEL_140;
    }
    return 0;
  }
  if ( BindingHelper::IsLocked((CClientSession *)((char *)v6 + 16))
    || BindingHelper::IsLocked((struct CBiometricUnit *)((char *)*a2 + 16)) )
  {
    CAsyncWorkItem::CompleteRequest(this, -2146861014);
    if ( v73 )
      std::_Ref_count_base::_Decref(v73);
    goto LABEL_138;
  }
  v7 = 0;
  if ( BindingHelper::IsEnrolling((CClientSession *)((char *)v6 + 16))
    && BindingHelper::IsEnrolling((struct CBiometricUnit *)((char *)*a2 + 16)) )
  {
    v8 = (char *)v6 + 16;
    (*(void (__fastcall **)(__int64, Binding **))(*((_QWORD *)v6 + 2) + 8LL))((__int64)v6 + 16, &v65);
    if ( v65 )
    {
      v9 = *((_DWORD *)*a2 + 20);
      if ( Binding::UnitId(v65) != v9 )
      {
        CAsyncWorkItem::CompleteRequest(this, -2146861012);
        if ( v66 )
          std::_Ref_count_base::_Decref(v66);
        if ( v73 )
          std::_Ref_count_base::_Decref(v73);
        goto LABEL_13;
      }
      v7 = 0;
    }
    if ( v66 )
      std::_Ref_count_base::_Decref(v66);
    v58 = *((_BYTE *)v6 + 208);
    CClientSession::ParentSensorPool(v6, &v65);
    v10 = v65;
    if ( !v65 )
    {
      CAsyncWorkItem::CompleteRequest(this, -2146861052);
      if ( v66 )
        std::_Ref_count_base::_Decref(v66);
      if ( v73 )
        std::_Ref_count_base::_Decref(v73);
      goto LABEL_23;
    }
    if ( (unsigned __int8)IsRequestCancelled(_InterlockedCompareExchange64((volatile signed __int64 *)this + 6, 0, 0)) )
    {
      CAsyncWorkItem::CompleteRequest(this, -2146861052);
      if ( v66 )
        std::_Ref_count_base::_Decref(v66);
      if ( v73 )
        std::_Ref_count_base::_Decref(v73);
      goto LABEL_23;
    }
    v12 = (struct _WINBIO_PIPELINE *)(*((_QWORD *)*a2 + 338) + 16LL);
    if ( *((_QWORD *)*a2 + 338) == -16 )
    {
      CAsyncWorkItem::CompleteRequest(this, -2147023537);
      if ( v66 )
        std::_Ref_count_base::_Decref(v66);
      if ( v73 )
        std::_Ref_count_base::_Decref(v73);
      goto LABEL_23;
    }
    if ( (Microsoft_Windows_BiometricsEnableBits & 8) != 0 )
    {
      PayloadBlobSize = &SystemTime;
      McGenEventWrite_EventWriteTransfer(&WBIOSRVC_PROVIDER_Context, WbioSrvcPerfEnrollCommitStart, v11, 1);
    }
    CEtwEvent::CaptureSensorInfo((CEtwEvent *)v90, *a2);
    CEtwEvent::CaptureConfigurationInfo((CEtwEvent *)v90, *a2);
    if ( !v58 )
    {
      EngineInterface = v12->EngineInterface;
      if ( !EngineInterface )
      {
        ActiveDatabase = -2147467261;
        goto LABEL_112;
      }
      CheckForDuplicate = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))EngineInterface->CheckForDuplicate;
      if ( !CheckForDuplicate )
      {
        ActiveDatabase = -2147467263;
        goto LABEL_111;
      }
      ActiveDatabase = CheckForDuplicate(v12, v89, &v60, &v59);
      if ( ActiveDatabase < 0 )
        goto LABEL_112;
    }
    if ( *((_DWORD *)v10 + 8) == 1 )
    {
      if ( !v59 )
      {
        if ( CBiometricUnit::SupportsSecureConnection(*a2) )
        {
          std::vector<unsigned char>::vector<unsigned char>(&SystemTime, (char *)v16 + 2936);
          v17 = *(_QWORD *)&SystemTime.wHour;
          v18 = *(const unsigned __int8 **)&SystemTime.wYear;
          if ( *(_QWORD *)&SystemTime.wYear == *(_QWORD *)&SystemTime.wHour )
          {
            ActiveDatabase = wil::details::in1diag3::Log_Hr(
                               retaddr,
                               (void *)0x86A,
                               (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
                               (const char *)0x8000FFFFLL,
                               (int)PayloadBlobSize);
            std::vector<unsigned char>::_Tidy(&SystemTime);
LABEL_107:
            CEtwEvent::CaptureIdentityInfo((CEtwEvent *)v90, (struct _WINBIO_IDENTITY *)((char *)v6 + 48));
            if ( ActiveDatabase >= 0 )
            {
              v49 = 1010;
            }
            else
            {
              v91 = ActiveDatabase;
              v49 = 1009;
            }
            CEtwEvent::Write(v90, v49, 3);
LABEL_111:
            if ( ActiveDatabase >= 0 )
            {
LABEL_113:
              CClientSession::ClearEnrollmentAuthorizationParameters(v6);
LABEL_114:
              CClientSession::ClearEnrollmentParameters(v6);
              CClientSession::ReleaseBinding(v6);
              if ( ActiveDatabase >= 0 && BindingHelper::IsAuthorizing((CClientSession *)((char *)v6 + 16)) )
              {
                v51 = (Binding **)(*(__int64 (__fastcall **)(char *, struct _SYSTEMTIME *))(*(_QWORD *)v8 + 8LL))(
                                    v8,
                                    &SystemTime);
                v52 = 1;
                v53 = *((_DWORD *)*a2 + 20);
                v7 = Binding::UnitId(*v51) == v53;
              }
              else
              {
                v52 = v71;
              }
              if ( (v52 & 1) != 0 && *(_QWORD *)&SystemTime.wHour )
                std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&SystemTime.wHour);
              if ( v7 )
                CClientSession::ReleaseBinding(v6);
              if ( (Microsoft_Windows_BiometricsEnableBits & 8) != 0 )
                McGenEventWrite_EventWriteTransfer(&WBIOSRVC_PROVIDER_Context, WbioSrvcPerfEnrollCommitStop, v50, 1);
              CAsyncWorkItem::CompleteRequest(this, ActiveDatabase);
              if ( v66 )
                std::_Ref_count_base::_Decref(v66);
              if ( v73 )
                std::_Ref_count_base::_Decref(v73);
LABEL_13:
              CEtwEvent::~CEtwEvent((CEtwEvent *)v90);
              WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____::_WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____(&v64);
              if ( v69 )
              {
                v69 = 0;
LABEL_140:
                lambda_cbedcef8ec9af1b827fb16d5b7cf8ad6_::operator()(v68);
                return 0;
              }
              return 0;
            }
LABEL_112:
            memset_0(*((void **)this + 11), 0, 0x4Cu);
            **((_DWORD **)this + 11) = 0;
            **((_BYTE **)this + 12) = 0;
            if ( ActiveDatabase < 0 )
              goto LABEL_114;
            goto LABEL_113;
          }
          v19 = *((_QWORD *)*a2 + 367);
          if ( v19 != *((_QWORD *)*a2 + 368) )
            *((_QWORD *)*a2 + 368) = v19;
          *(_OWORD *)&Identity.Type = *((_OWORD *)v6 + 3);
          *(_OWORD *)&Identity.Value.AccountSid.Data[8] = *((_OWORD *)v6 + 4);
          *(_OWORD *)&Identity.Value.AccountSid.Data[24] = *((_OWORD *)v6 + 5);
          *(_OWORD *)&Identity.Value.AccountSid.Data[40] = *((_OWORD *)v6 + 6);
          *(_OWORD *)&Identity.Value.AccountSid.Data[52] = *(_OWORD *)((char *)v6 + 108);
          *(_OWORD *)&v85.Type = *(_OWORD *)&Identity.Type;
          *(_OWORD *)&v85.Value.AccountSid.Data[8] = *(_OWORD *)&Identity.Value.AccountSid.Data[8];
          *(_OWORD *)&v85.Value.AccountSid.Data[24] = *(_OWORD *)&Identity.Value.AccountSid.Data[24];
          *(_OWORD *)&v85.Value.AccountSid.Data[40] = *(_OWORD *)&Identity.Value.AccountSid.Data[40];
          *(_OWORD *)&v85.Value.AccountSid.Data[52] = *(_OWORD *)&Identity.Value.AccountSid.Data[52];
          v20 = BioIsoAuthenticateEnrollmentIdentity(*((void **)*a2 + 365), v18, v17 - (_QWORD)v18, &Identity);
          v21 = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x87A,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
              (const char *)(unsigned int)v20,
              (int)PayloadBlobSize);
            ActiveDatabase = v21;
            std::vector<unsigned char>::_Tidy(&SystemTime);
            v7 = 0;
            goto LABEL_107;
          }
          ActiveDatabase = v20;
          p_Identity = &Identity;
          **((_BYTE **)this + 12) = 1;
          std::vector<unsigned char>::_Tidy(&SystemTime);
          v7 = 0;
        }
        else
        {
          p_Identity = (WINBIO_IDENTITY *)((char *)v6 + 48);
          *(_OWORD *)&v85.Type = *((_OWORD *)v6 + 3);
          *(_OWORD *)&v85.Value.AccountSid.Data[8] = *((_OWORD *)v6 + 4);
          *(_OWORD *)&v85.Value.AccountSid.Data[24] = *((_OWORD *)v6 + 5);
          *(_OWORD *)&v85.Value.AccountSid.Data[40] = *((_OWORD *)v6 + 6);
          *(_OWORD *)&v85.Value.AccountSid.Data[52] = *(_OWORD *)((char *)v6 + 108);
          **((_BYTE **)this + 12) = 1;
        }
LABEL_62:
        if ( **((_BYTE **)this + 12) )
        {
          FileTime = 0;
          ActiveDatabase = CBiometricUnit::GetActiveDatabase(*a2, (struct CTemplateDatabase **)&FileTime);
          if ( ActiveDatabase >= 0 )
          {
            if ( (*(_DWORD *)(*(_QWORD *)&FileTime + 64LL) & 0x10000) != 0 )
            {
              Uuid.Data1 = 0;
              *(_QWORD *)Uuid.Data4 = 0;
              v62 = 0;
              FileTime = 0;
              v24 = v12->EngineInterface;
              if ( v24 )
              {
                GetEnrollmentHash = (__int64 (__fastcall *)(struct _WINBIO_PIPELINE *, unsigned __int8 **, struct _FILETIME *))v24->GetEnrollmentHash;
                if ( GetEnrollmentHash )
                {
                  ActiveDatabase = GetEnrollmentHash(v12, &v62, &FileTime);
                  if ( ActiveDatabase >= 0 )
                  {
                    v26 = (unsigned __int64)FileTime;
                    v27 = v62;
                    v28 = CClientSession::EnrollmentSubFactor(v6);
                    ActiveDatabase = CStorageAuthenticator::Encode((DATA_BLOB *)&Uuid, p_Identity, v28, v27, v26);
                    v7 = 0;
                    if ( ActiveDatabase >= 0 )
                    {
                      Data1 = Uuid.Data1;
                      v30 = *(UCHAR **)Uuid.Data4;
                      v31 = CClientSession::EnrollmentSubFactor(v6);
                      ActiveDatabase = WbioEngineCommitEnrollment(v12, p_Identity, v31, v30, Data1);
                      v7 = 0;
                      if ( ActiveDatabase >= 0 )
                      {
                        LOBYTE(v32) = 1;
                        WbioStorageNotifyDatabaseChange(v12, v32);
                        WbioEngineRefreshCache(v12);
                        if ( CHardwareManager::IsVirtualSecureModeAvailable() )
                        {
                          SystemTime = *(struct _SYSTEMTIME *)&xmmword_1800DF158;
                          v33 = StorageManagerExport((struct _GUID *)&SystemTime);
                          if ( v33 < 0 )
                            wil::details::in1diag3::_Log_Hr(
                              retaddr,
                              (void *)0x8EB,
                              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
                              (const char *)(unsigned int)v33,
                              (int)PayloadBlobSize);
                        }
                      }
                    }
                    v10 = v65;
                  }
                }
                else
                {
                  ActiveDatabase = -2147467263;
                }
              }
              else
              {
                ActiveDatabase = -2147467261;
              }
              CStorageAuthenticator::~CStorageAuthenticator((CStorageAuthenticator *)&Uuid);
            }
            else
            {
              v34 = CClientSession::EnrollmentSubFactor(v6);
              ActiveDatabase = WbioEngineCommitEnrollment(v12, p_Identity, v34, 0, 0);
              if ( ActiveDatabase >= 0 )
              {
                LOBYTE(v15) = 1;
                WbioStorageNotifyDatabaseChange(v12, v15);
                WbioEngineRefreshCache(v12);
                if ( CHardwareManager::IsVirtualSecureModeAvailable() )
                {
                  SystemTime = *(struct _SYSTEMTIME *)&xmmword_1800DF158;
                  v35 = StorageManagerExport((struct _GUID *)&SystemTime);
                  v16 = retaddr;
                  if ( v35 < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x905,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
                      (const char *)(unsigned int)v35,
                      (int)PayloadBlobSize);
                }
              }
            }
          }
        }
        if ( ActiveDatabase < 0 )
          goto LABEL_106;
        if ( *((_DWORD *)v10 + 8) != 1 )
        {
LABEL_104:
          v47 = (_OWORD *)*((_QWORD *)this + 11);
          *v47 = *(_OWORD *)&v85.Type;
          v47[1] = *(_OWORD *)&v85.Value.AccountSid.Data[8];
          v47[2] = *(_OWORD *)&v85.Value.AccountSid.Data[24];
          v47[3] = *(_OWORD *)&v85.Value.AccountSid.Data[40];
          *(_OWORD *)((char *)v47 + 60) = *(_OWORD *)&v85.Value.AccountSid.Data[52];
          updated = UpdateBioEnrollmentRegKey(v16);
          if ( updated < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x961,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
              (const char *)(unsigned int)updated,
              (int)PayloadBlobSize);
LABEL_106:
          v8 = (char *)v6 + 16;
          goto LABEL_107;
        }
        LOBYTE(v15) = 1;
        CBioTraceLogging::OnEnrollmentEnd(a2, v15);
        v57 = 0;
        ActiveDatabase = CAccountManager::SetEnrolledFactorState(
                           &v85,
                           *((_DWORD *)*a2 + 22),
                           *((_DWORD *)*a2 + 745),
                           1,
                           &v57);
        if ( ActiveDatabase < 0 )
        {
          if ( (unsigned int)dword_18010F170 > 2 )
          {
            v61[0] = 1;
            *(_QWORD *)&Uuid.Data1 = v85.Value.AccountSid.Data;
            LODWORD(phToken) = *((_DWORD *)*a2 + 22);
            LODWORD(v62) = ActiveDatabase;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
              (_DWORD)phToken,
              (unsigned int)byte_1800EF573,
              v36,
              v37,
              (__int64)&v62,
              (__int64)&phToken,
              (__int64)&Uuid,
              (__int64)v61,
              (__int64)&v57);
          }
          ActiveDatabase = 0;
        }
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        FileTime = 0;
        if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          ActiveDatabase = LastError;
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
        {
LABEL_101:
          ActiveDatabase = CAccountManager::SetBioEnrolledTime(&v85, FileTime);
          v46 = CAccountManager::SetLastBioUseTime(&v85, FileTime, 1);
          ActiveDatabase = v46;
          v16 = retaddr;
          if ( v46 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x954,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
              (const char *)(unsigned int)v46,
              (int)PayloadBlobSize);
          ActiveDatabase = 0;
          goto LABEL_104;
        }
        v39 = (unsigned __int64)FileTime;
        v40 = *((_DWORD *)*a2 + 20);
        phToken = 0;
        active = WTSGetActiveConsoleSessionId();
        if ( !WTSQueryUserToken(active, &phToken) )
        {
LABEL_100:
          *((_DWORD *)CBioTraceLogging::Instance() + 36) = v40;
          CBioTraceLogging::SendTelemetry(ActiveDatabase, 0, 8, 2u, v39, 0);
          goto LABEL_101;
        }
        v62 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HandleUserSidRetrievalFailure>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_HandleUserSidRetrievalFailure>::GetImpl'::`2'::impl) )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v62,
            0);
          v42 = SHGetUserSid(phToken, &v62);
          if ( v42 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x940,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
              (const char *)(unsigned int)v42,
              (int)PayloadBlobSize);
LABEL_99:
            CloseHandle(phToken);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v62);
            goto LABEL_100;
          }
        }
        else
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v62,
            0);
          v43 = SHGetUserSid(phToken, &v62);
          if ( v43 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x947,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
              (const char *)(unsigned int)v43,
              (int)PayloadBlobSize);
        }
        v44 = CBioTraceLogging::Instance();
        v45 = std::wstring::wstring(v75, v62);
        CBioTraceLogging::SetCurrentUserSid(v44, v45);
        v7 = 0;
        goto LABEL_99;
      }
LABEL_59:
      ActiveDatabase = -2146861013;
      goto LABEL_107;
    }
    if ( v59 )
    {
      v23 = CClientSession::EnrollmentSubFactor(v6);
      if ( v23 != v60 )
        goto LABEL_59;
      p_Identity = (WINBIO_IDENTITY *)v89;
      **((_BYTE **)this + 12) = 0;
    }
    else
    {
      Uuid = 0;
      UuidCreate(&Uuid);
      v87 = 2;
      v88 = Uuid;
      p_Identity = (WINBIO_IDENTITY *)&v87;
      **((_BYTE **)this + 12) = 1;
    }
    *(_OWORD *)&v85.Type = *(_OWORD *)&p_Identity->Type;
    *(_OWORD *)&v85.Value.AccountSid.Data[8] = *(_OWORD *)&p_Identity->Value.AccountSid.Data[8];
    *(_OWORD *)&v85.Value.AccountSid.Data[24] = *(_OWORD *)&p_Identity->Value.AccountSid.Data[24];
    *(_OWORD *)&v85.Value.AccountSid.Data[40] = *(_OWORD *)&p_Identity->Value.AccountSid.Data[40];
    *(_OWORD *)&v85.Value.AccountSid.Data[52] = *(_OWORD *)&p_Identity->Value.AccountSid.Data[52];
    goto LABEL_62;
  }
  CAsyncWorkItem::CompleteRequest(this, -2146861012);
  if ( v73 )
    std::_Ref_count_base::_Decref(v73);
LABEL_23:
  CEtwEvent::~CEtwEvent((CEtwEvent *)v90);
  WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____::_WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____(&v64);
  if ( v69 )
  {
    v69 = 0;
    goto LABEL_140;
  }
  return 0;
}

```

## disassembly

```asm
0x18008f340  mov     [rsp-8+arg_10], rbx
0x18008f345  push    rbp
0x18008f346  push    rsi
0x18008f347  push    rdi
0x18008f348  push    r12
0x18008f34a  push    r13
0x18008f34c  push    r14
0x18008f34e  push    r15
0x18008f350  lea     rbp, [rsp-430h]
0x18008f358  sub     rsp, 530h
0x18008f35f  mov     rax, cs:__security_cookie
0x18008f366  xor     rax, rsp
0x18008f369  mov     [rbp+460h+var_40], rax
0x18008f370  mov     rbx, r8
0x18008f373  mov     r12, rdx
0x18008f376  mov     rsi, rcx
0x18008f379  xor     edi, edi
0x18008f37b  mov     [rbp+460h+var_4AC], edi
0x18008f37e  mov     [rsp+560h+var_510], edi
0x18008f382  mov     [rsp+560h+var_50B], dil
0x18008f387  mov     [rbp+460h+var_4D0], rdx
0x18008f38b  lea     rax, [rsp+560h+var_510]
0x18008f390  mov     [rbp+460h+var_4C8], rax
0x18008f394  lea     rax, [rsp+560h+var_50B]
0x18008f399  mov     [rbp+460h+var_4C0], rax
0x18008f39d  mov     [rbp+460h+var_4B8], 1
0x18008f3a1  mov     [rbp+460h+var_4B0], edi
0x18008f3a4  movups  xmm0, xmmword ptr cs:aCwinbiosrvenro_12; "CWinBioSrvEnrollCommit::Execute"
0x18008f3ab  movups  xmmword ptr [rbp+460h+var_60], xmm0
0x18008f3b2  movups  xmm1, xmmword ptr cs:aCwinbiosrvenro_12+10h; "Commit::Execute"
0x18008f3b9  movups  xmmword ptr [rbp+460h+var_60+10h], xmm1
0x18008f3c0  lea     rax, [rbp+460h+var_60]
0x18008f3c7  mov     [rbp+460h+var_498], rax
0x18008f3cb  lea     rax, [rbp+460h+var_4B0]
0x18008f3cf  mov     [rbp+460h+var_490], rax
0x18008f3d3  lea     rax, [rsp+560h+var_510]
0x18008f3d8  mov     [rbp+460h+var_488], rax
0x18008f3dc  lea     rcx, [rbp+460h+var_498]
0x18008f3e0  call    _lambda_ba70c506923d725df71d3a84c5f14ef8___operator__
0x18008f3e5  mov     [rbp+460h+var_4B0], 1
0x18008f3ec  lea     rax, [rbp+460h+var_498]
0x18008f3f0  mov     [rsp+560h+var_4F0], rax
0x18008f3f5  lea     r14d, [rdi+4Ch]
0x18008f3f9  mov     r8d, r14d; Size
0x18008f3fc  xor     edx, edx; Val
0x18008f3fe  lea     rcx, [rbp+460h+var_3D0]; void *
0x18008f405  call    memset_0
0x18008f40a  mov     r8d, r14d; Size
0x18008f40d  xor     edx, edx; Val
0x18008f40f  lea     rcx, [rbp+460h+var_330]; void *
0x18008f416  call    memset_0
0x18008f41b  mov     r8d, r14d; Size
0x18008f41e  xor     edx, edx; Val
0x18008f420  lea     rcx, [rbp+460h+Identity]; void *
0x18008f427  call    memset_0
0x18008f42c  mov     r8d, r14d; Size
0x18008f42f  xor     edx, edx; Val
0x18008f431  lea     rcx, [rbp+460h+var_2E0]; void *
0x18008f438  call    memset_0
0x18008f43d  mov     [rsp+560h+var_509], dil
0x18008f442  mov     [rsp+560h+var_50A], dil
0x18008f447  lea     rcx, [rbp+460h+var_290]; this
0x18008f44e  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x18008f453  nop
0x18008f454  movups  xmm0, xmmword ptr [rbx]
0x18008f457  movups  [rbp+460h+var_460], xmm0
0x18008f45b  movups  xmm1, xmmword ptr [rbx+10h]
0x18008f45f  movups  [rbp+460h+var_450], xmm1
0x18008f463  movups  xmm0, xmmword ptr [rbx+20h]
0x18008f467  movups  [rbp+460h+var_440], xmm0
0x18008f46b  movups  xmm1, xmmword ptr [rbx+30h]
0x18008f46f  movups  [rbp+460h+var_430], xmm1
0x18008f473  movups  xmm0, xmmword ptr [rbx+40h]
0x18008f477  movups  [rbp+460h+var_420], xmm0
0x18008f47b  movups  xmm1, xmmword ptr [rbx+50h]
0x18008f47f  movups  [rbp+460h+var_410], xmm1
0x18008f483  movups  xmm0, xmmword ptr [rbx+60h]
0x18008f487  movups  [rbp+460h+var_400], xmm0
0x18008f48b  movups  xmm1, xmmword ptr [rbx+70h]
0x18008f48f  movups  [rbp+460h+var_3F0], xmm1
0x18008f493  lea     rcx, [rsi+8]
0x18008f497  lea     rdx, [rbp+460h+var_4A8]
0x18008f49b  call    ?lock@?$weak_ptr@VCBiometricUnit@@@std@@QEBA?AV?$shared_ptr@VCBiometricUnit@@@2@XZ; std::weak_ptr<CBiometricUnit>::lock(void)
0x18008f4a0  nop
0x18008f4a1  mov     r14, [rbp+460h+var_4A8]
0x18008f4a5  test    r14, r14
0x18008f4a8  jz      loc_1800900BC
0x18008f4ae  prefetchw byte ptr [r14+0C8h]
0x18008f4b6  mov     eax, [r14+0C8h]
0x18008f4bd  mov     ecx, eax
0x18008f4bf  or      ecx, edi
0x18008f4c1  lock cmpxchg [r14+0C8h], ecx
0x18008f4ca  jnz     short loc_18008F4BD
0x18008f4cc  test    eax, eax
0x18008f4ce  jnz     loc_1800900BC
0x18008f4d4  lea     rcx, [r14+10h]; this
0x18008f4d8  call    ?IsLocked@BindingHelper@@QEAA_NXZ; BindingHelper::IsLocked(void)
0x18008f4dd  test    al, al
0x18008f4df  jnz     loc_180090085
0x18008f4e5  mov     rcx, [r12]
0x18008f4e9  add     rcx, 10h; this
0x18008f4ed  call    ?IsLocked@BindingHelper@@QEAA_NXZ; BindingHelper::IsLocked(void)
0x18008f4f2  test    al, al
0x18008f4f4  jnz     loc_180090085
0x18008f4fa  lea     rcx, [r14+10h]; this
0x18008f4fe  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x18008f503  xor     ebx, ebx
0x18008f505  test    al, al
0x18008f507  jz      loc_18009004B
0x18008f50d  mov     rcx, [r12]
0x18008f511  add     rcx, 10h; this
0x18008f515  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x18008f51a  test    al, al
0x18008f51c  jz      loc_18009004B
0x18008f522  lea     r15, [r14+10h]
0x18008f526  mov     rax, [r15]
0x18008f529  lea     rdx, [rsp+560h+var_4E8]
0x18008f52e  mov     rcx, r15
0x18008f531  mov     rax, [rax+8]
0x18008f535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f53a  nop
0x18008f53b  mov     rcx, [rsp+560h+var_4E8]; this
0x18008f540  test    rcx, rcx
0x18008f543  jz      short loc_18008F5AE
0x18008f545  mov     rax, [r12]
0x18008f549  mov     ebx, [rax+50h]
0x18008f54c  call    ?UnitId@Binding@@QEBAKXZ; Binding::UnitId(void)
0x18008f551  cmp     eax, ebx
0x18008f553  jz      short loc_18008F5AC
0x18008f555  mov     edx, 8009802Ch; int
0x18008f55a  mov     rcx, rsi; this
0x18008f55d  call    ?CompleteRequest@CAsyncWorkItem@@QEAAJJ@Z; CAsyncWorkItem::CompleteRequest(long)
0x18008f562  nop
0x18008f563  mov     rcx, [rbp+460h+var_4E0]; this
0x18008f567  test    rcx, rcx
0x18008f56a  jz      short loc_18008F572
0x18008f56c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f571  nop
0x18008f572  mov     rcx, [rbp+460h+var_4A0]; this
0x18008f576  test    rcx, rcx
0x18008f579  jz      short loc_18008F581
0x18008f57b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f580  nop
0x18008f581  lea     rcx, [rbp+460h+var_290]; this
0x18008f588  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18008f58d  nop
0x18008f58e  lea     rcx, [rsp+560h+var_4F0]
0x18008f593  call    WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8_______WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____
0x18008f598  nop
0x18008f599  cmp     [rbp+460h+var_4B8], 0
0x18008f59d  jz      loc_180090105
0x18008f5a3  mov     [rbp+460h+var_4B8], 0
0x18008f5a7  jmp     loc_1800900FB
0x18008f5ac  xor     ebx, ebx
0x18008f5ae  mov     rcx, [rbp+460h+var_4E0]; this
0x18008f5b2  test    rcx, rcx
0x18008f5b5  jz      short loc_18008F5BC
0x18008f5b7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f5bc  mov     al, [r14+0D0h]
0x18008f5c3  mov     [rsp+560h+var_50B], al
0x18008f5c7  lea     rdx, [rsp+560h+var_4E8]
0x18008f5cc  mov     rcx, r14
0x18008f5cf  call    ?ParentSensorPool@CClientSession@@QEAA?AV?$shared_ptr@VCSensorPool@@@std@@XZ; CClientSession::ParentSensorPool(void)
0x18008f5d4  nop
0x18008f5d5  mov     rdi, [rsp+560h+var_4E8]
0x18008f5da  test    rdi, rdi
0x18008f5dd  jnz     short loc_18008F634
0x18008f5df  mov     edx, 80098004h; int
0x18008f5e4  mov     rcx, rsi; this
0x18008f5e7  call    ?CompleteRequest@CAsyncWorkItem@@QEAAJJ@Z; CAsyncWorkItem::CompleteRequest(long)
0x18008f5ec  nop
0x18008f5ed  mov     rcx, [rbp+460h+var_4E0]; this
0x18008f5f1  test    rcx, rcx
0x18008f5f4  jz      short loc_18008F5FC
0x18008f5f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f5fb  nop
0x18008f5fc  mov     rcx, [rbp+460h+var_4A0]; this
0x18008f600  test    rcx, rcx
0x18008f603  jz      short loc_18008F60B
0x18008f605  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f60a  nop
0x18008f60b  lea     rcx, [rbp+460h+var_290]; this
0x18008f612  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18008f617  nop
0x18008f618  lea     rcx, [rsp+560h+var_4F0]
0x18008f61d  call    WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8_______WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____
0x18008f622  nop
0x18008f623  cmp     [rbp+460h+var_4B8], bl
0x18008f626  jz      loc_180090105
0x18008f62c  mov     [rbp+460h+var_4B8], bl
0x18008f62f  jmp     loc_1800900FB
0x18008f634  mov     rcx, rbx
0x18008f637  xor     eax, eax
0x18008f639  lock cmpxchg [rsi+30h], rcx
0x18008f63f  mov     rcx, rax
0x18008f642  call    _IsRequestCancelled
0x18008f647  test    al, al
0x18008f649  jz      short loc_18008F691
0x18008f64b  mov     edx, 80098004h; int
0x18008f650  mov     rcx, rsi; this
0x18008f653  call    ?CompleteRequest@CAsyncWorkItem@@QEAAJJ@Z; CAsyncWorkItem::CompleteRequest(long)
0x18008f658  nop
0x18008f659  mov     rcx, [rbp+460h+var_4E0]; this
0x18008f65d  test    rcx, rcx
0x18008f660  jz      short loc_18008F668
0x18008f662  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f667  nop
0x18008f668  mov     rcx, [rbp+460h+var_4A0]; this
0x18008f66c  test    rcx, rcx
0x18008f66f  jz      short loc_18008F677
0x18008f671  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f676  nop
0x18008f677  lea     rcx, [rbp+460h+var_290]; this
0x18008f67e  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18008f683  nop
0x18008f684  lea     rcx, [rsp+560h+var_4F0]
0x18008f689  call    WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8_______WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____
0x18008f68e  nop
0x18008f68f  jmp     short loc_18008F623
0x18008f691  mov     rax, [r12]
0x18008f695  mov     r13, [rax+0A90h]
0x18008f69c  add     r13, 10h
0x18008f6a0  jnz     short loc_18008F6EB
0x18008f6a2  mov     edx, 8007054Fh; int
0x18008f6a7  mov     rcx, rsi; this
0x18008f6aa  call    ?CompleteRequest@CAsyncWorkItem@@QEAAJJ@Z; CAsyncWorkItem::CompleteRequest(long)
0x18008f6af  nop
0x18008f6b0  mov     rcx, [rbp+460h+var_4E0]; this
0x18008f6b4  test    rcx, rcx
0x18008f6b7  jz      short loc_18008F6BF
0x18008f6b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f6be  nop
0x18008f6bf  mov     rcx, [rbp+460h+var_4A0]; this
0x18008f6c3  test    rcx, rcx
0x18008f6c6  jz      short loc_18008F6CE
0x18008f6c8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f6cd  nop
0x18008f6ce  lea     rcx, [rbp+460h+var_290]; this
0x18008f6d5  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18008f6da  nop
0x18008f6db  lea     rcx, [rsp+560h+var_4F0]
0x18008f6e0  call    WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8_______WppTraceUnwinder__lambda_ba70c506923d725df71d3a84c5f14ef8____
0x18008f6e5  nop
0x18008f6e6  jmp     loc_18008F623
0x18008f6eb  test    cs:Microsoft_Windows_BiometricsEnableBits, 8
0x18008f6f2  jz      short loc_18008F719
0x18008f6f4  lea     rax, [rbp+460h+SystemTime]
0x18008f6fb  mov     [rsp+560h+PayloadBlobSize], rax; int
0x18008f700  mov     r9d, 1
0x18008f706  lea     rdx, WbioSrvcPerfEnrollCommitStart
0x18008f70d  lea     rcx, WBIOSRVC_PROVIDER_Context
0x18008f714  call    McGenEventWrite_EventWriteTransfer
0x18008f719  mov     rdx, [r12]; struct CBiometricUnit *
0x18008f71d  lea     rcx, [rbp+460h+var_290]; this
0x18008f724  call    ?CaptureSensorInfo@CEtwEvent@@QEAAXPEAVCBiometricUnit@@@Z; CEtwEvent::CaptureSensorInfo(CBiometricUnit *)
0x18008f729  mov     rdx, [r12]; struct CBiometricUnit *
0x18008f72d  lea     rcx, [rbp+460h+var_290]; this
0x18008f734  call    ?CaptureConfigurationInfo@CEtwEvent@@QEAAXPEAVCBiometricUnit@@@Z; CEtwEvent::CaptureConfigurationInfo(CBiometricUnit *)
0x18008f739  cmp     [rsp+560h+var_50B], bl
0x18008f73d  jnz     short loc_18008F78A
0x18008f73f  mov     rax, [r13+20h]
0x18008f743  test    rax, rax
0x18008f746  jz      loc_18008F809
0x18008f74c  mov     rax, [rax+0A0h]
0x18008f753  test    rax, rax
0x18008f756  jnz     short loc_18008F765
0x18008f758  mov     [rsp+560h+var_510], 80004001h
0x18008f760  jmp     loc_18008FF26
0x18008f765  lea     r9, [rsp+560h+var_50A]
0x18008f76a  lea     r8, [rsp+560h+var_509]
0x18008f76f  lea     rdx, [rbp+460h+var_2E0]
0x18008f776  mov     rcx, r13
0x18008f779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f77e  mov     [rsp+560h+var_510], eax
0x18008f782  test    eax, eax
0x18008f784  js      loc_18008FF2C
0x18008f78a  cmp     dword ptr [rdi+20h], 1
0x18008f78e  jnz     loc_18008F959
0x18008f794  cmp     [rsp+560h+var_50A], bl
0x18008f798  jnz     loc_18008F97C
0x18008f79e  mov     rcx, [r12]; this
0x18008f7a2  call    ?SupportsSecureConnection@CBiometricUnit@@QEBA_NXZ; CBiometricUnit::SupportsSecureConnection(void)
0x18008f7a7  test    al, al
0x18008f7a9  jz      loc_18008F90E
0x18008f7af  lea     rdx, [rcx+0B78h]
0x18008f7b6  lea     rcx, [rbp+460h+SystemTime]
0x18008f7bd  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18008f7c2  nop
0x18008f7c3  mov     r8, qword ptr [rbp+460h+SystemTime.wHour]
0x18008f7ca  mov     rdx, qword ptr [rbp+460h+SystemTime.wYear]; unsigned __int8 *
0x18008f7d1  cmp     rdx, r8
0x18008f7d4  jnz     short loc_18008F816
0x18008f7d6  mov     rcx, [rbp+468h]; this
0x18008f7dd  mov     r9d, 8000FFFFh; char *
0x18008f7e3  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\biometrics\\serv"...
0x18008f7ea  mov     edx, 86Ah; void *
0x18008f7ef  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18008f7f4  mov     [rsp+560h+var_510], eax
0x18008f7f8  lea     rcx, [rbp+460h+SystemTime]
0x18008f7ff  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
  ... truncated ...
```
