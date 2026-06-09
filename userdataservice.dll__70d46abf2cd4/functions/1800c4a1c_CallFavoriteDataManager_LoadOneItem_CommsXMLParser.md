# CallFavoriteDataManager::_LoadOneItem(CommsXMLParser &)

- ea: `0x1800c4a1c`
- end: `0x1800c5454`
- name: `?_LoadOneItem@CallFavoriteDataManager@@AEAAJAEAVCommsXMLParser@@@Z`
- size: `2616`
- prototype: `int(CallFavoriteDataManager *__hidden this, struct CommsXMLParser *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c47d0`

## callees

- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x18005e048`
- `0x1800977b8`
- `0x1800977c4`
- `0x1800c112c`
- `0x1800c2a08`
- `0x1800c4a1c`
- `0x1800c5f4c`
- `0x1800c6134`
- `0x18012c76a`
- `0x18012e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800c4acb`
- `msvcrt!_wcsicmp` at `0x1800c4b55`
- `msvcrt!_wcsicmp` at `0x1800c4be6`
- `msvcrt!_wcsicmp` at `0x1800c4c76`
- `msvcrt!_wcsicmp` at `0x1800c4d07`
- `msvcrt!_wcsicmp` at `0x1800c4d98`
- `msvcrt!_wcsicmp` at `0x1800c4e17`
- `msvcrt!_wcsicmp` at `0x1800c4edd`
- `msvcrt!_wcsicmp` at `0x1800c4fa3`
- `msvcrt!_wcsicmp` at `0x1800c5022`
- `msvcrt!_wcsicmp` at `0x1800c50a1`
- `msvcrt!_wcsicmp` at `0x1800c5132`
- `msvcrt!_wcsicmp` at `0x1800c4acb`
- `msvcrt!_wcsicmp` at `0x1800c4b55`
- `msvcrt!_wcsicmp` at `0x1800c4be6`
- `msvcrt!_wcsicmp` at `0x1800c4c76`
- `msvcrt!_wcsicmp` at `0x1800c4d07`
- `msvcrt!_wcsicmp` at `0x1800c4d98`
- `msvcrt!_wcsicmp` at `0x1800c4e17`
- `msvcrt!_wcsicmp` at `0x1800c4edd`
- `msvcrt!_wcsicmp` at `0x1800c4fa3`
- `msvcrt!_wcsicmp` at `0x1800c5022`
- `msvcrt!_wcsicmp` at `0x1800c50a1`
- `msvcrt!_wcsicmp` at `0x1800c5132`
- `UserDataTypeHelperUtil!DupString` at `0x1800c4ba2`
- `UserDataTypeHelperUtil!DupString` at `0x1800c4cc3`
- `UserDataTypeHelperUtil!DupString` at `0x1800c4d54`
- `UserDataTypeHelperUtil!DupString` at `0x1800c50ee`
- `UserDataTypeHelperUtil!DupString` at `0x1800c5183`
- `UserDataTypeHelperUtil!DupString` at `0x1800c4ba2`
- `UserDataTypeHelperUtil!DupString` at `0x1800c4cc3`
- `UserDataTypeHelperUtil!DupString` at `0x1800c4d54`
- `UserDataTypeHelperUtil!DupString` at `0x1800c50ee`
- `UserDataTypeHelperUtil!DupString` at `0x1800c5183`
- `UserDataTypeHelperUtil!StringToBytes` at `0x1800c4e8d`
- `UserDataTypeHelperUtil!StringToBytes` at `0x1800c4f53`
- `UserDataTypeHelperUtil!StringToBytes` at `0x1800c4e8d`
- `UserDataTypeHelperUtil!StringToBytes` at `0x1800c4f53`

## string_xrefs

- `0x1800c51a2`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c51c9`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c51ff`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c5226`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c524d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c526f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c52b1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c52ec`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c5307`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c5329`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c5353`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c537d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c53a1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c53dd`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c5427`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c512b`: `CallbackToken`

## pseudocode

```c
__int64 __fastcall CallFavoriteDataManager::_LoadOneItem(CallFavoriteDataManager *this, struct CommsXMLParser *a2)
{
  char *v4; // rax
  char *v5; // rsi
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  const wchar_t *v9; // rax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  const wchar_t *v14; // rax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  const wchar_t *v18; // rax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  const wchar_t *v22; // rax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  const wchar_t *v26; // rax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  const wchar_t *v30; // rax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  const wchar_t *v34; // rax
  __int64 v35; // rax
  int v36; // eax
  unsigned __int64 v37; // rbx
  void *v38; // rax
  __int64 v39; // rax
  const wchar_t *v40; // rax
  __int64 v41; // rax
  int v42; // eax
  unsigned __int64 v43; // rbx
  void *v44; // rax
  __int64 v45; // rax
  const wchar_t *v46; // rax
  __int64 v47; // rax
  int v48; // eax
  __int64 v49; // rax
  const wchar_t *v50; // rax
  __int64 v51; // rax
  int v52; // eax
  __int64 v53; // rax
  const wchar_t *v54; // rax
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rax
  const wchar_t *v58; // rax
  __int64 v59; // rax
  int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // r9
  __int64 v63; // r9
  __int64 v64; // r9
  __int64 v65; // r9
  __int64 v66; // r9
  __int64 v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // r9
  __int64 v70; // rcx
  __int64 v71; // rdx
  __int64 v72; // r9
  __int64 v73; // r9
  struct UdmCallFavoriteItemDataWithId *v74; // rcx
  __int64 v76; // [rsp+30h] [rbp-59h] BYREF
  __int64 v77; // [rsp+38h] [rbp-51h]
  __int64 v78; // [rsp+50h] [rbp-39h] BYREF
  __int64 v79; // [rsp+58h] [rbp-31h] BYREF
  __int64 v80; // [rsp+60h] [rbp-29h] BYREF
  __int64 v81; // [rsp+68h] [rbp-21h] BYREF
  __int64 v82; // [rsp+70h] [rbp-19h] BYREF
  __int64 v83; // [rsp+78h] [rbp-11h] BYREF
  __int64 v84; // [rsp+80h] [rbp-9h] BYREF
  __int64 v85; // [rsp+88h] [rbp-1h] BYREF
  struct UdmCallFavoriteItemDataWithId *Block; // [rsp+90h] [rbp+7h] BYREF
  __int64 v87; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v88; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v89; // [rsp+A8h] [rbp+1Fh] BYREF
  __int64 v90[6]; // [rsp+B0h] [rbp+27h] BYREF
  int v91; // [rsp+100h] [rbp+77h] BYREF
  int v92; // [rsp+108h] [rbp+7Fh] BYREF

  v4 = (char *)operator new(0x70u);
  v5 = v4;
  if ( !v4 )
  {
    v7 = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
      1005);
    return v7;
  }
  memset_0(v4, 0, 0x70u);
  Block = (struct UdmCallFavoriteItemDataWithId *)v5;
  memset_0(v5, 0, 0x70u);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v76);
  v91 = 0;
  v92 = 0;
  while ( 1 )
  {
    v6 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 16LL))(a2);
    v7 = v6;
    if ( v6 )
      break;
    v8 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
    v9 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    if ( !_wcsicmp(L"Id", v9) )
    {
      ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v87, a2);
      v10 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 56LL))(v10, &v91);
      v7 = v11;
      if ( v11 < 0 )
      {
        Log_HREvent(
          (unsigned int)v11,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
          1016);
        v61 = v87;
        goto LABEL_55;
      }
      v12 = v87;
      *(_DWORD *)v5 = v91;
      goto LABEL_7;
    }
    v13 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
    v14 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    if ( _wcsicmp(L"Name", v14) )
    {
      v17 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v18 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      if ( !_wcsicmp(L"ContactId", v18) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v81, a2);
        v19 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 72LL))(v19, &v76);
        v7 = v20;
        if ( v20 < 0 )
        {
          v63 = 1026;
          goto LABEL_58;
        }
        v20 = StringToOLITEMID(v76, v5 + 24);
        v7 = v20;
        if ( v20 < 0 )
        {
          v63 = 1027;
LABEL_58:
          Log_HREvent(
            (unsigned int)v20,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            v63);
          v61 = v81;
          goto LABEL_55;
        }
        v12 = v81;
        goto LABEL_7;
      }
      v21 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v22 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
      if ( !_wcsicmp(L"Number", v22) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v82, a2);
        v23 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 72LL))(v23, &v76);
        v7 = v24;
        if ( v24 < 0 )
        {
          v64 = 1031;
          goto LABEL_61;
        }
        v24 = DupString(v5 + 8, v76);
        v7 = v24;
        if ( v24 < 0 )
        {
          v64 = 1032;
LABEL_61:
          Log_HREvent(
            (unsigned int)v24,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            v64);
          v61 = v82;
          goto LABEL_55;
        }
        v12 = v82;
        goto LABEL_7;
      }
      v25 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v26 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      if ( !_wcsicmp(L"Line", v26) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v83, a2);
        v27 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 72LL))(v27, &v76);
        v7 = v28;
        if ( v28 < 0 )
        {
          v65 = 1036;
          goto LABEL_64;
        }
        v28 = DupString(v5 + 80, v76);
        v7 = v28;
        if ( v28 < 0 )
        {
          v65 = 1037;
LABEL_64:
          Log_HREvent(
            (unsigned int)v28,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            v65);
          v61 = v83;
          goto LABEL_55;
        }
        v12 = v83;
        goto LABEL_7;
      }
      v29 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v30 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
      if ( !_wcsicmp(L"PropertyId", v30) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v88, a2);
        v31 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v32 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 56LL))(v31, &v91);
        v7 = v32;
        if ( v32 < 0 )
        {
          Log_HREvent(
            (unsigned int)v32,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            1041);
          v61 = v88;
          goto LABEL_55;
        }
        v12 = v88;
        *((_DWORD *)v5 + 18) = v91;
        goto LABEL_7;
      }
      v33 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v34 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
      if ( !_wcsicmp(L"RemoteId", v34) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v78, a2);
        v35 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v36 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 72LL))(v35, &v76);
        v7 = v36;
        if ( v36 < 0 )
        {
          v66 = 1046;
LABEL_69:
          v68 = 1;
          v67 = (unsigned int)v36;
LABEL_70:
          Log_HREvent(
            v67,
            v68,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            v66);
          v61 = v78;
          goto LABEL_55;
        }
        v37 = (unsigned __int64)((v77 - v76) >> 1) >> 1;
        v38 = operator new[](v37);
        *((_QWORD *)v5 + 6) = v38;
        if ( !v38 )
        {
          v7 = -2147024882;
          v66 = 1049;
          v67 = 2147942414LL;
          v68 = 0;
          goto LABEL_70;
        }
        StringToBytes(v76, v38, v37);
        v36 = ULongLongToULong(v37, (unsigned int *)v5 + 10);
        v7 = v36;
        if ( v36 < 0 )
        {
          v66 = 1052;
          goto LABEL_69;
        }
        v12 = v78;
        goto LABEL_7;
      }
      v39 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v40 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
      if ( !_wcsicmp(L"PropHash", v40) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v79, a2);
        v41 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v42 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 72LL))(v41, &v76);
        v7 = v42;
        if ( v42 < 0 )
        {
          v69 = 1056;
LABEL_74:
          v71 = 1;
          v70 = (unsigned int)v42;
LABEL_75:
          Log_HREvent(
            v70,
            v71,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            v69);
          v61 = v79;
          goto LABEL_55;
        }
        v43 = (unsigned __int64)((v77 - v76) >> 1) >> 1;
        v44 = operator new[](v43);
        *((_QWORD *)v5 + 8) = v44;
        if ( !v44 )
        {
          v7 = -2147024882;
          v69 = 1059;
          v70 = 2147942414LL;
          v71 = 0;
          goto LABEL_75;
        }
        StringToBytes(v76, v44, v43);
        v42 = ULongLongToULong(v43, (unsigned int *)v5 + 14);
        v7 = v42;
        if ( v42 < 0 )
        {
          v69 = 1061;
          goto LABEL_74;
        }
        v12 = v79;
        goto LABEL_7;
      }
      v45 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v46 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 8LL))(v45);
      if ( !_wcsicmp(L"IsVideoCall", v46) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v89, a2);
        v47 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v48 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 80LL))(v47, &v92);
        v7 = v48;
        if ( v48 < 0 )
        {
          Log_HREvent(
            (unsigned int)v48,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            1065);
          v61 = v89;
          goto LABEL_55;
        }
        v12 = v89;
        *((_DWORD *)v5 + 22) = v92;
        goto LABEL_7;
      }
      v49 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v50 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
      if ( !_wcsicmp(L"IsPublicSwitchTelephoneNetwork", v50) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)v90, a2);
        v51 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v52 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 80LL))(v51, &v92);
        v7 = v52;
        if ( v52 < 0 )
        {
          Log_HREvent(
            (unsigned int)v52,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            1070);
          v61 = v90[0];
          goto LABEL_55;
        }
        v12 = v90[0];
        *((_DWORD *)v5 + 23) = v92;
        goto LABEL_7;
      }
      v53 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v54 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
      if ( !_wcsicmp(L"ApplicationId", v54) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v84, a2);
        v55 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v56 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 72LL))(v55, &v76);
        v7 = v56;
        if ( v56 < 0 )
        {
          v72 = 1075;
          goto LABEL_80;
        }
        v56 = DupString(v5 + 96, v76);
        v7 = v56;
        if ( v56 < 0 )
        {
          v72 = 1076;
LABEL_80:
          Log_HREvent(
            (unsigned int)v56,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            v72);
          v61 = v84;
          goto LABEL_55;
        }
        v12 = v84;
        goto LABEL_7;
      }
      v57 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v58 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 8LL))(v57);
      if ( !_wcsicmp(L"CallbackToken", v58) )
      {
        ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v85, a2);
        v59 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
        v60 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 72LL))(v59, &v76);
        v7 = v60;
        if ( v60 < 0 )
        {
          v73 = 1080;
LABEL_83:
          Log_HREvent(
            (unsigned int)v60,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
            v73);
          v61 = v85;
LABEL_55:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 32LL))(v61);
LABEL_86:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v76);
          v74 = (struct UdmCallFavoriteItemDataWithId *)v5;
LABEL_87:
          FreeUdmCallFavoriteItemDataWithId(v74);
          return v7;
        }
        v60 = DupString(v5 + 104, v76);
        v7 = v60;
        if ( v60 < 0 )
        {
          v73 = 1081;
          goto LABEL_83;
        }
        v12 = v85;
        goto LABEL_7;
      }
    }
    else
    {
      ForwardParser_AutoDepth::ForwardParser_AutoDepth((ForwardParser_AutoDepth *)&v80, a2);
      v15 = (*(__int64 (__fastcall **)(struct CommsXMLParser *))(*(_QWORD *)a2 + 8LL))(a2);
      v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 72LL))(v15, &v76);
      v7 = v16;
      if ( v16 < 0 )
      {
        v62 = 1021;
        goto LABEL_54;
      }
      v16 = DupString(v5 + 16, v76);
      v7 = v16;
      if ( v16 < 0 )
      {
        v62 = 1022;
LABEL_54:
        Log_HREvent(
          (unsigned int)v16,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
          v62);
        v61 = v80;
        goto LABEL_55;
      }
      v12 = v80;
LABEL_7:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
    }
  }
  if ( v6 < 0 )
  {
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
      1084);
    goto LABEL_86;
  }
  if ( (unsigned __int8)utl::list<tlx::auto_xxx<UdmCallFavoriteItemDataWithId *,void (*)(UdmCallFavoriteItemDataWithId *),&void FreeUdmCallFavoriteItemDataWithId(UdmCallFavoriteItemDataWithId *),0>,utl::allocator<tlx::auto_xxx<UdmCallFavoriteItemDataWithId *,void (*)(UdmCallFavoriteItemDataWithId *),&void FreeUdmCallFavoriteItemDataWithId(UdmCallFavoriteItemDataWithId *),0>>>::push_back(
                          (char *)this + 48,
                          &Block) )
  {
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v76);
    if ( Block )
      FreeUdmCallFavoriteItemDataWithId(Block);
    return 0;
  }
  else
  {
    v7 = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
      1087);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v76);
    v74 = Block;
    if ( Block )
      goto LABEL_87;
    return v7;
  }
}

```

## disassembly

```asm
0x1800c4a1c  mov     [rsp-8+arg_0], rbx
0x1800c4a21  push    rbp
0x1800c4a22  push    rsi
0x1800c4a23  push    rdi
0x1800c4a24  push    r14
0x1800c4a26  push    r15
0x1800c4a28  lea     rbp, [rsp-37h]
0x1800c4a2d  sub     rsp, 0C0h
0x1800c4a34  mov     r15, rcx
0x1800c4a37  mov     ebx, 70h ; 'p'
0x1800c4a3c  mov     ecx, ebx; Size
0x1800c4a3e  mov     rdi, rdx
0x1800c4a41  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c4a46  xor     edx, edx; Val
0x1800c4a48  mov     rsi, rax
0x1800c4a4b  test    rax, rax
0x1800c4a4e  jz      loc_1800C5422
0x1800c4a54  mov     r8d, ebx; Size
0x1800c4a57  mov     rcx, rax; void *
0x1800c4a5a  call    memset_0
0x1800c4a5f  mov     r8d, ebx; Size
0x1800c4a62  mov     [rbp+57h+Block], rsi
0x1800c4a66  xor     edx, edx; Val
0x1800c4a68  mov     rcx, rsi; void *
0x1800c4a6b  call    memset_0
0x1800c4a70  lea     rcx, [rbp+57h+var_B0]; void *
0x1800c4a74  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800c4a79  mov     [rbp+57h+arg_10], 0
0x1800c4a80  mov     [rbp+57h+arg_18], 0
0x1800c4a87  mov     rax, [rdi]
0x1800c4a8a  mov     rcx, rdi
0x1800c4a8d  mov     rax, [rax+10h]
0x1800c4a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a96  mov     ebx, eax
0x1800c4a98  test    eax, eax
0x1800c4a9a  jnz     loc_1800C5399
0x1800c4aa0  mov     rax, [rdi]
0x1800c4aa3  mov     rcx, rdi
0x1800c4aa6  mov     rax, [rax+8]
0x1800c4aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4aaf  mov     rdx, rax
0x1800c4ab2  mov     rcx, [rax]
0x1800c4ab5  mov     rax, [rcx+8]
0x1800c4ab9  mov     rcx, rdx
0x1800c4abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ac1  mov     rdx, rax; String2
0x1800c4ac4  lea     rcx, aId_0; "Id"
0x1800c4acb  call    cs:__imp__wcsicmp
0x1800c4ad1  test    eax, eax
0x1800c4ad3  jnz     short loc_1800C4B2A
0x1800c4ad5  mov     rdx, rdi; struct IForwardParser *
0x1800c4ad8  lea     rcx, [rbp+57h+var_48]; this
0x1800c4adc  call    ??0ForwardParser_AutoDepth@@QEAA@PEAVIForwardParser@@@Z; ForwardParser_AutoDepth::ForwardParser_AutoDepth(IForwardParser *)
0x1800c4ae1  mov     rax, [rdi]
0x1800c4ae4  mov     rcx, rdi
0x1800c4ae7  mov     rax, [rax+8]
0x1800c4aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4af0  mov     r8, rax
0x1800c4af3  lea     rdx, [rbp+57h+arg_10]
0x1800c4af7  mov     rcx, [rax]
0x1800c4afa  mov     rax, [rcx+38h]
0x1800c4afe  mov     rcx, r8
0x1800c4b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b06  mov     ebx, eax
0x1800c4b08  test    eax, eax
0x1800c4b0a  js      loc_1800C519C
0x1800c4b10  mov     eax, [rbp+57h+arg_10]
0x1800c4b13  mov     rcx, [rbp+57h+var_48]
0x1800c4b17  mov     [rsi], eax
0x1800c4b19  mov     rax, [rcx]
0x1800c4b1c  mov     rax, [rax+20h]
0x1800c4b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b25  jmp     loc_1800C4A87
0x1800c4b2a  mov     rax, [rdi]
0x1800c4b2d  mov     rcx, rdi
0x1800c4b30  mov     rax, [rax+8]
0x1800c4b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b39  mov     rdx, rax
0x1800c4b3c  mov     rcx, [rax]
0x1800c4b3f  mov     rax, [rcx+8]
0x1800c4b43  mov     rcx, rdx
0x1800c4b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b4b  mov     rdx, rax; String2
0x1800c4b4e  lea     rcx, aName; "Name"
0x1800c4b55  call    cs:__imp__wcsicmp
0x1800c4b5b  test    eax, eax
0x1800c4b5d  jnz     short loc_1800C4BBB
0x1800c4b5f  mov     rdx, rdi; struct IForwardParser *
0x1800c4b62  lea     rcx, [rbp+57h+var_80]; this
0x1800c4b66  call    ??0ForwardParser_AutoDepth@@QEAA@PEAVIForwardParser@@@Z; ForwardParser_AutoDepth::ForwardParser_AutoDepth(IForwardParser *)
0x1800c4b6b  mov     rax, [rdi]
0x1800c4b6e  mov     rcx, rdi
0x1800c4b71  mov     rax, [rax+8]
0x1800c4b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b7a  mov     r8, rax
0x1800c4b7d  lea     rdx, [rbp+57h+var_B0]
0x1800c4b81  mov     rcx, [rax]
0x1800c4b84  mov     rax, [rcx+48h]
0x1800c4b88  mov     rcx, r8
0x1800c4b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b90  mov     ebx, eax
0x1800c4b92  test    eax, eax
0x1800c4b94  js      loc_1800C51C3
0x1800c4b9a  mov     rdx, [rbp+57h+var_B0]
0x1800c4b9e  lea     rcx, [rsi+10h]
0x1800c4ba2  call    cs:__imp_DupString
0x1800c4ba8  mov     ebx, eax
0x1800c4baa  test    eax, eax
0x1800c4bac  js      loc_1800C51BB
0x1800c4bb2  mov     rcx, [rbp+57h+var_80]
0x1800c4bb6  jmp     loc_1800C4B19
0x1800c4bbb  mov     rax, [rdi]
0x1800c4bbe  mov     rcx, rdi
0x1800c4bc1  mov     rax, [rax+8]
0x1800c4bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4bca  mov     rdx, rax
0x1800c4bcd  mov     rcx, [rax]
0x1800c4bd0  mov     rax, [rcx+8]
0x1800c4bd4  mov     rcx, rdx
0x1800c4bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4bdc  mov     rdx, rax; String2
0x1800c4bdf  lea     rcx, aContactid; "ContactId"
0x1800c4be6  call    cs:__imp__wcsicmp
0x1800c4bec  test    eax, eax
0x1800c4bee  jnz     short loc_1800C4C4B
0x1800c4bf0  mov     rdx, rdi; struct IForwardParser *
0x1800c4bf3  lea     rcx, [rbp+57h+var_78]; this
0x1800c4bf7  call    ??0ForwardParser_AutoDepth@@QEAA@PEAVIForwardParser@@@Z; ForwardParser_AutoDepth::ForwardParser_AutoDepth(IForwardParser *)
0x1800c4bfc  mov     rax, [rdi]
0x1800c4bff  mov     rcx, rdi
0x1800c4c02  mov     rax, [rax+8]
0x1800c4c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4c0b  mov     r8, rax
0x1800c4c0e  lea     rdx, [rbp+57h+var_B0]
0x1800c4c12  mov     rcx, [rax]
0x1800c4c15  mov     rax, [rcx+48h]
0x1800c4c19  mov     rcx, r8
0x1800c4c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4c21  mov     ebx, eax
0x1800c4c23  test    eax, eax
0x1800c4c25  js      loc_1800C51F9
0x1800c4c2b  mov     rcx, [rbp+57h+var_B0]
0x1800c4c2f  lea     rdx, [rsi+18h]
0x1800c4c33  call    StringToOLITEMID
0x1800c4c38  mov     ebx, eax
0x1800c4c3a  test    eax, eax
0x1800c4c3c  js      loc_1800C51F1
0x1800c4c42  mov     rcx, [rbp+57h+var_78]
0x1800c4c46  jmp     loc_1800C4B19
0x1800c4c4b  mov     rax, [rdi]
0x1800c4c4e  mov     rcx, rdi
0x1800c4c51  mov     rax, [rax+8]
0x1800c4c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4c5a  mov     rdx, rax
0x1800c4c5d  mov     rcx, [rax]
0x1800c4c60  mov     rax, [rcx+8]
0x1800c4c64  mov     rcx, rdx
0x1800c4c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4c6c  mov     rdx, rax; String2
0x1800c4c6f  lea     rcx, aNumber; "Number"
0x1800c4c76  call    cs:__imp__wcsicmp
0x1800c4c7c  test    eax, eax
0x1800c4c7e  jnz     short loc_1800C4CDC
0x1800c4c80  mov     rdx, rdi; struct IForwardParser *
0x1800c4c83  lea     rcx, [rbp+57h+var_70]; this
0x1800c4c87  call    ??0ForwardParser_AutoDepth@@QEAA@PEAVIForwardParser@@@Z; ForwardParser_AutoDepth::ForwardParser_AutoDepth(IForwardParser *)
0x1800c4c8c  mov     rax, [rdi]
0x1800c4c8f  mov     rcx, rdi
0x1800c4c92  mov     rax, [rax+8]
0x1800c4c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4c9b  mov     r8, rax
0x1800c4c9e  lea     rdx, [rbp+57h+var_B0]
0x1800c4ca2  mov     rcx, [rax]
0x1800c4ca5  mov     rax, [rcx+48h]
0x1800c4ca9  mov     rcx, r8
0x1800c4cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4cb1  mov     ebx, eax
0x1800c4cb3  test    eax, eax
0x1800c4cb5  js      loc_1800C5220
0x1800c4cbb  mov     rdx, [rbp+57h+var_B0]
0x1800c4cbf  lea     rcx, [rsi+8]
0x1800c4cc3  call    cs:__imp_DupString
0x1800c4cc9  mov     ebx, eax
0x1800c4ccb  test    eax, eax
0x1800c4ccd  js      loc_1800C5218
0x1800c4cd3  mov     rcx, [rbp+57h+var_70]
0x1800c4cd7  jmp     loc_1800C4B19
0x1800c4cdc  mov     rax, [rdi]
0x1800c4cdf  mov     rcx, rdi
0x1800c4ce2  mov     rax, [rax+8]
0x1800c4ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ceb  mov     rdx, rax
0x1800c4cee  mov     rcx, [rax]
0x1800c4cf1  mov     rax, [rcx+8]
0x1800c4cf5  mov     rcx, rdx
0x1800c4cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4cfd  mov     rdx, rax; String2
0x1800c4d00  lea     rcx, aLine; "Line"
0x1800c4d07  call    cs:__imp__wcsicmp
0x1800c4d0d  test    eax, eax
0x1800c4d0f  jnz     short loc_1800C4D6D
0x1800c4d11  mov     rdx, rdi; struct IForwardParser *
0x1800c4d14  lea     rcx, [rbp+57h+var_68]; this
0x1800c4d18  call    ??0ForwardParser_AutoDepth@@QEAA@PEAVIForwardParser@@@Z; ForwardParser_AutoDepth::ForwardParser_AutoDepth(IForwardParser *)
0x1800c4d1d  mov     rax, [rdi]
0x1800c4d20  mov     rcx, rdi
0x1800c4d23  mov     rax, [rax+8]
0x1800c4d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4d2c  mov     r8, rax
0x1800c4d2f  lea     rdx, [rbp+57h+var_B0]
0x1800c4d33  mov     rcx, [rax]
0x1800c4d36  mov     rax, [rcx+48h]
0x1800c4d3a  mov     rcx, r8
0x1800c4d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4d42  mov     ebx, eax
0x1800c4d44  test    eax, eax
0x1800c4d46  js      loc_1800C5247
0x1800c4d4c  mov     rdx, [rbp+57h+var_B0]
0x1800c4d50  lea     rcx, [rsi+50h]
0x1800c4d54  call    cs:__imp_DupString
0x1800c4d5a  mov     ebx, eax
0x1800c4d5c  test    eax, eax
0x1800c4d5e  js      loc_1800C523F
0x1800c4d64  mov     rcx, [rbp+57h+var_68]
0x1800c4d68  jmp     loc_1800C4B19
0x1800c4d6d  mov     rax, [rdi]
0x1800c4d70  mov     rcx, rdi
0x1800c4d73  mov     rax, [rax+8]
0x1800c4d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4d7c  mov     rdx, rax
0x1800c4d7f  mov     rcx, [rax]
0x1800c4d82  mov     rax, [rcx+8]
0x1800c4d86  mov     rcx, rdx
0x1800c4d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4d8e  mov     rdx, rax; String2
0x1800c4d91  lea     rcx, aPropertyid; "PropertyId"
0x1800c4d98  call    cs:__imp__wcsicmp
0x1800c4d9e  test    eax, eax
0x1800c4da0  jnz     short loc_1800C4DEC
0x1800c4da2  mov     rdx, rdi; struct IForwardParser *
0x1800c4da5  lea     rcx, [rbp+57h+var_40]; this
0x1800c4da9  call    ??0ForwardParser_AutoDepth@@QEAA@PEAVIForwardParser@@@Z; ForwardParser_AutoDepth::ForwardParser_AutoDepth(IForwardParser *)
0x1800c4dae  mov     rax, [rdi]
0x1800c4db1  mov     rcx, rdi
0x1800c4db4  mov     rax, [rax+8]
0x1800c4db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4dbd  mov     r8, rax
0x1800c4dc0  lea     rdx, [rbp+57h+arg_10]
0x1800c4dc4  mov     rcx, [rax]
0x1800c4dc7  mov     rax, [rcx+38h]
0x1800c4dcb  mov     rcx, r8
0x1800c4dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4dd3  mov     ebx, eax
0x1800c4dd5  test    eax, eax
0x1800c4dd7  js      loc_1800C5269
0x1800c4ddd  mov     eax, [rbp+57h+arg_10]
0x1800c4de0  mov     rcx, [rbp+57h+var_40]
0x1800c4de4  mov     [rsi+48h], eax
0x1800c4de7  jmp     loc_1800C4B19
0x1800c4dec  mov     rax, [rdi]
0x1800c4def  mov     rcx, rdi
0x1800c4df2  mov     rax, [rax+8]
0x1800c4df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4dfb  mov     rdx, rax
0x1800c4dfe  mov     rcx, [rax]
0x1800c4e01  mov     rax, [rcx+8]
0x1800c4e05  mov     rcx, rdx
0x1800c4e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e0d  mov     rdx, rax; String2
0x1800c4e10  lea     rcx, aRemoteid; "RemoteId"
0x1800c4e17  call    cs:__imp__wcsicmp
0x1800c4e1d  test    eax, eax
0x1800c4e1f  jnz     loc_1800C4EB2
0x1800c4e25  mov     rdx, rdi; struct IForwardParser *
0x1800c4e28  lea     rcx, [rbp+57h+var_90]; this
0x1800c4e2c  call    ??0ForwardParser_AutoDepth@@QEAA@PEAVIForwardParser@@@Z; ForwardParser_AutoDepth::ForwardParser_AutoDepth(IForwardParser *)
0x1800c4e31  mov     rax, [rdi]
0x1800c4e34  mov     rcx, rdi
0x1800c4e37  mov     rax, [rax+8]
0x1800c4e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e40  mov     r8, rax
0x1800c4e43  lea     rdx, [rbp+57h+var_B0]
0x1800c4e47  mov     rcx, [rax]
0x1800c4e4a  mov     rax, [rcx+48h]
0x1800c4e4e  mov     rcx, r8
0x1800c4e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e56  mov     ebx, eax
0x1800c4e58  test    eax, eax
0x1800c4e5a  js      loc_1800C52A4
0x1800c4e60  mov     rbx, [rbp+57h+var_A8]
0x1800c4e64  sub     rbx, [rbp+57h+var_B0]
0x1800c4e68  sar     rbx, 1
0x1800c4e6b  shr     rbx, 1
0x1800c4e6e  mov     rcx, rbx; unsigned __int64
0x1800c4e71  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c4e76  mov     [rsi+30h], rax
0x1800c4e7a  test    rax, rax
0x1800c4e7d  jz      loc_1800C5293
0x1800c4e83  mov     rcx, [rbp+57h+var_B0]
0x1800c4e87  mov     r8, rbx
  ... truncated ...
```
