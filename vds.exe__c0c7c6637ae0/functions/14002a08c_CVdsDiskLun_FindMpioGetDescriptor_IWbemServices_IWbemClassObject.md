# CVdsDiskLun::FindMpioGetDescriptor(IWbemServices *,IWbemClassObject * *)

- ea: `0x14002a08c`
- end: `0x14002a70e`
- name: `?FindMpioGetDescriptor@CVdsDiskLun@@AEAAJPEAUIWbemServices@@PEAPEAUIWbemClassObject@@@Z`
- size: `1666`
- prototype: `int(CVdsDiskLun *__hidden this, struct IWbemServices *, struct IWbemClassObject **)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140046390`
- `0x140046ef0`
- `0x140049360`
- `0x14004a6d0`

## callees

- `0x140012c48`
- `0x14001f220`
- `0x14002a08c`
- `0x14002e123`
- `0x14003d60c`
- `0x14003d638`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a5bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a5d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a5eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a602`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a5bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a5d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a5eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a602`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a2b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a636`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002a2a8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002a2a8`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14002a10d`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14002a10d`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14002a6aa`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14002a6aa`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x14002a41c`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x14002a41c`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x14002a43f`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x14002a43f`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14002a48c`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14002a4a9`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14002a4c6`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14002a4df`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14002a48c`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14002a4a9`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14002a4c6`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14002a4df`
- `vdsutil!VdsWmiGetObjectFromInstance` at `0x14002a46f`
- `vdsutil!VdsWmiGetObjectFromInstance` at `0x14002a46f`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14002a3e2`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14002a68a`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14002a3e2`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14002a68a`
- `vdsutil!OpenDevice` at `0x14002a237`
- `vdsutil!OpenDevice` at `0x14002a237`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002a14e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002a14e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002a69f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002a69f`
- `vdsutil!VdsTraceW` at `0x14002a183`
- `vdsutil!VdsTraceW` at `0x14002a207`
- `vdsutil!VdsTraceW` at `0x14002a21e`
- `vdsutil!VdsTraceW` at `0x14002a24f`
- `vdsutil!VdsTraceW` at `0x14002a361`
- `vdsutil!VdsTraceW` at `0x14002a595`
- `vdsutil!VdsTraceW` at `0x14002a5a9`
- `vdsutil!VdsTraceW` at `0x14002a183`
- `vdsutil!VdsTraceW` at `0x14002a207`
- `vdsutil!VdsTraceW` at `0x14002a21e`
- `vdsutil!VdsTraceW` at `0x14002a24f`
- `vdsutil!VdsTraceW` at `0x14002a361`
- `vdsutil!VdsTraceW` at `0x14002a595`
- `vdsutil!VdsTraceW` at `0x14002a5a9`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a2cd`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a2e1`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a2f2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a304`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a314`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a324`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a334`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a2cd`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a2e1`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a2f2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a304`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a314`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a324`
- `OLEAUT32!__imp_SysAllocString` at `0x14002a334`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a649`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a653`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a65c`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a665`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a66e`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a677`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a680`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a649`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a653`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a65c`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a665`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a66e`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a677`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a680`
- `OLEAUT32!__imp_VariantInit` at `0x14002a16f`
- `OLEAUT32!__imp_VariantInit` at `0x14002a16f`
- `OLEAUT32!__imp_VariantClear` at `0x14002a3ec`
- `OLEAUT32!__imp_VariantClear` at `0x14002a694`
- `OLEAUT32!__imp_VariantClear` at `0x14002a3ec`
- `OLEAUT32!__imp_VariantClear` at `0x14002a694`

## string_xrefs

- `0x14002a246`: `CVdsDiskLun::FindMpioGetDescriptor, 4, error=%ld`
- `0x14002a2bd`: `CVdsDiskLun::FindMpioGetDescriptor, 5, error=%ld`
- `0x14002a140`: `CVdsDiskLun::FindMpioGetDescriptor()`
- `0x14002a17a`: `CVdsDiskLun::FindMpioGetDescriptor, 1`
- `0x14002a1fb`: `CVdsDiskLun::FindMpioGetDescriptor, 2, hr=%lX`
- `0x14002a212`: `CVdsDiskLun::FindMpioGetDescriptor, 3, hr=%lX`
- `0x14002a2c6`: `MPIO_GET_DESCRIPTOR`
- `0x14002a30d`: `ScsiPathId`
- `0x14002a355`: `CVdsDiskLun::FindMpioGetDescriptor: VdsWmiCreateInstanceEnum MPIO_GET_DESCRIPTOR: WBEM_E_INVALID_CLASS`
- `0x14002a375`: `CVdsDiskLun::FindMpioGetDescriptor: VdsWmiCreateInstanceEnum MPIO_GET_DESCRIPTOR failed: %X`
- `0x14002a59d`: `CVdsDiskLun::FindMpioGetDescriptor: spMpioGetDescriptorEnum->Next: WBEM_E_INVALID_CLASS`
- `0x14002a589`: `CVdsDiskLun::FindMpioGetDescriptor: spMpioGetDescriptorEnum->Next failed: %X`
- `0x14002a577`: `CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetVariantObjectArrayFromInstance PdoInformation failed: %X`
- `0x14002a56e`: `CVdsDiskLun::FindMpioGetDescriptor: vdsPdoInformationEnum.Attach failed: %X`
- `0x14002a565`: `CVdsDiskLun::FindMpioGetDescriptor: vdsPdoInformationEnum.Next failed: %X`
- `0x14002a55c`: `CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance ScsiAddress failed: %X`
- `0x14002a553`: `CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance PortNumber failed: %X`
- `0x14002a54a`: `CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance ScsiPathId failed: %X`
- `0x14002a541`: `CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance TargetId failed: %X`
- `0x14002a538`: `CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance Lun failed: %X`
- `0x14002a580`: `CVdsDiskLun::FindMpioGetDescriptor: Could not find MPIO instance corresponding to LUN.`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CVdsDiskLun::FindMpioGetDescriptor(
        CVdsDiskLun *this,
        struct IWbemServices *a2,
        struct IWbemClassObject **a3)
{
  OLECHAR *v6; // r13
  OLECHAR *v7; // r14
  OLECHAR *v8; // r15
  OLECHAR *v9; // r12
  OLECHAR *LastError; // rbx
  OLECHAR *v11; // rdi
  int v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  int v15; // eax
  int VariantFromInstance; // eax
  int v17; // eax
  int v18; // eax
  int ObjectFromInstance; // eax
  int ByteFromInstance; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  struct IWbemClassObject *v24; // rax
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  BSTR v27; // [rsp+48h] [rbp-B8h]
  __int64 OutBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  struct IWbemClassObject *v30; // [rsp+60h] [rbp-A0h] BYREF
  int v31; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hDevice; // [rsp+70h] [rbp-90h] BYREF
  struct IWbemClassObject *v33; // [rsp+78h] [rbp-88h] BYREF
  DWORD BytesReturned; // [rsp+80h] [rbp-80h] BYREF
  BSTR v35; // [rsp+88h] [rbp-78h]
  struct IEnumWbemClassObject *v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-60h]
  VARIANTARG pvarg; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v40[24]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[24]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v42[88]; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+148h] [rbp+48h]
  LPVOID v44; // [rsp+150h] [rbp+50h]
  LPVOID v45; // [rsp+158h] [rbp+58h]
  LPVOID v46; // [rsp+160h] [rbp+60h]
  LPVOID v47; // [rsp+168h] [rbp+68h]

  v6 = 0;
  v37 = 0;
  memset_0(v42, 0, 0x80u);
  BytesReturned = 0;
  hDevice = (HANDLE)-1LL;
  v36 = 0;
  v30 = 0;
  v33 = 0;
  v29 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v40);
  bstrString = 0;
  v35 = 0;
  v27 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v31 = 0;
  v26 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v41, 0x5Eu, "CVdsDiskLun::FindMpioGetDescriptor()");
  memset_0(v42, 0, 0x80u);
  OutBuffer = 0;
  VariantInit(&pvarg);
  if ( !a3 )
  {
    VdsTraceW(0, L"CVdsDiskLun::FindMpioGetDescriptor, 1");
    LODWORD(LastError) = -2147024809;
LABEL_3:
    v11 = v27;
    goto LABEL_48;
  }
  *a3 = 0;
  if ( (**(int (__fastcall ***)(CVdsDiskLun *, GUID *, __int64 *))this)(this, &IID_IVdsDisk, &v37) < 0 )
  {
    LODWORD(LastError) = 0;
    v11 = 0;
    goto LABEL_48;
  }
  memset_0(v42, 0, 0x80u);
  v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v37 + 24LL))(v37, v42);
  LODWORD(LastError) = v12;
  if ( v12 < 0 )
  {
    if ( v12 == -2147212277 )
      VdsTraceW(1, L"CVdsDiskLun::FindMpioGetDescriptor, 2, hr=%lX");
    else
      VdsTraceW(0, L"CVdsDiskLun::FindMpioGetDescriptor, 3, hr=%lX", (unsigned int)v12);
    goto LABEL_3;
  }
  v13 = OpenDevice(v47, 0x80000000LL, &hDevice);
  LODWORD(LastError) = v13;
  if ( v13 )
  {
    VdsTraceW(0, L"CVdsDiskLun::FindMpioGetDescriptor, 4, error=%ld", v13);
    goto LABEL_12;
  }
  OutBuffer = 0;
  if ( !DeviceIoControl(hDevice, 0x41018u, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
  {
    LastError = (OLECHAR *)GetLastError();
    VdsTraceW(0, L"CVdsDiskLun::FindMpioGetDescriptor, 5, error=%ld", LastError);
LABEL_12:
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_3;
  }
  LastError = SysAllocString(L"MPIO_GET_DESCRIPTOR");
  bstrString = LastError;
  v35 = SysAllocString(L"PdoInformation");
  v27 = SysAllocString(L"ScsiAddress");
  v7 = SysAllocString(L"PortNumber");
  v8 = SysAllocString(L"ScsiPathId");
  v9 = SysAllocString(L"TargetId");
  v6 = SysAllocString(L"Lun");
  v14 = VdsWmiCreateInstanceEnum(a2, LastError, &v36);
  LODWORD(LastError) = v14;
  if ( v14 == -2147217392 )
  {
    VdsTraceW(
      3,
      L"CVdsDiskLun::FindMpioGetDescriptor: VdsWmiCreateInstanceEnum MPIO_GET_DESCRIPTOR: WBEM_E_INVALID_CLASS");
    v11 = v27;
  }
  else
  {
    if ( v14 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::FindMpioGetDescriptor: VdsWmiCreateInstanceEnum MPIO_GET_DESCRIPTOR failed: %X",
        (unsigned int)v14);
      goto LABEL_3;
    }
    v11 = v27;
    while ( 1 )
    {
      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v30);
      v15 = ((__int64 (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, struct IWbemClassObject **, int *))v36->lpVtbl->Next)(
              v36,
              0xFFFFFFFFLL,
              1,
              &v30,
              &v31);
      LODWORD(LastError) = v15;
      if ( v15 == -2147217392 )
        break;
      if ( v15 < 0 )
      {
        VdsTraceW(0, L"CVdsDiskLun::FindMpioGetDescriptor: spMpioGetDescriptorEnum->Next failed: %X", (unsigned int)v15);
        goto LABEL_48;
      }
      if ( v15 || v31 != 1 )
      {
        VdsTraceW(3, L"CVdsDiskLun::FindMpioGetDescriptor: Could not find MPIO instance corresponding to LUN.");
        goto LABEL_47;
      }
      CVdsWmiVariantObjectArrayEnum::Detach((CVdsWmiVariantObjectArrayEnum *)v40);
      VariantClear(&pvarg);
      VariantFromInstance = VdsWmiGetVariantFromInstance(v30, v35, 0x200Du, &pvarg);
      LODWORD(LastError) = VariantFromInstance;
      if ( VariantFromInstance < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetVariantObjectArrayFromInstance PdoInformation failed: %X",
          (unsigned int)VariantFromInstance);
        goto LABEL_48;
      }
      v17 = CVdsWmiVariantObjectArrayEnum::Attach((CVdsWmiVariantObjectArrayEnum *)v40, &pvarg);
      LODWORD(LastError) = v17;
      if ( v17 < 0 )
      {
        VdsTraceW(0, L"CVdsDiskLun::FindMpioGetDescriptor: vdsPdoInformationEnum.Attach failed: %X", (unsigned int)v17);
        goto LABEL_48;
      }
      while ( 1 )
      {
        ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v33);
        v18 = CVdsWmiVariantObjectArrayEnum::Next((CVdsWmiVariantObjectArrayEnum *)v40, &v33);
        LODWORD(LastError) = v18;
        if ( v18 == 1 )
          break;
        if ( v18 < 0 )
        {
          VdsTraceW(0, L"CVdsDiskLun::FindMpioGetDescriptor: vdsPdoInformationEnum.Next failed: %X", (unsigned int)v18);
          goto LABEL_48;
        }
        ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v29);
        ObjectFromInstance = VdsWmiGetObjectFromInstance(v33, v11, &v29);
        LODWORD(LastError) = ObjectFromInstance;
        if ( ObjectFromInstance < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance ScsiAddress failed: %X",
            (unsigned int)ObjectFromInstance);
          goto LABEL_48;
        }
        ByteFromInstance = VdsWmiGetByteFromInstance(v29, v7, &v26);
        LODWORD(LastError) = ByteFromInstance;
        if ( ByteFromInstance < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance PortNumber failed: %X",
            (unsigned int)ByteFromInstance);
          goto LABEL_48;
        }
        v21 = VdsWmiGetByteFromInstance(v29, v8, (char *)&v26 + 1);
        LODWORD(LastError) = v21;
        if ( v21 < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance ScsiPathId failed: %X",
            (unsigned int)v21);
          goto LABEL_48;
        }
        v22 = VdsWmiGetByteFromInstance(v29, v9, (char *)&v26 + 2);
        LODWORD(LastError) = v22;
        if ( v22 < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance TargetId failed: %X",
            (unsigned int)v22);
          goto LABEL_48;
        }
        v23 = VdsWmiGetByteFromInstance(v29, v6, (char *)&v26 + 3);
        LODWORD(LastError) = v23;
        if ( v23 < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::FindMpioGetDescriptor: VdsWmiGetObjectFromInstance Lun failed: %X",
            (unsigned int)v23);
          goto LABEL_48;
        }
        if ( HIDWORD(OutBuffer) == v26 )
        {
          v24 = v30;
          v30 = 0;
          *a3 = v24;
          LODWORD(LastError) = 0;
          goto LABEL_48;
        }
      }
    }
    VdsTraceW(3, L"CVdsDiskLun::FindMpioGetDescriptor: spMpioGetDescriptorEnum->Next: WBEM_E_INVALID_CLASS");
  }
LABEL_47:
  LODWORD(LastError) = -2147212288;
LABEL_48:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v44 )
  {
    CoTaskMemFree(v44);
    v44 = 0;
  }
  if ( v45 )
  {
    CoTaskMemFree(v45);
    v45 = 0;
  }
  if ( v46 )
  {
    CoTaskMemFree(v46);
    v46 = 0;
  }
  if ( v47 )
  {
    CoTaskMemFree(v47);
    v47 = 0;
  }
  if ( (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hDevice);
    hDevice = (HANDLE)-1LL;
  }
  SysFreeString(bstrString);
  SysFreeString(v35);
  SysFreeString(v11);
  SysFreeString(v7);
  SysFreeString(v8);
  SysFreeString(v9);
  SysFreeString(v6);
  CVdsWmiVariantObjectArrayEnum::Detach((CVdsWmiVariantObjectArrayEnum *)v40);
  VariantClear(&pvarg);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v41);
  CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14002a08c  mov     [rsp-8+arg_18], rbx
0x14002a091  push    rbp
0x14002a092  push    rsi
0x14002a093  push    rdi
0x14002a094  push    r12
0x14002a096  push    r13
0x14002a098  push    r14
0x14002a09a  push    r15
0x14002a09c  lea     rbp, [rsp-80h]
0x14002a0a1  sub     rsp, 180h
0x14002a0a8  mov     rax, cs:__security_cookie
0x14002a0af  xor     rax, rsp
0x14002a0b2  mov     [rbp+0B0h+var_40], rax
0x14002a0b6  mov     rsi, r8
0x14002a0b9  mov     rdi, rdx
0x14002a0bc  mov     rbx, rcx
0x14002a0bf  xor     r13d, r13d
0x14002a0c2  mov     [rbp+0B0h+var_118], r13
0x14002a0c6  xor     edx, edx; Val
0x14002a0c8  mov     r8d, 80h; Size
0x14002a0ce  lea     rcx, [rbp+0B0h+var_C0]; void *
0x14002a0d2  call    memset_0
0x14002a0d7  mov     [rbp+0B0h+BytesReturned], r13d
0x14002a0db  mov     [rsp+1B0h+hDevice], 0FFFFFFFFFFFFFFFFh
0x14002a0e4  mov     [rsp+1B0h+OutBuffer], r13
0x14002a0e9  mov     [rbp+0B0h+var_120], r13
0x14002a0ed  mov     [rsp+1B0h+var_150], r13
0x14002a0f2  mov     [rsp+1B0h+var_138], r13
0x14002a0f7  mov     [rsp+1B0h+var_158], r13
0x14002a0fc  xorps   xmm0, xmm0
0x14002a0ff  xor     eax, eax
0x14002a101  movups  xmmword ptr [rbp+0B0h+pvarg], xmm0
0x14002a105  mov     qword ptr [rbp+0B0h+pvarg+10h], rax
0x14002a109  lea     rcx, [rbp+0B0h+var_F0]
0x14002a10d  call    cs:__imp_??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum(void)
0x14002a113  nop
0x14002a114  mov     [rbp+0B0h+bstrString], r13
0x14002a118  mov     [rbp+0B0h+var_128], r13
0x14002a11c  mov     [rsp+1B0h+var_168], r13
0x14002a121  mov     r14d, r13d
0x14002a124  mov     r15d, r13d
0x14002a127  mov     r12d, r13d
0x14002a12a  xor     eax, eax
0x14002a12c  mov     [rsp+1B0h+var_148], eax
0x14002a130  mov     byte ptr [rsp+1B0h+var_170], al
0x14002a134  mov     byte ptr [rsp+1B0h+var_170+1], al
0x14002a138  mov     byte ptr [rsp+1B0h+var_170+2], al
0x14002a13c  mov     byte ptr [rsp+1B0h+var_170+3], al
0x14002a140  lea     r8, aCvdsdisklunFin_9; "CVdsDiskLun::FindMpioGetDescriptor()"
0x14002a147  lea     edx, [rax+5Eh]
0x14002a14a  lea     rcx, [rbp+0B0h+var_D8]
0x14002a14e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002a154  nop
0x14002a155  xor     edx, edx; Val
0x14002a157  mov     r8d, 80h; Size
0x14002a15d  lea     rcx, [rbp+0B0h+var_C0]; void *
0x14002a161  call    memset_0
0x14002a166  mov     [rsp+1B0h+OutBuffer], r13
0x14002a16b  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x14002a16f  call    cs:__imp_VariantInit
0x14002a175  test    rsi, rsi
0x14002a178  jnz     short loc_14002A198
0x14002a17a  lea     rdx, aCvdsdisklunFin_26; "CVdsDiskLun::FindMpioGetDescriptor, 1"
0x14002a181  xor     ecx, ecx
0x14002a183  call    cs:__imp_VdsTraceW
0x14002a189  mov     ebx, 80070057h
0x14002a18e  mov     rdi, [rsp+1B0h+var_168]
0x14002a193  jmp     loc_14002A5B4
0x14002a198  mov     qword ptr [rsi], 0
0x14002a19f  mov     rax, [rbx]
0x14002a1a2  lea     r8, [rbp+0B0h+var_118]
0x14002a1a6  lea     rdx, IID_IVdsDisk
0x14002a1ad  mov     rcx, rbx
0x14002a1b0  mov     rax, [rax]
0x14002a1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a1b8  test    eax, eax
0x14002a1ba  jns     short loc_14002A1C5
0x14002a1bc  xor     ebx, ebx
0x14002a1be  mov     edi, ebx
0x14002a1c0  jmp     loc_14002A5B4
0x14002a1c5  xor     edx, edx; Val
0x14002a1c7  mov     r8d, 80h; Size
0x14002a1cd  lea     rcx, [rbp+0B0h+var_C0]; void *
0x14002a1d1  call    memset_0
0x14002a1d6  mov     rcx, [rbp+0B0h+var_118]
0x14002a1da  mov     rax, [rcx]
0x14002a1dd  lea     rdx, [rbp+0B0h+var_C0]
0x14002a1e1  mov     rax, [rax+18h]
0x14002a1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a1ea  mov     ebx, eax
0x14002a1ec  test    eax, eax
0x14002a1ee  jns     short loc_14002A229
0x14002a1f0  mov     r8d, 8004240Bh
0x14002a1f6  cmp     eax, r8d
0x14002a1f9  jnz     short loc_14002A212
0x14002a1fb  lea     rdx, aCvdsdisklunFin_27; "CVdsDiskLun::FindMpioGetDescriptor, 2, "...
0x14002a202  mov     ecx, 1
0x14002a207  call    cs:__imp_VdsTraceW
0x14002a20d  jmp     loc_14002A18E
0x14002a212  lea     rdx, aCvdsdisklunFin_25; "CVdsDiskLun::FindMpioGetDescriptor, 3, "...
0x14002a219  mov     r8d, eax
0x14002a21c  xor     ecx, ecx
0x14002a21e  call    cs:__imp_VdsTraceW
0x14002a224  jmp     loc_14002A18E
0x14002a229  lea     r8, [rsp+1B0h+hDevice]
0x14002a22e  mov     edx, 80000000h
0x14002a233  mov     rcx, [rbp+0B0h+var_48]
0x14002a237  call    cs:__imp_OpenDevice
0x14002a23d  mov     ebx, eax
0x14002a23f  test    eax, eax
0x14002a241  jz      short loc_14002A26B
0x14002a243  mov     r8d, eax
0x14002a246  lea     rdx, aCvdsdisklunFin_1; "CVdsDiskLun::FindMpioGetDescriptor, 4, "...
0x14002a24d  xor     ecx, ecx
0x14002a24f  call    cs:__imp_VdsTraceW
0x14002a255  test    ebx, ebx
0x14002a257  jle     loc_14002A18E
0x14002a25d  movzx   ebx, bx
0x14002a260  or      ebx, 80070000h
0x14002a266  jmp     loc_14002A18E
0x14002a26b  mov     [rsp+1B0h+OutBuffer], 0
0x14002a274  mov     [rsp+1B0h+lpOverlapped], 0; lpOverlapped
0x14002a27d  lea     rax, [rbp+0B0h+BytesReturned]
0x14002a281  mov     [rsp+1B0h+lpBytesReturned], rax; lpBytesReturned
0x14002a286  mov     [rsp+1B0h+nOutBufferSize], 8; nOutBufferSize
0x14002a28e  lea     rax, [rsp+1B0h+OutBuffer]
0x14002a293  mov     [rsp+1B0h+lpOutBuffer], rax; lpOutBuffer
0x14002a298  xor     r9d, r9d; nInBufferSize
0x14002a29b  xor     r8d, r8d; lpInBuffer
0x14002a29e  mov     edx, 41018h; dwIoControlCode
0x14002a2a3  mov     rcx, [rsp+1B0h+hDevice]; hDevice
0x14002a2a8  call    cs:__imp_DeviceIoControl
0x14002a2ae  test    eax, eax
0x14002a2b0  jnz     short loc_14002A2C6
0x14002a2b2  call    cs:__imp_GetLastError
0x14002a2b8  mov     ebx, eax
0x14002a2ba  mov     r8d, eax
0x14002a2bd  lea     rdx, aCvdsdisklunFin_8; "CVdsDiskLun::FindMpioGetDescriptor, 5, "...
0x14002a2c4  jmp     short loc_14002A24D
0x14002a2c6  lea     rcx, psz; "MPIO_GET_DESCRIPTOR"
0x14002a2cd  call    cs:__imp_SysAllocString
0x14002a2d3  mov     rbx, rax
0x14002a2d6  mov     [rbp+0B0h+bstrString], rax
0x14002a2da  lea     rcx, aPdoinformation; "PdoInformation"
0x14002a2e1  call    cs:__imp_SysAllocString
0x14002a2e7  mov     [rbp+0B0h+var_128], rax
0x14002a2eb  lea     rcx, aScsiaddress; "ScsiAddress"
0x14002a2f2  call    cs:__imp_SysAllocString
0x14002a2f8  mov     [rsp+1B0h+var_168], rax
0x14002a2fd  lea     rcx, aPortnumber; "PortNumber"
0x14002a304  call    cs:__imp_SysAllocString
0x14002a30a  mov     r14, rax
0x14002a30d  lea     rcx, aScsipathid; "ScsiPathId"
0x14002a314  call    cs:__imp_SysAllocString
0x14002a31a  mov     r15, rax
0x14002a31d  lea     rcx, aTargetid; "TargetId"
0x14002a324  call    cs:__imp_SysAllocString
0x14002a32a  mov     r12, rax
0x14002a32d  lea     rcx, aLun; "Lun"
0x14002a334  call    cs:__imp_SysAllocString
0x14002a33a  mov     r13, rax
0x14002a33d  lea     r8, [rbp+0B0h+var_120]; struct IEnumWbemClassObject **
0x14002a341  mov     rdx, rbx; unsigned __int16 *
0x14002a344  mov     rcx, rdi; struct IWbemServices *
0x14002a347  call    ?VdsWmiCreateInstanceEnum@@YAJPEAUIWbemServices@@PEAGPEAPEAUIEnumWbemClassObject@@@Z; VdsWmiCreateInstanceEnum(IWbemServices *,ushort *,IEnumWbemClassObject * *)
0x14002a34c  mov     ebx, eax
0x14002a34e  cmp     eax, 80041010h
0x14002a353  jnz     short loc_14002A371
0x14002a355  lea     rdx, aCvdsdisklunFin_21; "CVdsDiskLun::FindMpioGetDescriptor: Vds"...
0x14002a35c  mov     ecx, 3
0x14002a361  call    cs:__imp_VdsTraceW
0x14002a367  mov     rdi, [rsp+1B0h+var_168]
0x14002a36c  jmp     loc_14002A5AF
0x14002a371  test    eax, eax
0x14002a373  jns     short loc_14002A381
0x14002a375  lea     rdx, aCvdsdisklunFin_10; "CVdsDiskLun::FindMpioGetDescriptor: Vds"...
0x14002a37c  jmp     loc_14002A219
0x14002a381  mov     rdi, [rsp+1B0h+var_168]
0x14002a386  lea     rcx, [rsp+1B0h+var_150]
0x14002a38b  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14002a390  mov     rcx, [rbp+0B0h+var_120]
0x14002a394  mov     rax, [rcx]
0x14002a397  lea     rdx, [rsp+1B0h+var_148]
0x14002a39c  mov     [rsp+1B0h+lpOutBuffer], rdx
0x14002a3a1  lea     r9, [rsp+1B0h+var_150]
0x14002a3a6  mov     r8d, 1
0x14002a3ac  or      edx, 0FFFFFFFFh
0x14002a3af  mov     rax, [rax+20h]
0x14002a3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a3b8  mov     ebx, eax
0x14002a3ba  cmp     eax, 80041010h
0x14002a3bf  jz      loc_14002A59D
0x14002a3c5  test    eax, eax
0x14002a3c7  js      loc_14002A589
0x14002a3cd  jnz     loc_14002A580
0x14002a3d3  cmp     [rsp+1B0h+var_148], 1
0x14002a3d8  jnz     loc_14002A580
0x14002a3de  lea     rcx, [rbp+0B0h+var_F0]
0x14002a3e2  call    cs:__imp_?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ; CVdsWmiVariantObjectArrayEnum::Detach(void)
0x14002a3e8  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x14002a3ec  call    cs:__imp_VariantClear
0x14002a3f2  mov     r8d, 200Dh; unsigned __int16
0x14002a3f8  lea     r9, [rbp+0B0h+pvarg]; struct tagVARIANT *
0x14002a3fc  mov     rdx, [rbp+0B0h+var_128]; unsigned __int16 *
0x14002a400  mov     rcx, [rsp+1B0h+var_150]; struct IWbemClassObject *
0x14002a405  call    ?VdsWmiGetVariantFromInstance@@YAJPEAUIWbemClassObject@@PEAGGPEAUtagVARIANT@@@Z; VdsWmiGetVariantFromInstance(IWbemClassObject *,ushort *,ushort,tagVARIANT *)
0x14002a40a  mov     ebx, eax
0x14002a40c  test    eax, eax
0x14002a40e  js      loc_14002A577
0x14002a414  lea     rdx, [rbp+0B0h+pvarg]
0x14002a418  lea     rcx, [rbp+0B0h+var_F0]
0x14002a41c  call    cs:__imp_?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z; CVdsWmiVariantObjectArrayEnum::Attach(tagVARIANT *)
0x14002a422  mov     ebx, eax
0x14002a424  test    eax, eax
0x14002a426  js      loc_14002A56E
0x14002a42c  lea     rcx, [rsp+1B0h+var_138]
0x14002a431  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14002a436  lea     rdx, [rsp+1B0h+var_138]
0x14002a43b  lea     rcx, [rbp+0B0h+var_F0]
0x14002a43f  call    cs:__imp_?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z; CVdsWmiVariantObjectArrayEnum::Next(IWbemClassObject * *)
0x14002a445  mov     ebx, eax
0x14002a447  cmp     eax, 1
0x14002a44a  jz      loc_14002A386
0x14002a450  test    eax, eax
0x14002a452  js      loc_14002A565
0x14002a458  lea     rcx, [rsp+1B0h+var_158]
0x14002a45d  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14002a462  lea     r8, [rsp+1B0h+var_158]
0x14002a467  mov     rdx, rdi
0x14002a46a  mov     rcx, [rsp+1B0h+var_138]
0x14002a46f  call    cs:__imp_VdsWmiGetObjectFromInstance
0x14002a475  mov     ebx, eax
0x14002a477  test    eax, eax
0x14002a479  js      loc_14002A55C
0x14002a47f  lea     r8, [rsp+1B0h+var_170]
0x14002a484  mov     rdx, r14
0x14002a487  mov     rcx, [rsp+1B0h+var_158]
0x14002a48c  call    cs:__imp_VdsWmiGetByteFromInstance
0x14002a492  mov     ebx, eax
0x14002a494  test    eax, eax
0x14002a496  js      loc_14002A553
0x14002a49c  lea     r8, [rsp+1B0h+var_170+1]
0x14002a4a1  mov     rdx, r15
0x14002a4a4  mov     rcx, [rsp+1B0h+var_158]
0x14002a4a9  call    cs:__imp_VdsWmiGetByteFromInstance
0x14002a4af  mov     ebx, eax
0x14002a4b1  test    eax, eax
0x14002a4b3  js      loc_14002A54A
0x14002a4b9  lea     r8, [rsp+1B0h+var_170+2]
0x14002a4be  mov     rdx, r12
0x14002a4c1  mov     rcx, [rsp+1B0h+var_158]
0x14002a4c6  call    cs:__imp_VdsWmiGetByteFromInstance
0x14002a4cc  mov     ebx, eax
0x14002a4ce  test    eax, eax
0x14002a4d0  js      short loc_14002A541
0x14002a4d2  lea     r8, [rsp+1B0h+var_170+3]
0x14002a4d7  mov     rdx, r13
0x14002a4da  mov     rcx, [rsp+1B0h+var_158]
0x14002a4df  call    cs:__imp_VdsWmiGetByteFromInstance
0x14002a4e5  mov     ebx, eax
0x14002a4e7  test    eax, eax
0x14002a4e9  js      short loc_14002A538
0x14002a4eb  mov     al, byte ptr [rsp+1B0h+var_170]
0x14002a4ef  cmp     byte ptr [rsp+1B0h+OutBuffer+4], al
0x14002a4f3  jnz     loc_14002A42C
0x14002a4f9  mov     al, byte ptr [rsp+1B0h+var_170+1]
0x14002a4fd  cmp     byte ptr [rsp+1B0h+OutBuffer+5], al
0x14002a501  jnz     loc_14002A42C
0x14002a507  mov     al, byte ptr [rsp+1B0h+var_170+2]
0x14002a50b  cmp     byte ptr [rsp+1B0h+OutBuffer+6], al
0x14002a50f  jnz     loc_14002A42C
0x14002a515  mov     al, byte ptr [rsp+1B0h+var_170+3]
0x14002a519  cmp     byte ptr [rsp+1B0h+OutBuffer+7], al
0x14002a51d  jnz     loc_14002A42C
0x14002a523  mov     rax, [rsp+1B0h+var_150]
0x14002a528  mov     [rsp+1B0h+var_150], 0
0x14002a531  mov     [rsi], rax
0x14002a534  xor     ebx, ebx
0x14002a536  jmp     short loc_14002A5B4
0x14002a538  lea     rdx, aCvdsdisklunFin_16; "CVdsDiskLun::FindMpioGetDescriptor: Vds"...
0x14002a53f  jmp     short loc_14002A590
0x14002a541  lea     rdx, aCvdsdisklunFin_24; "CVdsDiskLun::FindMpioGetDescriptor: Vds"...
0x14002a548  jmp     short loc_14002A590
0x14002a54a  lea     rdx, aCvdsdisklunFin_0; "CVdsDiskLun::FindMpioGetDescriptor: Vds"...
0x14002a551  jmp     short loc_14002A590
0x14002a553  lea     rdx, aCvdsdisklunFin_28; "CVdsDiskLun::FindMpioGetDescriptor: Vds"...
0x14002a55a  jmp     short loc_14002A590
0x14002a55c  lea     rdx, aCvdsdisklunFin_13; "CVdsDiskLun::FindMpioGetDescriptor: Vds"...
0x14002a563  jmp     short loc_14002A590
0x14002a565  lea     rdx, aCvdsdisklunFin_17; "CVdsDiskLun::FindMpioGetDescriptor: vds"...
0x14002a56c  jmp     short loc_14002A590
0x14002a56e  lea     rdx, aCvdsdisklunFin_11; "CVdsDiskLun::FindMpioGetDescriptor: vds"...
0x14002a575  jmp     short loc_14002A590
0x14002a577  lea     rdx, aCvdsdisklunFin_23; "CVdsDiskLun::FindMpioGetDescriptor: Vds"...
0x14002a57e  jmp     short loc_14002A590
0x14002a580  lea     rdx, aCvdsdisklunFin_19; "CVdsDiskLun::FindMpioGetDescriptor: Cou"...
0x14002a587  jmp     short loc_14002A5A4
0x14002a589  lea     rdx, aCvdsdisklunFin_2; "CVdsDiskLun::FindMpioGetDescriptor: spM"...
0x14002a590  mov     r8d, eax
0x14002a593  xor     ecx, ecx
  ... truncated ...
```
