# CMinShareFlow::InvokeFlowFromApplication(__int64)

- ea: `0x180061210`
- end: `0x180061a81`
- name: `?InvokeFlowFromApplication@CMinShareFlow@@UEAAJ_J@Z`
- size: `2161`
- prototype: `int(CMinShareFlow *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003d24`
- `0x1800160c0`
- `0x180018180`
- `0x180026ee0`
- `0x18002bc68`
- `0x180060748`
- `0x180060d8c`
- `0x180060f88`
- `0x18006109c`
- `0x1800610dc`
- `0x180061210`
- `0x180061b8c`
- `0x180061c64`
- `0x180061f50`
- `0x18006221c`
- `0x180078a24`
- `0x180079a9c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061301`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061314`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006192c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006193b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006192c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006193b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800613fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800613fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061a2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061a2f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800613dc`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800613dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CMinShareFlow::InvokeFlowFromApplication(CMinShareFlow *this, HWND a2, __int64 a3)
{
  volatile __int32 *v4; // rdi
  signed int AppIdForExtensionListItem; // ebx
  struct IDataTransferBroker *v6; // rsi
  __int64 (__fastcall *v7)(struct IDataTransferBroker *, int *, __int64 *); // rbx
  unsigned __int64 v8; // rsi
  HANDLE EventW; // rcx
  signed int LastError; // eax
  struct IDataTransferBroker *v11; // rbx
  __int64 (__fastcall *v12)(struct IDataTransferBroker *, HANDLE); // rsi
  HANDLE *v13; // rax
  HANDLE v14; // rdi
  char *v15; // r12
  unsigned __int64 v16; // r15
  char *v17; // r13
  unsigned __int64 v18; // r14
  struct IDataTransferBroker *v19; // rsi
  __int64 (__fastcall *v20)(struct IDataTransferBroker *, _QWORD, __int64 *, unsigned __int16 **); // rbx
  unsigned int v21; // eax
  struct IDataTransferBroker *v22; // rsi
  __int64 (__fastcall *v23)(struct IDataTransferBroker *, _QWORD, unsigned __int16 **); // rbx
  unsigned __int16 **v24; // rcx
  unsigned __int16 *v25; // rax
  unsigned int i; // eax
  struct IDataTransferBroker *v27; // rsi
  __int64 (__fastcall *v28)(struct IDataTransferBroker *, _QWORD, unsigned __int16 **); // rbx
  unsigned __int16 **v29; // rcx
  unsigned __int16 *v30; // rax
  const unsigned __int16 *v31; // rdx
  const unsigned __int16 *v32; // rcx
  const struct _GUID *v33; // r8
  HANDLE v34; // rbx
  __int64 (__fastcall *v35)(HANDLE, GUID *, HANDLE *); // rsi
  int v36; // eax
  unsigned int j; // r14d
  HANDLE v38; // rsi
  __int64 (__fastcall *v39)(HANDLE, _QWORD, GUID *, struct IExtensionListItem **); // rbx
  int v40; // eax
  struct IExtensionListItem *v41; // rsi
  __int64 (__fastcall *v42)(struct IExtensionListItem *, int *); // rbx
  int v43; // eax
  int v44; // ecx
  int v45; // ecx
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v47; // rax
  struct IDataTransferBroker *v49; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v50; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h]
  __int64 v52; // [rsp+58h] [rbp-A8h]
  int v53; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v54; // [rsp+68h] [rbp-98h] BYREF
  int v55[2]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE pHandles; // [rsp+78h] [rbp-88h] BYREF
  struct IExtensionListItem *v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+88h] [rbp-78h] BYREF
  int v59; // [rsp+8Ch] [rbp-74h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  HSTRING v61; // [rsp+98h] [rbp-68h] BYREF
  int v62[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-58h]
  __int64 v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h]
  int v66[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v67; // [rsp+C8h] [rbp-38h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  __int64 v70; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v71; // [rsp+E8h] [rbp-18h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  int *v73; // [rsp+F8h] [rbp-8h]
  __int128 v74; // [rsp+100h] [rbp+0h] BYREF
  __int64 v75; // [rsp+110h] [rbp+10h]
  _BYTE v76[128]; // [rsp+120h] [rbp+20h] BYREF
  __int64 dwindex; // [rsp+1C0h] [rbp+C0h] BYREF
  int v78; // [rsp+1C8h] [rbp+C8h] BYREF

  if ( _InterlockedCompareExchange(&`CMinShareFlow::InvokeFlowFromApplication'::`2'::s_fFlowInProgress, 1, 0) )
  {
    AppIdForExtensionListItem = -2147417846;
    ReportShareErrorViaHost(this, a2, 2147549450LL, this);
  }
  else
  {
    v4 = &`CMinShareFlow::InvokeFlowFromApplication'::`2'::s_fFlowInProgress;
    v73 = &`CMinShareFlow::InvokeFlowFromApplication'::`2'::s_fFlowInProgress;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), a2, a3, this, a2);
    }
    v49 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    AppIdForExtensionListItem = CDataTransferBroker_CreateInstance(a2, &v49);
    if ( AppIdForExtensionListItem >= 0 )
    {
      v58 = 0;
      v70 = 0;
      v71 = 0;
      v72 = 0;
      v6 = v49;
      v7 = *(__int64 (__fastcall **)(struct IDataTransferBroker *, int *, __int64 *))(*(_QWORD *)v49 + 24LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v70);
      v71 = -1;
      v72 = -1;
      AppIdForExtensionListItem = v7(v6, &v58, &v70);
      v8 = 0;
      if ( AppIdForExtensionListItem >= 0 )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        pHandles = EventW;
        if ( EventW )
        {
          v11 = v49;
          v12 = *(__int64 (__fastcall **)(struct IDataTransferBroker *, HANDLE))(*(_QWORD *)v49 + 176LL);
          v54 = EventW;
          v13 = (HANDLE *)___Make_U__DelegateInvokeHelper_UIDataTransferBrokerFetchHandler__V_lambda_ce7d1f1cdee4473bd8c5365a5ceed098____0_0__V___DelegateArgTraits_P8IDataTransferBrokerFetchHandler__EAAJX_E_Details_WRL_Microsoft__V_lambda_ce7d1f1cdee4473bd8c5365a5ceed098____Details_WRL_Microsoft__YA_AV__ComPtr_U__DelegateInvokeHelper_UIDataTransferBrokerFetchHandler__V_lambda_ce7d1f1cdee4473bd8c5365a5ceed098____0_0__V___DelegateArgTraits_P8IDataTransferBrokerFetchHandler__EAAJX_E_Details_WRL_Microsoft___12___QEAV_lambda_ce7d1f1cdee4473bd8c5365a5ceed098____Z(
                            &dwindex,
                            &v54);
          v14 = *v13;
          v54 = *v13;
          *v13 = 0;
          if ( dwindex )
          {
            dwindex = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
          }
          AppIdForExtensionListItem = v12(v11, v14);
          v8 = 0;
          if ( v14 )
            (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v14 + 16LL))(v14);
          _InterlockedExchange(&`CMinShareFlow::InvokeFlowFromApplication'::`2'::s_fFlowInProgress, 0);
          v4 = 0;
          v73 = 0;
          if ( AppIdForExtensionListItem >= 0 )
          {
            LODWORD(dwindex) = 0;
            CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, (LPDWORD)&dwindex);
            AppIdForExtensionListItem = (*(__int64 (__fastcall **)(struct IDataTransferBroker *))(*(_QWORD *)v49 + 184LL))(v49);
          }
          CloseHandle(pHandles);
        }
        else
        {
          LastError = GetLastError();
          AppIdForExtensionListItem = LastError;
          if ( LastError > 0 )
            AppIdForExtensionListItem = (unsigned __int16)LastError | 0x80070000;
        }
      }
      v59 = 0;
      v74 = 0;
      v75 = 0;
      v78 = 0;
      v53 = 0;
      v15 = 0;
      *(_QWORD *)v62 = 0;
      v16 = 0;
      v63 = 0;
      v64 = 0;
      v65 = 0;
      v17 = 0;
      *(_QWORD *)v66 = 0;
      v18 = 0;
      v67 = 0;
      v68 = 0;
      v69 = 0;
      if ( AppIdForExtensionListItem >= 0 )
      {
        AppIdForExtensionListItem = (*(__int64 (__fastcall **)(struct IDataTransferBroker *, int *))(*(_QWORD *)v49 + 40LL))(
                                      v49,
                                      &v59);
        if ( AppIdForExtensionListItem < 0 )
          goto LABEL_38;
        AppIdForExtensionListItem = (*(__int64 (__fastcall **)(struct IDataTransferBroker *, _QWORD, __int128 *))(*(_QWORD *)v49 + 48LL))(
                                      v49,
                                      0,
                                      &v74);
        if ( AppIdForExtensionListItem < 0 )
          goto LABEL_38;
        LODWORD(dwindex) = 0;
        v50 = 0;
        v51 = 0;
        v52 = 0;
        v19 = v49;
        v20 = *(__int64 (__fastcall **)(struct IDataTransferBroker *, _QWORD, __int64 *, unsigned __int16 **))(*(_QWORD *)v49 + 64LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
        v51 = -1;
        v52 = -1;
        AppIdForExtensionListItem = v20(v19, 0, &dwindex, &v50);
        v8 = 0;
        if ( AppIdForExtensionListItem >= 0 )
          AppIdForExtensionListItem = dwindex;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
        if ( AppIdForExtensionListItem < 0
          || (AppIdForExtensionListItem = (*(__int64 (__fastcall **)(struct IDataTransferBroker *, int *))(*(_QWORD *)v49 + 72LL))(
                                            v49,
                                            &v78),
              AppIdForExtensionListItem < 0)
          || (AppIdForExtensionListItem = (*(__int64 (__fastcall **)(struct IDataTransferBroker *, int *))(*(_QWORD *)v49 + 88LL))(
                                            v49,
                                            &v53),
              AppIdForExtensionListItem < 0) )
        {
LABEL_38:
          v21 = 0;
          goto LABEL_35;
        }
        if ( v53 + v78 )
        {
          AppIdForExtensionListItem = 0;
          v21 = 0;
          LODWORD(dwindex) = 0;
          do
          {
            if ( v21 >= v78 )
              break;
            v50 = 0;
            v51 = 0;
            v52 = 0;
            v22 = v49;
            v23 = *(__int64 (__fastcall **)(struct IDataTransferBroker *, _QWORD, unsigned __int16 **))(*(_QWORD *)v49 + 80LL);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
            v51 = -1;
            v52 = -1;
            AppIdForExtensionListItem = v23(v22, (unsigned int)dwindex, &v50);
            v8 = 0;
            if ( AppIdForExtensionListItem >= 0 )
            {
              AppIdForExtensionListItem = 0;
              if ( v16 != v65
                || (AppIdForExtensionListItem = CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::_EnsureCapacity(
                                                  v62,
                                                  v16 + 1),
                    v16 = v63,
                    v15 = *(char **)v62,
                    AppIdForExtensionListItem >= 0) )
              {
                v63 = ++v16;
                v24 = (unsigned __int16 **)&v15[24 * v16 - 24];
                if ( v24 )
                {
                  v24[1] = (unsigned __int16 *)v51;
                  v24[2] = (unsigned __int16 *)v52;
                  v25 = v50;
                  v50 = 0;
                  v52 = 0;
                  v51 = 0;
                  *v24 = v25;
                }
              }
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
            v21 = dwindex + 1;
LABEL_35:
            LODWORD(dwindex) = v21;
          }
          while ( AppIdForExtensionListItem >= 0 );
          for ( i = 0; ; i = dwindex + 1 )
          {
            LODWORD(dwindex) = i;
            if ( AppIdForExtensionListItem < 0 || i >= v53 )
              break;
            v50 = 0;
            v51 = 0;
            v52 = 0;
            v27 = v49;
            v28 = *(__int64 (__fastcall **)(struct IDataTransferBroker *, _QWORD, unsigned __int16 **))(*(_QWORD *)v49 + 96LL);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
            v51 = -1;
            v52 = -1;
            AppIdForExtensionListItem = v28(v27, (unsigned int)dwindex, &v50);
            v8 = 0;
            if ( AppIdForExtensionListItem >= 0 )
            {
              AppIdForExtensionListItem = 0;
              if ( v18 != v69
                || (AppIdForExtensionListItem = CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::_EnsureCapacity(
                                                  v66,
                                                  v18 + 1),
                    v18 = v67,
                    v17 = *(char **)v66,
                    AppIdForExtensionListItem >= 0) )
              {
                v67 = ++v18;
                v29 = (unsigned __int16 **)&v17[24 * v18 - 24];
                if ( v29 )
                {
                  v29[1] = (unsigned __int16 *)v51;
                  v29[2] = (unsigned __int16 *)v52;
                  v30 = v50;
                  v50 = 0;
                  v52 = 0;
                  v51 = 0;
                  *v29 = v30;
                }
              }
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
          }
        }
        else
        {
          AppIdForExtensionListItem = -2147418113;
        }
      }
      *(_QWORD *)v55 = 0;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v61 = 0;
      string = 0;
      if ( AppIdForExtensionListItem >= 0 )
      {
        LODWORD(dwindex) = 0;
        pHandles = 0;
        v54 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pHandles);
        if ( (int)CExtensionList::CreateInstance(v32, v31, v33, &pHandles) >= 0 )
        {
          v34 = pHandles;
          v35 = **(__int64 (__fastcall ***)(HANDLE, GUID *, HANDLE *))pHandles;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
          v36 = v35(v34, &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9, &v54);
          v8 = 0;
          if ( v36 >= 0 )
            (*(void (__fastcall **)(HANDLE, __int64 *))(*(_QWORD *)v54 + 24LL))(v54, &dwindex);
        }
        v57 = 0;
        for ( j = 0; ; ++j )
        {
          if ( j >= (unsigned int)dwindex )
          {
            AppIdForExtensionListItem = -2144927161;
            goto LABEL_62;
          }
          v38 = v54;
          v39 = *(__int64 (__fastcall **)(HANDLE, _QWORD, GUID *, struct IExtensionListItem **))(*(_QWORD *)v54 + 32LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
          v40 = v39(v38, j, &GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4, &v57);
          v8 = 0;
          if ( v40 >= 0 )
          {
            v41 = v57;
            v42 = *(__int64 (__fastcall **)(struct IExtensionListItem *, int *))(*(_QWORD *)v57 + 24LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v55);
            v43 = v42(v41, v55);
            v8 = 0;
            if ( v43 >= 0
              && ((unsigned __int8)CMinShareFlow::_MatchExtension(v44, v78, (int)v62, v55[0], L"SupportedDataFormats")
               || (unsigned __int8)CMinShareFlow::_MatchExtension(v45, v53, (int)v66, v55[0], L"SupportedFileTypes")) )
            {
              break;
            }
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
        v51 = -1;
        v52 = -1;
        AppIdForExtensionListItem = GetAppIdForExtensionListItem(v57, &v50);
        if ( AppIdForExtensionListItem >= 0 )
        {
          AppIdForExtensionListItem = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)v55 + 64LL))(
                                        *(_QWORD *)v55,
                                        &v61);
          if ( AppIdForExtensionListItem >= 0 )
            AppIdForExtensionListItem = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)v55 + 48LL))(
                                          *(_QWORD *)v55,
                                          &string);
        }
LABEL_62:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pHandles);
        if ( AppIdForExtensionListItem >= 0 )
        {
          memset_0(v76, 0, 0x48u);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v47 = WindowsGetStringRawBuffer(v61, 0);
          AppIdForExtensionListItem = CreateSharingActivationInfo(0, 1, v50, v47, StringRawBuffer, 0, &v74, v76);
          if ( AppIdForExtensionListItem >= 0 )
          {
            (*(void (__fastcall **)(struct IDataTransferBroker *, _BYTE *))(*(_QWORD *)v49 + 152LL))(v49, v76);
            FreeSharingActivationInfo((struct SHARING_ACTIVATION_INFO *)v76);
          }
        }
        v17 = *(char **)v66;
        v18 = v67;
        v15 = *(char **)v62;
        v16 = v63;
      }
      FreeSharableItemDescriptor((struct SHARABLE_ITEM_DESCRIPTOR *)&v74);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&v61);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v55);
      if ( v17 )
      {
        if ( v18 )
        {
          do
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v17[24 * v8++]);
          while ( v8 < v18 );
        }
        CoTaskMemFree(v17);
        v8 = 0;
      }
      if ( v15 )
      {
        if ( v16 )
        {
          do
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v15[24 * v8++]);
          while ( v8 < v16 );
        }
        CoTaskMemFree(v15);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v70);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    if ( v4 )
      _InterlockedExchange(v4, 0);
  }
  return (unsigned int)AppIdForExtensionListItem;
}

```

## disassembly

```asm
0x180061210  mov     [rsp-8+arg_0], rbx
0x180061215  push    rbp
0x180061216  push    rsi
0x180061217  push    rdi
0x180061218  push    r12
0x18006121a  push    r13
0x18006121c  push    r14
0x18006121e  push    r15
0x180061220  lea     rbp, [rsp-70h]
0x180061225  sub     rsp, 170h
0x18006122c  mov     rbx, rdx
0x18006122f  mov     r9, rcx
0x180061232  xor     eax, eax
0x180061234  lea     r14d, [rax+1]
0x180061238  lock cmpxchg cs:?s_fFlowInProgress@?1??InvokeFlowFromApplication@CMinShareFlow@@UEAAJ_J@Z@4JA, r14d; long `CMinShareFlow::InvokeFlowFromApplication(__int64)'::`2'::s_fFlowInProgress
0x180061241  jnz     loc_180061A57
0x180061247  lea     rdi, ?s_fFlowInProgress@?1??InvokeFlowFromApplication@CMinShareFlow@@UEAAJ_J@Z@4JA; long `CMinShareFlow::InvokeFlowFromApplication(__int64)'::`2'::s_fFlowInProgress
0x18006124e  mov     [rbp+0A0h+var_A8], rdi
0x180061252  lea     rax, WPP_GLOBAL_Control
0x180061259  mov     rcx, cs:WPP_GLOBAL_Control
0x180061260  cmp     rcx, rax
0x180061263  jz      short loc_18006127F
0x180061265  test    [rcx+44h], r14b
0x180061269  jz      short loc_18006127F
0x18006126b  cmp     byte ptr [rcx+41h], 4
0x18006126f  jb      short loc_18006127F
0x180061271  mov     [rsp+1A0h+lpdwindex], rdx
0x180061276  mov     rcx, [rcx+38h]
0x18006127a  call    WPP_SF_qq
0x18006127f  xor     esi, esi
0x180061281  mov     [rsp+1A0h+var_160], rsi
0x180061286  lea     rcx, [rsp+1A0h+var_160]
0x18006128b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061290  lea     rdx, [rsp+1A0h+var_160]; struct IDataTransferBroker **
0x180061295  mov     rcx, rbx; HWND
0x180061298  call    ?CDataTransferBroker_CreateInstance@@YAJPEAUHWND__@@PEAPEAUIDataTransferBroker@@@Z; CDataTransferBroker_CreateInstance(HWND__ *,IDataTransferBroker * *)
0x18006129d  mov     ebx, eax
0x18006129f  test    eax, eax
0x1800612a1  js      loc_180061A41
0x1800612a7  mov     [rbp+0A0h+var_118], esi
0x1800612aa  mov     [rbp+0A0h+var_C0], rsi
0x1800612ae  mov     [rbp+0A0h+var_B8], rsi
0x1800612b2  mov     [rbp+0A0h+var_B0], rsi
0x1800612b6  mov     rsi, [rsp+1A0h+var_160]
0x1800612bb  mov     rax, [rsi]
0x1800612be  mov     rbx, [rax+18h]
0x1800612c2  lea     rcx, [rbp+0A0h+var_C0]
0x1800612c6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800612cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800612cf  mov     [rbp+0A0h+var_B8], rax
0x1800612d3  mov     [rbp+0A0h+var_B0], rax
0x1800612d7  lea     r8, [rbp+0A0h+var_C0]
0x1800612db  lea     rdx, [rbp+0A0h+var_118]
0x1800612df  mov     rcx, rsi
0x1800612e2  mov     rax, rbx
0x1800612e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800612ea  mov     ebx, eax
0x1800612ec  xor     esi, esi
0x1800612ee  test    eax, eax
0x1800612f0  js      loc_180061403
0x1800612f6  xor     r9d, r9d; lpName
0x1800612f9  xor     r8d, r8d; bInitialState
0x1800612fc  mov     edx, r14d; bManualReset
0x1800612ff  xor     ecx, ecx; lpEventAttributes
0x180061301  call    cs:__imp_CreateEventW
0x180061307  mov     rcx, rax
0x18006130a  mov     [rsp+1A0h+pHandles], rax
0x18006130f  test    rax, rax
0x180061312  jnz     short loc_180061332
0x180061314  call    cs:__imp_GetLastError
0x18006131a  mov     ebx, eax
0x18006131c  test    eax, eax
0x18006131e  jle     loc_180061403
0x180061324  movzx   ebx, ax
0x180061327  or      ebx, 80070000h
0x18006132d  jmp     loc_180061403
0x180061332  mov     rbx, [rsp+1A0h+var_160]
0x180061337  mov     rax, [rbx]
0x18006133a  mov     rsi, [rax+0B0h]
0x180061341  mov     [rsp+1A0h+var_138], rcx
0x180061346  lea     rdx, [rsp+1A0h+var_138]
0x18006134b  lea     rcx, [rbp+0A0h+dwindex]
0x180061352  call    ??$Make@U?$DelegateInvokeHelper@UIDataTransferBrokerFetchHandler@@V_lambda_ce7d1f1cdee4473bd8c5365a5ceed098_@@$0?0$$V@?$DelegateArgTraits@P8IDataTransferBrokerFetchHandler@@EAAJX_E@Details@WRL@Microsoft@@V_lambda_ce7d1f1cdee4473bd8c5365a5ceed098_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@UIDataTransferBrokerFetchHandler@@V_lambda_ce7d1f1cdee4473bd8c5365a5ceed098_@@$0?0$$V@?$DelegateArgTraits@P8IDataTransferBrokerFetchHandler@@EAAJX_E@Details@WRL@Microsoft@@@12@$$QEAV_lambda_ce7d1f1cdee4473bd8c5365a5ceed098_@@@Z
0x180061357  mov     rdi, [rax]
0x18006135a  mov     [rsp+1A0h+var_138], rdi
0x18006135f  mov     qword ptr [rax], 0
0x180061366  mov     rcx, [rbp+0A0h+dwindex]
0x18006136d  test    rcx, rcx
0x180061370  jz      short loc_180061383
0x180061372  mov     [rbp+0A0h+dwindex], 0
0x18006137d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180061382  nop
0x180061383  mov     rdx, rdi
0x180061386  mov     rcx, rbx
0x180061389  mov     rax, rsi
0x18006138c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061391  mov     ebx, eax
0x180061393  xor     esi, esi
0x180061395  test    rdi, rdi
0x180061398  jz      short loc_1800613AA
0x18006139a  mov     rax, [rdi]
0x18006139d  mov     rcx, rdi
0x1800613a0  mov     rax, [rax+10h]
0x1800613a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800613a9  nop
0x1800613aa  mov     eax, esi
0x1800613ac  xchg    eax, cs:?s_fFlowInProgress@?1??InvokeFlowFromApplication@CMinShareFlow@@UEAAJ_J@Z@4JA; long `CMinShareFlow::InvokeFlowFromApplication(__int64)'::`2'::s_fFlowInProgress
0x1800613b2  mov     rdi, rsi
0x1800613b5  mov     [rbp+0A0h+var_A8], rsi
0x1800613b9  test    ebx, ebx
0x1800613bb  js      short loc_1800613F8
0x1800613bd  mov     dword ptr [rbp+0A0h+dwindex], esi
0x1800613c3  lea     rax, [rbp+0A0h+dwindex]
0x1800613ca  mov     [rsp+1A0h+lpdwindex], rax; lpdwindex
0x1800613cf  lea     r9, [rsp+1A0h+pHandles]; pHandles
0x1800613d4  mov     r8d, r14d; cHandles
0x1800613d7  or      edx, 0FFFFFFFFh; dwTimeout
0x1800613da  xor     ecx, ecx; dwFlags
0x1800613dc  call    cs:__imp_CoWaitForMultipleHandles
0x1800613e2  mov     rcx, [rsp+1A0h+var_160]
0x1800613e7  mov     rax, [rcx]
0x1800613ea  mov     rax, [rax+0B8h]
0x1800613f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800613f6  mov     ebx, eax
0x1800613f8  mov     rcx, [rsp+1A0h+pHandles]; hObject
0x1800613fd  call    cs:__imp_CloseHandle
0x180061403  mov     [rbp+0A0h+var_114], esi
0x180061406  xorps   xmm0, xmm0
0x180061409  xor     eax, eax
0x18006140b  movups  [rbp+0A0h+var_A0], xmm0
0x18006140f  mov     [rbp+0A0h+var_90], rax
0x180061413  mov     [rbp+0A0h+arg_18], esi
0x180061419  mov     [rsp+1A0h+var_140], esi
0x18006141d  mov     r12, rsi
0x180061420  mov     qword ptr [rbp+0A0h+var_100], rsi
0x180061424  mov     r15, rsi
0x180061427  mov     [rbp+0A0h+var_F8], rsi
0x18006142b  mov     [rbp+0A0h+var_F0], rsi
0x18006142f  mov     [rbp+0A0h+var_E8], rsi
0x180061433  mov     r13, rsi
0x180061436  mov     qword ptr [rbp+0A0h+var_E0], rsi
0x18006143a  mov     r14, rsi
0x18006143d  mov     [rbp+0A0h+var_D8], rsi
0x180061441  mov     [rbp+0A0h+var_D0], rsi
0x180061445  mov     [rbp+0A0h+var_C8], rsi
0x180061449  test    ebx, ebx
0x18006144b  js      loc_180061733
0x180061451  mov     rcx, [rsp+1A0h+var_160]
0x180061456  mov     rax, [rcx]
0x180061459  lea     rdx, [rbp+0A0h+var_114]
0x18006145d  mov     rax, [rax+28h]
0x180061461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061466  mov     ebx, eax
0x180061468  test    eax, eax
0x18006146a  js      loc_180061650
0x180061470  mov     rcx, [rsp+1A0h+var_160]
0x180061475  mov     rax, [rcx]
0x180061478  lea     r8, [rbp+0A0h+var_A0]
0x18006147c  xor     edx, edx
0x18006147e  mov     rax, [rax+30h]
0x180061482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061487  mov     ebx, eax
0x180061489  test    eax, eax
0x18006148b  js      loc_180061650
0x180061491  mov     dword ptr [rbp+0A0h+dwindex], esi
0x180061497  mov     [rsp+1A0h+var_158], rsi
0x18006149c  mov     [rsp+1A0h+var_150], rsi
0x1800614a1  mov     [rsp+1A0h+var_148], rsi
0x1800614a6  mov     rsi, [rsp+1A0h+var_160]
0x1800614ab  mov     rax, [rsi]
0x1800614ae  mov     rbx, [rax+40h]
0x1800614b2  lea     rcx, [rsp+1A0h+var_158]
0x1800614b7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800614bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800614c0  mov     [rsp+1A0h+var_150], rax
0x1800614c5  mov     [rsp+1A0h+var_148], rax
0x1800614ca  lea     r9, [rsp+1A0h+var_158]
0x1800614cf  lea     r8, [rbp+0A0h+dwindex]
0x1800614d6  xor     edx, edx
0x1800614d8  mov     rcx, rsi
0x1800614db  mov     rax, rbx
0x1800614de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800614e3  mov     ebx, eax
0x1800614e5  xor     esi, esi
0x1800614e7  test    eax, eax
0x1800614e9  cmovns  ebx, dword ptr [rbp+0A0h+dwindex]
0x1800614f0  lea     rcx, [rsp+1A0h+var_158]
0x1800614f5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800614fa  test    ebx, ebx
0x1800614fc  js      loc_180061650
0x180061502  mov     rcx, [rsp+1A0h+var_160]
0x180061507  mov     rax, [rcx]
0x18006150a  lea     rdx, [rbp+0A0h+arg_18]
0x180061511  mov     rax, [rax+48h]
0x180061515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006151a  mov     ebx, eax
0x18006151c  test    eax, eax
0x18006151e  js      loc_180061650
0x180061524  mov     rcx, [rsp+1A0h+var_160]
0x180061529  mov     rax, [rcx]
0x18006152c  lea     rdx, [rsp+1A0h+var_140]
0x180061531  mov     rax, [rax+58h]
0x180061535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006153a  mov     ebx, eax
0x18006153c  test    eax, eax
0x18006153e  js      loc_180061650
0x180061544  mov     ecx, [rbp+0A0h+arg_18]
0x18006154a  add     ecx, [rsp+1A0h+var_140]
0x18006154e  jz      loc_180061646
0x180061554  mov     ebx, esi
0x180061556  mov     eax, esi
0x180061558  mov     dword ptr [rbp+0A0h+dwindex], eax
0x18006155e  cmp     eax, [rbp+0A0h+arg_18]
0x180061564  jnb     loc_18006163F
0x18006156a  mov     [rsp+1A0h+var_158], rsi
0x18006156f  mov     [rsp+1A0h+var_150], rsi
0x180061574  mov     [rsp+1A0h+var_148], rsi
0x180061579  mov     rsi, [rsp+1A0h+var_160]
0x18006157e  mov     rax, [rsi]
0x180061581  mov     rbx, [rax+50h]
0x180061585  lea     rcx, [rsp+1A0h+var_158]
0x18006158a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006158f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180061593  mov     [rsp+1A0h+var_150], rax
0x180061598  mov     [rsp+1A0h+var_148], rax
0x18006159d  lea     r8, [rsp+1A0h+var_158]
0x1800615a2  mov     edx, dword ptr [rbp+0A0h+dwindex]
0x1800615a8  mov     rcx, rsi
0x1800615ab  mov     rax, rbx
0x1800615ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615b3  mov     ebx, eax
0x1800615b5  xor     esi, esi
0x1800615b7  test    eax, eax
0x1800615b9  js      short loc_18006161F
0x1800615bb  mov     ebx, esi
0x1800615bd  cmp     r15, [rbp+0A0h+var_E8]
0x1800615c1  jnz     short loc_1800615DE
0x1800615c3  lea     rdx, [r15+1]
0x1800615c7  lea     rcx, [rbp+0A0h+var_100]
0x1800615cb  call    ?_EnsureCapacity@?$CTSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardMergeHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@QEAAJ_K0@Z; CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800615d0  mov     ebx, eax
0x1800615d2  mov     r15, [rbp+0A0h+var_F8]
0x1800615d6  mov     r12, qword ptr [rbp+0A0h+var_100]
0x1800615da  test    eax, eax
0x1800615dc  js      short loc_18006161F
0x1800615de  inc     r15
0x1800615e1  mov     [rbp+0A0h+var_F8], r15
0x1800615e5  lea     rcx, [r15-1]
0x1800615e9  lea     rcx, [rcx+rcx*2]
0x1800615ed  lea     rcx, [r12+rcx*8]
0x1800615f1  test    rcx, rcx
0x1800615f4  jz      short loc_18006161F
0x1800615f6  mov     rax, [rsp+1A0h+var_150]
0x1800615fb  mov     [rcx+8], rax
0x1800615ff  mov     rax, [rsp+1A0h+var_148]
0x180061604  mov     [rcx+10h], rax
0x180061608  mov     rax, [rsp+1A0h+var_158]
0x18006160d  mov     [rsp+1A0h+var_158], rsi
0x180061612  mov     [rsp+1A0h+var_148], rsi
0x180061617  mov     [rsp+1A0h+var_150], rsi
0x18006161c  mov     [rcx], rax
0x18006161f  lea     rcx, [rsp+1A0h+var_158]
0x180061624  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180061629  mov     eax, dword ptr [rbp+0A0h+dwindex]
0x18006162f  inc     eax
0x180061631  test    ebx, ebx
0x180061633  mov     dword ptr [rbp+0A0h+dwindex], eax
0x180061639  jns     loc_18006155E
0x18006163f  mov     eax, esi
0x180061641  jmp     loc_180061725
0x180061646  mov     ebx, 8000FFFFh
0x18006164b  jmp     loc_180061733
0x180061650  mov     eax, esi
0x180061652  jmp     short loc_180061631
0x180061654  cmp     eax, [rsp+1A0h+var_140]
0x180061658  jnb     loc_180061733
0x18006165e  mov     [rsp+1A0h+var_158], rsi
0x180061663  mov     [rsp+1A0h+var_150], rsi
0x180061668  mov     [rsp+1A0h+var_148], rsi
0x18006166d  mov     rsi, [rsp+1A0h+var_160]
0x180061672  mov     rax, [rsi]
0x180061675  mov     rbx, [rax+60h]
0x180061679  lea     rcx, [rsp+1A0h+var_158]
0x18006167e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180061683  or      rax, 0FFFFFFFFFFFFFFFFh
0x180061687  mov     [rsp+1A0h+var_150], rax
0x18006168c  mov     [rsp+1A0h+var_148], rax
0x180061691  lea     r8, [rsp+1A0h+var_158]
0x180061696  mov     edx, dword ptr [rbp+0A0h+dwindex]
0x18006169c  mov     rcx, rsi
0x18006169f  mov     rax, rbx
0x1800616a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800616a7  mov     ebx, eax
0x1800616a9  xor     esi, esi
0x1800616ab  test    eax, eax
0x1800616ad  js      short loc_180061713
0x1800616af  mov     ebx, esi
0x1800616b1  cmp     r14, [rbp+0A0h+var_C8]
0x1800616b5  jnz     short loc_1800616D2
0x1800616b7  lea     rdx, [r14+1]
  ... truncated ...
```
