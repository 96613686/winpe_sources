# CVssWriterPublisherFilter::PrepareToFire(_GUID const &,ushort *,IFiringControl *)

- ea: `0x14001b9f0`
- end: `0x14001c842`
- name: `?PrepareToFire@CVssWriterPublisherFilter@@UEAAJAEBU_GUID@@PEAGPEAUIFiringControl@@@Z`
- size: `3666`
- prototype: `__int64 __fastcall(CVssWriterPublisherFilter *__hidden this, const struct _GUID *, unsigned __int16 *, struct IFiringControl *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x140006020`
- `0x1400088fc`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013c60`
- `0x140019e30`
- `0x14001b9f0`
- `0x14001c848`
- `0x14001d750`
- `0x140026f60`
- `0x140031760`
- `0x14003a8f0`
- `0x14003c160`
- `0x140058c78`
- `0x140070fcc`
- `0x140091560`
- `0x1400921dc`
- `0x1400a0740`
- `0x1400ceac0`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001bae0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001bae0`
- `VssTrace!__imp_VssTraceMessage` at `0x14001c5cb`
- `VssTrace!__imp_VssTraceMessage` at `0x14001c5cb`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001c2c9`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001c2c9`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001bb38`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001bb38`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c111`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c1f1`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c34b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c111`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c1f1`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c34b`
- `OLEAUT32!__imp_VariantInit` at `0x14001c0d2`
- `OLEAUT32!__imp_VariantInit` at `0x14001c306`
- `OLEAUT32!__imp_VariantInit` at `0x14001c0d2`
- `OLEAUT32!__imp_VariantInit` at `0x14001c306`
- `OLEAUT32!__imp_VariantClear` at `0x14001c157`
- `OLEAUT32!__imp_VariantClear` at `0x14001c3a6`
- `OLEAUT32!__imp_VariantClear` at `0x14001c408`
- `OLEAUT32!__imp_VariantClear` at `0x14001c7c5`
- `OLEAUT32!__imp_VariantClear` at `0x14001c157`
- `OLEAUT32!__imp_VariantClear` at `0x14001c3a6`
- `OLEAUT32!__imp_VariantClear` at `0x14001c408`
- `OLEAUT32!__imp_VariantClear` at `0x14001c7c5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001c141`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001c383`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001c141`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001c383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c03d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c063`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c03d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c063`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c228`

## string_xrefs

- `0x14001ba2d`: `CVssWriterPublisherFilter::PrepareToFire`
- `0x14001bc1f`: `CVssWriterPublisherFilter::PrepareToFire`
- `0x14001c169`: `CVssWriterPublisherFilter::PrepareToFire`
- `0x14001c41d`: `CVssWriterPublisherFilter::PrepareToFire`
- `0x14001c708`: `CVssWriterPublisherFilter::PrepareToFire`
- `0x14001c821`: `CVssWriterPublisherFilter::PrepareToFire`
- `0x14001c486`: `Firing subscriber SID (%s) for method (%s)`
- `0x14001c1d2`: `Subscriber with SID (%s) for method (%s) was not fired.`
- `0x14001c0e2`: `WriterInstanceId`
- `0x14001c316`: `WriterId`
- `0x14001c69c`: `IEventSubscription::get_OwnerSID`
- `0x14001c76c`: `Subscriber with SID (%s) is not allowed to fire`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall CVssWriterPublisherFilter::PrepareToFire(
        PACL *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        struct IFiringControl *a4)
{
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  int v11; // ebx
  __int64 i; // rbx
  void *v13; // rcx
  int v14; // ebx
  __int64 j; // rbx
  void *v16; // rcx
  int v17; // ebx
  __int64 k; // rbx
  void *v19; // rcx
  int v20; // ebx
  __int64 m; // rbx
  void *v22; // rcx
  int v23; // ebx
  __int64 n; // rbx
  void *v25; // rcx
  int ii; // ebx
  char IsSidAllowedToFire; // bl
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, _QWORD, VARIANTARG *); // rdi
  ATL::CComBSTR *v30; // rax
  int v31; // ebx
  unsigned int v32; // ebx
  __int64 (__fastcall *v34)(__int64, _QWORD, VARIANTARG *); // rdi
  ATL::CComBSTR *v35; // rax
  unsigned int jj; // edx
  unsigned int kk; // edx
  struct _ACL *v38; // rcx
  __int64 v39; // rax
  int v40; // ebx
  struct _ACL *v41; // rcx
  __int64 v42; // rax
  CVssDebugInfo *v43; // rax
  CVssDebugInfo *v44; // rax
  CVssDebugInfo *v45; // rax
  CVssDebugInfo *v46; // rax
  CVssDebugInfo *v47; // rax
  ATL::CComBSTR *v48; // rax
  char v49; // al
  CVssDebugInfo *v50; // rax
  BSTR bstrString; // [rsp+58h] [rbp-2B0h] BYREF
  BSTR v52; // [rsp+60h] [rbp-2A8h] BYREF
  __int64 v53; // [rsp+68h] [rbp-2A0h] BYREF
  __int64 v54; // [rsp+70h] [rbp-298h] BYREF
  const unsigned __int16 *v55; // [rsp+78h] [rbp-290h] BYREF
  const unsigned __int16 *v56; // [rsp+80h] [rbp-288h]
  const unsigned __int16 *v57; // [rsp+88h] [rbp-280h]
  int v58; // [rsp+90h] [rbp-278h]
  int v59; // [rsp+94h] [rbp-274h]
  int v60; // [rsp+98h] [rbp-270h]
  LPVOID pv[15]; // [rsp+A0h] [rbp-268h] BYREF
  int v62; // [rsp+118h] [rbp-1F0h]
  VARIANTARG pvarg; // [rsp+120h] [rbp-1E8h] BYREF
  __int64 (__fastcall ***v64)(_QWORD, GUID *, __int64 *); // [rsp+138h] [rbp-1D0h] BYREF
  unsigned __int64 v65; // [rsp+140h] [rbp-1C8h] BYREF
  int v66; // [rsp+148h] [rbp-1C0h]
  const unsigned __int16 *v67; // [rsp+150h] [rbp-1B8h]
  const unsigned __int16 *v68; // [rsp+158h] [rbp-1B0h]
  unsigned int v69; // [rsp+160h] [rbp-1A8h]
  unsigned int v70; // [rsp+164h] [rbp-1A4h]
  const unsigned __int16 *v71; // [rsp+168h] [rbp-1A0h]
  unsigned int v72; // [rsp+170h] [rbp-198h]
  DWORD TickCount; // [rsp+174h] [rbp-194h]
  int v74; // [rsp+178h] [rbp-190h]
  __int128 v75; // [rsp+180h] [rbp-188h]
  __int128 v76; // [rsp+190h] [rbp-178h]
  __int64 v77; // [rsp+1A0h] [rbp-168h]
  int v78; // [rsp+1B0h] [rbp-158h] BYREF
  int v79; // [rsp+1B4h] [rbp-154h] BYREF
  __int64 v80; // [rsp+1B8h] [rbp-150h] BYREF
  BSTR v81; // [rsp+1C0h] [rbp-148h] BYREF
  void **v82; // [rsp+1C8h] [rbp-140h] BYREF
  void *v83; // [rsp+1D0h] [rbp-138h]
  char v84[8]; // [rsp+1E0h] [rbp-128h] BYREF
  _QWORD v85[3]; // [rsp+1E8h] [rbp-120h] BYREF
  int v86; // [rsp+200h] [rbp-108h]
  int v87; // [rsp+204h] [rbp-104h]
  int v88; // [rsp+208h] [rbp-100h]
  char v89[120]; // [rsp+210h] [rbp-F8h] BYREF
  int v90; // [rsp+288h] [rbp-80h]
  GUID v91; // [rsp+2A0h] [rbp-68h] BYREF
  GUID pclsid; // [rsp+2B0h] [rbp-58h] BYREF

  v55 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
  v56 = L"CVssWriterPublisherFilter::PrepareToFire";
  v57 = L"FLTRC";
  v58 = 303;
  v59 = 11;
  v60 = 255;
  v62 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v66 = 0;
  v71 = L"CVssWriterPublisherFilter::PrepareToFire";
  v67 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
  v68 = L"FLTRC";
  v69 = 303;
  v70 = 11;
  TickCount = GetTickCount();
  v74 = 255;
  v65 = 0xFFFFFFFF00000000uLL;
  v77 = 0;
  v75 = 0;
  v76 = 0;
  v54 = 0;
  if ( (int)VssGetTracingContextPerThread(&v54) < 0 || (int)VssSetTracingContextPerThread(&v65) < 0 )
  {
    v8 = v77;
  }
  else
  {
    v8 = v54;
    v77 = v54;
  }
  if ( v8 )
    v72 = *(_DWORD *)(v8 + 48) + 1;
  else
    v72 = 0;
  v9 = 160;
  if ( v74 != 255 )
    v9 = v74;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v65, v70) )
    VssTraceMessage(v67, v68, v69, v72, v70, v71, L"ENTER", v9, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v55);
  v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_6050b110_ce87_4126_a114_50aefcfc95f8.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_6050b110_ce87_4126_a114_50aefcfc95f8.Data1 )
    v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_6050b110_ce87_4126_a114_50aefcfc95f8.Data4;
  if ( !v10 )
  {
    CVssWriterPublisherFilter::SetupGenericSids((CVssWriterPublisherFilter *)this);
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v54);
    v78 = 0;
    v11 = (*(__int64 (__fastcall **)(PACL, GUID *, unsigned __int16 *, _QWORD, int *, __int64 *))(*(_QWORD *)this[1]
                                                                                                + 32LL))(
            this[1],
            &GUID_6050b110_ce87_4126_a114_50aefcfc95f8,
            a3,
            0,
            &v78,
            &v54);
    v66 = v11;
    v55 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
    v56 = L"CVssWriterPublisherFilter::PrepareToFire";
    v57 = L"FLTRC";
    v58 = 328;
    v59 = 11;
    v60 = 255;
    v62 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    bstrString = (BSTR)&v55;
    if ( v11 < 0 )
    {
      v43 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v85, (const struct CVssDebugInfo *)&v55);
      CVssFunctionTracer::TranslateError(&v65, v43, (unsigned int)v11, L"IMultiInterfaceEventControl::GetSubscriptions");
    }
    if ( HIBYTE(v62) )
    {
      for ( i = 0; i != 15; ++i )
      {
        v13 = pv[i];
        if ( v13 )
        {
          CoTaskMemFree(v13);
          pv[i] = 0;
        }
      }
    }
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v80);
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 72LL))(v54, &v80);
    v66 = v14;
    v55 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
    v56 = L"CVssWriterPublisherFilter::PrepareToFire";
    v57 = L"FLTRC";
    v58 = 333;
    v59 = 11;
    v60 = 255;
    v62 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    bstrString = (BSTR)&v55;
    if ( v14 < 0 )
    {
      v44 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v85, (const struct CVssDebugInfo *)&v55);
      CVssFunctionTracer::TranslateError(&v65, v44, (unsigned int)v14, L"IEventObjectCollection::get_NewEnum");
    }
    if ( HIBYTE(v62) )
    {
      for ( j = 0; j != 15; ++j )
      {
        v16 = pv[j];
        if ( v16 )
        {
          CoTaskMemFree(v16);
          pv[j] = 0;
        }
      }
    }
    while ( 1 )
    {
      ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v53);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v64);
      v79 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v80 + 32LL))(
              v80,
              1,
              &v64,
              &v79);
      v66 = v17;
      v55 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
      v56 = L"CVssWriterPublisherFilter::PrepareToFire";
      v57 = L"FLTRC";
      v58 = 343;
      v59 = 11;
      v60 = 255;
      v62 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      if ( v17 < 0 )
      {
        v45 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v85, (const struct CVssDebugInfo *)&v55);
        CVssFunctionTracer::TranslateError(&v65, v45, (unsigned int)v17, L"IEnumEventObject::Next");
      }
      if ( HIBYTE(v62) )
      {
        for ( k = 0; k != 15; ++k )
        {
          v19 = pv[k];
          if ( v19 )
          {
            CoTaskMemFree(v19);
            pv[k] = 0;
          }
        }
        v17 = v66;
      }
      if ( v17 == 1 )
      {
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v64);
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v53);
        v66 = 0;
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v80);
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v54);
        v32 = v66;
        CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v65);
        return v32;
      }
      v20 = (**v64)(v64, &GUID_4a6b0e15_2e38_11d1_9965_00c04fbbb345, &v53);
      v66 = v20;
      v55 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
      v56 = L"CVssWriterPublisherFilter::PrepareToFire";
      v57 = L"FLTRC";
      v58 = 348;
      v59 = 11;
      v60 = 255;
      v62 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      if ( v20 < 0 )
      {
        v46 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v85, (const struct CVssDebugInfo *)&v55);
        CVssFunctionTracer::TranslateError(&v65, v46, (unsigned int)v20, L"IUnknown::QueryInterface");
      }
      if ( HIBYTE(v62) )
      {
        for ( m = 0; m != 15; ++m )
        {
          v22 = pv[m];
          if ( v22 )
          {
            CoTaskMemFree(v22);
            pv[m] = 0;
          }
        }
      }
      v52 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v53 + 184LL))(v53, &v52);
      v66 = v23;
      v55 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
      v56 = L"CVssWriterPublisherFilter::PrepareToFire";
      v57 = L"FLTRC";
      v58 = 353;
      v59 = 11;
      v60 = 255;
      v62 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      if ( v23 < 0 )
      {
        v47 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v85, (const struct CVssDebugInfo *)&v55);
        CVssFunctionTracer::TranslateError(&v65, v47, (unsigned int)v23, L"IEventSubscription::get_OwnerSID");
      }
      if ( HIBYTE(v62) )
      {
        for ( n = 0; n != 15; ++n )
        {
          v25 = pv[n];
          if ( v25 )
          {
            CoTaskMemFree(v25);
            pv[n] = 0;
          }
        }
      }
      for ( ii = 0; ii < *((_DWORD *)this + 50); ++ii )
      {
        if ( VssHashAreKeysEqual<ATL::CComBSTR>((BSTR *)&this[23][ii], &v52) )
        {
          if ( ii != -1 )
          {
            IsSidAllowedToFire = *(&this[24]->AclRevision + ii);
            goto LABEL_50;
          }
          break;
        }
      }
      v83 = 0;
      v82 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
      CAutoSid::CreateFromString((CAutoSid *)&v82, v52);
      IsSidAllowedToFire = CVssSidCollection::IsSidAllowedToFire(this + 7, v83);
      if ( !IsSidAllowedToFire )
      {
        v55 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
        v56 = L"CVssWriterPublisherFilter::PrepareToFire";
        v57 = L"FLTRC";
        v58 = 367;
        v59 = 11;
        v60 = 255;
        v62 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        CVssFunctionTracer::Trace(&v65, &v55, L"Subscriber with SID (%s) is not allowed to fire", v52);
      }
      v48 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v84, (const struct ATL::CComBSTR *)&v52);
      CVssSimpleMap<ATL::CComBSTR,bool>::Add((__int64)(this + 23), v48, IsSidAllowedToFire);
      CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v82);
LABEL_50:
      if ( IsSidAllowedToFire )
      {
        v28 = v53;
        if ( *((_DWORD *)this + 8) )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          v34 = *(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v28 + 280LL);
          v35 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v81, L"WriterId");
          LODWORD(v34) = v34(v28, *(_QWORD *)v35, &pvarg);
          SysFreeString(v81);
          if ( (_DWORD)v34 )
            goto LABEL_57;
          if ( pvarg.vt != 8 )
            goto LABEL_57;
          v91 = 0;
          if ( CLSIDFromString(pvarg.bstrVal, &v91) < 0 )
            goto LABEL_57;
          for ( jj = 0; ; ++jj )
          {
            if ( jj >= *((_DWORD *)this + 8) )
            {
              VariantClear(&pvarg);
              goto LABEL_52;
            }
            v41 = &this[3][2 * jj];
            v42 = *(_QWORD *)v41 - *(_QWORD *)&v91.Data1;
            if ( *v41 == *(_QWORD *)&v91.Data1 )
              v42 = *(_QWORD *)&v41[1] - *(_QWORD *)v91.Data4;
            if ( !v42 )
              break;
          }
          VariantClear(&pvarg);
          if ( !*((_BYTE *)this + 53) )
            goto LABEL_58;
          v49 = *((_BYTE *)this + 52);
        }
        else
        {
LABEL_52:
          if ( !*((_BYTE *)this + 52) )
          {
            if ( *((_DWORD *)this + 12) )
            {
              memset(&pvarg, 0, sizeof(pvarg));
              VariantInit(&pvarg);
              v29 = *(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v28 + 280LL);
              v30 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"WriterInstanceId");
              v31 = v29(v28, *(_QWORD *)v30, &pvarg);
              SysFreeString(bstrString);
              if ( !v31 && pvarg.vt == 8 )
              {
                pclsid = 0;
                if ( CLSIDFromString(pvarg.bstrVal, &pclsid) >= 0 )
                {
                  for ( kk = 0; kk < *((_DWORD *)this + 12); ++kk )
                  {
                    v38 = &this[5][2 * kk];
                    v39 = *(_QWORD *)v38 - *(_QWORD *)&pclsid.Data1;
                    if ( *v38 == *(_QWORD *)&pclsid.Data1 )
                      v39 = *(_QWORD *)&v38[1] - *(_QWORD *)pclsid.Data4;
                    if ( !v39 )
                    {
                      VariantClear(&pvarg);
                      goto LABEL_77;
                    }
                  }
                }
              }
LABEL_57:
              VariantClear(&pvarg);
            }
LABEL_58:
            v55 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
            v56 = L"CVssWriterPublisherFilter::PrepareToFire";
            v57 = L"FLTRC";
            v58 = 388;
            v59 = 11;
            v60 = 255;
            v62 = 0x1000000;
            memset_0(pv, 0, sizeof(pv));
            CVssFunctionTracer::Trace(&v65, &v55, L"Subscriber with SID (%s) for method (%s) was not fired.", v52, a3);
            goto LABEL_59;
          }
          v49 = *((_BYTE *)this + 53) == 0;
        }
        if ( !v49 )
          goto LABEL_58;
LABEL_77:
        v85[0] = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
        v85[1] = L"CVssWriterPublisherFilter::PrepareToFire";
        v85[2] = L"FLTRC";
        v86 = 382;
        v87 = 11;
        v88 = 255;
        v90 = 0x1000000;
        memset_0(v89, 0, sizeof(v89));
        CVssFunctionTracer::Trace(&v65, v85, L"Firing subscriber SID (%s) for method (%s)", v52, a3);
        v40 = ((__int64 (__fastcall *)(struct IFiringControl *, __int64))a4->lpVtbl->FireSubscription)(a4, v53);
        v66 = v40;
        v55 = L"base\\stor\\vss\\modules\\filter\\filter.cxx";
        v56 = L"CVssWriterPublisherFilter::PrepareToFire";
        v57 = L"FLTRC";
        v58 = 385;
        v59 = 11;
        v60 = 255;
        v62 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        if ( v40 < 0 )
        {
          v50 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v85, (const struct CVssDebugInfo *)&v55);
          CVssFunctionTracer::TranslateError(&v65, v50, (unsigned int)v40, L"FireSubscription");
        }
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v55);
      }
LABEL_59:
      SysFreeString(v52);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v64);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v53);
    }
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v65);
  return 2147942487LL;
}

```

## disassembly

```asm
0x14001b9f0  push    rbx
0x14001b9f2  push    rsi
0x14001b9f3  push    rdi
0x14001b9f4  push    r12
0x14001b9f6  push    r13
0x14001b9f8  push    r14
0x14001b9fa  push    r15
0x14001b9fc  sub     rsp, 2D0h
0x14001ba03  mov     rax, cs:__security_cookie
0x14001ba0a  xor     rax, rsp
0x14001ba0d  mov     [rsp+308h+var_48], rax
0x14001ba15  mov     r12, r9
0x14001ba18  mov     r15, r8
0x14001ba1b  mov     rdi, rdx
0x14001ba1e  mov     r14, rcx
0x14001ba21  lea     rsi, aBaseStorVssMod_33; "base\\stor\\vss\\modules\\filter\\filte"...
0x14001ba28  mov     [rsp+308h+var_290], rsi
0x14001ba2d  lea     rax, aCvsswriterpubl; "CVssWriterPublisherFilter::PrepareToFir"...
0x14001ba34  mov     [rsp+308h+var_288], rax
0x14001ba3c  lea     rax, aFltrc; "FLTRC"
0x14001ba43  mov     [rsp+308h+var_280], rax
0x14001ba4b  mov     [rsp+308h+var_278], 12Fh
0x14001ba56  mov     [rsp+308h+var_274], 0Bh
0x14001ba61  mov     [rsp+308h+var_270], 0FFh
0x14001ba6c  xor     r13d, r13d
0x14001ba6f  mov     [rsp+308h+var_1F0], 1000000h
0x14001ba7a  xor     edx, edx; Val
0x14001ba7c  mov     r8d, 78h ; 'x'; Size
0x14001ba82  lea     rcx, [rsp+308h+pv]; void *
0x14001ba8a  call    memset_0
0x14001ba8f  mov     [rsp+308h+var_1C0], r13d
0x14001ba97  mov     rax, [rsp+308h+var_288]
0x14001ba9f  mov     [rsp+308h+var_1A0], rax
0x14001baa7  mov     rax, [rsp+308h+var_290]
0x14001baac  mov     [rsp+308h+var_1B8], rax
0x14001bab4  mov     rax, [rsp+308h+var_280]
0x14001babc  mov     [rsp+308h+var_1B0], rax
0x14001bac4  mov     eax, [rsp+308h+var_278]
0x14001bacb  mov     [rsp+308h+var_1A8], eax
0x14001bad2  mov     eax, [rsp+308h+var_274]
0x14001bad9  mov     [rsp+308h+var_1A4], eax
0x14001bae0  call    cs:__imp_GetTickCount
0x14001bae6  mov     [rsp+308h+var_194], eax
0x14001baed  mov     [rsp+308h+var_1C4], 0FFFFFFFFh
0x14001baf8  mov     eax, [rsp+308h+var_270]
0x14001baff  mov     [rsp+308h+var_190], eax
0x14001bb06  mov     [rsp+308h+var_1C8], r13d
0x14001bb0e  mov     [rsp+308h+var_168], r13
0x14001bb16  xorps   xmm0, xmm0
0x14001bb19  movdqa  [rsp+308h+var_188], xmm0
0x14001bb22  xorps   xmm1, xmm1
0x14001bb25  movdqa  [rsp+308h+var_178], xmm1
0x14001bb2e  mov     [rsp+308h+var_298], r13
0x14001bb33  lea     rcx, [rsp+308h+var_298]
0x14001bb38  call    cs:__imp_VssGetTracingContextPerThread
0x14001bb3e  test    eax, eax
0x14001bb40  jns     loc_14001C2C1
0x14001bb46  mov     rax, [rsp+308h+var_168]
0x14001bb4e  test    rax, rax
0x14001bb51  jz      loc_14001C3B1
0x14001bb57  mov     eax, [rax+30h]
0x14001bb5a  inc     eax
0x14001bb5c  mov     [rsp+308h+var_198], eax
0x14001bb63  mov     ebx, 0A0h
0x14001bb68  cmp     [rsp+308h+var_190], 0FFh
0x14001bb73  cmovnz  ebx, [rsp+308h+var_190]
0x14001bb7b  mov     edx, [rsp+308h+var_1A4]; unsigned int
0x14001bb82  lea     rcx, [rsp+308h+var_1C8]; this
0x14001bb8a  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14001bb8f  test    eax, eax
0x14001bb91  jnz     loc_14001C57E
0x14001bb97  lea     rcx, [rsp+308h+var_290]; this
0x14001bb9c  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14001bba1  nop
0x14001bba2  mov     rax, [rdi]
0x14001bba5  sub     rax, qword ptr cs:_GUID_6050b110_ce87_4126_a114_50aefcfc95f8.Data1
0x14001bbac  jnz     short loc_14001BBB9
0x14001bbae  mov     rax, [rdi+8]
0x14001bbb2  sub     rax, qword ptr cs:_GUID_6050b110_ce87_4126_a114_50aefcfc95f8.Data4
0x14001bbb9  test    rax, rax
0x14001bbbc  jnz     loc_14001C2AD
0x14001bbc2  mov     rcx, r14; this
0x14001bbc5  call    ?SetupGenericSids@CVssWriterPublisherFilter@@AEAAXXZ; CVssWriterPublisherFilter::SetupGenericSids(void)
0x14001bbca  lea     rcx, [rsp+308h+var_298]
0x14001bbcf  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14001bbd4  nop
0x14001bbd5  mov     [rsp+308h+var_158], r13d
0x14001bbdd  mov     rcx, [r14+8]
0x14001bbe1  mov     rax, [rcx]
0x14001bbe4  lea     rdx, [rsp+308h+var_298]
0x14001bbe9  mov     [rsp+308h+var_2E0], rdx
0x14001bbee  lea     rdx, [rsp+308h+var_158]
0x14001bbf6  mov     [rsp+308h+var_2E8], rdx
0x14001bbfb  xor     r9d, r9d
0x14001bbfe  mov     r8, r15
0x14001bc01  lea     rdx, _GUID_6050b110_ce87_4126_a114_50aefcfc95f8
0x14001bc08  mov     rax, [rax+20h]
0x14001bc0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bc11  mov     ebx, eax
0x14001bc13  mov     [rsp+308h+var_1C0], eax
0x14001bc1a  mov     [rsp+308h+var_290], rsi
0x14001bc1f  lea     rdi, aCvsswriterpubl; "CVssWriterPublisherFilter::PrepareToFir"...
0x14001bc26  mov     [rsp+308h+var_288], rdi
0x14001bc2e  lea     rax, aFltrc; "FLTRC"
0x14001bc35  mov     [rsp+308h+var_280], rax
0x14001bc3d  mov     [rsp+308h+var_278], 148h
0x14001bc48  mov     [rsp+308h+var_274], 0Bh
0x14001bc53  mov     [rsp+308h+var_270], 0FFh
0x14001bc5e  mov     [rsp+308h+var_1F0], 1000000h
0x14001bc69  xor     edx, edx; Val
0x14001bc6b  mov     r8d, 78h ; 'x'; Size
0x14001bc71  lea     rcx, [rsp+308h+pv]; void *
0x14001bc79  call    memset_0
0x14001bc7e  lea     rax, [rsp+308h+var_290]
0x14001bc83  mov     [rsp+308h+bstrString], rax
0x14001bc88  test    ebx, ebx
0x14001bc8a  js      loc_14001C5D6
0x14001bc90  cmp     byte ptr [rsp+308h+var_1F0+3], 0
0x14001bc98  jz      short loc_14001BCBA
0x14001bc9a  mov     rbx, r13
0x14001bc9d  nop     dword ptr [rax]
0x14001bca0  mov     rcx, [rsp+rbx*8+308h+pv]; pv
0x14001bca8  test    rcx, rcx
0x14001bcab  jnz     loc_14001C215
0x14001bcb1  inc     rbx
0x14001bcb4  cmp     rbx, 0Fh
0x14001bcb8  jnz     short loc_14001BCA0
0x14001bcba  lea     rcx, [rsp+308h+var_150]
0x14001bcc2  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14001bcc7  nop
0x14001bcc8  mov     rcx, [rsp+308h+var_298]
0x14001bccd  mov     rax, [rcx]
0x14001bcd0  lea     rdx, [rsp+308h+var_150]
0x14001bcd8  mov     rax, [rax+48h]
0x14001bcdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bce1  mov     ebx, eax
0x14001bce3  mov     [rsp+308h+var_1C0], eax
0x14001bcea  mov     [rsp+308h+var_290], rsi
0x14001bcef  mov     [rsp+308h+var_288], rdi
0x14001bcf7  lea     rax, aFltrc; "FLTRC"
0x14001bcfe  mov     [rsp+308h+var_280], rax
0x14001bd06  mov     [rsp+308h+var_278], 14Dh
0x14001bd11  mov     [rsp+308h+var_274], 0Bh
0x14001bd1c  mov     [rsp+308h+var_270], 0FFh
0x14001bd27  mov     [rsp+308h+var_1F0], 1000000h
0x14001bd32  xor     edx, edx; Val
0x14001bd34  mov     r8d, 78h ; 'x'; Size
0x14001bd3a  lea     rcx, [rsp+308h+pv]; void *
0x14001bd42  call    memset_0
0x14001bd47  lea     rax, [rsp+308h+var_290]
0x14001bd4c  mov     [rsp+308h+bstrString], rax
0x14001bd51  test    ebx, ebx
0x14001bd53  js      loc_14001C603
0x14001bd59  cmp     byte ptr [rsp+308h+var_1F0+3], 0
0x14001bd61  jz      short loc_14001BD8A
0x14001bd63  mov     rbx, r13
0x14001bd66  nop     word ptr [rax+rax+00000000h]
0x14001bd70  mov     rcx, [rsp+rbx*8+308h+pv]; pv
0x14001bd78  test    rcx, rcx
0x14001bd7b  jnz     loc_14001C228
0x14001bd81  inc     rbx
0x14001bd84  cmp     rbx, 0Fh
0x14001bd88  jnz     short loc_14001BD70
0x14001bd8a  lea     rcx, [rsp+308h+var_2A0]
0x14001bd8f  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14001bd94  nop
0x14001bd95  lea     rcx, [rsp+308h+var_1D0]
0x14001bd9d  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14001bda2  nop
0x14001bda3  mov     [rsp+308h+var_154], r13d
0x14001bdab  mov     rcx, [rsp+308h+var_150]
0x14001bdb3  mov     rax, [rcx]
0x14001bdb6  lea     r9, [rsp+308h+var_154]
0x14001bdbe  lea     r8, [rsp+308h+var_1D0]
0x14001bdc6  mov     edx, 1
0x14001bdcb  mov     rax, [rax+20h]
0x14001bdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bdd4  mov     ebx, eax
0x14001bdd6  mov     [rsp+308h+var_1C0], eax
0x14001bddd  mov     [rsp+308h+var_290], rsi
0x14001bde2  mov     [rsp+308h+var_288], rdi
0x14001bdea  lea     rax, aFltrc; "FLTRC"
0x14001bdf1  mov     [rsp+308h+var_280], rax
0x14001bdf9  mov     [rsp+308h+var_278], 157h
0x14001be04  mov     [rsp+308h+var_274], 0Bh
0x14001be0f  mov     [rsp+308h+var_270], 0FFh
0x14001be1a  mov     [rsp+308h+var_1F0], 1000000h
0x14001be25  xor     edx, edx; Val
0x14001be27  mov     r8d, 78h ; 'x'; Size
0x14001be2d  lea     rcx, [rsp+308h+pv]; void *
0x14001be35  call    memset_0
0x14001be3a  lea     rax, [rsp+308h+var_290]
0x14001be3f  mov     [rsp+308h+var_2B8], rax
0x14001be44  test    ebx, ebx
0x14001be46  js      loc_14001C630
0x14001be4c  cmp     byte ptr [rsp+308h+var_1F0+3], 0
0x14001be54  jz      short loc_14001BE81
0x14001be56  mov     rbx, r13
0x14001be59  nop     dword ptr [rax+00000000h]
0x14001be60  mov     rcx, [rsp+rbx*8+308h+pv]; pv
0x14001be68  test    rcx, rcx
0x14001be6b  jnz     loc_14001C03D
0x14001be71  inc     rbx
0x14001be74  cmp     rbx, 0Fh
0x14001be78  jnz     short loc_14001BE60
0x14001be7a  mov     ebx, [rsp+308h+var_1C0]
0x14001be81  cmp     ebx, 1
0x14001be84  jz      loc_14001C23B
0x14001be8a  mov     rcx, [rsp+308h+var_1D0]
0x14001be92  mov     rax, [rcx]
0x14001be95  lea     r8, [rsp+308h+var_2A0]
0x14001be9a  lea     rdx, _GUID_4a6b0e15_2e38_11d1_9965_00c04fbbb345
0x14001bea1  mov     rax, [rax]
0x14001bea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bea9  mov     ebx, eax
0x14001beab  mov     [rsp+308h+var_1C0], eax
0x14001beb2  mov     [rsp+308h+var_290], rsi
0x14001beb7  mov     [rsp+308h+var_288], rdi
0x14001bebf  lea     rax, aFltrc; "FLTRC"
0x14001bec6  mov     [rsp+308h+var_280], rax
0x14001bece  mov     [rsp+308h+var_278], 15Ch
0x14001bed9  mov     [rsp+308h+var_274], 0Bh
0x14001bee4  mov     [rsp+308h+var_270], 0FFh
0x14001beef  mov     [rsp+308h+var_1F0], 1000000h
0x14001befa  xor     edx, edx; Val
0x14001befc  mov     r8d, 78h ; 'x'; Size
0x14001bf02  lea     rcx, [rsp+308h+pv]; void *
0x14001bf0a  call    memset_0
0x14001bf0f  lea     rax, [rsp+308h+var_290]
0x14001bf14  mov     [rsp+308h+var_2B8], rax
0x14001bf19  test    ebx, ebx
0x14001bf1b  js      loc_14001C65D
0x14001bf21  cmp     byte ptr [rsp+308h+var_1F0+3], 0
0x14001bf29  jz      short loc_14001BF4A
0x14001bf2b  mov     rbx, r13
0x14001bf2e  xchg    ax, ax
0x14001bf30  mov     rcx, [rsp+rbx*8+308h+pv]; pv
0x14001bf38  test    rcx, rcx
0x14001bf3b  jnz     loc_14001C050
0x14001bf41  inc     rbx
0x14001bf44  cmp     rbx, 0Fh
0x14001bf48  jnz     short loc_14001BF30
0x14001bf4a  mov     [rsp+308h+var_2A8], r13
0x14001bf4f  mov     rcx, [rsp+308h+var_2A0]
0x14001bf54  mov     rax, [rcx]
0x14001bf57  lea     rdx, [rsp+308h+var_2A8]
0x14001bf5c  mov     rax, [rax+0B8h]
0x14001bf63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf68  mov     ebx, eax
0x14001bf6a  mov     [rsp+308h+var_1C0], eax
0x14001bf71  mov     [rsp+308h+var_290], rsi
0x14001bf76  mov     [rsp+308h+var_288], rdi
0x14001bf7e  lea     rsi, aFltrc; "FLTRC"
0x14001bf85  mov     [rsp+308h+var_280], rsi
0x14001bf8d  mov     [rsp+308h+var_278], 161h
0x14001bf98  mov     [rsp+308h+var_274], 0Bh
0x14001bfa3  mov     [rsp+308h+var_270], 0FFh
0x14001bfae  mov     [rsp+308h+var_1F0], 1000000h
0x14001bfb9  xor     edx, edx; Val
0x14001bfbb  mov     r8d, 78h ; 'x'; Size
0x14001bfc1  lea     rcx, [rsp+308h+pv]; void *
0x14001bfc9  call    memset_0
0x14001bfce  lea     rax, [rsp+308h+var_290]
0x14001bfd3  mov     [rsp+308h+var_2B8], rax
0x14001bfd8  test    ebx, ebx
0x14001bfda  js      loc_14001C68A
0x14001bfe0  cmp     byte ptr [rsp+308h+var_1F0+3], 0
0x14001bfe8  jz      short loc_14001C006
0x14001bfea  mov     rbx, r13
0x14001bfed  nop     dword ptr [rax]
0x14001bff0  mov     rcx, [rsp+rbx*8+308h+pv]; pv
0x14001bff8  test    rcx, rcx
0x14001bffb  jnz     short loc_14001C063
0x14001bffd  inc     rbx
0x14001c000  cmp     rbx, 0Fh
0x14001c004  jnz     short loc_14001BFF0
0x14001c006  mov     ebx, r13d
0x14001c009  nop     dword ptr [rax+00000000h]
0x14001c010  cmp     ebx, [r14+0C8h]
0x14001c017  jge     loc_14001C6B7
0x14001c01d  movsxd  rsi, ebx
0x14001c020  mov     rax, [r14+0B8h]
0x14001c027  lea     rcx, [rax+rsi*8]
0x14001c02b  lea     rdx, [rsp+308h+var_2A8]
0x14001c030  call    ??$VssHashAreKeysEqual@VCComBSTR@ATL@@@@YAHAEBVCComBSTR@ATL@@0@Z; VssHashAreKeysEqual<ATL::CComBSTR>(ATL::CComBSTR const &,ATL::CComBSTR const &)
0x14001c035  test    eax, eax
0x14001c037  jnz     short loc_14001C073
0x14001c039  inc     ebx
0x14001c03b  jmp     short loc_14001C010
0x14001c03d  call    cs:__imp_CoTaskMemFree
0x14001c043  mov     [rsp+rbx*8+308h+pv], r13
0x14001c04b  jmp     loc_14001BE71
0x14001c050  call    cs:__imp_CoTaskMemFree
0x14001c056  mov     [rsp+rbx*8+308h+pv], r13
0x14001c05e  jmp     loc_14001BF41
0x14001c063  call    cs:__imp_CoTaskMemFree
0x14001c069  mov     [rsp+rbx*8+308h+pv], r13
0x14001c071  jmp     short loc_14001BFFD
0x14001c073  cmp     ebx, 0FFFFFFFFh
0x14001c076  jz      loc_14001C6B7
  ... truncated ...
```
