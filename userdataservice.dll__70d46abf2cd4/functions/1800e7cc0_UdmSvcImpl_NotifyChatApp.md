# UdmSvcImpl_NotifyChatApp

- ea: `0x1800e7cc0`
- end: `0x1800e840a`
- name: `UdmSvcImpl_NotifyChatApp`
- size: `1866`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800021c4`
- `0x180002270`
- `0x18000231c`
- `0x180008ee8`
- `0x180008f0c`
- `0x180009990`
- `0x18001fc7c`
- `0x180020994`
- `0x18006ce2c`
- `0x18008d830`
- `0x1800caa34`
- `0x1800cd620`
- `0x1800e5c3c`
- `0x1800e5d8c`
- `0x1800e5ec4`
- `0x1800e6220`
- `0x1800e6340`
- `0x1800e6620`
- `0x1800e677c`
- `0x1800e7cc0`
- `0x180116598`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `MessagingDataModel2!Messaging_IsFilterProviderId` at `0x1800e7e54`
- `MessagingDataModel2!Messaging_IsFilterProviderId` at `0x1800e7e54`
- `MessagingDataModel2!Messaging_IsCustomAppProviderId` at `0x1800e7f57`
- `MessagingDataModel2!Messaging_IsCustomAppProviderId` at `0x1800e7f57`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e7d6e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e7d6e`

## string_xrefs

- `0x1800e7d38`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e7d80`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e7dbd`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e7e05`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e7e92`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e7f8f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e7fd6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e8014`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e805d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e80f1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e82d3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e8348`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e8391`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`

## pseudocode

```c
__int64 __fastcall UdmSvcImpl_NotifyChatApp(struct __MIDL_UserDataModelService_0001 *a1, __int64 a2, _DWORD *a3)
{
  int ServiceDataSession; // eax
  int DefaultMessagingApp; // ebx
  __int64 v7; // r9
  HRESULT v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  int DefaultFilterApp; // eax
  __int64 v15; // r9
  __int64 v16; // rcx
  int AllMessagingApps; // eax
  _QWORD *i; // rbx
  int v19; // eax
  int AllCompanionApps; // eax
  _QWORD *j; // rbx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // r8
  int v29; // esi
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  struct ChatApp *v33; // rbx
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  __int64 v37; // r8
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int Instance; // eax
  __int64 v42; // r9
  int v43; // eax
  _QWORD *k; // rbx
  int v45; // eax
  unsigned int v47; // [rsp+40h] [rbp-C0h] BYREF
  struct ChatApp *v48; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  struct ISmEntryId *v50; // [rsp+58h] [rbp-A8h] BYREF
  struct ChatAppManager *v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  __m128i v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+88h] [rbp-78h]
  struct ServiceDataSession *v56; // [rsp+90h] [rbp-70h] BYREF
  __int64 v57; // [rsp+98h] [rbp-68h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v59; // [rsp+B0h] [rbp-50h]
  _OWORD v60[4]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v61[4]; // [rsp+F8h] [rbp-8h] BYREF

  *a3 = 0;
  v56 = 0;
  ServiceDataSession = GetServiceDataSession(a1, &v56);
  DefaultMessagingApp = ServiceDataSession;
  if ( ServiceDataSession >= 0 )
  {
    ServiceDataSession = ServiceDataSession::ValidateCallerSecurity(v56, 0, 0x4000u, 1);
    DefaultMessagingApp = ServiceDataSession;
    if ( ServiceDataSession < 0 )
    {
      v7 = 716;
      goto LABEL_5;
    }
    ppv = 0;
    v8 = CoCreateInstance(
           &GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7,
           0,
           0x17u,
           &GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c,
           &ppv);
    DefaultMessagingApp = v8;
    if ( v8 < 0 )
    {
      Log_HREvent(
        (unsigned int)v8,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
        720);
LABEL_8:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
      goto LABEL_90;
    }
    v50 = 0;
    v9 = ChatUdmObjectIdToSmEntryId((const struct UdmObjectId *)a2, &v50);
    DefaultMessagingApp = v9;
    if ( v9 < 0 )
    {
      Log_HREvent(
        (unsigned int)v9,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
        722);
LABEL_11:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v50);
      goto LABEL_8;
    }
    v52 = 0;
    v10 = (*(__int64 (__fastcall **)(LPVOID, struct ISmEntryId *, __int64 *))(*(_QWORD *)ppv + 88LL))(ppv, v50, &v52);
    DefaultMessagingApp = v10;
    if ( v10 < 0 )
    {
      v11 = 724;
LABEL_14:
      Log_HREvent(
        (unsigned int)v10,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
        v11);
LABEL_15:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
      goto LABEL_11;
    }
    v47 = -1;
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 560LL))(v52, &v47);
    DefaultMessagingApp = v10;
    if ( v10 < 0 )
    {
      v11 = 726;
      goto LABEL_14;
    }
    if ( (unsigned int)Messaging_IsFilterProviderId(v47) )
    {
      if ( v47 == 3 )
      {
        LODWORD(v51) = 0;
        v48 = 0;
        DefaultFilterApp = ChatAppManager::GetDefaultFilterApp((int *)&v51, &v48);
        DefaultMessagingApp = DefaultFilterApp;
        if ( DefaultFilterApp < 0 )
        {
          v15 = 735;
LABEL_22:
          v16 = (unsigned int)DefaultFilterApp;
LABEL_23:
          Log_HREvent(
            v16,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
            v15);
LABEL_24:
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v48);
          goto LABEL_15;
        }
        if ( !(_DWORD)v51 )
          goto LABEL_88;
        DefaultFilterApp = ChatApp::Notify(v48, 57, 0, v47);
        DefaultMessagingApp = DefaultFilterApp;
        if ( DefaultFilterApp < 0 )
        {
          v15 = 739;
          goto LABEL_22;
        }
      }
      else
      {
        if ( v47 != 4 )
          Log_AssertionEvent_22(v13, v12, 746);
        LODWORD(v51) = 0;
        v48 = 0;
        DefaultFilterApp = ChatAppManager::GetDefaultFilterApp((int *)&v51, &v48);
        DefaultMessagingApp = DefaultFilterApp;
        if ( DefaultFilterApp < 0 )
        {
          v15 = 751;
          goto LABEL_22;
        }
        if ( !(_DWORD)v51 )
          goto LABEL_88;
        DefaultFilterApp = ChatApp::Notify(v48, 37, a2, v47);
        DefaultMessagingApp = DefaultFilterApp;
        if ( DefaultFilterApp < 0 )
        {
          v15 = 755;
          goto LABEL_22;
        }
      }
      *a3 = 1;
LABEL_88:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v48);
LABEL_89:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v50);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
      DefaultMessagingApp = 0;
      goto LABEL_90;
    }
    if ( (unsigned int)Messaging_IsCustomAppProviderId(v47) )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v59 = -1;
      AllMessagingApps = ChatAppManager::GetAllMessagingApps(&si128);
      DefaultMessagingApp = AllMessagingApps;
      if ( AllMessagingApps >= 0 )
      {
        for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
        {
          v19 = ChatApp::Notify(*i, 37, a2, v47);
          if ( v19 < 0 )
            Log_HREvent(
              (unsigned int)v19,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
              768);
        }
        v54 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        v55 = -1;
        AllCompanionApps = ChatAppManager::GetAllCompanionApps(&v54);
        DefaultMessagingApp = AllCompanionApps;
        if ( AllCompanionApps >= 0 )
        {
          for ( j = (_QWORD *)v54.m128i_i64[0]; j != (_QWORD *)v54.m128i_i64[1]; ++j )
          {
            v22 = ChatApp::Notify(*j, 37, a2, v47);
            if ( v22 < 0 )
              Log_HREvent(
                (unsigned int)v22,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
                776);
          }
          utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(&v54);
          utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(&si128);
          goto LABEL_89;
        }
        Log_HREvent(
          (unsigned int)AllCompanionApps,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
          773);
        utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(&v54);
      }
      else
      {
        Log_HREvent(
          (unsigned int)AllMessagingApps,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
          765);
      }
      utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(&si128);
      goto LABEL_15;
    }
    if ( !(unsigned int)Messaging_IsSmsMmsProviderId(v47) )
      Log_AssertionEvent_22(v24, v23, 781);
    LODWORD(v51) = 0;
    v48 = 0;
    DefaultMessagingApp = ChatAppManager::GetDefaultMessagingApp((int *)&v51, &v48);
    if ( DefaultMessagingApp < 0 )
    {
      memset(v60, 0, 58);
      v27 = UdmObjectIdToString(a2, v25, v60);
      v29 = v27;
      if ( v27 < 0 )
      {
        Log_HREvent(
          (unsigned int)v27,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
          791);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v48);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v50);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
        DefaultMessagingApp = v29;
        goto LABEL_90;
      }
      if ( (unsigned int)dword_180158088 > 3 && (unsigned __int8)tlgKeywordOn(&dword_180158088, 0x400000000000LL, v28) )
      {
        v57 = 2048;
        v53 = (__int64)v60;
        LODWORD(v51) = DefaultMessagingApp;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          v30,
          (unsigned int)&unk_18014A6D0,
          v31,
          v32,
          (__int64)&v51,
          (__int64)&v53,
          (__int64)&v57);
      }
      v15 = 802;
      v16 = (unsigned int)DefaultMessagingApp;
      goto LABEL_23;
    }
    if ( (_DWORD)v51 )
    {
      v33 = v48;
      if ( (unsigned int)dword_180158088 > 3 && (unsigned __int8)tlgKeywordOn(&dword_180158088, 0x400000000000LL, v26) )
      {
        v53 = 2048;
        v57 = *((_QWORD *)v33 + 3);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          v34,
          (unsigned int)&dword_18014A634,
          v35,
          v36,
          (__int64)&v57,
          (__int64)&v53);
      }
      DefaultFilterApp = ChatApp::Notify(v33, 37, a2, v47);
      DefaultMessagingApp = DefaultFilterApp;
      if ( DefaultFilterApp < 0 )
      {
        v15 = 815;
        goto LABEL_22;
      }
      *a3 = 1;
      goto LABEL_80;
    }
    memset(v61, 0, 58);
    DefaultFilterApp = UdmObjectIdToString(a2, v25, v61);
    DefaultMessagingApp = DefaultFilterApp;
    if ( DefaultFilterApp < 0 )
    {
      v15 = 822;
      goto LABEL_22;
    }
    if ( (unsigned int)dword_180158088 > 3 && (unsigned __int8)tlgKeywordOn(&dword_180158088, 0x400000000000LL, v37) )
    {
      v53 = (__int64)v61;
      LODWORD(v51) = *(_DWORD *)(a2 + 12);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v38,
        (unsigned int)byte_18014A683,
        v39,
        v40,
        (__int64)&v51,
        (__int64)&v53);
    }
    v51 = 0;
    Instance = ChatAppManager::GetInstance(&v51);
    DefaultMessagingApp = Instance;
    if ( Instance >= 0 )
    {
      Instance = ChatAppManager::QueuePendingMessagingNotification(
                   v51,
                   (const struct ChatMessageNotificationEventDataPayload *)a2,
                   v47);
      DefaultMessagingApp = Instance;
      if ( Instance >= 0 )
      {
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v51);
LABEL_80:
        v54 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        v55 = -1;
        v43 = ChatAppManager::GetAllCompanionApps(&v54);
        DefaultMessagingApp = v43;
        if ( v43 < 0 )
        {
          Log_HREvent(
            (unsigned int)v43,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
            839);
          utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(&v54);
          goto LABEL_24;
        }
        for ( k = (_QWORD *)v54.m128i_i64[0]; k != (_QWORD *)v54.m128i_i64[1]; ++k )
        {
          v45 = ChatApp::Notify(*k, 37, a2, v47);
          if ( v45 < 0 )
            Log_HREvent(
              (unsigned int)v45,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
              842);
        }
        utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(&v54);
        goto LABEL_88;
      }
      v42 = 834;
    }
    else
    {
      v42 = 833;
    }
    Log_HREvent(
      (unsigned int)Instance,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
      v42);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v51);
    goto LABEL_24;
  }
  v7 = 714;
LABEL_5:
  Log_HREvent(
    (unsigned int)ServiceDataSession,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
    v7);
LABEL_90:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v56);
  return (unsigned int)DefaultMessagingApp;
}

```

## disassembly

```asm
0x1800e7cc0  mov     [rsp-8+arg_18], rbx
0x1800e7cc5  push    rbp
0x1800e7cc6  push    rsi
0x1800e7cc7  push    rdi
0x1800e7cc8  push    r14
0x1800e7cca  push    r15
0x1800e7ccc  lea     rbp, [rsp-40h]
0x1800e7cd1  sub     rsp, 140h
0x1800e7cd8  mov     rax, cs:__security_cookie
0x1800e7cdf  xor     rax, rsp
0x1800e7ce2  mov     [rbp+60h+var_28], rax
0x1800e7ce6  mov     rsi, rdx
0x1800e7ce9  xor     r15d, r15d
0x1800e7cec  lea     rdx, [rbp+60h+var_D0]; struct ServiceDataSession **
0x1800e7cf0  mov     [r8], r15d
0x1800e7cf3  mov     [rbp+60h+var_D0], r15
0x1800e7cf7  mov     r14, r8
0x1800e7cfa  call    ?GetServiceDataSession@@YAJPEAU__MIDL_UserDataModelService_0001@@PEAPEAVServiceDataSession@@@Z; GetServiceDataSession(__MIDL_UserDataModelService_0001 *,ServiceDataSession * *)
0x1800e7cff  mov     ebx, eax
0x1800e7d01  test    eax, eax
0x1800e7d03  jns     short loc_1800E7D11
0x1800e7d05  mov     r9d, 2CAh
0x1800e7d0b  lea     edx, [r15+1]
0x1800e7d0f  jmp     short loc_1800E7D38
0x1800e7d11  mov     rcx, [rbp+60h+var_D0]; this
0x1800e7d15  mov     edi, 1
0x1800e7d1a  mov     r9d, edi; int
0x1800e7d1d  xor     edx, edx; unsigned int
0x1800e7d1f  mov     r8d, 4000h; unsigned int
0x1800e7d25  call    ?ValidateCallerSecurity@ServiceDataSession@@QEAAJKKH@Z; ServiceDataSession::ValidateCallerSecurity(ulong,ulong,int)
0x1800e7d2a  mov     ebx, eax
0x1800e7d2c  test    eax, eax
0x1800e7d2e  jns     short loc_1800E7D4B
0x1800e7d30  mov     r9d, 2CCh
0x1800e7d36  mov     edx, edi
0x1800e7d38  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e7d3f  mov     ecx, eax
0x1800e7d41  call    Log_HREvent
0x1800e7d46  jmp     loc_1800E83DC
0x1800e7d4b  xor     edx, edx; pUnkOuter
0x1800e7d4d  mov     [rsp+160h+var_110], r15
0x1800e7d52  lea     rax, [rsp+160h+var_110]
0x1800e7d57  lea     r9, _GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c; riid
0x1800e7d5e  mov     [rsp+160h+ppv], rax; ppv
0x1800e7d63  lea     rcx, _GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7; rclsid
0x1800e7d6a  lea     r8d, [rdx+17h]; dwClsContext
0x1800e7d6e  call    cs:__imp_CoCreateInstance
0x1800e7d74  mov     ebx, eax
0x1800e7d76  test    eax, eax
0x1800e7d78  jns     short loc_1800E7D9F
0x1800e7d7a  mov     r9d, 2D0h
0x1800e7d80  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e7d87  mov     edx, edi
0x1800e7d89  mov     ecx, eax
0x1800e7d8b  call    Log_HREvent
0x1800e7d90  lea     rcx, [rsp+160h+var_110]
0x1800e7d95  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e7d9a  jmp     loc_1800E83DC
0x1800e7d9f  lea     rdx, [rsp+160h+var_108]; struct ISmEntryId **
0x1800e7da4  mov     [rsp+160h+var_108], r15
0x1800e7da9  mov     rcx, rsi; struct UdmObjectId *
0x1800e7dac  call    ?ChatUdmObjectIdToSmEntryId@@YAJAEBUUdmObjectId@@PEAPEAUISmEntryId@@@Z; ChatUdmObjectIdToSmEntryId(UdmObjectId const &,ISmEntryId * *)
0x1800e7db1  mov     ebx, eax
0x1800e7db3  test    eax, eax
0x1800e7db5  jns     short loc_1800E7DD9
0x1800e7db7  mov     r9d, 2D2h
0x1800e7dbd  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e7dc4  mov     edx, edi
0x1800e7dc6  mov     ecx, eax
0x1800e7dc8  call    Log_HREvent
0x1800e7dcd  lea     rcx, [rsp+160h+var_108]
0x1800e7dd2  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e7dd7  jmp     short loc_1800E7D90
0x1800e7dd9  mov     rcx, [rsp+160h+var_110]
0x1800e7dde  lea     r8, [rsp+160h+var_F8]
0x1800e7de3  mov     rdx, [rsp+160h+var_108]
0x1800e7de8  mov     [rsp+160h+var_F8], r15
0x1800e7ded  mov     rax, [rcx]
0x1800e7df0  mov     rax, [rax+58h]
0x1800e7df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7df9  mov     ebx, eax
0x1800e7dfb  test    eax, eax
0x1800e7dfd  jns     short loc_1800E7E21
0x1800e7dff  mov     r9d, 2D4h
0x1800e7e05  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e7e0c  mov     edx, edi
0x1800e7e0e  mov     ecx, eax
0x1800e7e10  call    Log_HREvent
0x1800e7e15  lea     rcx, [rsp+160h+var_F8]
0x1800e7e1a  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e7e1f  jmp     short loc_1800E7DCD
0x1800e7e21  mov     rcx, [rsp+160h+var_F8]
0x1800e7e26  lea     rdx, [rsp+160h+var_120]
0x1800e7e2b  mov     [rsp+160h+var_120], 0FFFFFFFFh
0x1800e7e33  mov     rax, [rcx]
0x1800e7e36  mov     rax, [rax+230h]
0x1800e7e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7e42  mov     ebx, eax
0x1800e7e44  test    eax, eax
0x1800e7e46  jns     short loc_1800E7E50
0x1800e7e48  mov     r9d, 2D6h
0x1800e7e4e  jmp     short loc_1800E7E05
0x1800e7e50  mov     ecx, [rsp+160h+var_120]
0x1800e7e54  call    cs:__imp_Messaging_IsFilterProviderId
0x1800e7e5a  test    eax, eax
0x1800e7e5c  jz      loc_1800E7F53
0x1800e7e62  cmp     [rsp+160h+var_120], 3
0x1800e7e67  jnz     short loc_1800E7EE4
0x1800e7e69  lea     rdx, [rsp+160h+var_118]; struct ChatApp **
0x1800e7e6e  mov     dword ptr [rsp+160h+var_100], r15d
0x1800e7e73  lea     rcx, [rsp+160h+var_100]; int *
0x1800e7e78  mov     [rsp+160h+var_118], r15
0x1800e7e7d  call    ?GetDefaultFilterApp@ChatAppManager@@SAJPEAHPEAPEAVChatApp@@@Z; ChatAppManager::GetDefaultFilterApp(int *,ChatApp * *)
0x1800e7e82  mov     ebx, eax
0x1800e7e84  test    eax, eax
0x1800e7e86  jns     short loc_1800E7EAD
0x1800e7e88  mov     r9d, 2DFh
0x1800e7e8e  mov     ecx, eax
0x1800e7e90  mov     edx, edi
0x1800e7e92  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e7e99  call    Log_HREvent
0x1800e7e9e  lea     rcx, [rsp+160h+var_118]
0x1800e7ea3  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e7ea8  jmp     loc_1800E7E15
0x1800e7ead  cmp     dword ptr [rsp+160h+var_100], r15d
0x1800e7eb2  jz      loc_1800E83B1
0x1800e7eb8  mov     r9d, [rsp+160h+var_120]
0x1800e7ebd  xor     r8d, r8d
0x1800e7ec0  mov     rcx, [rsp+160h+var_118]
0x1800e7ec5  lea     edx, [r8+39h]
0x1800e7ec9  call    ?Notify@ChatApp@@QEAAJW4_SebiEventType@@PEBUChatMessageNotificationEventDataPayload@@K@Z; ChatApp::Notify(_SebiEventType,ChatMessageNotificationEventDataPayload const *,ulong)
0x1800e7ece  mov     ebx, eax
0x1800e7ed0  test    eax, eax
0x1800e7ed2  jns     short loc_1800E7EDC
0x1800e7ed4  mov     r9d, 2E3h
0x1800e7eda  jmp     short loc_1800E7E8E
0x1800e7edc  mov     [r14], edi
0x1800e7edf  jmp     loc_1800E83B1
0x1800e7ee4  cmp     [rsp+160h+var_120], 4
0x1800e7ee9  jz      short loc_1800E7EF6
0x1800e7eeb  mov     r8d, 2EAh
0x1800e7ef1  call    Log_AssertionEvent_22
0x1800e7ef6  lea     rdx, [rsp+160h+var_118]; struct ChatApp **
0x1800e7efb  mov     dword ptr [rsp+160h+var_100], r15d
0x1800e7f00  lea     rcx, [rsp+160h+var_100]; int *
0x1800e7f05  mov     [rsp+160h+var_118], r15
0x1800e7f0a  call    ?GetDefaultFilterApp@ChatAppManager@@SAJPEAHPEAPEAVChatApp@@@Z; ChatAppManager::GetDefaultFilterApp(int *,ChatApp * *)
0x1800e7f0f  mov     ebx, eax
0x1800e7f11  test    eax, eax
0x1800e7f13  jns     short loc_1800E7F20
0x1800e7f15  mov     r9d, 2EFh
0x1800e7f1b  jmp     loc_1800E7E8E
0x1800e7f20  cmp     dword ptr [rsp+160h+var_100], r15d
0x1800e7f25  jz      loc_1800E83B1
0x1800e7f2b  mov     r9d, [rsp+160h+var_120]
0x1800e7f30  mov     r8, rsi
0x1800e7f33  mov     rcx, [rsp+160h+var_118]
0x1800e7f38  mov     edx, 25h ; '%'
0x1800e7f3d  call    ?Notify@ChatApp@@QEAAJW4_SebiEventType@@PEBUChatMessageNotificationEventDataPayload@@K@Z; ChatApp::Notify(_SebiEventType,ChatMessageNotificationEventDataPayload const *,ulong)
0x1800e7f42  mov     ebx, eax
0x1800e7f44  test    eax, eax
0x1800e7f46  jns     short loc_1800E7EDC
0x1800e7f48  mov     r9d, 2F3h
0x1800e7f4e  jmp     loc_1800E7E8E
0x1800e7f53  mov     ecx, [rsp+160h+var_120]
0x1800e7f57  call    cs:__imp_Messaging_IsCustomAppProviderId
0x1800e7f5d  test    eax, eax
0x1800e7f5f  jz      loc_1800E808B
0x1800e7f65  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800e7f6d  lea     rcx, [rbp+60h+var_C0]
0x1800e7f71  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800e7f75  movdqu  [rbp+60h+var_C0], xmm0
0x1800e7f7a  mov     [rbp+60h+var_B0], r14
0x1800e7f7e  call    ?GetAllMessagingApps@ChatAppManager@@SAJPEAV?$vector@V?$CComPtr@VChatApp@@@ATL@@V?$allocator@V?$CComPtr@VChatApp@@@ATL@@@utl@@@utl@@@Z; ChatAppManager::GetAllMessagingApps(utl::vector<ATL::CComPtr<ChatApp>,utl::allocator<ATL::CComPtr<ChatApp>>> *)
0x1800e7f83  mov     ebx, eax
0x1800e7f85  test    eax, eax
0x1800e7f87  jns     short loc_1800E7FAD
0x1800e7f89  mov     r9d, 2FDh
0x1800e7f8f  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e7f96  mov     edx, edi
0x1800e7f98  mov     ecx, eax
0x1800e7f9a  call    Log_HREvent
0x1800e7f9f  lea     rcx, [rbp+60h+var_C0]
0x1800e7fa3  call    ?_Uninit@?$vector@V?$CComPtr@UIStore@@@ATL@@V?$allocator@V?$CComPtr@UIStore@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(void)
0x1800e7fa8  jmp     loc_1800E7E15
0x1800e7fad  mov     rbx, qword ptr [rbp+60h+var_C0]
0x1800e7fb1  cmp     rbx, qword ptr [rbp+60h+var_C0+8]
0x1800e7fb5  jz      short loc_1800E7FEC
0x1800e7fb7  mov     r9d, [rsp+160h+var_120]
0x1800e7fbc  mov     r8, rsi
0x1800e7fbf  mov     rcx, [rbx]
0x1800e7fc2  mov     edx, 25h ; '%'
0x1800e7fc7  call    ?Notify@ChatApp@@QEAAJW4_SebiEventType@@PEBUChatMessageNotificationEventDataPayload@@K@Z; ChatApp::Notify(_SebiEventType,ChatMessageNotificationEventDataPayload const *,ulong)
0x1800e7fcc  test    eax, eax
0x1800e7fce  jns     short loc_1800E7FE6
0x1800e7fd0  mov     r9d, 300h
0x1800e7fd6  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e7fdd  xor     edx, edx
0x1800e7fdf  mov     ecx, eax
0x1800e7fe1  call    Log_HREvent
0x1800e7fe6  add     rbx, 8
0x1800e7fea  jmp     short loc_1800E7FB1
0x1800e7fec  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800e7ff4  lea     rcx, [rsp+160h+var_E8]
0x1800e7ff9  movdqu  [rsp+160h+var_E8], xmm0
0x1800e7fff  mov     [rbp+60h+var_D8], r14
0x1800e8003  call    ?GetAllCompanionApps@ChatAppManager@@SAJPEAV?$vector@V?$CComPtr@VChatApp@@@ATL@@V?$allocator@V?$CComPtr@VChatApp@@@ATL@@@utl@@@utl@@@Z; ChatAppManager::GetAllCompanionApps(utl::vector<ATL::CComPtr<ChatApp>,utl::allocator<ATL::CComPtr<ChatApp>>> *)
0x1800e8008  mov     ebx, eax
0x1800e800a  test    eax, eax
0x1800e800c  jns     short loc_1800E8033
0x1800e800e  mov     r9d, 305h
0x1800e8014  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e801b  mov     edx, edi
0x1800e801d  mov     ecx, eax
0x1800e801f  call    Log_HREvent
0x1800e8024  lea     rcx, [rsp+160h+var_E8]
0x1800e8029  call    ?_Uninit@?$vector@V?$CComPtr@UIStore@@@ATL@@V?$allocator@V?$CComPtr@UIStore@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(void)
0x1800e802e  jmp     loc_1800E7F9F
0x1800e8033  mov     rbx, qword ptr [rsp+160h+var_E8]
0x1800e8038  cmp     rbx, qword ptr [rbp+60h+var_E8+8]
0x1800e803c  jz      short loc_1800E8073
0x1800e803e  mov     r9d, [rsp+160h+var_120]
0x1800e8043  mov     r8, rsi
0x1800e8046  mov     rcx, [rbx]
0x1800e8049  mov     edx, 25h ; '%'
0x1800e804e  call    ?Notify@ChatApp@@QEAAJW4_SebiEventType@@PEBUChatMessageNotificationEventDataPayload@@K@Z; ChatApp::Notify(_SebiEventType,ChatMessageNotificationEventDataPayload const *,ulong)
0x1800e8053  test    eax, eax
0x1800e8055  jns     short loc_1800E806D
0x1800e8057  mov     r9d, 308h
0x1800e805d  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e8064  xor     edx, edx
0x1800e8066  mov     ecx, eax
0x1800e8068  call    Log_HREvent
0x1800e806d  add     rbx, 8
0x1800e8071  jmp     short loc_1800E8038
0x1800e8073  lea     rcx, [rsp+160h+var_E8]
0x1800e8078  call    ?_Uninit@?$vector@V?$CComPtr@UIStore@@@ATL@@V?$allocator@V?$CComPtr@UIStore@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(void)
0x1800e807d  lea     rcx, [rbp+60h+var_C0]
0x1800e8081  call    ?_Uninit@?$vector@V?$CComPtr@UIStore@@@ATL@@V?$allocator@V?$CComPtr@UIStore@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<IStore>,utl::allocator<ATL::CComPtr<IStore>>>::_Uninit(void)
0x1800e8086  jmp     loc_1800E83BB
0x1800e808b  mov     ecx, [rsp+160h+var_120]; unsigned int
0x1800e808f  call    ?Messaging_IsSmsMmsProviderId@@YAHK@Z; Messaging_IsSmsMmsProviderId(ulong)
0x1800e8094  test    eax, eax
0x1800e8096  jnz     short loc_1800E80A3
0x1800e8098  mov     r8d, 30Dh
0x1800e809e  call    Log_AssertionEvent_22
0x1800e80a3  lea     rdx, [rsp+160h+var_118]; struct ChatApp **
0x1800e80a8  mov     dword ptr [rsp+160h+var_100], r15d
0x1800e80ad  lea     rcx, [rsp+160h+var_100]; int *
0x1800e80b2  mov     [rsp+160h+var_118], r15
0x1800e80b7  call    ?GetDefaultMessagingApp@ChatAppManager@@SAJPEAHPEAPEAVChatApp@@@Z; ChatAppManager::GetDefaultMessagingApp(int *,ChatApp * *)
0x1800e80bc  mov     ebx, eax
0x1800e80be  test    eax, eax
0x1800e80c0  jns     loc_1800E81A0
0x1800e80c6  xorps   xmm0, xmm0
0x1800e80c9  lea     r8, [rbp+60h+var_A8]
0x1800e80cd  movups  xmmword ptr [rbp+60h+var_88], xmm0
0x1800e80d1  mov     rcx, rsi
0x1800e80d4  movups  xmmword ptr [rbp+60h+var_88+0Ah], xmm0
0x1800e80d8  movups  [rbp+60h+var_A8], xmm0
0x1800e80dc  movups  [rbp+60h+var_98], xmm0
0x1800e80e0  call    UdmObjectIdToString
0x1800e80e5  mov     esi, eax
0x1800e80e7  test    eax, eax
0x1800e80e9  jns     short loc_1800E8130
0x1800e80eb  mov     r9d, 317h
0x1800e80f1  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e80f8  mov     edx, edi
0x1800e80fa  mov     ecx, eax
0x1800e80fc  call    Log_HREvent
0x1800e8101  lea     rcx, [rsp+160h+var_118]
0x1800e8106  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e810b  lea     rcx, [rsp+160h+var_F8]
0x1800e8110  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e8115  lea     rcx, [rsp+160h+var_108]
0x1800e811a  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e811f  lea     rcx, [rsp+160h+var_110]
0x1800e8124  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e8129  mov     ebx, esi
0x1800e812b  jmp     loc_1800E83DC
0x1800e8130  mov     eax, cs:dword_180158088
0x1800e8136  cmp     eax, 3
0x1800e8139  jbe     short loc_1800E8193
0x1800e813b  mov     rdx, 400000000000h
0x1800e8145  lea     rcx, dword_180158088
0x1800e814c  call    _tlgKeywordOn
0x1800e8151  test    al, al
0x1800e8153  jz      short loc_1800E8193
0x1800e8155  lea     rax, [rbp+60h+var_A8]
0x1800e8159  mov     [rbp+60h+var_C8], 800h
0x1800e8161  mov     [rsp+160h+var_F0], rax
0x1800e8166  lea     rdx, unk_18014A6D0
0x1800e816d  lea     rax, [rbp+60h+var_C8]
0x1800e8171  mov     dword ptr [rsp+160h+var_100], ebx
0x1800e8175  mov     [rsp+160h+var_130], rax
0x1800e817a  lea     rax, [rsp+160h+var_F0]
0x1800e817f  mov     [rsp+160h+var_138], rax
0x1800e8184  lea     rax, [rsp+160h+var_100]
0x1800e8189  mov     [rsp+160h+ppv], rax
0x1800e818e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
  ... truncated ...
```
