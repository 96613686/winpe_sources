# GetMessageAttachments(ISmMessage *,utl::vector<auto_struct<UdmChatAttachment,&Udm::FreeUdmChatAttachment(UdmChatAttachment *)>,utl::allocator<auto_struct<UdmChatAttachment,&Udm::FreeUdmChatAttachment(UdmChatAttachment *)>>> *)

- ea: `0x1800cb6bc`
- end: `0x1800cbfaa`
- name: `?GetMessageAttachments@@YAJPEAUISmMessage@@PEAV?$vector@U?$auto_struct@UUdmChatAttachment@@$1?FreeUdmChatAttachment@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmChatAttachment@@$1?FreeUdmChatAttachment@Udm@@YAXPEAU1@@Z@@@utl@@@utl@@@Z`
- size: `2286`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d1f3c`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x1800234d4`
- `0x18003cda4`
- `0x18003ed7c`
- `0x18006db44`
- `0x180072ccc`
- `0x1800965d8`
- `0x1800cb6bc`
- `0x1800cee14`
- `0x1800cfc84`
- `0x180116344`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `MessagingDataModel2!Messaging_IsRcsMessage` at `0x1800cb90c`
- `MessagingDataModel2!Messaging_IsRcsMessage` at `0x1800cb90c`
- `MessagingDataModel2!Messaging_SmEntryIdToUdmObjectId` at `0x1800cb72b`
- `MessagingDataModel2!Messaging_SmEntryIdToUdmObjectId` at `0x1800cb72b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800cba25`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800cba9d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800cba25`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800cba9d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800cb9f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800cba75`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800cb9f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800cba75`
- `UserDataTypeHelperUtil!DupString` at `0x1800cb898`
- `UserDataTypeHelperUtil!DupString` at `0x1800cb8b1`
- `UserDataTypeHelperUtil!DupString` at `0x1800cb898`
- `UserDataTypeHelperUtil!DupString` at `0x1800cb8b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800cbc9d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800cbc9d`

## string_xrefs

- `0x1800cb73d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800cb77d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800cb79f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`

## pseudocode

```c
__int64 __fastcall GetMessageAttachments(__int64 *a1, _QWORD *a2)
{
  __int64 v2; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64); // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64); // rbx
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 (__fastcall *v23)(__int64 *, __int64); // rbx
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rcx
  struct _RTL_CRITICAL_SECTION *v27; // rbx
  int CurrentFileTransferProgress; // eax
  struct _RTL_CRITICAL_SECTION *v29; // rbx
  __int64 v30; // r9
  struct UdmChatAttachment *v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rdx
  struct UdmChatAttachment *v35; // rdx
  HRESULT Instance; // eax
  __int64 v37; // r9
  unsigned int v38; // ebx
  int updated; // edi
  __int64 v41; // r9
  LPVOID Context; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *ppv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL fPending; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v49; // [rsp+68h] [rbp-98h] BYREF
  int v50; // [rsp+6Ch] [rbp-94h] BYREF
  _DWORD v51[4]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v52; // [rsp+80h] [rbp-80h] BYREF
  __int128 v53; // [rsp+90h] [rbp-70h]
  __int128 v54; // [rsp+A0h] [rbp-60h]
  __int128 v55; // [rsp+B0h] [rbp-50h]
  double v56; // [rsp+C0h] [rbp-40h]
  struct ISmEntryId *v57; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v58; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v59; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v60; // [rsp+F0h] [rbp-10h]
  __int128 v61; // [rsp+100h] [rbp+0h] BYREF
  __int128 v62; // [rsp+110h] [rbp+10h] BYREF
  double v63[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v64; // [rsp+130h] [rbp+30h] BYREF
  int v65; // [rsp+138h] [rbp+38h]

  v2 = *a1;
  v57 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, struct ISmEntryId **))(v2 + 184))(a1, &v57);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 841;
LABEL_5:
    Log_HREvent(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      v7);
    goto LABEL_89;
  }
  v64 = 0;
  v65 = 0;
  v5 = Messaging_SmEntryIdToUdmObjectId(v57, (struct UdmObjectId *)&v64);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 844;
    goto LABEL_5;
  }
  v8 = *a1;
  v44 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v8 + 240))(a1, &v44);
  v6 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent(
      (unsigned int)v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      847);
    goto LABEL_8;
  }
  while ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44) )
  {
    v46 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 32LL))(v44, &v46);
    v6 = v10;
    if ( v10 < 0 )
    {
      Log_HREvent(
        (unsigned int)v10,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
        852);
      goto LABEL_52;
    }
    v11 = v46;
    v47 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 48LL);
    v13 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v47);
    v14 = v12(v11, v13);
    v6 = v14;
    if ( v14 < 0 )
    {
      Log_HREvent(
        (unsigned int)v14,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
        855);
      goto LABEL_50;
    }
    v15 = v46;
    v48 = 0;
    v16 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 80LL);
    v17 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v48);
    v18 = v16(v15, v17);
    v6 = v18;
    if ( v18 < 0 )
    {
      Log_HREvent(
        (unsigned int)v18,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
        858);
      goto LABEL_48;
    }
    memset_0(&v52, 0, 0x48u);
    v59 = v52;
    v61 = v54;
    v60 = v53;
    v63[0] = v56;
    v62 = v55;
    v19 = DupString((char *)&v61 + 8, v47);
    v6 = v19;
    if ( v19 < 0 )
    {
      v32 = 861;
      goto LABEL_45;
    }
    v19 = DupString((char *)&v62 + 8, v48);
    v6 = v19;
    if ( v19 < 0 )
    {
      v32 = 862;
      goto LABEL_45;
    }
    LODWORD(v61) = -1;
    v50 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 144LL))(v46, &v50);
    v6 = v19;
    if ( v19 < 0 )
    {
      v32 = 866;
      goto LABEL_45;
    }
    *(_QWORD *)&v59 = (unsigned int)v64 | 0x2300000000LL;
    DWORD2(v59) = v50;
    v63[0] = 0.0;
    if ( (unsigned int)Messaging_IsRcsMessage(a1) )
    {
      v20 = *a1;
      v51[0] = 0;
      v19 = (*(__int64 (__fastcall **)(__int64 *, _DWORD *))(v20 + 544))(a1, v51);
      v6 = v19;
      if ( v19 < 0 )
      {
        v32 = 880;
        goto LABEL_45;
      }
      v21 = *a1;
      v49 = -1;
      v19 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v21 + 560))(a1, &v49);
      v6 = v19;
      if ( v19 < 0 )
      {
        v32 = 883;
LABEL_45:
        v34 = 1;
        v33 = (unsigned int)v19;
LABEL_46:
        Log_HREvent(
          v33,
          v34,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
          v32);
        Udm::FreeUdmChatAttachment((Udm *)&v59, v35);
        memset_0(&v52, 0, 0x48u);
        v59 = v52;
        v61 = v54;
        v60 = v53;
        v63[0] = v56;
        v62 = v55;
LABEL_48:
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v48);
LABEL_50:
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v47);
LABEL_52:
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v46);
LABEL_8:
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v44);
        goto LABEL_89;
      }
      if ( (unsigned int)(v51[0] - 1) <= 1 )
      {
        v22 = *a1;
        ppv = 0;
        v23 = *(__int64 (__fastcall **)(__int64 *, __int64))(v22 + 688);
        v24 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&ppv);
        v25 = v23(a1, v24);
        if ( v25 < 0 )
          Log_HREvent(
            (unsigned int)v25,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
            888);
        if ( ppv )
        {
          v26 = -1;
          do
            ++v26;
          while ( ppv[v26] );
          if ( v26 )
          {
            fPending = 0;
            Context = 0;
            InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
            v27 = (struct _RTL_CRITICAL_SECTION *)Context;
            if ( !Context )
            {
              RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
              v58 = 0;
              InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
              v27 = (struct _RTL_CRITICAL_SECTION *)qword_18015DCE0;
              tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v58);
            }
            CurrentFileTransferProgress = RcsFileTransferProgressTracker::GetCurrentFileTransferProgress(
                                            v27 + 6,
                                            ppv,
                                            v49,
                                            v63);
            if ( CurrentFileTransferProgress == -2147023728 )
            {
              fPending = 0;
              Context = 0;
              InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
              v29 = (struct _RTL_CRITICAL_SECTION *)Context;
              if ( !Context )
              {
                RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
                v58 = 0;
                InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
                v29 = (struct _RTL_CRITICAL_SECTION *)qword_18015DCE0;
                tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v58);
              }
              CurrentFileTransferProgress = RcsFileTransferProgressTracker::GetCurrentFileTransferProgress(
                                              v29 + 6,
                                              ppv,
                                              v49,
                                              v63);
              if ( CurrentFileTransferProgress < 0 )
              {
                v30 = 899;
                goto LABEL_35;
              }
            }
            else if ( CurrentFileTransferProgress < 0 )
            {
              v30 = 903;
LABEL_35:
              Log_HREvent(
                (unsigned int)CurrentFileTransferProgress,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
                v30);
            }
          }
        }
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&ppv);
      }
    }
    if ( !(unsigned __int8)utl::vector<auto_struct<UdmChatAttachment,&void Udm::FreeUdmChatAttachment(UdmChatAttachment *)>,utl::allocator<auto_struct<UdmChatAttachment,&void Udm::FreeUdmChatAttachment(UdmChatAttachment *)>>>::push_back(
                             a2,
                             &v59) )
    {
      v6 = -2147024882;
      v32 = 909;
      v33 = 2147942414LL;
      v34 = 0;
      goto LABEL_46;
    }
    Udm::FreeUdmChatAttachment((Udm *)&v59, v31);
    memset_0(&v52, 0, 0x48u);
    v59 = v52;
    v61 = v54;
    v60 = v53;
    v63[0] = v56;
    v62 = v55;
    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v48);
    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v47);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v46);
  }
  if ( !((a2[1] - *a2) / 72LL) )
  {
LABEL_88:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v44);
    v6 = 0;
    goto LABEL_89;
  }
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_SlideAccessor,
               0,
               0x17u,
               &GUID_c98ae9f4_bd7e_4eb1_957f_c32547df6a6e,
               (LPVOID *)&ppv);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v37 = 915;
LABEL_56:
    Log_HREvent(
      (unsigned int)Instance,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      v37);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
    goto LABEL_8;
  }
  Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, a1);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v37 = 916;
    goto LABEL_56;
  }
  fPending = 0;
  Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, WINBOOL *))(*(_QWORD *)ppv + 32LL))(ppv, &fPending);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v37 = 919;
    goto LABEL_56;
  }
  v38 = 0;
  if ( !fPending )
  {
LABEL_87:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
    goto LABEL_88;
  }
  while ( 2 )
  {
    Context = 0;
    if ( !(*(unsigned int (__fastcall **)(unsigned __int16 *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 40LL))(
            ppv,
            v38,
            &Context) )
    {
      updated = UpdateMatchingAttachment(v38, Context, a2, 0);
      if ( updated < 0 )
      {
        v41 = 926;
        goto LABEL_91;
      }
      if ( Context )
        ATL::AtlComPtrAssign((struct IUnknown **)&Context, 0);
    }
    if ( !(*(unsigned int (__fastcall **)(unsigned __int16 *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 48LL))(
            ppv,
            v38,
            &Context) )
    {
      updated = UpdateMatchingAttachment(v38, Context, a2, 0);
      if ( updated < 0 )
      {
        v41 = 932;
        goto LABEL_91;
      }
      if ( Context )
        ATL::AtlComPtrAssign((struct IUnknown **)&Context, 0);
    }
    if ( !(*(unsigned int (__fastcall **)(unsigned __int16 *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 56LL))(
            ppv,
            v38,
            &Context) )
    {
      updated = UpdateMatchingAttachment(v38, Context, a2, 0);
      if ( updated < 0 )
      {
        v41 = 938;
        goto LABEL_91;
      }
      if ( Context )
        ATL::AtlComPtrAssign((struct IUnknown **)&Context, 0);
    }
    if ( !(*(unsigned int (__fastcall **)(unsigned __int16 *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 64LL))(
            ppv,
            v38,
            &Context) )
    {
      updated = UpdateMatchingAttachment(v38, Context, a2, 0);
      if ( updated < 0 )
      {
        v41 = 944;
        goto LABEL_91;
      }
      if ( Context )
        ATL::AtlComPtrAssign((struct IUnknown **)&Context, 0);
    }
    if ( !(*(unsigned int (__fastcall **)(unsigned __int16 *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 72LL))(
            ppv,
            v38,
            &Context) )
    {
      updated = UpdateMatchingAttachment(v38, Context, a2, 0);
      if ( updated < 0 )
      {
        v41 = 950;
        goto LABEL_91;
      }
      if ( Context )
        ATL::AtlComPtrAssign((struct IUnknown **)&Context, 0);
    }
    if ( (*(unsigned int (__fastcall **)(unsigned __int16 *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 96LL))(
           ppv,
           v38,
           &Context) )
    {
      goto LABEL_86;
    }
    updated = UpdateMatchingAttachment(v38, Context, a2, 1);
    if ( updated >= 0 )
    {
      if ( Context )
        ATL::AtlComPtrAssign((struct IUnknown **)&Context, 0);
LABEL_86:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&Context);
      if ( ++v38 >= fPending )
        goto LABEL_87;
      continue;
    }
    break;
  }
  v41 = 956;
LABEL_91:
  Log_HREvent(
    (unsigned int)updated,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
    v41);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&Context);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v44);
  v6 = updated;
LABEL_89:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v57);
  return v6;
}

```

## disassembly

```asm
0x1800cb6bc  mov     rax, rsp
0x1800cb6bf  mov     [rax+18h], rbx
0x1800cb6c3  push    rbp
0x1800cb6c4  push    rsi
0x1800cb6c5  push    rdi
0x1800cb6c6  push    r12
0x1800cb6c8  push    r13
0x1800cb6ca  push    r14
0x1800cb6cc  push    r15
0x1800cb6ce  lea     rbp, [rsp-60h]
0x1800cb6d3  sub     rsp, 160h
0x1800cb6da  movaps  xmmword ptr [rax-48h], xmm6
0x1800cb6de  mov     rax, cs:__security_cookie
0x1800cb6e5  xor     rax, rsp
0x1800cb6e8  mov     [rbp+90h+var_50], rax
0x1800cb6ec  mov     rax, [rcx]
0x1800cb6ef  mov     r13, rdx
0x1800cb6f2  xor     r12d, r12d
0x1800cb6f5  lea     rdx, [rbp+90h+var_C0]
0x1800cb6f9  mov     r15, rcx
0x1800cb6fc  mov     [rbp+90h+var_C0], r12
0x1800cb700  mov     rax, [rax+0B8h]
0x1800cb707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb70c  mov     ebx, eax
0x1800cb70e  test    eax, eax
0x1800cb710  jns     short loc_1800CB71A
0x1800cb712  mov     r9d, 349h
0x1800cb718  jmp     short loc_1800CB73D
0x1800cb71a  mov     rcx, [rbp+90h+var_C0]
0x1800cb71e  lea     rdx, [rbp+90h+var_60]
0x1800cb722  xor     eax, eax
0x1800cb724  mov     [rbp+90h+var_60], rax
0x1800cb728  mov     [rbp+90h+var_58], eax
0x1800cb72b  call    cs:__imp_?Messaging_SmEntryIdToUdmObjectId@@YAJPEAUISmEntryId@@PEAUUdmObjectId@@@Z; Messaging_SmEntryIdToUdmObjectId(ISmEntryId *,UdmObjectId *)
0x1800cb731  mov     ebx, eax
0x1800cb733  test    eax, eax
0x1800cb735  jns     short loc_1800CB755
0x1800cb737  mov     r9d, 34Ch
0x1800cb73d  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800cb744  mov     edx, 1
0x1800cb749  mov     ecx, eax
0x1800cb74b  call    Log_HREvent
0x1800cb750  jmp     loc_1800CBF17
0x1800cb755  mov     rax, [r15]
0x1800cb758  lea     rdx, [rsp+190h+var_150]
0x1800cb75d  mov     rcx, r15
0x1800cb760  mov     [rsp+190h+var_150], r12
0x1800cb765  mov     rax, [rax+0F0h]
0x1800cb76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb771  mov     ebx, eax
0x1800cb773  test    eax, eax
0x1800cb775  jns     short loc_1800CB79F
0x1800cb777  mov     r9d, 34Fh
0x1800cb77d  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800cb784  mov     edx, 1
0x1800cb789  mov     ecx, eax
0x1800cb78b  call    Log_HREvent
0x1800cb790  lea     rcx, [rsp+190h+var_150]
0x1800cb795  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800cb79a  jmp     loc_1800CBF17
0x1800cb79f  lea     r14, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800cb7a6  mov     esi, 1
0x1800cb7ab  xorps   xmm6, xmm6
0x1800cb7ae  mov     rcx, [rsp+190h+var_150]
0x1800cb7b3  mov     rax, [rcx]
0x1800cb7b6  mov     rax, [rax+18h]
0x1800cb7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb7bf  test    eax, eax
0x1800cb7c1  jnz     loc_1800CBC51
0x1800cb7c7  mov     rcx, [rsp+190h+var_150]
0x1800cb7cc  lea     rdx, [rsp+190h+var_140]
0x1800cb7d1  mov     [rsp+190h+var_140], r12
0x1800cb7d6  mov     rax, [rcx]
0x1800cb7d9  mov     rax, [rax+20h]
0x1800cb7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb7e2  mov     ebx, eax
0x1800cb7e4  test    eax, eax
0x1800cb7e6  js      loc_1800CBC30
0x1800cb7ec  mov     rdi, [rsp+190h+var_140]
0x1800cb7f1  lea     rcx, [rsp+190h+var_138]
0x1800cb7f6  mov     [rsp+190h+var_138], r12
0x1800cb7fb  mov     rax, [rdi]
0x1800cb7fe  mov     rbx, [rax+30h]
0x1800cb802  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x1800cb807  mov     rdx, rax
0x1800cb80a  mov     rcx, rdi
0x1800cb80d  mov     rax, rbx
0x1800cb810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb815  mov     ebx, eax
0x1800cb817  test    eax, eax
0x1800cb819  js      loc_1800CBC12
0x1800cb81f  mov     rdi, [rsp+190h+var_140]
0x1800cb824  lea     rcx, [rsp+190h+var_130]
0x1800cb829  mov     [rsp+190h+var_130], r12
0x1800cb82e  mov     rax, [rdi]
0x1800cb831  mov     rbx, [rax+50h]
0x1800cb835  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x1800cb83a  mov     rdx, rax
0x1800cb83d  mov     rcx, rdi
0x1800cb840  mov     rax, rbx
0x1800cb843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb848  mov     ebx, eax
0x1800cb84a  test    eax, eax
0x1800cb84c  js      loc_1800CBBF4
0x1800cb852  mov     edi, 48h ; 'H'
0x1800cb857  lea     rcx, [rbp+90h+var_110]; void *
0x1800cb85b  mov     r8d, edi; Size
0x1800cb85e  xor     edx, edx; Val
0x1800cb860  call    memset_0
0x1800cb865  movaps  xmm0, [rbp+90h+var_110]
0x1800cb869  lea     rcx, [rbp+90h+var_90+8]
0x1800cb86d  movaps  xmm1, [rbp+90h+var_100]
0x1800cb871  mov     rdx, [rsp+190h+var_138]
0x1800cb876  movaps  [rbp+90h+var_B0], xmm0
0x1800cb87a  movaps  xmm0, [rbp+90h+var_F0]
0x1800cb87e  movaps  [rbp+90h+var_90], xmm0
0x1800cb882  movsd   xmm0, [rbp+90h+var_D0]
0x1800cb887  movaps  [rbp+90h+var_A0], xmm1
0x1800cb88b  movaps  xmm1, [rbp+90h+var_E0]
0x1800cb88f  movsd   [rbp+90h+var_70], xmm0
0x1800cb894  movaps  [rbp+90h+var_80], xmm1
0x1800cb898  call    cs:__imp_DupString
0x1800cb89e  mov     ebx, eax
0x1800cb8a0  test    eax, eax
0x1800cb8a2  js      loc_1800CBB9F
0x1800cb8a8  mov     rdx, [rsp+190h+var_130]
0x1800cb8ad  lea     rcx, [rbp+90h+var_80+8]
0x1800cb8b1  call    cs:__imp_DupString
0x1800cb8b7  mov     ebx, eax
0x1800cb8b9  test    eax, eax
0x1800cb8bb  js      loc_1800CBB97
0x1800cb8c1  mov     rcx, [rsp+190h+var_140]
0x1800cb8c6  lea     rdx, [rsp+190h+var_124]
0x1800cb8cb  mov     dword ptr [rbp+90h+var_90], 0FFFFFFFFh
0x1800cb8d2  mov     [rsp+190h+var_124], r12d
0x1800cb8d7  mov     rax, [rcx]
0x1800cb8da  mov     rax, [rax+90h]
0x1800cb8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb8e6  mov     ebx, eax
0x1800cb8e8  test    eax, eax
0x1800cb8ea  js      loc_1800CBB8F
0x1800cb8f0  mov     eax, dword ptr [rbp+90h+var_60]
0x1800cb8f3  mov     rcx, r15
0x1800cb8f6  mov     dword ptr [rbp+90h+var_B0], eax
0x1800cb8f9  mov     eax, [rsp+190h+var_124]
0x1800cb8fd  mov     dword ptr [rbp+90h+var_B0+8], eax
0x1800cb900  movsd   [rbp+90h+var_70], xmm6
0x1800cb905  mov     dword ptr [rbp+90h+var_B0+4], 23h ; '#'
0x1800cb90c  call    cs:__imp_Messaging_IsRcsMessage
0x1800cb912  test    eax, eax
0x1800cb914  jz      loc_1800CBAFA
0x1800cb91a  mov     rax, [r15]
0x1800cb91d  lea     rdx, [rsp+190h+var_120]
0x1800cb922  mov     rcx, r15
0x1800cb925  mov     [rsp+190h+var_120], r12d
0x1800cb92a  mov     rax, [rax+220h]
0x1800cb931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb936  mov     ebx, eax
0x1800cb938  test    eax, eax
0x1800cb93a  js      loc_1800CBB76
0x1800cb940  mov     rax, [r15]
0x1800cb943  lea     rdx, [rsp+190h+var_128]
0x1800cb948  mov     rcx, r15
0x1800cb94b  mov     [rsp+190h+var_128], 0FFFFFFFFh
0x1800cb953  mov     rax, [rax+230h]
0x1800cb95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb95f  mov     ebx, eax
0x1800cb961  test    eax, eax
0x1800cb963  js      loc_1800CBB6E
0x1800cb969  mov     eax, [rsp+190h+var_120]
0x1800cb96d  dec     eax
0x1800cb96f  cmp     eax, esi
0x1800cb971  ja      loc_1800CBAFA
0x1800cb977  mov     rax, [r15]
0x1800cb97a  lea     rcx, [rsp+190h+var_158]
0x1800cb97f  mov     [rsp+190h+var_158], r12
0x1800cb984  mov     rbx, [rax+2B0h]
0x1800cb98b  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x1800cb990  mov     rdx, rax
0x1800cb993  mov     rcx, r15
0x1800cb996  mov     rax, rbx
0x1800cb999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb99e  test    eax, eax
0x1800cb9a0  jns     short loc_1800CB9B4
0x1800cb9a2  mov     r9d, 378h
0x1800cb9a8  mov     r8, r14
0x1800cb9ab  xor     edx, edx
0x1800cb9ad  mov     ecx, eax
0x1800cb9af  call    Log_HREvent
0x1800cb9b4  mov     rax, [rsp+190h+var_158]
0x1800cb9b9  test    rax, rax
0x1800cb9bc  jz      loc_1800CBAF0
0x1800cb9c2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800cb9c6  inc     rcx
0x1800cb9c9  cmp     [rax+rcx*2], r12w
0x1800cb9ce  jnz     short loc_1800CB9C6
0x1800cb9d0  test    rcx, rcx
0x1800cb9d3  jz      loc_1800CBAF0
0x1800cb9d9  lea     r9, [rsp+190h+Context]; lpContext
0x1800cb9de  mov     [rsp+190h+fPending], r12d
0x1800cb9e3  lea     r8, [rsp+190h+fPending]; fPending
0x1800cb9e8  mov     [rsp+190h+Context], r12
0x1800cb9ed  xor     edx, edx; dwFlags
0x1800cb9ef  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800cb9f6  call    cs:__imp_InitOnceBeginInitialize
0x1800cb9fc  mov     rbx, [rsp+190h+Context]
0x1800cba01  lea     rdi, qword_18015DCE0
0x1800cba08  test    rbx, rbx
0x1800cba0b  jnz     short loc_1800CBA37
0x1800cba0d  mov     rcx, rdi; this
0x1800cba10  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800cba15  mov     r8, rdi; lpContext
0x1800cba18  mov     [rbp+90h+var_B8], r12
0x1800cba1c  xor     edx, edx; dwFlags
0x1800cba1e  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800cba25  call    cs:__imp_InitOnceComplete
0x1800cba2b  lea     rcx, [rbp+90h+var_B8]
0x1800cba2f  mov     rbx, rdi
0x1800cba32  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800cba37  mov     r8d, [rsp+190h+var_128]; unsigned int
0x1800cba3c  lea     rcx, [rbx+0F0h]; this
0x1800cba43  mov     rdx, [rsp+190h+var_158]; unsigned __int16 *
0x1800cba48  lea     r9, [rbp+90h+var_70]; double *
0x1800cba4c  call    ?GetCurrentFileTransferProgress@RcsFileTransferProgressTracker@@QEAAJPEBGKPEAN@Z; RcsFileTransferProgressTracker::GetCurrentFileTransferProgress(ushort const *,ulong,double *)
0x1800cba51  cmp     eax, 80070490h
0x1800cba56  jnz     short loc_1800CBAD5
0x1800cba58  lea     r9, [rsp+190h+Context]; lpContext
0x1800cba5d  mov     [rsp+190h+fPending], r12d
0x1800cba62  lea     r8, [rsp+190h+fPending]; fPending
0x1800cba67  mov     [rsp+190h+Context], r12
0x1800cba6c  xor     edx, edx; dwFlags
0x1800cba6e  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800cba75  call    cs:__imp_InitOnceBeginInitialize
0x1800cba7b  mov     rbx, [rsp+190h+Context]
0x1800cba80  test    rbx, rbx
0x1800cba83  jnz     short loc_1800CBAAF
0x1800cba85  mov     rcx, rdi; this
0x1800cba88  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800cba8d  mov     r8, rdi; lpContext
0x1800cba90  mov     [rbp+90h+var_B8], r12
0x1800cba94  xor     edx, edx; dwFlags
0x1800cba96  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800cba9d  call    cs:__imp_InitOnceComplete
0x1800cbaa3  lea     rcx, [rbp+90h+var_B8]
0x1800cbaa7  mov     rbx, rdi
0x1800cbaaa  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800cbaaf  mov     r8d, [rsp+190h+var_128]; unsigned int
0x1800cbab4  lea     rcx, [rbx+0F0h]; this
0x1800cbabb  mov     rdx, [rsp+190h+var_158]; unsigned __int16 *
0x1800cbac0  lea     r9, [rbp+90h+var_70]; double *
0x1800cbac4  call    ?GetCurrentFileTransferProgress@RcsFileTransferProgressTracker@@QEAAJPEBGKPEAN@Z; RcsFileTransferProgressTracker::GetCurrentFileTransferProgress(ushort const *,ulong,double *)
0x1800cbac9  test    eax, eax
0x1800cbacb  jns     short loc_1800CBAEB
0x1800cbacd  mov     r9d, 383h
0x1800cbad3  jmp     short loc_1800CBADF
0x1800cbad5  test    eax, eax
0x1800cbad7  jns     short loc_1800CBAEB
0x1800cbad9  mov     r9d, 387h
0x1800cbadf  mov     r8, r14
0x1800cbae2  xor     edx, edx
0x1800cbae4  mov     ecx, eax
0x1800cbae6  call    Log_HREvent
0x1800cbaeb  mov     edi, 48h ; 'H'
0x1800cbaf0  lea     rcx, [rsp+190h+var_158]
0x1800cbaf5  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x1800cbafa  lea     rdx, [rbp+90h+var_B0]
0x1800cbafe  mov     rcx, r13
0x1800cbb01  call    ?push_back@?$vector@U?$auto_struct@UUdmChatAttachment@@$1?FreeUdmChatAttachment@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmChatAttachment@@$1?FreeUdmChatAttachment@Udm@@YAXPEAU1@@Z@@@utl@@@utl@@QEAA_N$$QEAU?$auto_struct@UUdmChatAttachment@@$1?FreeUdmChatAttachment@Udm@@YAXPEAU1@@Z@@@Z; utl::vector<auto_struct<UdmChatAttachment,&Udm::FreeUdmChatAttachment(UdmChatAttachment *)>,utl::allocator<auto_struct<UdmChatAttachment,&Udm::FreeUdmChatAttachment(UdmChatAttachment *)>>>::push_back(auto_struct<UdmChatAttachment,&Udm::FreeUdmChatAttachment(UdmChatAttachment *)> &&)
0x1800cbb06  test    al, al
0x1800cbb08  jz      short loc_1800CBB7E
0x1800cbb0a  lea     rcx, [rbp+90h+var_B0]; this
0x1800cbb0e  call    ?FreeUdmChatAttachment@Udm@@YAXPEAUUdmChatAttachment@@@Z; Udm::FreeUdmChatAttachment(UdmChatAttachment *)
0x1800cbb13  mov     r8, rdi; Size
0x1800cbb16  lea     rcx, [rbp+90h+var_110]; void *
0x1800cbb1a  xor     edx, edx; Val
0x1800cbb1c  call    memset_0
0x1800cbb21  movaps  xmm0, [rbp+90h+var_110]
0x1800cbb25  lea     rcx, [rsp+190h+var_130]
0x1800cbb2a  movaps  xmm1, [rbp+90h+var_100]
0x1800cbb2e  movaps  [rbp+90h+var_B0], xmm0
0x1800cbb32  movaps  xmm0, [rbp+90h+var_F0]
0x1800cbb36  movaps  [rbp+90h+var_90], xmm0
0x1800cbb3a  movsd   xmm0, [rbp+90h+var_D0]
0x1800cbb3f  movaps  [rbp+90h+var_A0], xmm1
0x1800cbb43  movaps  xmm1, [rbp+90h+var_E0]
0x1800cbb47  movsd   [rbp+90h+var_70], xmm0
0x1800cbb4c  movaps  [rbp+90h+var_80], xmm1
0x1800cbb50  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x1800cbb55  lea     rcx, [rsp+190h+var_138]
0x1800cbb5a  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x1800cbb5f  lea     rcx, [rsp+190h+var_140]
0x1800cbb64  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800cbb69  jmp     loc_1800CB7AE
0x1800cbb6e  mov     r9d, 373h
0x1800cbb74  jmp     short loc_1800CBBA5
0x1800cbb76  mov     r9d, 370h
0x1800cbb7c  jmp     short loc_1800CBBA5
0x1800cbb7e  mov     ebx, 8007000Eh
0x1800cbb83  mov     r9d, 38Dh
0x1800cbb89  mov     ecx, ebx
  ... truncated ...
```
