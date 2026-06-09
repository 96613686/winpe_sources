# GetLocalIdArrayFromAppointmentRemoteObjectId(ushort const *,int,ulong *,UdmObjectId * *,UdmObjectId * *)

- ea: `0x1800e8fdc`
- end: `0x1800e98be`
- name: `?GetLocalIdArrayFromAppointmentRemoteObjectId@@YAJPEBGHPEAKPEAPEAUUdmObjectId@@2@Z`
- size: `2274`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, int@<edx>, unsigned int *@<r8>, struct UdmObjectId **@<r9>, struct UdmObjectId **)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a6100`

## callees

- `0x1800049f0`
- `0x1800054c0`
- `0x180008ee8`
- `0x180008f0c`
- `0x18000ae80`
- `0x18000e1f8`
- `0x180012988`
- `0x1800303cc`
- `0x180032228`
- `0x180049f80`
- `0x18005b080`
- `0x18005e048`
- `0x180060b40`
- `0x180065fb0`
- `0x180072ccc`
- `0x18007ca60`
- `0x1800e8da0`
- `0x1800e8fdc`
- `0x1800e9988`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800e9139`
- `msvcrt!wcscpy_s` at `0x1800e9139`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e93da`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e93da`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800e9392`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800e9392`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e93b4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e93b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e90f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e90f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e9120`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e9120`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e975d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e97a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e975d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e97a2`
- `unistore!CreateStoreManager` at `0x1800e9167`
- `unistore!CreateStoreManager` at `0x1800e9167`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x1800e9067`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x1800e9067`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800e90e3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800e90e3`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800e909a`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800e909a`

## string_xrefs

- `0x1800e90c6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e91fb`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e928f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e95ef`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e961f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e9652`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e9677`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e96b6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e9703`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e9775`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800e97c4`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`

## pseudocode

```c
__int64 __fastcall GetLocalIdArrayFromAppointmentRemoteObjectId(
        const unsigned __int16 *a1,
        int a2,
        unsigned int *a3,
        struct UdmObjectId **a4,
        struct UdmObjectId **a5)
{
  void **v7; // rax
  int RpcClientThreadToken; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  LONG PackageFamilyNameFromToken; // eax
  void **v14; // rbx
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  char *v21; // rbx
  int PropertiesForStore; // esi
  __int64 v23; // r12
  char *v24; // r14
  __int64 v25; // r13
  int v26; // eax
  int v27; // r15d
  StorePropertyCache *v28; // rsi
  __int64 v29; // rcx
  char *v30; // rcx
  char *v31; // r8
  int v32; // eax
  int v33; // edx
  char *v34; // rbx
  char v35; // al
  int v36; // eax
  char *v37; // rcx
  __int64 *v38; // rdx
  int v39; // eax
  char *v40; // rsi
  char *v41; // rcx
  __int64 *v42; // rdx
  __int64 v43; // r9
  __int64 v44; // r9
  __int64 v45; // r9
  __int64 v46; // r9
  __int64 v47; // rdx
  unsigned __int64 v48; // rbx
  struct UdmObjectId *v49; // rsi
  SIZE_T v50; // r9
  __int64 v51; // r9
  __int64 v52; // rcx
  __int64 v53; // rdx
  unsigned int i; // ecx
  __int64 v55; // rax
  __int64 v56; // r8
  int v57; // eax
  struct UdmObjectId *v58; // r9
  __int64 v60; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Pid[2]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE token; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v64; // [rsp+60h] [rbp-A0h] BYREF
  struct UdmObjectId *v65; // [rsp+68h] [rbp-98h] BYREF
  __int64 v66; // [rsp+70h] [rbp-90h] BYREF
  int v67; // [rsp+78h] [rbp-88h]
  __int64 v68; // [rsp+80h] [rbp-80h] BYREF
  char *v69; // [rsp+88h] [rbp-78h]
  char *v70; // [rsp+90h] [rbp-70h]
  __int64 v71; // [rsp+98h] [rbp-68h] BYREF
  char *v72; // [rsp+A0h] [rbp-60h]
  char *v73; // [rsp+A8h] [rbp-58h]
  __int64 v74; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID Context; // [rsp+B8h] [rbp-48h] BYREF
  struct StorePropertySet *v76; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v77; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int *v78; // [rsp+D0h] [rbp-30h]
  struct UdmObjectId **v79; // [rsp+D8h] [rbp-28h]
  struct UdmObjectId **v80; // [rsp+E0h] [rbp-20h]
  __int64 v81; // [rsp+E8h] [rbp-18h] BYREF
  int v82; // [rsp+F0h] [rbp-10h]
  int v83; // [rsp+F4h] [rbp-Ch]
  const unsigned __int16 *v84; // [rsp+F8h] [rbp-8h]
  __int64 v85; // [rsp+100h] [rbp+0h]
  int v86; // [rsp+108h] [rbp+8h]
  int v87; // [rsp+10Ch] [rbp+Ch]
  __int64 *v88; // [rsp+110h] [rbp+10h]
  unsigned int v89[2]; // [rsp+118h] [rbp+18h] BYREF
  int v90; // [rsp+120h] [rbp+20h]
  WCHAR packageFamilyName[128]; // [rsp+130h] [rbp+30h] BYREF

  *a3 = 0;
  *a4 = 0;
  v78 = a3;
  LODWORD(v65) = a2;
  *a5 = 0;
  v80 = a5;
  v79 = a4;
  memset_0(packageFamilyName, 0, sizeof(packageFamilyName));
  if ( a2 )
  {
    token = 0;
    v7 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&token);
    RpcClientThreadToken = GetRpcClientThreadToken(8u, v7);
    v9 = RpcClientThreadToken;
    if ( RpcClientThreadToken < 0 )
    {
      v10 = 265;
      v11 = 1;
      v12 = (unsigned int)RpcClientThreadToken;
LABEL_10:
      Log_HREvent(
        v12,
        v11,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
        v10);
LABEL_19:
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&token);
      return v9;
    }
    packageFamilyNameLength[0] = 128;
    PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(token, packageFamilyNameLength, packageFamilyName);
    v9 = PackageFamilyNameFromToken;
    if ( PackageFamilyNameFromToken == 15700 )
    {
      Pid[0] = 0;
      if ( I_RpcBindingInqLocalClientPID(0, Pid)
        || (EnterCriticalSection(&g_testProcessMapLock),
            v14 = *(void ***)utl::_HashTable<unsigned long,utl::pair<unsigned long const,bool>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,bool>>,0>::find<void>(
                               &g_testProcessMap,
                               &v77,
                               Pid),
            LeaveCriticalSection(&g_testProcessMapLock),
            &g_testProcessMap == v14) )
      {
        v9 = 0;
        goto LABEL_19;
      }
      if ( wcscpy_s(packageFamilyName, 0x80u, L"testpackage_0000000000000") )
      {
        v10 = 280;
        v9 = -2147024809;
LABEL_9:
        v11 = 0;
        v12 = v9;
        goto LABEL_10;
      }
    }
    else if ( PackageFamilyNameFromToken )
    {
      if ( PackageFamilyNameFromToken > 0 )
        v9 = (unsigned __int16)PackageFamilyNameFromToken | 0x80070000;
      v10 = 272;
      goto LABEL_9;
    }
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&token);
  }
  v74 = 0;
  v15 = CreateStoreManager(0, &v74);
  v9 = v15;
  if ( v15 < 0 )
  {
    v16 = 291;
    v17 = (unsigned int)v15;
LABEL_25:
    Log_HREvent(v17, 1, "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp", v16);
    goto LABEL_94;
  }
  if ( !a1 )
  {
    v9 = -2147024809;
    Log_HREvent(2147942487LL, 0, "onecoreuap\\private\\base\\inc\\BlobHelpers.h", 38);
    Log_AssertionEvent_23();
LABEL_24:
    v16 = 294;
    v17 = v9;
    goto LABEL_25;
  }
  token = 0;
  v18 = StringCbLengthW(a1, 0x190u, (unsigned __int64 *)&token);
  v9 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent((unsigned int)v18, 1, "onecoreuap\\private\\base\\inc\\BlobHelpers.h", 42);
    goto LABEL_24;
  }
  v82 = (_DWORD)token + 2;
  v87 = 17432641;
  v86 = 4;
  v81 = 17432641;
  v88 = &v81;
  v83 = 0;
  v84 = a1;
  v85 = 4;
  v60 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v74 + 136LL))(v74, 3, 0x2000000);
  v9 = v19;
  if ( v19 >= 0 )
  {
    utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&v68);
    utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&v71);
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 120LL))(v60);
    v21 = v69;
    PropertiesForStore = v20;
    v23 = v68;
    v24 = v72;
    v25 = v71;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( PropertiesForStore < 0 )
        {
          if ( PropertiesForStore == -2147024871 )
          {
            *(_QWORD *)packageFamilyNameLength = 0;
            v48 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)&v21[-v23] >> 2);
            PropertiesForStore = ULongLongMult(v48, 0xCu, (unsigned __int64 *)packageFamilyNameLength);
            if ( PropertiesForStore >= 0 )
            {
              v65 = (struct UdmObjectId *)LocalAlloc(0x40u, *(SIZE_T *)packageFamilyNameLength);
              v49 = v65;
              if ( v65 )
              {
                *(_QWORD *)packageFamilyNameLength = LocalAlloc(0x40u, *(SIZE_T *)packageFamilyNameLength);
                v50 = *(_QWORD *)packageFamilyNameLength;
                if ( *(_QWORD *)packageFamilyNameLength )
                {
                  for ( i = 0; i < v48; *(_DWORD *)(v50 + 4 * v56 + 8) = v55 )
                  {
                    v55 = i++;
                    v56 = 3 * v55;
                    LODWORD(v55) = *(_DWORD *)(v23 + 12 * v55 + 8);
                    *(_QWORD *)((char *)v49 + 4 * v56) = *(_QWORD *)(v23 + 4 * v56);
                    *((_DWORD *)v49 + v56 + 2) = v55;
                    LODWORD(v55) = *(_DWORD *)(v25 + 4 * v56 + 8);
                    *(_QWORD *)(v50 + 4 * v56) = *(_QWORD *)(v25 + 4 * v56);
                  }
                  v57 = ULongLongToULong(v48, v78);
                  v9 = v57;
                  if ( v57 >= 0 )
                  {
                    v65 = 0;
                    *(_QWORD *)packageFamilyNameLength = 0;
                    *v79 = v49;
                    *v80 = v58;
                    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(packageFamilyNameLength);
                    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v65);
                    utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v71);
                    utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v68);
                    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v60);
                    v9 = 0;
                    goto LABEL_94;
                  }
                  v51 = 394;
                  v53 = 1;
                  v52 = (unsigned int)v57;
                }
                else
                {
                  v9 = -2147024882;
                  v51 = 386;
                  v52 = 2147942414LL;
                  v53 = 0;
                }
                Log_HREvent(
                  v52,
                  v53,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
                  v51);
                auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(packageFamilyNameLength);
              }
              else
              {
                v9 = -2147024882;
                Log_HREvent(
                  2147942414LL,
                  0,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
                  383);
              }
              auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v65);
              goto LABEL_74;
            }
            v46 = 380;
            v47 = 1;
          }
          else
          {
            v46 = 375;
            v47 = 0;
          }
          Log_HREvent(
            (unsigned int)PropertiesForStore,
            v47,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
            v46);
          goto LABEL_77;
        }
        *(_QWORD *)Pid = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v60 + 40LL))(v60, Pid);
        PropertiesForStore = v26;
        if ( v26 < 0 )
        {
          Log_HREvent(
            (unsigned int)v26,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
            323);
          goto LABEL_76;
        }
        ATL::CComQIPtr<IUSItem,&__s_GUID const _GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16>::CComQIPtr<IUSItem,&__s_GUID const _GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16>(
          &v64,
          *(_QWORD *)Pid);
        if ( !v64 )
        {
          v45 = 326;
          v9 = -2147467262;
LABEL_72:
          Log_HREvent(
            v9,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
            v45);
LABEL_73:
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v64);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(Pid);
LABEL_74:
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v71);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v68);
          goto LABEL_28;
        }
        *(_QWORD *)v89 = 0;
        v90 = 0;
        PropertiesForStore = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v64 + 24LL))(v64, v89);
        if ( PropertiesForStore < 0 )
        {
          v43 = 329;
          v29 = (unsigned int)PropertiesForStore;
          goto LABEL_69;
        }
        v27 = v90;
        v66 = v89[0] | 0xC00000000LL;
        v67 = v90;
        if ( !(_DWORD)v65 )
          break;
        v76 = 0;
        packageFamilyNameLength[0] = 0;
        Context = 0;
        InitOnceBeginInitialize(&stru_18015EA68, 0, (PBOOL)packageFamilyNameLength, &Context);
        v28 = (StorePropertyCache *)Context;
        if ( !Context )
        {
          qword_18015EA70 = 0;
          InitializeCriticalSectionEx(&stru_18015EA78, 0, 0);
          utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(qword_18015EAA0);
          v77 = 0;
          InitOnceComplete(&stru_18015EA68, 0, &qword_18015EA70);
          v28 = (StorePropertyCache *)&qword_18015EA70;
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v77);
        }
        PropertiesForStore = StorePropertyCache::GetPropertiesForStore(v28, v89[0], &v76);
        if ( !(unsigned int)IsItemNotFoundError(PropertiesForStore) )
        {
          if ( (int)v29 < 0 )
          {
            v43 = 346;
LABEL_69:
            Log_HREvent(
              v29,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
              v43);
            goto LABEL_70;
          }
          v30 = (char *)*((_QWORD *)v76 + 1);
          if ( v30 )
          {
            v31 = (char *)((char *)packageFamilyName - v30);
            do
            {
              v32 = *(unsigned __int16 *)&v31[(_QWORD)v30];
              v33 = *(unsigned __int16 *)v30 - v32;
              if ( v33 )
                break;
              v30 += 2;
            }
            while ( v32 );
            if ( !v33 )
              break;
          }
        }
        PropertiesForStore = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 96LL))(v60);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v64);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(Pid);
      }
      if ( v21 == v70 )
      {
        v34 = (char *)&v66 - v23;
        v35 = utl::vector<UdmObjectId,utl::allocator<UdmObjectId>>::_Grow(&v68);
        v23 = v68;
        if ( v35 )
        {
          v37 = v69;
          v38 = &v66;
          if ( v34 < &v69[-v68] )
            v38 = (__int64 *)&v34[v68];
          v21 = v69 + 12;
          *(_QWORD *)v69 = *v38;
          *((_DWORD *)v37 + 2) = *((_DWORD *)v38 + 2);
          v36 = 1;
          v69 = v37 + 12;
        }
        else
        {
          v21 = v69;
          v36 = 0;
        }
        if ( !v36 )
        {
          v45 = 360;
          v9 = -2147024882;
          goto LABEL_72;
        }
      }
      else
      {
        *(_QWORD *)v21 = v66;
        *((_DWORD *)v21 + 2) = v27;
        v21 += 12;
        v69 = v21;
      }
      token = 0;
      PropertiesForStore = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v64 + 168LL))(v64, &token);
      if ( PropertiesForStore < 0 )
        break;
      PropertiesForStore = (*(__int64 (__fastcall **)(HANDLE, unsigned int *))(*(_QWORD *)token + 24LL))(token, v89);
      if ( PropertiesForStore < 0 )
      {
        v44 = 365;
        goto LABEL_66;
      }
      v66 = v89[0] | 0xB00000000LL;
      v39 = v90;
      v67 = v90;
      if ( v24 == v73 )
      {
        v40 = (char *)&v66 - v25;
        if ( !(unsigned __int8)utl::vector<UdmObjectId,utl::allocator<UdmObjectId>>::_Grow(&v71) )
        {
          v9 = -2147024882;
          Log_HREvent(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
            371);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&token);
          goto LABEL_73;
        }
        v41 = v72;
        v42 = &v66;
        v25 = v71;
        if ( v40 < &v72[-v71] )
          v42 = (__int64 *)&v40[v71];
        v24 = v72 + 12;
        *(_QWORD *)v72 = *v42;
        *((_DWORD *)v41 + 2) = *((_DWORD *)v42 + 2);
      }
      else
      {
        *(_QWORD *)v24 = v66;
        *((_DWORD *)v24 + 2) = v39;
        v24 += 12;
      }
      v72 = v24;
      PropertiesForStore = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 96LL))(v60);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&token);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v64);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(Pid);
    }
    v44 = 363;
LABEL_66:
    Log_HREvent(
      (unsigned int)PropertiesForStore,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      v44);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&token);
LABEL_70:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v64);
LABEL_76:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(Pid);
LABEL_77:
    utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v71);
    utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v68);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v60);
    v9 = PropertiesForStore;
  }
  else
  {
    Log_HREvent(
      (unsigned int)v19,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      314);
LABEL_28:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v60);
  }
LABEL_94:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v74);
  return v9;
}

```

## disassembly

```asm
0x1800e8fdc  mov     [rsp-8+arg_8], rbx
0x1800e8fe1  push    rbp
0x1800e8fe2  push    rsi
0x1800e8fe3  push    rdi
0x1800e8fe4  push    r12
0x1800e8fe6  push    r13
0x1800e8fe8  push    r14
0x1800e8fea  push    r15
0x1800e8fec  lea     rbp, [rsp-140h]
0x1800e8ff4  sub     rsp, 240h
0x1800e8ffb  mov     rax, cs:__security_cookie
0x1800e9002  xor     rax, rsp
0x1800e9005  mov     [rbp+170h+var_40], rax
0x1800e900c  mov     dword ptr [r8], 0
0x1800e9013  mov     rsi, rcx
0x1800e9016  mov     rcx, [rbp+170h+arg_20]
0x1800e901d  xor     r15d, r15d
0x1800e9020  mov     [r9], r15
0x1800e9023  mov     ebx, edx
0x1800e9025  mov     [rbp+170h+var_1A0], r8
0x1800e9029  mov     r8d, 100h; Size
0x1800e902f  mov     dword ptr [rsp+270h+var_208], edx
0x1800e9033  xor     edx, edx; Val
0x1800e9035  mov     [rcx], r15
0x1800e9038  mov     [rbp+170h+var_190], rcx
0x1800e903c  lea     rcx, [rbp+170h+packageFamilyName]; void *
0x1800e9040  mov     [rbp+170h+var_198], r9
0x1800e9044  call    memset_0
0x1800e9049  test    ebx, ebx
0x1800e904b  jz      loc_1800E915D
0x1800e9051  lea     rcx, [rsp+270h+token]
0x1800e9056  mov     [rsp+270h+token], r15
0x1800e905b  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x1800e9060  mov     rdx, rax
0x1800e9063  lea     ecx, [r15+8]
0x1800e9067  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x1800e906d  mov     ebx, eax
0x1800e906f  test    eax, eax
0x1800e9071  jns     short loc_1800E9081
0x1800e9073  mov     r9d, 109h
0x1800e9079  lea     edx, [r15+1]
0x1800e907d  mov     ecx, eax
0x1800e907f  jmp     short loc_1800E90C6
0x1800e9081  mov     rcx, [rsp+270h+token]; token
0x1800e9086  lea     r8, [rbp+170h+packageFamilyName]; packageFamilyName
0x1800e908a  mov     r14d, 80h
0x1800e9090  lea     rdx, [rsp+270h+packageFamilyNameLength]; packageFamilyNameLength
0x1800e9095  mov     [rsp+270h+packageFamilyNameLength], r14d
0x1800e909a  call    cs:__imp_GetPackageFamilyNameFromToken
0x1800e90a0  mov     ebx, eax
0x1800e90a2  cmp     eax, 3D54h
0x1800e90a7  jz      short loc_1800E90D7
0x1800e90a9  test    eax, eax
0x1800e90ab  jz      loc_1800E9153
0x1800e90b1  jle     short loc_1800E90BC
0x1800e90b3  movzx   ebx, ax
0x1800e90b6  or      ebx, 80070000h
0x1800e90bc  mov     r9d, 110h
0x1800e90c2  xor     edx, edx
0x1800e90c4  mov     ecx, ebx
0x1800e90c6  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e90cd  call    Log_HREvent
0x1800e90d2  jmp     loc_1800E9185
0x1800e90d7  lea     rdx, [rsp+270h+Pid]; Pid
0x1800e90dc  mov     [rsp+270h+Pid], r15d
0x1800e90e1  xor     ecx, ecx; Binding
0x1800e90e3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800e90e9  test    eax, eax
0x1800e90eb  jnz     loc_1800E9182
0x1800e90f1  lea     rcx, ?g_testProcessMapLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800e90f8  call    cs:__imp_EnterCriticalSection
0x1800e90fe  lea     rdi, ?g_testProcessMap@@3V?$unordered_set@KU?$hash@K@utl@@U?$equal_to@K@2@V?$allocator@K@2@@utl@@A; utl::unordered_set<ulong,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<ulong>> g_testProcessMap
0x1800e9105  mov     rcx, rdi
0x1800e9108  lea     r8, [rsp+270h+Pid]
0x1800e910d  lea     rdx, [rbp+170h+var_1A8]
0x1800e9111  call    ??$find@X@?$_HashTable@KU?$pair@$$CBK_N@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBK_N@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBK_N@utl@@@utl@@U?$pair@$$CBK_N@2@@1@AEBK@Z; utl::_HashTable<ulong,utl::pair<ulong const,bool>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,bool>>,0>::find<void>(ulong const &)
0x1800e9116  lea     rcx, ?g_testProcessMapLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800e911d  mov     rbx, [rax]
0x1800e9120  call    cs:__imp_LeaveCriticalSection
0x1800e9126  cmp     rdi, rbx
0x1800e9129  jz      short loc_1800E9182
0x1800e912b  lea     r8, ?c_unitTestPackageFamilyName@@3QBGB; "testpackage_0000000000000"
0x1800e9132  mov     rdx, r14; SizeInWords
0x1800e9135  lea     rcx, [rbp+170h+packageFamilyName]; Destination
0x1800e9139  call    cs:__imp_wcscpy_s
0x1800e913f  test    eax, eax
0x1800e9141  jz      short loc_1800E9153
0x1800e9143  mov     r9d, 118h
0x1800e9149  mov     ebx, 80070057h
0x1800e914e  jmp     loc_1800E90C2
0x1800e9153  lea     rcx, [rsp+270h+token]
0x1800e9158  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800e915d  lea     rdx, [rbp+170h+var_1C0]
0x1800e9161  mov     [rbp+170h+var_1C0], r15
0x1800e9165  xor     ecx, ecx
0x1800e9167  call    cs:__imp_CreateStoreManager
0x1800e916d  mov     ebx, eax
0x1800e916f  test    eax, eax
0x1800e9171  jns     short loc_1800E9194
0x1800e9173  mov     r9d, 123h
0x1800e9179  mov     edx, 1
0x1800e917e  mov     ecx, eax
0x1800e9180  jmp     short loc_1800E91FB
0x1800e9182  mov     ebx, r15d
0x1800e9185  lea     rcx, [rsp+270h+token]
0x1800e918a  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800e918f  jmp     loc_1800E9892
0x1800e9194  mov     edi, 1
0x1800e9199  test    rsi, rsi
0x1800e919c  jnz     short loc_1800E91BE
0x1800e919e  mov     ebx, 80070057h
0x1800e91a3  lea     r9d, [rdi+25h]
0x1800e91a7  mov     ecx, ebx
0x1800e91a9  lea     r8, aOnecoreuapPriv_4; "onecoreuap\\private\\base\\inc\\BlobHel"...
0x1800e91b0  xor     edx, edx
0x1800e91b2  call    Log_HREvent
0x1800e91b7  call    Log_AssertionEvent_23
0x1800e91bc  jmp     short loc_1800E91F1
0x1800e91be  lea     r8, [rsp+270h+token]; unsigned __int64 *
0x1800e91c3  mov     [rsp+270h+token], r15
0x1800e91c8  mov     edx, 190h; unsigned __int64
0x1800e91cd  mov     rcx, rsi; unsigned __int16 *
0x1800e91d0  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800e91d5  mov     ebx, eax
0x1800e91d7  test    eax, eax
0x1800e91d9  jns     short loc_1800E920C
0x1800e91db  mov     r9d, 2Ah ; '*'
0x1800e91e1  lea     r8, aOnecoreuapPriv_4; "onecoreuap\\private\\base\\inc\\BlobHel"...
0x1800e91e8  mov     edx, edi
0x1800e91ea  mov     ecx, eax
0x1800e91ec  call    Log_HREvent
0x1800e91f1  mov     r9d, 126h
0x1800e91f7  mov     edx, edi
0x1800e91f9  mov     ecx, ebx
0x1800e91fb  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e9202  call    Log_HREvent
0x1800e9207  jmp     loc_1800E9889
0x1800e920c  mov     eax, dword ptr [rsp+270h+token]
0x1800e9210  lea     rdx, [rsp+270h+var_230]
0x1800e9215  add     eax, 2
0x1800e9218  mov     [rsp+270h+var_240], rdx
0x1800e921d  mov     [rbp+170h+var_180], eax
0x1800e9220  lea     rdx, [rbp+170h+var_170]
0x1800e9224  mov     [rsp+270h+var_248], rdx
0x1800e9229  mov     ecx, 10A0041h
0x1800e922e  mov     [rbp+170h+var_164], ecx
0x1800e9231  mov     eax, 4
0x1800e9236  mov     rcx, [rbp+170h+var_1C0]
0x1800e923a  xor     r9d, r9d
0x1800e923d  mov     [rbp+170h+var_168], eax
0x1800e9240  mov     r8d, 2000000h
0x1800e9246  lea     rax, [rbp+170h+var_188]
0x1800e924a  mov     [rbp+170h+var_188], 10A0041h
0x1800e9252  mov     [rbp+170h+var_160], rax
0x1800e9256  mov     [rbp+170h+var_17C], r15d
0x1800e925a  lea     edx, [r9+3]
0x1800e925e  mov     [rbp+170h+var_178], rsi
0x1800e9262  mov     [rbp+170h+var_170], 4
0x1800e926a  mov     [rsp+270h+var_230], r15
0x1800e926f  mov     rax, [rcx]
0x1800e9272  mov     [rsp+270h+var_250], r15
0x1800e9277  mov     rax, [rax+88h]
0x1800e927e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9283  mov     ebx, eax
0x1800e9285  test    eax, eax
0x1800e9287  jns     short loc_1800E92AE
0x1800e9289  mov     r9d, 13Ah
0x1800e928f  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e9296  mov     edx, edi
0x1800e9298  mov     ecx, eax
0x1800e929a  call    Log_HREvent
0x1800e929f  lea     rcx, [rsp+270h+var_230]
0x1800e92a4  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e92a9  jmp     loc_1800E9889
0x1800e92ae  lea     rcx, [rbp+170h+var_1F0]
0x1800e92b2  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800e92b7  lea     rcx, [rbp+170h+var_1D8]
0x1800e92bb  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800e92c0  mov     rcx, [rsp+270h+var_230]
0x1800e92c5  mov     rax, [rcx]
0x1800e92c8  mov     rax, [rax+78h]
0x1800e92cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e92d1  mov     rbx, [rbp+170h+var_1E8]
0x1800e92d5  mov     esi, eax
0x1800e92d7  mov     r12, [rbp+170h+var_1F0]
0x1800e92db  mov     r14, [rbp+170h+var_1D0]
0x1800e92df  mov     r13, [rbp+170h+var_1D8]
0x1800e92e3  test    esi, esi
0x1800e92e5  js      loc_1800E96F3
0x1800e92eb  mov     rcx, [rsp+270h+var_230]
0x1800e92f0  lea     rdx, [rsp+270h+Pid]
0x1800e92f5  mov     qword ptr [rsp+270h+Pid], r15
0x1800e92fa  mov     rax, [rcx]
0x1800e92fd  mov     rax, [rax+28h]
0x1800e9301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9306  mov     esi, eax
0x1800e9308  test    eax, eax
0x1800e930a  js      loc_1800E96B0
0x1800e9310  mov     rdx, qword ptr [rsp+270h+Pid]
0x1800e9315  lea     rcx, [rsp+270h+var_210]
0x1800e931a  call    ??0?$CComQIPtr@UIUSItem@@$1?_GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IUSItem,&__s_GUID const _GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16>::CComQIPtr<IUSItem,&__s_GUID const _GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16>(IUnknown *)
0x1800e931f  mov     rcx, [rsp+270h+var_210]
0x1800e9324  test    rcx, rcx
0x1800e9327  jz      loc_1800E966A
0x1800e932d  xor     eax, eax
0x1800e932f  lea     rdx, [rbp+170h+var_158]
0x1800e9333  mov     qword ptr [rbp+170h+var_158], rax
0x1800e9337  mov     [rbp+170h+var_150], eax
0x1800e933a  mov     rax, [rcx]
0x1800e933d  mov     rax, [rax+18h]
0x1800e9341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9346  mov     esi, eax
0x1800e9348  test    eax, eax
0x1800e934a  js      loc_1800E9648
0x1800e9350  mov     eax, [rbp+170h+var_158]
0x1800e9353  mov     r15d, [rbp+170h+var_150]
0x1800e9357  mov     dword ptr [rsp+270h+var_200], eax
0x1800e935b  xor     eax, eax
0x1800e935d  mov     [rsp+270h+var_1F8], r15d
0x1800e9362  mov     dword ptr [rsp+270h+var_200+4], 0Ch
0x1800e936a  cmp     dword ptr [rsp+270h+var_208], eax
0x1800e936e  jz      loc_1800E946F
0x1800e9374  lea     r9, [rbp+170h+Context]; lpContext
0x1800e9378  mov     [rbp+170h+var_1B0], rax
0x1800e937c  lea     r8, [rsp+270h+packageFamilyNameLength]; fPending
0x1800e9381  mov     [rsp+270h+packageFamilyNameLength], eax
0x1800e9385  xor     edx, edx; dwFlags
0x1800e9387  mov     [rbp+170h+Context], rax
0x1800e938b  lea     rcx, stru_18015EA68; lpInitOnce
0x1800e9392  call    cs:__imp_InitOnceBeginInitialize
0x1800e9398  mov     rsi, [rbp+170h+Context]
0x1800e939c  test    rsi, rsi
0x1800e939f  jnz     short loc_1800E93F0
0x1800e93a1  xor     r8d, r8d; Flags
0x1800e93a4  mov     cs:qword_18015EA70, rsi
0x1800e93ab  xor     edx, edx; dwSpinCount
0x1800e93ad  lea     rcx, stru_18015EA78; lpCriticalSection
0x1800e93b4  call    cs:__imp_InitializeCriticalSectionEx
0x1800e93ba  lea     rcx, qword_18015EAA0
0x1800e93c1  call    ??0?$unordered_map@W4_SebiEventType@@U_GUID@@U?$hash@W4_SebiEventType@@@utl@@U?$equal_to@W4_SebiEventType@@@4@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@4@@utl@@QEAA@XZ; utl::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>(void)
0x1800e93c6  lea     r8, qword_18015EA70; lpContext
0x1800e93cd  mov     [rbp+170h+var_1A8], rsi
0x1800e93d1  xor     edx, edx; dwFlags
0x1800e93d3  lea     rcx, stru_18015EA68; lpInitOnce
0x1800e93da  call    cs:__imp_InitOnceComplete
0x1800e93e0  lea     rcx, [rbp+170h+var_1A8]
0x1800e93e4  lea     rsi, qword_18015EA70
0x1800e93eb  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800e93f0  mov     edx, [rbp+170h+var_158]; unsigned int
0x1800e93f3  lea     r8, [rbp+170h+var_1B0]; struct StorePropertySet **
0x1800e93f7  mov     rcx, rsi; this
0x1800e93fa  call    ?GetPropertiesForStore@StorePropertyCache@@QEAAJKPEAPEBUStorePropertySet@@@Z; StorePropertyCache::GetPropertiesForStore(ulong,StorePropertySet const * *)
0x1800e93ff  mov     ecx, eax; int
0x1800e9401  mov     esi, eax
0x1800e9403  call    ?IsItemNotFoundError@@YAHJ@Z; IsItemNotFoundError(long)
0x1800e9408  test    eax, eax
0x1800e940a  jnz     short loc_1800E9440
0x1800e940c  test    ecx, ecx
0x1800e940e  js      loc_1800E95E2
0x1800e9414  mov     rax, [rbp+170h+var_1B0]
0x1800e9418  mov     rcx, [rax+8]
0x1800e941c  test    rcx, rcx
0x1800e941f  jz      short loc_1800E9440
0x1800e9421  lea     r8, [rbp+170h+packageFamilyName]
0x1800e9425  sub     r8, rcx
0x1800e9428  movzx   edx, word ptr [rcx]
0x1800e942b  movzx   eax, word ptr [rcx+r8]
0x1800e9430  sub     edx, eax
0x1800e9432  jnz     short loc_1800E943C
0x1800e9434  add     rcx, 2
0x1800e9438  test    eax, eax
0x1800e943a  jnz     short loc_1800E9428
0x1800e943c  test    edx, edx
0x1800e943e  jz      short loc_1800E946F
0x1800e9440  mov     rcx, [rsp+270h+var_230]
0x1800e9445  mov     rax, [rcx]
0x1800e9448  mov     rax, [rax+60h]
0x1800e944c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9451  lea     rcx, [rsp+270h+var_210]
0x1800e9456  mov     esi, eax
0x1800e9458  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e945d  lea     rcx, [rsp+270h+Pid]
0x1800e9462  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800e9467  xor     r15d, r15d
0x1800e946a  jmp     loc_1800E92E3
0x1800e946f  cmp     rbx, [rbp+170h+var_1E0]
0x1800e9473  jz      short loc_1800E9490
0x1800e9475  movsd   xmm0, [rsp+270h+var_200]
0x1800e947b  movsd   qword ptr [rbx], xmm0
0x1800e947f  mov     [rbx+8], r15d
0x1800e9483  add     rbx, 0Ch
0x1800e9487  mov     [rbp+170h+var_1E8], rbx
0x1800e948b  xor     r15d, r15d
0x1800e948e  jmp     short loc_1800E94ED
0x1800e9490  lea     rbx, [rsp+270h+var_200]
0x1800e9495  lea     rcx, [rbp+170h+var_1F0]
0x1800e9499  sub     rbx, r12
0x1800e949c  call    ?_Grow@?$vector@UUdmObjectId@@V?$allocator@UUdmObjectId@@@utl@@@utl@@AEAA_NXZ; utl::vector<UdmObjectId,utl::allocator<UdmObjectId>>::_Grow(void)
0x1800e94a1  mov     r12, [rbp+170h+var_1F0]
0x1800e94a5  xor     r15d, r15d
  ... truncated ...
```
