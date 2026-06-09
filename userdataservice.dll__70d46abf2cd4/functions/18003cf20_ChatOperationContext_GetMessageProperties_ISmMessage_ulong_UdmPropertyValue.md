# ChatOperationContext::GetMessageProperties(ISmMessage *,ulong *,UdmPropertyValue * *)

- ea: `0x18003cf20`
- end: `0x18003e1d6`
- name: `?GetMessageProperties@ChatOperationContext@@QEAAJPEAUISmMessage@@PEAKPEAPEAUUdmPropertyValue@@@Z`
- size: `4790`
- prototype: `int(ChatOperationContext *__hidden this, struct ISmMessage *, unsigned int *, struct UdmPropertyValue **)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800d217c`
- `0x1801215b8`

## callees

- `0x1800049f0`
- `0x180007760`
- `0x180008ee8`
- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180027280`
- `0x180027910`
- `0x180035c40`
- `0x18003cda4`
- `0x18003cf20`
- `0x18003e1dc`
- `0x18003e25c`
- `0x18003e3e4`
- `0x18003e470`
- `0x18003e8a8`
- `0x18003ed7c`
- `0x18005e048`
- `0x180079824`
- `0x18007cb70`
- `0x18007d510`
- `0x1800842f8`
- `0x1800977ac`
- `0x1800d0bd0`
- `0x1800d1e60`
- `0x1800d3108`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `MessagingDataModel2!Messaging_IsSIMMessage` at `0x18003d975`
- `MessagingDataModel2!Messaging_IsSIMMessage` at `0x18003d975`
- `MessagingDataModel2!Messaging_SmEntryIdToUdmObjectId` at `0x18003dd5c`
- `MessagingDataModel2!Messaging_SmEntryIdToUdmObjectId` at `0x18003deac`
- `MessagingDataModel2!Messaging_SmEntryIdToUdmObjectId` at `0x18003dd5c`
- `MessagingDataModel2!Messaging_SmEntryIdToUdmObjectId` at `0x18003deac`
- `UserDataTypeHelperUtil!DupString` at `0x18003d18a`
- `UserDataTypeHelperUtil!DupString` at `0x18003d5db`
- `UserDataTypeHelperUtil!DupString` at `0x18003d89c`
- `UserDataTypeHelperUtil!DupString` at `0x18003dad1`
- `UserDataTypeHelperUtil!DupString` at `0x18003db6c`
- `UserDataTypeHelperUtil!DupString` at `0x18003dcb0`
- `UserDataTypeHelperUtil!DupString` at `0x18003d18a`
- `UserDataTypeHelperUtil!DupString` at `0x18003d5db`
- `UserDataTypeHelperUtil!DupString` at `0x18003d89c`
- `UserDataTypeHelperUtil!DupString` at `0x18003dad1`
- `UserDataTypeHelperUtil!DupString` at `0x18003db6c`
- `UserDataTypeHelperUtil!DupString` at `0x18003dcb0`
- `OLEAUT32!__imp_SysAllocString` at `0x18003d37e`
- `OLEAUT32!__imp_SysAllocString` at `0x18003d50f`
- `OLEAUT32!__imp_SysAllocString` at `0x18003d37e`
- `OLEAUT32!__imp_SysAllocString` at `0x18003d50f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d83b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d861`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e0aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e0ba`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e0e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d83b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d861`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e0aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e0ba`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e0e0`

## string_xrefs

- `0x18003d025`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d1db`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d28f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d2ed`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d35d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d428`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d47a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d4ee`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d594`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d5b7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d820`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d8b3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003daa0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003db3d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003dc60`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003dcc2`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003dd24`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003de73`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003e033`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18003d15c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x18003da06`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`

## pseudocode

```c
__int64 __fastcall ChatOperationContext::GetMessageProperties(
        ChatOperationContext *this,
        struct ISmMessage *a2,
        unsigned int *a3,
        struct UdmPropertyValue **a4)
{
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rdx
  void (__fastcall **v11)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v12; // eax
  void (__fastcall **v13)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v14)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v15)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v16; // eax
  void (__fastcall **v17)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v18; // eax
  void (__fastcall **v19)(struct ISmMessage *, GUID *, __int64 *); // rax
  __int64 v20; // rbx
  int (__fastcall *v21)(__int64, _QWORD *); // rdi
  _QWORD *v22; // rax
  HINSTANCE v23; // rcx
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *StringRes; // rbx
  BSTR *p_bstrString; // rcx
  int FormattedString; // eax
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rcx
  BSTR v31; // rax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, _QWORD *); // rbx
  _QWORD *v34; // rax
  int v35; // eax
  int v36; // eax
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rcx
  BSTR v40; // rax
  void (__fastcall **v41)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v42; // eax
  __int64 v43; // r9
  int v44; // ecx
  int v45; // edi
  void (__fastcall **v46)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v47)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v48)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v49)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v50)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v51)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v52)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v53; // eax
  unsigned int v54; // edi
  _BYTE *v55; // rcx
  int v56; // eax
  __int64 v57; // r9
  __int64 v58; // rcx
  void (__fastcall **v59)(struct ISmMessage *, GUID *, __int64 *); // rax
  unsigned int v60; // eax
  int IsSIMMessage; // eax
  bool v62; // zf
  int v63; // eax
  void (__fastcall **v64)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v65; // eax
  __int64 v66; // r9
  __int64 v67; // rbx
  int v68; // eax
  __int64 v69; // r9
  void (__fastcall **v70)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v71)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v72; // eax
  int v73; // eax
  void (__fastcall **v74)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v75; // eax
  __int64 v76; // r9
  _DWORD *v77; // rax
  int v78; // ecx
  void (__fastcall **v79)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v80)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v81)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v82; // eax
  __int64 v83; // r9
  _DWORD *v84; // rax
  int v85; // ecx
  void (__fastcall **v86)(struct ISmMessage *, GUID *, __int64 *); // rax
  void (__fastcall **v87)(struct ISmMessage *, GUID *, __int64 *); // rax
  int v88; // eax
  BSTR v90; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v91; // [rsp+38h] [rbp-C8h] BYREF
  void *v92; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v93; // [rsp+48h] [rbp-B8h]
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v95; // [rsp+60h] [rbp-A0h] BYREF
  int v96; // [rsp+68h] [rbp-98h] BYREF
  __int64 v97; // [rsp+70h] [rbp-90h] BYREF
  struct ISmEntryId *v98; // [rsp+78h] [rbp-88h] BYREF
  int v99; // [rsp+80h] [rbp-80h] BYREF
  __int64 v100; // [rsp+88h] [rbp-78h] BYREF
  struct ISmEntryId *v101; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v102[4]; // [rsp+98h] [rbp-68h] BYREF
  int v103; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v104; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v105; // [rsp+A4h] [rbp-5Ch] BYREF
  int v106; // [rsp+A8h] [rbp-58h] BYREF
  int v107; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v108; // [rsp+B0h] [rbp-50h] BYREF
  int v109; // [rsp+B4h] [rbp-4Ch] BYREF
  int v110; // [rsp+B8h] [rbp-48h] BYREF
  int v111; // [rsp+BCh] [rbp-44h] BYREF
  int v112; // [rsp+C0h] [rbp-40h] BYREF
  int v113; // [rsp+C4h] [rbp-3Ch] BYREF
  int v114; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v115; // [rsp+CCh] [rbp-34h] BYREF
  void *v116[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v117; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v118; // [rsp+F0h] [rbp-10h] BYREF
  void *v119; // [rsp+F8h] [rbp-8h]
  void *Block[2]; // [rsp+100h] [rbp+0h] BYREF
  char v121; // [rsp+110h] [rbp+10h] BYREF
  __int64 v122; // [rsp+120h] [rbp+20h] BYREF
  __int64 v123; // [rsp+128h] [rbp+28h] BYREF
  __int64 v124; // [rsp+130h] [rbp+30h] BYREF
  void *v125; // [rsp+138h] [rbp+38h] BYREF
  void **v126; // [rsp+140h] [rbp+40h] BYREF
  char v127; // [rsp+148h] [rbp+48h]
  __int64 v128; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v129[4]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v130[4]; // [rsp+178h] [rbp+78h] BYREF
  _QWORD v131[4]; // [rsp+198h] [rbp+98h] BYREF
  _QWORD v132[4]; // [rsp+1B8h] [rbp+B8h] BYREF
  va_list Arguments[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  OLECHAR *v134[4]; // [rsp+1E8h] [rbp+E8h] BYREF
  OLECHAR *psz[4]; // [rsp+208h] [rbp+108h] BYREF
  __int64 v136; // [rsp+228h] [rbp+128h] BYREF
  int v137; // [rsp+230h] [rbp+130h]
  __int64 v138; // [rsp+238h] [rbp+138h] BYREF
  int v139; // [rsp+240h] [rbp+140h]
  va_list v140[2]; // [rsp+248h] [rbp+148h] BYREF
  unsigned __int16 v141[12]; // [rsp+258h] [rbp+158h] BYREF

  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      ChatOperationContextGetMessageProperties,
      a3,
      1,
      v140);
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      Chat_ChatOperationContext_GetMessageProperties_START,
      a3,
      1,
      v140);
  v102[1] = 1;
  *a3 = 0;
  *a4 = 0;
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&v92);
  v127 = 1;
  v126 = &v92;
  if ( (unsigned __int8)utl::vector<UdmPropertyValue,utl::allocator<UdmPropertyValue>>::_Resize<,0>(&v92, 26) )
  {
    v11 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v114 = 0;
    v12 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v11[3])(a2, &v114);
    v7 = v12;
    if ( v12 < 0 )
    {
      v8 = 1135;
LABEL_9:
      v9 = (unsigned int)v12;
LABEL_10:
      v10 = 1;
      goto LABEL_11;
    }
    *((_DWORD *)v92 + 2) = v114 == 0;
    *((_DWORD *)v92 + 1) = 302055425;
    *(_DWORD *)v92 = 0;
    v13 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v103 = 0;
    v12 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v13[54])(a2, &v103);
    v7 = v12;
    if ( v12 < 0 )
    {
      v8 = 1143;
      goto LABEL_9;
    }
    *((_DWORD *)v92 + 8) = v103 == 0;
    *((_DWORD *)v92 + 7) = 302120961;
    *((_DWORD *)v92 + 6) = 0;
    v14 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v128 = 0;
    v12 = ((__int64 (__fastcall *)(struct ISmMessage *, __int64 *))v14[17])(a2, &v128);
    v7 = v12;
    if ( v12 < 0 )
    {
      v8 = 1151;
      goto LABEL_9;
    }
    *((_QWORD *)v92 + 7) = v128;
    *((_DWORD *)v92 + 13) = 302841860;
    *((_DWORD *)v92 + 12) = 0;
    v15 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v115 = 0;
    v12 = ((__int64 (__fastcall *)(struct ISmMessage *, unsigned int *))v15[70])(a2, &v115);
    v7 = v12;
    if ( v12 < 0 )
    {
      v8 = 1159;
      goto LABEL_9;
    }
    memset(v141, 0, 22);
    v16 = StringCchPrintfW(v141, 0xBu, L"%d", v115);
    v7 = v16;
    if ( v16 < 0 )
    {
      Log_HREvent(
        (unsigned int)v16,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
        29);
      v8 = 1162;
      v9 = v7;
      goto LABEL_10;
    }
    v12 = DupString((char *)v92 + 80, v141);
    v7 = v12;
    if ( v12 < 0 )
    {
      v8 = 1164;
      goto LABEL_9;
    }
    *((_DWORD *)v92 + 19) = 302383109;
    *((_DWORD *)v92 + 18) = 0;
    v17 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v90 = 0;
    v18 = ((__int64 (__fastcall *)(struct ISmMessage *, BSTR *))v17[14])(a2, &v90);
    v7 = v18;
    if ( v18 < 0 )
    {
      Log_HREvent(
        (unsigned int)v18,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        1170);
LABEL_24:
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v90);
      goto LABEL_182;
    }
    v19 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v91 = 0;
    (*v19)(a2, &GUID_0ba6a6c2_14db_456a_a2bf_c4de45d6a8a6, &v91);
    v20 = v91;
    if ( v91 )
    {
      v97 = 0;
      v21 = *(int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v91 + 944LL);
      v22 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v97);
      if ( v21(v20, v22) >= 0 && v97 )
      {
        StringRes = LoadStringRes(v23, 0x32CCu, v24);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v129);
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 v129,
                                 v90) )
        {
          v7 = -2147024882;
          Log_HREvent(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            1187);
LABEL_30:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v129);
LABEL_31:
          p_bstrString = (BSTR *)&v97;
LABEL_32:
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(p_bstrString);
LABEL_33:
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v91);
          goto LABEL_24;
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v131);
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 v131,
                                 v97) )
        {
          v7 = -2147024882;
          Log_HREvent(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            1190);
LABEL_36:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v131);
          goto LABEL_30;
        }
        Arguments[0] = (va_list)v129[0];
        Arguments[1] = (va_list)v131[0];
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(psz);
        FormattedString = GetFormattedString(StringRes, Arguments);
        v7 = FormattedString;
        if ( FormattedString < 0 )
        {
          v28 = 1197;
          v29 = 1;
          v30 = (unsigned int)FormattedString;
LABEL_39:
          Log_HREvent(
            v30,
            v29,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            v28);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(psz);
          goto LABEL_36;
        }
        v31 = SysAllocString(psz[0]);
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::reset(
          &v90,
          v31);
        if ( !v90 )
        {
          v7 = -2147024882;
          v28 = 1200;
          v30 = 2147942414LL;
          v29 = 0;
          goto LABEL_39;
        }
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(psz);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v131);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v129);
      }
      v32 = v91;
      v100 = 0;
      v33 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v91 + 984LL);
      v34 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v100);
      v35 = v33(v32, v34);
      v7 = v35;
      if ( v35 < 0 )
      {
        if ( v35 != -2147023728 )
        {
          Log_HREvent(
            (unsigned int)v35,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            1226);
          goto LABEL_48;
        }
      }
      else if ( v100 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v130);
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 v130,
                                 v90) )
        {
          v7 = -2147024882;
          Log_HREvent(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            1211);
LABEL_47:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v130);
LABEL_48:
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v100);
          goto LABEL_31;
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v132);
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 v132,
                                 v100) )
        {
          v7 = -2147024882;
          Log_HREvent(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            1214);
LABEL_51:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v132);
          goto LABEL_47;
        }
        v140[0] = (va_list)v130[0];
        v140[1] = (va_list)v132[0];
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v134);
        v36 = GetFormattedString(L"%1!s! \r\n%2!s!", v140);
        v7 = v36;
        if ( v36 < 0 )
        {
          v37 = 1219;
          v38 = 1;
          v39 = (unsigned int)v36;
LABEL_54:
          Log_HREvent(
            v39,
            v38,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            v37);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v134);
          goto LABEL_51;
        }
        v40 = SysAllocString(v134[0]);
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::reset(
          &v90,
          v40);
        if ( !v90 )
        {
          v7 = -2147024882;
          v37 = 1222;
          v39 = 2147942414LL;
          v38 = 0;
          goto LABEL_54;
        }
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v134);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v132);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v130);
      }
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v100);
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v97);
    }
    v41 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v99 = 0;
    v42 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v41[24])(a2, &v99);
    v7 = v42;
    if ( v42 < 0 )
    {
      v43 = 1231;
LABEL_61:
      Log_HREvent(
        (unsigned int)v42,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        v43);
      goto LABEL_33;
    }
    v42 = DupString((char *)v92 + 104, v90);
    v7 = v42;
    if ( v42 < 0 )
    {
      v43 = 1233;
      goto LABEL_61;
    }
    v44 = 302252037;
    v96 = 0;
    v45 = 0;
    if ( v99 == 2 )
      v44 = 302776325;
    *((_DWORD *)v92 + 25) = v44;
    *((_DWORD *)v92 + 24) = 0;
    v46 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v113 = 1;
    v42 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v46[8])(a2, &v113);
    v7 = v42;
    if ( v42 < 0 )
    {
      v43 = 1243;
      goto LABEL_61;
    }
    if ( !v113 )
    {
      v47 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
      v105 = 0;
      v42 = ((__int64 (__fastcall *)(struct ISmMessage *, unsigned int *))v47[68])(a2, &v105);
      v7 = v42;
      if ( v42 < 0 )
      {
        v43 = 1247;
        goto LABEL_61;
      }
      v48 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
      v104 = 0;
      v42 = ((__int64 (__fastcall *)(struct ISmMessage *, unsigned int *))v48[79])(a2, &v104);
      v7 = v42;
      if ( v42 < 0 )
      {
        v43 = 1250;
        goto LABEL_61;
      }
      v42 = SmMessageStatusToChatMessageStatus(v105, v103 == 0, v104, &v96);
      v7 = v42;
      if ( v42 < 0 )
      {
        v43 = 1252;
        goto LABEL_61;
      }
      v45 = v96;
    }
    *((_DWORD *)v92 + 32) = v45;
    *((_DWORD *)v92 + 31) = 302317570;
    *((_DWORD *)v92 + 30) = 0;
    v49 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v122 = 0;
    v42 = ((__int64 (__fastcall *)(struct ISmMessage *, __int64 *))v49[96])(a2, &v122);
    v7 = v42;
    if ( v42 < 0 )
    {
      v43 = 1261;
      goto LABEL_61;
    }
    *((_QWORD *)v92 + 19) = v122;
    *((_DWORD *)v92 + 37) = 302579715;
    *((_DWORD *)v92 + 36) = 0;
    v50 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v123 = 0;
    v42 = ((__int64 (__fastcall *)(struct ISmMessage *, __int64 *))v50[97])(a2, &v123);
    v7 = v42;
    if ( v42 < 0 )
    {
      v43 = 1269;
      goto LABEL_61;
    }
    *((_QWORD *)v92 + 22) = v123;
    *((_DWORD *)v92 + 43) = 302645251;
    *((_DWORD *)v92 + 42) = 0;
    v51 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v106 = 0;
    v42 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v51[45])(a2, &v106);
    v7 = v42;
    if ( v42 < 0 )
    {
      v43 = 1277;
      goto LABEL_61;
    }
    *((_DWORD *)v92 + 50) = v106 != 0;
    *((_DWORD *)v92 + 49) = 302448641;
    *((_DWORD *)v92 + 48) = 0;
    v52 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    bstrString = 0;
    v53 = ((__int64 (__fastcall *)(struct ISmMessage *, BSTR *))v52[82])(a2, &bstrString);
    v54 = v53;
    if ( v53 < 0 )
    {
      Log_HREvent(
        (unsigned int)v53,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        1285);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v91 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v90 )
        SysFreeString(v90);
      tlx::_UndoSolo__lambda_afbe8a15375f6be8cb1341b9a12cfcce___::__UndoSolo__lambda_afbe8a15375f6be8cb1341b9a12cfcce___(&v126);
      v55 = v92;
      if ( v92 == (void *)-1LL )
        goto LABEL_178;
      goto LABEL_177;
    }
    v56 = DupString((char *)v92 + 224, bstrString);
    v7 = v56;
    if ( v56 < 0 )
    {
      v57 = 1287;
LABEL_95:
      v58 = (unsigned int)v56;
LABEL_96:
      Log_HREvent(
        v58,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        v57);
LABEL_97:
      p_bstrString = &bstrString;
      goto LABEL_32;
    }
    *((_DWORD *)v92 + 55) = 302710789;
    *((_DWORD *)v92 + 54) = 0;
    v59 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v124 = 0;
    v56 = ((__int64 (__fastcall *)(struct ISmMessage *, __int64 *))v59[19])(a2, &v124);
    v7 = v56;
    if ( v56 < 0 )
    {
      v57 = 1293;
      goto LABEL_95;
    }
    *((_QWORD *)v92 + 31) = v124;
    *((_DWORD *)v92 + 61) = 302186500;
    *((_DWORD *)v92 + 60) = 0;
    v60 = (*(__int64 (__fastcall **)(struct ISmMessage *))(*(_QWORD *)a2 + 736LL))(a2);
    *((_QWORD *)v92 + 34) = v60;
    *((_DWORD *)v92 + 67) = 303104003;
    *((_DWORD *)v92 + 66) = 0;
    IsSIMMessage = Messaging_IsSIMMessage(a2);
    *((_DWORD *)v92 + 74) = IsSIMMessage;
    *((_DWORD *)v92 + 73) = 302972929;
    *((_DWORD *)v92 + 72) = 0;
    if ( v99 > 10001 )
    {
      switch ( v99 )
      {
        case 10002:
          v63 = 5;
          break;
        case 10003:
          v63 = 4;
          break;
        case 10004:
          v63 = 6;
          break;
        default:
          if ( v99 != 10005 && v99 != 10006 )
          {
            v62 = v99 == 10007;
LABEL_112:
            if ( !v62 )
            {
              v7 = -2147024809;
              Log_HREvent(
                2147942487LL,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
                580);
              v57 = 1316;
              v58 = 2147942487LL;
              goto LABEL_96;
            }
          }
LABEL_104:
          v63 = 0;
          break;
      }
    }
    else
    {
      if ( v99 != 10001 )
      {
        if ( (unsigned int)v99 >= 6 )
        {
          v62 = v99 == 10000;
          goto LABEL_112;
        }
        goto LABEL_104;
      }
      v63 = 3;
    }
    if ( !v63 )
      v63 = (*(__int64 (__fastcall **)(struct ISmMessage *))(*(_QWORD *)a2 + 672LL))(a2);
    *((_DWORD *)v92 + 80) = v63;
    *((_DWORD *)v92 + 79) = 302907394;
    *((_DWORD *)v92 + 78) = 0;
    v64 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v95 = 0;
    v65 = ((__int64 (__fastcall *)(struct ISmMessage *, BSTR *))v64[86])(a2, &v95);
    v7 = v65;
    if ( v65 < 0 )
    {
      v66 = 1326;
LABEL_121:
      Log_HREvent(
        (unsigned int)v65,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        v66);
LABEL_122:
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v95);
      goto LABEL_97;
    }
    v65 = DupString((char *)v92 + 344, v95);
    v7 = v65;
    if ( v65 < 0 )
    {
      v66 = 1328;
      goto LABEL_121;
    }
    *((_DWORD *)v92 + 85) = 303038469;
    *((_DWORD *)v92 + 84) = 0;
    v67 = (*(__int64 (__fastcall **)(struct ISmMessage *))(*(_QWORD *)a2 + 704LL))(a2);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v116);
    v68 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
            v116,
            L"%I64u",
            v67);
    v7 = v68;
    if ( v68 < 0 )
    {
      v69 = 1337;
LABEL_127:
      Log_HREvent(
        (unsigned int)v68,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        v69);
LABEL_128:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v116);
      goto LABEL_122;
    }
    v68 = DupString((char *)v92 + 368, v116[0]);
    v7 = v68;
    if ( v68 < 0 )
    {
      v69 = 1339;
      goto LABEL_127;
    }
    *((_DWORD *)v92 + 91) = 303890437;
    *((_DWORD *)v92 + 90) = 0;
    v70 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v107 = 0;
    v68 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v70[31])(a2, &v107);
    v7 = v68;
    if ( v68 < 0 )
    {
      v69 = 1346;
      goto LABEL_127;
    }
    *((_DWORD *)v92 + 98) = v107;
    *((_DWORD *)v92 + 97) = 303169537;
    *((_DWORD *)v92 + 96) = 0;
    v71 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v108 = 0;
    v125 = 0;
    v68 = ((__int64 (__fastcall *)(struct ISmMessage *, unsigned int *, void **))v71[94])(a2, &v108, &v125);
    v7 = v68;
    if ( v68 < 0 )
    {
      v69 = 1357;
      goto LABEL_127;
    }
    v118 = v108;
    v119 = v125;
    v96 = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(Block);
    v72 = ParseThreadingInfo(&v118, &v96, Block);
    v54 = v72;
    if ( v72 < 0 )
    {
      Log_HREvent(
        (unsigned int)v72,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        1365);
      goto LABEL_164;
    }
    *((_DWORD *)v92 + 104) = v96;
    *((_DWORD *)v92 + 103) = 303235074;
    *((_DWORD *)v92 + 102) = 0;
    v73 = DupString((char *)v92 + 440, Block[0]);
    v7 = v73;
    if ( v73 < 0 )
    {
      Log_HREvent(
        (unsigned int)v73,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        1373);
LABEL_139:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Block);
      goto LABEL_128;
    }
    *((_DWORD *)v92 + 109) = 303300613;
    *((_DWORD *)v92 + 108) = 0;
    v74 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
    v98 = 0;
    v75 = ((__int64 (__fastcall *)(struct ISmMessage *, struct ISmEntryId **))v74[51])(a2, &v98);
    v7 = v75;
    if ( v75 >= 0 )
    {
      v136 = 0;
      v137 = 0;
      Messaging_SmEntryIdToUdmObjectId(v98, (struct UdmObjectId *)&v136);
      v77 = v92;
      v78 = v137;
      *((_QWORD *)v92 + 58) = v136;
      v77[118] = v78;
      *((_DWORD *)v92 + 115) = 303431687;
      *((_DWORD *)v92 + 114) = 0;
      v79 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
      v109 = 0;
      v75 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v79[75])(a2, &v109);
      v7 = v75;
      if ( v75 >= 0 )
      {
        *((_DWORD *)v92 + 122) = v109;
        *((_DWORD *)v92 + 121) = 303366145;
        *((_DWORD *)v92 + 120) = 0;
        v80 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
        v110 = 0;
        v75 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v80[43])(a2, &v110);
        v7 = v75;
        if ( v75 >= 0 )
        {
          *((_DWORD *)v92 + 128) = v110 != 0;
          *((_DWORD *)v92 + 127) = 303497217;
          *((_DWORD *)v92 + 126) = 0;
          v81 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
          v101 = 0;
          v82 = ((__int64 (__fastcall *)(struct ISmMessage *, struct ISmEntryId **))v81[23])(a2, &v101);
          v7 = v82;
          if ( v82 >= 0 )
          {
            v138 = 0;
            v139 = 0;
            Messaging_SmEntryIdToUdmObjectId(v101, (struct UdmObjectId *)&v138);
            v84 = v92;
            v85 = v139;
            v96 = 0;
            *((_QWORD *)v92 + 67) = v138;
            v84[136] = v85;
            *((_DWORD *)v92 + 133) = 303562759;
            *((_DWORD *)v92 + 132) = 0;
            v82 = SmMessageTypeToChatMessageOperatorKind((unsigned int)v99, &v96);
            v7 = v82;
            if ( v82 >= 0 )
            {
              *((_DWORD *)v92 + 140) = v96;
              *((_DWORD *)v92 + 139) = 303628290;
              *((_DWORD *)v92 + 138) = 0;
              v86 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
              v111 = 0;
              v82 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v86[104])(a2, &v111);
              v7 = v82;
              if ( v82 >= 0 )
              {
                *((_DWORD *)v92 + 146) = v111;
                *((_DWORD *)v92 + 145) = 303693825;
                *((_DWORD *)v92 + 144) = 0;
                v87 = *(void (__fastcall ***)(struct ISmMessage *, GUID *, __int64 *))a2;
                v112 = 0;
                v82 = ((__int64 (__fastcall *)(struct ISmMessage *, int *))v87[39])(a2, &v112);
                v7 = v82;
                if ( v82 >= 0 )
                {
                  v118 = 0;
                  v119 = 0;
                  *((_DWORD *)v92 + 152) = v112;
                  *((_DWORD *)v92 + 151) = 303759361;
                  *((_DWORD *)v92 + 150) = 0;
                  if ( v92 != v93 )
                  {
                    v119 = v92;
                    v118 = 0xAAAAAAAAAAAAAAABuLL * ((v93 - (_BYTE *)v92) >> 3);
                  }
                  v88 = Udm::ReformUdmPropsForMidl(&v118, a4);
                  v54 = v88;
                  if ( v88 < 0 )
                  {
                    Log_HREvent(
                      (unsigned int)v88,
                      1,
                      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
                      1448);
                    if ( v101 )
                      (*(void (__fastcall **)(struct ISmEntryId *))(*(_QWORD *)v101 + 16LL))(v101);
                    if ( v98 )
                      (*(void (__fastcall **)(struct ISmEntryId *))(*(_QWORD *)v98 + 16LL))(v98);
LABEL_164:
                    if ( Block[0] != &v121 )
                      operator delete(Block[0]);
                    if ( v116[0] != &v117 )
                      operator delete(v116[0]);
                    if ( v95 )
                      SysFreeString(v95);
                    if ( bstrString )
                      SysFreeString(bstrString);
                    if ( v91 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                    if ( v90 )
                      SysFreeString(v90);
                    tlx::_UndoSolo__lambda_afbe8a15375f6be8cb1341b9a12cfcce___::__UndoSolo__lambda_afbe8a15375f6be8cb1341b9a12cfcce___(&v126);
                    v55 = v92;
                    if ( v92 == (void *)-1LL )
                      goto LABEL_178;
LABEL_177:
                    v93 = v55;
                    operator delete(v55);
LABEL_178:
                    lambda_ccf03758d40c6368aa84169c5e431fbe_::operator()();
                    return v54;
                  }
                  v82 = ULongLongToULong(0xAAAAAAAAAAAAAAABuLL * ((v93 - (_BYTE *)v92) >> 3), a3);
                  v7 = v82;
                  if ( v82 >= 0 )
                  {
                    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v101);
                    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v98);
                    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Block);
                    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v116);
                    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v95);
                    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&bstrString);
                    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v91);
                    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v90);
                    v7 = 0;
                    goto LABEL_182;
                  }
                  v83 = 1450;
                }
                else
                {
                  v83 = 1439;
                }
              }
              else
              {
                v83 = 1431;
              }
            }
            else
            {
              v83 = 1422;
            }
          }
          else
          {
            v83 = 1410;
          }
          Log_HREvent(
            (unsigned int)v82,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            v83);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v101);
          goto LABEL_143;
        }
        v76 = 1401;
      }
      else
      {
        v76 = 1392;
      }
    }
    else
    {
      v76 = 1380;
    }
    Log_HREvent(
      (unsigned int)v75,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
      v76);
LABEL_143:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v98);
    goto LABEL_139;
  }
  v7 = -2147024882;
  v8 = 1130;
  v9 = 2147942414LL;
  v10 = 0;
LABEL_11:
  Log_HREvent(
    v9,
    v10,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
    v8);
LABEL_182:
  tlx::_UndoSolo__lambda_afbe8a15375f6be8cb1341b9a12cfcce___::__UndoSolo__lambda_afbe8a15375f6be8cb1341b9a12cfcce___(&v126);
  utl::vector<UdmPropertyValue,utl::allocator<UdmPropertyValue>>::_Uninit(&v92);
  tlx::_UndoSolo__lambda_ccf03758d40c6368aa84169c5e431fbe___::__UndoSolo__lambda_ccf03758d40c6368aa84169c5e431fbe___(v102);
  return v7;
}

```

## disassembly

```asm
0x18003cf20  mov     [rsp-8+arg_0], rbx
0x18003cf25  push    rbp
0x18003cf26  push    rsi
0x18003cf27  push    rdi
0x18003cf28  push    r12
0x18003cf2a  push    r13
0x18003cf2c  push    r14
0x18003cf2e  push    r15
0x18003cf30  lea     rbp, [rsp-180h]
0x18003cf38  sub     rsp, 280h
0x18003cf3f  mov     rax, cs:__security_cookie
0x18003cf46  xor     rax, rsp
0x18003cf49  mov     [rbp+1B0h+var_40], rax
0x18003cf50  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 10h
0x18003cf57  mov     r14, r9
0x18003cf5a  mov     r15, r8
0x18003cf5d  mov     rsi, rdx
0x18003cf60  mov     r13d, 1
0x18003cf66  jz      short loc_18003CF8A
0x18003cf68  lea     rax, [rbp+1B0h+var_68]
0x18003cf6f  mov     r9d, r13d
0x18003cf72  lea     rdx, ChatOperationContextGetMessageProperties
0x18003cf79  mov     [rsp+2B0h+var_290], rax
0x18003cf7e  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x18003cf85  call    McGenEventWrite_EventWriteTransfer
0x18003cf8a  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, r13b
0x18003cf91  jz      short loc_18003CFB5
0x18003cf93  lea     rax, [rbp+1B0h+var_68]
0x18003cf9a  mov     r9d, r13d
0x18003cf9d  lea     rdx, Chat_ChatOperationContext_GetMessageProperties_START
0x18003cfa4  mov     [rsp+2B0h+var_290], rax
0x18003cfa9  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x18003cfb0  call    McGenEventWrite_EventWriteTransfer
0x18003cfb5  xor     r12d, r12d
0x18003cfb8  mov     [rbp+1B0h+var_217], r13b
0x18003cfbc  mov     [r15], r12d
0x18003cfbf  lea     rcx, [rsp+2B0h+var_270]
0x18003cfc4  mov     [r14], r12
0x18003cfc7  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x18003cfcc  lea     rcx, [rsp+2B0h+var_270]
0x18003cfd1  mov     [rbp+1B0h+var_168], r13b
0x18003cfd5  mov     [rbp+1B0h+var_170], rcx
0x18003cfd9  lea     edx, [r12+1Ah]
0x18003cfde  lea     rcx, [rsp+2B0h+var_270]
0x18003cfe3  call    ??$_Resize@$$V$0A@@?$vector@UUdmPropertyValue@@V?$allocator@UUdmPropertyValue@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<UdmPropertyValue,utl::allocator<UdmPropertyValue>>::_Resize<,0>(unsigned __int64)
0x18003cfe8  test    al, al
0x18003cfea  jnz     short loc_18003CFFD
0x18003cfec  mov     ebx, 8007000Eh
0x18003cff1  mov     r9d, 46Ah
0x18003cff7  mov     ecx, ebx
0x18003cff9  xor     edx, edx
0x18003cffb  jmp     short loc_18003D025
0x18003cffd  mov     rax, [rsi]
0x18003d000  lea     rdx, [rbp+1B0h+var_1E8]
0x18003d004  mov     rcx, rsi
0x18003d007  mov     [rbp+1B0h+var_1E8], r12d
0x18003d00b  mov     rax, [rax+18h]
0x18003d00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d014  mov     ebx, eax
0x18003d016  test    eax, eax
0x18003d018  jns     short loc_18003D036
0x18003d01a  mov     r9d, 46Fh
0x18003d020  mov     ecx, eax
0x18003d022  mov     edx, r13d
0x18003d025  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003d02c  call    Log_HREvent
0x18003d031  jmp     loc_18003E18E
0x18003d036  cmp     [rbp+1B0h+var_1E8], r12d
0x18003d03a  lea     rdx, [rbp+1B0h+var_214]
0x18003d03e  mov     rax, [rsp+2B0h+var_270]
0x18003d043  mov     ecx, r12d
0x18003d046  setz    cl
0x18003d049  mov     [rax+8], ecx
0x18003d04c  mov     rcx, rsi
0x18003d04f  mov     rax, [rsp+2B0h+var_270]
0x18003d054  mov     dword ptr [rax+4], 12010001h
0x18003d05b  mov     rax, [rsp+2B0h+var_270]
0x18003d060  mov     [rax], r12d
0x18003d063  mov     rax, [rsi]
0x18003d066  mov     [rbp+1B0h+var_214], r12d
0x18003d06a  mov     rax, [rax+1B0h]
0x18003d071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d076  mov     ebx, eax
0x18003d078  test    eax, eax
0x18003d07a  jns     short loc_18003D084
0x18003d07c  mov     r9d, 477h
0x18003d082  jmp     short loc_18003D020
0x18003d084  cmp     [rbp+1B0h+var_214], r12d
0x18003d088  lea     rdx, [rbp+1B0h+var_160]
0x18003d08c  mov     rax, [rsp+2B0h+var_270]
0x18003d091  mov     ecx, r12d
0x18003d094  setz    cl
0x18003d097  mov     [rax+20h], ecx
0x18003d09a  mov     rcx, rsi
0x18003d09d  mov     rax, [rsp+2B0h+var_270]
0x18003d0a2  mov     dword ptr [rax+1Ch], 12020001h
0x18003d0a9  mov     rax, [rsp+2B0h+var_270]
0x18003d0ae  mov     [rax+18h], r12d
0x18003d0b2  mov     rax, [rsi]
0x18003d0b5  mov     [rbp+1B0h+var_160], r12
0x18003d0b9  mov     rax, [rax+88h]
0x18003d0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0c5  mov     ebx, eax
0x18003d0c7  test    eax, eax
0x18003d0c9  jns     short loc_18003D0D6
0x18003d0cb  mov     r9d, 47Fh
0x18003d0d1  jmp     loc_18003D020
0x18003d0d6  mov     rax, [rsp+2B0h+var_270]
0x18003d0db  lea     rdx, [rbp+1B0h+var_1E4]
0x18003d0df  mov     rcx, [rbp+1B0h+var_160]
0x18003d0e3  mov     [rax+38h], rcx
0x18003d0e7  mov     rcx, rsi
0x18003d0ea  mov     rax, [rsp+2B0h+var_270]
0x18003d0ef  mov     dword ptr [rax+34h], 120D0004h
0x18003d0f6  mov     rax, [rsp+2B0h+var_270]
0x18003d0fb  mov     [rax+30h], r12d
0x18003d0ff  mov     rax, [rsi]
0x18003d102  mov     [rbp+1B0h+var_1E4], r12d
0x18003d106  mov     rax, [rax+230h]
0x18003d10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d112  mov     ebx, eax
0x18003d114  test    eax, eax
0x18003d116  jns     short loc_18003D123
0x18003d118  mov     r9d, 487h
0x18003d11e  jmp     loc_18003D020
0x18003d123  mov     r9d, [rbp+1B0h+var_1E4]
0x18003d127  lea     r8, aD; "%d"
0x18003d12e  xor     eax, eax
0x18003d130  lea     rcx, [rbp+1B0h+var_58]; unsigned __int16 *
0x18003d137  xorps   xmm0, xmm0
0x18003d13a  movups  xmmword ptr [rbp+1B0h+var_58], xmm0
0x18003d141  mov     qword ptr [rbp+1B0h+var_58+0Eh], rax
0x18003d148  lea     edx, [rax+0Bh]; unsigned __int64
0x18003d14b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d150  mov     ebx, eax
0x18003d152  test    eax, eax
0x18003d154  jns     short loc_18003D17A
0x18003d156  mov     r9d, 1Dh
0x18003d15c  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003d163  mov     edx, r13d
0x18003d166  mov     ecx, eax
0x18003d168  call    Log_HREvent
0x18003d16d  mov     r9d, 48Ah
0x18003d173  mov     ecx, ebx
0x18003d175  jmp     loc_18003D022
0x18003d17a  mov     rcx, [rsp+2B0h+var_270]
0x18003d17f  lea     rdx, [rbp+1B0h+var_58]
0x18003d186  add     rcx, 50h ; 'P'
0x18003d18a  call    cs:__imp_DupString
0x18003d190  mov     ebx, eax
0x18003d192  test    eax, eax
0x18003d194  jns     short loc_18003D1A1
0x18003d196  mov     r9d, 48Ch
0x18003d19c  jmp     loc_18003D020
0x18003d1a1  mov     rax, [rsp+2B0h+var_270]
0x18003d1a6  lea     rdx, [rsp+2B0h+var_280]
0x18003d1ab  mov     rcx, rsi
0x18003d1ae  mov     dword ptr [rax+4Ch], 12060005h
0x18003d1b5  mov     rax, [rsp+2B0h+var_270]
0x18003d1ba  mov     [rax+48h], r12d
0x18003d1be  mov     rax, [rsi]
0x18003d1c1  mov     [rsp+2B0h+var_280], r12
0x18003d1c6  mov     rax, [rax+70h]
0x18003d1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1cf  mov     ebx, eax
0x18003d1d1  test    eax, eax
0x18003d1d3  jns     short loc_18003D1FB
0x18003d1d5  mov     r9d, 492h
0x18003d1db  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003d1e2  mov     edx, r13d
0x18003d1e5  mov     ecx, eax
0x18003d1e7  call    Log_HREvent
0x18003d1ec  lea     rcx, [rsp+2B0h+var_280]
0x18003d1f1  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x18003d1f6  jmp     loc_18003E18E
0x18003d1fb  mov     rax, [rsi]
0x18003d1fe  lea     r8, [rsp+2B0h+var_278]
0x18003d203  lea     rdx, _GUID_0ba6a6c2_14db_456a_a2bf_c4de45d6a8a6
0x18003d20a  mov     [rsp+2B0h+var_278], r12
0x18003d20f  mov     rcx, rsi
0x18003d212  mov     rax, [rax]
0x18003d215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d21a  mov     rbx, [rsp+2B0h+var_278]
0x18003d21f  test    rbx, rbx
0x18003d222  jz      loc_18003D56E
0x18003d228  mov     [rsp+2B0h+var_240], r12
0x18003d22d  lea     rcx, [rsp+2B0h+var_240]
0x18003d232  mov     rax, [rbx]
0x18003d235  mov     rdi, [rax+3B0h]
0x18003d23c  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18003d241  mov     rdx, rax
0x18003d244  mov     rcx, rbx
0x18003d247  mov     rax, rdi
0x18003d24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d24f  test    eax, eax
0x18003d251  js      loc_18003D3CA
0x18003d257  cmp     [rsp+2B0h+var_240], r12
0x18003d25c  jz      loc_18003D3CA
0x18003d262  mov     edx, 32CCh; unsigned int
0x18003d267  call    ?LoadStringRes@@YAPEBGPEAUHINSTANCE__@@IPEBG@Z; LoadStringRes(HINSTANCE__ *,uint,ushort const *)
0x18003d26c  lea     rcx, [rbp+1B0h+var_158]; void *
0x18003d270  mov     rbx, rax
0x18003d273  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18003d278  mov     rdx, [rsp+2B0h+var_280]
0x18003d27d  lea     rcx, [rbp+1B0h+var_158]
0x18003d281  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18003d286  test    al, al
0x18003d288  jnz     short loc_18003D2C7
0x18003d28a  mov     ebx, 8007000Eh
0x18003d28f  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003d296  mov     ecx, ebx
0x18003d298  mov     r9d, 4A3h
0x18003d29e  xor     edx, edx
0x18003d2a0  call    Log_HREvent
0x18003d2a5  lea     rcx, [rbp+1B0h+var_158]; void *
0x18003d2a9  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003d2ae  lea     rcx, [rsp+2B0h+var_240]
0x18003d2b3  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x18003d2b8  lea     rcx, [rsp+2B0h+var_278]
0x18003d2bd  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18003d2c2  jmp     loc_18003D1EC
0x18003d2c7  lea     rcx, [rbp+1B0h+var_118]; void *
0x18003d2ce  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18003d2d3  mov     rdx, [rsp+2B0h+var_240]
0x18003d2d8  lea     rcx, [rbp+1B0h+var_118]
0x18003d2df  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18003d2e4  test    al, al
0x18003d2e6  jnz     short loc_18003D311
0x18003d2e8  mov     ebx, 8007000Eh
0x18003d2ed  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003d2f4  mov     ecx, ebx
0x18003d2f6  mov     r9d, 4A6h
0x18003d2fc  xor     edx, edx
0x18003d2fe  call    Log_HREvent
0x18003d303  lea     rcx, [rbp+1B0h+var_118]; void *
0x18003d30a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003d30f  jmp     short loc_18003D2A5
0x18003d311  mov     rax, [rbp+1B0h+var_158]
0x18003d315  lea     rcx, [rbp+1B0h+psz]; void *
0x18003d31c  mov     [rbp+1B0h+Arguments], rax
0x18003d323  mov     rax, [rbp+1B0h+var_118]
0x18003d32a  mov     [rbp+1B0h+var_D0], rax
0x18003d331  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18003d336  lea     r8, [rbp+1B0h+psz]
0x18003d33d  mov     rcx, rbx; lpSource
0x18003d340  lea     rdx, [rbp+1B0h+Arguments]; Arguments
0x18003d347  call    GetFormattedString
0x18003d34c  mov     ebx, eax
0x18003d34e  test    eax, eax
0x18003d350  jns     short loc_18003D377
0x18003d352  mov     r9d, 4ADh
0x18003d358  mov     edx, r13d
0x18003d35b  mov     ecx, eax
0x18003d35d  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003d364  call    Log_HREvent
0x18003d369  lea     rcx, [rbp+1B0h+psz]; void *
0x18003d370  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003d375  jmp     short loc_18003D303
0x18003d377  mov     rcx, [rbp+1B0h+psz]; psz
0x18003d37e  call    cs:__imp_SysAllocString
0x18003d384  mov     rdx, rax
0x18003d387  lea     rcx, [rsp+2B0h+var_280]
0x18003d38c  call    ?reset@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAAXPEAG@Z; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::reset(ushort *)
0x18003d391  cmp     [rsp+2B0h+var_280], r12
0x18003d396  jnz     short loc_18003D3A9
0x18003d398  mov     ebx, 8007000Eh
0x18003d39d  mov     r9d, 4B0h
0x18003d3a3  mov     ecx, ebx
0x18003d3a5  xor     edx, edx
0x18003d3a7  jmp     short loc_18003D35D
0x18003d3a9  lea     rcx, [rbp+1B0h+psz]; void *
0x18003d3b0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003d3b5  lea     rcx, [rbp+1B0h+var_118]; void *
0x18003d3bc  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003d3c1  lea     rcx, [rbp+1B0h+var_158]; void *
0x18003d3c5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003d3ca  mov     rdi, [rsp+2B0h+var_278]
0x18003d3cf  lea     rcx, [rbp+1B0h+var_228]
0x18003d3d3  mov     [rbp+1B0h+var_228], r12
0x18003d3d7  mov     rax, [rdi]
0x18003d3da  mov     rbx, [rax+3D8h]
0x18003d3e1  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18003d3e6  mov     rdx, rax
0x18003d3e9  mov     rcx, rdi
0x18003d3ec  mov     rax, rbx
0x18003d3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3f4  mov     ebx, eax
0x18003d3f6  test    eax, eax
0x18003d3f8  js      loc_18003D5AA
0x18003d3fe  cmp     [rbp+1B0h+var_228], r12
0x18003d402  jz      loc_18003D55B
0x18003d408  lea     rcx, [rbp+1B0h+var_138]; void *
0x18003d40c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18003d411  mov     rdx, [rsp+2B0h+var_280]
0x18003d416  lea     rcx, [rbp+1B0h+var_138]
0x18003d41a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18003d41f  test    al, al
0x18003d421  jnz     short loc_18003D455
0x18003d423  mov     ebx, 8007000Eh
0x18003d428  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
  ... truncated ...
```
