# CVdsService::LoadIscsiInitiator(void)

- ea: `0x14000ae70`
- end: `0x14000b5b5`
- name: `?LoadIscsiInitiator@CVdsService@@CAJXZ`
- size: `1861`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140009e70`

## callees

- `0x14000ae70`
- `0x14001f220`
- `0x140020968`
- `0x14002e123`
- `0x14003825c`
- `0x14003cd8c`
- `0x14003d60c`
- `0x14003d638`
- `0x14003ea94`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b3ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b3ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b3c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b3c5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000b10e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000b10e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14000aefb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14000aefb`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14000b03a`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14000b03a`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14000b4ca`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14000b4ca`
- `vdsutil!VdsWmiConnectToNamespace` at `0x14000b06b`
- `vdsutil!VdsWmiConnectToNamespace` at `0x14000b06b`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x14000b1a2`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x14000b1a2`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x14000b1c5`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x14000b1c5`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14000b1eb`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14000b1eb`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b20f`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b266`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b2d4`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b2f1`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b307`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b36c`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b20f`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b266`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b2d4`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b2f1`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b307`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14000b36c`
- `vdsutil!VdsWmiGetObjectFromInstance` at `0x14000b237`
- `vdsutil!VdsWmiGetObjectFromInstance` at `0x14000b237`
- `vdsutil!VdsWmiCopyFromVariantByteArray` at `0x14000b2b7`
- `vdsutil!VdsWmiCopyFromVariantByteArray` at `0x14000b2b7`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14000b145`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14000b396`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14000b145`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14000b396`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000aee4`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000aee4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000b55e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000b55e`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000b3d8`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000b3d8`
- `vdsutil!VdsTraceW` at `0x14000b13b`
- `vdsutil!VdsTraceW` at `0x14000b13b`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af2c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af40`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af54`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af65`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af76`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af86`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af96`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afa7`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afb8`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afc8`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afd9`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afea`
- `OLEAUT32!__imp_SysAllocString` at `0x14000affb`
- `OLEAUT32!__imp_SysAllocString` at `0x14000b00c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af2c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af40`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af54`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af65`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af76`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af86`
- `OLEAUT32!__imp_SysAllocString` at `0x14000af96`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afa7`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afb8`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afc8`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afd9`
- `OLEAUT32!__imp_SysAllocString` at `0x14000afea`
- `OLEAUT32!__imp_SysAllocString` at `0x14000affb`
- `OLEAUT32!__imp_SysAllocString` at `0x14000b00c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b441`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b44a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b454`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b45e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b467`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b470`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b47a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b484`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b48d`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b497`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b4a1`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b4ab`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b4b5`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b4bf`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b441`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b44a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b454`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b45e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b467`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b470`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b47a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b484`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b48d`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b497`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b4a1`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b4ab`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b4b5`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b4bf`
- `OLEAUT32!__imp_SysStringLen` at `0x14000b32f`
- `OLEAUT32!__imp_SysStringLen` at `0x14000b32f`
- `OLEAUT32!__imp_VariantInit` at `0x14000b045`
- `OLEAUT32!__imp_VariantInit` at `0x14000b04f`
- `OLEAUT32!__imp_VariantInit` at `0x14000b059`
- `OLEAUT32!__imp_VariantInit` at `0x14000b045`
- `OLEAUT32!__imp_VariantInit` at `0x14000b04f`
- `OLEAUT32!__imp_VariantInit` at `0x14000b059`
- `OLEAUT32!__imp_VariantClear` at `0x14000b352`
- `OLEAUT32!__imp_VariantClear` at `0x14000b3f8`
- `OLEAUT32!__imp_VariantClear` at `0x14000b402`
- `OLEAUT32!__imp_VariantClear` at `0x14000b352`
- `OLEAUT32!__imp_VariantClear` at `0x14000b3f8`
- `OLEAUT32!__imp_VariantClear` at `0x14000b402`

## string_xrefs

- `0x14000af39`: `MSiSCSI_PortalInfoClass`
- `0x14000aed4`: `CVdsService::LoadIscsiInitiator()`
- `0x14000aef4`: `iscsidsc.dll`
- `0x14000b132`: `CVdsService::LoadIscsiInitiator: CVdsIscsiInitiatorAdapterInternal CreateInstance: Out of memory.`
- `0x14000b298`: `CVdsService::LoadIscsiInitiator: Invalid IP address retrieved.`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 CVdsService::LoadIscsiInitiator(void)
{
  CVdsIscsiInitiatorAdapterInternal *v0; // rbx
  OLECHAR *v1; // rsi
  unsigned __int16 *v2; // r14
  OLECHAR *v3; // r15
  OLECHAR *v4; // r12
  OLECHAR *v5; // r13
  int v6; // edi
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // r14
  HRESULT VariantFromInstance; // edi
  int v10; // eax
  UINT v11; // eax
  CVdsIscsiInitiatorAdapterInternal *v12; // rcx
  _BYTE v14[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct IWbemClassObject *v15; // [rsp+38h] [rbp-C8h] BYREF
  struct IWbemClassObject *v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  VDS_IPADDRESS_TYPE v18; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v19; // [rsp+50h] [rbp-B0h] BYREF
  struct IWbemClassObject *v20; // [rsp+58h] [rbp-A8h] BYREF
  void *v21; // [rsp+60h] [rbp-A0h] BYREF
  CVdsIscsiInitiatorAdapterInternal *v22; // [rsp+68h] [rbp-98h] BYREF
  struct IEnumWbemClassObject *v23; // [rsp+70h] [rbp-90h] BYREF
  struct IWbemServices *v24; // [rsp+78h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-80h]
  BSTR v26; // [rsp+88h] [rbp-78h]
  BSTR v27; // [rsp+90h] [rbp-70h]
  BSTR v28; // [rsp+98h] [rbp-68h]
  BSTR v29; // [rsp+A0h] [rbp-60h]
  BSTR v30; // [rsp+A8h] [rbp-58h]
  BSTR v31; // [rsp+B0h] [rbp-50h]
  BSTR v32; // [rsp+B8h] [rbp-48h]
  BSTR v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG v35; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v36[24]; // [rsp+E8h] [rbp-18h] BYREF
  OLECHAR *v37; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v38; // [rsp+108h] [rbp+8h]
  VARIANTARG v39; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG pvarg; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v41[16]; // [rsp+140h] [rbp+40h] BYREF
  GUID pguid; // [rsp+150h] [rbp+50h] BYREF
  _VDS_IPADDRESS v43; // [rsp+160h] [rbp+60h] BYREF

  v17 = 0;
  v14[0] = 0;
  v19 = 0;
  v18 = VDS_IPT_TEXT;
  memset_0(&v43, 0, sizeof(v43));
  pguid = 0;
  v0 = 0;
  v22 = 0;
  v21 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v41, 0x5Eu, "CVdsService::LoadIscsiInitiator()");
  if ( !CVdsService::m_hIscsidscModule )
    CVdsService::m_hIscsidscModule = LoadLibraryW(L"iscsidsc.dll");
  v34 = 0;
  v24 = 0;
  v23 = 0;
  v20 = 0;
  v16 = 0;
  v15 = 0;
  v1 = SysAllocString(L"root\\wmi");
  v37 = v1;
  v2 = SysAllocString(L"MSiSCSI_PortalInfoClass");
  v38 = v2;
  bstrString = SysAllocString(L"InstanceName");
  v26 = SysAllocString(L"PortalInformation");
  v3 = SysAllocString(L"PortalType");
  v4 = SysAllocString(L"Index");
  v27 = SysAllocString(L"IPAddr");
  v28 = SysAllocString(L"Type");
  v5 = SysAllocString(L"IpV4Address");
  v29 = SysAllocString(L"IpV6Address");
  v30 = SysAllocString(L"IpV6FlowInfo");
  v31 = SysAllocString(L"IpV6ScopeId");
  v32 = SysAllocString(L"TextAddress");
  v33 = SysAllocString(L"Port");
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v39, 0, sizeof(v39));
  memset(&v35, 0, sizeof(v35));
  CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v36);
  VariantInit(&pvarg);
  VariantInit(&v39);
  VariantInit(&v35);
  v6 = VdsWmiConnectToNamespace(v1, &v34, &v24);
  if ( v6 >= 0 )
  {
    v6 = VdsWmiCreateInstanceEnum(v24, v2, &v23);
    if ( v6 >= 0 )
    {
      v7 = bstrString;
      v8 = v26;
      while ( 1 )
      {
        ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v20);
        v6 = ((__int64 (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, struct IWbemClassObject **, int *))v23->lpVtbl->Next)(
               v23,
               0xFFFFFFFFLL,
               1,
               &v20,
               &v17);
        if ( v6 || v17 != 1 )
          break;
        VariantFromInstance = VdsWmiGetVariantFromInstance(v20, v7, 8u, &pvarg);
        if ( VariantFromInstance < 0 )
          goto LABEL_36;
        VariantFromInstance = CoCreateGuid(&pguid);
        if ( VariantFromInstance < 0 )
          goto LABEL_36;
        ATL::CComObject<CVdsIscsiInitiatorAdapterInternal>::CreateInstance((__int64 *)&v22);
        v0 = v22;
        if ( v22 )
        {
          (*(void (__fastcall **)(CVdsIscsiInitiatorAdapterInternal *))(*(_QWORD *)v22 + 8LL))(v22);
          VariantFromInstance = CVdsIscsiInitiatorAdapterInternal::Initialize(v0, &pguid, pvarg.bstrVal);
          if ( VariantFromInstance < 0
            || (VariantFromInstance = VdsWmiGetVariantFromInstance(v20, v8, 0x200Du, &v39), VariantFromInstance < 0)
            || (VariantFromInstance = CVdsWmiVariantObjectArrayEnum::Attach((CVdsWmiVariantObjectArrayEnum *)v36, &v39),
                VariantFromInstance < 0) )
          {
LABEL_36:
            CVdsWmiVariantObjectArrayEnum::Detach((CVdsWmiVariantObjectArrayEnum *)v36);
            if ( VariantFromInstance >= 0
              && (**(int (__fastcall ***)(CVdsIscsiInitiatorAdapterInternal *, GUID *, void **))v0)(
                   v0,
                   &IID_IUnknown,
                   &v21) >= 0 )
            {
              EnterCriticalSection(&g_GlobalCriticalSection);
              CRtlList::InsertTailPointer((CRtlList *)CVdsService::m_lstIscsiInitiatorAdapters, v21);
              v21 = 0;
              LeaveCriticalSection(&g_GlobalCriticalSection);
            }
            goto LABEL_39;
          }
          do
          {
LABEL_16:
            ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v16);
            v10 = CVdsWmiVariantObjectArrayEnum::Next((CVdsWmiVariantObjectArrayEnum *)v36, &v16);
            VariantFromInstance = v10;
            if ( v10 >= 0 && v10 != 1 )
            {
              VariantFromInstance = VdsWmiGetByteFromInstance(v16, v3, v14);
              if ( VariantFromInstance >= 0 )
                continue;
            }
            goto LABEL_36;
          }
          while ( v14[0] );
          VariantFromInstance = VdsWmiGetUlongFromInstance(v16, v4, &v19);
          if ( VariantFromInstance < 0 )
            goto LABEL_36;
          ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v15);
          VariantFromInstance = VdsWmiGetObjectFromInstance(v16, v27, &v15);
          if ( VariantFromInstance < 0 )
            goto LABEL_36;
          memset_0(&v43, 0, sizeof(v43));
          VariantFromInstance = VdsWmiGetUlongFromInstance(v15, v28, &v18);
          if ( VariantFromInstance < 0 )
            goto LABEL_36;
          v43.type = v18;
          if ( v18 )
          {
            switch ( v18 )
            {
              case VDS_IPT_IPV4:
                VariantFromInstance = VdsWmiGetUlongFromInstance(v15, v5, &v43.ipv4Address);
                break;
              case VDS_IPT_IPV6:
                VariantFromInstance = VdsWmiCopyFromVariantByteArray(v15, v29, 16, v43.ipv6Address);
                if ( VariantFromInstance < 0 )
                  goto LABEL_36;
                VariantFromInstance = VdsWmiGetUlongFromInstance(v15, v30, &v43.ulIpv6FlowInfo);
                if ( VariantFromInstance < 0 )
                  goto LABEL_36;
                VariantFromInstance = VdsWmiGetUlongFromInstance(v15, v31, &v43.ulIpv6ScopeId);
                break;
              case VDS_IPT_EMPTY:
                goto LABEL_34;
              default:
                VdsTraceW(0, L"CVdsService::LoadIscsiInitiator: Invalid IP address retrieved.");
                goto LABEL_12;
            }
          }
          else
          {
            VariantFromInstance = VdsWmiGetVariantFromInstance(v15, v32, 8u, &v35);
            v11 = SysStringLen(v35.bstrVal);
            StringCchCopyNW(v43.wszTextAddress, 0x101u, v35.bstrVal, v11 + 1);
            VariantClear(&v35);
          }
          if ( VariantFromInstance < 0 )
            goto LABEL_36;
LABEL_34:
          VariantFromInstance = VdsWmiGetUlongFromInstance(v16, v33, &v43.ulPort);
          if ( VariantFromInstance < 0 )
            goto LABEL_36;
          VariantFromInstance = CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal(v0, v19, &v43);
          if ( VariantFromInstance < 0 )
            goto LABEL_36;
          goto LABEL_16;
        }
        VdsTraceW(
          0,
          L"CVdsService::LoadIscsiInitiator: CVdsIscsiInitiatorAdapterInternal CreateInstance: Out of memory.");
LABEL_12:
        CVdsWmiVariantObjectArrayEnum::Detach((CVdsWmiVariantObjectArrayEnum *)v36);
LABEL_39:
        VariantClear(&v39);
        VariantClear(&pvarg);
        ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v21);
        v12 = v0;
        if ( v0 )
        {
          v0 = 0;
          v22 = 0;
          (*(void (__fastcall **)(CVdsIscsiInitiatorAdapterInternal *))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      v1 = v37;
      v2 = v38;
    }
  }
  SysFreeString(v1);
  SysFreeString(v2);
  SysFreeString(bstrString);
  SysFreeString(v26);
  SysFreeString(v3);
  SysFreeString(v4);
  SysFreeString(v27);
  SysFreeString(v28);
  SysFreeString(v5);
  SysFreeString(v29);
  SysFreeString(v30);
  SysFreeString(v31);
  SysFreeString(v32);
  SysFreeString(v33);
  CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v36);
  if ( v15 )
    ((void (__fastcall *)(struct IWbemClassObject *))v15->lpVtbl->Release)(v15);
  if ( v16 )
    ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
  if ( v20 )
    ((void (__fastcall *)(struct IWbemClassObject *))v20->lpVtbl->Release)(v20);
  if ( v23 )
    ((void (__fastcall *)(struct IEnumWbemClassObject *))v23->lpVtbl->Release)(v23);
  if ( v24 )
    ((void (__fastcall *)(struct IWbemServices *))v24->lpVtbl->Release)(v24);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v41);
  if ( v21 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000ae70  push    rbp
0x14000ae72  push    rbx
0x14000ae73  push    rsi
0x14000ae74  push    rdi
0x14000ae75  push    r12
0x14000ae77  push    r13
0x14000ae79  push    r14
0x14000ae7b  push    r15
0x14000ae7d  lea     rbp, [rsp-2A8h]
0x14000ae85  sub     rsp, 3A8h
0x14000ae8c  mov     rax, cs:__security_cookie
0x14000ae93  xor     rax, rsp
0x14000ae96  mov     [rbp+2E0h+var_48], rax
0x14000ae9d  xor     edi, edi
0x14000ae9f  mov     [rsp+3E0h+var_398], edi
0x14000aea3  mov     [rsp+3E0h+var_3B0], dil
0x14000aea8  mov     [rsp+3E0h+var_390], edi
0x14000aeac  mov     [rsp+3E0h+var_394], edi
0x14000aeb0  xor     edx, edx; Val
0x14000aeb2  mov     r8d, 228h; Size
0x14000aeb8  lea     rcx, [rbp+2E0h+var_280]; void *
0x14000aebc  call    memset_0
0x14000aec1  xorps   xmm0, xmm0
0x14000aec4  movups  xmmword ptr [rbp+2E0h+pguid.Data1], xmm0
0x14000aec8  mov     ebx, edi
0x14000aeca  mov     [rsp+3E0h+var_378], rbx
0x14000aecf  mov     [rsp+3E0h+var_380], rdi
0x14000aed4  lea     r8, aCvdsserviceLoa_3; "CVdsService::LoadIscsiInitiator()"
0x14000aedb  mov     edx, 5Eh ; '^'
0x14000aee0  lea     rcx, [rbp+2E0h+var_2A0]
0x14000aee4  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000aeea  nop
0x14000aeeb  cmp     cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * CVdsService::m_hIscsidscModule
0x14000aef2  jnz     short loc_14000AF08
0x14000aef4  lea     rcx, aIscsidscDll; "iscsidsc.dll"
0x14000aefb  call    cs:__imp_LoadLibraryW
0x14000af01  mov     cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CVdsService::m_hIscsidscModule
0x14000af08  mov     [rbp+2E0h+var_318], rdi
0x14000af0c  mov     [rsp+3E0h+var_368], rdi
0x14000af11  mov     [rsp+3E0h+var_370], rdi
0x14000af16  mov     [rsp+3E0h+var_388], rdi
0x14000af1b  mov     [rsp+3E0h+var_3A0], rdi
0x14000af20  mov     [rsp+3E0h+var_3A8], rdi
0x14000af25  lea     rcx, Source; "root\\wmi"
0x14000af2c  call    cs:__imp_SysAllocString
0x14000af32  mov     rsi, rax
0x14000af35  mov     [rbp+2E0h+var_2E0], rax
0x14000af39  lea     rcx, aMsiscsiPortali; "MSiSCSI_PortalInfoClass"
0x14000af40  call    cs:__imp_SysAllocString
0x14000af46  mov     r14, rax
0x14000af49  mov     [rbp+2E0h+var_2D8], rax
0x14000af4d  lea     rcx, aInstancename; "InstanceName"
0x14000af54  call    cs:__imp_SysAllocString
0x14000af5a  mov     [rbp+2E0h+bstrString], rax
0x14000af5e  lea     rcx, aPortalinformat; "PortalInformation"
0x14000af65  call    cs:__imp_SysAllocString
0x14000af6b  mov     [rbp+2E0h+var_358], rax
0x14000af6f  lea     rcx, aPortaltype; "PortalType"
0x14000af76  call    cs:__imp_SysAllocString
0x14000af7c  mov     r15, rax
0x14000af7f  lea     rcx, aIndex; "Index"
0x14000af86  call    cs:__imp_SysAllocString
0x14000af8c  mov     r12, rax
0x14000af8f  lea     rcx, aIpaddr; "IPAddr"
0x14000af96  call    cs:__imp_SysAllocString
0x14000af9c  mov     [rbp+2E0h+var_350], rax
0x14000afa0  lea     rcx, aType; "Type"
0x14000afa7  call    cs:__imp_SysAllocString
0x14000afad  mov     [rbp+2E0h+var_348], rax
0x14000afb1  lea     rcx, aIpv4address; "IpV4Address"
0x14000afb8  call    cs:__imp_SysAllocString
0x14000afbe  mov     r13, rax
0x14000afc1  lea     rcx, aIpv6address; "IpV6Address"
0x14000afc8  call    cs:__imp_SysAllocString
0x14000afce  mov     [rbp+2E0h+var_340], rax
0x14000afd2  lea     rcx, aIpv6flowinfo; "IpV6FlowInfo"
0x14000afd9  call    cs:__imp_SysAllocString
0x14000afdf  mov     [rbp+2E0h+var_338], rax
0x14000afe3  lea     rcx, aIpv6scopeid; "IpV6ScopeId"
0x14000afea  call    cs:__imp_SysAllocString
0x14000aff0  mov     [rbp+2E0h+var_330], rax
0x14000aff4  lea     rcx, aTextaddress; "TextAddress"
0x14000affb  call    cs:__imp_SysAllocString
0x14000b001  mov     [rbp+2E0h+var_328], rax
0x14000b005  lea     rcx, aPort; "Port"
0x14000b00c  call    cs:__imp_SysAllocString
0x14000b012  mov     [rbp+2E0h+var_320], rax
0x14000b016  xorps   xmm0, xmm0
0x14000b019  xor     eax, eax
0x14000b01b  movups  xmmword ptr [rbp+2E0h+pvarg], xmm0
0x14000b01f  mov     qword ptr [rbp+2E0h+pvarg+10h], rax
0x14000b023  xorps   xmm1, xmm1
0x14000b026  movups  xmmword ptr [rbp+2E0h+var_2D0], xmm1
0x14000b02a  mov     qword ptr [rbp+2E0h+var_2D0+10h], rax
0x14000b02e  movups  xmmword ptr [rbp+2E0h+var_310], xmm0
0x14000b032  mov     qword ptr [rbp+2E0h+var_310+10h], rax
0x14000b036  lea     rcx, [rbp+2E0h+var_2F8]
0x14000b03a  call    cs:__imp_??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum(void)
0x14000b040  nop
0x14000b041  lea     rcx, [rbp+2E0h+pvarg]; pvarg
0x14000b045  call    cs:__imp_VariantInit
0x14000b04b  lea     rcx, [rbp+2E0h+var_2D0]; pvarg
0x14000b04f  call    cs:__imp_VariantInit
0x14000b055  lea     rcx, [rbp+2E0h+var_310]; pvarg
0x14000b059  call    cs:__imp_VariantInit
0x14000b05f  lea     r8, [rsp+3E0h+var_368]
0x14000b064  lea     rdx, [rbp+2E0h+var_318]
0x14000b068  mov     rcx, rsi
0x14000b06b  call    cs:__imp_VdsWmiConnectToNamespace
0x14000b071  mov     edi, eax
0x14000b073  test    eax, eax
0x14000b075  js      loc_14000B43E
0x14000b07b  lea     r8, [rsp+3E0h+var_370]; struct IEnumWbemClassObject **
0x14000b080  mov     rdx, r14; unsigned __int16 *
0x14000b083  mov     rcx, [rsp+3E0h+var_368]; struct IWbemServices *
0x14000b088  call    ?VdsWmiCreateInstanceEnum@@YAJPEAUIWbemServices@@PEAGPEAPEAUIEnumWbemClassObject@@@Z; VdsWmiCreateInstanceEnum(IWbemServices *,ushort *,IEnumWbemClassObject * *)
0x14000b08d  mov     edi, eax
0x14000b08f  test    eax, eax
0x14000b091  js      loc_14000B43E
0x14000b097  mov     rsi, [rbp+2E0h+bstrString]
0x14000b09b  mov     r14, [rbp+2E0h+var_358]
0x14000b09f  lea     rcx, [rsp+3E0h+var_388]
0x14000b0a4  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14000b0a9  mov     rcx, [rsp+3E0h+var_370]
0x14000b0ae  mov     rax, [rcx]
0x14000b0b1  lea     rdx, [rsp+3E0h+var_398]
0x14000b0b6  mov     [rsp+3E0h+var_3C0], rdx
0x14000b0bb  lea     r9, [rsp+3E0h+var_388]
0x14000b0c0  mov     edx, 0FFFFFFFFh
0x14000b0c5  mov     r8d, 1
0x14000b0cb  mov     rax, [rax+20h]
0x14000b0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0d4  mov     edi, eax
0x14000b0d6  test    eax, eax
0x14000b0d8  jnz     loc_14000B436
0x14000b0de  cmp     [rsp+3E0h+var_398], 1
0x14000b0e3  jnz     loc_14000B436
0x14000b0e9  mov     r8d, 8; unsigned __int16
0x14000b0ef  lea     r9, [rbp+2E0h+pvarg]; struct tagVARIANT *
0x14000b0f3  mov     rdx, rsi; unsigned __int16 *
0x14000b0f6  mov     rcx, [rsp+3E0h+var_388]; struct IWbemClassObject *
0x14000b0fb  call    ?VdsWmiGetVariantFromInstance@@YAJPEAUIWbemClassObject@@PEAGGPEAUtagVARIANT@@@Z; VdsWmiGetVariantFromInstance(IWbemClassObject *,ushort *,ushort,tagVARIANT *)
0x14000b100  mov     edi, eax
0x14000b102  test    eax, eax
0x14000b104  js      loc_14000B392
0x14000b10a  lea     rcx, [rbp+2E0h+pguid]; pguid
0x14000b10e  call    cs:__imp_CoCreateGuid
0x14000b114  mov     edi, eax
0x14000b116  test    eax, eax
0x14000b118  js      loc_14000B392
0x14000b11e  lea     rcx, [rsp+3E0h+var_378]
0x14000b123  call    ?CreateInstance@?$CComObject@VCVdsIscsiInitiatorAdapterInternal@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CVdsIscsiInitiatorAdapterInternal>::CreateInstance(ATL::CComObject<CVdsIscsiInitiatorAdapterInternal> * *)
0x14000b128  mov     rbx, [rsp+3E0h+var_378]
0x14000b12d  test    rbx, rbx
0x14000b130  jnz     short loc_14000B150
0x14000b132  lea     rdx, aCvdsserviceLoa_18; "CVdsService::LoadIscsiInitiator: CVdsIs"...
0x14000b139  xor     ecx, ecx
0x14000b13b  call    cs:__imp_VdsTraceW
0x14000b141  lea     rcx, [rbp+2E0h+var_2F8]
0x14000b145  call    cs:__imp_?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ; CVdsWmiVariantObjectArrayEnum::Detach(void)
0x14000b14b  jmp     loc_14000B3F4
0x14000b150  mov     rax, [rbx]
0x14000b153  mov     rcx, rbx
0x14000b156  mov     rax, [rax+8]
0x14000b15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b15f  mov     r8, qword ptr [rbp+2E0h+pvarg+8]; unsigned __int16 *
0x14000b163  lea     rdx, [rbp+2E0h+pguid]; struct _GUID *
0x14000b167  mov     rcx, rbx; this
0x14000b16a  call    ?Initialize@CVdsIscsiInitiatorAdapterInternal@@QEAAJPEBU_GUID@@PEAG@Z; CVdsIscsiInitiatorAdapterInternal::Initialize(_GUID const *,ushort *)
0x14000b16f  mov     edi, eax
0x14000b171  test    eax, eax
0x14000b173  js      loc_14000B392
0x14000b179  mov     r8d, 200Dh; unsigned __int16
0x14000b17f  lea     r9, [rbp+2E0h+var_2D0]; struct tagVARIANT *
0x14000b183  mov     rdx, r14; unsigned __int16 *
0x14000b186  mov     rcx, [rsp+3E0h+var_388]; struct IWbemClassObject *
0x14000b18b  call    ?VdsWmiGetVariantFromInstance@@YAJPEAUIWbemClassObject@@PEAGGPEAUtagVARIANT@@@Z; VdsWmiGetVariantFromInstance(IWbemClassObject *,ushort *,ushort,tagVARIANT *)
0x14000b190  mov     edi, eax
0x14000b192  test    eax, eax
0x14000b194  js      loc_14000B392
0x14000b19a  lea     rdx, [rbp+2E0h+var_2D0]
0x14000b19e  lea     rcx, [rbp+2E0h+var_2F8]
0x14000b1a2  call    cs:__imp_?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z; CVdsWmiVariantObjectArrayEnum::Attach(tagVARIANT *)
0x14000b1a8  mov     edi, eax
0x14000b1aa  test    eax, eax
0x14000b1ac  js      loc_14000B392
0x14000b1b2  lea     rcx, [rsp+3E0h+var_3A0]
0x14000b1b7  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14000b1bc  lea     rdx, [rsp+3E0h+var_3A0]
0x14000b1c1  lea     rcx, [rbp+2E0h+var_2F8]
0x14000b1c5  call    cs:__imp_?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z; CVdsWmiVariantObjectArrayEnum::Next(IWbemClassObject * *)
0x14000b1cb  mov     edi, eax
0x14000b1cd  test    eax, eax
0x14000b1cf  js      loc_14000B392
0x14000b1d5  cmp     eax, 1
0x14000b1d8  jz      loc_14000B392
0x14000b1de  lea     r8, [rsp+3E0h+var_3B0]
0x14000b1e3  mov     rdx, r15
0x14000b1e6  mov     rcx, [rsp+3E0h+var_3A0]
0x14000b1eb  call    cs:__imp_VdsWmiGetByteFromInstance
0x14000b1f1  mov     edi, eax
0x14000b1f3  test    eax, eax
0x14000b1f5  js      loc_14000B392
0x14000b1fb  cmp     [rsp+3E0h+var_3B0], 0
0x14000b200  jnz     short loc_14000B1B2
0x14000b202  lea     r8, [rsp+3E0h+var_390]
0x14000b207  mov     rdx, r12
0x14000b20a  mov     rcx, [rsp+3E0h+var_3A0]
0x14000b20f  call    cs:__imp_VdsWmiGetUlongFromInstance
0x14000b215  mov     edi, eax
0x14000b217  test    eax, eax
0x14000b219  js      loc_14000B392
0x14000b21f  lea     rcx, [rsp+3E0h+var_3A8]
0x14000b224  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14000b229  lea     r8, [rsp+3E0h+var_3A8]
0x14000b22e  mov     rdx, [rbp+2E0h+var_350]
0x14000b232  mov     rcx, [rsp+3E0h+var_3A0]
0x14000b237  call    cs:__imp_VdsWmiGetObjectFromInstance
0x14000b23d  mov     edi, eax
0x14000b23f  test    eax, eax
0x14000b241  js      loc_14000B392
0x14000b247  xor     edx, edx; Val
0x14000b249  mov     r8d, 228h; Size
0x14000b24f  lea     rcx, [rbp+2E0h+var_280]; void *
0x14000b253  call    memset_0
0x14000b258  lea     r8, [rsp+3E0h+var_394]
0x14000b25d  mov     rdx, [rbp+2E0h+var_348]
0x14000b261  mov     rcx, [rsp+3E0h+var_3A8]
0x14000b266  call    cs:__imp_VdsWmiGetUlongFromInstance
0x14000b26c  mov     edi, eax
0x14000b26e  test    eax, eax
0x14000b270  js      loc_14000B392
0x14000b276  mov     ecx, [rsp+3E0h+var_394]
0x14000b27a  mov     [rbp+2E0h+var_280.type], ecx
0x14000b27d  test    ecx, ecx
0x14000b27f  jz      loc_14000B311
0x14000b285  sub     ecx, 1
0x14000b288  jz      short loc_14000B2FB
0x14000b28a  sub     ecx, 1
0x14000b28d  jz      short loc_14000B2A4
0x14000b28f  cmp     ecx, 1
0x14000b292  jz      loc_14000B35C
0x14000b298  lea     rdx, aCvdsserviceLoa_11; "CVdsService::LoadIscsiInitiator: Invali"...
0x14000b29f  jmp     loc_14000B139
0x14000b2a4  lea     r9, [rbp+2E0h+var_280.ipv6Address]
0x14000b2a8  mov     r8d, 10h
0x14000b2ae  mov     rdx, [rbp+2E0h+var_340]
0x14000b2b2  mov     rcx, [rsp+3E0h+var_3A8]
0x14000b2b7  call    cs:__imp_VdsWmiCopyFromVariantByteArray
0x14000b2bd  mov     edi, eax
0x14000b2bf  test    eax, eax
0x14000b2c1  js      loc_14000B392
0x14000b2c7  lea     r8, [rbp+2E0h+var_280.ulIpv6FlowInfo]
0x14000b2cb  mov     rdx, [rbp+2E0h+var_338]
0x14000b2cf  mov     rcx, [rsp+3E0h+var_3A8]
0x14000b2d4  call    cs:__imp_VdsWmiGetUlongFromInstance
0x14000b2da  mov     edi, eax
0x14000b2dc  test    eax, eax
0x14000b2de  js      loc_14000B392
0x14000b2e4  lea     r8, [rbp+2E0h+var_280.ulIpv6ScopeId]
0x14000b2e8  mov     rdx, [rbp+2E0h+var_330]
0x14000b2ec  mov     rcx, [rsp+3E0h+var_3A8]
0x14000b2f1  call    cs:__imp_VdsWmiGetUlongFromInstance
0x14000b2f7  mov     edi, eax
0x14000b2f9  jmp     short loc_14000B358
0x14000b2fb  lea     r8, [rbp+2E0h+var_280.ipv4Address]
0x14000b2ff  mov     rdx, r13
0x14000b302  mov     rcx, [rsp+3E0h+var_3A8]
0x14000b307  call    cs:__imp_VdsWmiGetUlongFromInstance
0x14000b30d  mov     edi, eax
0x14000b30f  jmp     short loc_14000B358
0x14000b311  mov     r8d, 8; unsigned __int16
0x14000b317  lea     r9, [rbp+2E0h+var_310]; struct tagVARIANT *
0x14000b31b  mov     rdx, [rbp+2E0h+var_328]; unsigned __int16 *
0x14000b31f  mov     rcx, [rsp+3E0h+var_3A8]; struct IWbemClassObject *
0x14000b324  call    ?VdsWmiGetVariantFromInstance@@YAJPEAUIWbemClassObject@@PEAGGPEAUtagVARIANT@@@Z; VdsWmiGetVariantFromInstance(IWbemClassObject *,ushort *,ushort,tagVARIANT *)
0x14000b329  mov     edi, eax
0x14000b32b  mov     rcx, qword ptr [rbp+2E0h+var_310+8]; pbstr
0x14000b32f  call    cs:__imp_SysStringLen
0x14000b335  lea     r9d, [rax+1]; unsigned __int64
0x14000b339  mov     r8, qword ptr [rbp+2E0h+var_310+8]; unsigned __int16 *
0x14000b33d  mov     edx, 101h; unsigned __int64
0x14000b342  lea     rcx, [rbp+2E0h+var_280.wszTextAddress]; unsigned __int16 *
0x14000b349  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000b34e  lea     rcx, [rbp+2E0h+var_310]; pvarg
0x14000b352  call    cs:__imp_VariantClear
0x14000b358  test    edi, edi
0x14000b35a  js      short loc_14000B392
0x14000b35c  lea     r8, [rbp+2E0h+var_280.ulPort]
0x14000b363  mov     rdx, [rbp+2E0h+var_320]
0x14000b367  mov     rcx, [rsp+3E0h+var_3A0]
0x14000b36c  call    cs:__imp_VdsWmiGetUlongFromInstance
0x14000b372  mov     edi, eax
0x14000b374  test    eax, eax
0x14000b376  js      short loc_14000B392
0x14000b378  lea     r8, [rbp+2E0h+var_280]; struct _VDS_IPADDRESS *
0x14000b37c  mov     edx, [rsp+3E0h+var_390]; unsigned int
0x14000b380  mov     rcx, rbx; this
0x14000b383  call    ?AddInitiatorPortal@CVdsIscsiInitiatorAdapterInternal@@QEAAJKPEBU_VDS_IPADDRESS@@@Z; CVdsIscsiInitiatorAdapterInternal::AddInitiatorPortal(ulong,_VDS_IPADDRESS const *)
0x14000b388  mov     edi, eax
  ... truncated ...
```
