# EmailOperationContext::ModifyHelper(UdmItemUpdate const *,UdmOperationResult *)

- ea: `0x1800b2bf4`
- end: `0x1800b375c`
- name: `?ModifyHelper@EmailOperationContext@@AEAAJPEBUUdmItemUpdate@@PEAUUdmOperationResult@@@Z`
- size: `2920`
- prototype: `__int64 __fastcall(EmailOperationContext *__hidden this, const struct UdmItemUpdate *, struct UdmOperationResult *)`
- caller_count: `2`
- callee_count: `32`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800b3764`
- `0x1800b47a0`

## callees

- `0x1800049f0`
- `0x180008ee8`
- `0x180008f0c`
- `0x18000dfe0`
- `0x18000e1f8`
- `0x180022fa8`
- `0x1800278bc`
- `0x18003848c`
- `0x18003863c`
- `0x18003b470`
- `0x1800564f0`
- `0x18005e048`
- `0x180062fa8`
- `0x180064828`
- `0x180065bdc`
- `0x18007ba18`
- `0x18007d2d0`
- `0x18007d3ec`
- `0x1800811e8`
- `0x1800b0888`
- `0x1800b0ab4`
- `0x1800b0ae4`
- `0x1800b1084`
- `0x1800b1348`
- `0x1800b1560`
- `0x1800b2bf4`
- `0x1800b5ac4`
- `0x1800b6288`
- `0x1800f6c5c`
- `0x1800f8dbc`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `CEMAPI!SetConversationId` at `0x1800b32a6`
- `CEMAPI!SetConversationId` at `0x1800b32a6`
- `CEMAPI!HrGetOneProp` at `0x1800b324f`
- `CEMAPI!HrGetOneProp` at `0x1800b3665`
- `CEMAPI!HrGetOneProp` at `0x1800b324f`
- `CEMAPI!HrGetOneProp` at `0x1800b3665`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b3281`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b334b`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b3458`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b352a`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b368e`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b36c8`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b3281`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b334b`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b3458`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b352a`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b368e`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b36c8`
- `unistore!CreateStoreManager` at `0x1800b2ea9`
- `unistore!CreateStoreManager` at `0x1800b2ea9`
- `UserDataTypeHelperUtil!MapiIdToEmailUdmId` at `0x1800b3388`
- `UserDataTypeHelperUtil!MapiIdToEmailUdmId` at `0x1800b36ac`
- `UserDataTypeHelperUtil!MapiIdToEmailUdmId` at `0x1800b3388`
- `UserDataTypeHelperUtil!MapiIdToEmailUdmId` at `0x1800b36ac`

## string_xrefs

- `0x1800b2c58`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b2cb5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b2cf6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b2e7e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b2ebb`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b2f03`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b2fee`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b3155`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b3261`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b3332`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b33ea`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b34e2`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b361e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b3677`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`

## pseudocode

```c
__int64 __fastcall EmailOperationContext::ModifyHelper(
        EmailOperationContext *this,
        const struct UdmItemUpdate *a2,
        struct UdmOperationResult *a3)
{
  unsigned __int8 v5; // al
  bool v6; // zf
  unsigned int v7; // ebx
  const struct UdmMapiPropMap near *const *v8; // rax
  __int64 i; // rdi
  __int64 MapiMapEntryByUdmPropId; // rax
  unsigned int v11; // edx
  __int64 v12; // r11
  int v13; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  EmailHelper *v17; // rcx
  EmailHelper *v18; // rcx
  unsigned int *v19; // r8
  const struct UdmPropertyValue *v20; // r8
  _OWORD *v21; // rax
  LPBYTE lpb; // xmm1_8
  int v23; // eax
  _QWORD *v24; // r12
  int v25; // eax
  int v26; // r13d
  struct IMAPIProp *v27; // rdi
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // r10
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // rcx
  unsigned __int64 v38; // rcx
  unsigned int j; // r15d
  LPMAPIPROP v40; // rcx
  EmailHelper *v41; // rbx
  void **v42; // rax
  HRESULT v43; // eax
  __int64 v44; // r9
  void *v45; // rcx
  __int64 v46; // rdx
  EmailHelper *v47; // rdi
  __int64 (__fastcall *v48)(EmailHelper *, struct _SPropValue *, __int64, int *); // rbx
  int v49; // eax
  __int64 v50; // r9
  __int64 v51; // r9
  __int64 v52; // rdx
  __int64 v53; // rcx
  int v54; // eax
  __int64 v55; // rdx
  int ConversationId; // eax
  __int64 v57; // r9
  struct IMessage *v58; // rdx
  _DWORD *v59; // rcx
  __int64 (__fastcall *v60)(EmailHelper *, __int64 *, __int64, int *, void **); // rdi
  void **v61; // rax
  int v62; // eax
  __int64 v63; // r9
  __int64 v64; // rdx
  __int64 v65; // rcx
  int updated; // eax
  __int64 v67; // r9
  __int64 v68; // rdx
  __int64 v69; // rcx
  unsigned int v70; // eax
  unsigned int v71; // edi
  LPSPropValue *v72; // rax
  HRESULT OneProp; // eax
  __int64 v74; // r9
  int v75; // eax
  EmailOperationContext *v76; // rcx
  void **v78; // [rsp+20h] [rbp-E0h]
  LPMAPIPROP v79; // [rsp+40h] [rbp-C0h] BYREF
  struct IUSStoreManager *v80; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v81; // [rsp+50h] [rbp-B0h] BYREF
  LPMAPIPROP lpMapiProp; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 v83; // [rsp+60h] [rbp-A0h]
  EmailHelper *v84; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v85[24]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v86; // [rsp+88h] [rbp-78h] BYREF
  EmailOperationContext *v87; // [rsp+90h] [rbp-70h] BYREF
  int v88; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v90; // [rsp+A8h] [rbp-58h] BYREF
  int v91; // [rsp+B0h] [rbp-50h] BYREF
  EmailHelper *v92; // [rsp+B8h] [rbp-48h] BYREF
  struct _SPropValue *v93; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD *v94; // [rsp+C8h] [rbp-38h]
  _OWORD *v95; // [rsp+D0h] [rbp-30h]
  LPVOID v96; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v97[56]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v98; // [rsp+118h] [rbp+18h] BYREF
  __int64 v99; // [rsp+120h] [rbp+20h]
  unsigned int *v100[3]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v101; // [rsp+140h] [rbp+40h] BYREF
  const struct UdmMapiPropMap near *const *v102; // [rsp+148h] [rbp+48h]
  struct _SPropValue v103; // [rsp+150h] [rbp+50h] BYREF

  v87 = this;
  *(_DWORD *)a3 = 0;
  v101 = 0;
  LODWORD(v102) = 0;
  v5 = operator==((char *)a2 + 16, &v101);
  v6 = *(_DWORD *)a2 == 5;
  v83 = v5;
  if ( v6 )
  {
    v101 = 11;
    v8 = &s_EmailFolder_PropMap;
LABEL_6:
    v102 = v8;
    utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&v93);
    if ( !(unsigned __int8)utl::vector<_SPropValue,utl::allocator<_SPropValue>>::reserve(
                             &v93,
                             *((unsigned int *)a2 + 7)) )
    {
      v7 = -2147024882;
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        663);
LABEL_150:
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v93);
      return v7;
    }
    utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v100);
    v88 = 0;
    if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::push_back(v100, &v88) )
    {
      v7 = -2147024882;
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        666);
LABEL_149:
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v100);
      goto LABEL_150;
    }
    utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v85);
    for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 7); i = (unsigned int)(i + 1) )
    {
      MapiMapEntryByUdmPropId = FindMapiMapEntryByUdmPropId(&v101, *(unsigned int *)(*((_QWORD *)a2 + 4) + 24 * i + 4));
      if ( !MapiMapEntryByUdmPropId )
      {
        v14 = 673;
        v7 = -2147024809;
        goto LABEL_34;
      }
      if ( *(_QWORD *)(MapiMapEntryByUdmPropId + 16) )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, struct _SPropValue **, _BYTE *, unsigned int **))(MapiMapEntryByUdmPropId
                                                                                                  + 16))(
                v12,
                &v93,
                v85,
                v100);
        v7 = v13;
        if ( v13 < 0 )
        {
          v14 = 677;
LABEL_16:
          v15 = 1;
          v16 = (unsigned int)v13;
          goto LABEL_35;
        }
      }
      else
      {
        v17 = (EmailHelper *)*(unsigned int *)(MapiMapEntryByUdmPropId + 4);
        v81 = 0;
        if ( (unsigned int)EmailHelper::IsNamedPropTag(v17, v11) )
        {
          v13 = EmailHelper::MapNamedPropTag(v18, (unsigned int)&v81, v19);
          v7 = v13;
          if ( v13 < 0 )
          {
            v14 = 685;
            goto LABEL_16;
          }
          LODWORD(v18) = v81;
        }
        else
        {
          v81 = (unsigned int)v18;
        }
        v20 = (const struct UdmPropertyValue *)(*((_QWORD *)a2 + 4) + 24 * i);
        if ( (*(_DWORD *)v20 & 0x400) != 0 )
        {
          if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne<unsigned long const &>(
                                   v100,
                                   &v81) )
          {
            v14 = 694;
            goto LABEL_24;
          }
        }
        else
        {
          memset(&v103, 0, sizeof(v103));
          v103.ulPropTag = (unsigned int)v18;
          v13 = UdmPropToMapiProp(v20, &v103);
          v7 = v13;
          if ( v13 < 0 )
          {
            v14 = 701;
            goto LABEL_16;
          }
          v21 = v94;
          if ( v94 == v95 )
          {
            if ( !(unsigned __int8)utl::vector<_SPropValue,utl::allocator<_SPropValue>>::_PushBackOne2<_SPropValue const &>(
                                     &v93,
                                     &v103) )
            {
              v14 = 702;
LABEL_24:
              v7 = -2147024882;
LABEL_34:
              v15 = 0;
              v16 = v7;
LABEL_35:
              Log_HREvent(
                v16,
                v15,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
                v14);
LABEL_36:
              utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v85);
              goto LABEL_149;
            }
          }
          else
          {
            lpb = v103.Value.bin.lpb;
            *v94 = *(_OWORD *)&v103.ulPropTag;
            *((_QWORD *)v21 + 2) = lpb;
            v94 = (_OWORD *)((char *)v94 + 24);
          }
        }
      }
    }
    v80 = 0;
    v23 = CreateStoreManager(0, &v80);
    v7 = v23;
    if ( v23 < 0 )
    {
      Log_HREvent(
        (unsigned int)v23,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        709);
LABEL_39:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v80);
      goto LABEL_36;
    }
    AutoTopLevelTransaction::AutoTopLevelTransaction((AutoTopLevelTransaction *)v97);
    v24 = (_QWORD *)((char *)a2 + 4);
    v25 = AutoTopLevelTransaction::Begin((AutoTopLevelTransaction *)v97, v80, *((_DWORD *)a2 + 1));
    v7 = v25;
    if ( v25 < 0 )
    {
      Log_HREvent(
        (unsigned int)v25,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        712);
LABEL_42:
      AutoTopLevelTransaction::~AutoTopLevelTransaction((AutoTopLevelTransaction *)v97);
      goto LABEL_39;
    }
    v26 = v83;
    v27 = 0;
    v79 = 0;
    lpMapiProp = 0;
    if ( v83 )
    {
      if ( *(_DWORD *)a2 == 5 )
      {
        v31 = EmailOperationContext::CreateFolder(
                v87,
                (const struct UdmItemUpdate *)((char *)a2 + 4),
                0xAAAAAAAAAAAAAAABuLL * (((char *)v94 - (char *)v93) >> 3),
                v93,
                &v79);
        v7 = v31;
        if ( v31 < 0 )
        {
          v28 = 721;
          goto LABEL_54;
        }
      }
      else
      {
        if ( *(_DWORD *)a2 != 8 )
        {
          v7 = -2147024809;
          v28 = 729;
          v29 = 2147942487LL;
          v30 = 0;
LABEL_56:
          Log_HREvent(
            v29,
            v30,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
            v28);
LABEL_57:
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&lpMapiProp);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v79);
          goto LABEL_42;
        }
        v31 = EmailOperationContext::CreateMessage(
                v87,
                (const struct UdmItemUpdate *)((char *)a2 + 4),
                &v79,
                (struct IMAPIFolder **)&lpMapiProp);
        v7 = v31;
        if ( v31 < 0 )
        {
          v28 = 725;
          goto LABEL_54;
        }
        v27 = lpMapiProp;
      }
    }
    else
    {
      v31 = EmailOperationContext::MapiOpenItemById(
              v87,
              (const struct UdmItemUpdate *)((char *)a2 + 16),
              0,
              (struct IUnknown **)&v79,
              0);
      v7 = v31;
      if ( v31 < 0 )
      {
        v28 = 735;
        goto LABEL_54;
      }
    }
    v31 = EmailOperationContext::ConvertBitPropSetsToNormalPropSets(v32, v79, v85, &v93);
    v7 = v31;
    if ( v31 < 0 )
    {
      v28 = 738;
      goto LABEL_54;
    }
    if ( 0xAAAAAAAAAAAAAAABuLL * (((char *)v94 - (char *)v93) >> 3) )
    {
      v90 = 0;
      if ( !v79
        || (((void (__fastcall *)(LPMAPIPROP, GUID *, __int64 *))v79->lpVtbl->QueryInterface)(
              v79,
              &GUID_438dee14_338d_43f9_a28e_f13a7c49a601,
              &v90),
            !v90) )
      {
        v7 = -2147467262;
        v35 = 743;
        v37 = 2147500034LL;
        v36 = 0;
        goto LABEL_73;
      }
      v81 = 0;
      v33 = ULongLongToULong(0xAAAAAAAAAAAAAAABuLL * (((char *)v94 - (char *)v93) >> 3), &v81);
      v7 = v33;
      if ( v33 < 0 )
      {
        v35 = 746;
LABEL_65:
        v36 = 1;
        v37 = (unsigned int)v33;
LABEL_73:
        Log_HREvent(
          v37,
          v36,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
          v35);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v90);
        goto LABEL_57;
      }
      v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _SPropValue *, __int64, _QWORD, _QWORD))(*(_QWORD *)v34 + 24LL))(
              v34,
              v81,
              v93,
              3,
              0,
              0);
      v7 = v33;
      if ( v33 < 0 )
      {
        v35 = 752;
        goto LABEL_65;
      }
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v90);
    }
    v38 = v100[1] - v100[0];
    if ( v38 > 1 )
    {
      v31 = ULongLongToULong(v38 - 1, v100[0]);
      v7 = v31;
      if ( v31 < 0 )
      {
        v28 = 757;
        goto LABEL_54;
      }
      v31 = ((__int64 (__fastcall *)(LPMAPIPROP, unsigned int *, _QWORD))v79->lpVtbl->DeleteProps)(v79, v100[0], 0);
      v7 = v31;
      if ( v31 < 0 )
      {
        v28 = 758;
LABEL_54:
        v30 = 1;
LABEL_55:
        v29 = (unsigned int)v31;
        goto LABEL_56;
      }
    }
    for ( j = 0; j < *((_DWORD *)a2 + 10); ++j )
    {
      v31 = SetStreamProperty(v79);
      v7 = v31;
      if ( v31 < 0 )
      {
        v28 = 764;
LABEL_81:
        v30 = 1;
        goto LABEL_55;
      }
    }
    if ( *(_DWORD *)a2 != 8 )
    {
      if ( v83 )
      {
        *(_DWORD *)a3 = 1;
        v87 = 0;
        v72 = (LPSPropValue *)CMapiProps::operator&(&v87);
        OneProp = HrGetOneProp(v79, 0xFFF0102u, v72);
        v7 = OneProp;
        if ( OneProp < 0 )
        {
          Log_HREvent(
            (unsigned int)OneProp,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
            881);
          MAPIFreeBuffer(v87);
          v87 = 0;
          goto LABEL_57;
        }
        MapiIdToEmailUdmId(&v101, *((unsigned int *)v87 + 2), *((_QWORD *)v87 + 2), v74);
        v75 = (int)v102;
        v76 = v87;
        *((_QWORD *)a3 + 1) = v101;
        *((_DWORD *)a3 + 4) = v75;
        MAPIFreeBuffer(v76);
      }
      goto LABEL_146;
    }
    v40 = v79;
    *(_DWORD *)a3 = 4;
    v84 = 0;
    if ( !v40
      || (((void (__fastcall *)(LPMAPIPROP, GUID *, EmailHelper **))v40->lpVtbl->QueryInterface)(
            v40,
            &IID_IMessage,
            &v84),
          (v41 = v84) == 0) )
    {
      v7 = -2147467262;
      v67 = 773;
      v69 = 2147500034LL;
      v68 = 0;
      goto LABEL_140;
    }
    v81 = 0;
    if ( v26 )
    {
      pv = 0;
      v42 = tlx::replace<_SPropValue,&void FreeSPropValueArray(_SPropValue *)>(&pv);
      v43 = HrGetOneProp(v27, 0x36010003u, (LPSPropValue *)v42);
      v7 = v43;
      if ( v43 < 0 )
      {
        v44 = 781;
LABEL_88:
        Log_HREvent(
          (unsigned int)v43,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
          v44);
LABEL_89:
        v45 = pv;
        goto LABEL_90;
      }
      v46 = 65539;
      if ( (*((_BYTE *)pv + 8) & 4) != 0 )
        v46 = 1114115;
      v43 = SetConversationId(v84, v46);
      v7 = v43;
      if ( v43 < 0 )
      {
        v44 = 790;
        goto LABEL_88;
      }
      v47 = v84;
      v103.ulPropTag = 5;
      v103.dwAlignPad = 268370178;
      v103.Value.cur.int64 = 0x4050000B37640014LL;
      v103.Value.bin.lpb = (LPBYTE)0x3017010230150102LL;
      v86 = 0;
      v91 = 0;
      v48 = *(__int64 (__fastcall **)(EmailHelper *, struct _SPropValue *, __int64, int *))(*(_QWORD *)v84 + 40LL);
      v78 = tlx::replace<_SPropValue,&void FreeSPropValueArray(_SPropValue *)>(&v86);
      v49 = v48(v47, &v103, 0x80000000LL, &v91);
      v7 = v49;
      if ( v49 < 0 )
      {
        v51 = 800;
        v52 = 1;
        v53 = (unsigned int)v49;
LABEL_98:
        Log_HREvent(
          v53,
          v52,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
          v51);
        goto LABEL_99;
      }
      if ( v91 != v103.ulPropTag || *(_DWORD *)v86 != v103.dwAlignPad || *((_DWORD *)v86 + 6) != v103.Value.l )
      {
        v7 = -2147418113;
        v51 = 806;
        v53 = 2147549183LL;
        v52 = 0;
        goto LABEL_98;
      }
      MapiIdToEmailUdmId(&v101, *((unsigned int *)v86 + 2), *((_QWORD *)v86 + 2), v50);
      v54 = (int)v102;
      *((_QWORD *)a3 + 1) = v101;
      *((_DWORD *)a3 + 4) = v54;
      *((_QWORD *)a3 + 4) = *v24;
      *((_DWORD *)a3 + 10) = *((_DWORD *)a2 + 3);
      *((_QWORD *)a3 + 6) = *((_QWORD *)v86 + 4);
      v55 = *(unsigned int *)v24;
      v92 = 0;
      ConversationId = (*(__int64 (__fastcall **)(struct IUSStoreManager *, __int64, EmailHelper **))(*(_QWORD *)v80 + 64LL))(
                         v80,
                         v55,
                         &v92);
      v7 = ConversationId;
      if ( ConversationId < 0 )
      {
        v57 = 814;
LABEL_106:
        Log_HREvent(
          (unsigned int)ConversationId,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
          v57);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v92);
LABEL_99:
        if ( v86 )
          MAPIFreeBuffer(v86);
        goto LABEL_89;
      }
      ConversationId = EmailHelper::GetConversationId(
                         v92,
                         (struct IUSStore *)((char *)v86 + 72),
                         (const struct _SPropValue *)v86 + 4,
                         (const struct _SPropValue *)((char *)a3 + 20),
                         (struct UdmObjectId *)v78);
      v7 = ConversationId;
      if ( ConversationId < 0 )
      {
        v57 = 819;
        goto LABEL_106;
      }
      if ( *((_DWORD *)v86 + 12) == v103.Value.cur.Hi )
        v81 = *((unsigned __int16 *)v86 + 28);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v92);
      if ( v86 )
        MAPIFreeBuffer(v86);
      v59 = pv;
      if ( !pv )
        goto LABEL_124;
      goto LABEL_123;
    }
    v101 = 0x3764001400000002LL;
    LODWORD(v102) = 1078984715;
    v96 = 0;
    v88 = 0;
    v60 = *(__int64 (__fastcall **)(EmailHelper *, __int64 *, __int64, int *, void **))(*(_QWORD *)v84 + 40LL);
    v61 = tlx::replace<_SPropValue,&void FreeSPropValueArray(_SPropValue *)>(&v96);
    v62 = v60(v41, &v101, 0x80000000LL, &v88, v61);
    v7 = v62;
    if ( v62 >= 0 )
    {
      if ( v88 == (_DWORD)v101 )
      {
        v59 = v96;
        if ( *(_DWORD *)v96 == HIDWORD(v101) )
        {
          *((_QWORD *)a3 + 6) = *((_QWORD *)v96 + 1);
          if ( v59[6] == (_DWORD)v102 )
            v81 = *((unsigned __int16 *)v59 + 16);
LABEL_123:
          MAPIFreeBuffer(v59);
LABEL_124:
          if ( *((_DWORD *)a2 + 14) )
          {
            v98 = *((unsigned int *)a2 + 15);
            v99 = *((_QWORD *)a2 + 8);
            updated = EmailOperationContext::UpdateRecipients(v59, v84, &v98);
            v7 = updated;
            if ( updated < 0 )
            {
              v67 = 856;
LABEL_127:
              v68 = 1;
              v69 = (unsigned int)updated;
LABEL_140:
              Log_HREvent(
                v69,
                v68,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
                v67);
LABEL_141:
              ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v84);
              goto LABEL_57;
            }
          }
          v70 = v81;
          v71 = v81;
          if ( *((_DWORD *)a2 + 18) )
          {
            v98 = *((unsigned int *)a2 + 19);
            v99 = *((_QWORD *)a2 + 10);
            updated = EmailOperationContext::UpdateAttachments(v87, v84, &v98, &v81, (char *)a3 + 56, (char *)a3 + 64);
            v7 = updated;
            if ( updated < 0 )
            {
              v67 = 867;
              goto LABEL_127;
            }
            v70 = v81;
          }
          if ( v71 && !v70 )
          {
            updated = EmailHelper::SetAsNotSmartSendable(v84, v58);
            v7 = updated;
            if ( updated < 0 )
            {
              v67 = 872;
              goto LABEL_127;
            }
            v70 = v81;
          }
          *((_DWORD *)a3 + 18) = v70;
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v84);
LABEL_146:
          v31 = AutoTopLevelTransaction::End((AutoTopLevelTransaction *)v97, 1);
          v7 = v31;
          if ( v31 < 0 )
          {
            v28 = 886;
            goto LABEL_81;
          }
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&lpMapiProp);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v79);
          AutoTopLevelTransaction::~AutoTopLevelTransaction((AutoTopLevelTransaction *)v97);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v80);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v85);
          v7 = 0;
          goto LABEL_149;
        }
      }
      v7 = -2147418113;
      v63 = 841;
      v65 = 2147549183LL;
      v64 = 0;
    }
    else
    {
      v63 = 837;
      v64 = 1;
      v65 = (unsigned int)v62;
    }
    Log_HREvent(
      v65,
      v64,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
      v63);
    v45 = v96;
LABEL_90:
    if ( v45 )
      MAPIFreeBuffer(v45);
    goto LABEL_141;
  }
  if ( *(_DWORD *)a2 == 8 )
  {
    v101 = 80;
    v8 = &s_EmailMessage_PropMap;
    goto LABEL_6;
  }
  v7 = -2147024809;
  Log_HREvent(
    2147942487LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
    658);
  return v7;
}

```

## disassembly

```asm
0x1800b2bf4  mov     [rsp-8+arg_18], rbx
0x1800b2bf9  push    rbp
0x1800b2bfa  push    rsi
0x1800b2bfb  push    rdi
0x1800b2bfc  push    r12
0x1800b2bfe  push    r13
0x1800b2c00  push    r14
0x1800b2c02  push    r15
0x1800b2c04  lea     rbp, [rsp-70h]
0x1800b2c09  sub     rsp, 170h
0x1800b2c10  mov     rax, cs:__security_cookie
0x1800b2c17  xor     rax, rsp
0x1800b2c1a  mov     [rbp+0A0h+var_38], rax
0x1800b2c1e  xor     eax, eax
0x1800b2c20  mov     [rbp+0A0h+var_110], rcx
0x1800b2c24  lea     rcx, [rdx+10h]
0x1800b2c28  mov     dword ptr [r8], 0
0x1800b2c2f  mov     rsi, rdx
0x1800b2c32  mov     [rbp+0A0h+var_60], rax
0x1800b2c36  lea     rdx, [rbp+0A0h+var_60]
0x1800b2c3a  mov     dword ptr [rbp+0A0h+var_58], eax
0x1800b2c3d  mov     r14, r8
0x1800b2c40  call    ??8@YA_NAEBUUdmObjectId@@0@Z; operator==(UdmObjectId const &,UdmObjectId const &)
0x1800b2c45  cmp     dword ptr [rsi], 5
0x1800b2c48  mov     [rsp+1A0h+var_140], al
0x1800b2c4c  jz      short loc_1800B2C84
0x1800b2c4e  cmp     dword ptr [rsi], 8
0x1800b2c51  jz      short loc_1800B2C73
0x1800b2c53  mov     ebx, 80070057h
0x1800b2c58  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b2c5f  mov     ecx, ebx
0x1800b2c61  mov     r9d, 292h
0x1800b2c67  xor     edx, edx
0x1800b2c69  call    Log_HREvent
0x1800b2c6e  jmp     loc_1800B3733
0x1800b2c73  mov     [rbp+0A0h+var_60], 50h ; 'P'
0x1800b2c7b  lea     rax, ?s_EmailMessage_PropMap@@3QBUUdmMapiPropMap@@B; UdmMapiPropMap const near * const s_EmailMessage_PropMap
0x1800b2c82  jmp     short loc_1800B2C93
0x1800b2c84  mov     [rbp+0A0h+var_60], 0Bh
0x1800b2c8c  lea     rax, ?s_EmailFolder_PropMap@@3QBUUdmMapiPropMap@@B; UdmMapiPropMap const near * const s_EmailFolder_PropMap
0x1800b2c93  lea     rcx, [rbp+0A0h+var_E0]
0x1800b2c97  mov     [rbp+0A0h+var_58], rax
0x1800b2c9b  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800b2ca0  mov     edx, [rsi+1Ch]
0x1800b2ca3  lea     rcx, [rbp+0A0h+var_E0]
0x1800b2ca7  call    ?reserve@?$vector@U_SPropValue@@V?$allocator@U_SPropValue@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_SPropValue,utl::allocator<_SPropValue>>::reserve(unsigned __int64)
0x1800b2cac  test    al, al
0x1800b2cae  jnz     short loc_1800B2CD0
0x1800b2cb0  mov     ebx, 8007000Eh
0x1800b2cb5  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b2cbc  mov     ecx, ebx
0x1800b2cbe  mov     r9d, 297h
0x1800b2cc4  xor     edx, edx
0x1800b2cc6  call    Log_HREvent
0x1800b2ccb  jmp     loc_1800B372A
0x1800b2cd0  lea     rcx, [rbp+0A0h+var_78]
0x1800b2cd4  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800b2cd9  lea     rdx, [rbp+0A0h+var_108]
0x1800b2cdd  mov     [rbp+0A0h+var_108], 0
0x1800b2ce4  lea     rcx, [rbp+0A0h+var_78]
0x1800b2ce8  call    ?push_back@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_N$$QEAK@Z; utl::vector<ulong,utl::allocator<ulong>>::push_back(ulong &&)
0x1800b2ced  test    al, al
0x1800b2cef  jnz     short loc_1800B2D11
0x1800b2cf1  mov     ebx, 8007000Eh
0x1800b2cf6  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b2cfd  mov     ecx, ebx
0x1800b2cff  mov     r9d, 29Ah
0x1800b2d05  xor     edx, edx
0x1800b2d07  call    Log_HREvent
0x1800b2d0c  jmp     loc_1800B3721
0x1800b2d11  lea     rcx, [rsp+1A0h+var_130]
0x1800b2d16  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800b2d1b  xor     edi, edi
0x1800b2d1d  lea     r15d, [rdi+1]
0x1800b2d21  cmp     edi, [rsi+1Ch]
0x1800b2d24  jnb     loc_1800B2E99
0x1800b2d2a  mov     rax, [rsi+20h]
0x1800b2d2e  lea     r15, [rdi+rdi*2]
0x1800b2d32  lea     rcx, [rbp+0A0h+var_60]
0x1800b2d36  lea     r11, [rax+r15*8]
0x1800b2d3a  mov     edx, [r11+4]
0x1800b2d3e  call    ?FindMapiMapEntryByUdmPropId@@YAPEBUUdmMapiPropMap@@AEBV?$Vector@$$CBUUdmMapiPropMap@@@Udm@@K@Z; FindMapiMapEntryByUdmPropId(Udm::Vector<UdmMapiPropMap const> const &,ulong)
0x1800b2d43  test    rax, rax
0x1800b2d46  jz      loc_1800B2E6F
0x1800b2d4c  mov     r10, [rax+10h]
0x1800b2d50  test    r10, r10
0x1800b2d53  jz      short loc_1800B2D89
0x1800b2d55  lea     r9, [rbp+0A0h+var_78]
0x1800b2d59  mov     rcx, r11
0x1800b2d5c  lea     r8, [rsp+1A0h+var_130]
0x1800b2d61  mov     rax, r10
0x1800b2d64  lea     rdx, [rbp+0A0h+var_E0]
0x1800b2d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2d6d  mov     ebx, eax
0x1800b2d6f  test    eax, eax
0x1800b2d71  jns     loc_1800B2E43
0x1800b2d77  mov     r9d, 2A5h
0x1800b2d7d  mov     edx, 1
0x1800b2d82  mov     ecx, eax
0x1800b2d84  jmp     loc_1800B2E7E
0x1800b2d89  mov     ecx, [rax+4]; this
0x1800b2d8c  mov     [rsp+1A0h+var_150], 0
0x1800b2d94  call    ?IsNamedPropTag@EmailHelper@@YAHK@Z; EmailHelper::IsNamedPropTag(ulong)
0x1800b2d99  test    eax, eax
0x1800b2d9b  jz      short loc_1800B2DB7
0x1800b2d9d  lea     rdx, [rsp+1A0h+var_150]; unsigned int
0x1800b2da2  call    ?MapNamedPropTag@EmailHelper@@YAJKPEAK@Z; EmailHelper::MapNamedPropTag(ulong,ulong *)
0x1800b2da7  mov     ebx, eax
0x1800b2da9  test    eax, eax
0x1800b2dab  js      loc_1800B2E51
0x1800b2db1  mov     ecx, [rsp+1A0h+var_150]
0x1800b2db5  jmp     short loc_1800B2DBB
0x1800b2db7  mov     [rsp+1A0h+var_150], ecx
0x1800b2dbb  mov     rax, [rsi+20h]
0x1800b2dbf  lea     r8, [rax+r15*8]
0x1800b2dc3  test    dword ptr [r8], 400h
0x1800b2dca  jz      short loc_1800B2DEE
0x1800b2dcc  lea     rdx, [rsp+1A0h+var_150]
0x1800b2dd1  lea     rcx, [rbp+0A0h+var_78]
0x1800b2dd5  call    ??$_PushBackOne@AEBK@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_NAEBK@Z; utl::vector<ulong,utl::allocator<ulong>>::_PushBackOne<ulong const &>(ulong const &)
0x1800b2dda  test    al, al
0x1800b2ddc  jnz     short loc_1800B2E43
0x1800b2dde  mov     r9d, 2B6h
0x1800b2de4  mov     ebx, 8007000Eh
0x1800b2de9  jmp     loc_1800B2E7A
0x1800b2dee  xorps   xmm0, xmm0
0x1800b2df1  lea     rdx, [rbp+0A0h+var_50]; struct _SPropValue *
0x1800b2df5  movups  xmmword ptr [rbp+0A0h+var_50.ulPropTag], xmm0
0x1800b2df9  mov     [rbp+0A0h+var_50.ulPropTag], ecx
0x1800b2dfc  xor     eax, eax
0x1800b2dfe  mov     rcx, r8; struct UdmPropertyValue *
0x1800b2e01  mov     qword ptr [rbp+0A0h+var_50.Value+8], rax
0x1800b2e05  call    ?UdmPropToMapiProp@@YAJPEBUUdmPropertyValue@@PEAU_SPropValue@@@Z; UdmPropToMapiProp(UdmPropertyValue const *,_SPropValue *)
0x1800b2e0a  mov     ebx, eax
0x1800b2e0c  test    eax, eax
0x1800b2e0e  js      short loc_1800B2E64
0x1800b2e10  mov     rax, [rbp+0A0h+var_D8]
0x1800b2e14  cmp     rax, [rbp+0A0h+var_D0]
0x1800b2e18  jz      short loc_1800B2E32
0x1800b2e1a  movups  xmm0, xmmword ptr [rbp+0A0h+var_50.ulPropTag]
0x1800b2e1e  movsd   xmm1, qword ptr [rbp+0A0h+var_50.Value+8]
0x1800b2e23  movups  xmmword ptr [rax], xmm0
0x1800b2e26  movsd   qword ptr [rax+10h], xmm1
0x1800b2e2b  add     [rbp+0A0h+var_D8], 18h
0x1800b2e30  jmp     short loc_1800B2E43
0x1800b2e32  lea     rdx, [rbp+0A0h+var_50]
0x1800b2e36  lea     rcx, [rbp+0A0h+var_E0]
0x1800b2e3a  call    ??$_PushBackOne2@AEBU_SPropValue@@@?$vector@U_SPropValue@@V?$allocator@U_SPropValue@@@utl@@@utl@@AEAA_NAEBU_SPropValue@@@Z; utl::vector<_SPropValue,utl::allocator<_SPropValue>>::_PushBackOne2<_SPropValue const &>(_SPropValue const &)
0x1800b2e3f  test    al, al
0x1800b2e41  jz      short loc_1800B2E5C
0x1800b2e43  mov     r15d, 1
0x1800b2e49  add     edi, r15d
0x1800b2e4c  jmp     loc_1800B2D21
0x1800b2e51  mov     r9d, 2ADh
0x1800b2e57  jmp     loc_1800B2D7D
0x1800b2e5c  mov     r9d, 2BEh
0x1800b2e62  jmp     short loc_1800B2DE4
0x1800b2e64  mov     r9d, 2BDh
0x1800b2e6a  jmp     loc_1800B2D7D
0x1800b2e6f  mov     r9d, 2A1h
0x1800b2e75  mov     ebx, 80070057h
0x1800b2e7a  xor     edx, edx
0x1800b2e7c  mov     ecx, ebx
0x1800b2e7e  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b2e85  call    Log_HREvent
0x1800b2e8a  lea     rcx, [rsp+1A0h+var_130]
0x1800b2e8f  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800b2e94  jmp     loc_1800B3721
0x1800b2e99  lea     rdx, [rsp+1A0h+var_158]
0x1800b2e9e  mov     [rsp+1A0h+var_158], 0
0x1800b2ea7  xor     ecx, ecx
0x1800b2ea9  call    cs:__imp_CreateStoreManager
0x1800b2eaf  mov     ebx, eax
0x1800b2eb1  test    eax, eax
0x1800b2eb3  jns     short loc_1800B2ED8
0x1800b2eb5  mov     r9d, 2C5h
0x1800b2ebb  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b2ec2  mov     edx, r15d
0x1800b2ec5  mov     ecx, eax
0x1800b2ec7  call    Log_HREvent
0x1800b2ecc  lea     rcx, [rsp+1A0h+var_158]
0x1800b2ed1  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800b2ed6  jmp     short loc_1800B2E8A
0x1800b2ed8  lea     rcx, [rbp+0A0h+var_C0]; this
0x1800b2edc  call    ??0AutoTopLevelTransaction@@QEAA@XZ; AutoTopLevelTransaction::AutoTopLevelTransaction(void)
0x1800b2ee1  mov     rdx, [rsp+1A0h+var_158]; struct IUSStoreManager *
0x1800b2ee6  lea     r12, [rsi+4]
0x1800b2eea  mov     r8d, [r12]; unsigned int
0x1800b2eee  lea     rcx, [rbp+0A0h+var_C0]; this
0x1800b2ef2  call    ?Begin@AutoTopLevelTransaction@@QEAAJPEAUIUSStoreManager@@K@Z; AutoTopLevelTransaction::Begin(IUSStoreManager *,ulong)
0x1800b2ef7  mov     ebx, eax
0x1800b2ef9  test    eax, eax
0x1800b2efb  jns     short loc_1800B2F1F
0x1800b2efd  mov     r9d, 2C8h
0x1800b2f03  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b2f0a  mov     edx, r15d
0x1800b2f0d  mov     ecx, eax
0x1800b2f0f  call    Log_HREvent
0x1800b2f14  lea     rcx, [rbp+0A0h+var_C0]; this
0x1800b2f18  call    ??1AutoTopLevelTransaction@@UEAA@XZ; AutoTopLevelTransaction::~AutoTopLevelTransaction(void)
0x1800b2f1d  jmp     short loc_1800B2ECC
0x1800b2f1f  movzx   r13d, [rsp+1A0h+var_140]
0x1800b2f25  xor     edi, edi
0x1800b2f27  mov     [rsp+1A0h+var_160], 0
0x1800b2f30  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800b2f3a  mov     [rsp+1A0h+lpMapiProp], rdi
0x1800b2f3f  test    r13d, r13d
0x1800b2f42  jz      loc_1800B3013
0x1800b2f48  cmp     dword ptr [rsi], 5
0x1800b2f4b  jz      short loc_1800B2FB4
0x1800b2f4d  cmp     dword ptr [rsi], 8
0x1800b2f50  jz      short loc_1800B2F66
0x1800b2f52  mov     ebx, 80070057h
0x1800b2f57  mov     r9d, 2D9h
0x1800b2f5d  mov     ecx, ebx
0x1800b2f5f  xor     edx, edx
0x1800b2f61  jmp     loc_1800B2FEE
0x1800b2f66  mov     rcx, [rbp+0A0h+var_110]; this
0x1800b2f6a  lea     r9, [rsp+1A0h+lpMapiProp]; struct IMAPIFolder **
0x1800b2f6f  lea     r8, [rsp+1A0h+var_160]; struct IMAPIProp **
0x1800b2f74  mov     rdx, r12; struct UdmObjectId *
0x1800b2f77  call    ?CreateMessage@EmailOperationContext@@AEAAJAEBUUdmObjectId@@PEAPEAUIMAPIProp@@PEAPEAUIMAPIFolder@@@Z; EmailOperationContext::CreateMessage(UdmObjectId const &,IMAPIProp * *,IMAPIFolder * *)
0x1800b2f7c  mov     ebx, eax
0x1800b2f7e  test    eax, eax
0x1800b2f80  jns     short loc_1800B2F8A
0x1800b2f82  mov     r9d, 2D5h
0x1800b2f88  jmp     short loc_1800B2FE9
0x1800b2f8a  mov     rdi, [rsp+1A0h+lpMapiProp]
0x1800b2f8f  mov     rdx, [rsp+1A0h+var_160]
0x1800b2f94  lea     r9, [rbp+0A0h+var_E0]
0x1800b2f98  lea     r8, [rsp+1A0h+var_130]
0x1800b2f9d  call    ?ConvertBitPropSetsToNormalPropSets@EmailOperationContext@@AEAAJPEAUIMAPIProp@@AEBV?$vector@U_SPropValue@@V?$allocator@U_SPropValue@@@utl@@@utl@@PEAV34@@Z; EmailOperationContext::ConvertBitPropSetsToNormalPropSets(IMAPIProp *,utl::vector<_SPropValue,utl::allocator<_SPropValue>> const &,utl::vector<_SPropValue,utl::allocator<_SPropValue>> *)
0x1800b2fa2  mov     ebx, eax
0x1800b2fa4  test    eax, eax
0x1800b2fa6  jns     loc_1800B303F
0x1800b2fac  mov     r9d, 2E2h
0x1800b2fb2  jmp     short loc_1800B2FE9
0x1800b2fb4  mov     r9, [rbp+0A0h+var_E0]; struct _SPropValue *
0x1800b2fb8  mov     rdx, r12; struct UdmObjectId *
0x1800b2fbb  mov     r8, [rbp+0A0h+var_D8]
0x1800b2fbf  mov     rcx, [rbp+0A0h+var_110]; this
0x1800b2fc3  sub     r8, r9
0x1800b2fc6  sar     r8, 3
0x1800b2fca  imul    r8, rax; unsigned __int64
0x1800b2fce  lea     rax, [rsp+1A0h+var_160]
0x1800b2fd3  mov     [rsp+1A0h+var_180], rax; struct IMAPIProp **
0x1800b2fd8  call    ?CreateFolder@EmailOperationContext@@AEAAJAEBUUdmObjectId@@_KPEBU_SPropValue@@PEAPEAUIMAPIProp@@@Z; EmailOperationContext::CreateFolder(UdmObjectId const &,unsigned __int64,_SPropValue const *,IMAPIProp * *)
0x1800b2fdd  mov     ebx, eax
0x1800b2fdf  test    eax, eax
0x1800b2fe1  jns     short loc_1800B2F8F
0x1800b2fe3  mov     r9d, 2D1h
0x1800b2fe9  mov     edx, r15d
0x1800b2fec  mov     ecx, eax
0x1800b2fee  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b2ff5  call    Log_HREvent
0x1800b2ffa  lea     rcx, [rsp+1A0h+lpMapiProp]
0x1800b2fff  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800b3004  lea     rcx, [rsp+1A0h+var_160]
0x1800b3009  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800b300e  jmp     loc_1800B2F14
0x1800b3013  mov     rcx, [rbp+0A0h+var_110]; this
0x1800b3017  lea     r9, [rsp+1A0h+var_160]; struct IUnknown **
0x1800b301c  xor     r8d, r8d; int
0x1800b301f  mov     [rsp+1A0h+var_180], rdi; struct IMsgStore **
0x1800b3024  lea     rdx, [rsi+10h]; struct UdmObjectId *
0x1800b3028  call    ?MapiOpenItemById@EmailOperationContext@@QEAAJAEBUUdmObjectId@@HPEAPEAUIUnknown@@PEAPEAUIMsgStore@@@Z; EmailOperationContext::MapiOpenItemById(UdmObjectId const &,int,IUnknown * *,IMsgStore * *)
0x1800b302d  mov     ebx, eax
0x1800b302f  test    eax, eax
0x1800b3031  jns     loc_1800B2F8F
0x1800b3037  mov     r9d, 2DFh
0x1800b303d  jmp     short loc_1800B2FE9
0x1800b303f  mov     rax, [rbp+0A0h+var_D8]
0x1800b3043  mov     rbx, 0AAAAAAAAAAAAAAABh
0x1800b304d  sub     rax, [rbp+0A0h+var_E0]
0x1800b3051  sar     rax, 3
0x1800b3055  imul    rax, rbx
0x1800b3059  test    rax, rax
0x1800b305c  jz      loc_1800B3119
0x1800b3062  mov     rcx, [rsp+1A0h+var_160]
0x1800b3067  mov     [rbp+0A0h+var_F8], 0
0x1800b306f  test    rcx, rcx
0x1800b3072  jz      loc_1800B3146
0x1800b3078  mov     rax, [rcx]
0x1800b307b  lea     r8, [rbp+0A0h+var_F8]
0x1800b307f  lea     rdx, _GUID_438dee14_338d_43f9_a28e_f13a7c49a601
0x1800b3086  mov     rax, [rax]
0x1800b3089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b308e  mov     r10, [rbp+0A0h+var_F8]
0x1800b3092  test    r10, r10
0x1800b3095  jz      loc_1800B3146
0x1800b309b  mov     rcx, [rbp+0A0h+var_D8]
0x1800b309f  lea     rdx, [rsp+1A0h+var_150]; unsigned int *
0x1800b30a4  sub     rcx, [rbp+0A0h+var_E0]
0x1800b30a8  sar     rcx, 3
0x1800b30ac  imul    rcx, rbx; unsigned __int64
0x1800b30b0  mov     [rsp+1A0h+var_150], 0
0x1800b30b8  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800b30bd  mov     ebx, eax
0x1800b30bf  test    eax, eax
0x1800b30c1  jns     short loc_1800B30D3
  ... truncated ...
```
