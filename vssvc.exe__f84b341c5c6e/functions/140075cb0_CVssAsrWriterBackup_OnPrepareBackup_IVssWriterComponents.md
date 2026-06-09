# CVssAsrWriterBackup::OnPrepareBackup(IVssWriterComponents *)

- ea: `0x140075cb0`
- end: `0x1400768bc`
- name: `?OnPrepareBackup@CVssAsrWriterBackup@@UEAA_NPEAVIVssWriterComponents@@@Z`
- size: `3084`
- prototype: `bool __fastcall(CVssAsrWriterBackup *__hidden this, struct IVssWriterComponents *)`
- caller_count: `0`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400088fc`
- `0x140008908`
- `0x140009a40`
- `0x14000a834`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x14003c160`
- `0x14003fc04`
- `0x1400518bc`
- `0x140055ba4`
- `0x140055bbc`
- `0x14005bcf8`
- `0x140075cb0`
- `0x1400921dc`
- `0x140099818`
- `0x1400a18bc`
- `0x1400ccf30`
- `0x1400d0474`
- `0x1400da2e4`
- `0x1400da314`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140076354`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140076354`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x140076376`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x140076376`
- `OLEAUT32!__imp_SysFreeString` at `0x1400761b8`
- `OLEAUT32!__imp_SysFreeString` at `0x140076247`
- `OLEAUT32!__imp_SysFreeString` at `0x14007685a`
- `OLEAUT32!__imp_SysFreeString` at `0x140076869`
- `OLEAUT32!__imp_SysFreeString` at `0x1400761b8`
- `OLEAUT32!__imp_SysFreeString` at `0x140076247`
- `OLEAUT32!__imp_SysFreeString` at `0x14007685a`
- `OLEAUT32!__imp_SysFreeString` at `0x140076869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140075ff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140076088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007644d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140075ff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140076088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007644d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400767f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140076806`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007681c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140076837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007684b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400767f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140076806`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007681c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140076837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007684b`

## string_xrefs

- `0x140075ccc`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x140076755`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x14007663f`: `IVssAsrWriterBackup::GetAsrMetadata`
- `0x140075fd4`: `IVssWriterComponents::GetComponentCount`
- `0x140076226`: `IVssComponent::GetComponentName`
- `0x140076197`: `IVssWriterComponents::GetComponent`
- `0x140075e02`: `ASR Writer`
- `0x140075ec4`: `ASR Writer`
- `0x1400765e9`: `ASR Writer`
- `0x140075cd8`: `CVssAsrWriterBackup::OnPrepareBackup`
- `0x14007675c`: `CVssAsrWriterBackup::OnPrepareBackup`
- `0x1400762b5`: `IVssComponent::GetLogicalPath`
- `0x1400764ca`: `SafeStrCopy`
- `0x1400766d5`: `IVssComponent::SetBackupMetadata`
- `0x140076732`: `No ASR writer components selected`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall CVssAsrWriterBackup::OnPrepareBackup(CVssAsrWriterBackup *this, struct IVssWriterComponents *a2)
{
  LPVOID *v2; // r14
  CVssAsrWriterBackup *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  void *v6; // rax
  char *v7; // rax
  char *v8; // r14
  unsigned int j; // eax
  BSTR v10; // rsi
  unsigned int v11; // eax
  unsigned int v12; // r8d
  char *v13; // rbx
  __int64 v14; // rax
  SIZE_T v15; // r14
  void *v16; // rax
  int v17; // ebx
  int v18; // eax
  __int64 v19; // rax
  unsigned int v20; // ebx
  unsigned int v21; // esi
  unsigned int k; // r15d
  unsigned __int16 i; // cx
  LPVOID v25; // [rsp+40h] [rbp-1E8h]
  const unsigned __int16 *v26; // [rsp+50h] [rbp-1D8h] BYREF
  const unsigned __int16 *v27; // [rsp+58h] [rbp-1D0h]
  const unsigned __int16 *v28; // [rsp+60h] [rbp-1C8h]
  __int64 v29; // [rsp+68h] [rbp-1C0h]
  int v30; // [rsp+70h] [rbp-1B8h]
  _QWORD v31[15]; // [rsp+78h] [rbp-1B0h] BYREF
  int v32; // [rsp+F0h] [rbp-138h]
  int v33; // [rsp+F8h] [rbp-130h]
  unsigned __int16 *v34; // [rsp+100h] [rbp-128h] BYREF
  BSTR bstrString; // [rsp+108h] [rbp-120h] BYREF
  unsigned int v36; // [rsp+110h] [rbp-118h]
  BSTR String1; // [rsp+118h] [rbp-110h] BYREF
  struct IUnknown *v38; // [rsp+120h] [rbp-108h] BYREF
  unsigned int v39; // [rsp+128h] [rbp-100h]
  LPVOID pv; // [rsp+130h] [rbp-F8h] BYREF
  LPVOID v41; // [rsp+138h] [rbp-F0h]
  struct IUnknown *v42[2]; // [rsp+140h] [rbp-E8h] BYREF
  LPVOID v43; // [rsp+150h] [rbp-D8h] BYREF
  int v44; // [rsp+158h] [rbp-D0h]
  unsigned int v45; // [rsp+174h] [rbp-B4h]
  void **v46; // [rsp+1C0h] [rbp-68h] BYREF
  __int64 v47; // [rsp+1C8h] [rbp-60h]
  int v48; // [rsp+1D0h] [rbp-58h] BYREF
  wchar_t *EndPtr; // [rsp+1D8h] [rbp-50h] BYREF
  _com_error *v50; // [rsp+1E0h] [rbp-48h] BYREF
  const std::exception *v51; // [rsp+1E8h] [rbp-40h] BYREF
  unsigned int v54; // [rsp+240h] [rbp+18h] BYREF
  unsigned int v55; // [rsp+248h] [rbp+20h]

  v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
  v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
  v28 = L"WRTASRWC";
  v29 = 0x400000169LL;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v43, (__int64)&v26, 0);
  pv = 0;
  v54 = 0;
  ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(v42);
  ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v38);
  v47 = 0;
  v46 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
  String1 = 0;
  bstrString = 0;
  EndPtr = 0;
  v39 = 0;
  v41 = 0;
  v55 = 0;
  v2 = 0;
  v25 = 0;
  v34 = 0;
  v33 = 0;
  v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
  v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
  v28 = L"WRTASRWC";
  v29 = 0x40000017FLL;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  try
  {
    CVssFunctionTracer::AddContext((__int64)&v43, (__int64)&v26, 5012, (__int64)L"ASR Writer");
    v3 = this;
    v4 = *((unsigned int *)this + 6);
    if ( (int)v4 < 0 )
    {
      v44 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 2) + 56LL))(
              *((_QWORD *)this + 2),
              v4,
              &v34);
      if ( v44 >= 0 )
      {
        CVssAsrWriterBackup::_SetBackupErrorMsg(this, a2, *((_DWORD *)this + 6), v34);
        v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
        v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
        v28 = L"WRTASRWC";
        v29 = 0x400000187LL;
        v30 = 255;
        v32 = 0x1000000;
        memset_0(v31, 0, sizeof(v31));
        CVssFunctionTracer::AddErrorSpecificContext(&v43, &v26, L"ASR Writer", v34);
      }
      v44 = *((_DWORD *)this + 6);
      v33 = v44;
      v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
      v28 = L"WRTASRWC";
      v29 = 0x40000018CLL;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      CVssFunctionTracer::CheckForErrorInternal(&v43, &v26, L"Check OnIdentifyError");
      v3 = this;
    }
  }
  catch ( long v48 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v43,
      v48,
      L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
      L"WRTASRWC",
      L"CVssAsrWriterBackup::OnPrepareBackup",
      0x1F4u,
      v45);
    v2 = (LPVOID *)v25;
    goto LABEL_42;
  }
  catch ( _com_error *v50 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v43,
      v50,
      L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
      L"WRTASRWC",
      L"CVssAsrWriterBackup::OnPrepareBackup",
      0x1F4u,
      v45);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v43,
      L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
      L"WRTASRWC",
      L"CVssAsrWriterBackup::OnPrepareBackup",
      0x1F4u,
      v45);
    v2 = (LPVOID *)v25;
    goto LABEL_42;
  }
  catch ( const std::exception *v51 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v43,
      v51,
      L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
      L"WRTASRWC",
      L"CVssAsrWriterBackup::OnPrepareBackup",
      0x1F4u,
      v45);
  }
  catch ( ... )
  {
    v44 = -2147418113;
    v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
    v28 = L"WRTASRWC";
    v29 = 500;
    v30 = 255;
    v32 = 0x1000000;
    for ( i = 0; i < 0xFu; ++i )
      v31[i] = 0;
    CVssFunctionTracer::Trace(&v43, &v26, L"Exception caught!");
    v2 = (LPVOID *)v25;
    goto LABEL_42;
  }
  v5 = *((_QWORD *)v3 + 1);
  if ( v5 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v5 + 120LL))(v5) )
  {
    v44 = (**(__int64 (__fastcall ***)(struct IVssWriterComponents *, unsigned int *))a2)(a2, &v54);
    v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
    v28 = L"WRTASRWC";
    v29 = 0x400000196LL;
    v30 = 255;
    v32 = 0x1000000;
    memset_0(v31, 0, sizeof(v31));
    CVssFunctionTracer::CheckForErrorInternal(&v43, &v26, L"IVssWriterComponents::GetComponentCount");
    v6 = CoTaskMemAlloc(4LL * v54);
    v41 = v6;
    if ( !v6 )
    {
      v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
      v28 = L"WRTASRWC";
      v29 = 0x40000019ELL;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      CVssFunctionTracer::Throw(&v43, &v26, 2147942414LL, L"E_OUTOFMEMORY");
    }
    memset_0(v6, 0, 4LL * v54);
    v7 = (char *)CoTaskMemAlloc(8LL * v54);
    v8 = v7;
    v25 = v7;
    if ( !v7 )
    {
      v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
      v28 = L"WRTASRWC";
      v29 = 0x4000001A5LL;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      CVssFunctionTracer::Throw(&v43, &v26, 2147942414LL, L"E_OUTOFMEMORY");
    }
    memset_0(v7, 0, 8LL * v54);
    for ( j = 0; ; j = v36 + 1 )
    {
      v36 = j;
      if ( j >= v54 )
        break;
      ATL::CComPtrBase<IVssSnapshotDescription>::Release(&v38);
      v44 = (*(__int64 (__fastcall **)(struct IVssWriterComponents *, _QWORD, struct IUnknown **))(*(_QWORD *)a2 + 16LL))(
              a2,
              v36,
              &v38);
      v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
      v28 = L"WRTASRWC";
      v29 = 0x4000001AFLL;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      CVssFunctionTracer::CheckForErrorInternal(&v43, &v26, L"IVssWriterComponents::GetComponent");
      SysFreeString(bstrString);
      bstrString = 0;
      v44 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR *))v38->lpVtbl[1].Release)(v38, &bstrString);
      v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
      v28 = L"WRTASRWC";
      v29 = 0x4000001B3LL;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      CVssFunctionTracer::CheckForErrorInternal(&v43, &v26, L"IVssComponent::GetComponentName");
      SysFreeString(String1);
      String1 = 0;
      v44 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR *))v38->lpVtbl[1].QueryInterface)(v38, &String1);
      v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
      v28 = L"WRTASRWC";
      v29 = 0x4000001B7LL;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      CVssFunctionTracer::CheckForErrorInternal(&v43, &v26, L"IVssComponent::GetLogicalPath");
      v10 = bstrString;
      if ( !wcscmp_0(bstrString, L"ASR") )
      {
        ATL::CComPtr<IVssSnapshotProvider>::operator=(v42, &v38);
      }
      else if ( !wcscmp_0(String1, L"Disks") )
      {
        if ( ATL::CComBSTR::Length((ATL::CComBSTR *)&bstrString) <= 8
          || (unsigned int)_o__wcsnicmp(bstrString, L"harddisk", 8) )
        {
          v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
          v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
          v28 = L"WRTASRWC";
          v29 = 0x4000001C6LL;
          v30 = 255;
          v32 = 0x1000000;
          memset_0(v31, 0, sizeof(v31));
          CVssFunctionTracer::Throw(&v43, &v26, 2147549183LL, L"Invalid disk number");
        }
        v11 = wcstoul(bstrString + 8, &EndPtr, 10);
        v12 = v39;
        *((_DWORD *)v41 + v39) = v11;
        v39 = v12 + 1;
      }
      else if ( !wcscmp_0(String1, L"Volumes") )
      {
        v13 = &v8[8 * v55];
        if ( v13 )
          *(_QWORD *)v13 = 0;
        if ( v10 && v13 )
        {
          v14 = -1;
          do
            ++v14;
          while ( v10[v14] );
          v15 = 2LL * (unsigned int)(v14 + 1);
          v16 = CoTaskMemAlloc(v15);
          *(_QWORD *)v13 = v16;
          if ( v16 )
          {
            v17 = 0;
            memcpy_0(v16, v10, v15);
          }
          else
          {
            v17 = -2147024882;
          }
          v8 = (char *)v25;
        }
        else
        {
          v17 = -2147024809;
        }
        v44 = v17;
        v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
        v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
        v28 = L"WRTASRWC";
        v29 = 0x4000001D3LL;
        v30 = 255;
        v32 = 0x1000000;
        memset_0(v31, 0, sizeof(v31));
        CVssFunctionTracer::CheckForErrorInternal(&v43, &v26, L"SafeStrCopy");
        ++v55;
      }
    }
    if ( ATL::CComPtrBase<CVssSnapshotSetObject>::operator!=(v42, 0) )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, _QWORD, char *, LPVOID *))(**((_QWORD **)this + 2) + 48LL))(
              *((_QWORD *)this + 2),
              v39,
              v41,
              v55,
              v8,
              &pv);
      v44 = v18;
      if ( v18 < 0 )
      {
        v33 = v18;
        (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 **))(**((_QWORD **)this + 2) + 56LL))(
          *((_QWORD *)this + 2),
          (unsigned int)v18,
          &v34);
        if ( v34 )
        {
          CVssAsrWriterBackup::_SetBackupErrorMsg(this, a2, v44, v34);
          v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
          v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
          v28 = L"WRTASRWC";
          v29 = 0x4000001E3LL;
          v30 = 255;
          v32 = 0x1000000;
          memset_0(v31, 0, sizeof(v31));
          CVssFunctionTracer::AddErrorSpecificContext(&v43, &v26, L"ASR Writer", v34);
        }
      }
      v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
      v28 = L"WRTASRWC";
      v29 = 0x4000001E6LL;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      CVssFunctionTracer::CheckForErrorInternal(&v43, &v26, L"IVssAsrWriterBackup::GetAsrMetadata");
      CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom(&v46, pv);
      v19 = ATL::CComPtrBase<IGlobalInterfaceTable>::operator->((__int64)v42);
      v44 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 72LL))(v19, v47);
      v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
      v28 = L"WRTASRWC";
      v29 = 0x4000001EBLL;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      CVssFunctionTracer::CheckForErrorInternal(&v43, &v26, L"IVssComponent::SetBackupMetadata");
    }
    v2 = (LPVOID *)v25;
  }
  else
  {
    v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
    v28 = L"WRTASRWC";
    v29 = 0x4000001F0LL;
    v30 = 255;
    v32 = 0x1000000;
    memset_0(v31, 0, sizeof(v31));
    CVssFunctionTracer::Trace(&v43, &v26, L"No ASR writer components selected");
  }
LABEL_42:
  v20 = v44;
  if ( v33 < 0 )
    v20 = v33;
  v26 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
  v27 = L"CVssAsrWriterBackup::OnPrepareBackup";
  v28 = L"WRTASRWC";
  v29 = 0x4000001F6LL;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  CVssAsrWriterBackup::TranslateWriterError(this, &v26, v20, v34);
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v34);
  v34 = 0;
  CoTaskMemFree(v41);
  v21 = 0;
  for ( k = v55; v21 < k; ++v21 )
  {
    CoTaskMemFree(v2[v21]);
    v2[v21] = 0;
  }
  CoTaskMemFree(v2);
  SysFreeString(bstrString);
  SysFreeString(String1);
  CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v46);
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v38);
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v42);
  CVssFunctionTracer::~CVssFunctionTracer(&v43);
  return 1;
}

```

## disassembly

```asm
0x140075cb0  mov     [rsp+arg_8], rdx
0x140075cb5  mov     [rsp+arg_0], rcx
0x140075cba  push    rbx
0x140075cbb  push    rsi
0x140075cbc  push    rdi
0x140075cbd  push    r12
0x140075cbf  push    r13
0x140075cc1  push    r14
0x140075cc3  push    r15
0x140075cc5  sub     rsp, 1F0h
0x140075ccc  lea     r15, aBaseStorVssMod_7; "base\\stor\\vss\\modules\\writers\\asrw"...
0x140075cd3  mov     [rsp+228h+var_1D8], r15
0x140075cd8  lea     r12, aCvssasrwriterb_5; "CVssAsrWriterBackup::OnPrepareBackup"
0x140075cdf  mov     [rsp+228h+var_1D0], r12
0x140075ce4  lea     r13, aWrtasrwc; "WRTASRWC"
0x140075ceb  mov     [rsp+228h+var_1C8], r13
0x140075cf0  mov     [rsp+228h+var_1C0], 169h
0x140075cf8  mov     ebx, 4
0x140075cfd  mov     [rsp+228h+var_1BC], ebx
0x140075d01  mov     [rsp+228h+var_1B8], 0FFh
0x140075d09  xor     edi, edi
0x140075d0b  mov     [rsp+228h+var_138], 1000000h
0x140075d16  lea     esi, [rbx+74h]
0x140075d19  mov     r8d, esi; Size
0x140075d1c  xor     edx, edx; Val
0x140075d1e  lea     rcx, [rsp+228h+var_1B0]; void *
0x140075d23  call    memset_0
0x140075d28  xor     r8d, r8d
0x140075d2b  lea     rdx, [rsp+228h+var_1D8]
0x140075d30  lea     rcx, [rsp+228h+var_D8]
0x140075d38  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140075d3d  nop
0x140075d3e  mov     [rsp+228h+pv], rdi
0x140075d46  mov     [rsp+228h+arg_10], edi
0x140075d4d  lea     rcx, [rsp+228h+var_E8]
0x140075d55  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x140075d5a  nop
0x140075d5b  lea     rcx, [rsp+228h+var_108]
0x140075d63  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x140075d68  nop
0x140075d69  mov     [rsp+228h+var_60], rdi
0x140075d71  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x140075d78  mov     [rsp+228h+var_68], rax
0x140075d80  mov     [rsp+228h+String1], rdi
0x140075d88  mov     [rsp+228h+bstrString], rdi
0x140075d90  mov     [rsp+228h+EndPtr], rdi
0x140075d98  mov     [rsp+228h+var_100], edi
0x140075d9f  mov     [rsp+228h+var_F0], rdi
0x140075da7  mov     [rsp+228h+arg_18], edi
0x140075dae  mov     r14d, edi
0x140075db1  mov     [rsp+228h+var_1E8], rdi
0x140075db6  mov     [rsp+228h+var_128], rdi
0x140075dbe  mov     [rsp+228h+var_130], edi
0x140075dc5  mov     [rsp+228h+var_1D8], r15
0x140075dca  mov     [rsp+228h+var_1D0], r12
0x140075dcf  mov     [rsp+228h+var_1C8], r13
0x140075dd4  mov     [rsp+228h+var_1C0], 17Fh
0x140075ddc  mov     [rsp+228h+var_1BC], ebx
0x140075de0  mov     [rsp+228h+var_1B8], 0FFh
0x140075de8  mov     [rsp+228h+var_138], 1000000h
0x140075df3  mov     r8d, esi; Size
0x140075df6  xor     edx, edx; Val
0x140075df8  lea     rcx, [rsp+228h+var_1B0]; void *
0x140075dfd  call    memset_0
0x140075e02  lea     r9, aAsrWriter; "ASR Writer"
0x140075e09  mov     r8d, 1394h
0x140075e0f  lea     rdx, [rsp+228h+var_1D8]
0x140075e14  lea     rcx, [rsp+228h+var_D8]
0x140075e1c  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x140075e21  mov     rax, [rsp+228h+arg_0]
0x140075e29  mov     edx, [rax+18h]
0x140075e2c  test    edx, edx
0x140075e2e  jns     loc_140075F54
0x140075e34  mov     rcx, [rax+10h]
0x140075e38  mov     rax, [rcx]
0x140075e3b  lea     r8, [rsp+228h+var_128]
0x140075e43  mov     rax, [rax+38h]
0x140075e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075e4c  mov     [rsp+228h+var_D0], eax
0x140075e53  test    eax, eax
0x140075e55  js      loc_140075EDD
0x140075e5b  mov     r9, [rsp+228h+var_128]; unsigned __int16 *
0x140075e63  mov     rax, [rsp+228h+arg_0]
0x140075e6b  mov     r8d, [rax+18h]; int
0x140075e6f  mov     rdx, [rsp+228h+arg_8]; struct IVssWriterComponents *
0x140075e77  mov     rcx, rax; this
0x140075e7a  call    ?_SetBackupErrorMsg@CVssAsrWriterBackup@@AEAAJPEAVIVssWriterComponents@@JPEBG@Z; CVssAsrWriterBackup::_SetBackupErrorMsg(IVssWriterComponents *,long,ushort const *)
0x140075e7f  mov     [rsp+228h+var_1D8], r15
0x140075e84  mov     [rsp+228h+var_1D0], r12
0x140075e89  mov     [rsp+228h+var_1C8], r13
0x140075e8e  mov     [rsp+228h+var_1C0], 187h
0x140075e96  mov     [rsp+228h+var_1BC], ebx
0x140075e9a  mov     [rsp+228h+var_1B8], 0FFh
0x140075ea2  mov     [rsp+228h+var_138], 1000000h
0x140075ead  mov     r8d, esi; Size
0x140075eb0  xor     edx, edx; Val
0x140075eb2  lea     rcx, [rsp+228h+var_1B0]; void *
0x140075eb7  call    memset_0
0x140075ebc  mov     r9, [rsp+228h+var_128]
0x140075ec4  lea     r8, aAsrWriter; "ASR Writer"
0x140075ecb  lea     rdx, [rsp+228h+var_1D8]
0x140075ed0  lea     rcx, [rsp+228h+var_D8]
0x140075ed8  call    ?AddErrorSpecificContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG1ZZ; CVssFunctionTracer::AddErrorSpecificContext(CVssDebugInfo,ushort const *,ushort const *,...)
0x140075edd  mov     rcx, [rsp+228h+arg_0]
0x140075ee5  mov     eax, [rcx+18h]
0x140075ee8  mov     [rsp+228h+var_D0], eax
0x140075eef  mov     [rsp+228h+var_130], eax
0x140075ef6  mov     [rsp+228h+var_1D8], r15
0x140075efb  mov     [rsp+228h+var_1D0], r12
0x140075f00  mov     [rsp+228h+var_1C8], r13
0x140075f05  mov     [rsp+228h+var_1C0], 18Ch
0x140075f0d  mov     [rsp+228h+var_1BC], ebx
0x140075f11  mov     [rsp+228h+var_1B8], 0FFh
0x140075f19  mov     [rsp+228h+var_138], 1000000h
0x140075f24  mov     r8, rsi; Size
0x140075f27  xor     edx, edx; Val
0x140075f29  lea     rcx, [rsp+228h+var_1B0]; void *
0x140075f2e  call    memset_0
0x140075f33  lea     r8, aCheckOnidentif; "Check OnIdentifyError"
0x140075f3a  lea     rdx, [rsp+228h+var_1D8]
0x140075f3f  lea     rcx, [rsp+228h+var_D8]
0x140075f47  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x140075f4c  mov     rax, [rsp+228h+arg_0]
0x140075f54  mov     rcx, [rax+8]
0x140075f58  test    rcx, rcx
0x140075f5b  jz      loc_1400766F5
0x140075f61  mov     rax, [rcx]
0x140075f64  mov     rax, [rax+78h]
0x140075f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075f6d  test    al, al
0x140075f6f  jz      loc_1400766F5
0x140075f75  mov     rcx, [rsp+228h+arg_8]
0x140075f7d  mov     rax, [rcx]
0x140075f80  lea     rdx, [rsp+228h+arg_10]
0x140075f88  mov     rax, [rax]
0x140075f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075f90  mov     [rsp+228h+var_D0], eax
0x140075f97  mov     [rsp+228h+var_1D8], r15
0x140075f9c  mov     [rsp+228h+var_1D0], r12
0x140075fa1  mov     [rsp+228h+var_1C8], r13
0x140075fa6  mov     [rsp+228h+var_1C0], 196h
0x140075fae  mov     [rsp+228h+var_1BC], ebx
0x140075fb2  mov     [rsp+228h+var_1B8], 0FFh
0x140075fba  mov     [rsp+228h+var_138], 1000000h
0x140075fc5  mov     r8, rsi; Size
0x140075fc8  xor     edx, edx; Val
0x140075fca  lea     rcx, [rsp+228h+var_1B0]; void *
0x140075fcf  call    memset_0
0x140075fd4  lea     r8, aIvsswritercomp_0; "IVssWriterComponents::GetComponentCount"
0x140075fdb  lea     rdx, [rsp+228h+var_1D8]
0x140075fe0  lea     rcx, [rsp+228h+var_D8]
0x140075fe8  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x140075fed  mov     ecx, [rsp+228h+arg_10]
0x140075ff4  shl     rcx, 2; cb
0x140075ff8  call    cs:__imp_CoTaskMemAlloc
0x140075ffe  mov     [rsp+228h+var_F0], rax
0x140076006  test    rax, rax
0x140076009  jnz     short loc_140076067
0x14007600b  mov     [rsp+228h+var_1D8], r15
0x140076010  mov     [rsp+228h+var_1D0], r12
0x140076015  mov     [rsp+228h+var_1C8], r13
0x14007601a  mov     [rsp+228h+var_1C0], 19Eh
0x140076022  mov     [rsp+228h+var_1BC], ebx
0x140076026  mov     [rsp+228h+var_1B8], 0FFh
0x14007602e  mov     [rsp+228h+var_138], 1000000h
0x140076039  mov     r8, rsi; Size
0x14007603c  xor     edx, edx; Val
0x14007603e  lea     rcx, [rsp+228h+var_1B0]; void *
0x140076043  call    memset_0
0x140076048  lea     r9, aEOutofmemory_0; "E_OUTOFMEMORY"
0x14007604f  mov     r8d, 8007000Eh
0x140076055  lea     rdx, [rsp+228h+var_1D8]
0x14007605a  lea     rcx, [rsp+228h+var_D8]
0x140076062  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140076067  mov     r8d, [rsp+228h+arg_10]
0x14007606f  shl     r8, 2; Size
0x140076073  xor     edx, edx; Val
0x140076075  mov     rcx, rax; void *
0x140076078  call    memset_0
0x14007607d  mov     ecx, [rsp+228h+arg_10]
0x140076084  shl     rcx, 3; cb
0x140076088  call    cs:__imp_CoTaskMemAlloc
0x14007608e  mov     r14, rax
0x140076091  mov     [rsp+228h+var_1E8], rax
0x140076096  test    rax, rax
0x140076099  jnz     short loc_1400760F7
0x14007609b  mov     [rsp+228h+var_1D8], r15
0x1400760a0  mov     [rsp+228h+var_1D0], r12
0x1400760a5  mov     [rsp+228h+var_1C8], r13
0x1400760aa  mov     [rsp+228h+var_1C0], 1A5h
0x1400760b2  mov     [rsp+228h+var_1BC], ebx
0x1400760b6  mov     [rsp+228h+var_1B8], 0FFh
0x1400760be  mov     [rsp+228h+var_138], 1000000h
0x1400760c9  mov     r8, rsi; Size
0x1400760cc  xor     edx, edx; Val
0x1400760ce  lea     rcx, [rsp+228h+var_1B0]; void *
0x1400760d3  call    memset_0
0x1400760d8  lea     r9, aEOutofmemory_0; "E_OUTOFMEMORY"
0x1400760df  mov     r8d, 8007000Eh
0x1400760e5  lea     rdx, [rsp+228h+var_1D8]
0x1400760ea  lea     rcx, [rsp+228h+var_D8]
0x1400760f2  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400760f7  mov     r8d, [rsp+228h+arg_10]
0x1400760ff  shl     r8, 3; Size
0x140076103  xor     edx, edx; Val
0x140076105  mov     rcx, rax; void *
0x140076108  call    memset_0
0x14007610d  mov     eax, edi
0x14007610f  mov     [rsp+228h+var_118], eax
0x140076116  cmp     eax, [rsp+228h+arg_10]
0x14007611d  jnb     loc_1400764EF
0x140076123  lea     rcx, [rsp+228h+var_108]
0x14007612b  call    ?Release@?$CComPtrBase@VIVssSnapshotDescription@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVssSnapshotDescription>::Release(void)
0x140076130  mov     rcx, [rsp+228h+arg_8]
0x140076138  mov     rax, [rcx]
0x14007613b  lea     r8, [rsp+228h+var_108]
0x140076143  mov     edx, [rsp+228h+var_118]
0x14007614a  mov     rax, [rax+10h]
0x14007614e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076153  mov     [rsp+228h+var_D0], eax
0x14007615a  mov     [rsp+228h+var_1D8], r15
0x14007615f  mov     [rsp+228h+var_1D0], r12
0x140076164  mov     [rsp+228h+var_1C8], r13
0x140076169  mov     [rsp+228h+var_1C0], 1AFh
0x140076171  mov     [rsp+228h+var_1BC], ebx
0x140076175  mov     [rsp+228h+var_1B8], 0FFh
0x14007617d  mov     [rsp+228h+var_138], 1000000h
0x140076188  mov     r8, rsi; Size
0x14007618b  xor     edx, edx; Val
0x14007618d  lea     rcx, [rsp+228h+var_1B0]; void *
0x140076192  call    memset_0
0x140076197  lea     r8, aIvsswritercomp_1; "IVssWriterComponents::GetComponent"
0x14007619e  lea     rdx, [rsp+228h+var_1D8]
0x1400761a3  lea     rcx, [rsp+228h+var_D8]
0x1400761ab  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400761b0  mov     rcx, [rsp+228h+bstrString]; bstrString
0x1400761b8  call    cs:__imp_SysFreeString
0x1400761be  mov     [rsp+228h+bstrString], rdi
0x1400761c6  mov     rcx, [rsp+228h+var_108]
0x1400761ce  mov     rax, [rcx]
0x1400761d1  lea     rdx, [rsp+228h+bstrString]
0x1400761d9  mov     rax, [rax+28h]
0x1400761dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400761e2  mov     [rsp+228h+var_D0], eax
0x1400761e9  mov     [rsp+228h+var_1D8], r15
0x1400761ee  mov     [rsp+228h+var_1D0], r12
0x1400761f3  mov     [rsp+228h+var_1C8], r13
0x1400761f8  mov     [rsp+228h+var_1C0], 1B3h
0x140076200  mov     [rsp+228h+var_1BC], ebx
0x140076204  mov     [rsp+228h+var_1B8], 0FFh
0x14007620c  mov     [rsp+228h+var_138], 1000000h
0x140076217  mov     r8, rsi; Size
0x14007621a  xor     edx, edx; Val
0x14007621c  lea     rcx, [rsp+228h+var_1B0]; void *
0x140076221  call    memset_0
0x140076226  lea     r8, aIvsscomponentG_0; "IVssComponent::GetComponentName"
0x14007622d  lea     rdx, [rsp+228h+var_1D8]
0x140076232  lea     rcx, [rsp+228h+var_D8]
0x14007623a  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14007623f  mov     rcx, [rsp+228h+String1]; bstrString
0x140076247  call    cs:__imp_SysFreeString
0x14007624d  mov     [rsp+228h+String1], rdi
0x140076255  mov     rcx, [rsp+228h+var_108]
0x14007625d  mov     rax, [rcx]
0x140076260  lea     rdx, [rsp+228h+String1]
0x140076268  mov     rax, [rax+18h]
0x14007626c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076271  mov     [rsp+228h+var_D0], eax
0x140076278  mov     [rsp+228h+var_1D8], r15
0x14007627d  mov     [rsp+228h+var_1D0], r12
0x140076282  mov     [rsp+228h+var_1C8], r13
0x140076287  mov     [rsp+228h+var_1C0], 1B7h
0x14007628f  mov     [rsp+228h+var_1BC], ebx
0x140076293  mov     [rsp+228h+var_1B8], 0FFh
0x14007629b  mov     [rsp+228h+var_138], 1000000h
0x1400762a6  mov     r8, rsi; Size
0x1400762a9  xor     edx, edx; Val
0x1400762ab  lea     rcx, [rsp+228h+var_1B0]; void *
0x1400762b0  call    memset_0
0x1400762b5  lea     r8, aIvsscomponentG; "IVssComponent::GetLogicalPath"
0x1400762bc  lea     rdx, [rsp+228h+var_1D8]
0x1400762c1  lea     rcx, [rsp+228h+var_D8]
0x1400762c9  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400762ce  lea     rdx, aAsr; "ASR"
0x1400762d5  mov     rsi, [rsp+228h+bstrString]
0x1400762dd  mov     rcx, rsi; String1
0x1400762e0  call    wcscmp_0
0x1400762e5  test    eax, eax
0x1400762e7  jnz     short loc_140076311
0x1400762e9  lea     rdx, [rsp+228h+var_108]
0x1400762f1  lea     rcx, [rsp+228h+var_E8]
0x1400762f9  call    ??4?$CComPtr@UIVssSnapshotProvider@@@ATL@@QEAAPEAUIVssSnapshotProvider@@AEBV01@@Z; ATL::CComPtr<IVssSnapshotProvider>::operator=(ATL::CComPtr<IVssSnapshotProvider> const &)
0x1400762fe  mov     esi, 78h ; 'x'
0x140076303  mov     eax, [rsp+228h+var_118]
0x14007630a  inc     eax
0x14007630c  jmp     loc_14007610F
0x140076311  lea     rdx, aDisks; "Disks"
0x140076318  mov     rcx, [rsp+228h+String1]; String1
0x140076320  call    wcscmp_0
0x140076325  test    eax, eax
  ... truncated ...
```
