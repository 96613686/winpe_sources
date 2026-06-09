# CWMCService::RegisterServer(CMediaServer *,IWMCContentProvider *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,_EVENT_DESCRIPTOR &)

- ea: `0x140050ab0`
- end: `0x140051731`
- name: `?RegisterServer@CWMCService@@AEAAJPEAVCMediaServer@@PEAUIWMCContentProvider@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@2AEAU_EVENT_DESCRIPTOR@@@Z`
- size: `3201`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14004c0f4`
- `0x1400519ec`

## callees

- `0x140003750`
- `0x140006d70`
- `0x140007020`
- `0x140008eac`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c920`
- `0x14000e660`
- `0x140023bdc`
- `0x140024688`
- `0x140027660`
- `0x14002dd84`
- `0x14002eb14`
- `0x140032eec`
- `0x14003e4e0`
- `0x14003e5f4`
- `0x14003f17c`
- `0x14003fad8`
- `0x1400476ac`
- `0x14004dce0`
- `0x14004f2e0`
- `0x140050878`
- `0x140050ab0`
- `0x140054148`
- `0x140054490`
- `0x140062504`
- `0x14009e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400515ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1400515f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400515fe`
- `OLEAUT32!__imp_SysFreeString` at `0x140051608`
- `OLEAUT32!__imp_SysFreeString` at `0x1400515ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1400515f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400515fe`
- `OLEAUT32!__imp_SysFreeString` at `0x140051608`
- `ole32!CoCreateInstance` at `0x140050baa`
- `ole32!CoCreateInstance` at `0x140050baa`

## string_xrefs

- `0x14005105a`: `<dlna:X_DLNADOC xmlns:dlna="urn:schemas-dlna-org:device-1-0">DMS-1.50</dlna:X_DLNADOC>\n`
- `0x1400510d5`: `<microsoft:magicPacketWakeSupported xmlns:microsoft="urn:schemas-microsoft-com:WMPNSS-1-0">1</microsoft:magicPacketWakeSupported>\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CWMCService::RegisterServer(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3,
        const unsigned __int16 **a4,
        __int64 *a5,
        unsigned __int16 *a6)
{
  unsigned __int16 *v9; // r15
  __int64 *v10; // rsi
  int updated; // r14d
  __int64 (__fastcall *v12)(__int64, __int64, __int64); // rbx
  __int64 BufferSetLength; // rax
  __int64 (__fastcall *v14)(__int64, __int64, __int64); // rbx
  __int64 v15; // rax
  unsigned int v16; // ebx
  unsigned int v17; // edx
  int StringValue; // eax
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  PVOID v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  int ModulePath; // eax
  OLECHAR *v25; // rbx
  OLECHAR *v26; // rdi
  OLECHAR *v27; // rsi
  PVOID *v28; // rcx
  int v29; // r14d
  __int64 v30; // rcx
  __int64 v32; // [rsp+40h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-61h] BYREF
  __int64 v34; // [rsp+50h] [rbp-59h] BYREF
  __int64 v35; // [rsp+58h] [rbp-51h] BYREF
  __int64 v36; // [rsp+60h] [rbp-49h] BYREF
  __int64 v37; // [rsp+68h] [rbp-41h] BYREF
  __int64 v38; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 *v39; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int16 *v40; // [rsp+80h] [rbp-29h] BYREF
  __int64 v41; // [rsp+88h] [rbp-21h] BYREF
  BSTR v42; // [rsp+90h] [rbp-19h] BYREF
  BSTR v43; // [rsp+98h] [rbp-11h] BYREF
  BSTR v44; // [rsp+A0h] [rbp-9h] BYREF
  _QWORD v45[9]; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v46; // [rsp+100h] [rbp+57h] BYREF
  BSTR bstrString; // [rsp+108h] [rbp+5Fh] BYREF

  v46 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, a2, a3);
  }
  ppv = 0;
  v38 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v32);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v46);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v37);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v36);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v41);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v35);
  v9 = a6;
  *(_OWORD *)a6 = *(_OWORD *)WMC_E_SERVICE_FAILED_CRSERVER_UNEXPECTED;
  v10 = a5;
  if ( a2 && a3 )
  {
    updated = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 0x17u, &GUID_204810b6_73b2_11d4_bf42_00b0d0118b56, &ppv);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        203,
        &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
        (unsigned int)updated);
    }
    *(_OWORD *)v9 = WMC_E_SERVICE_FAILED_CRSERVER_CREATE_UPNPREGISTRAR;
    if ( updated >= 0 )
    {
      updated = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                  ppv,
                  &GUID_204810b7_73b2_11d4_bf42_00b0d0118b56,
                  &v38);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          204,
          &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
          (unsigned int)updated);
      }
      *(_OWORD *)v9 = WMC_E_SERVICE_FAILED_CRSERVER_QI_UPNPREGISTRAR;
      if ( updated >= 0 )
      {
        v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a3 + 80LL);
        BufferSetLength = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(v10, 64);
        updated = v12(a3, 63, BufferSetLength);
        if ( updated < 0 )
        {
          ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v10, 0);
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v10, 0xFFFFFFFFLL);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
            v10,
            60,
            95);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
            v10,
            62,
            95);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
            v10,
            38,
            95);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            205,
            (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
            updated,
            *v10);
        }
        *(_OWORD *)v9 = WMC_E_SERVICE_FAILED_CRSERVER_GETFRIENDLYNAME;
        if ( updated >= 0 )
        {
          v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a3 + 88LL);
          v15 = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(&v32, 64);
          updated = v14(a3, 63, v15);
          ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v32, ((updated >> 31) & 1u) - 1);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              206,
              (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
              updated,
              v32);
          }
          *(_OWORD *)v9 = WMC_E_SERVICE_FAILED_CRSERVER_GETSERIALNUMBER;
          if ( updated >= 0 )
          {
            memset(v45, 0, 24);
            v16 = ATL::CRegKey::Open(
                    (ATL::CRegKey *)v45,
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0",
                    0x2011Fu);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v17 = 5;
              if ( v16 )
                v17 = 2;
              if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v17 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  207,
                  &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                  v16);
            }
            if ( !v16 )
            {
              StringValue = GetStringValue((ATL::CRegKey *)v45, L"ModelName");
              updated = StringValue;
              if ( StringValue > 0 )
                updated = (unsigned __int16)StringValue | 0x80070000;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
              {
                WPP_SF_dS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  208,
                  (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                  updated,
                  v46);
              }
              if ( updated >= 0 )
              {
                v19 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                                  &v46,
                                  &a6,
                                  31);
                ATL::CSimpleStringT<unsigned short,0>::operator=(&v46, v19);
                ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&a6);
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
                  &v46,
                  60,
                  95);
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
                  &v46,
                  62,
                  95);
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
                  &v46,
                  38,
                  95);
              }
            }
            if ( !*(_DWORD *)(v46 - 16) )
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::LoadStringW(
                &v46,
                203);
            if ( *(_DWORD *)(v46 - 16) )
              updated = 0;
            v20 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                              &v46,
                              &a6,
                              31);
            ATL::CSimpleStringT<unsigned short,0>::operator=(&v46, v20);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&a6);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
            {
              WPP_SF_dS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                209,
                (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                updated,
                v46);
            }
            *(_OWORD *)v9 = WMC_E_SERVICE_FAILED_CRSERVER_GETMODELNAME;
            ATL::CRegKey::Close((ATL::CRegKey *)v45);
            if ( updated >= 0 )
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v37, L"12.0");
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
              {
                WPP_SF_dS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  210,
                  (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                  updated,
                  v37);
              }
              ATL::CSimpleStringT<unsigned short,0>::SetString(
                &v36,
                L"<dlna:X_DLNADOC xmlns:dlna=\"urn:schemas-dlna-org:device-1-0\">DMS-1.50</dlna:X_DLNADOC>\r\n");
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
              {
                WPP_SF_dS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  211,
                  (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                  updated,
                  v36);
              }
              if ( !*((_DWORD *)*a4 - 4) )
                CWMCService::ReadPersistedServerUPnPID(v21, &v32, a4);
              if ( (unsigned int)IsWakeOnLANEnabled() )
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(
                  &v35,
                  L"<microsoft:magicPacketWakeSupported xmlns:microsoft=\"urn:schemas-microsoft-com:WMPNSS-1-0\">1</micros"
                   "oft:magicPacketWakeSupported>\r\n");
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
                {
                  WPP_SF_dS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    212,
                    (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                    updated,
                    v35);
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    updated = -2147467261;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&a6);
  if ( updated >= 0 )
  {
    v23 = GenerateStringFromResourceData(v22, &a6);
    updated = v23;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v23 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        213,
        &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
        (unsigned int)v23);
    }
    *(_OWORD *)v9 = WMC_E_SERVICE_FAILED_CRSERVER_GENERATE_DEVICEDOC;
    if ( updated >= 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
        &a6,
        L"%FRIENDLYNAME%",
        *v10);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
        &a6,
        L"%SERIALNUMBER%",
        v32);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
        &a6,
        L"%MODELNAME%",
        v46);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
        &a6,
        L"%MODELNUMBER%",
        v37);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
        &a6,
        L"%DLNAELEMENT%",
        v36);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
        &a6,
        L"%REMOTEELEMENT%",
        v41);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
        &a6,
        L"%MAGICPACKETELEMENT%",
        v35);
    }
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v39);
  if ( updated >= 0 )
  {
    ModulePath = GetModulePath(&v39);
    updated = ModulePath;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ModulePath >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        214,
        &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
        (unsigned int)ModulePath);
    }
    *(_OWORD *)v9 = *(_OWORD *)WMC_E_SERVICE_FAILED_CRSERVER_UNEXPECTED;
  }
  v34 = 0;
  if ( updated >= 0 )
  {
    updated = (**a2)(a2, &GUID_00000000_0000_0000_c000_000000000046, &v34);
    *(_OWORD *)v9 = *(_OWORD *)WMC_E_SERVICE_FAILED_CRSERVER_UNEXPECTED;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&v40,
    (char *)L"Not Sure What should go here or if we even need it.");
  if ( updated >= 0 )
  {
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v42, a6);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v43, v39);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v44, v40);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, *a4);
    v25 = v42;
    v26 = v43;
    v27 = v44;
    if ( *((_DWORD *)*a4 - 4) )
    {
      updated = (*(__int64 (__fastcall **)(__int64, BSTR, BSTR, __int64, BSTR, BSTR, int))(*(_QWORD *)v38 + 32LL))(
                  v38,
                  bstrString,
                  v42,
                  v34,
                  v44,
                  v43,
                  900);
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          215,
          &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
          (unsigned int)updated);
        v28 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( updated == -2147180495 )
      {
        v29 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, bstrString, 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v29 >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            216,
            &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
            (unsigned int)v29);
        }
        if ( v29 < 0 )
          goto LABEL_102;
        updated = (*(__int64 (__fastcall **)(__int64, BSTR, OLECHAR *, __int64, OLECHAR *, OLECHAR *, int))(*(_QWORD *)v38 + 32LL))(
                    v38,
                    bstrString,
                    v25,
                    v34,
                    v27,
                    v26,
                    900);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            217,
            &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
            (unsigned int)updated);
        }
      }
      else if ( updated == -2147180494 )
      {
        if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 2) != 0 && *((_BYTE *)v28 + 25) >= 4u )
          WPP_SF_S(v28[2], 218, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, *a4);
        ATL::CSimpleStringT<unsigned short,0>::Empty(a4);
        updated = 0;
        goto LABEL_107;
      }
      if ( updated < 0 )
      {
LABEL_102:
        updated = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64))(*(_QWORD *)ppv + 56LL))(ppv, bstrString, 1);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            219,
            &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
            (unsigned int)updated);
        }
        ATL::CSimpleStringT<unsigned short,0>::Empty(a4);
      }
    }
LABEL_107:
    if ( !*((_DWORD *)*a4 - 4) )
    {
      updated = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64, OLECHAR *, OLECHAR *, int, BSTR *))(*(_QWORD *)ppv + 32LL))(
                  ppv,
                  v25,
                  v34,
                  v27,
                  v26,
                  900,
                  &bstrString);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          220,
          &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
          (unsigned int)updated);
      }
      *(_OWORD *)v9 = WMC_E_SERVICE_FAILED_CRSERVER_REGISTERRUNNINGDEVICE;
      if ( updated >= 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a4, bstrString);
        updated = CWMCService::UpdateServerUPnPDeviceID(v30, &v32, a4);
        *(_OWORD *)v9 = WMC_E_SERVICE_FAILED_CRSERVER_WRITEREGISTRY;
      }
    }
    SysFreeString(bstrString);
    SysFreeString(v27);
    SysFreeString(v26);
    SysFreeString(v25);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((updated >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      221,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      (unsigned int)updated);
  }
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v39);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&a6);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v35);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v41);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v36);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v37);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v46);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140050ab0  mov     [rsp-8+arg_10], rbx
0x140050ab5  mov     [rsp-8+arg_0], rcx
0x140050aba  push    rbp
0x140050abb  push    rsi
0x140050abc  push    rdi
0x140050abd  push    r12
0x140050abf  push    r13
0x140050ac1  push    r14
0x140050ac3  push    r15
0x140050ac5  lea     rbp, [rsp-17h]
0x140050aca  sub     rsp, 0C0h
0x140050ad1  mov     r12, r9
0x140050ad4  mov     rdi, r8
0x140050ad7  mov     r13, rdx
0x140050ada  lea     rax, WPP_GLOBAL_Control
0x140050ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x140050ae8  cmp     rcx, rax
0x140050aeb  jz      short loc_140050B16
0x140050aed  test    byte ptr [rcx+1Ch], 1
0x140050af1  jz      short loc_140050B16
0x140050af3  cmp     byte ptr [rcx+19h], 5
0x140050af7  jb      short loc_140050B16
0x140050af9  mov     edx, 0CAh
0x140050afe  mov     [rsp+0F0h+ppv], r8
0x140050b03  mov     r9, r13
0x140050b06  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140050b0d  mov     rcx, [rcx+10h]
0x140050b11  call    WPP_SF_qq
0x140050b16  mov     [rbp+47h+var_A8], 0
0x140050b1e  mov     [rbp+47h+var_80], 0
0x140050b26  lea     rcx, [rbp+47h+var_B0]
0x140050b2a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140050b2f  nop
0x140050b30  lea     rcx, [rbp+47h+arg_0]
0x140050b34  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140050b39  nop
0x140050b3a  lea     rcx, [rbp+47h+var_88]
0x140050b3e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140050b43  nop
0x140050b44  lea     rcx, [rbp+47h+var_90]
0x140050b48  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140050b4d  nop
0x140050b4e  lea     rcx, [rbp+47h+var_68]
0x140050b52  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140050b57  nop
0x140050b58  lea     rcx, [rbp+47h+var_98]
0x140050b5c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140050b61  nop
0x140050b62  movups  xmm0, xmmword ptr cs:WMC_E_SERVICE_FAILED_CRSERVER_UNEXPECTED
0x140050b69  mov     r15, [rbp+47h+arg_28]
0x140050b6d  movdqu  xmmword ptr [r15], xmm0
0x140050b72  mov     rsi, [rbp+47h+arg_20]
0x140050b76  mov     ebx, 2
0x140050b7b  test    r13, r13
0x140050b7e  jz      loc_140051134
0x140050b84  test    rdi, rdi
0x140050b87  jz      loc_140051134
0x140050b8d  lea     rax, [rbp+47h+var_A8]
0x140050b91  mov     [rsp+0F0h+ppv], rax; ppv
0x140050b96  lea     r9, _GUID_204810b6_73b2_11d4_bf42_00b0d0118b56; riid
0x140050b9d  xor     edx, edx; pUnkOuter
0x140050b9f  lea     r8d, [rbx+15h]; dwClsContext
0x140050ba3  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x140050baa  call    cs:__imp_CoCreateInstance
0x140050bb0  mov     r14d, eax
0x140050bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140050bba  lea     rax, WPP_GLOBAL_Control
0x140050bc1  cmp     rcx, rax
0x140050bc4  jz      short loc_140050BF7
0x140050bc6  test    [rcx+1Ch], bl
0x140050bc9  jz      short loc_140050BF7
0x140050bcb  mov     edx, r14d
0x140050bce  sar     edx, 1Fh
0x140050bd1  and     edx, 0FFFFFFFDh
0x140050bd4  add     edx, 5
0x140050bd7  movzx   eax, byte ptr [rcx+19h]
0x140050bdb  cmp     eax, edx
0x140050bdd  jb      short loc_140050BF7
0x140050bdf  mov     edx, 0CBh
0x140050be4  mov     r9d, r14d
0x140050be7  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140050bee  mov     rcx, [rcx+10h]
0x140050bf2  call    WPP_SF_d
0x140050bf7  movups  xmm0, cs:WMC_E_SERVICE_FAILED_CRSERVER_CREATE_UPNPREGISTRAR
0x140050bfe  movdqu  xmmword ptr [r15], xmm0
0x140050c03  test    r14d, r14d
0x140050c06  js      loc_14005113A
0x140050c0c  mov     rcx, [rbp+47h+var_A8]
0x140050c10  mov     rax, [rcx]
0x140050c13  lea     r8, [rbp+47h+var_80]
0x140050c17  lea     rdx, _GUID_204810b7_73b2_11d4_bf42_00b0d0118b56
0x140050c1e  mov     rax, [rax]
0x140050c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050c26  mov     r14d, eax
0x140050c29  mov     rcx, cs:WPP_GLOBAL_Control
0x140050c30  lea     rax, WPP_GLOBAL_Control
0x140050c37  cmp     rcx, rax
0x140050c3a  jz      short loc_140050C6D
0x140050c3c  test    [rcx+1Ch], bl
0x140050c3f  jz      short loc_140050C6D
0x140050c41  mov     edx, r14d
0x140050c44  sar     edx, 1Fh
0x140050c47  and     edx, 0FFFFFFFDh
0x140050c4a  add     edx, 5
0x140050c4d  movzx   eax, byte ptr [rcx+19h]
0x140050c51  cmp     eax, edx
0x140050c53  jb      short loc_140050C6D
0x140050c55  mov     edx, 0CCh
0x140050c5a  mov     r9d, r14d
0x140050c5d  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140050c64  mov     rcx, [rcx+10h]
0x140050c68  call    WPP_SF_d
0x140050c6d  movups  xmm0, cs:WMC_E_SERVICE_FAILED_CRSERVER_QI_UPNPREGISTRAR
0x140050c74  movdqu  xmmword ptr [r15], xmm0
0x140050c79  test    r14d, r14d
0x140050c7c  js      loc_14005113A
0x140050c82  mov     rax, [rdi]
0x140050c85  mov     rbx, [rax+50h]
0x140050c89  mov     edx, 40h ; '@'
0x140050c8e  mov     rcx, rsi
0x140050c91  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x140050c96  mov     r8, rax
0x140050c99  mov     edx, 3Fh ; '?'
0x140050c9e  mov     rcx, rdi
0x140050ca1  mov     rax, rbx
0x140050ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050ca9  mov     r14d, eax
0x140050cac  mov     ebx, 5Fh ; '_'
0x140050cb1  mov     rcx, rsi
0x140050cb4  test    eax, eax
0x140050cb6  js      short loc_140050CEC
0x140050cb8  or      edx, 0FFFFFFFFh
0x140050cbb  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x140050cc0  mov     r8d, ebx
0x140050cc3  lea     edx, [rbx-23h]
0x140050cc6  mov     rcx, rsi
0x140050cc9  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort,ushort)
0x140050cce  mov     r8d, ebx
0x140050cd1  lea     edx, [rbx-21h]
0x140050cd4  mov     rcx, rsi
0x140050cd7  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort,ushort)
0x140050cdc  mov     r8d, ebx
0x140050cdf  lea     edx, [rbx-39h]
0x140050ce2  mov     rcx, rsi
0x140050ce5  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort,ushort)
0x140050cea  jmp     short loc_140050CF3
0x140050cec  xor     edx, edx
0x140050cee  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x140050cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x140050cfa  lea     rax, WPP_GLOBAL_Control
0x140050d01  cmp     rcx, rax
0x140050d04  jz      short loc_140050D40
0x140050d06  test    byte ptr [rcx+1Ch], 2
0x140050d0a  jz      short loc_140050D40
0x140050d0c  mov     edx, r14d
0x140050d0f  sar     edx, 1Fh
0x140050d12  and     edx, 0FFFFFFFDh
0x140050d15  add     edx, 5
0x140050d18  movzx   eax, byte ptr [rcx+19h]
0x140050d1c  cmp     eax, edx
0x140050d1e  jb      short loc_140050D40
0x140050d20  mov     edx, 0CDh
0x140050d25  mov     rax, [rsi]
0x140050d28  mov     [rsp+0F0h+ppv], rax
0x140050d2d  mov     r9d, r14d
0x140050d30  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140050d37  mov     rcx, [rcx+10h]
0x140050d3b  call    WPP_SF_dS
0x140050d40  movups  xmm0, cs:WMC_E_SERVICE_FAILED_CRSERVER_GETFRIENDLYNAME
0x140050d47  movdqu  xmmword ptr [r15], xmm0
0x140050d4c  test    r14d, r14d
0x140050d4f  js      loc_14005113A
0x140050d55  mov     rax, [rdi]
0x140050d58  mov     rbx, [rax+58h]
0x140050d5c  mov     edx, 40h ; '@'
0x140050d61  lea     rcx, [rbp+47h+var_B0]
0x140050d65  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x140050d6a  mov     r8, rax
0x140050d6d  mov     edx, 3Fh ; '?'
0x140050d72  mov     rcx, rdi
0x140050d75  mov     rax, rbx
0x140050d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050d7d  mov     r14d, eax
0x140050d80  mov     ebx, eax
0x140050d82  sar     ebx, 1Fh
0x140050d85  mov     edx, ebx
0x140050d87  and     edx, 1
0x140050d8a  dec     edx
0x140050d8c  lea     rcx, [rbp+47h+var_B0]
0x140050d90  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x140050d95  mov     rcx, cs:WPP_GLOBAL_Control
0x140050d9c  lea     rax, WPP_GLOBAL_Control
0x140050da3  cmp     rcx, rax
0x140050da6  jz      short loc_140050DDD
0x140050da8  test    byte ptr [rcx+1Ch], 2
0x140050dac  jz      short loc_140050DDD
0x140050dae  and     ebx, 0FFFFFFFDh
0x140050db1  add     ebx, 5
0x140050db4  movzx   eax, byte ptr [rcx+19h]
0x140050db8  cmp     eax, ebx
0x140050dba  jb      short loc_140050DDD
0x140050dbc  mov     edx, 0CEh
0x140050dc1  mov     rax, [rbp+47h+var_B0]
0x140050dc5  mov     [rsp+0F0h+ppv], rax
0x140050dca  mov     r9d, r14d
0x140050dcd  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140050dd4  mov     rcx, [rcx+10h]
0x140050dd8  call    WPP_SF_dS
0x140050ddd  movups  xmm0, cs:WMC_E_SERVICE_FAILED_CRSERVER_GETSERIALNUMBER
0x140050de4  movdqu  xmmword ptr [r15], xmm0
0x140050de9  xor     edi, edi
0x140050deb  test    r14d, r14d
0x140050dee  js      loc_14005113C
0x140050df4  mov     [rbp+47h+var_48], rdi
0x140050df8  mov     [rbp+47h+var_40], rdi
0x140050dfc  mov     [rbp+47h+var_38], rdi
0x140050e00  mov     r9d, 2011Fh; unsigned int
0x140050e06  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows Media Play"...
0x140050e0d  mov     rdx, 0FFFFFFFF80000002h; hKey
0x140050e14  lea     rcx, [rbp+47h+var_48]; this
0x140050e18  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140050e1d  mov     ebx, eax
0x140050e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140050e26  lea     rax, WPP_GLOBAL_Control
0x140050e2d  cmp     rcx, rax
0x140050e30  jz      short loc_140050E62
0x140050e32  lea     eax, [rdi+2]
0x140050e35  test    [rcx+1Ch], al
0x140050e38  jz      short loc_140050E62
0x140050e3a  lea     edx, [rdi+5]
0x140050e3d  test    ebx, ebx
0x140050e3f  cmovnz  edx, eax
0x140050e42  movzx   eax, byte ptr [rcx+19h]
0x140050e46  cmp     eax, edx
0x140050e48  jb      short loc_140050E62
0x140050e4a  mov     edx, 0CFh
0x140050e4f  mov     r9d, ebx
0x140050e52  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140050e59  mov     rcx, [rcx+10h]
0x140050e5d  call    WPP_SF_d
0x140050e62  test    ebx, ebx
0x140050e64  jnz     loc_140050F43
0x140050e6a  lea     r8, [rbp+47h+arg_0]
0x140050e6e  lea     rdx, aModelname_0; "ModelName"
0x140050e75  lea     rcx, [rbp+47h+var_48]; this
0x140050e79  call    ?GetStringValue@@YAJAEAVCRegKey@ATL@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; GetStringValue(ATL::CRegKey &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140050e7e  mov     r14d, eax
0x140050e81  test    eax, eax
0x140050e83  jle     short loc_140050E90
0x140050e85  movzx   r14d, ax
0x140050e89  or      r14d, 80070000h
0x140050e90  mov     rcx, cs:WPP_GLOBAL_Control
0x140050e97  lea     rbx, WPP_GLOBAL_Control
0x140050e9e  cmp     rcx, rbx
0x140050ea1  jz      short loc_140050EDE
0x140050ea3  test    byte ptr [rcx+1Ch], 2
0x140050ea7  jz      short loc_140050EDE
0x140050ea9  mov     edx, r14d
0x140050eac  sar     edx, 1Fh
0x140050eaf  and     edx, 0FFFFFFFDh
0x140050eb2  add     edx, 5
0x140050eb5  movzx   eax, byte ptr [rcx+19h]
0x140050eb9  cmp     eax, edx
0x140050ebb  jb      short loc_140050EDE
0x140050ebd  mov     edx, 0D0h
0x140050ec2  mov     rax, [rbp+47h+arg_0]
0x140050ec6  mov     [rsp+0F0h+ppv], rax
0x140050ecb  mov     r9d, r14d
0x140050ece  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140050ed5  mov     rcx, [rcx+10h]
0x140050ed9  call    WPP_SF_dS
0x140050ede  test    r14d, r14d
0x140050ee1  js      short loc_140050F4A
0x140050ee3  mov     r8d, 1Fh
0x140050ee9  lea     rdx, [rbp+47h+arg_28]
0x140050eed  lea     rcx, [rbp+47h+arg_0]
0x140050ef1  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x140050ef6  mov     rdx, rax
0x140050ef9  lea     rcx, [rbp+47h+arg_0]
0x140050efd  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140050f02  lea     rcx, [rbp+47h+arg_28]
0x140050f06  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140050f0b  mov     edx, 3Ch ; '<'
0x140050f10  lea     r8d, [rdx+23h]
0x140050f14  lea     rcx, [rbp+47h+arg_0]
0x140050f18  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort,ushort)
0x140050f1d  mov     edx, 3Eh ; '>'
0x140050f22  lea     r8d, [rdx+21h]
0x140050f26  lea     rcx, [rbp+47h+arg_0]
0x140050f2a  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort,ushort)
0x140050f2f  mov     edx, 26h ; '&'
0x140050f34  lea     r8d, [rdx+39h]
0x140050f38  lea     rcx, [rbp+47h+arg_0]
0x140050f3c  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort,ushort)
0x140050f41  jmp     short loc_140050F4A
0x140050f43  lea     rbx, WPP_GLOBAL_Control
0x140050f4a  mov     rax, [rbp+47h+arg_0]
0x140050f4e  cmp     [rax-10h], edi
0x140050f51  jnz     short loc_140050F61
0x140050f53  mov     edx, 0CBh
  ... truncated ...
```
