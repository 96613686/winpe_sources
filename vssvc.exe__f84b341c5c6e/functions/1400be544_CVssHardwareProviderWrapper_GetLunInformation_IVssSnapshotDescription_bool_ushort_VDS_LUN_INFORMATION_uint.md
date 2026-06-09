# CVssHardwareProviderWrapper::GetLunInformation(IVssSnapshotDescription *,bool,ushort * * *,_VDS_LUN_INFORMATION * *,uint *)

- ea: `0x1400be544`
- end: `0x1400bef5a`
- name: `?GetLunInformation@CVssHardwareProviderWrapper@@AEAAXPEAVIVssSnapshotDescription@@_NPEAPEAPEAGPEAPEAU_VDS_LUN_INFORMATION@@PEAI@Z`
- size: `2582`
- prototype: `void __fastcall(CVssHardwareProviderWrapper *__hidden this, struct IVssSnapshotDescription *, bool, unsigned __int16 ***, struct _VDS_LUN_INFORMATION **, unsigned int *)`
- caller_count: `3`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004d814`
- `0x1400b6140`
- `0x1400ca888`

## callees

- `0x1400088fc`
- `0x1400137c0`
- `0x140013b00`
- `0x140015e38`
- `0x140025b00`
- `0x14003c160`
- `0x14003fc04`
- `0x140049ec4`
- `0x14004d404`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400a18bc`
- `0x1400be068`
- `0x1400be544`
- `0x1400f4010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400bea38`
- `OLEAUT32!__imp_SysFreeString` at `0x1400bea38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400be678`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400be731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400be976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bed85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400be678`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400be731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400be976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bed85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400be74a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400bed4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400beefb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400be74a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400bed4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400beefb`

## string_xrefs

- `0x1400beaa1`: `StringCchCopyW()`
- `0x1400bed1c`: `IVssLunInformation::GetStorageDeviceIdDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CVssHardwareProviderWrapper::GetLunInformation(
        CVssHardwareProviderWrapper *this,
        struct IVssSnapshotDescription *a2,
        char a3,
        unsigned __int16 ***a4,
        struct _VDS_LUN_INFORMATION **a5,
        unsigned int *a6)
{
  unsigned __int16 ***v6; // rbx
  struct IVssSnapshotDescription *v7; // rsi
  struct _VDS_LUN_INFORMATION *v8; // r12
  unsigned __int16 **v9; // r15
  unsigned __int16 **v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdi
  struct _VDS_LUN_INFORMATION *v13; // r13
  unsigned __int64 v14; // rbx
  unsigned __int16 *v15; // rax
  unsigned int v16; // eax
  const unsigned __int16 *v17; // r8
  __int64 v18; // rax
  int v19; // eax
  VDS_INTERCONNECT *v20; // rax
  ULONG v21; // eax
  ULONG i; // ebx
  __int64 v23; // r8
  unsigned int v24; // edx
  ULONG v25; // [rsp+50h] [rbp-1C8h] BYREF
  __int64 v26; // [rsp+58h] [rbp-1C0h] BYREF
  const unsigned __int16 *v27; // [rsp+60h] [rbp-1B8h] BYREF
  const unsigned __int16 *v28; // [rsp+68h] [rbp-1B0h]
  const unsigned __int16 *v29; // [rsp+70h] [rbp-1A8h]
  int v30; // [rsp+78h] [rbp-1A0h]
  int v31; // [rsp+7Ch] [rbp-19Ch]
  int v32; // [rsp+80h] [rbp-198h]
  _BYTE v33[120]; // [rsp+88h] [rbp-190h] BYREF
  int v34; // [rsp+100h] [rbp-118h]
  BSTR bstrString; // [rsp+108h] [rbp-110h] BYREF
  unsigned int v36; // [rsp+110h] [rbp-108h]
  __int64 *v37; // [rsp+118h] [rbp-100h] BYREF
  unsigned __int16 **v38; // [rsp+120h] [rbp-F8h]
  LPVOID pv; // [rsp+128h] [rbp-F0h] BYREF
  struct _VDS_LUN_INFORMATION *v40; // [rsp+130h] [rbp-E8h]
  int pExceptionObject; // [rsp+140h] [rbp-D8h] BYREF
  LPVOID v42; // [rsp+150h] [rbp-C8h] BYREF
  int v43; // [rsp+158h] [rbp-C0h]
  unsigned int v44; // [rsp+174h] [rbp-A4h]
  int v45; // [rsp+1C0h] [rbp-58h] BYREF
  const std::exception *v46; // [rsp+1C8h] [rbp-50h] BYREF
  _com_error *v47; // [rsp+1D0h] [rbp-48h] BYREF
  CVssHardwareProviderWrapper *v48; // [rsp+220h] [rbp+8h] BYREF
  struct IVssSnapshotDescription *v49; // [rsp+228h] [rbp+10h]
  char v50; // [rsp+230h] [rbp+18h]
  unsigned __int16 ***v51; // [rsp+238h] [rbp+20h]

  v51 = a4;
  v50 = a3;
  v49 = a2;
  v48 = this;
  v6 = a4;
  v7 = a2;
  v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
  v29 = L"CORHWUTC";
  v30 = 2147;
  v31 = 1;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v42, (__int64)&v27, 0);
  LODWORD(v48) = 0;
  v43 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, CVssHardwareProviderWrapper **))(*(_QWORD *)v7 + 160LL))(
          v7,
          &v48);
  v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
  v29 = L"CORHWUTC";
  v30 = 2152;
  v31 = 1;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  CVssFunctionTracer::CheckForErrorInternal(&v42, &v27, L"IVssSnapshotDescription::GetLunCount");
  v8 = (struct _VDS_LUN_INFORMATION *)CoTaskMemAlloc(96LL * (unsigned int)v48);
  v40 = v8;
  if ( !v8 )
  {
    v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
    v29 = L"CORHWUTC";
    v30 = 2159;
    v31 = 1;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::Throw(&v42, &v27, 2147942414LL, L"Cannot allocate lun information array");
  }
  memset_0(v8, 0, 96LL * (unsigned int)v48);
  v9 = 0;
  v38 = 0;
  if ( v6 )
  {
    v10 = (unsigned __int16 **)CoTaskMemAlloc(8LL * (unsigned int)v48);
    v9 = v10;
    v38 = v10;
    if ( !v10 )
    {
      CoTaskMemFree(v8);
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
      v29 = L"CORHWUTC";
      v30 = 2173;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::Throw(&v42, &v27, 2147942414LL, L"Cannot allocate device names array");
    }
    memset_0(v10, 0, 8LL * (unsigned int)v48);
  }
  pv = 0;
  try
  {
    v24 = 0;
    while ( 1 )
    {
      v36 = v24;
      if ( v24 >= (unsigned int)v48 )
        break;
      ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v26);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v37);
      v12 = (unsigned int)v11;
      v13 = &v8[(unsigned int)v11];
      v13->m_version = 1;
      v43 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, __int64, __int64 **))(*(_QWORD *)v7 + 176LL))(
              v7,
              v11,
              &v37);
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
      v29 = L"CORHWUTC";
      v30 = 2195;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::CheckForErrorInternal(&v42, &v27, L"IVssSnapshotDescription::GetLunMapping");
      if ( v6 )
      {
        bstrString = 0;
        v43 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v37 + 48))(v37, &bstrString);
        v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
        v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
        v29 = L"CORHWUTC";
        v30 = 2202;
        v31 = 1;
        v32 = 255;
        v34 = 0x1000000;
        memset_0(v33, 0, sizeof(v33));
        CVssFunctionTracer::CheckForErrorInternal(&v42, &v27, L"ILunMappipng::GetSourceDevice");
        v14 = ATL::CComBSTR::Length((ATL::CComBSTR *)&bstrString) + 1;
        v15 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)(2 * v14));
        v9[v12] = v15;
        if ( !v15 )
        {
          v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
          v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
          v29 = L"CORHWUTC";
          v30 = 2206;
          v31 = 1;
          v32 = 255;
          v34 = 0x1000000;
          memset_0(v33, 0, sizeof(v33));
          CVssFunctionTracer::Throw(&v42, &v27, 2147942414LL, L"Cannot allocate source device name");
        }
        v16 = ATL::CComBSTR::Length((ATL::CComBSTR *)&bstrString);
        v17 = bstrString;
        if ( !v16 )
          v17 = &byte_1400F9C88;
        v43 = StringCchCopyW(v9[v12], v14, v17);
        SysFreeString(bstrString);
      }
      if ( v43 < 0 )
      {
        v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
        v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
        v29 = L"CORHWUTC";
        v30 = 2213;
        v31 = 1;
        v32 = 255;
        v34 = 0x1000000;
        memset_0(v33, 0, sizeof(v33));
        CVssFunctionTracer::TranslateGenericError(&v42, &v27, (unsigned int)v43, L"StringCchCopyW()");
      }
      v18 = *v37;
      if ( v50 )
        v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 72))(v37, &v26);
      else
        v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 64))(v37, &v26);
      v43 = v19;
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
      v29 = L"CORHWUTC";
      v30 = 2222;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::CheckForErrorInternal(&v42, &v27, L"IVssLunMapping::GetSourceLun");
      v43 = (*(__int64 (__fastcall **)(__int64, BYTE *, BYTE *, BOOL *, char **, char **, char **, char **, VDS_STORAGE_BUS_TYPE *))(*(_QWORD *)v26 + 32LL))(
              v26,
              &v13->m_DeviceType,
              &v13->m_DeviceTypeModifier,
              &v13->m_bCommandQueueing,
              &v13->m_szVendorId,
              &v13->m_szProductId,
              &v13->m_szProductRevision,
              &v13->m_szSerialNumber,
              &v13->m_BusType);
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
      v29 = L"CORHWUTC";
      v30 = 2237;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::CheckForErrorInternal(&v42, &v27, L"IVssLunInformation::GetLunBasicType");
      v43 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v26 + 40LL))(v26, &v13->m_diskSignature);
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
      v29 = L"CORHWUTC";
      v30 = 2241;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::CheckForErrorInternal(&v42, &v27, L"IVssLunInformation::GetDiskSignature");
      v43 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v26 + 88LL))(v26, &pv);
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
      v29 = L"CORHWUTC";
      v30 = 2245;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::CheckForErrorInternal(&v42, &v27, L"IVssLunInformation::GetStorageDeviceIdDescriptor");
      CVssHardwareProviderWrapper::CopyStorageDeviceIdDescriptorToLun((struct _STORAGE_DEVICE_ID_DESCRIPTOR *)pv, v13);
      CoTaskMemFree(pv);
      pv = 0;
      v25 = 0;
      v43 = (*(__int64 (__fastcall **)(__int64, ULONG *))(*(_QWORD *)v26 + 64LL))(v26, &v25);
      v20 = (VDS_INTERCONNECT *)CoTaskMemAlloc(32LL * v25);
      v13->m_rgInterconnects = v20;
      memset_0(v20, 0, 32LL * v25);
      v21 = v25;
      v13->m_cInterconnects = v25;
      for ( i = 0; i < v21; ++i )
      {
        v23 = (__int64)&v13->m_rgInterconnects[i];
        v43 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, __int64, __int64))(*(_QWORD *)v26 + 72LL))(
                v26,
                i,
                v23,
                v23 + 4,
                v23 + 8,
                v23 + 16,
                v23 + 24);
        v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
        v28 = L"CVssHardwareProviderWrapper::GetLunInformation";
        v29 = L"CORHWUTC";
        v30 = 2280;
        v31 = 1;
        v32 = 255;
        v34 = 0x1000000;
        memset_0(v33, 0, sizeof(v33));
        CVssFunctionTracer::CheckForErrorInternal(&v42, &v27, L"IVssLunInformation::GetInterconnectAddress");
        v21 = v25;
      }
      *a5 = v8;
      *a6 = (unsigned int)v48;
      v6 = v51;
      if ( v51 )
        *v51 = v9;
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v37);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v26);
      v24 = v36 + 1;
      v7 = v49;
    }
  }
  catch ( long v45 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v42,
      v45,
      L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx",
      L"CORHWUTC",
      L"CVssHardwareProviderWrapper::GetLunInformation",
      0x8F2u,
      v44);
    v9 = v38;
    v8 = v40;
  }
  catch ( _com_error *v47 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v42,
      v47,
      L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx",
      L"CORHWUTC",
      L"CVssHardwareProviderWrapper::GetLunInformation",
      0x8F2u,
      v44);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v42,
      L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx",
      L"CORHWUTC",
      L"CVssHardwareProviderWrapper::GetLunInformation",
      0x8F2u,
      v44);
    v9 = v38;
    v8 = v40;
  }
  catch ( const std::exception *v46 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v42,
      v46,
      L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx",
      L"CORHWUTC",
      L"CVssHardwareProviderWrapper::GetLunInformation",
      0x8F2u,
      v44);
  }
  if ( v43 < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    CVssHardwareProviderWrapper::FreeLunInfo(v8, v9, 0, (unsigned int)v48);
    pExceptionObject = v43;
    throw (long *)&pExceptionObject;
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v42);
}

```

## disassembly

```asm
0x1400be544  mov     rax, rsp
0x1400be547  mov     [rax+20h], r9
0x1400be54b  mov     [rax+18h], r8b
0x1400be54f  mov     [rax+10h], rdx
0x1400be553  mov     [rax+8], rcx
0x1400be557  push    rbx
0x1400be558  push    rsi
0x1400be559  push    rdi
0x1400be55a  push    r12
0x1400be55c  push    r13
0x1400be55e  push    r14
0x1400be560  push    r15
0x1400be562  sub     rsp, 1E0h
0x1400be569  mov     rbx, r9
0x1400be56c  mov     rsi, rdx
0x1400be56f  lea     r13, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400be576  mov     [rsp+218h+var_1B8], r13
0x1400be57b  lea     r15, aCvsshardwarepr_78; "CVssHardwareProviderWrapper::GetLunInfo"...
0x1400be582  mov     [rsp+218h+var_1B0], r15
0x1400be587  lea     r12, aCorhwutc; "CORHWUTC"
0x1400be58e  mov     [rsp+218h+var_1A8], r12
0x1400be593  mov     [rsp+218h+var_1A0], 863h
0x1400be59b  mov     edi, 1
0x1400be5a0  mov     [rsp+218h+var_19C], edi
0x1400be5a4  mov     dword ptr [rax-198h], 0FFh
0x1400be5ae  xor     r14d, r14d
0x1400be5b1  mov     dword ptr [rax-118h], 1000000h
0x1400be5bb  xor     edx, edx; Val
0x1400be5bd  lea     r8d, [rdi+77h]; Size
0x1400be5c1  lea     rcx, [rax-190h]; void *
0x1400be5c8  call    memset_0
0x1400be5cd  xor     r8d, r8d
0x1400be5d0  lea     rdx, [rsp+218h+var_1B8]
0x1400be5d5  lea     rcx, [rsp+218h+var_C8]
0x1400be5dd  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400be5e2  nop
0x1400be5e3  mov     dword ptr [rsp+218h+arg_0], r14d
0x1400be5eb  mov     rax, [rsi]
0x1400be5ee  lea     rdx, [rsp+218h+arg_0]
0x1400be5f6  mov     rcx, rsi
0x1400be5f9  mov     rax, [rax+0A0h]
0x1400be600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400be605  mov     [rsp+218h+var_C0], eax
0x1400be60c  mov     [rsp+218h+var_1B8], r13
0x1400be611  mov     [rsp+218h+var_1B0], r15
0x1400be616  mov     [rsp+218h+var_1A8], r12
0x1400be61b  mov     [rsp+218h+var_1A0], 868h
0x1400be623  mov     [rsp+218h+var_19C], edi
0x1400be627  mov     [rsp+218h+var_198], 0FFh
0x1400be632  mov     [rsp+218h+var_118], 1000000h
0x1400be63d  xor     edx, edx; Val
0x1400be63f  lea     r8d, [rdi+77h]; Size
0x1400be643  lea     rcx, [rsp+218h+var_190]; void *
0x1400be64b  call    memset_0
0x1400be650  lea     r8, aIvsssnapshotde_5; "IVssSnapshotDescription::GetLunCount"
0x1400be657  lea     rdx, [rsp+218h+var_1B8]
0x1400be65c  lea     rcx, [rsp+218h+var_C8]
0x1400be664  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400be669  mov     eax, dword ptr [rsp+218h+arg_0]
0x1400be670  lea     rcx, [rax+rax*2]
0x1400be674  shl     rcx, 5; cb
0x1400be678  call    cs:__imp_CoTaskMemAlloc
0x1400be67e  mov     r12, rax
0x1400be681  mov     [rsp+218h+var_E8], rax
0x1400be689  test    rax, rax
0x1400be68c  jnz     short loc_1400BE6F9
0x1400be68e  mov     [rsp+218h+var_1B8], r13
0x1400be693  mov     [rsp+218h+var_1B0], r15
0x1400be698  lea     rax, aCorhwutc; "CORHWUTC"
0x1400be69f  mov     [rsp+218h+var_1A8], rax
0x1400be6a4  mov     [rsp+218h+var_1A0], 86Fh
0x1400be6ac  mov     [rsp+218h+var_19C], edi
0x1400be6b0  mov     [rsp+218h+var_198], 0FFh
0x1400be6bb  mov     [rsp+218h+var_118], 1000000h
0x1400be6c6  xor     edx, edx; Val
0x1400be6c8  lea     r8d, [rdi+77h]; Size
0x1400be6cc  lea     rcx, [rsp+218h+var_190]; void *
0x1400be6d4  call    memset_0
0x1400be6d9  lea     r9, aCannotAllocate_18; "Cannot allocate lun information array"
0x1400be6e0  mov     r8d, 8007000Eh
0x1400be6e6  lea     rdx, [rsp+218h+var_1B8]
0x1400be6eb  lea     rcx, [rsp+218h+var_C8]
0x1400be6f3  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400be6f9  mov     eax, dword ptr [rsp+218h+arg_0]
0x1400be700  lea     r8, [rax+rax*2]
0x1400be704  shl     r8, 5; Size
0x1400be708  xor     edx, edx; Val
0x1400be70a  mov     rcx, r12; void *
0x1400be70d  call    memset_0
0x1400be712  mov     r15, r14
0x1400be715  mov     [rsp+218h+var_F8], r14
0x1400be71d  test    rbx, rbx
0x1400be720  jz      loc_1400BE7D8
0x1400be726  mov     ecx, dword ptr [rsp+218h+arg_0]
0x1400be72d  shl     rcx, 3; cb
0x1400be731  call    cs:__imp_CoTaskMemAlloc
0x1400be737  mov     r15, rax
0x1400be73a  mov     [rsp+218h+var_F8], rax
0x1400be742  test    rax, rax
0x1400be745  jnz     short loc_1400BE7C2
0x1400be747  mov     rcx, r12; pv
0x1400be74a  call    cs:__imp_CoTaskMemFree
0x1400be750  mov     [rsp+218h+var_1B8], r13
0x1400be755  lea     rax, aCvsshardwarepr_78; "CVssHardwareProviderWrapper::GetLunInfo"...
0x1400be75c  mov     [rsp+218h+var_1B0], rax
0x1400be761  lea     rax, aCorhwutc; "CORHWUTC"
0x1400be768  mov     [rsp+218h+var_1A8], rax
0x1400be76d  mov     [rsp+218h+var_1A0], 87Dh
0x1400be775  mov     [rsp+218h+var_19C], edi
0x1400be779  mov     [rsp+218h+var_198], 0FFh
0x1400be784  mov     [rsp+218h+var_118], 1000000h
0x1400be78f  xor     edx, edx; Val
0x1400be791  lea     r8d, [r15+78h]; Size
0x1400be795  lea     rcx, [rsp+218h+var_190]; void *
0x1400be79d  call    memset_0
0x1400be7a2  lea     r9, aCannotAllocate_16; "Cannot allocate device names array"
0x1400be7a9  mov     r8d, 8007000Eh
0x1400be7af  lea     rdx, [rsp+218h+var_1B8]
0x1400be7b4  lea     rcx, [rsp+218h+var_C8]
0x1400be7bc  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400be7c2  mov     r8d, dword ptr [rsp+218h+arg_0]
0x1400be7ca  shl     r8, 3; Size
0x1400be7ce  xor     edx, edx; Val
0x1400be7d0  mov     rcx, rax; void *
0x1400be7d3  call    memset_0
0x1400be7d8  mov     [rsp+218h+pv], r14
0x1400be7e0  mov     edx, r14d
0x1400be7e3  mov     [rsp+218h+var_108], edx
0x1400be7ea  cmp     edx, dword ptr [rsp+218h+arg_0]
0x1400be7f1  jnb     loc_1400BEEC9
0x1400be7f7  lea     rcx, [rsp+218h+var_1C0]
0x1400be7fc  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x1400be801  nop
0x1400be802  lea     rcx, [rsp+218h+var_100]
0x1400be80a  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x1400be80f  nop
0x1400be810  mov     edi, edx
0x1400be812  lea     r13, [rdi+rdi*2]
0x1400be816  shl     r13, 5
0x1400be81a  add     r13, r12
0x1400be81d  mov     dword ptr [r13+0], 1
0x1400be825  mov     rax, [rsi]
0x1400be828  lea     r8, [rsp+218h+var_100]
0x1400be830  mov     rcx, rsi
0x1400be833  mov     rax, [rax+0B0h]
0x1400be83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400be83f  mov     [rsp+218h+var_C0], eax
0x1400be846  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400be84d  mov     [rsp+218h+var_1B8], rax
0x1400be852  lea     rax, aCvsshardwarepr_78; "CVssHardwareProviderWrapper::GetLunInfo"...
0x1400be859  mov     [rsp+218h+var_1B0], rax
0x1400be85e  lea     rax, aCorhwutc; "CORHWUTC"
0x1400be865  mov     [rsp+218h+var_1A8], rax
0x1400be86a  mov     [rsp+218h+var_1A0], 893h
0x1400be872  mov     esi, 1
0x1400be877  mov     [rsp+218h+var_19C], esi
0x1400be87b  mov     [rsp+218h+var_198], 0FFh
0x1400be886  mov     [rsp+218h+var_118], 1000000h
0x1400be891  xor     edx, edx; Val
0x1400be893  lea     r8d, [rsi+77h]; Size
0x1400be897  lea     rcx, [rsp+218h+var_190]; void *
0x1400be89f  call    memset_0
0x1400be8a4  lea     r8, aIvsssnapshotde_7; "IVssSnapshotDescription::GetLunMapping"
0x1400be8ab  lea     rdx, [rsp+218h+var_1B8]
0x1400be8b0  lea     rcx, [rsp+218h+var_C8]
0x1400be8b8  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400be8bd  test    rbx, rbx
0x1400be8c0  jz      loc_1400BEA3E
0x1400be8c6  mov     [rsp+218h+bstrString], r14
0x1400be8ce  mov     rcx, [rsp+218h+var_100]
0x1400be8d6  mov     rax, [rcx]
0x1400be8d9  lea     rdx, [rsp+218h+bstrString]
0x1400be8e1  mov     rax, [rax+30h]
0x1400be8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400be8ea  mov     [rsp+218h+var_C0], eax
0x1400be8f1  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400be8f8  mov     [rsp+218h+var_1B8], rax
0x1400be8fd  lea     rax, aCvsshardwarepr_78; "CVssHardwareProviderWrapper::GetLunInfo"...
0x1400be904  mov     [rsp+218h+var_1B0], rax
0x1400be909  lea     rax, aCorhwutc; "CORHWUTC"
0x1400be910  mov     [rsp+218h+var_1A8], rax
0x1400be915  mov     [rsp+218h+var_1A0], 89Ah
0x1400be91d  mov     [rsp+218h+var_19C], esi
0x1400be921  mov     [rsp+218h+var_198], 0FFh
0x1400be92c  mov     [rsp+218h+var_118], 1000000h
0x1400be937  xor     edx, edx; Val
0x1400be939  lea     r8d, [rsi+77h]; Size
0x1400be93d  lea     rcx, [rsp+218h+var_190]; void *
0x1400be945  call    memset_0
0x1400be94a  lea     r8, aIlunmappipngGe; "ILunMappipng::GetSourceDevice"
0x1400be951  lea     rdx, [rsp+218h+var_1B8]
0x1400be956  lea     rcx, [rsp+218h+var_C8]
0x1400be95e  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400be963  lea     rcx, [rsp+218h+bstrString]; this
0x1400be96b  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x1400be970  lea     ebx, [rax+1]
0x1400be973  lea     ecx, [rbx+rbx]; cb
0x1400be976  call    cs:__imp_CoTaskMemAlloc
0x1400be97c  mov     [r15+rdi*8], rax
0x1400be980  test    rax, rax
0x1400be983  jnz     short loc_1400BE9FD
0x1400be985  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400be98c  mov     [rsp+218h+var_1B8], rax
0x1400be991  lea     rax, aCvsshardwarepr_78; "CVssHardwareProviderWrapper::GetLunInfo"...
0x1400be998  mov     [rsp+218h+var_1B0], rax
0x1400be99d  lea     rax, aCorhwutc; "CORHWUTC"
0x1400be9a4  mov     [rsp+218h+var_1A8], rax
0x1400be9a9  mov     [rsp+218h+var_1A0], 89Eh
0x1400be9b1  mov     [rsp+218h+var_19C], esi
0x1400be9b5  mov     [rsp+218h+var_198], 0FFh
0x1400be9c0  mov     [rsp+218h+var_118], 1000000h
0x1400be9cb  xor     edx, edx; Val
0x1400be9cd  lea     r8d, [rsi+77h]; Size
0x1400be9d1  lea     rcx, [rsp+218h+var_190]; void *
0x1400be9d9  call    memset_0
0x1400be9de  lea     r9, aCannotAllocate_15; "Cannot allocate source device name"
0x1400be9e5  mov     r8d, 8007000Eh
0x1400be9eb  lea     rdx, [rsp+218h+var_1B8]
0x1400be9f0  lea     rcx, [rsp+218h+var_C8]
0x1400be9f8  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400be9fd  lea     rcx, [rsp+218h+bstrString]; this
0x1400bea05  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x1400bea0a  mov     rcx, [r15+rdi*8]; unsigned __int16 *
0x1400bea0e  mov     rdx, rbx; unsigned __int64
0x1400bea11  test    eax, eax
0x1400bea13  mov     r8, [rsp+218h+bstrString]
0x1400bea1b  jnz     short loc_1400BEA24
0x1400bea1d  lea     r8, byte_1400F9C88; unsigned __int16 *
0x1400bea24  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400bea29  mov     [rsp+218h+var_C0], eax
0x1400bea30  mov     rcx, [rsp+218h+bstrString]; bstrString
0x1400bea38  call    cs:__imp_SysFreeString
0x1400bea3e  cmp     [rsp+218h+var_C0], r14d
0x1400bea46  jge     short loc_1400BEAC2
0x1400bea48  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400bea4f  mov     [rsp+218h+var_1B8], rax
0x1400bea54  lea     rax, aCvsshardwarepr_78; "CVssHardwareProviderWrapper::GetLunInfo"...
0x1400bea5b  mov     [rsp+218h+var_1B0], rax
0x1400bea60  lea     rax, aCorhwutc; "CORHWUTC"
0x1400bea67  mov     [rsp+218h+var_1A8], rax
0x1400bea6c  mov     [rsp+218h+var_1A0], 8A5h
0x1400bea74  mov     [rsp+218h+var_19C], esi
0x1400bea78  mov     [rsp+218h+var_198], 0FFh
0x1400bea83  mov     [rsp+218h+var_118], 1000000h
0x1400bea8e  xor     edx, edx; Val
0x1400bea90  lea     r8d, [rdx+78h]; Size
0x1400bea94  lea     rcx, [rsp+218h+var_190]; void *
0x1400bea9c  call    memset_0
0x1400beaa1  lea     r9, aStringcchcopyw; "StringCchCopyW()"
0x1400beaa8  mov     r8d, [rsp+218h+var_C0]
0x1400beab0  lea     rdx, [rsp+218h+var_1B8]
0x1400beab5  lea     rcx, [rsp+218h+var_C8]
0x1400beabd  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1400beac2  mov     rcx, [rsp+218h+var_100]
0x1400beaca  lea     rdx, [rsp+218h+var_1C0]
0x1400beacf  mov     rax, [rcx]
0x1400bead2  cmp     [rsp+218h+arg_10], r14b
0x1400beada  jz      short loc_1400BEAE7
0x1400beadc  mov     rax, [rax+48h]
0x1400beae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400beae5  jmp     short loc_1400BEAF0
0x1400beae7  mov     rax, [rax+40h]
0x1400beaeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400beaf0  mov     [rsp+218h+var_C0], eax
0x1400beaf7  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400beafe  mov     [rsp+218h+var_1B8], rax
0x1400beb03  lea     rax, aCvsshardwarepr_78; "CVssHardwareProviderWrapper::GetLunInfo"...
0x1400beb0a  mov     [rsp+218h+var_1B0], rax
0x1400beb0f  lea     rax, aCorhwutc; "CORHWUTC"
0x1400beb16  mov     [rsp+218h+var_1A8], rax
0x1400beb1b  mov     [rsp+218h+var_1A0], 8AEh
0x1400beb23  mov     [rsp+218h+var_19C], esi
0x1400beb27  mov     [rsp+218h+var_198], 0FFh
0x1400beb32  mov     [rsp+218h+var_118], 1000000h
0x1400beb3d  xor     edx, edx; Val
0x1400beb3f  lea     r8d, [rdx+78h]; Size
0x1400beb43  lea     rcx, [rsp+218h+var_190]; void *
0x1400beb4b  call    memset_0
0x1400beb50  lea     r8, aIvsslunmapping_1; "IVssLunMapping::GetSourceLun"
0x1400beb57  lea     rdx, [rsp+218h+var_1B8]
0x1400beb5c  lea     rcx, [rsp+218h+var_C8]
0x1400beb64  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400beb69  mov     rcx, [rsp+218h+var_1C0]
0x1400beb6e  mov     rax, [rcx]
0x1400beb71  lea     r10, [r13+0Ch]
0x1400beb75  lea     r11, [r13+28h]
0x1400beb79  lea     rbx, [r13+20h]
0x1400beb7d  lea     rdi, [r13+18h]
0x1400beb81  lea     rsi, [r13+10h]
0x1400beb85  lea     r9, [r13+8]
0x1400beb89  lea     r8, [r13+5]
0x1400beb8d  lea     rdx, [r13+4]
0x1400beb91  mov     [rsp+218h+var_1D8], r10
0x1400beb96  mov     [rsp+218h+var_1E0], r11
0x1400beb9b  mov     [rsp+218h+var_1E8], rbx
0x1400beba0  mov     [rsp+218h+var_1F0], rdi
0x1400beba5  mov     [rsp+218h+var_1F8], rsi
0x1400bebaa  mov     rax, [rax+20h]
0x1400bebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400bebb3  mov     [rsp+218h+var_C0], eax
  ... truncated ...
```
