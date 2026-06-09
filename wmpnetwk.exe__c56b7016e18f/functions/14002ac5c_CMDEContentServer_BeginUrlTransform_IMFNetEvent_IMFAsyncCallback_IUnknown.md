# CMDEContentServer::BeginUrlTransform(IMFNetEvent *,IMFAsyncCallback *,IUnknown *)

- ea: `0x14002ac5c`
- end: `0x14002b894`
- name: `?BeginUrlTransform@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `3128`
- prototype: `int(CMDEContentServer *__hidden this, struct IMFNetEvent *, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14008f4ac`

## callees

- `0x1400065e0`
- `0x140006d70`
- `0x14000b3b0`
- `0x14000c920`
- `0x140024688`
- `0x14002ac5c`
- `0x14002b89c`
- `0x14002ba58`
- `0x140039218`
- `0x14003b610`
- `0x14003f17c`
- `0x14004a834`
- `0x140054490`
- `0x14005480c`
- `0x140057bc4`
- `0x140062f88`
- `0x140090118`
- `0x140090174`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14002aca3`
- `KERNEL32!EnterCriticalSection` at `0x14002aca3`
- `KERNEL32!LeaveCriticalSection` at `0x14002b831`
- `KERNEL32!LeaveCriticalSection` at `0x14002b831`
- `KERNEL32!CompareStringW` at `0x14002b1a7`
- `KERNEL32!CompareStringW` at `0x14002b201`
- `KERNEL32!CompareStringW` at `0x14002b1a7`
- `KERNEL32!CompareStringW` at `0x14002b201`
- `ole32!PropVariantClear` at `0x14002b70d`
- `ole32!PropVariantClear` at `0x14002b70d`
- `MFPlat!CreatePropertyStore` at `0x14002b406`
- `MFPlat!CreatePropertyStore` at `0x14002b406`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x14002b588`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x14002b588`
- `MFPlat!MFCreateAsyncResult` at `0x14002addb`
- `MFPlat!MFCreateAsyncResult` at `0x14002addb`
- `MFPlat!MFInvokeCallback` at `0x14002b6bc`
- `MFPlat!MFInvokeCallback` at `0x14002b6bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CMDEContentServer::BeginUrlTransform(
        CMDEContentServer *this,
        IUnknown *a2,
        struct IMFAsyncCallback *a3,
        struct IUnknown *a4)
{
  IUnknown *v4; // rbx
  IMFAsyncCallback *v5; // rdi
  unsigned __int64 v8; // r13
  unsigned int v9; // r14d
  HRESULT LocalPath; // esi
  __int64 v11; // rdx
  PVOID v12; // rcx
  PVOID *v13; // rcx
  const WCHAR *v14; // rbx
  char v15; // al
  _DWORD *v16; // rdi
  char v17; // al
  char v18; // al
  _DWORD *v19; // rbx
  BOOL v20; // edi
  int v21; // eax
  const WCHAR *v22; // rax
  int v23; // eax
  int v24; // eax
  HRESULT v25; // eax
  int v26; // eax
  int v27; // eax
  HRESULT v28; // eax
  int v29; // ecx
  PCNZWCH v31; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B8h] BYREF
  WCHAR *v33; // [rsp+58h] [rbp-B0h] BYREF
  IMFByteStream *ppByteStream; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD *lpString2; // [rsp+68h] [rbp-A0h] BYREF
  PCNZWCH v36[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v37; // [rsp+80h] [rbp-88h]
  IStream *pStream; // [rsp+88h] [rbp-80h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+90h] [rbp-78h] BYREF
  __int64 v40; // [rsp+98h] [rbp-70h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-60h] BYREF
  PROPVARIANT pvar[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v44; // [rsp+C0h] [rbp-48h]
  _QWORD v45[2]; // [rsp+C8h] [rbp-40h] BYREF
  int v46; // [rsp+D8h] [rbp-30h]
  int v47; // [rsp+DCh] [rbp-2Ch]
  int v48; // [rsp+E0h] [rbp-28h]
  int v49; // [rsp+E4h] [rbp-24h]
  __int64 v50; // [rsp+E8h] [rbp-20h]
  __int64 v51; // [rsp+F0h] [rbp-18h]
  int v52; // [rsp+F8h] [rbp-10h]
  int v53; // [rsp+FCh] [rbp-Ch]
  __int64 v54; // [rsp+100h] [rbp-8h]
  __int64 v55; // [rsp+108h] [rbp+0h]
  unsigned __int64 v56; // [rsp+118h] [rbp+10h]
  __int64 v57; // [rsp+168h] [rbp+60h] BYREF
  struct IMFAsyncCallback *v58; // [rsp+178h] [rbp+70h]
  struct IUnknown *v59; // [rsp+180h] [rbp+78h]

  v59 = a4;
  v58 = a3;
  v4 = a4;
  v5 = a3;
  v8 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
  if ( v8 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  v56 = v8;
  v9 = 0;
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      (_DWORD)this,
      (unsigned int)MDE_Callback_Begin_Url_Transform_Start,
      (_DWORD)a2,
      (_DWORD)v5,
      (char)v4,
      0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, a2, v5, v4);
  }
  ppAsyncResult = 0;
  v33 = 0;
  v32 = 0;
  v57 = 0;
  v42 = 0;
  v41 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  pStream = 0;
  ppByteStream = 0;
  *(_OWORD *)pvar = 0;
  v44 = 0;
  v40 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v45[0] = 0;
  v45[1] = 0;
  v46 = 17;
  v50 = 0xFFFFFFFFLL;
  v51 = 0;
  v52 = 0;
  v53 = 10;
  v54 = 0;
  v55 = 0;
  v47 = 1061158912;
  v48 = 1048576000;
  v49 = 1074790400;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(v45);
  LocalPath = MFCreateAsyncResult(a2, v5, v4, &ppAsyncResult);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((LocalPath >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      148,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)LocalPath);
  }
  if ( LocalPath >= 0 )
  {
    LocalPath = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                  a2,
                  &IID_IMFNetUrlTransformEvent,
                  &v32);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((LocalPath >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        149,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)LocalPath,
        v32);
    }
    if ( LocalPath >= 0 )
    {
      LocalPath = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl[13].QueryInterface)(
                    a2,
                    &IID_IPropertyStore,
                    &v57);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = ((LocalPath >> 31) & 0xFFFFFFFD) + 5;
        if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v11 )
          WPP_SF_dq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            150,
            &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
            (unsigned int)LocalPath,
            v57);
      }
      if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
        McTemplateU0p_EventWriteTransfer(v12, v11, v57);
      if ( LocalPath >= 0 )
      {
        LocalPath = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v57 + 40LL))(
                      v57,
                      qword_1400BF680,
                      pvar);
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((LocalPath >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            151,
            &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
            (unsigned int)LocalPath);
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( LocalPath >= 0 )
        {
          if ( pvar[1] && LOWORD(pvar[0]) == 31 )
          {
            LocalPath = (*(__int64 (__fastcall **)(__int64, WCHAR **))(*(_QWORD *)v32 + 336LL))(v32, &v33);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((LocalPath >> 31) & 0xFFFFFFFD) + 5 )
            {
              WPP_SF_dS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                153,
                (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                LocalPath,
                (__int64)v33);
            }
            if ( LocalPath >= 0 )
            {
              v36[0] = (PCNZWCH)31;
              v37 = 0;
              v36[1] = v33;
              LocalPath = (*(__int64 (__fastcall **)(__int64, __int64 *, PCNZWCH *))(*(_QWORD *)v57 + 48LL))(
                            v57,
                            qword_1400BF668,
                            v36);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((LocalPath >> 31) & 0xFFFFFFFD) + 5 )
              {
                WPP_SF_dS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  154,
                  (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                  LocalPath,
                  (__int64)v33);
              }
              if ( LocalPath >= 0 )
              {
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
                  (void **)&v31,
                  (char *)v33);
                LocalPath = ParseUrl(&v31, &v40, v45);
                ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v31);
                if ( LocalPath >= 0 )
                {
                  LocalPath = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl[12].Release)(
                                a2,
                                &IID_IPropertyStore,
                                &v42);
                  if ( LocalPath >= 0 )
                  {
                    v14 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
                    v31 = v14;
                    lpString2 = (_DWORD *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
                    v15 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::Lookup(
                            v45,
                            L"albumArt",
                            &lpString2);
                    v16 = lpString2;
                    if ( v15 && *(lpString2 - 4) && CompareStringW(0x7Fu, 1u, L"true", -1, (PCNZWCH)lpString2, -1) == 2 )
                    {
                      v9 = 1;
                    }
                    else
                    {
                      v17 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::Lookup(
                              v45,
                              L"IFOFile",
                              &v31);
                      v14 = v31;
                      if ( v17 && *((_DWORD *)v31 - 4) && CompareStringW(0x7Fu, 1u, L"true", -1, v31, -1) == 2 )
                        v9 = 2;
                    }
                    LocalPath = CMDEContentServer::GetLocalPath(this, &v40, pvar[1], v9, 0, &v41, &pStream);
                    ATL::CStringData::Release((ATL::CStringData *)(v16 - 6));
                    ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
                    if ( LocalPath >= 0 )
                    {
                      lpString2 = (_DWORD *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
                      v18 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::Lookup(
                              v45,
                              L"formatID",
                              &lpString2);
                      v19 = lpString2;
                      if ( v18 && *(lpString2 - 4) )
                      {
                        v20 = 1;
                      }
                      else
                      {
                        v20 = 0;
                        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v31);
                        if ( (unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::Lookup(
                                                v45,
                                                L"format",
                                                &v31) )
                          v20 = *((_DWORD *)v31 - 4) != 0;
                        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v31);
                      }
                      *(_OWORD *)v36 = 0;
                      v37 = 0;
                      LOWORD(v36[0]) = 11;
                      if ( v20 )
                        LOWORD(v36[1]) = 0;
                      else
                        LOWORD(v36[1]) = -1;
                      LocalPath = (*(__int64 (__fastcall **)(__int64, __int64 *, PCNZWCH *))(*(_QWORD *)v57 + 48LL))(
                                    v57,
                                    PKEY_MFNETCONNECTION_DOWNLOADREQUEST,
                                    v36);
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((LocalPath >> 31) & 0xFFFFFFFD) + 5 )
                      {
                        WPP_SF_Dd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          155,
                          &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                          (unsigned int)LocalPath);
                      }
                      if ( pStream || ppByteStream )
                      {
                        v31 = 0;
                        if ( !v20 )
                        {
                          LocalPath = CreatePropertyStore((IPropertyStore **)&v31);
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((LocalPath >> 31) & 0xFFFFFFFD) + 5 )
                          {
                            WPP_SF_dq(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              156,
                              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                              (unsigned int)LocalPath,
                              v31);
                          }
                          if ( LocalPath >= 0 )
                          {
                            LOWORD(v36[0]) = 31;
                            v22 = L"image/jpeg";
                            if ( v9 != 1 )
                              v22 = L"application/octet-stream";
                            v36[1] = v22;
                            v23 = (*(__int64 (__fastcall **)(PCNZWCH, __int64 *, PCNZWCH *))(*(_QWORD *)v31 + 48LL))(
                                    v31,
                                    PKEY_MDEPROFILE_OUTPUTMIMETYPE,
                                    v36);
                            LocalPath = v23;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                              && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v23 >> 31) & 0xFFFFFFFD) + 5 )
                            {
                              WPP_SF_dS(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                157,
                                (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                                v23,
                                (__int64)v36[1]);
                            }
                            if ( LocalPath >= 0 )
                            {
                              LOWORD(v36[0]) = 11;
                              LOWORD(v36[1]) = -1;
                              v24 = (*(__int64 (__fastcall **)(PCNZWCH, __int64 *, PCNZWCH *))(*(_QWORD *)v31 + 48LL))(
                                      v31,
                                      PKEY_MDEPROFILE_HTTP_ENABLED,
                                      v36);
                              LocalPath = v24;
                              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v24 >> 31) & 0xFFFFFFFD) + 5 )
                              {
                                WPP_SF_d(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  158,
                                  &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                                  (unsigned int)v24);
                              }
                            }
                          }
                        }
                        if ( LocalPath >= 0 )
                        {
                          if ( ppByteStream )
                            goto LABEL_97;
                          v25 = MFCreateMFByteStreamOnStream(pStream, &ppByteStream);
                          LocalPath = v25;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v25 >> 31) & 0xFFFFFFFD) + 5 )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              159,
                              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                              (unsigned int)v25);
                          }
                          if ( LocalPath >= 0 )
                          {
LABEL_97:
                            v26 = (*(__int64 (__fastcall **)(__int64, IMFByteStream *, PCNZWCH))(*(_QWORD *)v32 + 360LL))(
                                    v32,
                                    ppByteStream,
                                    v31);
                            LocalPath = v26;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                              && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v26 >> 31) & 0xFFFFFFFD) + 5 )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                160,
                                &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                                (unsigned int)v26);
                            }
                          }
                        }
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v31);
                      }
                      else
                      {
                        v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 344LL))(v32, v41);
                        LocalPath = v21;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v21 >> 31) & 0xFFFFFFFD) + 5 )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            161,
                            &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                            (unsigned int)v21);
                        }
                      }
                      ATL::CStringData::Release((ATL::CStringData *)(v19 - 6));
                      if ( LocalPath >= 0 )
                      {
                        v27 = ((__int64 (__fastcall *)(IMFAsyncResult *, _QWORD))ppAsyncResult->lpVtbl->SetStatus)(
                                ppAsyncResult,
                                (unsigned int)LocalPath);
                        LocalPath = v27;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v27 >> 31) & 0xFFFFFFFD) + 5 )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            162,
                            &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                            (unsigned int)v27);
                        }
                        if ( LocalPath >= 0 )
                        {
                          v28 = MFInvokeCallback(ppAsyncResult);
                          LocalPath = v28;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v28 >> 31) & 0xFFFFFFFD) + 5 )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              163,
                              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                              (unsigned int)v28);
                          }
                        }
                      }
                    }
                    LOBYTE(v4) = (_BYTE)v59;
                    LODWORD(v5) = (_DWORD)v58;
                  }
                }
              }
            }
          }
          else
          {
            LocalPath = -2147467259;
            if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 2u )
              WPP_SF_d(v13[2], 152, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, 2147500037LL);
          }
        }
      }
    }
  }
  PropVariantClear(pvar);
  v29 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((LocalPath >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      164,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)LocalPath);
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      v29,
      (unsigned int)MDE_Callback_Begin_Url_Transform_Stop,
      (_DWORD)a2,
      (_DWORD)v5,
      (char)v4,
      LocalPath);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(v45);
  ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
  if ( ppByteStream )
    ((void (__fastcall *)(IMFByteStream *))ppByteStream->lpVtbl->Release)(ppByteStream);
  if ( pStream )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)pStream + 16LL))(pStream);
  ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( ppAsyncResult )
    ((void (__fastcall *)(IMFAsyncResult *))ppAsyncResult->lpVtbl->Release)(ppAsyncResult);
  if ( v8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  return (unsigned int)LocalPath;
}

```

## disassembly

```asm
0x14002ac5c  mov     rax, rsp
0x14002ac5f  mov     [rax+10h], rbx
0x14002ac63  mov     [rax+20h], r9
0x14002ac67  mov     [rax+18h], r8
0x14002ac6b  push    rbp
0x14002ac6c  push    rsi
0x14002ac6d  push    rdi
0x14002ac6e  push    r12
0x14002ac70  push    r13
0x14002ac72  push    r14
0x14002ac74  push    r15
0x14002ac76  lea     rbp, [rax-58h]
0x14002ac7a  sub     rsp, 120h
0x14002ac81  mov     rbx, r9
0x14002ac84  mov     rdi, r8
0x14002ac87  mov     r12, rdx
0x14002ac8a  mov     r15, rcx
0x14002ac8d  mov     rax, rcx
0x14002ac90  lea     r10, [rcx+8]
0x14002ac94  neg     rax
0x14002ac97  sbb     r13, r13
0x14002ac9a  and     r13, r10
0x14002ac9d  jz      short loc_14002ACA9
0x14002ac9f  lea     rcx, [r13+8]; lpCriticalSection
0x14002aca3  call    cs:__imp_EnterCriticalSection
0x14002aca9  mov     [rbp+50h+var_40], r13
0x14002acad  xor     r14d, r14d
0x14002acb0  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14002acb7  jz      short loc_14002ACD5
0x14002acb9  mov     [rsp+150h+cchCount2], r14d
0x14002acbe  mov     [rsp+150h+lpString2], rbx
0x14002acc3  mov     r9, rdi
0x14002acc6  mov     r8, r12
0x14002acc9  lea     rdx, MDE_Callback_Begin_Url_Transform_Start
0x14002acd0  call    McTemplateU0pppq_EventWriteTransfer
0x14002acd5  lea     rax, WPP_GLOBAL_Control
0x14002acdc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ace3  cmp     rcx, rax
0x14002ace6  jz      short loc_14002AD16
0x14002ace8  test    byte ptr [rcx+1Ch], 1
0x14002acec  jz      short loc_14002AD16
0x14002acee  cmp     byte ptr [rcx+19h], 5
0x14002acf2  jb      short loc_14002AD16
0x14002acf4  mov     edx, 93h
0x14002acf9  mov     qword ptr [rsp+150h+cchCount2], rbx
0x14002acfe  mov     [rsp+150h+lpString2], rdi
0x14002ad03  mov     r9, r12
0x14002ad06  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002ad0d  mov     rcx, [rcx+10h]
0x14002ad11  call    WPP_SF_qqq
0x14002ad16  mov     [rbp+50h+ppAsyncResult], r14
0x14002ad1a  mov     [rsp+150h+var_100], r14
0x14002ad1f  mov     [rsp+150h+var_108], r14
0x14002ad24  mov     [rbp+50h+arg_0], r14
0x14002ad28  mov     [rbp+50h+var_B0], r14
0x14002ad2c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002ad33  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002ad3a  mov     rax, [rax+18h]
0x14002ad3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ad43  add     rax, 18h
0x14002ad47  mov     [rbp+50h+var_B8], rax
0x14002ad4b  mov     [rbp+50h+pStream], r14
0x14002ad4f  mov     [rsp+150h+ppByteStream], r14
0x14002ad54  xorps   xmm0, xmm0
0x14002ad57  xor     eax, eax
0x14002ad59  movups  xmmword ptr [rbp+50h+pvar], xmm0
0x14002ad5d  mov     [rbp+50h+var_98], rax
0x14002ad61  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002ad68  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002ad6f  mov     rax, [rax+18h]
0x14002ad73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ad78  add     rax, 18h
0x14002ad7c  mov     [rbp+50h+var_C0], rax
0x14002ad80  mov     [rbp+50h+var_90], r14
0x14002ad84  mov     [rbp+50h+var_88], r14
0x14002ad88  mov     [rbp+50h+var_80], 11h
0x14002ad8f  mov     eax, 0FFFFFFFFh
0x14002ad94  mov     [rbp+50h+var_70], rax
0x14002ad98  mov     [rbp+50h+var_68], r14
0x14002ad9c  mov     [rbp+50h+var_60], r14d
0x14002ada0  mov     [rbp+50h+var_5C], 0Ah
0x14002ada7  mov     [rbp+50h+var_58], r14
0x14002adab  mov     [rbp+50h+var_50], r14
0x14002adaf  mov     [rbp+50h+var_7C], 3F400000h
0x14002adb6  mov     [rbp+50h+var_78], 3E800000h
0x14002adbd  mov     [rbp+50h+var_74], 40100000h
0x14002adc4  lea     rcx, [rbp+50h+var_90]
0x14002adc8  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CComPtr@UIWMCContentProvider@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CComPtr@UIWMCContentProvider@@@ATL@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(void)
0x14002adcd  nop
0x14002adce  lea     r9, [rbp+50h+ppAsyncResult]; ppAsyncResult
0x14002add2  mov     r8, rbx; punkState
0x14002add5  mov     rdx, rdi; pCallback
0x14002add8  mov     rcx, r12; punkObject
0x14002addb  call    cs:__imp_MFCreateAsyncResult
0x14002ade1  mov     esi, eax
0x14002ade3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002adea  lea     rax, WPP_GLOBAL_Control
0x14002adf1  cmp     rcx, rax
0x14002adf4  jz      short loc_14002AE27
0x14002adf6  test    byte ptr [rcx+1Ch], 2
0x14002adfa  jz      short loc_14002AE27
0x14002adfc  mov     edx, esi
0x14002adfe  sar     edx, 1Fh
0x14002ae01  and     edx, 0FFFFFFFDh
0x14002ae04  add     edx, 5
0x14002ae07  movzx   eax, byte ptr [rcx+19h]
0x14002ae0b  cmp     eax, edx
0x14002ae0d  jb      short loc_14002AE27
0x14002ae0f  mov     edx, 94h
0x14002ae14  mov     r9d, esi
0x14002ae17  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002ae1e  mov     rcx, [rcx+10h]
0x14002ae22  call    WPP_SF_d
0x14002ae27  test    esi, esi
0x14002ae29  js      loc_14002B709
0x14002ae2f  mov     rax, [r12]
0x14002ae33  lea     r8, [rsp+150h+var_108]
0x14002ae38  lea     rdx, IID_IMFNetUrlTransformEvent
0x14002ae3f  mov     rcx, r12
0x14002ae42  mov     rax, [rax]
0x14002ae45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae4a  mov     esi, eax
0x14002ae4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ae53  lea     rax, WPP_GLOBAL_Control
0x14002ae5a  cmp     rcx, rax
0x14002ae5d  jz      short loc_14002AE9A
0x14002ae5f  test    byte ptr [rcx+1Ch], 2
0x14002ae63  jz      short loc_14002AE9A
0x14002ae65  mov     edx, esi
0x14002ae67  sar     edx, 1Fh
0x14002ae6a  and     edx, 0FFFFFFFDh
0x14002ae6d  add     edx, 5
0x14002ae70  movzx   eax, byte ptr [rcx+19h]
0x14002ae74  cmp     eax, edx
0x14002ae76  jb      short loc_14002AE9A
0x14002ae78  mov     edx, 95h
0x14002ae7d  mov     rax, [rsp+150h+var_108]
0x14002ae82  mov     [rsp+150h+lpString2], rax
0x14002ae87  mov     r9d, esi
0x14002ae8a  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002ae91  mov     rcx, [rcx+10h]
0x14002ae95  call    WPP_SF_dq
0x14002ae9a  test    esi, esi
0x14002ae9c  js      loc_14002B709
0x14002aea2  mov     rax, [r12]
0x14002aea6  lea     r8, [rbp+50h+arg_0]
0x14002aeaa  lea     rdx, IID_IPropertyStore
0x14002aeb1  mov     rcx, r12
0x14002aeb4  mov     rax, [rax+138h]
0x14002aebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aec0  mov     esi, eax
0x14002aec2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aec9  lea     rax, WPP_GLOBAL_Control
0x14002aed0  cmp     rcx, rax
0x14002aed3  jz      short loc_14002AF0F
0x14002aed5  test    byte ptr [rcx+1Ch], 2
0x14002aed9  jz      short loc_14002AF0F
0x14002aedb  mov     edx, esi
0x14002aedd  sar     edx, 1Fh
0x14002aee0  and     edx, 0FFFFFFFDh
0x14002aee3  add     edx, 5
0x14002aee6  movzx   eax, byte ptr [rcx+19h]
0x14002aeea  cmp     eax, edx
0x14002aeec  jb      short loc_14002AF0F
0x14002aeee  mov     edx, 96h
0x14002aef3  mov     rax, [rbp+50h+arg_0]
0x14002aef7  mov     [rsp+150h+lpString2], rax
0x14002aefc  mov     r9d, esi
0x14002aeff  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002af06  mov     rcx, [rcx+10h]
0x14002af0a  call    WPP_SF_dq
0x14002af0f  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14002af16  jz      short loc_14002AF21
0x14002af18  mov     r8, [rbp+50h+arg_0]
0x14002af1c  call    McTemplateU0p_EventWriteTransfer
0x14002af21  test    esi, esi
0x14002af23  js      loc_14002B709
0x14002af29  mov     rcx, [rbp+50h+arg_0]
0x14002af2d  mov     rax, [rcx]
0x14002af30  lea     r8, [rbp+50h+pvar]
0x14002af34  lea     rdx, qword_1400BF680
0x14002af3b  mov     rax, [rax+28h]
0x14002af3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af44  mov     esi, eax
0x14002af46  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af4d  lea     rax, WPP_GLOBAL_Control
0x14002af54  cmp     rcx, rax
0x14002af57  jz      short loc_14002AFA0
0x14002af59  test    byte ptr [rcx+1Ch], 2
0x14002af5d  jz      short loc_14002AFA0
0x14002af5f  mov     edx, esi
0x14002af61  sar     edx, 1Fh
0x14002af64  and     edx, 0FFFFFFFDh
0x14002af67  add     edx, 5
0x14002af6a  movzx   eax, byte ptr [rcx+19h]
0x14002af6e  cmp     eax, edx
0x14002af70  jb      short loc_14002AF99
0x14002af72  movzx   eax, word ptr [rbp+50h+pvar]
0x14002af76  mov     edx, 97h
0x14002af7b  mov     dword ptr [rsp+150h+lpString2], eax
0x14002af7f  mov     r9d, esi
0x14002af82  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002af89  mov     rcx, [rcx+10h]
0x14002af8d  call    WPP_SF_Dd
0x14002af92  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af99  lea     rax, WPP_GLOBAL_Control
0x14002afa0  test    esi, esi
0x14002afa2  js      loc_14002B709
0x14002afa8  cmp     [rbp+50h+pvar+8], r14
0x14002afac  jz      loc_14002B854
0x14002afb2  mov     edx, 1Fh
0x14002afb7  cmp     dx, word ptr [rbp+50h+pvar]
0x14002afbb  jnz     loc_14002B854
0x14002afc1  mov     rcx, [rsp+150h+var_108]
0x14002afc6  mov     rax, [rcx]
0x14002afc9  lea     rdx, [rsp+150h+var_100]
0x14002afce  mov     rax, [rax+150h]
0x14002afd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002afda  mov     esi, eax
0x14002afdc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002afe3  lea     rax, WPP_GLOBAL_Control
0x14002afea  cmp     rcx, rax
0x14002afed  jz      short loc_14002B02A
0x14002afef  test    byte ptr [rcx+1Ch], 2
0x14002aff3  jz      short loc_14002B02A
0x14002aff5  mov     edx, esi
0x14002aff7  sar     edx, 1Fh
0x14002affa  and     edx, 0FFFFFFFDh
0x14002affd  add     edx, 5
0x14002b000  movzx   eax, byte ptr [rcx+19h]
0x14002b004  cmp     eax, edx
0x14002b006  jb      short loc_14002B02A
0x14002b008  mov     edx, 99h
0x14002b00d  mov     rax, [rsp+150h+var_100]
0x14002b012  mov     [rsp+150h+lpString2], rax
0x14002b017  mov     r9d, esi
0x14002b01a  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002b021  mov     rcx, [rcx+10h]
0x14002b025  call    WPP_SF_dS
0x14002b02a  test    esi, esi
0x14002b02c  js      loc_14002B709
0x14002b032  xorps   xmm0, xmm0
0x14002b035  xor     eax, eax
0x14002b037  movups  xmmword ptr [rsp+150h+var_F0+8], xmm0
0x14002b03c  mov     [rsp+150h+var_D8], rax
0x14002b041  mov     eax, 1Fh
0x14002b046  mov     word ptr [rsp+150h+var_F0+8], ax
0x14002b04b  mov     rax, [rsp+150h+var_100]
0x14002b050  mov     [rsp+150h+var_E0], rax
0x14002b055  mov     rcx, [rbp+50h+arg_0]
0x14002b059  mov     rax, [rcx]
0x14002b05c  lea     r8, [rsp+150h+var_F0+8]
0x14002b061  lea     rdx, qword_1400BF668
0x14002b068  mov     rax, [rax+30h]
0x14002b06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b071  mov     esi, eax
0x14002b073  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b07a  lea     rax, WPP_GLOBAL_Control
0x14002b081  cmp     rcx, rax
0x14002b084  jz      short loc_14002B0C1
0x14002b086  test    byte ptr [rcx+1Ch], 2
0x14002b08a  jz      short loc_14002B0C1
0x14002b08c  mov     edx, esi
0x14002b08e  sar     edx, 1Fh
0x14002b091  and     edx, 0FFFFFFFDh
0x14002b094  add     edx, 5
0x14002b097  movzx   eax, byte ptr [rcx+19h]
0x14002b09b  cmp     eax, edx
0x14002b09d  jb      short loc_14002B0C1
0x14002b09f  mov     edx, 9Ah
0x14002b0a4  mov     rax, [rsp+150h+var_100]
0x14002b0a9  mov     [rsp+150h+lpString2], rax
0x14002b0ae  mov     r9d, esi
0x14002b0b1  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002b0b8  mov     rcx, [rcx+10h]
0x14002b0bc  call    WPP_SF_dS
0x14002b0c1  test    esi, esi
0x14002b0c3  js      loc_14002B709
0x14002b0c9  mov     rdx, [rsp+150h+var_100]
0x14002b0ce  lea     rcx, [rsp+150h+var_110]
0x14002b0d3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14002b0d8  nop
0x14002b0d9  lea     r8, [rbp+50h+var_90]
0x14002b0dd  lea     rdx, [rbp+50h+var_C0]
0x14002b0e1  lea     rcx, [rsp+150h+var_110]
0x14002b0e6  call    ?ParseUrl@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@AEAV12@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V3@@2@@Z; ParseUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>> &)
0x14002b0eb  mov     esi, eax
0x14002b0ed  lea     rcx, [rsp+150h+var_110]
0x14002b0f2  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14002b0f7  test    esi, esi
0x14002b0f9  js      loc_14002B709
0x14002b0ff  mov     rax, [r12]
0x14002b103  lea     r8, [rbp+50h+var_B0]
0x14002b107  lea     rdx, IID_IPropertyStore
0x14002b10e  mov     rcx, r12
0x14002b111  mov     rax, [rax+130h]
0x14002b118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b11d  mov     esi, eax
0x14002b11f  test    eax, eax
0x14002b121  js      loc_14002B709
  ... truncated ...
```
