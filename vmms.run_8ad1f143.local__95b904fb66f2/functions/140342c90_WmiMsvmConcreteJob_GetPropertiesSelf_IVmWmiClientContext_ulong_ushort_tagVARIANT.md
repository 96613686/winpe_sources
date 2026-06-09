# WmiMsvmConcreteJob::GetPropertiesSelf(IVmWmiClientContext *,ulong,ushort * *,tagVARIANT *)

- ea: `0x140342c90`
- end: `0x140344b98`
- name: `?GetPropertiesSelf@WmiMsvmConcreteJob@@MEAAXPEAUIVmWmiClientContext@@KPEAPEAGPEAUtagVARIANT@@@Z`
- size: `7944`
- prototype: `void __fastcall(WmiMsvmConcreteJob *__hidden this, struct IVmWmiClientContext *, unsigned int, unsigned __int16 **, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `45`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14001a000`
- `0x140022640`
- `0x140032594`
- `0x14003d89c`
- `0x140054fc8`
- `0x14005df58`
- `0x140063794`
- `0x140074270`
- `0x14007b380`
- `0x140081828`
- `0x1400819d4`
- `0x140082388`
- `0x1400826e0`
- `0x140084480`
- `0x1400923e8`
- `0x14009626c`
- `0x140096cdc`
- `0x140097760`
- `0x140099fac`
- `0x14009acc0`
- `0x1400b189c`
- `0x1400b2544`
- `0x1400c8b90`
- `0x1400cb0f8`
- `0x1400cc17c`
- `0x1400da7b0`
- `0x1400e135c`
- `0x1400ebf20`
- `0x1400ee880`
- `0x1401683b4`
- `0x140188e18`
- `0x1401eee50`
- `0x1401eef04`
- `0x1401fb370`
- `0x14025edd4`
- `0x140342c90`
- `0x1404828e0`
- `0x1404835a0`
- `0x1406dfbec`
- `0x1406dfc80`
- `0x1406dff80`
- `0x1406e0920`
- `0x1406e0a58`
- `0x1406e0b1c`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403433fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403433fb`
- `OLEAUT32!__imp_VariantInit` at `0x140343ac5`
- `OLEAUT32!__imp_VariantInit` at `0x140343fca`
- `OLEAUT32!__imp_VariantInit` at `0x140344a85`
- `OLEAUT32!__imp_VariantInit` at `0x140343ac5`
- `OLEAUT32!__imp_VariantInit` at `0x140343fca`
- `OLEAUT32!__imp_VariantInit` at `0x140344a85`
- `OLEAUT32!__imp_VariantClear` at `0x140343fa0`
- `OLEAUT32!__imp_VariantClear` at `0x140344a33`
- `OLEAUT32!__imp_VariantClear` at `0x140344b5a`
- `OLEAUT32!__imp_VariantClear` at `0x140343fa0`
- `OLEAUT32!__imp_VariantClear` at `0x140344a33`
- `OLEAUT32!__imp_VariantClear` at `0x140344b5a`

## string_xrefs

- `0x1403430b2`: `InstallDate`
- `0x140343ad2`: `ExportDirectory`
- `0x140343aeb`: `ExportDirectory`
- `0x140344177`: `ExportDirectory`
- `0x140344190`: `ExportDirectory`
- `0x140344528`: `ExportedRuntimeFilePath[%u]`
- `0x140344655`: `ExportedRuntimeFilePath[%u]`
- `0x140343e8a`: `ExportedRuntimeFilePath`
- `0x140343ea3`: `ExportedRuntimeFilePath`
- `0x140343d7a`: `ExportedLogFilePaths`
- `0x140343d93`: `ExportedLogFilePaths`
- `0x140344906`: `ExportedLogFilePaths`
- `0x140343e02`: `ExportedConfigFilePath`
- `0x140343e1b`: `ExportedConfigFilePath`
- `0x1403443fb`: `ExportedConfigFilePath[%u]`
- `0x140343f12`: `ExportedGuestStateFilePath`
- `0x140343f2b`: `ExportedGuestStateFilePath`
- `0x140344951`: `ExportedLogFilePaths[%u]`
- `0x140343407`: `PercentComplete`
- `0x140343635`: `ScheduledStartTime`
- `0x140342f51`: `DeleteOnCompletion`
- `0x140342ed3`: `JobCompletionStatusCode`
- `0x140343a34`: `CopyFileToGuestSettingData`
- `0x1403444dd`: `ExportedRuntimeFilePaths`
- `0x14034460a`: `ExportedGuestStateFilePaths`
- `0x1403443b0`: `ExportedConfigFilePaths`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
void __fastcall WmiMsvmConcreteJob::GetPropertiesSelf(
        WmiMsvmConcreteJob *this,
        struct IVmWmiClientContext *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        struct tagVARIANT *a5)
{
  WmiMsvmConcreteJob *v7; // r15
  _WORD *PropertyValue; // rbx
  Vml::VmVariant *v9; // rsi
  __int16 ConcreteTaskType; // bx
  Vml::VmVariant *v11; // rsi
  __int16 MigrationTaskType; // bx
  VARIANTARG *v13; // rsi
  __int64 v14; // rax
  VARIANTARG *v15; // rbx
  Vml::VmVariant *v16; // rsi
  int ErrorHResult; // ebx
  Vml::VmVariant *v18; // rsi
  __int16 DiskTaskType; // bx
  Vml::VmVariant *v20; // rsi
  bool v21; // bl
  Vml::VmVariant *v22; // rsi
  __int64 v23; // rbx
  Vml::VmVariant *v24; // rsi
  int v25; // eax
  __int16 v26; // bx
  __int64 v27; // rax
  _WORD *v28; // rbx
  __int64 v29; // rax
  _WORD *v30; // rbx
  VARIANTARG *v31; // rax
  VARIANTARG *v32; // rbx
  OLECHAR *v33; // rdx
  Vml::VmVariant *v34; // rax
  Vml::VmVariant *v35; // rbx
  Vml::VmVariant *v36; // rsi
  __int16 JobState; // bx
  Vml::VmVariant *v38; // rbx
  unsigned __int16 *JobStatus; // rax
  Vml::VmVariant *v40; // rax
  Vml::VmVariant *v41; // rbx
  __int64 v42; // rax
  _WORD *v43; // rbx
  VARIANTARG *v44; // rax
  VARIANTARG *v45; // rax
  VARIANTARG *v46; // rbx
  OLECHAR *v47; // rdx
  Vml::VmVariant *v48; // rsi
  unsigned __int64 v49; // rbx
  Vml::VmVariant *v50; // rax
  Vml::VmVariant *v51; // rbx
  Vml::VmVariant *v52; // rax
  Vml::VmVariant *v53; // rbx
  VARIANTARG *v54; // rbx
  Vml::VmVariant *v55; // rsi
  __int64 v56; // rbx
  VARIANTARG *v57; // rbx
  VARIANTARG *v58; // rbx
  VARIANTARG *v59; // rbx
  int v60; // eax
  Vml::VmVariant *v61; // rsi
  SAFEARRAY *v62; // rbx
  __int16 v63; // di
  VARIANTARG *v64; // rdi
  VARIANTARG *v65; // rdi
  VARIANTARG *v66; // rdi
  VARIANTARG *v67; // rdi
  int v68; // r8d
  SAFEARRAY *v69; // rdx
  void **v70; // rax
  void *v71; // rcx
  __int64 v72; // r8
  __int64 v73; // rcx
  char v74; // di
  VARIANTARG *v75; // rdi
  int v76; // eax
  int v77; // r8d
  SAFEARRAY *v78; // rdx
  void *p_psa; // rcx
  VARIANTARG *v80; // rbx
  Vml::VmVariant *v81; // rbx
  int v82; // eax
  Vml::VmVariant *v83; // rbx
  int v84; // eax
  Vml::VmVariant *v85; // rbx
  int v86; // eax
  Vml::VmVariant *v87; // rbx
  int v88; // eax
  Vml::VmVariant *v89; // rbx
  int v90; // eax
  Vml::VmVariant *v91; // rbx
  int v92; // eax
  Vml::VmVariant *v93; // rbx
  int v94; // eax
  Vml::VmVariant *v95; // rbx
  int v96; // eax
  Vml::VmVariant *v97; // rbx
  int v98; // eax
  struct _GUID *v99; // rcx
  Vml::VmVariant *v100; // rbx
  int v101; // eax
  Vml::VmVariant *v102; // rbx
  int v103; // eax
  Vml::VmVariant *v104; // rbx
  int v105; // eax
  Vml::VmVariant *v106; // rbx
  int v107; // eax
  int v108; // eax
  unsigned int v109; // ebx
  Vml::VmVariant *v110; // r13
  unsigned int i; // esi
  int v112; // eax
  __int64 v113; // rax
  Vml::VmVariant *v114; // r13
  unsigned int j; // esi
  int v116; // eax
  __int64 v117; // rax
  Vml::VmVariant *v118; // r13
  unsigned int k; // esi
  int v120; // eax
  __int64 v121; // rax
  Vml::VmVariant *v122; // r13
  unsigned int m; // esi
  int v124; // eax
  __int64 v125; // rax
  int v126; // eax
  unsigned int v127; // ebx
  Vml::VmVariant *v128; // r13
  unsigned int n; // esi
  int v130; // eax
  __int64 v131; // rax
  Vml::VmVariant *v132; // r13
  unsigned int ii; // esi
  int v134; // eax
  __int64 v135; // rax
  VARIANTARG *v136; // rbx
  int v137; // eax
  OLECHAR *v138; // rax
  struct tagVARIANT *v139; // [rsp+20h] [rbp-158h]
  int v140; // [rsp+20h] [rbp-158h]
  int v141; // [rsp+20h] [rbp-158h]
  _DWORD v142[2]; // [rsp+30h] [rbp-148h] BYREF
  unsigned __int16 **v143; // [rsp+38h] [rbp-140h]
  struct tagVARIANT *v144; // [rsp+40h] [rbp-138h]
  __int64 v145; // [rsp+50h] [rbp-128h] BYREF
  SAFEARRAY *psa; // [rsp+58h] [rbp-120h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-118h] BYREF
  LPVOID pv[2]; // [rsp+80h] [rbp-F8h] BYREF
  __m128i si128; // [rsp+90h] [rbp-E8h]
  OLECHAR *psz[2]; // [rsp+A0h] [rbp-D8h] BYREF
  __m128i v151; // [rsp+B0h] [rbp-C8h]
  struct _GUID v152; // [rsp+C0h] [rbp-B8h] BYREF
  _BYTE v153[80]; // [rsp+E0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v7 = this;
  *(_QWORD *)&pvarg.vt = this;
  VmWmiCimManagedSystemElement::GetPropertiesSelf(this, a2, a3, a4, a5);
  v142[1] = 0;
  v142[0] = a3;
  v143 = a4;
  v144 = a5;
  PropertyValue = (_WORD *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                             v142,
                             L"Cancellable");
  if ( PropertyValue )
  {
    LODWORD(v145) = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v7 + 4) + 136LL))(*((_QWORD *)v7 + 4), &v145) >= 0 )
    {
      PropertyValue[4] = -((v145 & 1) != 0);
      *PropertyValue = 11;
    }
  }
  if ( *((_DWORD *)v7 + 10) == 1 )
  {
    v9 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"JobType");
    if ( v9 )
    {
      ConcreteTaskType = WmiMsvmConcreteJob::GetConcreteTaskType((char *)v7 - 24);
      Vml::VmVariant::Clear(v9);
      *(_WORD *)v9 = 18;
      *((_WORD *)v9 + 4) = ConcreteTaskType;
    }
  }
  if ( *((_DWORD *)v7 + 10) == 3 )
  {
    v11 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"JobType");
    if ( v11 )
    {
      MigrationTaskType = WmiMsvmConcreteJob::GetMigrationTaskType((char *)v7 - 24);
      Vml::VmVariant::Clear(v11);
      *(_WORD *)v11 = 18;
      *((_WORD *)v11 + 4) = MigrationTaskType;
    }
  }
  if ( *((_DWORD *)v7 + 10) == 2 )
  {
    pv[0] = 0;
    v145 = 0;
    (*(void (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)v7 + 4) + 104LL))(*((_QWORD *)v7 + 4), pv);
    Vml::VmComPtr<IVmStorageTaskData>::Reset<IUnknown>(&v145, pv[0]);
    v13 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"Child");
    v14 = Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"Parent");
    v15 = (VARIANTARG *)v14;
    if ( v13 || v14 )
    {
      psz[0] = 0;
      psa = 0;
      if ( v145
        && (*(int (__fastcall **)(__int64, OLECHAR **, SAFEARRAY **))(*(_QWORD *)v145 + 24LL))(v145, psz, &psa) >= 0 )
      {
        if ( v13 )
          Vml::VmVariant::Assign(v13, psz[0]);
        if ( v15 )
          Vml::VmVariant::Assign(v15, &psa->cDims);
      }
      else
      {
        if ( v13 )
          Vml::VmVariant::Clear((Vml::VmVariant *)v13);
        if ( v15 )
          Vml::VmVariant::Clear((Vml::VmVariant *)v15);
      }
      Vml::VmBstr::~VmBstr((Vml::VmBstr *)&psa);
      Vml::VmBstr::~VmBstr((Vml::VmBstr *)psz);
    }
    v16 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                              v142,
                              L"JobCompletionStatusCode");
    if ( v16 )
    {
      ErrorHResult = WmiMsvmConcreteJob::GetErrorHResult((WmiMsvmConcreteJob *)((char *)v7 - 24));
      Vml::VmVariant::Clear(v16);
      *(_WORD *)v16 = 3;
      *((_DWORD *)v16 + 2) = ErrorHResult;
    }
    v18 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"JobType");
    if ( v18 )
    {
      DiskTaskType = WmiMsvmConcreteJob::GetDiskTaskType((char *)v7 - 24);
      Vml::VmVariant::Clear(v18);
      *(_WORD *)v18 = 18;
      *((_WORD *)v18 + 4) = DiskTaskType;
    }
    Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v145);
    Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(pv);
  }
  v20 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"DeleteOnCompletion");
  if ( v20 )
  {
    v21 = 0;
    LODWORD(v145) = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v7 + 4) + 240LL))(*((_QWORD *)v7 + 4), &v145) >= 0 )
      v21 = (_DWORD)v145 == 0;
    Vml::VmVariant::Assign(v20, v21);
  }
  v22 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"ElapsedTime");
  if ( v22 )
  {
    *(_QWORD *)&v152.Data1 = 0;
    if ( (*(int (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)v7 + 4) + 216LL))(*((_QWORD *)v7 + 4), &v152) >= 0 )
    {
      v23 = *(_QWORD *)&v152.Data1;
      Vml::VmVariant::Clear(v22);
      *(_WORD *)v22 = 21;
      *((_QWORD *)v22 + 1) = v23;
    }
  }
  v24 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"ErrorCode");
  if ( v24 )
  {
    v25 = WmiMsvmConcreteJob::GetErrorHResult((WmiMsvmConcreteJob *)((char *)v7 - 24));
    v26 = VmWmiMethodStatusFromHResult(v25);
    Vml::VmVariant::Clear(v24);
    *(_WORD *)v24 = 18;
    *((_WORD *)v24 + 4) = v26;
  }
  v27 = Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"ErrorDescription");
  v28 = (_WORD *)v27;
  if ( v27
    && (*(int (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v7 + 4) + 160LL))(*((_QWORD *)v7 + 4), 0, v27 + 8) >= 0 )
  {
    *v28 = 8;
  }
  v29 = Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"ErrorSummaryDescription");
  v30 = (_WORD *)v29;
  if ( v29
    && (*(int (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v7 + 4) + 168LL))(*((_QWORD *)v7 + 4), 0, v29 + 8) >= 0 )
  {
    *v30 = 8;
  }
  v31 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"InstallDate");
  if ( v31 )
  {
    *(_QWORD *)&v152.Data1 = 0;
    Vml::VmVariant::Assign(v31, (FILETIME *)&v152);
  }
  v32 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"InstanceId");
  if ( v32 )
  {
    v152 = 0;
    if ( (*(int (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)v7 + 4) + 120LL))(*((_QWORD *)v7 + 4), &v152) >= 0 )
    {
      *(_OWORD *)pv = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(pv[0]) = 0;
      Vml::VmGuid::ToString(&v152, pv);
      v33 = (OLECHAR *)pv;
      if ( si128.m128i_i64[1] > 7uLL )
        v33 = (OLECHAR *)pv[0];
      Vml::VmVariant::Assign(v32, v33);
      std::wstring::_Tidy_deallocate(pv);
    }
  }
  v34 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"JobRunTimes");
  v35 = v34;
  if ( v34 )
  {
    Vml::VmVariant::Clear(v34);
    *(_WORD *)v35 = 19;
    *((_DWORD *)v35 + 2) = 1;
  }
  v36 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"JobState");
  if ( v36 )
  {
    JobState = WmiMsvmConcreteJob::GetJobState((char *)v7 - 24);
    Vml::VmVariant::Clear(v36);
    *(_WORD *)v36 = 18;
    *((_WORD *)v36 + 4) = JobState;
  }
  v38 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"JobStatus");
  if ( v38 )
  {
    JobStatus = WmiMsvmConcreteJob::GetJobStatus((WmiMsvmConcreteJob *)((char *)v7 - 24));
    Vml::VmVariant::Attach(v38, JobStatus);
  }
  v40 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"LocalOrUtcTime");
  v41 = v40;
  if ( v40 )
  {
    Vml::VmVariant::Clear(v40);
    *(_WORD *)v41 = 18;
    *((_WORD *)v41 + 4) = 2;
  }
  v42 = Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"Name");
  v43 = (_WORD *)v42;
  if ( v42
    && (*(int (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v7 + 4) + 144LL))(*((_QWORD *)v7 + 4), 0, v42 + 8) >= 0 )
  {
    *v43 = 8;
  }
  v44 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"Notify");
  if ( v44 )
    Vml::VmVariant::Assign(v44, (OLECHAR *)&pwszBaseUri);
  v45 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                        v142,
                        L"OtherRecoveryAction");
  if ( v45 )
    Vml::VmVariant::Assign(v45, (OLECHAR *)&pwszBaseUri);
  v46 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"Owner");
  *(_QWORD *)&v152.Data1 = v46;
  if ( v46 )
  {
    pv[1] = 0;
    pv[0] = 0;
    if ( (*(int (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)v7 + 4) + 176LL))(*((_QWORD *)v7 + 4), pv) >= 0 )
    {
      memset_0(v153, 0, sizeof(v153));
      Vml::VmSid::VmSid((Vml::VmSid *)v153, pv[0]);
      *(_OWORD *)psz = 0;
      v151 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(psz[0]) = 0;
      try
      {
        Vml::VmSid::GetSamCompatibleName();
      }
      catch ( ... )
      {
        Vml::VmSid::ToString(v153, psz);
        v46 = *(VARIANTARG **)&v152.Data1;
        v7 = *(WmiMsvmConcreteJob **)&pvarg.vt;
      }
      v47 = (OLECHAR *)psz;
      if ( v151.m128i_i64[1] > 7uLL )
        v47 = psz[0];
      Vml::VmVariant::Assign(v46, v47);
      std::wstring::_Tidy_deallocate(psz);
      Vml::VmSid::~VmSid((Vml::VmSid *)v153);
    }
    CoTaskMemFree(pv[0]);
  }
  v48 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"PercentComplete");
  if ( v48 )
  {
    *(_QWORD *)&v152.Data1 = 0;
    pv[0] = 0;
    if ( (*(int (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)v7 + 4) + 32LL))(*((_QWORD *)v7 + 4), &v152) >= 0
      && (*(int (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)v7 + 4) + 40LL))(*((_QWORD *)v7 + 4), pv) >= 0 )
    {
      v49 = 100LL * *(_QWORD *)&v152.Data1 / (unsigned __int64)pv[0];
      Vml::VmVariant::Clear(v48);
      *(_WORD *)v48 = 18;
      *((_WORD *)v48 + 4) = v49;
    }
  }
  v50 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"Priority");
  v51 = v50;
  if ( v50 )
  {
    Vml::VmVariant::Clear(v50);
    *(_WORD *)v51 = 19;
    *((_DWORD *)v51 + 2) = 0;
  }
  v52 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"RecoveryAction");
  v53 = v52;
  if ( v52 )
  {
    Vml::VmVariant::Clear(v52);
    *(_WORD *)v53 = 18;
    *((_WORD *)v53 + 4) = 2;
  }
  v54 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"StartTime");
  if ( v54 )
  {
    pv[0] = 0;
    if ( (*(int (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)v7 + 4) + 208LL))(*((_QWORD *)v7 + 4), pv) >= 0 )
      Vml::VmVariant::Assign(v54, (FILETIME *)pv);
  }
  v55 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"TimeBeforeRemoval");
  if ( v55 )
  {
    LODWORD(v145) = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v7 + 4) + 240LL))(*((_QWORD *)v7 + 4), &v145) >= 0 )
    {
      v56 = 10000000LL * (unsigned int)v145;
      Vml::VmVariant::Clear(v55);
      *(_WORD *)v55 = 21;
      *((_QWORD *)v55 + 1) = v56;
    }
  }
  v57 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                        v142,
                        L"TimeOfLastStateChange");
  if ( v57 )
  {
    pv[0] = 0;
    if ( (*(int (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)v7 + 4) + 224LL))(*((_QWORD *)v7 + 4), pv) >= 0 )
      Vml::VmVariant::Assign(v57, (FILETIME *)pv);
  }
  v58 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v142, L"TimeSubmitted");
  if ( v58 )
  {
    pv[0] = 0;
    if ( (*(int (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)v7 + 4) + 200LL))(*((_QWORD *)v7 + 4), pv) >= 0 )
      Vml::VmVariant::Assign(v58, (FILETIME *)pv);
  }
  v59 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                        v142,
                        L"ScheduledStartTime");
  if ( v59 )
  {
    pv[0] = 0;
    if ( (*(int (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)v7 + 4) + 264LL))(*((_QWORD *)v7 + 4), pv) >= 0 )
      Vml::VmVariant::Assign(v59, (FILETIME *)pv);
  }
  v60 = *((_DWORD *)v7 + 10);
  switch ( v60 )
  {
    case 3:
      *(_QWORD *)&v152.Data1 = 0;
      psa = 0;
      (*(void (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)v7 + 4) + 104LL))(*((_QWORD *)v7 + 4), &v152);
      Vml::VmComPtr<IVmMigrationTaskData>::Reset<IUnknown>(&psa, *(_QWORD *)&v152.Data1);
      v61 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"MigrationType");
      v62 = psa;
      if ( v61 )
      {
        LODWORD(v145) = 0;
        (*(void (__fastcall **)(SAFEARRAY *, __int64 *))(*(_QWORD *)&psa->cDims + 24LL))(psa, &v145);
        v63 = v145;
        Vml::VmVariant::Clear(v61);
        *(_WORD *)v61 = 18;
        *((_WORD *)v61 + 4) = v63;
      }
      v64 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"VirtualSystemName");
      if ( v64 )
      {
        *(_OWORD *)&pvarg.vt = 0;
        *(_OWORD *)pv = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(pv[0]) = 0;
        (*(void (__fastcall **)(SAFEARRAY *, VARIANTARG *))(*(_QWORD *)&v62->cDims + 32LL))(v62, &pvarg);
        Vml::VmGuid::ToString((struct _GUID *)&pvarg, pv);
        Vml::VmVariant::Assign(v64, (OLECHAR *)pv);
        std::wstring::_Tidy_deallocate(pv);
      }
      v65 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"DestinationHost");
      if ( v65 )
      {
        pv[0] = 0;
        (*(void (__fastcall **)(SAFEARRAY *, LPVOID *))(*(_QWORD *)&v62->cDims + 40LL))(v62, pv);
        if ( pv[0] )
          Vml::VmVariant::Assign(v65, (OLECHAR *)pv[0]);
        Vml::VmBstr::~VmBstr((Vml::VmBstr *)pv);
      }
      v66 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"NewSystemSettingData");
      if ( v66 )
      {
        pv[0] = 0;
        (*(void (__fastcall **)(SAFEARRAY *, LPVOID *))(*(_QWORD *)&v62->cDims + 48LL))(v62, pv);
        if ( pv[0] )
          Vml::VmVariant::Assign(v66, (OLECHAR *)pv[0]);
        Vml::VmBstr::~VmBstr((Vml::VmBstr *)pv);
      }
      v67 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"NewResourceSettingData");
      if ( v67 )
      {
        psz[0] = 0;
        (*(void (__fastcall **)(SAFEARRAY *, OLECHAR **))(*(_QWORD *)&v62->cDims + 56LL))(v62, psz);
        v69 = (SAFEARRAY *)psz[0];
        if ( !psz[0] )
        {
          Vml::VmSafeArray::Create((Vml::VmSafeArray *)psz, 8u, v68, 0, v139);
          v69 = (SAFEARRAY *)psz[0];
        }
        Vml::VmVariant::Assign(v67, v69);
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)psz);
      }
      v70 = (void **)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(&pvarg);
      v71 = *v70;
      *v70 = 0;
      pv[0] = v71;
      v73 = VirtualizationSettings::VirtualizationSettings(psz, 0, v72, pv);
      v74 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 128LL))(v73);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>(&psz[1]);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>(pv);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>(&pvarg);
      if ( v74 )
      {
        v75 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                              v142,
                              L"MigrationStateList");
        if ( v75 )
        {
          psz[0] = 0;
          v76 = (*(__int64 (__fastcall **)(SAFEARRAY *, OLECHAR **))(*(_QWORD *)&v62->cDims + 64LL))(v62, psz);
          if ( v76 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x799,
              (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
              (const char *)(unsigned int)v76,
              (int)v139);
          v78 = (SAFEARRAY *)psz[0];
          if ( !psz[0] )
          {
            Vml::VmSafeArray::Create((Vml::VmSafeArray *)psz, 0x12u, v77, 0, v139);
            v78 = (SAFEARRAY *)psz[0];
          }
          Vml::VmVariant::Assign(v75, v78);
          Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)psz);
        }
      }
      Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&psa);
      p_psa = &v152;
LABEL_127:
      Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(p_psa);
      return;
    case 4:
      psa = 0;
      pv[0] = 0;
      (*(void (__fastcall **)(_QWORD, SAFEARRAY **))(**((_QWORD **)v7 + 4) + 104LL))(*((_QWORD *)v7 + 4), &psa);
      Vml::VmComPtr<IVmCopyFilesToGuestTaskData>::Reset<IUnknown>(pv, psa);
      v80 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                            v142,
                            L"CopyFileToGuestSettingData");
      if ( v80 )
      {
        *(_QWORD *)&v152.Data1 = 0;
        (*(void (__fastcall **)(LPVOID, struct _GUID *))(*(_QWORD *)pv[0] + 24LL))(pv[0], &v152);
        if ( *(_QWORD *)&v152.Data1 )
          Vml::VmVariant::Assign(v80, *(SAFEARRAY **)&v152.Data1);
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v152);
      }
      Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(pv);
      p_psa = &psa;
      goto LABEL_127;
    case 5:
      v145 = 0;
      VariantInit(&pvarg);
      v81 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"ExportDirectory");
      if ( v81 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ExportDirectory");
        v82 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                *((_QWORD *)v7 + 4),
                1,
                &v145,
                &pvarg);
        if ( v82 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7D1,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v82,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v81, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v83 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"VirtualMachineId");
      if ( v83 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"VirtualMachineId");
        v84 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                *((_QWORD *)v7 + 4),
                1,
                &v145,
                &pvarg);
        if ( v84 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7E2,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v84,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v83, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v85 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"ReferencePointId");
      if ( v85 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ReferencePointId");
        v86 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                *((_QWORD *)v7 + 4),
                1,
                &v145,
                &pvarg);
        if ( v86 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7F3,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v86,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v85, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v87 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"BaseReferencePointId");
      if ( v87 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"BaseReferencePointId");
        v88 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                *((_QWORD *)v7 + 4),
                1,
                &v145,
                &pvarg);
        if ( v88 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x804,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v88,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v87, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v89 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"ExportedDisks");
      if ( v89 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ExportedDisks");
        v90 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                *((_QWORD *)v7 + 4),
                1,
                &v145,
                &pvarg);
        if ( v90 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x815,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v90,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v89, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v91 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"ExportedLogFilePaths");
      if ( v91 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ExportedLogFilePaths");
        v92 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                *((_QWORD *)v7 + 4),
                1,
                &v145,
                &pvarg);
        if ( v92 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x826,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v92,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v91, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v93 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"ExportedConfigFilePath");
      if ( v93 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ExportedConfigFilePath");
        v94 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                *((_QWORD *)v7 + 4),
                1,
                &v145,
                &pvarg);
        if ( v94 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x837,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v94,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v93, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v95 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"ExportedRuntimeFilePath");
      if ( v95 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ExportedRuntimeFilePath");
        v96 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                *((_QWORD *)v7 + 4),
                1,
                &v145,
                &pvarg);
        if ( v96 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x848,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v96,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v95, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v97 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                v142,
                                L"ExportedGuestStateFilePath");
      if ( v97 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ExportedGuestStateFilePath");
        v98 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                *((_QWORD *)v7 + 4),
                1,
                &v145,
                &pvarg);
        if ( v98 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x859,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v98,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v97, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      VariantClear(&pvarg);
LABEL_184:
      v99 = (struct _GUID *)&v145;
      goto LABEL_282;
    case 6:
      v145 = 0;
      VariantInit(&pvarg);
      psz[0] = 0;
      v100 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"CollectionId");
      if ( v100 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"CollectionId");
        v101 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                 *((_QWORD *)v7 + 4),
                 1,
                 &v145,
                 &pvarg);
        if ( v101 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x875,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v101,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v100, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v102 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"ReferencePointGroupId");
      if ( v102 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ReferencePointGroupId");
        v103 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                 *((_QWORD *)v7 + 4),
                 1,
                 &v145,
                 &pvarg);
        if ( v103 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x886,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v103,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v102, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v104 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"BaseReferencePointGroupId");
      if ( v104 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"BaseReferencePointGroupId");
        v105 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                 *((_QWORD *)v7 + 4),
                 1,
                 &v145,
                 &pvarg);
        if ( v105 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x897,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v105,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v104, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      v106 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"ExportDirectory");
      if ( v106 )
      {
        Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ExportDirectory");
        v107 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                 *((_QWORD *)v7 + 4),
                 1,
                 &v145,
                 &pvarg);
        if ( v107 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8A8,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
            (const char *)(unsigned int)v107,
            (int)v139);
        if ( pvarg.vt > 1u )
          Vml::VmVariant::Assign(v106, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      }
      Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"VirtualMachineCount");
      v108 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
               *((_QWORD *)v7 + 4),
               1,
               &v145,
               &pvarg);
      if ( v108 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8B8,
          (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
          (const char *)(unsigned int)v108,
          (int)v139);
      v109 = 0;
      if ( pvarg.vt > 1u )
        v109 = Vml::VmVariant::ToULONG(&pvarg);
      Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      v110 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"VirtualMachineId");
      if ( v110 )
      {
        psa = 0;
        Vml::VmSafeArray::VmSafeArray((Vml::VmSafeArray *)&psa, 8u, 0, v109, 0);
        for ( i = 0; i < v109; ++i )
        {
          Vml::VmBstr::Format((Vml::VmBstr *)&v145, L"VirtualMachine[%u]", i);
          v112 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                   *((_QWORD *)v7 + 4),
                   1,
                   &v145,
                   &pvarg);
          if ( v112 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x8CE,
              (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
              (const char *)(unsigned int)v112,
              (int)v139);
          if ( pvarg.vt > 1u )
          {
            v113 = Vml::VmVariant::ToString(&pvarg);
            Vml::VmBstr::Assign(psz, v113);
            std::wstring::_Tidy_deallocate(&v152);
            Vml::VmSafeArray::PutElement((Vml::VmSafeArray *)&psa, i, psz);
          }
          Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        }
        Vml::VmVariant::Assign(&pvarg, psa);
        Vml::VmVariant::Assign(v110, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&psa);
      }
      v114 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"ExportedConfigFilePaths");
      if ( v114 )
      {
        psa = 0;
        Vml::VmSafeArray::VmSafeArray((Vml::VmSafeArray *)&psa, 8u, 0, v109, 0);
        for ( j = 0; j < v109; ++j )
        {
          Vml::VmBstr::Format((Vml::VmBstr *)&v145, L"ExportedConfigFilePath[%u]", j);
          v116 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                   *((_QWORD *)v7 + 4),
                   1,
                   &v145,
                   &pvarg);
          if ( v116 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x8EA,
              (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
              (const char *)(unsigned int)v116,
              (int)v139);
          if ( pvarg.vt > 1u )
          {
            v117 = Vml::VmVariant::ToString(&pvarg);
            Vml::VmBstr::Assign(psz, v117);
            std::wstring::_Tidy_deallocate(&v152);
            Vml::VmSafeArray::PutElement((Vml::VmSafeArray *)&psa, j, psz);
          }
          Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        }
        if ( Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&psa) )
        {
          Vml::VmVariant::Assign(&pvarg, psa);
          Vml::VmVariant::Assign(v114, &pvarg);
          Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        }
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&psa);
      }
      v118 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"ExportedRuntimeFilePaths");
      if ( v118 )
      {
        psa = 0;
        Vml::VmSafeArray::VmSafeArray((Vml::VmSafeArray *)&psa, 8u, 0, v109, 0);
        for ( k = 0; k < v109; ++k )
        {
          Vml::VmBstr::Format((Vml::VmBstr *)&v145, L"ExportedRuntimeFilePath[%u]", k);
          v120 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                   *((_QWORD *)v7 + 4),
                   1,
                   &v145,
                   &pvarg);
          if ( v120 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x909,
              (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
              (const char *)(unsigned int)v120,
              (int)v139);
          if ( pvarg.vt > 1u )
          {
            v121 = Vml::VmVariant::ToString(&pvarg);
            Vml::VmBstr::Assign(psz, v121);
            std::wstring::_Tidy_deallocate(&v152);
            Vml::VmSafeArray::PutElement((Vml::VmSafeArray *)&psa, k, psz);
          }
          Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        }
        if ( Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&psa) )
        {
          Vml::VmVariant::Assign(&pvarg, psa);
          Vml::VmVariant::Assign(v118, &pvarg);
          Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        }
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&psa);
      }
      v122 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"ExportedGuestStateFilePaths");
      if ( v122 )
      {
        psa = 0;
        Vml::VmSafeArray::VmSafeArray((Vml::VmSafeArray *)&psa, 8u, 0, v109, 0);
        for ( m = 0; m < v109; ++m )
        {
          Vml::VmBstr::Format((Vml::VmBstr *)&v145, L"ExportedRuntimeFilePath[%u]", m);
          v124 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                   *((_QWORD *)v7 + 4),
                   1,
                   &v145,
                   &pvarg);
          if ( v124 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x928,
              (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
              (const char *)(unsigned int)v124,
              (int)v139);
          if ( pvarg.vt > 1u )
          {
            v125 = Vml::VmVariant::ToString(&pvarg);
            Vml::VmBstr::Assign(psz, v125);
            std::wstring::_Tidy_deallocate(&v152);
            Vml::VmSafeArray::PutElement((Vml::VmSafeArray *)&psa, m, psz);
          }
          Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        }
        if ( Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&psa) )
        {
          Vml::VmVariant::Assign(&pvarg, psa);
          Vml::VmVariant::Assign(v122, &pvarg);
          Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        }
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&psa);
      }
      Vml::VmBstr::Assign((Vml::VmBstr *)&v145, L"ExportedDiskAndLogFileCount");
      v126 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
               *((_QWORD *)v7 + 4),
               1,
               &v145,
               &pvarg);
      if ( v126 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x941,
          (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
          (const char *)(unsigned int)v126,
          (int)v139);
      v127 = 0;
      if ( pvarg.vt > 1u )
        v127 = Vml::VmVariant::ToULONG(&pvarg);
      Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
      v128 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"ExportedDisks");
      if ( v128 )
      {
        psa = 0;
        Vml::VmSafeArray::VmSafeArray((Vml::VmSafeArray *)&psa, 8u, 0, v127, 0);
        for ( n = 0; n < v127; ++n )
        {
          Vml::VmBstr::Format((Vml::VmBstr *)&v145, L"ExportedDisks[%u]", n);
          v130 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                   *((_QWORD *)v7 + 4),
                   1,
                   &v145,
                   &pvarg);
          if ( v130 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x957,
              (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
              (const char *)(unsigned int)v130,
              v140);
          if ( pvarg.vt > 1u )
          {
            v131 = Vml::VmVariant::ToString(&pvarg);
            Vml::VmBstr::Assign(psz, v131);
            std::wstring::_Tidy_deallocate(&v152);
            Vml::VmSafeArray::PutElement((Vml::VmSafeArray *)&psa, n, psz);
          }
          Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        }
        Vml::VmVariant::Assign(&pvarg, psa);
        Vml::VmVariant::Assign(v128, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&psa);
      }
      v132 = (Vml::VmVariant *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                 v142,
                                 L"ExportedLogFilePaths");
      if ( v132 )
      {
        psa = 0;
        Vml::VmSafeArray::VmSafeArray((Vml::VmSafeArray *)&psa, 8u, 0, v127, 0);
        for ( ii = 0; ii < v127; ++ii )
        {
          Vml::VmBstr::Format((Vml::VmBstr *)&v145, L"ExportedLogFilePaths[%u]", ii);
          v134 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
                   *((_QWORD *)v7 + 4),
                   1,
                   &v145,
                   &pvarg);
          if ( v134 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x973,
              (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
              (const char *)(unsigned int)v134,
              v141);
          if ( pvarg.vt > 1u )
          {
            v135 = Vml::VmVariant::ToString(&pvarg);
            Vml::VmBstr::Assign(psz, v135);
            std::wstring::_Tidy_deallocate(v142);
            Vml::VmSafeArray::PutElement((Vml::VmSafeArray *)&psa, ii, psz);
          }
          Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        }
        Vml::VmVariant::Assign(&pvarg, psa);
        Vml::VmVariant::Assign(v132, &pvarg);
        Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&psa);
      }
      Vml::VmBstr::~VmBstr((Vml::VmBstr *)psz);
      VariantClear(&pvarg);
      goto LABEL_184;
  }
  if ( v60 != 7 )
    return;
  *(_QWORD *)&v152.Data1 = 0;
  VariantInit(&pvarg);
  v136 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                         v142,
                         L"ExtendedResultInformation");
  if ( v136 )
  {
    Vml::VmBstr::Assign((Vml::VmBstr *)&v152, L"ExtendedResultInformation");
    v137 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _GUID *, VARIANTARG *))(**((_QWORD **)v7 + 4) + 344LL))(
             *((_QWORD *)v7 + 4),
             1,
             &v152,
             &pvarg);
    if ( v137 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x991,
        (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmconcretejob.cpp",
        (const char *)(unsigned int)v137,
        (int)v139);
    if ( pvarg.vt <= 1u )
    {
      Vml::VmVariant::Assign(v136, (OLECHAR *)&pwszBaseUri);
    }
    else
    {
      v138 = (OLECHAR *)Vml::VmVariant::ToString(&pvarg);
      Vml::VmVariant::Assign(v136, v138);
      std::wstring::_Tidy_deallocate(v142);
    }
    Vml::VmVariant::Clear((Vml::VmVariant *)&pvarg);
  }
  VariantClear(&pvarg);
  v99 = &v152;
LABEL_282:
  Vml::VmBstr::~VmBstr((Vml::VmBstr *)v99);
}

```

## disassembly

```asm
0x140342c90  push    rbx
0x140342c92  push    rsi
0x140342c93  push    rdi
0x140342c94  push    r12
0x140342c96  push    r13
0x140342c98  push    r14
0x140342c9a  push    r15
0x140342c9c  sub     rsp, 140h
0x140342ca3  mov     rax, cs:__security_cookie
0x140342caa  xor     rax, rsp
0x140342cad  mov     [rsp+178h+var_48], rax
0x140342cb5  mov     rsi, r9
0x140342cb8  mov     edi, r8d
0x140342cbb  mov     r15, rcx
0x140342cbe  mov     qword ptr [rsp+178h+pvarg], rcx
0x140342cc3  mov     rbx, [rsp+178h+arg_20]
0x140342ccb  mov     [rsp+178h+var_158], rbx; struct tagVARIANT *
0x140342cd0  call    ?GetPropertiesSelf@VmWmiCimManagedSystemElement@@MEAAXPEAUIVmWmiClientContext@@KPEAPEAGPEAUtagVARIANT@@@Z; VmWmiCimManagedSystemElement::GetPropertiesSelf(IVmWmiClientContext *,ulong,ushort * *,tagVARIANT *)
0x140342cd5  xor     r14d, r14d
0x140342cd8  mov     [rsp+178h+var_144], r14d
0x140342cdd  mov     [rsp+178h+var_148], edi
0x140342ce1  mov     [rsp+178h+var_140], rsi
0x140342ce6  mov     [rsp+178h+var_138], rbx
0x140342ceb  lea     rdx, aCancellable; "Cancellable"
0x140342cf2  lea     rcx, [rsp+178h+var_148]
0x140342cf7  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140342cfc  mov     rbx, rax
0x140342cff  test    rax, rax
0x140342d02  jz      short loc_140342D40
0x140342d04  mov     dword ptr [rsp+178h+var_128], r14d
0x140342d09  mov     rcx, [r15+20h]
0x140342d0d  mov     rdx, [rcx]
0x140342d10  mov     rax, [rdx+88h]
0x140342d17  lea     rdx, [rsp+178h+var_128]
0x140342d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140342d21  test    eax, eax
0x140342d23  js      short loc_140342D40
0x140342d25  mov     eax, dword ptr [rsp+178h+var_128]
0x140342d29  lea     edi, [r14+1]
0x140342d2d  and     al, dil
0x140342d30  neg     al
0x140342d32  sbb     ax, ax
0x140342d35  mov     [rbx+8], ax
0x140342d39  mov     word ptr [rbx], 0Bh
0x140342d3e  jmp     short loc_140342D45
0x140342d40  mov     edi, 1
0x140342d45  lea     r12, [r15-18h]
0x140342d49  cmp     [r12+40h], edi
0x140342d4e  jnz     short loc_140342D8B
0x140342d50  lea     rdx, aJobtype; "JobType"
0x140342d57  lea     rcx, [rsp+178h+var_148]
0x140342d5c  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140342d61  mov     rsi, rax
0x140342d64  test    rax, rax
0x140342d67  jz      short loc_140342D8B
0x140342d69  mov     rcx, r12
0x140342d6c  call    ?GetConcreteTaskType@WmiMsvmConcreteJob@@AEBA?AW4CONCRETE_TASK_TYPE@1@XZ; WmiMsvmConcreteJob::GetConcreteTaskType(void)
0x140342d71  mov     ebx, eax
0x140342d73  mov     rcx, rsi; this
0x140342d76  call    ?Clear@VmVariant@Vml@@QEAAXXZ; Vml::VmVariant::Clear(void)
0x140342d7b  mov     r13d, 12h
0x140342d81  mov     [rsi], r13w
0x140342d85  mov     [rsi+8], bx
0x140342d89  jmp     short loc_140342D91
0x140342d8b  mov     r13d, 12h
0x140342d91  cmp     dword ptr [r15+28h], 3
0x140342d96  jnz     short loc_140342DCB
0x140342d98  lea     rdx, aJobtype; "JobType"
0x140342d9f  lea     rcx, [rsp+178h+var_148]
0x140342da4  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140342da9  mov     rsi, rax
0x140342dac  test    rax, rax
0x140342daf  jz      short loc_140342DCB
0x140342db1  mov     rcx, r12
0x140342db4  call    ?GetMigrationTaskType@WmiMsvmConcreteJob@@AEBA?AW4MIGRATION_TASK_TYPE@1@XZ; WmiMsvmConcreteJob::GetMigrationTaskType(void)
0x140342db9  mov     ebx, eax
0x140342dbb  mov     rcx, rsi; this
0x140342dbe  call    ?Clear@VmVariant@Vml@@QEAAXXZ; Vml::VmVariant::Clear(void)
0x140342dc3  mov     [rsi], r13w
0x140342dc7  mov     [rsi+8], bx
0x140342dcb  cmp     dword ptr [r15+28h], 2
0x140342dd0  jnz     loc_140342F51
0x140342dd6  mov     [rsp+178h+pv], r14
0x140342dde  mov     [rsp+178h+var_128], r14
0x140342de3  mov     rcx, [r15+20h]
0x140342de7  mov     rax, [rcx]
0x140342dea  lea     rdx, [rsp+178h+pv]
0x140342df2  mov     rax, [rax+68h]
0x140342df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140342dfb  mov     rdx, [rsp+178h+pv]
0x140342e03  lea     rcx, [rsp+178h+var_128]
0x140342e08  call    ??$Reset@UIUnknown@@@?$VmComPtr@UIVmStorageTaskData@@@Vml@@QEAAXPEAUIUnknown@@@Z; Vml::VmComPtr<IVmStorageTaskData>::Reset<IUnknown>(IUnknown *)
0x140342e0d  lea     rdx, aChild; "Child"
0x140342e14  lea     rcx, [rsp+178h+var_148]
0x140342e19  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140342e1e  mov     rsi, rax
0x140342e21  lea     rdx, aParent; "Parent"
0x140342e28  lea     rcx, [rsp+178h+var_148]
0x140342e2d  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140342e32  mov     rbx, rax
0x140342e35  test    rsi, rsi
0x140342e38  jnz     short loc_140342E43
0x140342e3a  test    rax, rax
0x140342e3d  jz      loc_140342ED3
0x140342e43  mov     [rsp+178h+psz], r14
0x140342e4b  mov     [rsp+178h+psa], r14
0x140342e50  mov     rcx, [rsp+178h+var_128]
0x140342e55  test    rcx, rcx
0x140342e58  jz      short loc_140342EA0
0x140342e5a  mov     rax, [rcx]
0x140342e5d  lea     r8, [rsp+178h+psa]
0x140342e62  lea     rdx, [rsp+178h+psz]
0x140342e6a  mov     rax, [rax+18h]
0x140342e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140342e73  test    eax, eax
0x140342e75  js      short loc_140342EA0
0x140342e77  test    rsi, rsi
0x140342e7a  jz      short loc_140342E8C
0x140342e7c  mov     rdx, [rsp+178h+psz]; psz
0x140342e84  mov     rcx, rsi; pvarg
0x140342e87  call    ?Assign@VmVariant@Vml@@QEAAXPEBG@Z; Vml::VmVariant::Assign(ushort const *)
0x140342e8c  test    rbx, rbx
0x140342e8f  jz      short loc_140342EBB
0x140342e91  mov     rdx, [rsp+178h+psa]; psz
0x140342e96  mov     rcx, rbx; pvarg
0x140342e99  call    ?Assign@VmVariant@Vml@@QEAAXPEBG@Z; Vml::VmVariant::Assign(ushort const *)
0x140342e9e  jmp     short loc_140342EBB
0x140342ea0  test    rsi, rsi
0x140342ea3  jz      short loc_140342EAD
0x140342ea5  mov     rcx, rsi; this
0x140342ea8  call    ?Clear@VmVariant@Vml@@QEAAXXZ; Vml::VmVariant::Clear(void)
0x140342ead  test    rbx, rbx
0x140342eb0  jz      short loc_140342EBB
0x140342eb2  mov     rcx, rbx; this
0x140342eb5  call    ?Clear@VmVariant@Vml@@QEAAXXZ; Vml::VmVariant::Clear(void)
0x140342eba  nop
0x140342ebb  lea     rcx, [rsp+178h+psa]; this
0x140342ec0  call    ??1VmBstr@Vml@@QEAA@XZ; Vml::VmBstr::~VmBstr(void)
0x140342ec5  nop
0x140342ec6  lea     rcx, [rsp+178h+psz]; this
0x140342ece  call    ??1VmBstr@Vml@@QEAA@XZ; Vml::VmBstr::~VmBstr(void)
0x140342ed3  lea     rdx, aJobcompletions; "JobCompletionStatusCode"
0x140342eda  lea     rcx, [rsp+178h+var_148]
0x140342edf  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140342ee4  mov     rsi, rax
0x140342ee7  test    rax, rax
0x140342eea  jz      short loc_140342F06
0x140342eec  mov     rcx, r12; this
0x140342eef  call    ?GetErrorHResult@WmiMsvmConcreteJob@@AEBAJXZ; WmiMsvmConcreteJob::GetErrorHResult(void)
0x140342ef4  mov     ebx, eax
0x140342ef6  mov     rcx, rsi; this
0x140342ef9  call    ?Clear@VmVariant@Vml@@QEAAXXZ; Vml::VmVariant::Clear(void)
0x140342efe  mov     word ptr [rsi], 3
0x140342f03  mov     [rsi+8], ebx
0x140342f06  lea     rdx, aJobtype; "JobType"
0x140342f0d  lea     rcx, [rsp+178h+var_148]
0x140342f12  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140342f17  mov     rsi, rax
0x140342f1a  test    rax, rax
0x140342f1d  jz      short loc_140342F39
0x140342f1f  mov     rcx, r12
0x140342f22  call    ?GetDiskTaskType@WmiMsvmConcreteJob@@AEBA?AW4DISK_TASK_TYPE@1@XZ; WmiMsvmConcreteJob::GetDiskTaskType(void)
0x140342f27  mov     ebx, eax
0x140342f29  mov     rcx, rsi; this
0x140342f2c  call    ?Clear@VmVariant@Vml@@QEAAXXZ; Vml::VmVariant::Clear(void)
0x140342f31  mov     [rsi], r13w
0x140342f35  mov     [rsi+8], bx
0x140342f39  lea     rcx, [rsp+178h+var_128]; void *
0x140342f3e  call    ??1?$VmComPtr@UIVssAsync@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(void)
0x140342f43  nop
0x140342f44  lea     rcx, [rsp+178h+pv]; void *
0x140342f4c  call    ??1?$VmComPtr@UIVssAsync@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(void)
0x140342f51  lea     rdx, aDeleteoncomple; "DeleteOnCompletion"
0x140342f58  lea     rcx, [rsp+178h+var_148]
0x140342f5d  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140342f62  mov     rsi, rax
0x140342f65  test    rax, rax
0x140342f68  jz      short loc_140342FA1
0x140342f6a  movzx   ebx, r14b
0x140342f6e  mov     dword ptr [rsp+178h+var_128], r14d
0x140342f73  mov     rcx, [r15+20h]
0x140342f77  mov     rdx, [rcx]
0x140342f7a  mov     rax, [rdx+0F0h]
0x140342f81  lea     rdx, [rsp+178h+var_128]
0x140342f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140342f8b  test    eax, eax
0x140342f8d  js      short loc_140342F97
0x140342f8f  cmp     dword ptr [rsp+178h+var_128], r14d
0x140342f94  cmovz   ebx, edi
0x140342f97  mov     dl, bl; bool
0x140342f99  mov     rcx, rsi; this
0x140342f9c  call    ?Assign@VmVariant@Vml@@QEAAX_N@Z; Vml::VmVariant::Assign(bool)
0x140342fa1  lea     rdx, aElapsedtime; "ElapsedTime"
0x140342fa8  lea     rcx, [rsp+178h+var_148]
0x140342fad  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140342fb2  mov     rsi, rax
0x140342fb5  test    rax, rax
0x140342fb8  jz      short loc_140342FFA
0x140342fba  mov     qword ptr [rsp+178h+var_B8.Data1], r14
0x140342fc2  mov     rcx, [r15+20h]
0x140342fc6  mov     rdx, [rcx]
0x140342fc9  mov     rax, [rdx+0D8h]
0x140342fd0  lea     rdx, [rsp+178h+var_B8]
0x140342fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140342fdd  test    eax, eax
0x140342fdf  js      short loc_140342FFA
0x140342fe1  mov     rbx, qword ptr [rsp+178h+var_B8.Data1]
0x140342fe9  mov     rcx, rsi; this
0x140342fec  call    ?Clear@VmVariant@Vml@@QEAAXXZ; Vml::VmVariant::Clear(void)
0x140342ff1  mov     word ptr [rsi], 15h
0x140342ff6  mov     [rsi+8], rbx
0x140342ffa  lea     rdx, aErrorcode; "ErrorCode"
0x140343001  lea     rcx, [rsp+178h+var_148]
0x140343006  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x14034300b  mov     rsi, rax
0x14034300e  test    rax, rax
0x140343011  jz      short loc_140343034
0x140343013  mov     rcx, r12; this
0x140343016  call    ?GetErrorHResult@WmiMsvmConcreteJob@@AEBAJXZ; WmiMsvmConcreteJob::GetErrorHResult(void)
0x14034301b  mov     ecx, eax; int
0x14034301d  call    ?VmWmiMethodStatusFromHResult@@YAIJ@Z; VmWmiMethodStatusFromHResult(long)
0x140343022  mov     ebx, eax
0x140343024  mov     rcx, rsi; this
0x140343027  call    ?Clear@VmVariant@Vml@@QEAAXXZ; Vml::VmVariant::Clear(void)
0x14034302c  mov     [rsi], r13w
0x140343030  mov     [rsi+8], bx
0x140343034  lea     rdx, aErrordescripti; "ErrorDescription"
0x14034303b  lea     rcx, [rsp+178h+var_148]
0x140343040  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140343045  mov     rbx, rax
0x140343048  test    rax, rax
0x14034304b  jz      short loc_140343074
0x14034304d  mov     rcx, [r15+20h]
0x140343051  mov     rdx, [rcx]
0x140343054  lea     r8, [rax+8]
0x140343058  mov     rax, [rdx+0A0h]
0x14034305f  xor     edx, edx
0x140343061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140343066  test    eax, eax
0x140343068  js      short loc_140343074
0x14034306a  mov     esi, 8
0x14034306f  mov     [rbx], si
0x140343072  jmp     short loc_140343079
0x140343074  mov     esi, 8
0x140343079  lea     rdx, aErrorsummaryde; "ErrorSummaryDescription"
0x140343080  lea     rcx, [rsp+178h+var_148]
0x140343085  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x14034308a  mov     rbx, rax
0x14034308d  test    rax, rax
0x140343090  jz      short loc_1403430B2
0x140343092  mov     rcx, [r15+20h]
0x140343096  mov     rdx, [rcx]
0x140343099  lea     r8, [rax+8]
0x14034309d  mov     rax, [rdx+0A8h]
0x1403430a4  xor     edx, edx
0x1403430a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1403430ab  test    eax, eax
0x1403430ad  js      short loc_1403430B2
0x1403430af  mov     [rbx], si
0x1403430b2  lea     rdx, aInstalldate; "InstallDate"
0x1403430b9  lea     rcx, [rsp+178h+var_148]
0x1403430be  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x1403430c3  test    rax, rax
0x1403430c6  jz      short loc_1403430E0
0x1403430c8  mov     qword ptr [rsp+178h+var_B8.Data1], r14
0x1403430d0  lea     rdx, [rsp+178h+var_B8]; lpFileTime
0x1403430d8  mov     rcx, rax; pvarg
0x1403430db  call    ?Assign@VmVariant@Vml@@QEAAXAEBU_FILETIME@@@Z; Vml::VmVariant::Assign(_FILETIME const &)
0x1403430e0  lea     rdx, aInstanceid; "InstanceId"
0x1403430e7  lea     rcx, [rsp+178h+var_148]
0x1403430ec  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x1403430f1  mov     rbx, rax
0x1403430f4  test    rax, rax
0x1403430f7  jz      loc_140343192
0x1403430fd  xorps   xmm0, xmm0
0x140343100  movdqa  xmmword ptr [rsp+178h+var_B8.Data1], xmm0
0x140343109  mov     rcx, [r15+20h]
0x14034310d  mov     rdx, [rcx]
0x140343110  mov     rax, [rdx+78h]
0x140343114  lea     rdx, [rsp+178h+var_B8]
0x14034311c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140343121  test    eax, eax
0x140343123  js      short loc_140343192
0x140343125  xorps   xmm0, xmm0
0x140343128  movups  xmmword ptr [rsp+178h+pv], xmm0
0x140343130  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140343138  movdqu  [rsp+178h+var_E8], xmm1
0x140343141  mov     word ptr [rsp+178h+pv], r14w
0x14034314a  xor     r8d, r8d
0x14034314d  lea     rdx, [rsp+178h+pv]; Src
0x140343155  lea     rcx, [rsp+178h+var_B8]; struct _GUID *
0x14034315d  call    ?ToString@VmGuid@Vml@@SAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Vml::VmGuid::ToString(_GUID const &,std::wstring &,int)
0x140343162  lea     rdx, [rsp+178h+pv]
0x14034316a  cmp     qword ptr [rsp+178h+var_E8+8], 7
0x140343173  cmova   rdx, [rsp+178h+pv]; psz
0x14034317c  mov     rcx, rbx; pvarg
0x14034317f  call    ?Assign@VmVariant@Vml@@QEAAXPEBG@Z; Vml::VmVariant::Assign(ushort const *)
0x140343184  nop
0x140343185  lea     rcx, [rsp+178h+pv]
0x14034318d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
