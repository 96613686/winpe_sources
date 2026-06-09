# GenerateLineColumnUpdates(CallHistoryDataSession *,UdmObjectId,ulong,UdmPropertyValue *,utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>> *,utl::vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>>> *)

- ea: `0x1800d8c34`
- end: `0x1800d93b2`
- name: `?GenerateLineColumnUpdates@@YAJPEAVCallHistoryDataSession@@UUdmObjectId@@KPEAUUdmPropertyValue@@PEAV?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@PEAV?$vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@utl@@@5@@Z`
- size: `1918`
- prototype: `__int64 __usercall@<rax>(struct CallHistoryDataSession *@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d8b0c`

## callees

- `0x1800049f0`
- `0x180008ee8`
- `0x180008f0c`
- `0x180009918`
- `0x180012988`
- `0x180027220`
- `0x18003307c`
- `0x180041be4`
- `0x18005e160`
- `0x18005e1bc`
- `0x180062674`
- `0x180064828`
- `0x180066860`
- `0x180075f98`
- `0x1800765d0`
- `0x1800d8624`
- `0x1800d8c34`
- `0x1800d93b8`
- `0x1800d9d90`
- `0x1800d9f7c`
- `0x1800e18b4`
- `0x1800e2f58`
- `0x18012c7b0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800d908e`
- `msvcrt!wcscpy_s` at `0x1800d908e`
- `UserDataTypeHelperUtil!DupString` at `0x1800d8dfe`
- `UserDataTypeHelperUtil!DupString` at `0x1800d8efa`
- `UserDataTypeHelperUtil!DupString` at `0x1800d8f40`
- `UserDataTypeHelperUtil!DupString` at `0x1800d8dfe`
- `UserDataTypeHelperUtil!DupString` at `0x1800d8efa`
- `UserDataTypeHelperUtil!DupString` at `0x1800d8f40`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800d90a4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800d90a4`

## string_xrefs

- `0x1800d8fd7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800d8c9f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d8d85`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d8ddf`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d8e8f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d8f10`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d917b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d9233`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d92ad`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d9370`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`

## pseudocode

```c
__int64 __fastcall GenerateLineColumnUpdates(
        DatabaseVolumeSession **a1,
        __int64 a2,
        unsigned int a3,
        struct UdmPropertyValue *a4,
        _QWORD *a5,
        __int64 a6)
{
  unsigned __int64 v8; // rsi
  unsigned int AppInstanceId; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  struct UdmPropertyValue *PropByUdmPropId; // rax
  struct UdmPropertyValue *v13; // rdx
  unsigned __int64 v14; // rcx
  __int64 v15; // r10
  __int64 v16; // rsi
  struct UdmPropertyValue *v17; // r14
  const struct UdmObjectId *v18; // rbx
  unsigned int v19; // r8d
  int v20; // r11d
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  struct UdmPropertyValue *v25; // rdx
  unsigned __int16 *v26; // r15
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  struct UdmPropertyValue *v30; // rdx
  int v31; // eax
  int v32; // ecx
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rcx
  struct UdmPropertyValue *v36; // rdx
  unsigned __int16 *v37; // rax
  int v38; // edx
  int v39; // ecx
  void **v40; // rax
  int AppDisplayName; // eax
  __int64 v42; // r9
  __int64 v43; // rdx
  __int64 v44; // rcx
  char v45; // bl
  struct UdmPropertyValue *v46; // rdx
  DatabaseVolumeSession *v47; // rcx
  __int64 v48; // rcx
  unsigned int Column; // ebx
  int v50; // eax
  __int64 v51; // r9
  __int64 v52; // rcx
  const wchar_t *v53; // r8
  __int64 v54; // rdx
  int v55; // eax
  struct UdmPropertyValue *v56; // rdx
  struct UdmPropertyValue *v57; // rdx
  struct UdmPropertyValue *v58; // rdx
  void **v59; // rax
  int v60; // eax
  __int64 v61; // r9
  __int64 v62; // rdx
  __int64 v63; // rcx
  _QWORD *v64; // rax
  __int64 v65; // r15
  int v66; // eax
  unsigned __int16 *v67; // rcx
  int v68; // r9d
  int v69; // r8d
  unsigned __int16 *v70; // rax
  __int64 v71; // r15
  int v72; // edx
  int v73; // ecx
  void *v75; // [rsp+30h] [rbp-D0h] BYREF
  int v76; // [rsp+38h] [rbp-C8h]
  _QWORD *v77; // [rsp+40h] [rbp-C0h] BYREF
  int v78; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v79; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v80[24]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v81; // [rsp+88h] [rbp-78h] BYREF
  __int64 v82; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v83[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v84; // [rsp+B0h] [rbp-50h]
  GUID pclsid; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v86[12]; // [rsp+D0h] [rbp-30h]
  int v87; // [rsp+DCh] [rbp-24h]
  __int64 v88; // [rsp+E0h] [rbp-20h]
  __int128 v89; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v90; // [rsp+100h] [rbp+0h]
  wchar_t Destination[40]; // [rsp+110h] [rbp+10h] BYREF

  *(_QWORD *)&v79.Data1 = a2;
  v77 = a5;
  pclsid = 0;
  v8 = a3;
  AppInstanceId = ServiceDataSession::GetAppInstanceId((ServiceDataSession *)a1, (struct AppInstanceId *)&pclsid);
  if ( (AppInstanceId & 0x80000000) == 0 )
  {
    PropByUdmPropId = FindPropByUdmPropId(v8, a4, 0x190005u);
    v16 = (__int64)PropByUdmPropId;
    if ( PropByUdmPropId && *((_QWORD *)PropByUdmPropId + 1) == v15 )
    {
      v10 = 195;
      v11 = 0;
      AppInstanceId = -2147024809;
      goto LABEL_3;
    }
    v17 = FindPropByUdmPropId(v14, v13, 0x240002u);
    utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v80);
    v18 = *(const struct UdmObjectId **)&v79.Data1;
    v75 = 0;
    v76 = 0;
    if ( (unsigned __int8)operator==(*(_QWORD *)&v79.Data1, &v75) )
    {
      v90 = 0;
      v89 = 0;
      if ( !v17 )
      {
        *(_QWORD *)((char *)&v89 + 4) = v19 | 0x100000000LL;
        if ( !(unsigned __int8)utl::vector<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::push_back(
                                 a6,
                                 &v89) )
        {
          v21 = 210;
          AppInstanceId = -2147024882;
LABEL_11:
          v22 = 0;
          v23 = AppInstanceId;
LABEL_15:
          Log_HREvent(
            v23,
            v22,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
            v21);
LABEL_79:
          Udm::FreeUdmPropVal((Udm *)&v89, v25);
LABEL_112:
          utl::vector<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::_Uninit(v80);
          return AppInstanceId;
        }
        v17 = (struct UdmPropertyValue *)(*(_QWORD *)(a6 + 8) - 24LL);
      }
      v24 = UdmPropToJetSetColumn(a1, v17, a5);
      AppInstanceId = v24;
      if ( v24 < 0 )
      {
        v21 = 216;
        v22 = 1;
        v23 = (unsigned int)v24;
        goto LABEL_15;
      }
      v26 = *(unsigned __int16 **)&pclsid.Data1;
      if ( *((_DWORD *)v17 + 2) == 1 && (!*(_QWORD *)&pclsid.Data1 || !**(_WORD **)&pclsid.Data1) )
      {
        v21 = 221;
        AppInstanceId = -2147024846;
        goto LABEL_11;
      }
      v82 = 0;
      v81 = 0;
      if ( !v16 )
      {
        if ( *((_DWORD *)v17 + 2) != 1 )
        {
          v27 = 228;
          AppInstanceId = -2147024809;
LABEL_23:
          v28 = 0;
          v29 = AppInstanceId;
LABEL_24:
          Log_HREvent(
            v29,
            v28,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
            v27);
LABEL_78:
          Udm::FreeUdmPropVal((Udm *)&v81, v30);
          v82 = 0;
          v81 = 0;
          goto LABEL_79;
        }
        DWORD1(v81) = 1638405;
        v31 = DupString((char *)&v81 + 8, *(_QWORD *)&pclsid.Data1);
        AppInstanceId = v31;
        if ( v31 < 0 )
        {
          v27 = 231;
LABEL_27:
          v28 = 1;
          v29 = (unsigned int)v31;
          goto LABEL_24;
        }
        if ( !(unsigned __int8)utl::vector<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::push_back(
                                 a6,
                                 &v81) )
        {
          v27 = 233;
          AppInstanceId = -2147024882;
          goto LABEL_23;
        }
        v16 = *(_QWORD *)(a6 + 8) - 24LL;
      }
      v31 = UdmPropToJetSetColumn(a1, v16, v77);
      AppInstanceId = v31;
      if ( v31 < 0 )
      {
        v27 = 239;
        goto LABEL_27;
      }
      *(_OWORD *)v83 = 0;
      HIDWORD(v83[0]) = 1966085;
      v84 = 0;
      v32 = *((_DWORD *)v17 + 2);
      if ( v32 )
      {
        if ( v32 != 1 )
        {
          v33 = 305;
          AppInstanceId = -2147024809;
LABEL_36:
          v34 = 0;
          v35 = AppInstanceId;
LABEL_37:
          Log_HREvent(
            v35,
            v34,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
            v33);
LABEL_77:
          Udm::FreeUdmPropVal((Udm *)v83, v36);
          v84 = 0;
          *(_OWORD *)v83 = 0;
          goto LABEL_78;
        }
        v37 = v26;
        do
        {
          v38 = *(unsigned __int16 *)((char *)v37 + *(_QWORD *)(v16 + 8) - (_QWORD)v26);
          v39 = *v37 - v38;
          if ( v39 )
            break;
          ++v37;
        }
        while ( v38 );
        if ( v39 )
        {
          v33 = 249;
          AppInstanceId = -2147024891;
          goto LABEL_36;
        }
        v75 = 0;
        v40 = tlx::replace<UdmPropertyValue,&void _MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>(&v75);
        AppDisplayName = GetAppDisplayName(*(PCWSTR *)(v16 + 8), (__int64)v40);
        AppInstanceId = AppDisplayName;
        if ( AppDisplayName == -2147023728 )
        {
          AppDisplayName = DupString(&v83[1], v26);
          AppInstanceId = AppDisplayName;
          if ( AppDisplayName < 0 )
          {
            v42 = 255;
LABEL_46:
            v43 = 1;
            v44 = (unsigned int)AppDisplayName;
LABEL_47:
            Log_HREvent(
              v44,
              v43,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
              v42);
            auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v75);
            goto LABEL_77;
          }
        }
        else
        {
          if ( AppDisplayName < 0 )
          {
            v42 = 259;
            goto LABEL_46;
          }
          AppDisplayName = DupString(&v83[1], v75);
          AppInstanceId = AppDisplayName;
          if ( AppDisplayName < 0 )
          {
            v42 = 260;
            goto LABEL_46;
          }
        }
        *(_QWORD *)v79.Data4 = *(_QWORD *)pclsid.Data4;
        *(_QWORD *)&v79.Data1 = 0;
        *(_QWORD *)v86 = 0;
        pclsid = v79;
        v45 = utl::vector<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::push_back(
                a6,
                &pclsid);
        Udm::FreeUdmPropVal((Udm *)&pclsid, v46);
        if ( !v45 )
        {
          v42 = 266;
LABEL_54:
          AppInstanceId = -2147024882;
          v43 = 0;
          v44 = 2147942414LL;
          goto LABEL_47;
        }
        v47 = a1[255];
        *(_DWORD *)&pclsid.Data2 = 0;
        *(_QWORD *)&v86[4] = 0;
        v88 = 0;
        v78 = 0;
        Column = DatabaseVolumeSession::FindColumnEx(v47, (const struct ColumnDefinition *)&off_180130EA0, &v78);
        if ( !v78 )
          Log_AssertionEvent_2(
            v48,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
            203);
        *(_QWORD *)pclsid.Data4 = *(_QWORD *)(a6 + 8) - 16LL;
        pclsid.Data1 = Column;
        *(_DWORD *)v86 = 8;
        v87 = 1;
        if ( !(unsigned __int8)utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>>::_PushBackOne<JET_SETCOLUMN const &>(
                                 v77,
                                 &pclsid) )
        {
          v42 = 274;
          goto LABEL_54;
        }
        auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v75);
        goto LABEL_69;
      }
      v75 = 0;
      ATL::CComPtr<ServiceDataSession>::operator=(&v75, a1);
      v50 = CallHistoryOperationContext::ValidateCallerSecurity(&v75, 2, 0, 1);
      AppInstanceId = v50;
      if ( v50 >= 0 )
      {
        v53 = *(const wchar_t **)(v16 + 8);
        pclsid = GUID_NULL;
        if ( v53 && *v53 == 123 && wcscpy_s(Destination, 0x27u, v53) >= 0 && CLSIDFromString(Destination, &pclsid) >= 0 )
        {
          v79 = pclsid;
          if ( (int)GetPhoneLineName(&v79, &v83[1]) >= 0 )
          {
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v75);
LABEL_69:
            v55 = UdmPropToJetSetColumn(a1, v83, v77);
            AppInstanceId = v55;
            if ( v55 < 0 )
            {
              v33 = 311;
              v34 = 1;
              v35 = (unsigned int)v55;
              goto LABEL_37;
            }
            if ( !(unsigned __int8)utl::vector<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::push_back(
                                     a6,
                                     v83) )
            {
              v33 = 313;
              AppInstanceId = -2147024882;
              goto LABEL_36;
            }
            Udm::FreeUdmPropVal((Udm *)v83, v56);
            *(_OWORD *)v83 = 0;
            v84 = 0;
            Udm::FreeUdmPropVal((Udm *)&v81, v57);
            v81 = 0;
            v82 = 0;
            Udm::FreeUdmPropVal((Udm *)&v89, v58);
LABEL_107:
            AppInstanceId = 0;
            goto LABEL_112;
          }
          AppInstanceId = -2147024809;
          v51 = 299;
          v52 = 2147942487LL;
          v54 = 0;
LABEL_76:
          Log_HREvent(
            v52,
            v54,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
            v51);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v75);
          goto LABEL_77;
        }
        AppInstanceId = -2147024809;
        v51 = 295;
        v52 = 2147942487LL;
      }
      else
      {
        v51 = 283;
        v52 = (unsigned int)v50;
      }
      v54 = 1;
      goto LABEL_76;
    }
    v79.Data1 = v19;
    v78 = 0;
    v77 = 0;
    *(_DWORD *)&v79.Data2 = v20;
    v59 = tlx::replace<_USRestriction,&void _LocalFreer<_USRestriction>(_USRestriction *)>((void **)&v77);
    v60 = PropertyMapper_CallHistory(
            (struct CallHistoryDataSession *)a1,
            v18,
            2u,
            &v79.Data1,
            &v78,
            (struct UdmPropertyValue **)v59);
    AppInstanceId = v60;
    if ( v60 < 0 )
    {
      v61 = 326;
      v62 = 1;
      v63 = (unsigned int)v60;
LABEL_110:
      Log_HREvent(
        v63,
        v62,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
        v61);
      goto LABEL_111;
    }
    if ( !v78 )
    {
      Log_HREvent(
        2147943568LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
        328);
      auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v77);
      AppInstanceId = -2147023728;
      goto LABEL_112;
    }
    v64 = v77;
    if ( (v77[3] & 0x100) != 0 )
      v65 = 0;
    else
      v65 = v77[4];
    if ( *((_DWORD *)v77 + 2) == 1 )
    {
      if ( !v65 )
        goto LABEL_108;
      v67 = *(unsigned __int16 **)&pclsid.Data1;
      do
      {
        v68 = *(unsigned __int16 *)((char *)v67 + v65 - *(_QWORD *)&pclsid.Data1);
        v69 = *v67 - v68;
        if ( v69 )
          break;
        ++v67;
      }
      while ( v68 );
      if ( v69 )
      {
LABEL_108:
        v61 = 339;
LABEL_109:
        AppInstanceId = -2147024891;
        v62 = 0;
        v63 = 2147942405LL;
        goto LABEL_110;
      }
    }
    else
    {
      v75 = 0;
      ATL::CComPtr<ServiceDataSession>::operator=(&v75, a1);
      v66 = CallHistoryOperationContext::ValidateCallerSecurity(&v75, 2, 0, 1);
      AppInstanceId = v66;
      if ( v66 < 0 )
      {
        Log_HREvent(
          (unsigned int)v66,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
          346);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v75);
LABEL_111:
        auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v77);
        goto LABEL_112;
      }
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v75);
      v64 = v77;
    }
    if ( !v17 || *((_DWORD *)v17 + 2) == *((_DWORD *)v64 + 2) )
    {
      if ( !v16 )
        goto LABEL_106;
      if ( v65 )
      {
        v70 = *(unsigned __int16 **)(v16 + 8);
        v71 = v65 - (_QWORD)v70;
        do
        {
          v72 = *(unsigned __int16 *)((char *)v70 + v71);
          v73 = *v70 - v72;
          if ( v73 )
            break;
          ++v70;
        }
        while ( v72 );
        if ( !v73 )
        {
LABEL_106:
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v77);
          goto LABEL_107;
        }
      }
      v61 = 361;
    }
    else
    {
      v61 = 354;
    }
    goto LABEL_109;
  }
  v10 = 191;
  v11 = 1;
LABEL_3:
  Log_HREvent(
    AppInstanceId,
    v11,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
    v10);
  return AppInstanceId;
}

```

## disassembly

```asm
0x1800d8c34  push    rbp
0x1800d8c36  push    rbx
0x1800d8c37  push    rsi
0x1800d8c38  push    rdi
0x1800d8c39  push    r12
0x1800d8c3b  push    r13
0x1800d8c3d  push    r14
0x1800d8c3f  push    r15
0x1800d8c41  lea     rbp, [rsp-78h]
0x1800d8c46  sub     rsp, 178h
0x1800d8c4d  mov     rax, cs:__security_cookie
0x1800d8c54  xor     rax, rsp
0x1800d8c57  mov     [rbp+0B0h+var_50], rax
0x1800d8c5b  mov     r15, [rbp+0B0h+arg_20]
0x1800d8c62  xorps   xmm0, xmm0
0x1800d8c65  mov     r13, [rbp+0B0h+arg_28]
0x1800d8c6c  mov     rdi, r9
0x1800d8c6f  mov     qword ptr [rsp+1B0h+var_160.Data1], rdx
0x1800d8c74  mov     r12, rcx
0x1800d8c77  lea     rdx, [rbp+0B0h+pclsid]; struct AppInstanceId *
0x1800d8c7b  mov     [rsp+1B0h+var_170], r15
0x1800d8c80  movups  xmmword ptr [rbp+0B0h+pclsid.Data1], xmm0
0x1800d8c84  mov     esi, r8d
0x1800d8c87  call    ?GetAppInstanceId@ServiceDataSession@@QEAAJPEAUAppInstanceId@@@Z; ServiceDataSession::GetAppInstanceId(AppInstanceId *)
0x1800d8c8c  xor     r10d, r10d
0x1800d8c8f  mov     ebx, eax
0x1800d8c91  test    eax, eax
0x1800d8c93  jns     short loc_1800D8CB2
0x1800d8c95  mov     r9d, 0BFh
0x1800d8c9b  lea     edx, [r10+1]
0x1800d8c9f  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d8ca6  mov     ecx, ebx
0x1800d8ca8  call    Log_HREvent
0x1800d8cad  jmp     loc_1800D9390
0x1800d8cb2  mov     r11d, 190005h
0x1800d8cb8  mov     rcx, rsi; unsigned __int64
0x1800d8cbb  mov     r8d, r11d; unsigned int
0x1800d8cbe  mov     rdx, rdi; struct UdmPropertyValue *
0x1800d8cc1  call    ?FindPropByUdmPropId@@YAPEAUUdmPropertyValue@@_KPEAU1@K@Z; FindPropByUdmPropId(unsigned __int64,UdmPropertyValue *,ulong)
0x1800d8cc6  mov     rsi, rax
0x1800d8cc9  test    rax, rax
0x1800d8ccc  jz      short loc_1800D8CE3
0x1800d8cce  cmp     [rax+8], r10
0x1800d8cd2  jnz     short loc_1800D8CE3
0x1800d8cd4  mov     r9d, 0C3h
0x1800d8cda  xor     edx, edx
0x1800d8cdc  mov     ebx, 80070057h
0x1800d8ce1  jmp     short loc_1800D8C9F
0x1800d8ce3  mov     r8d, 240002h; unsigned int
0x1800d8ce9  call    ?FindPropByUdmPropId@@YAPEAUUdmPropertyValue@@_KPEAU1@K@Z; FindPropByUdmPropId(unsigned __int64,UdmPropertyValue *,ulong)
0x1800d8cee  lea     rcx, [rsp+1B0h+var_140]
0x1800d8cf3  mov     r14, rax
0x1800d8cf6  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800d8cfb  mov     rbx, qword ptr [rsp+1B0h+var_160.Data1]
0x1800d8d00  lea     rdx, [rsp+1B0h+var_180]
0x1800d8d05  xor     ecx, ecx
0x1800d8d07  mov     [rsp+1B0h+var_180], rcx
0x1800d8d0c  mov     [rsp+1B0h+var_178], ecx
0x1800d8d10  mov     rcx, rbx
0x1800d8d13  call    ??8@YA_NAEBUUdmObjectId@@0@Z; operator==(UdmObjectId const &,UdmObjectId const &)
0x1800d8d18  test    al, al
0x1800d8d1a  jz      loc_1800D91CB
0x1800d8d20  xor     eax, eax
0x1800d8d22  xorps   xmm0, xmm0
0x1800d8d25  mov     [rbp+0B0h+var_B0], rax
0x1800d8d29  movups  [rbp+0B0h+var_C0], xmm0
0x1800d8d2d  lea     edi, [rax+1]
0x1800d8d30  test    r14, r14
0x1800d8d33  jnz     short loc_1800D8D65
0x1800d8d35  lea     rdx, [rbp+0B0h+var_C0]
0x1800d8d39  mov     dword ptr [rbp+0B0h+var_C0+4], r8d
0x1800d8d3d  mov     rcx, r13
0x1800d8d40  mov     dword ptr [rbp+0B0h+var_C0+8], edi
0x1800d8d43  call    ?push_back@?$vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@utl@@@utl@@QEAA_N$$QEAU?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@Z; utl::vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::push_back(auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)> &&)
0x1800d8d48  test    al, al
0x1800d8d4a  jnz     short loc_1800D8D5D
0x1800d8d4c  mov     r9d, 0D2h
0x1800d8d52  mov     ebx, 8007000Eh
0x1800d8d57  xor     edx, edx
0x1800d8d59  mov     ecx, ebx
0x1800d8d5b  jmp     short loc_1800D8D85
0x1800d8d5d  mov     r14, [r13+8]
0x1800d8d61  sub     r14, 18h
0x1800d8d65  mov     r8, r15
0x1800d8d68  mov     rdx, r14
0x1800d8d6b  mov     rcx, r12
0x1800d8d6e  call    ?UdmPropToJetSetColumn@@YAJPEAVCallHistoryDataSession@@PEBUUdmPropertyValue@@PEAV?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@@Z; UdmPropToJetSetColumn(CallHistoryDataSession *,UdmPropertyValue const *,utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>> *)
0x1800d8d73  xor     ecx, ecx
0x1800d8d75  mov     ebx, eax
0x1800d8d77  test    eax, eax
0x1800d8d79  jns     short loc_1800D8D96
0x1800d8d7b  mov     r9d, 0D8h
0x1800d8d81  mov     edx, edi
0x1800d8d83  mov     ecx, eax
0x1800d8d85  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d8d8c  call    Log_HREvent
0x1800d8d91  jmp     loc_1800D91BD
0x1800d8d96  mov     r15, qword ptr [rbp+0B0h+pclsid.Data1]
0x1800d8d9a  cmp     [r14+8], edi
0x1800d8d9e  jnz     short loc_1800D8DB8
0x1800d8da0  test    r15, r15
0x1800d8da3  jz      short loc_1800D8DAB
0x1800d8da5  cmp     [r15], cx
0x1800d8da9  jnz     short loc_1800D8DB8
0x1800d8dab  mov     r9d, 0DDh
0x1800d8db1  mov     ebx, 80070032h
0x1800d8db6  jmp     short loc_1800D8D57
0x1800d8db8  xor     eax, eax
0x1800d8dba  xorps   xmm0, xmm0
0x1800d8dbd  mov     [rbp+0B0h+var_118], rax
0x1800d8dc1  movups  [rbp+0B0h+var_128], xmm0
0x1800d8dc5  test    rsi, rsi
0x1800d8dc8  jnz     short loc_1800D8E3B
0x1800d8dca  cmp     [r14+8], edi
0x1800d8dce  jz      short loc_1800D8DF0
0x1800d8dd0  mov     r9d, 0E4h
0x1800d8dd6  mov     ebx, 80070057h
0x1800d8ddb  xor     edx, edx
0x1800d8ddd  mov     ecx, ebx
0x1800d8ddf  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d8de6  call    Log_HREvent
0x1800d8deb  jmp     loc_1800D91A7
0x1800d8df0  mov     rdx, r15
0x1800d8df3  mov     dword ptr [rbp+0B0h+var_128+4], 190005h
0x1800d8dfa  lea     rcx, [rbp+0B0h+var_128+8]
0x1800d8dfe  call    cs:__imp_DupString
0x1800d8e04  mov     ebx, eax
0x1800d8e06  test    eax, eax
0x1800d8e08  jns     short loc_1800D8E16
0x1800d8e0a  mov     r9d, 0E7h
0x1800d8e10  mov     edx, edi
0x1800d8e12  mov     ecx, eax
0x1800d8e14  jmp     short loc_1800D8DDF
0x1800d8e16  lea     rdx, [rbp+0B0h+var_128]
0x1800d8e1a  mov     rcx, r13
0x1800d8e1d  call    ?push_back@?$vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@utl@@@utl@@QEAA_N$$QEAU?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@Z; utl::vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::push_back(auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)> &&)
0x1800d8e22  test    al, al
0x1800d8e24  jnz     short loc_1800D8E33
0x1800d8e26  mov     r9d, 0E9h
0x1800d8e2c  mov     ebx, 8007000Eh
0x1800d8e31  jmp     short loc_1800D8DDB
0x1800d8e33  mov     rsi, [r13+8]
0x1800d8e37  sub     rsi, 18h
0x1800d8e3b  mov     r8, [rsp+1B0h+var_170]
0x1800d8e40  mov     rdx, rsi
0x1800d8e43  mov     rcx, r12
0x1800d8e46  call    ?UdmPropToJetSetColumn@@YAJPEAVCallHistoryDataSession@@PEBUUdmPropertyValue@@PEAV?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@@Z; UdmPropToJetSetColumn(CallHistoryDataSession *,UdmPropertyValue const *,utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>> *)
0x1800d8e4b  mov     ebx, eax
0x1800d8e4d  test    eax, eax
0x1800d8e4f  jns     short loc_1800D8E59
0x1800d8e51  mov     r9d, 0EFh
0x1800d8e57  jmp     short loc_1800D8E10
0x1800d8e59  xor     eax, eax
0x1800d8e5b  xorps   xmm0, xmm0
0x1800d8e5e  movups  xmmword ptr [rbp+0B0h+var_110], xmm0
0x1800d8e62  mov     dword ptr [rbp+0B0h+var_110+4], 1E0005h
0x1800d8e69  mov     [rbp+0B0h+var_100], rax
0x1800d8e6d  mov     ecx, [r14+8]
0x1800d8e71  xor     r14d, r14d
0x1800d8e74  test    ecx, ecx
0x1800d8e76  jz      loc_1800D9028
0x1800d8e7c  cmp     ecx, edi
0x1800d8e7e  jz      short loc_1800D8EA0
0x1800d8e80  mov     r9d, 131h
0x1800d8e86  mov     ebx, 80070057h
0x1800d8e8b  xor     edx, edx
0x1800d8e8d  mov     ecx, ebx
0x1800d8e8f  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d8e96  call    Log_HREvent
0x1800d8e9b  jmp     loc_1800D9191
0x1800d8ea0  mov     r8, [rsi+8]
0x1800d8ea4  mov     rax, r15
0x1800d8ea7  sub     r8, r15
0x1800d8eaa  movzx   ecx, word ptr [rax]
0x1800d8ead  movzx   edx, word ptr [rax+r8]
0x1800d8eb2  sub     ecx, edx
0x1800d8eb4  jnz     short loc_1800D8EBE
0x1800d8eb6  add     rax, 2
0x1800d8eba  test    edx, edx
0x1800d8ebc  jnz     short loc_1800D8EAA
0x1800d8ebe  test    ecx, ecx
0x1800d8ec0  jz      short loc_1800D8ECF
0x1800d8ec2  mov     r9d, 0F9h
0x1800d8ec8  mov     ebx, 80070005h
0x1800d8ecd  jmp     short loc_1800D8E8B
0x1800d8ecf  lea     rcx, [rsp+1B0h+var_180]
0x1800d8ed4  mov     [rsp+1B0h+var_180], r14
0x1800d8ed9  call    ??$replace@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAUUdmPropertyValue@@AEAV?$auto_ptr@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>(tlx::auto_ptr<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)> &)
0x1800d8ede  mov     rcx, [rsi+8]; sourceString
0x1800d8ee2  mov     rdx, rax
0x1800d8ee5  call    GetAppDisplayName
0x1800d8eea  mov     ebx, eax
0x1800d8eec  cmp     eax, 80070490h
0x1800d8ef1  jnz     short loc_1800D8F2B
0x1800d8ef3  mov     rdx, r15
0x1800d8ef6  lea     rcx, [rbp+0B0h+var_110+8]
0x1800d8efa  call    cs:__imp_DupString
0x1800d8f00  mov     ebx, eax
0x1800d8f02  test    eax, eax
0x1800d8f04  jns     short loc_1800D8F54
0x1800d8f06  mov     r9d, 0FFh
0x1800d8f0c  mov     edx, edi
0x1800d8f0e  mov     ecx, eax
0x1800d8f10  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d8f17  call    Log_HREvent
0x1800d8f1c  lea     rcx, [rsp+1B0h+var_180]
0x1800d8f21  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800d8f26  jmp     loc_1800D9191
0x1800d8f2b  test    eax, eax
0x1800d8f2d  jns     short loc_1800D8F37
0x1800d8f2f  mov     r9d, 103h
0x1800d8f35  jmp     short loc_1800D8F0C
0x1800d8f37  mov     rdx, [rsp+1B0h+var_180]
0x1800d8f3c  lea     rcx, [rbp+0B0h+var_110+8]
0x1800d8f40  call    cs:__imp_DupString
0x1800d8f46  mov     ebx, eax
0x1800d8f48  test    eax, eax
0x1800d8f4a  jns     short loc_1800D8F54
0x1800d8f4c  mov     r9d, 104h
0x1800d8f52  jmp     short loc_1800D8F0C
0x1800d8f54  mov     rax, qword ptr [rbp+0B0h+pclsid.Data4]
0x1800d8f58  lea     rdx, [rbp+0B0h+pclsid]
0x1800d8f5c  mov     qword ptr [rsp+1B0h+var_160.Data4], rax
0x1800d8f61  mov     rcx, r13
0x1800d8f64  mov     qword ptr [rsp+1B0h+var_160.Data1], r14
0x1800d8f69  movups  xmm0, xmmword ptr [rsp+1B0h+var_160.Data1]
0x1800d8f6e  mov     qword ptr [rbp+0B0h+var_E0], r14
0x1800d8f72  movups  xmmword ptr [rbp+0B0h+pclsid.Data1], xmm0
0x1800d8f76  call    ?push_back@?$vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@utl@@@utl@@QEAA_N$$QEAU?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@Z; utl::vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::push_back(auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)> &&)
0x1800d8f7b  lea     rcx, [rbp+0B0h+pclsid]; this
0x1800d8f7f  mov     bl, al
0x1800d8f81  call    ?FreeUdmPropVal@Udm@@YAXPEAUUdmPropertyValue@@@Z; Udm::FreeUdmPropVal(UdmPropertyValue *)
0x1800d8f86  test    bl, bl
0x1800d8f88  jnz     short loc_1800D8F9E
0x1800d8f8a  mov     r9d, 10Ah
0x1800d8f90  mov     ebx, 8007000Eh
0x1800d8f95  xor     edx, edx
0x1800d8f97  mov     ecx, ebx
0x1800d8f99  jmp     loc_1800D8F10
0x1800d8f9e  mov     rcx, [r12+7F8h]; this
0x1800d8fa6  lea     r8, [rsp+1B0h+var_168]; int *
0x1800d8fab  lea     rdx, off_180130EA0; struct ColumnDefinition *
0x1800d8fb2  mov     dword ptr [rbp+0B0h+pclsid.Data2], r14d
0x1800d8fb6  mov     qword ptr [rbp+0B0h+var_E0+4], r14
0x1800d8fba  mov     [rbp+0B0h+var_D0], r14
0x1800d8fbe  mov     [rsp+1B0h+var_168], r14d
0x1800d8fc3  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x1800d8fc8  mov     ebx, eax
0x1800d8fca  cmp     [rsp+1B0h+var_168], r14d
0x1800d8fcf  jnz     short loc_1800D8FE3
0x1800d8fd1  mov     r8d, 0CBh
0x1800d8fd7  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d8fde  call    Log_AssertionEvent_2
0x1800d8fe3  mov     rax, [r13+8]
0x1800d8fe7  lea     rdx, [rbp+0B0h+pclsid]
0x1800d8feb  mov     rcx, [rsp+1B0h+var_170]
0x1800d8ff0  sub     rax, 10h
0x1800d8ff4  mov     qword ptr [rbp+0B0h+pclsid.Data4], rax
0x1800d8ff8  mov     [rbp+0B0h+pclsid.Data1], ebx
0x1800d8ffb  mov     dword ptr [rbp+0B0h+var_E0], 8
0x1800d9002  mov     [rbp+0B0h+var_D4], edi
0x1800d9005  call    ??$_PushBackOne@AEBUJET_SETCOLUMN@@@?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@AEAA_NAEBUJET_SETCOLUMN@@@Z; utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>>::_PushBackOne<JET_SETCOLUMN const &>(JET_SETCOLUMN const &)
0x1800d900a  test    al, al
0x1800d900c  jnz     short loc_1800D9019
0x1800d900e  mov     r9d, 112h
0x1800d9014  jmp     loc_1800D8F90
0x1800d9019  lea     rcx, [rsp+1B0h+var_180]
0x1800d901e  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800d9023  jmp     loc_1800D90EC
0x1800d9028  mov     rdx, r12
0x1800d902b  mov     [rsp+1B0h+var_180], r14
0x1800d9030  lea     rcx, [rsp+1B0h+var_180]
0x1800d9035  call    ??4?$CComPtr@VServiceDataSession@@@ATL@@QEAAPEAVServiceDataSession@@PEAV2@@Z; ATL::CComPtr<ServiceDataSession>::operator=(ServiceDataSession *)
0x1800d903a  xor     r8d, r8d
0x1800d903d  lea     rcx, [rsp+1B0h+var_180]
0x1800d9042  mov     r9d, edi
0x1800d9045  lea     edx, [r8+2]
0x1800d9049  call    ?ValidateCallerSecurity@CallHistoryOperationContext@@QEAAJW4UdmAccessLevel@@KH@Z; CallHistoryOperationContext::ValidateCallerSecurity(UdmAccessLevel,ulong,int)
0x1800d904e  mov     ebx, eax
0x1800d9050  test    eax, eax
0x1800d9052  jns     short loc_1800D9061
0x1800d9054  mov     r9d, 11Bh
0x1800d905a  mov     ecx, eax
0x1800d905c  jmp     loc_1800D9179
0x1800d9061  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800d9068  mov     r8, [rsi+8]; Source
0x1800d906c  movdqu  xmmword ptr [rbp+0B0h+pclsid.Data1], xmm0
0x1800d9071  test    r8, r8
0x1800d9074  jz      loc_1800D916C
0x1800d907a  cmp     word ptr [r8], 7Bh ; '{'
0x1800d907f  jnz     loc_1800D916C
0x1800d9085  mov     edx, 27h ; '''; SizeInWords
0x1800d908a  lea     rcx, [rbp+0B0h+Destination]; Destination
0x1800d908e  call    cs:__imp_wcscpy_s
0x1800d9094  test    eax, eax
0x1800d9096  js      loc_1800D916C
0x1800d909c  lea     rdx, [rbp+0B0h+pclsid]; pclsid
0x1800d90a0  lea     rcx, [rbp+0B0h+Destination]; lpsz
0x1800d90a4  call    cs:__imp_CLSIDFromString
0x1800d90aa  test    eax, eax
  ... truncated ...
```
