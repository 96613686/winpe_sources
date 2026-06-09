# Subscription::SetPropW(_EC_SUBSCRIPTION_PROPERTY_ID,_EC_VARIANT * const)

- ea: `0x180007aa0`
- end: `0x180009085`
- name: `?SetPropW@Subscription@@QEAAKW4_EC_SUBSCRIPTION_PROPERTY_ID@@QEAU_EC_VARIANT@@@Z`
- size: `5605`
- prototype: `__int64 __fastcall(Subscription *this, signed int, struct _EC_VARIANT *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005b90`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x180007aa0`
- `0x18000a820`
- `0x18000acec`
- `0x18000ad88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c35`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007d30`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007d30`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180007ec3`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180007ec3`

## string_xrefs

- `0x180009062`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
__int64 __fastcall Subscription::SetPropW(Subscription *this, signed int a2, struct _EC_VARIANT *const a3)
{
  __int64 v3; // rsi
  struct _ENUM_NAMEVALUE_PAIR near **v6; // rax
  const struct tag_EcRpcMetadataPropertyList *v7; // rcx
  const struct tag_EcRpcMetadataPropertyList *v8; // rcx
  struct _ENUM_NAMEVALUE_PAIR near **v9; // rax
  const struct tag_EcRpcMetadataPropertyList *v10; // rcx
  ULONGLONG DateTimeVal; // rax
  const struct tag_EcRpcMetadataPropertyList *v12; // rcx
  struct _ENUM_NAMEVALUE_PAIR near **v13; // rax
  struct _ENUM_NAMEVALUE_PAIR near **v14; // rax
  struct _ENUM_NAMEVALUE_PAIR near **v15; // rax
  unsigned int v16; // r8d
  __int64 v17; // rdx
  DWORD LastError; // ebx
  struct _EC_VARIANT v20; // [rsp+30h] [rbp-50h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-40h] BYREF
  FILETIME FileTime2; // [rsp+B0h] [rbp+30h] BYREF
  FILETIME FileTime1; // [rsp+C8h] [rbp+48h] BYREF

  v3 = a2;
  if ( (*((_BYTE *)this + 88) & 2) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 4317);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0x10DDu,
      "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
      168);
    throw (wmi::GenericException *)pExceptionObject;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0x57u,
      "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
      171);
    throw (wmi::GenericException *)pExceptionObject;
  }
  if ( a2 > 16 )
  {
    if ( a2 > 24 )
    {
      switch ( a2 )
      {
        case 25:
          if ( a3->Type >= 2 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              303);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        case 26:
          if ( (a3->Type & 0xFFFFFFFB) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              307);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        case 27:
          if ( a3->Type == 2 )
          {
            if ( !EnumNameValueSubscriptionType )
              goto LABEL_337;
            v15 = &EnumNameValueSubscriptionType;
            while ( *((_DWORD *)v15 + 2) != a3->BooleanVal )
            {
              v15 += 2;
              if ( !*v15 )
                goto LABEL_337;
            }
            if ( !*v15 )
            {
LABEL_337:
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
              }
              wmi::GenericException::GenericException(
                (wmi::GenericException *)pExceptionObject,
                0x57u,
                "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
                314);
              throw (wmi::GenericException *)pExceptionObject;
            }
          }
          else if ( a3->Type )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              311);
            throw (wmi::GenericException *)pExceptionObject;
          }
          if ( !*((_BYTE *)this + 104) )
          {
            FileTime2.dwLowDateTime = 0;
            v20 = 0;
            if ( !(unsigned int)SubscriptionWriteData::GetPropW(
                                  (Subscription *)((char *)this + 40),
                                  a2,
                                  0x10u,
                                  &v20,
                                  (unsigned int *)&FileTime2)
              && a3->BooleanVal != v20.BooleanVal )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
              }
              wmi::GenericException::GenericException(
                (wmi::GenericException *)pExceptionObject,
                0x57u,
                "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
                324);
              throw (wmi::GenericException *)pExceptionObject;
            }
          }
          break;
        case 28:
        case 29:
        case 30:
          if ( (a3->Type & 0x7F) != 4 && a3->Type )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              332);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        case 31:
          if ( (a3->Type & 0xFFFFFFFB) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              337);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        default:
          goto LABEL_317;
      }
    }
    else
    {
      switch ( a2 )
      {
        case 24:
          if ( (a3->Type & 0xFFFFFFFB) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              299);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        case 17:
          if ( a3->Type == 4 )
          {
            if ( a3->DateTimeVal && !LocaleNameToLCID(a3->StringVal, 0) )
            {
              LastError = GetLastError();
              if ( !LastError )
                LastError = 1287;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  39,
                  WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids,
                  LastError);
              }
              wmi::GenericException::GenericException(
                (wmi::GenericException *)pExceptionObject,
                LastError,
                "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
                265);
              throw (wmi::GenericException *)pExceptionObject;
            }
          }
          else if ( a3->Type )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              261);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        case 18:
          if ( a3->Type == 2 )
          {
            if ( !EnumNameValueContentFormat )
              goto LABEL_295;
            v14 = &EnumNameValueContentFormat;
            while ( *((_DWORD *)v14 + 2) != a3->BooleanVal )
            {
              v14 += 2;
              if ( !*v14 )
                goto LABEL_295;
            }
            if ( !*v14 )
            {
LABEL_295:
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
              }
              wmi::GenericException::GenericException(
                (wmi::GenericException *)pExceptionObject,
                0x57u,
                "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
                272);
              throw (wmi::GenericException *)pExceptionObject;
            }
          }
          else if ( a3->Type )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              269);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        case 19:
          if ( (a3->Type & 0xFFFFFFFB) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              276);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        case 20:
          if ( (a3->Type & 0xFFFFFFFB) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              295);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        case 21:
          if ( a3->Type == 2 )
          {
            if ( !EnumNameValueCredentialsType )
              goto LABEL_275;
            v13 = &EnumNameValueCredentialsType;
            while ( *((_DWORD *)v13 + 2) != a3->BooleanVal )
            {
              v13 += 2;
              if ( !*v13 )
                goto LABEL_275;
            }
            if ( !*v13 )
            {
LABEL_275:
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
              }
              wmi::GenericException::GenericException(
                (wmi::GenericException *)pExceptionObject,
                0x57u,
                "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
                283);
              throw (wmi::GenericException *)pExceptionObject;
            }
          }
          else if ( a3->Type )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              280);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        case 22:
          if ( (a3->Type & 0xFFFFFFFB) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              287);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
        default:
          if ( (a3->Type & 0xFFFFFFFB) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              291);
            throw (wmi::GenericException *)pExceptionObject;
          }
          break;
      }
    }
  }
  else if ( a2 == 16 )
  {
    if ( a3->Type == 2 )
    {
      v12 = (const struct tag_EcRpcMetadataPropertyList *)*((_QWORD *)this + 5);
      FileTime2.dwLowDateTime = 1;
      ReadMetadataProp(v12, a2, (unsigned int *)&FileTime2);
      if ( FileTime2.dwLowDateTime != 1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 50);
        }
        wmi::GenericException::GenericException(
          (wmi::GenericException *)pExceptionObject,
          0x32u,
          "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
          257);
        throw (wmi::GenericException *)pExceptionObject;
      }
    }
    else if ( a3->Type )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        254);
      throw (wmi::GenericException *)pExceptionObject;
    }
  }
  else if ( a2 > 8 )
  {
    switch ( a2 )
    {
      case 9:
        if ( a3->Type == 3 )
        {
          DateTimeVal = a3->DateTimeVal;
          FileTime2.dwLowDateTime = a3->DateTimeVal;
          FileTime2.dwHighDateTime = HIDWORD(DateTimeVal);
          FileTime1.dwLowDateTime = -1460463376;
          FileTime1.dwHighDateTime = 102863855;
          if ( CompareFileTime(&FileTime1, &FileTime2) == -1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              212);
            throw (wmi::GenericException *)pExceptionObject;
          }
        }
        else if ( a3->Type )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
          }
          wmi::GenericException::GenericException(
            (wmi::GenericException *)pExceptionObject,
            0x57u,
            "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
            203);
          throw (wmi::GenericException *)pExceptionObject;
        }
        break;
      case 10:
        if ( (a3->Type & 0xFFFFFFFB) != 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
          }
          wmi::GenericException::GenericException(
            (wmi::GenericException *)pExceptionObject,
            0x57u,
            "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
            218);
          throw (wmi::GenericException *)pExceptionObject;
        }
        break;
      case 11:
        if ( (a3->Type & 0xFFFFFFFB) != 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
          }
          wmi::GenericException::GenericException(
            (wmi::GenericException *)pExceptionObject,
            0x57u,
            "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
            222);
          throw (wmi::GenericException *)pExceptionObject;
        }
        break;
      case 12:
        if ( (a3->Type & 0xFFFFFFFD) != 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
          }
          wmi::GenericException::GenericException(
            (wmi::GenericException *)pExceptionObject,
            0x57u,
            "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
            226);
          throw (wmi::GenericException *)pExceptionObject;
        }
        break;
      case 13:
        if ( a3->Type == 2 )
        {
          if ( !EnumNameValueDeliveryMode )
            goto LABEL_215;
          v9 = &EnumNameValueDeliveryMode;
          while ( *((_DWORD *)v9 + 2) != a3->BooleanVal )
          {
            v9 += 2;
            if ( !*v9 )
              goto LABEL_215;
          }
          if ( !*v9 )
          {
LABEL_215:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x57u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              233);
            throw (wmi::GenericException *)pExceptionObject;
          }
          v10 = (const struct tag_EcRpcMetadataPropertyList *)*((_QWORD *)this + 5);
          FileTime2.dwLowDateTime = 1;
          ReadMetadataProp(v10, a2, (unsigned int *)&FileTime2);
          if ( FileTime2.dwLowDateTime != 1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 50);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x32u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              236);
            throw (wmi::GenericException *)pExceptionObject;
          }
        }
        else if ( a3->Type )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
          }
          wmi::GenericException::GenericException(
            (wmi::GenericException *)pExceptionObject,
            0x57u,
            "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
            230);
          throw (wmi::GenericException *)pExceptionObject;
        }
        break;
      case 14:
        if ( a3->Type == 2 )
        {
          v8 = (const struct tag_EcRpcMetadataPropertyList *)*((_QWORD *)this + 5);
          FileTime2.dwLowDateTime = 1;
          ReadMetadataProp(v8, a2, (unsigned int *)&FileTime2);
          if ( FileTime2.dwLowDateTime != 1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 50);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x32u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              243);
            throw (wmi::GenericException *)pExceptionObject;
          }
        }
        else if ( a3->Type )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
          }
          wmi::GenericException::GenericException(
            (wmi::GenericException *)pExceptionObject,
            0x57u,
            "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
            240);
          throw (wmi::GenericException *)pExceptionObject;
        }
        break;
      default:
        if ( a3->Type == 2 )
        {
          v7 = (const struct tag_EcRpcMetadataPropertyList *)*((_QWORD *)this + 5);
          FileTime2.dwLowDateTime = 1;
          ReadMetadataProp(v7, a2, (unsigned int *)&FileTime2);
          if ( FileTime2.dwLowDateTime != 1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 50);
            }
            wmi::GenericException::GenericException(
              (wmi::GenericException *)pExceptionObject,
              0x32u,
              "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
              250);
            throw (wmi::GenericException *)pExceptionObject;
          }
        }
        else if ( a3->Type )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
          }
          wmi::GenericException::GenericException(
            (wmi::GenericException *)pExceptionObject,
            0x57u,
            "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
            247);
          throw (wmi::GenericException *)pExceptionObject;
        }
        break;
    }
  }
  else if ( a2 == 8 )
  {
    if ( a3->Type == 2 )
    {
      if ( !EnumNameValueConfigurationMode )
        goto LABEL_185;
      v6 = &EnumNameValueConfigurationMode;
      while ( *((_DWORD *)v6 + 2) != a3->BooleanVal )
      {
        v6 += 2;
        if ( !*v6 )
          goto LABEL_185;
      }
      if ( !*v6 )
      {
LABEL_185:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
        }
        wmi::GenericException::GenericException(
          (wmi::GenericException *)pExceptionObject,
          0x57u,
          "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
          199);
        throw (wmi::GenericException *)pExceptionObject;
      }
    }
    else if ( a3->Type )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        196);
      throw (wmi::GenericException *)pExceptionObject;
    }
  }
  else if ( a2 )
  {
    if ( a2 == 1 || a2 == 2 || a2 == 3 || a2 == 4 || a2 == 5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        185);
      throw (wmi::GenericException *)pExceptionObject;
    }
    if ( a2 != 6 )
    {
      if ( a2 == 7 )
      {
        if ( (a3->Type & 0xFFFFFFFB) != 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
          }
          wmi::GenericException::GenericException(
            (wmi::GenericException *)pExceptionObject,
            0x57u,
            "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
            192);
          throw (wmi::GenericException *)pExceptionObject;
        }
        goto LABEL_146;
      }
LABEL_317:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        340);
      throw (wmi::GenericException *)pExceptionObject;
    }
    if ( (a3->Type & 0xFFFFFFFB) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        188);
      throw (wmi::GenericException *)pExceptionObject;
    }
  }
  else if ( a3->Type >= 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 87);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0x57u,
      "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
      178);
    throw (wmi::GenericException *)pExceptionObject;
  }
LABEL_146:
  v16 = SubscriptionWriteData::SetPropW((Subscription *)((char *)this + 40), (enum _EC_SUBSCRIPTION_PROPERTY_ID)v3, a3);
  if ( !v16 )
  {
    v17 = *((_QWORD *)this + 5);
    if ( (unsigned int)v3 >= *(_DWORD *)v17 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp",
        1221);
      throw (wmi::GenericException *)pExceptionObject;
    }
    *(_DWORD *)(*(_QWORD *)(v17 + 8) + 24 * v3 + 4) |= 1u;
  }
  return v16;
}

```

## disassembly

```asm
0x180007aa0  mov     [rsp-28h+arg_8], rbx
0x180007aa5  mov     [rsp-28h+arg_10], rsi
0x180007aaa  push    rbp
0x180007aab  push    rdi
0x180007aac  push    r12
0x180007aae  push    r14
0x180007ab0  push    r15
0x180007ab2  mov     rbp, rsp
0x180007ab5  sub     rsp, 80h
0x180007abc  mov     r15d, 2
0x180007ac2  movsxd  rsi, edx
0x180007ac5  mov     rbx, r8
0x180007ac8  mov     r14, rcx
0x180007acb  test    [rcx+58h], r15b
0x180007acf  jz      loc_180008030
0x180007ad5  xor     r12d, r12d
0x180007ad8  test    rbx, rbx
0x180007adb  jz      loc_180008098
0x180007ae1  lea     edi, [r15-1]
0x180007ae5  cmp     esi, 10h
0x180007ae8  jg      loc_180007D77
0x180007aee  jz      loc_180007D44
0x180007af4  cmp     esi, 8
0x180007af7  jg      loc_180007BBB
0x180007afd  jz      short loc_180007B6E
0x180007aff  mov     ecx, esi
0x180007b01  test    edx, edx
0x180007b03  jz      short loc_180007B5F
0x180007b05  sub     ecx, edi
0x180007b07  jz      loc_1800081C4
0x180007b0d  sub     ecx, edi
0x180007b0f  jz      loc_1800081C4
0x180007b15  sub     ecx, edi
0x180007b17  jz      loc_1800081C4
0x180007b1d  sub     ecx, edi
0x180007b1f  jz      loc_1800081C4
0x180007b25  sub     ecx, edi
0x180007b27  jz      loc_1800081C4
0x180007b2d  sub     ecx, edi
0x180007b2f  jz      short loc_180007B4C
0x180007b31  cmp     ecx, edi
0x180007b33  jnz     loc_180008D0A
0x180007b39  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007b41  jnz     loc_1800080FE
0x180007b47  jmp     loc_180007FE4
0x180007b4c  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007b54  jnz     loc_180008161
0x180007b5a  jmp     loc_180007FE4
0x180007b5f  cmp     [r8+0Ch], r15d
0x180007b63  jnb     loc_180008227
0x180007b69  jmp     loc_180007FE4
0x180007b6e  cmp     [r8+0Ch], r15d
0x180007b72  jz      short loc_180007B83
0x180007b74  cmp     [r8+0Ch], r12d
0x180007b78  jnz     loc_18000828A
0x180007b7e  jmp     loc_180007FE4
0x180007b83  cmp     cs:?EnumNameValueConfigurationMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A, r12; _ENUM_NAMEVALUE_PAIR near * EnumNameValueConfigurationMode
0x180007b8a  jz      loc_1800082ED
0x180007b90  mov     ecx, [r8]
0x180007b93  lea     rax, ?EnumNameValueConfigurationMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; _ENUM_NAMEVALUE_PAIR near * EnumNameValueConfigurationMode
0x180007b9a  cmp     [rax+8], ecx
0x180007b9d  jz      short loc_180007BAD
0x180007b9f  add     rax, 10h
0x180007ba3  cmp     [rax], r12
0x180007ba6  jnz     short loc_180007B9A
0x180007ba8  jmp     loc_1800082ED
0x180007bad  cmp     [rax], r12
0x180007bb0  jz      loc_1800082ED
0x180007bb6  jmp     loc_180007FE4
0x180007bbb  mov     ecx, esi
0x180007bbd  sub     ecx, 9
0x180007bc0  jz      loc_180007CF4
0x180007bc6  sub     ecx, edi
0x180007bc8  jz      loc_180007CE1
0x180007bce  sub     ecx, edi
0x180007bd0  jz      loc_180007CCE
0x180007bd6  sub     ecx, edi
0x180007bd8  jz      loc_180007CBB
0x180007bde  sub     ecx, edi
0x180007be0  jz      short loc_180007C54
0x180007be2  sub     ecx, edi
0x180007be4  jz      short loc_180007C21
0x180007be6  cmp     ecx, edi
0x180007be8  jnz     loc_180008D0A
0x180007bee  cmp     [r8+0Ch], r15d
0x180007bf2  jz      short loc_180007C03
0x180007bf4  cmp     [r8+0Ch], r12d
0x180007bf8  jnz     loc_180008350
0x180007bfe  jmp     loc_180007FE4
0x180007c03  mov     rcx, [r14+28h]; struct tag_EcRpcMetadataPropertyList *
0x180007c07  lea     r8, [rbp+FileTime2]; unsigned int *
0x180007c0b  mov     [rbp+FileTime2.dwLowDateTime], edi
0x180007c0e  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180007c13  cmp     [rbp+FileTime2.dwLowDateTime], edi
0x180007c16  jnz     loc_1800083B3
0x180007c1c  jmp     loc_180007FE4
0x180007c21  cmp     [r8+0Ch], r15d
0x180007c25  jz      short loc_180007C36
0x180007c27  cmp     [r8+0Ch], r12d
0x180007c2b  jnz     loc_180008416
0x180007c31  jmp     loc_180007FE4
0x180007c36  mov     rcx, [r14+28h]; struct tag_EcRpcMetadataPropertyList *
0x180007c3a  lea     r8, [rbp+FileTime2]; unsigned int *
0x180007c3e  mov     [rbp+FileTime2.dwLowDateTime], edi
0x180007c41  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180007c46  cmp     [rbp+FileTime2.dwLowDateTime], edi
0x180007c49  jnz     loc_180008479
0x180007c4f  jmp     loc_180007FE4
0x180007c54  cmp     [r8+0Ch], r15d
0x180007c58  jz      short loc_180007C69
0x180007c5a  cmp     [r8+0Ch], r12d
0x180007c5e  jnz     loc_1800084DC
0x180007c64  jmp     loc_180007FE4
0x180007c69  cmp     cs:?EnumNameValueDeliveryMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A, r12; _ENUM_NAMEVALUE_PAIR near * EnumNameValueDeliveryMode
0x180007c70  jz      loc_18000853F
0x180007c76  mov     ecx, [r8]
0x180007c79  lea     rax, ?EnumNameValueDeliveryMode@@3PAU_ENUM_NAMEVALUE_PAIR@@A; _ENUM_NAMEVALUE_PAIR near * EnumNameValueDeliveryMode
0x180007c80  cmp     [rax+8], ecx
0x180007c83  jz      short loc_180007C94
0x180007c85  add     rax, 10h
0x180007c89  cmp     [rax], r12
0x180007c8c  jz      loc_18000853F
0x180007c92  jmp     short loc_180007C80
0x180007c94  cmp     [rax], r12
0x180007c97  jz      loc_18000853F
0x180007c9d  mov     rcx, [r14+28h]; struct tag_EcRpcMetadataPropertyList *
0x180007ca1  lea     r8, [rbp+FileTime2]; unsigned int *
0x180007ca5  mov     [rbp+FileTime2.dwLowDateTime], edi
0x180007ca8  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180007cad  cmp     [rbp+FileTime2.dwLowDateTime], edi
0x180007cb0  jnz     loc_1800085A2
0x180007cb6  jmp     loc_180007FE4
0x180007cbb  test    dword ptr [r8+0Ch], 0FFFFFFFDh
0x180007cc3  jnz     loc_180008605
0x180007cc9  jmp     loc_180007FE4
0x180007cce  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007cd6  jnz     loc_180008668
0x180007cdc  jmp     loc_180007FE4
0x180007ce1  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007ce9  jnz     loc_1800086CB
0x180007cef  jmp     loc_180007FE4
0x180007cf4  cmp     dword ptr [r8+0Ch], 3
0x180007cf9  jz      short loc_180007D0A
0x180007cfb  cmp     [r8+0Ch], r12d
0x180007cff  jnz     loc_18000872E
0x180007d05  jmp     loc_180007FE4
0x180007d0a  mov     rcx, [r8]
0x180007d0d  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180007d11  mov     rax, rcx
0x180007d14  mov     [rbp+FileTime2.dwLowDateTime], ecx
0x180007d17  shr     rax, 20h
0x180007d1b  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180007d1f  mov     [rbp+FileTime2.dwHighDateTime], eax
0x180007d22  mov     [rbp+FileTime1.dwLowDateTime], 0A8F318F0h
0x180007d29  mov     [rbp+FileTime1.dwHighDateTime], 62193EFh
0x180007d30  call    cs:__imp_CompareFileTime
0x180007d36  cmp     eax, 0FFFFFFFFh
0x180007d39  jz      loc_180008791
0x180007d3f  jmp     loc_180007FE4
0x180007d44  cmp     [r8+0Ch], r15d
0x180007d48  jz      short loc_180007D59
0x180007d4a  cmp     [r8+0Ch], r12d
0x180007d4e  jnz     loc_1800087F4
0x180007d54  jmp     loc_180007FE4
0x180007d59  mov     rcx, [rcx+28h]; struct tag_EcRpcMetadataPropertyList *
0x180007d5d  lea     r8, [rbp+FileTime2]; unsigned int *
0x180007d61  mov     [rbp+FileTime2.dwLowDateTime], edi
0x180007d64  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180007d69  cmp     [rbp+FileTime2.dwLowDateTime], edi
0x180007d6c  jnz     loc_180008857
0x180007d72  jmp     loc_180007FE4
0x180007d77  cmp     esi, 18h
0x180007d7a  jg      loc_180007EE9
0x180007d80  jz      loc_180007ED6
0x180007d86  mov     ecx, esi
0x180007d88  sub     ecx, 11h
0x180007d8b  jz      loc_180007E9F
0x180007d91  sub     ecx, edi
0x180007d93  jz      loc_180007E52
0x180007d99  sub     ecx, edi
0x180007d9b  jz      loc_180007E3F
0x180007da1  sub     ecx, edi
0x180007da3  jz      loc_180007E2C
0x180007da9  sub     ecx, edi
0x180007dab  jz      short loc_180007DDF
0x180007dad  sub     ecx, edi
0x180007daf  jz      short loc_180007DCC
0x180007db1  cmp     ecx, edi
0x180007db3  jnz     loc_180008D0A
0x180007db9  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007dc1  jnz     loc_1800088BA
0x180007dc7  jmp     loc_180007FE4
0x180007dcc  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007dd4  jnz     loc_18000891D
0x180007dda  jmp     loc_180007FE4
0x180007ddf  cmp     [r8+0Ch], r15d
0x180007de3  jz      short loc_180007DF4
0x180007de5  cmp     [r8+0Ch], r12d
0x180007de9  jnz     loc_180008980
0x180007def  jmp     loc_180007FE4
0x180007df4  cmp     cs:?EnumNameValueCredentialsType@@3PAU_ENUM_NAMEVALUE_PAIR@@A, r12; _ENUM_NAMEVALUE_PAIR near * EnumNameValueCredentialsType
0x180007dfb  jz      loc_1800089E3
0x180007e01  mov     ecx, [r8]
0x180007e04  lea     rax, ?EnumNameValueCredentialsType@@3PAU_ENUM_NAMEVALUE_PAIR@@A; _ENUM_NAMEVALUE_PAIR near * EnumNameValueCredentialsType
0x180007e0b  cmp     [rax+8], ecx
0x180007e0e  jz      short loc_180007E1E
0x180007e10  add     rax, 10h
0x180007e14  cmp     [rax], r12
0x180007e17  jnz     short loc_180007E0B
0x180007e19  jmp     loc_1800089E3
0x180007e1e  cmp     [rax], r12
0x180007e21  jz      loc_1800089E3
0x180007e27  jmp     loc_180007FE4
0x180007e2c  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007e34  jnz     loc_180008A46
0x180007e3a  jmp     loc_180007FE4
0x180007e3f  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007e47  jnz     loc_180008AA9
0x180007e4d  jmp     loc_180007FE4
0x180007e52  cmp     [r8+0Ch], r15d
0x180007e56  jz      short loc_180007E67
0x180007e58  cmp     [r8+0Ch], r12d
0x180007e5c  jnz     loc_180008B0C
0x180007e62  jmp     loc_180007FE4
0x180007e67  cmp     cs:?EnumNameValueContentFormat@@3PAU_ENUM_NAMEVALUE_PAIR@@A, r12; _ENUM_NAMEVALUE_PAIR near * EnumNameValueContentFormat
0x180007e6e  jz      loc_180008B6F
0x180007e74  mov     ecx, [r8]
0x180007e77  lea     rax, ?EnumNameValueContentFormat@@3PAU_ENUM_NAMEVALUE_PAIR@@A; _ENUM_NAMEVALUE_PAIR near * EnumNameValueContentFormat
0x180007e7e  cmp     [rax+8], ecx
0x180007e81  jz      short loc_180007E91
0x180007e83  add     rax, 10h
0x180007e87  cmp     [rax], r12
0x180007e8a  jnz     short loc_180007E7E
0x180007e8c  jmp     loc_180008B6F
0x180007e91  cmp     [rax], r12
0x180007e94  jz      loc_180008B6F
0x180007e9a  jmp     loc_180007FE4
0x180007e9f  cmp     dword ptr [r8+0Ch], 4
0x180007ea4  jz      short loc_180007EB5
0x180007ea6  cmp     [r8+0Ch], r12d
0x180007eaa  jnz     loc_180008BD2
0x180007eb0  jmp     loc_180007FE4
0x180007eb5  mov     rcx, [r8]; lpName
0x180007eb8  test    rcx, rcx
0x180007ebb  jz      loc_180007FE4
0x180007ec1  xor     edx, edx; dwFlags
0x180007ec3  call    cs:__imp_LocaleNameToLCID
0x180007ec9  test    eax, eax
0x180007ecb  jz      loc_180008C35
0x180007ed1  jmp     loc_180007FE4
0x180007ed6  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007ede  jnz     loc_180008CA7
0x180007ee4  jmp     loc_180007FE4
0x180007ee9  mov     ecx, esi
0x180007eeb  sub     ecx, 19h
0x180007eee  jz      loc_180007FDA
0x180007ef4  sub     ecx, edi
0x180007ef6  jz      loc_180007FCA
0x180007efc  sub     ecx, edi
0x180007efe  jz      short loc_180007F44
0x180007f00  sub     ecx, edi
0x180007f02  jz      short loc_180007F27
0x180007f04  sub     ecx, edi
0x180007f06  jz      short loc_180007F27
0x180007f08  sub     ecx, edi
0x180007f0a  jz      short loc_180007F27
0x180007f0c  cmp     ecx, edi
0x180007f0e  jnz     loc_180008D0A
0x180007f14  test    dword ptr [r8+0Ch], 0FFFFFFFBh
0x180007f1c  jnz     loc_180008D6D
0x180007f22  jmp     loc_180007FE4
0x180007f27  mov     eax, [r8+0Ch]
0x180007f2b  and     al, 7Fh
0x180007f2d  cmp     al, 4
0x180007f2f  jz      loc_180007FE4
0x180007f35  cmp     [r8+0Ch], r12d
0x180007f39  jnz     loc_180008DD0
0x180007f3f  jmp     loc_180007FE4
0x180007f44  cmp     [r8+0Ch], r15d
0x180007f48  jz      short loc_180007F56
0x180007f4a  cmp     [r8+0Ch], r12d
0x180007f4e  jnz     loc_180008E33
0x180007f54  jmp     short loc_180007F8A
0x180007f56  cmp     cs:?EnumNameValueSubscriptionType@@3PAU_ENUM_NAMEVALUE_PAIR@@A, r12; _ENUM_NAMEVALUE_PAIR near * EnumNameValueSubscriptionType
0x180007f5d  jz      loc_180008E96
0x180007f63  mov     ecx, [r8]
0x180007f66  lea     rax, ?EnumNameValueSubscriptionType@@3PAU_ENUM_NAMEVALUE_PAIR@@A; _ENUM_NAMEVALUE_PAIR near * EnumNameValueSubscriptionType
0x180007f6d  cmp     [rax+8], ecx
0x180007f70  jz      short loc_180007F81
0x180007f72  add     rax, 10h
0x180007f76  cmp     [rax], r12
0x180007f79  jz      loc_180008E96
0x180007f7f  jmp     short loc_180007F6D
0x180007f81  cmp     [rax], r12
0x180007f84  jz      loc_180008E96
0x180007f8a  cmp     [r14+68h], r12b
0x180007f8e  jnz     short loc_180007FE4
0x180007f90  xorps   xmm0, xmm0
0x180007f93  mov     [rbp+FileTime2.dwLowDateTime], r12d
0x180007f97  lea     rax, [rbp+FileTime2]
  ... truncated ...
```
