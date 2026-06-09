# CWwanFirstTimeModemReadyTelemetryEventContext::Emit(int)

- ea: `0x18009a244`
- end: `0x18009ae47`
- name: `?Emit@CWwanFirstTimeModemReadyTelemetryEventContext@@QEAAXH@Z`
- size: `3075`
- prototype: `void __fastcall(CWwanFirstTimeModemReadyTelemetryEventContext *__hidden this, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003cfd8`
- `0x18009b070`

## callees

- `0x18000153c`
- `0x180005e74`
- `0x1800085d0`
- `0x1800094f4`
- `0x18001150c`
- `0x180011a1c`
- `0x180012300`
- `0x180013288`
- `0x180013588`
- `0x180014b5c`
- `0x180014c68`
- `0x180016c50`
- `0x18009a1c0`
- `0x18009a244`
- `0x18009af90`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009a48d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009a48d`

## string_xrefs

- `0x18009a549`: `SupportedDataClassBitMap`
- `0x18009a56b`: `SupportedDataClassBitMap`
- `0x18009a338`: `Failed to get WWAN_READY_INFO [%u]`
- `0x18009a287`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a346`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a4e8`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a532`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a57c`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a5c6`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a776`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a7d6`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a836`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a896`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a8f6`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a956`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009a9b6`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009aa24`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009aa92`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009ab00`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`
- `0x18009ae10`: `CWwanFirstTimeModemReadyTelemetryEventContext::Emit`

## pseudocode

```c
void __fastcall CWwanFirstTimeModemReadyTelemetryEventContext::Emit(
        CWwanFirstTimeModemReadyTelemetryEventContext *this,
        int a2)
{
  int v4; // r13d
  int v5; // edi
  int v6; // r14d
  __int64 v7; // rcx
  int v8; // r12d
  int v9; // r15d
  unsigned int v10; // eax
  __int64 v11; // rax
  signed __int64 v12; // r12
  StateSeparation *v13; // rbx
  unsigned int DWORD; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  int String; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  const unsigned __int16 *v25; // r15
  int v26; // eax
  const unsigned __int16 *v27; // r15
  int v28; // eax
  const unsigned __int16 *v29; // r15
  int v30; // eax
  __int128 v31; // xmm0
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // [rsp+28h] [rbp-138h]
  __int64 v36; // [rsp+E0h] [rbp-80h] BYREF
  unsigned int v37; // [rsp+E8h] [rbp-78h] BYREF
  unsigned int v38; // [rsp+ECh] [rbp-74h] BYREF
  unsigned int v39; // [rsp+F0h] [rbp-70h] BYREF
  int v40; // [rsp+F4h] [rbp-6Ch] BYREF
  int v41; // [rsp+F8h] [rbp-68h] BYREF
  int v42; // [rsp+FCh] [rbp-64h] BYREF
  int v43; // [rsp+100h] [rbp-60h] BYREF
  int v44; // [rsp+104h] [rbp-5Ch] BYREF
  StateSeparation *v45; // [rsp+108h] [rbp-58h] BYREF
  __int64 v46; // [rsp+110h] [rbp-50h] BYREF
  const WCHAR *v47; // [rsp+118h] [rbp-48h] BYREF
  const WCHAR *v48; // [rsp+120h] [rbp-40h] BYREF
  const WCHAR *v49; // [rsp+128h] [rbp-38h] BYREF
  const WCHAR *v50; // [rsp+130h] [rbp-30h] BYREF
  __int64 v51; // [rsp+138h] [rbp-28h] BYREF
  __int64 v52; // [rsp+140h] [rbp-20h] BYREF
  __int64 v53; // [rsp+148h] [rbp-18h] BYREF
  __int64 v54; // [rsp+150h] [rbp-10h] BYREF
  const WCHAR *v55; // [rsp+158h] [rbp-8h] BYREF
  const WCHAR *v56; // [rsp+160h] [rbp+0h] BYREF
  const WCHAR *v57; // [rsp+168h] [rbp+8h] BYREF
  const WCHAR *v58; // [rsp+170h] [rbp+10h] BYREF
  const WCHAR *v59; // [rsp+178h] [rbp+18h] BYREF
  const WCHAR *v60; // [rsp+180h] [rbp+20h] BYREF
  const WCHAR *v61; // [rsp+188h] [rbp+28h] BYREF
  __int64 v62[28]; // [rsp+190h] [rbp+30h] BYREF
  GUID rguid; // [rsp+270h] [rbp+110h] BYREF
  OLECHAR sz[56]; // [rsp+280h] [rbp+120h] BYREF
  __int128 v65; // [rsp+2F0h] [rbp+190h] BYREF
  __int64 v66; // [rsp+300h] [rbp+1A0h]
  __int64 v67; // [rsp+308h] [rbp+1A8h]
  __int128 v68; // [rsp+310h] [rbp+1B0h] BYREF
  __int64 v69; // [rsp+320h] [rbp+1C0h]
  __int64 v70; // [rsp+328h] [rbp+1C8h]
  __int128 v71; // [rsp+330h] [rbp+1D0h] BYREF
  __int64 v72; // [rsp+340h] [rbp+1E0h]
  __int64 v73; // [rsp+348h] [rbp+1E8h]
  __int128 v74; // [rsp+350h] [rbp+1F0h] BYREF
  __int64 v75; // [rsp+360h] [rbp+200h]
  __int64 v76; // [rsp+368h] [rbp+208h]
  __int128 v77; // [rsp+370h] [rbp+210h] BYREF
  __int64 v78; // [rsp+380h] [rbp+220h]
  __int64 v79; // [rsp+388h] [rbp+228h]
  __int128 v80; // [rsp+390h] [rbp+230h] BYREF
  __int64 v81; // [rsp+3A0h] [rbp+240h]
  __int64 v82; // [rsp+3A8h] [rbp+248h]
  __int128 v83; // [rsp+3B0h] [rbp+250h] BYREF
  __int64 v84; // [rsp+3C0h] [rbp+260h]
  __int64 v85; // [rsp+3C8h] [rbp+268h]
  __int128 v86; // [rsp+3D0h] [rbp+270h] BYREF
  __int64 v87; // [rsp+3E0h] [rbp+280h]
  __int64 v88; // [rsp+3E8h] [rbp+288h]
  __int128 v89; // [rsp+3F0h] [rbp+290h] BYREF
  __int64 v90; // [rsp+400h] [rbp+2A0h]
  __int64 v91; // [rsp+408h] [rbp+2A8h]
  __int128 v92; // [rsp+410h] [rbp+2B0h] BYREF
  __int64 v93; // [rsp+420h] [rbp+2C0h]
  __int64 v94; // [rsp+428h] [rbp+2C8h]
  __int128 v95; // [rsp+430h] [rbp+2D0h] BYREF

  WwanLog::Verbose(
    "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
    (const struct _GUID *)(*(_QWORD *)this + 12536LL),
    L"enter");
  v4 = 0;
  if ( *((_BYTE *)this + 156) )
  {
    v5 = 0;
    CWwanFirstTimeModemReadyTelemetryEventContext::Stop(this);
    v6 = 1;
    if ( !a2 )
    {
      v7 = *(_QWORD *)this;
      v8 = 0;
      rguid = 0;
      v9 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v7 + 320LL))(v7, &rguid) )
      {
        v8 = *(_DWORD *)rguid.Data4;
        v4 = *(_DWORD *)&rguid.Data4[4];
        a2 = *(_DWORD *)&rguid.Data2;
        v9 = *(unsigned __int8 *)(*(_QWORD *)this + 27608LL);
      }
      memset_0(sz, 0, 0x64u);
      v10 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(**(_QWORD **)this + 440LL))(*(_QWORD *)this, sz);
      if ( v10 )
      {
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          (const struct _GUID *)(*(_QWORD *)this + 12536LL),
          L"Failed to get WWAN_READY_INFO [%u]",
          v10);
        v5 = 6;
      }
      else
      {
        switch ( *(_DWORD *)sz )
        {
          case 2:
          case 7:
            v5 = 3;
            break;
          case 3:
            v5 = 4;
            break;
          case 6:
            v5 = 5;
            break;
          default:
            if ( a2 )
            {
              if ( v9 )
              {
                v5 = 13;
              }
              else if ( v8 && v4 )
              {
                if ( *(_DWORD *)sz == 5 )
                {
                  v5 = 10;
                }
                else if ( *(_DWORD *)sz )
                {
                  if ( *(_DWORD *)sz == 4 )
                  {
                    v5 = 12;
                  }
                  else if ( *(_DWORD *)sz == 1 )
                  {
                    v11 = HIDWORD(*(_QWORD *)(*(_QWORD *)this + 14344LL));
                    if ( (_DWORD)v11 == 6 )
                    {
                      v5 = 9;
                    }
                    else if ( (unsigned int)(v11 - 3) <= 2 )
                    {
                      if ( *(_DWORD *)(*(_QWORD *)this + 14556LL) != 2 )
                        v5 = 8;
                    }
                    else
                    {
                      v5 = 7;
                    }
                  }
                  else
                  {
                    v5 = 14;
                  }
                }
                else
                {
                  v5 = 11;
                }
              }
              else
              {
                v5 = 2;
              }
            }
            else
            {
              v5 = 1;
            }
            break;
        }
      }
    }
    if ( CServiceHandler::s_lLoggingRegistered >= 0 )
    {
      v39 = 37;
      v12 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
      std::make_unique<StateSeparation,enum _REG_ROOT_PATH,0>(&v45, &v39);
      memset_0(sz, 0, 0x5Eu);
      rguid = *(GUID *)(*(_QWORD *)this + 12536LL);
      StringFromGUID2(&rguid, sz, 47);
      v13 = v45;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      DWORD = StateSeparation::GetDWORD(v45, sz, L"DSDxType", (unsigned int *)&v36 + 1);
      if ( DWORD )
      {
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s DWORD property [%s] with error (%u)",
          sz,
          L"DSDxType",
          DWORD);
        HIDWORD(v36) = 0;
      }
      v15 = StateSeparation::GetDWORD(v13, sz, L"ActiveSIMSlotForDSSA", (unsigned int *)&v36);
      if ( v15 )
      {
        LODWORD(v35) = v15;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s DWORD property [%s] with error (%u)",
          sz,
          L"ActiveSIMSlotForDSSA",
          v35);
        LODWORD(v36) = 0;
      }
      v16 = StateSeparation::GetDWORD(v13, sz, L"SupportedDataClassBitMap", &v37);
      if ( v16 )
      {
        LODWORD(v35) = v16;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s DWORD property [%s] with error (%u)",
          sz,
          L"SupportedDataClassBitMap",
          v35);
        v37 = 0;
      }
      v17 = StateSeparation::GetDWORD(v13, sz, L"ModemOptionalCapabilityBitMap", &v38);
      if ( v17 )
      {
        LODWORD(v35) = v17;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s DWORD property [%s] with error (%u)",
          sz,
          L"ModemOptionalCapabilityBitMap",
          v35);
        v38 = 0;
      }
      if ( v36 != 0x200000001LL )
        v6 = 0;
      v90 = 0;
      v89 = 0;
      v86 = 0;
      LOWORD(v89) = 0;
      v83 = 0;
      LOWORD(v86) = 0;
      v92 = 0;
      LOWORD(v83) = 0;
      v77 = 0;
      LOWORD(v92) = 0;
      v74 = 0;
      LOWORD(v77) = 0;
      v71 = 0;
      LOWORD(v74) = 0;
      v68 = 0;
      LOWORD(v71) = 0;
      v80 = 0;
      LOWORD(v68) = 0;
      v65 = 0;
      LOWORD(v80) = 0;
      LOWORD(v65) = 0;
      v91 = 7;
      v87 = 0;
      v88 = 7;
      v84 = 0;
      v85 = 7;
      v93 = 0;
      v94 = 7;
      v78 = 0;
      v79 = 7;
      v75 = 0;
      v76 = 7;
      v72 = 0;
      v73 = 7;
      v69 = 0;
      v70 = 7;
      v81 = 0;
      v82 = 7;
      v66 = 0;
      v67 = 7;
      String = StateSeparation::GetString(v13, sz, L"HWID", &v89);
      if ( String )
      {
        LODWORD(v35) = String;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          L"HWID",
          v35);
        v90 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v89) = 0;
      }
      v19 = StateSeparation::GetString(v13, sz, L"DriverName", &v86);
      if ( v19 )
      {
        LODWORD(v35) = v19;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          L"DriverName",
          v35);
        v87 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v86) = 0;
      }
      v20 = StateSeparation::GetString(v13, sz, L"Manufacturer", &v83);
      if ( v20 )
      {
        LODWORD(v35) = v20;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          L"Manufacturer",
          v35);
        v84 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v83) = 0;
      }
      v21 = StateSeparation::GetString(v13, sz, L"Model", &v92);
      if ( v21 )
      {
        LODWORD(v35) = v21;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          L"Model",
          v35);
        v93 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v92) = 0;
      }
      v22 = StateSeparation::GetString(v13, sz, L"FirmwareVersion", &v77);
      if ( v22 )
      {
        LODWORD(v35) = v22;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          L"FirmwareVersion",
          v35);
        v78 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v77) = 0;
      }
      v23 = StateSeparation::GetString(v13, sz, L"DriverVersion", &v74);
      if ( v23 )
      {
        LODWORD(v35) = v23;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          L"DriverVersion",
          v35);
        v75 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v74) = 0;
      }
      v24 = StateSeparation::GetString(v13, sz, L"InterfaceTypeVer", &v71);
      if ( v24 )
      {
        LODWORD(v35) = v24;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          L"InterfaceTypeVer",
          v35);
        v72 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v71) = 0;
      }
      v25 = L"MCC1";
      if ( !v6 )
        v25 = L"MCC0";
      v26 = StateSeparation::GetString(v13, sz, v25, &v68);
      if ( v26 )
      {
        LODWORD(v35) = v26;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          v25,
          v35);
        v69 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v68) = 0;
      }
      v27 = L"MNC1";
      if ( !v6 )
        v27 = L"MNC0";
      v28 = StateSeparation::GetString(v13, sz, v27, &v80);
      if ( v28 )
      {
        LODWORD(v35) = v28;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          v27,
          v35);
        v81 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v80) = 0;
      }
      v29 = L"HomeProviderName1";
      if ( !v6 )
        v29 = L"HomeProviderName0";
      v30 = StateSeparation::GetString(v13, sz, v29, &v65);
      if ( v30 )
      {
        LODWORD(v35) = v30;
        WwanLog::Error(
          "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
          0,
          L": Failed to get interface %s string property [%s] with error (%u)",
          sz,
          v29,
          v35);
        v66 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v65) = 0;
      }
      if ( (unsigned int)dword_180151040 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x800000000000LL) )
        {
          v39 = *((_DWORD *)this + 35);
          v40 = *((_DWORD *)this + 34);
          v41 = *((_DWORD *)this + 37);
          v42 = *((_DWORD *)this + 38);
          v43 = *((_DWORD *)this + 36);
          v44 = v5;
          v46 = 16779264;
          v47 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v65);
          v48 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v80);
          v49 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v68);
          v50 = L"5G";
          v51 = v37;
          v52 = v38;
          v53 = (unsigned int)v36;
          v54 = HIDWORD(v36);
          v55 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v71);
          v56 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v74);
          v57 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v77);
          v58 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v86);
          v59 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v89);
          v60 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v92);
          v61 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v83);
          v31 = *(_OWORD *)(*(_QWORD *)this + 12536LL);
          *(_QWORD *)&rguid.Data1 = v12;
          v62[0] = (__int64)&v95;
          v95 = v31;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v32,
            (__int64)word_18014071A,
            v33,
            v34,
            (__int64)&rguid,
            v62,
            &v61,
            &v60,
            &v59,
            &v58,
            &v57,
            &v56,
            &v55,
            (__int64)&v54,
            (__int64)&v53,
            (__int64)&v52,
            (__int64)&v51,
            &v50,
            &v49,
            &v48,
            &v47,
            (__int64)&v46,
            (__int64)&v44,
            (__int64)&v43,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v40,
            (__int64)&v39);
        }
      }
      std::wstring::_Tidy_deallocate(&v65);
      std::wstring::_Tidy_deallocate(&v80);
      std::wstring::_Tidy_deallocate(&v68);
      std::wstring::_Tidy_deallocate(&v71);
      std::wstring::_Tidy_deallocate(&v74);
      std::wstring::_Tidy_deallocate(&v77);
      std::wstring::_Tidy_deallocate(&v92);
      std::wstring::_Tidy_deallocate(&v83);
      std::wstring::_Tidy_deallocate(&v86);
      std::wstring::_Tidy_deallocate(&v89);
      std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(&v45);
      WwanLog::Verbose(
        "CWwanFirstTimeModemReadyTelemetryEventContext::Emit",
        (const struct _GUID *)(*(_QWORD *)this + 12536LL),
        L"Emit to telemetry provider");
    }
    CWwanFirstTimeModemReadyTelemetryEventContext::Clear(this);
  }
}

```

## disassembly

```asm
0x18009a244  push    rbp
0x18009a246  push    rbx
0x18009a247  push    rsi
0x18009a248  push    rdi
0x18009a249  push    r12
0x18009a24b  push    r13
0x18009a24d  push    r14
0x18009a24f  push    r15
0x18009a251  lea     rbp, [rsp-2F8h]
0x18009a259  sub     rsp, 458h
0x18009a260  mov     rax, cs:__security_cookie
0x18009a267  xor     rax, rsp
0x18009a26a  mov     [rbp+330h+var_50], rax
0x18009a271  mov     ebx, edx
0x18009a273  lea     r8, aEnter; "enter"
0x18009a27a  mov     rdx, [rcx]
0x18009a27d  mov     rsi, rcx
0x18009a280  add     rdx, 30F8h; struct _GUID *
0x18009a287  lea     rcx, aCwwanfirsttime_4; "CWwanFirstTimeModemReadyTelemetryEventC"...
0x18009a28e  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18009a293  xor     r13d, r13d
0x18009a296  cmp     [rsi+9Ch], r13b
0x18009a29d  jz      loc_18009AE24
0x18009a2a3  mov     rcx, rsi; this
0x18009a2a6  mov     edi, r13d
0x18009a2a9  call    ?Stop@CWwanFirstTimeModemReadyTelemetryEventContext@@AEAAXXZ; CWwanFirstTimeModemReadyTelemetryEventContext::Stop(void)
0x18009a2ae  lea     r14d, [r13+1]
0x18009a2b2  test    ebx, ebx
0x18009a2b4  jnz     loc_18009A425
0x18009a2ba  mov     rcx, [rsi]
0x18009a2bd  lea     rdx, [rbp+330h+rguid]
0x18009a2c4  xorps   xmm0, xmm0
0x18009a2c7  mov     r12d, r13d
0x18009a2ca  movups  xmmword ptr [rbp+330h+rguid.Data1], xmm0
0x18009a2d1  xor     r15d, r15d
0x18009a2d4  mov     rax, [rcx]
0x18009a2d7  mov     rax, [rax+140h]
0x18009a2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a2e3  test    eax, eax
0x18009a2e5  jnz     short loc_18009A306
0x18009a2e7  mov     rax, [rsi]
0x18009a2ea  mov     r12d, dword ptr [rbp+330h+rguid.Data4]
0x18009a2f1  mov     r13d, dword ptr [rbp+330h+rguid.Data4+4]
0x18009a2f8  mov     ebx, dword ptr [rbp+330h+rguid.Data2]
0x18009a2fe  movzx   r15d, byte ptr [rax+6BD8h]
0x18009a306  xor     edx, edx; Val
0x18009a308  lea     rcx, [rbp+330h+sz]; void *
0x18009a30f  lea     r8d, [rdx+64h]; Size
0x18009a313  call    memset_0
0x18009a318  mov     rcx, [rsi]
0x18009a31b  lea     rdx, [rbp+330h+sz]
0x18009a322  mov     rax, [rcx]
0x18009a325  mov     rax, [rax+1B8h]
0x18009a32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a331  test    eax, eax
0x18009a333  jz      short loc_18009A35F
0x18009a335  mov     rdx, [rsi]
0x18009a338  lea     r8, aFailedToGetWwa; "Failed to get WWAN_READY_INFO [%u]"
0x18009a33f  add     rdx, 30F8h; struct _GUID *
0x18009a346  lea     rcx, aCwwanfirsttime_4; "CWwanFirstTimeModemReadyTelemetryEventC"...
0x18009a34d  mov     r9d, eax
0x18009a350  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009a355  mov     edi, 6
0x18009a35a  jmp     loc_18009A422
0x18009a35f  mov     eax, dword ptr [rbp+330h+sz]
0x18009a365  cmp     eax, 2
0x18009a368  jz      loc_18009A41D
0x18009a36e  cmp     eax, 7
0x18009a371  jz      loc_18009A41D
0x18009a377  cmp     eax, 3
0x18009a37a  jnz     short loc_18009A384
0x18009a37c  lea     edi, [rax+1]
0x18009a37f  jmp     loc_18009A422
0x18009a384  cmp     eax, 6
0x18009a387  jnz     short loc_18009A391
0x18009a389  lea     edi, [rax-1]
0x18009a38c  jmp     loc_18009A422
0x18009a391  test    ebx, ebx
0x18009a393  jnz     short loc_18009A39D
0x18009a395  mov     edi, r14d
0x18009a398  jmp     loc_18009A422
0x18009a39d  test    r15d, r15d
0x18009a3a0  jz      short loc_18009A3A9
0x18009a3a2  mov     edi, 0Dh
0x18009a3a7  jmp     short loc_18009A422
0x18009a3a9  test    r12d, r12d
0x18009a3ac  jz      short loc_18009A416
0x18009a3ae  test    r13d, r13d
0x18009a3b1  jz      short loc_18009A416
0x18009a3b3  xor     r13d, r13d
0x18009a3b6  cmp     eax, 5
0x18009a3b9  jnz     short loc_18009A3C0
0x18009a3bb  lea     edi, [rax+5]
0x18009a3be  jmp     short loc_18009A425
0x18009a3c0  test    eax, eax
0x18009a3c2  jnz     short loc_18009A3C9
0x18009a3c4  lea     edi, [rax+0Bh]
0x18009a3c7  jmp     short loc_18009A425
0x18009a3c9  cmp     eax, 4
0x18009a3cc  jnz     short loc_18009A3D3
0x18009a3ce  lea     edi, [rax+8]
0x18009a3d1  jmp     short loc_18009A425
0x18009a3d3  cmp     eax, r14d
0x18009a3d6  jz      short loc_18009A3DF
0x18009a3d8  mov     edi, 0Eh
0x18009a3dd  jmp     short loc_18009A425
0x18009a3df  mov     rcx, [rsi]
0x18009a3e2  mov     rax, [rcx+3808h]
0x18009a3e9  shr     rax, 20h
0x18009a3ed  cmp     eax, 6
0x18009a3f0  jnz     short loc_18009A3F7
0x18009a3f2  lea     edi, [rax+3]
0x18009a3f5  jmp     short loc_18009A425
0x18009a3f7  add     eax, 0FFFFFFFDh
0x18009a3fa  cmp     eax, 2
0x18009a3fd  jbe     short loc_18009A406
0x18009a3ff  mov     edi, 7
0x18009a404  jmp     short loc_18009A425
0x18009a406  cmp     dword ptr [rcx+38DCh], 2
0x18009a40d  jz      short loc_18009A425
0x18009a40f  mov     edi, 8
0x18009a414  jmp     short loc_18009A425
0x18009a416  mov     edi, 2
0x18009a41b  jmp     short loc_18009A422
0x18009a41d  mov     edi, 3
0x18009a422  xor     r13d, r13d
0x18009a425  cmp     cs:?s_lLoggingRegistered@CServiceHandler@@0JA, r13d; long CServiceHandler::s_lLoggingRegistered
0x18009a42c  jl      loc_18009AE1C
0x18009a432  mov     r12, r14
0x18009a435  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r12; unsigned __int64 g_TelemetrySequenceNumber
0x18009a43e  lea     rdx, [rbp+330h+var_3A0]
0x18009a442  mov     [rbp+330h+var_3A0], 25h ; '%'
0x18009a449  lea     rcx, [rbp+330h+var_388]
0x18009a44d  add     r12, r14
0x18009a450  call    ??$make_unique@VStateSeparation@@W4_REG_ROOT_PATH@@$0A@@std@@YA?AV?$unique_ptr@VStateSeparation@@U?$default_delete@VStateSeparation@@@std@@@0@$$QEAW4_REG_ROOT_PATH@@@Z; std::make_unique<StateSeparation,_REG_ROOT_PATH,0>(_REG_ROOT_PATH &&)
0x18009a455  xor     edx, edx; Val
0x18009a457  lea     rcx, [rbp+330h+sz]; void *
0x18009a45e  lea     r8d, [rdx+5Eh]; Size
0x18009a462  call    memset_0
0x18009a467  mov     rax, [rsi]
0x18009a46a  lea     rdx, [rbp+330h+sz]; lpsz
0x18009a471  mov     r8d, 2Fh ; '/'; cchMax
0x18009a477  lea     rcx, [rbp+330h+rguid]; rguid
0x18009a47e  movups  xmm0, xmmword ptr [rax+30F8h]
0x18009a485  movdqu  xmmword ptr [rbp+330h+rguid.Data1], xmm0
0x18009a48d  call    cs:__imp_StringFromGUID2
0x18009a493  mov     rbx, [rbp+330h+var_388]
0x18009a497  lea     r9, [rbp+330h+var_3B0+4]; unsigned int *
0x18009a49b  mov     rcx, rbx; this
0x18009a49e  mov     dword ptr [rbp+330h+var_3B0+4], r13d
0x18009a4a2  lea     r8, aDsdxtype; "DSDxType"
0x18009a4a9  mov     dword ptr [rbp+330h+var_3B0], r13d
0x18009a4ad  lea     rdx, [rbp+330h+sz]; unsigned __int16 *
0x18009a4b4  mov     [rbp+330h+var_3A8], r13d
0x18009a4b8  mov     [rbp+330h+var_3A4], r13d
0x18009a4bc  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18009a4c1  lea     r15, aFailedToGetInt_0; ": Failed to get interface %s DWORD prop"...
0x18009a4c8  test    eax, eax
0x18009a4ca  jz      short loc_18009A4F8
0x18009a4cc  mov     dword ptr [rsp+490h+var_468], eax
0x18009a4d0  lea     r9, [rbp+330h+sz]
0x18009a4d7  lea     rax, aDsdxtype; "DSDxType"
0x18009a4de  mov     r8, r15; unsigned __int16 *
0x18009a4e1  xor     edx, edx; struct _GUID *
0x18009a4e3  mov     [rsp+490h+var_470], rax
0x18009a4e8  lea     rcx, aCwwanfirsttime_4; "CWwanFirstTimeModemReadyTelemetryEventC"...
0x18009a4ef  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009a4f4  mov     dword ptr [rbp+330h+var_3B0+4], r13d
0x18009a4f8  lea     r9, [rbp+330h+var_3B0]; unsigned int *
0x18009a4fc  mov     rcx, rbx; this
0x18009a4ff  lea     r8, aActivesimslotf; "ActiveSIMSlotForDSSA"
0x18009a506  lea     rdx, [rbp+330h+sz]; unsigned __int16 *
0x18009a50d  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18009a512  test    eax, eax
0x18009a514  jz      short loc_18009A542
0x18009a516  mov     dword ptr [rsp+490h+var_468], eax
0x18009a51a  lea     r9, [rbp+330h+sz]
0x18009a521  lea     rax, aActivesimslotf; "ActiveSIMSlotForDSSA"
0x18009a528  mov     r8, r15; unsigned __int16 *
0x18009a52b  xor     edx, edx; struct _GUID *
0x18009a52d  mov     [rsp+490h+var_470], rax
0x18009a532  lea     rcx, aCwwanfirsttime_4; "CWwanFirstTimeModemReadyTelemetryEventC"...
0x18009a539  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009a53e  mov     dword ptr [rbp+330h+var_3B0], r13d
0x18009a542  lea     r9, [rbp+330h+var_3A8]; unsigned int *
0x18009a546  mov     rcx, rbx; this
0x18009a549  lea     r8, aSupporteddatac; "SupportedDataClassBitMap"
0x18009a550  lea     rdx, [rbp+330h+sz]; unsigned __int16 *
0x18009a557  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18009a55c  test    eax, eax
0x18009a55e  jz      short loc_18009A58C
0x18009a560  mov     dword ptr [rsp+490h+var_468], eax
0x18009a564  lea     r9, [rbp+330h+sz]
0x18009a56b  lea     rax, aSupporteddatac; "SupportedDataClassBitMap"
0x18009a572  mov     r8, r15; unsigned __int16 *
0x18009a575  xor     edx, edx; struct _GUID *
0x18009a577  mov     [rsp+490h+var_470], rax
0x18009a57c  lea     rcx, aCwwanfirsttime_4; "CWwanFirstTimeModemReadyTelemetryEventC"...
0x18009a583  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009a588  mov     [rbp+330h+var_3A8], r13d
0x18009a58c  lea     r9, [rbp+330h+var_3A4]; unsigned int *
0x18009a590  mov     rcx, rbx; this
0x18009a593  lea     r8, aModemoptionalc; "ModemOptionalCapabilityBitMap"
0x18009a59a  lea     rdx, [rbp+330h+sz]; unsigned __int16 *
0x18009a5a1  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18009a5a6  test    eax, eax
0x18009a5a8  jz      short loc_18009A5D6
0x18009a5aa  mov     dword ptr [rsp+490h+var_468], eax
0x18009a5ae  lea     r9, [rbp+330h+sz]
0x18009a5b5  lea     rax, aModemoptionalc; "ModemOptionalCapabilityBitMap"
0x18009a5bc  mov     r8, r15; unsigned __int16 *
0x18009a5bf  xor     edx, edx; struct _GUID *
0x18009a5c1  mov     [rsp+490h+var_470], rax
0x18009a5c6  lea     rcx, aCwwanfirsttime_4; "CWwanFirstTimeModemReadyTelemetryEventC"...
0x18009a5cd  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009a5d2  mov     [rbp+330h+var_3A4], r13d
0x18009a5d6  cmp     dword ptr [rbp+330h+var_3B0+4], 2
0x18009a5da  jnz     short loc_18009A5E2
0x18009a5dc  cmp     dword ptr [rbp+330h+var_3B0], r14d
0x18009a5e0  jz      short loc_18009A5E5
0x18009a5e2  mov     r14d, r13d
0x18009a5e5  xorps   xmm0, xmm0
0x18009a5e8  mov     [rbp+330h+var_90], r13
0x18009a5ef  movups  [rbp+330h+var_A0], xmm0
0x18009a5f6  lea     r9, [rbp+330h+var_A0]
0x18009a5fd  mov     rcx, rbx
0x18009a600  movups  [rbp+330h+var_C0], xmm0
0x18009a607  lea     r8, aHwid; "HWID"
0x18009a60e  mov     word ptr [rbp+330h+var_A0], r13w
0x18009a616  movups  [rbp+330h+var_E0], xmm0
0x18009a61d  lea     rdx, [rbp+330h+sz]
0x18009a624  mov     word ptr [rbp+330h+var_C0], r13w
0x18009a62c  movups  [rbp+330h+var_80], xmm0
0x18009a633  mov     word ptr [rbp+330h+var_E0], r13w
0x18009a63b  movups  [rbp+330h+var_120], xmm0
0x18009a642  mov     word ptr [rbp+330h+var_80], r13w
0x18009a64a  movups  [rbp+330h+var_140], xmm0
0x18009a651  mov     word ptr [rbp+330h+var_120], r13w
0x18009a659  movups  [rbp+330h+var_160], xmm0
0x18009a660  mov     word ptr [rbp+330h+var_140], r13w
0x18009a668  movups  [rbp+330h+var_180], xmm0
0x18009a66f  mov     word ptr [rbp+330h+var_160], r13w
0x18009a677  movups  [rbp+330h+var_100], xmm0
0x18009a67e  mov     word ptr [rbp+330h+var_180], r13w
0x18009a686  movups  [rbp+330h+var_1A0], xmm0
0x18009a68d  mov     word ptr [rbp+330h+var_100], r13w
0x18009a695  mov     word ptr [rbp+330h+var_1A0], r13w
0x18009a69d  mov     [rbp+330h+var_88], 7
0x18009a6a8  mov     [rbp+330h+var_B0], r13
0x18009a6af  mov     [rbp+330h+var_A8], 7
0x18009a6ba  mov     [rbp+330h+var_D0], r13
0x18009a6c1  mov     [rbp+330h+var_C8], 7
0x18009a6cc  mov     [rbp+330h+var_70], r13
0x18009a6d3  mov     [rbp+330h+var_68], 7
0x18009a6de  mov     [rbp+330h+var_110], r13
0x18009a6e5  mov     [rbp+330h+var_108], 7
0x18009a6f0  mov     [rbp+330h+var_130], r13
0x18009a6f7  mov     [rbp+330h+var_128], 7
0x18009a702  mov     [rbp+330h+var_150], r13
0x18009a709  mov     [rbp+330h+var_148], 7
0x18009a714  mov     [rbp+330h+var_170], r13
0x18009a71b  mov     [rbp+330h+var_168], 7
0x18009a726  mov     [rbp+330h+var_F0], r13
0x18009a72d  mov     [rbp+330h+var_E8], 7
0x18009a738  mov     [rbp+330h+var_190], r13
0x18009a73f  mov     [rbp+330h+var_188], 7
0x18009a74a  call    ?GetString@StateSeparation@@QEAAKPEBG0PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StateSeparation::GetString(ushort const *,ushort const *,std::wstring *)
0x18009a74f  lea     r15, aFailedToGetInt; ": Failed to get interface %s string pro"...
0x18009a756  test    eax, eax
0x18009a758  jz      short loc_18009A799
0x18009a75a  mov     dword ptr [rsp+490h+var_468], eax
0x18009a75e  lea     r9, [rbp+330h+sz]
0x18009a765  lea     rax, aHwid; "HWID"
0x18009a76c  mov     r8, r15; unsigned __int16 *
0x18009a76f  xor     edx, edx; struct _GUID *
0x18009a771  mov     [rsp+490h+var_470], rax
0x18009a776  lea     rcx, aCwwanfirsttime_4; "CWwanFirstTimeModemReadyTelemetryEventC"...
0x18009a77d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009a782  lea     rcx, [rbp+330h+var_A0]
0x18009a789  mov     [rbp+330h+var_90], r13
0x18009a790  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009a795  mov     [rax], r13w
0x18009a799  lea     r9, [rbp+330h+var_C0]
0x18009a7a0  mov     rcx, rbx
0x18009a7a3  lea     r8, aDrivername; "DriverName"
0x18009a7aa  lea     rdx, [rbp+330h+sz]
0x18009a7b1  call    ?GetString@StateSeparation@@QEAAKPEBG0PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StateSeparation::GetString(ushort const *,ushort const *,std::wstring *)
0x18009a7b6  test    eax, eax
0x18009a7b8  jz      short loc_18009A7F9
0x18009a7ba  mov     dword ptr [rsp+490h+var_468], eax
0x18009a7be  lea     r9, [rbp+330h+sz]
0x18009a7c5  lea     rax, aDrivername; "DriverName"
0x18009a7cc  mov     r8, r15; unsigned __int16 *
0x18009a7cf  xor     edx, edx; struct _GUID *
0x18009a7d1  mov     [rsp+490h+var_470], rax
0x18009a7d6  lea     rcx, aCwwanfirsttime_4; "CWwanFirstTimeModemReadyTelemetryEventC"...
0x18009a7dd  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009a7e2  lea     rcx, [rbp+330h+var_C0]
0x18009a7e9  mov     [rbp+330h+var_B0], r13
0x18009a7f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
  ... truncated ...
```
