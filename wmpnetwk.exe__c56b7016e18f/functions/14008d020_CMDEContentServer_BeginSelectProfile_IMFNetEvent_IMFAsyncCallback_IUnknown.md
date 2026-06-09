# CMDEContentServer::BeginSelectProfile(IMFNetEvent *,IMFAsyncCallback *,IUnknown *)

- ea: `0x14008d020`
- end: `0x14008d946`
- name: `?BeginSelectProfile@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `2342`
- prototype: `int(CMDEContentServer *__hidden this, struct IMFNetEvent *, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14008f4ac`

## callees

- `0x140006d70`
- `0x14000b3b0`
- `0x14000c920`
- `0x140024688`
- `0x140035084`
- `0x1400359f4`
- `0x140039218`
- `0x14003a168`
- `0x14003b898`
- `0x14003f17c`
- `0x140041c80`
- `0x140045f20`
- `0x14004a500`
- `0x14004a834`
- `0x14005480c`
- `0x140057bc4`
- `0x14005e7c0`
- `0x140062f88`
- `0x14008d020`
- `0x140090118`
- `0x140090174`
- `0x1400909a4`
- `0x14009e010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x14008d750`
- `OLEAUT32!__imp_VariantClear` at `0x14008d75b`
- `OLEAUT32!__imp_VariantClear` at `0x14008d750`
- `OLEAUT32!__imp_VariantClear` at `0x14008d75b`
- `ole32!PropVariantClear` at `0x14008d765`
- `ole32!PropVariantClear` at `0x14008d83e`
- `ole32!PropVariantClear` at `0x14008d848`
- `ole32!PropVariantClear` at `0x14008d765`
- `ole32!PropVariantClear` at `0x14008d83e`
- `ole32!PropVariantClear` at `0x14008d848`
- `MFPlat!MFCreateAsyncResult` at `0x14008d15d`
- `MFPlat!MFCreateAsyncResult` at `0x14008d15d`
- `MFPlat!MFInvokeCallback` at `0x14008d7cd`
- `MFPlat!MFInvokeCallback` at `0x14008d7cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CMDEContentServer::BeginSelectProfile(
        CMDEContentServer *this,
        IUnknown *a2,
        struct IMFAsyncCallback *a3,
        struct IUnknown *a4)
{
  int v8; // ecx
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  int ObjectW; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  PVOID *v15; // r10
  PVOID *v16; // r10
  int v17; // edi
  int v18; // r9d
  __int64 v19; // rdx
  PVOID v20; // rcx
  int v21; // ecx
  int v23; // [rsp+30h] [rbp-D0h]
  int v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  struct IWMCUPnPObject *v27; // [rsp+50h] [rbp-B0h] BYREF
  struct IPropertyStore *v28; // [rsp+58h] [rbp-A8h] BYREF
  struct IMFCollection *v29; // [rsp+60h] [rbp-A0h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  void *v32; // [rsp+78h] [rbp-88h] BYREF
  PROPVARIANT v33[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+90h] [rbp-70h]
  PROPVARIANT pvar[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-58h]
  PROPVARIANT v37[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-28h] BYREF
  VARIANTARG v42; // [rsp+F0h] [rbp-10h] BYREF
  VARIANTARG v43; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG v44; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v45[80]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v46[528]; // [rsp+1A0h] [rbp+A0h] BYREF

  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(
    &v40,
    ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      v8,
      (unsigned int)MDE_Callback_Begin_Select_Profile_Start,
      (_DWORD)a2,
      (_DWORD)a3,
      (char)a4,
      0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, a2, a3, a4);
  }
  ppAsyncResult = 0;
  v26 = 0;
  v29 = 0;
  v28 = 0;
  v25 = 0;
  v27 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v31);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v39);
  ATL::CAtlMap<_GUID,bool,ATL::CElementTraits<_GUID>,ATL::CElementTraits<bool>>::CAtlMap<_GUID,bool,ATL::CElementTraits<_GUID>,ATL::CElementTraits<bool>>(
    (unsigned int)v45,
    v9,
    v10,
    v11,
    LODWORD(FLOAT_2_25));
  *(_OWORD *)v33 = 0;
  v34 = 0;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  ObjectW = MFCreateAsyncResult(a2, a3, a4, &ppAsyncResult);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      168,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)ObjectW);
  }
  if ( ObjectW >= 0 )
  {
    ObjectW = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                a2,
                &IID_IMFNetProfilesEvent,
                &v26);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        169,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)ObjectW,
        v26);
    }
    if ( ObjectW >= 0 )
    {
      ObjectW = (*(__int64 (__fastcall **)(__int64, struct IMFCollection **))(*(_QWORD *)v26 + 384LL))(v26, &v29);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_dq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          170,
          &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
          (unsigned int)ObjectW,
          v29);
      }
      if ( ObjectW >= 0 )
      {
        ObjectW = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl[13].QueryInterface)(
                    a2,
                    &IID_IPropertyStore,
                    &v25);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v14 = ((ObjectW >> 31) & 0xFFFFFFFD) + 5;
          if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v14 )
            WPP_SF_dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              171,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)ObjectW,
              v25);
        }
        if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
          McTemplateU0p_EventWriteTransfer(v14, v13, v25);
        if ( ObjectW >= 0 )
        {
          ObjectW = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
                      v25,
                      qword_1400BF668,
                      v33);
          v15 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              172,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)ObjectW);
            v15 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( ObjectW >= 0 )
          {
            if ( LOWORD(v33[0]) != 31 )
            {
              ObjectW = -2147418113;
              if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 2u )
                WPP_SF_DDd(
                  v15[2],
                  173,
                  &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                  2147549183LL,
                  31,
                  LOWORD(v33[0]));
              goto LABEL_84;
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v32,
              (char *)v33[1]);
            ObjectW = ParseUrl(&v32, &v31, v45);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v32);
            if ( ObjectW >= 0 )
            {
              ObjectW = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
                          v25,
                          qword_1400BF680,
                          v37);
              v16 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
              {
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  174,
                  &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                  (unsigned int)ObjectW);
                v16 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( ObjectW >= 0 )
              {
                if ( !v37[1] || LOWORD(v37[0]) != 31 )
                {
                  ObjectW = -2147467259;
                  if ( v16 == &WPP_GLOBAL_Control || (*((_BYTE *)v16 + 28) & 2) == 0 || *((_BYTE *)v16 + 25) < 2u )
                    goto LABEL_84;
                  v19 = 175;
                  v20 = v16[2];
LABEL_83:
                  WPP_SF_d(v20, v19, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, (unsigned int)ObjectW);
                  goto LABEL_84;
                }
                ObjectW = CMDEContentServer::GetObjectW(this, &v31, v37[1], &v27);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    176,
                    &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                    (unsigned int)ObjectW);
                }
                if ( ObjectW >= 0 )
                {
                  ObjectW = CMDEContentServer::GetProfile(this, v29, v27, (const WCHAR *)v33[1], (__int64)v45, &v28);
                  if ( ObjectW >= 0 )
                  {
                    ObjectW = (*(__int64 (__fastcall **)(__int64, struct IPropertyStore *))(*(_QWORD *)v26 + 408LL))(
                                v26,
                                v28);
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        177,
                        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                        (unsigned int)ObjectW);
                    }
                    if ( ObjectW >= 0 )
                    {
                      *(_OWORD *)pvar = 0;
                      v36 = 0;
                      v17 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v28->lpVtbl->GetValue)(
                              v28,
                              PKEY_MDEPROFILE_HTTP_ENABLED,
                              pvar);
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v17 >> 31) & 0xFFFFFFFD) + 5 )
                      {
                        v24 = LOWORD(pvar[0]);
                        v23 = 11;
                        WPP_SF_d_guid_Ddd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          178,
                          (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                          v17,
                          (__int64)PKEY_MDEPROFILE_HTTP_ENABLED);
                      }
                      if ( v17 >= 0 && LOWORD(pvar[0]) == 11 && LOWORD(pvar[1]) )
                      {
                        v42.vt = 19;
                        v42.lVal = 3;
                        pvarg.vt = 19;
                        pvarg.lVal = 8;
                        v43 = pvarg;
                        v44 = v42;
                        v18 = (*(__int64 (__fastcall **)(struct IWMCUPnPObject *, VARIANTARG *, _QWORD, VARIANTARG *, int, _BYTE *, int, int))(*(_QWORD *)v27 + 64LL))(
                                v27,
                                &v44,
                                0,
                                &v43,
                                256,
                                v46,
                                v23,
                                v24);
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v18 >> 31) & 0xFFFFFFFD) + 5 )
                        {
                          WPP_SF_dLLS(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            179,
                            (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                            v18,
                            v42.cVal,
                            pvarg.cVal,
                            (__int64)v46);
                        }
                        VariantClear(&pvarg);
                        VariantClear(&v42);
                      }
                      PropVariantClear(pvar);
                      ObjectW = ((__int64 (__fastcall *)(IMFAsyncResult *, _QWORD))ppAsyncResult->lpVtbl->SetStatus)(
                                  ppAsyncResult,
                                  (unsigned int)ObjectW);
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          180,
                          &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                          (unsigned int)ObjectW);
                      }
                      if ( ObjectW >= 0 )
                      {
                        ObjectW = MFInvokeCallback(ppAsyncResult);
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
                        {
                          v19 = 181;
                          v20 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
                          goto LABEL_83;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_84:
  PropVariantClear(v33);
  PropVariantClear(v37);
  v21 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ObjectW >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      182,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)ObjectW);
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      v21,
      (unsigned int)MDE_Callback_Begin_Select_Profile_Stop,
      (_DWORD)a2,
      (_DWORD)a3,
      (char)a4,
      ObjectW);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(v45);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v39);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppAsyncResult);
  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v40);
  return (unsigned int)ObjectW;
}

```

## disassembly

```asm
0x14008d020  push    rbp
0x14008d022  push    rbx
0x14008d023  push    rsi
0x14008d024  push    rdi
0x14008d025  push    r12
0x14008d027  push    r13
0x14008d029  push    r14
0x14008d02b  push    r15
0x14008d02d  lea     rbp, [rsp-2C8h]
0x14008d035  sub     rsp, 3C8h
0x14008d03c  mov     rax, cs:__security_cookie
0x14008d043  xor     rax, rsp
0x14008d046  mov     [rbp+300h+var_50], rax
0x14008d04d  mov     r15, r9
0x14008d050  mov     r14, r8
0x14008d053  mov     rsi, rdx
0x14008d056  mov     rdi, rcx
0x14008d059  mov     rax, rcx
0x14008d05c  add     rcx, 8
0x14008d060  neg     rax
0x14008d063  sbb     rdx, rdx
0x14008d066  and     rdx, rcx
0x14008d069  lea     rcx, [rbp+300h+var_330]
0x14008d06d  call    ??0?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@PEAV?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@1@@Z; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(ATL::CComObjectRootEx<ATL::CComMultiThreadModel> *)
0x14008d072  nop
0x14008d073  xor     r12d, r12d
0x14008d076  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14008d07d  jz      short loc_14008D09B
0x14008d07f  mov     dword ptr [rsp+400h+var_3D8], r12d
0x14008d084  mov     [rsp+400h+var_3E0], r15
0x14008d089  mov     r9, r14
0x14008d08c  mov     r8, rsi
0x14008d08f  lea     rdx, MDE_Callback_Begin_Select_Profile_Start
0x14008d096  call    McTemplateU0pppq_EventWriteTransfer
0x14008d09b  lea     rax, WPP_GLOBAL_Control
0x14008d0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d0a9  cmp     rcx, rax
0x14008d0ac  jz      short loc_14008D0DC
0x14008d0ae  test    byte ptr [rcx+1Ch], 1
0x14008d0b2  jz      short loc_14008D0DC
0x14008d0b4  cmp     byte ptr [rcx+19h], 5
0x14008d0b8  jb      short loc_14008D0DC
0x14008d0ba  mov     edx, 0A7h
0x14008d0bf  mov     [rsp+400h+var_3D8], r15
0x14008d0c4  mov     [rsp+400h+var_3E0], r14
0x14008d0c9  mov     r9, rsi
0x14008d0cc  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008d0d3  mov     rcx, [rcx+10h]
0x14008d0d7  call    WPP_SF_qqq
0x14008d0dc  mov     [rsp+400h+ppAsyncResult], r12
0x14008d0e1  mov     [rsp+400h+var_3B8], r12
0x14008d0e6  mov     [rsp+400h+var_3A0], r12
0x14008d0eb  mov     [rsp+400h+var_3A8], r12
0x14008d0f0  mov     [rsp+400h+var_3C0], r12
0x14008d0f5  mov     [rsp+400h+var_3B0], r12
0x14008d0fa  lea     rcx, [rsp+400h+var_390]
0x14008d0ff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14008d104  nop
0x14008d105  lea     rcx, [rbp+300h+var_338]
0x14008d109  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14008d10e  nop
0x14008d10f  movss   xmm0, cs:__real@40100000
0x14008d117  movss   dword ptr [rsp+400h+var_3E0], xmm0
0x14008d11d  movss   xmm3, cs:__real@3e800000
0x14008d125  movss   xmm2, cs:__real@3f400000
0x14008d12d  lea     rcx, [rbp+300h+var_2B0]
0x14008d131  call    ??0?$CAtlMap@U_GUID@@_NV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@_N@3@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<_GUID,bool,ATL::CElementTraits<_GUID>,ATL::CElementTraits<bool>>::CAtlMap<_GUID,bool,ATL::CElementTraits<_GUID>,ATL::CElementTraits<bool>>(uint,float,float,float,uint)
0x14008d136  nop
0x14008d137  xorps   xmm3, xmm3
0x14008d13a  xor     eax, eax
0x14008d13c  movups  xmmword ptr [rbp+300h+var_380], xmm3
0x14008d140  mov     [rbp+300h+var_370], rax
0x14008d144  xorps   xmm0, xmm0
0x14008d147  movups  xmmword ptr [rbp+300h+var_350], xmm0
0x14008d14b  mov     [rbp+300h+var_340], rax
0x14008d14f  lea     r9, [rsp+400h+ppAsyncResult]; ppAsyncResult
0x14008d154  mov     r8, r15; punkState
0x14008d157  mov     rdx, r14; pCallback
0x14008d15a  mov     rcx, rsi; punkObject
0x14008d15d  call    cs:__imp_MFCreateAsyncResult
0x14008d163  mov     ebx, eax
0x14008d165  mov     r13b, 2
0x14008d168  mov     r10, cs:WPP_GLOBAL_Control
0x14008d16f  lea     rax, WPP_GLOBAL_Control
0x14008d176  cmp     r10, rax
0x14008d179  jz      short loc_14008D1AD
0x14008d17b  test    [r10+1Ch], r13b
0x14008d17f  jz      short loc_14008D1AD
0x14008d181  mov     ecx, ebx
0x14008d183  sar     ecx, 1Fh
0x14008d186  and     ecx, 0FFFFFFFDh
0x14008d189  add     ecx, 5
0x14008d18c  movzx   eax, byte ptr [r10+19h]
0x14008d191  cmp     eax, ecx
0x14008d193  jb      short loc_14008D1AD
0x14008d195  mov     edx, 0A8h
0x14008d19a  mov     r9d, ebx
0x14008d19d  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008d1a4  mov     rcx, [r10+10h]
0x14008d1a8  call    WPP_SF_d
0x14008d1ad  test    ebx, ebx
0x14008d1af  js      loc_14008D83A
0x14008d1b5  mov     rax, [rsi]
0x14008d1b8  lea     r8, [rsp+400h+var_3B8]
0x14008d1bd  lea     rdx, IID_IMFNetProfilesEvent
0x14008d1c4  mov     rcx, rsi
0x14008d1c7  mov     rax, [rax]
0x14008d1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d1cf  mov     ebx, eax
0x14008d1d1  mov     r10, cs:WPP_GLOBAL_Control
0x14008d1d8  lea     rax, WPP_GLOBAL_Control
0x14008d1df  cmp     r10, rax
0x14008d1e2  jz      short loc_14008D220
0x14008d1e4  test    [r10+1Ch], r13b
0x14008d1e8  jz      short loc_14008D220
0x14008d1ea  mov     ecx, ebx
0x14008d1ec  sar     ecx, 1Fh
0x14008d1ef  and     ecx, 0FFFFFFFDh
0x14008d1f2  add     ecx, 5
0x14008d1f5  movzx   eax, byte ptr [r10+19h]
0x14008d1fa  cmp     eax, ecx
0x14008d1fc  jb      short loc_14008D220
0x14008d1fe  mov     edx, 0A9h
0x14008d203  mov     rax, [rsp+400h+var_3B8]
0x14008d208  mov     [rsp+400h+var_3E0], rax
0x14008d20d  mov     r9d, ebx
0x14008d210  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008d217  mov     rcx, [r10+10h]
0x14008d21b  call    WPP_SF_dq
0x14008d220  test    ebx, ebx
0x14008d222  js      loc_14008D83A
0x14008d228  mov     rcx, [rsp+400h+var_3B8]
0x14008d22d  mov     rax, [rcx]
0x14008d230  lea     rdx, [rsp+400h+var_3A0]
0x14008d235  mov     rax, [rax+180h]
0x14008d23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d241  mov     ebx, eax
0x14008d243  mov     r10, cs:WPP_GLOBAL_Control
0x14008d24a  lea     rax, WPP_GLOBAL_Control
0x14008d251  cmp     r10, rax
0x14008d254  jz      short loc_14008D292
0x14008d256  test    [r10+1Ch], r13b
0x14008d25a  jz      short loc_14008D292
0x14008d25c  mov     ecx, ebx
0x14008d25e  sar     ecx, 1Fh
0x14008d261  and     ecx, 0FFFFFFFDh
0x14008d264  add     ecx, 5
0x14008d267  movzx   eax, byte ptr [r10+19h]
0x14008d26c  cmp     eax, ecx
0x14008d26e  jb      short loc_14008D292
0x14008d270  mov     edx, 0AAh
0x14008d275  mov     rax, [rsp+400h+var_3A0]
0x14008d27a  mov     [rsp+400h+var_3E0], rax
0x14008d27f  mov     r9d, ebx
0x14008d282  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008d289  mov     rcx, [r10+10h]
0x14008d28d  call    WPP_SF_dq
0x14008d292  test    ebx, ebx
0x14008d294  js      loc_14008D83A
0x14008d29a  mov     rax, [rsi]
0x14008d29d  lea     r8, [rsp+400h+var_3C0]
0x14008d2a2  lea     rdx, IID_IPropertyStore
0x14008d2a9  mov     rcx, rsi
0x14008d2ac  mov     rax, [rax+138h]
0x14008d2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d2b8  mov     ebx, eax
0x14008d2ba  mov     r10, cs:WPP_GLOBAL_Control
0x14008d2c1  lea     rax, WPP_GLOBAL_Control
0x14008d2c8  cmp     r10, rax
0x14008d2cb  jz      short loc_14008D309
0x14008d2cd  test    [r10+1Ch], r13b
0x14008d2d1  jz      short loc_14008D309
0x14008d2d3  mov     ecx, ebx
0x14008d2d5  sar     ecx, 1Fh
0x14008d2d8  and     ecx, 0FFFFFFFDh
0x14008d2db  add     ecx, 5
0x14008d2de  movzx   eax, byte ptr [r10+19h]
0x14008d2e3  cmp     eax, ecx
0x14008d2e5  jb      short loc_14008D309
0x14008d2e7  mov     edx, 0ABh
0x14008d2ec  mov     rax, [rsp+400h+var_3C0]
0x14008d2f1  mov     [rsp+400h+var_3E0], rax
0x14008d2f6  mov     r9d, ebx
0x14008d2f9  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008d300  mov     rcx, [r10+10h]
0x14008d304  call    WPP_SF_dq
0x14008d309  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14008d310  jz      short loc_14008D31C
0x14008d312  mov     r8, [rsp+400h+var_3C0]
0x14008d317  call    McTemplateU0p_EventWriteTransfer
0x14008d31c  test    ebx, ebx
0x14008d31e  js      loc_14008D83A
0x14008d324  mov     rcx, [rsp+400h+var_3C0]
0x14008d329  mov     rax, [rcx]
0x14008d32c  lea     r8, [rbp+300h+var_380]
0x14008d330  lea     rdx, qword_1400BF668
0x14008d337  mov     rax, [rax+28h]
0x14008d33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d340  mov     ebx, eax
0x14008d342  mov     r10, cs:WPP_GLOBAL_Control
0x14008d349  lea     rax, WPP_GLOBAL_Control
0x14008d350  cmp     r10, rax
0x14008d353  jz      short loc_14008D395
0x14008d355  test    [r10+1Ch], r13b
0x14008d359  jz      short loc_14008D395
0x14008d35b  mov     ecx, ebx
0x14008d35d  sar     ecx, 1Fh
0x14008d360  and     ecx, 0FFFFFFFDh
0x14008d363  add     ecx, 5
0x14008d366  movzx   eax, byte ptr [r10+19h]
0x14008d36b  cmp     eax, ecx
0x14008d36d  jb      short loc_14008D38E
0x14008d36f  mov     edx, 0ACh
0x14008d374  mov     r9d, ebx
0x14008d377  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008d37e  mov     rcx, [r10+10h]
0x14008d382  call    WPP_SF_d
0x14008d387  mov     r10, cs:WPP_GLOBAL_Control
0x14008d38e  lea     rax, WPP_GLOBAL_Control
0x14008d395  test    ebx, ebx
0x14008d397  js      loc_14008D83A
0x14008d39d  mov     ecx, 1Fh
0x14008d3a2  cmp     cx, word ptr [rbp+300h+var_380]
0x14008d3a6  jz      short loc_14008D3F3
0x14008d3a8  mov     ebx, 8000FFFFh
0x14008d3ad  cmp     r10, rax
0x14008d3b0  jz      loc_14008D83A
0x14008d3b6  test    [r10+1Ch], r13b
0x14008d3ba  jz      loc_14008D83A
0x14008d3c0  cmp     [r10+19h], r13b
0x14008d3c4  jb      loc_14008D83A
0x14008d3ca  movzx   eax, word ptr [rbp+300h+var_380]
0x14008d3ce  mov     edx, 0ADh
0x14008d3d3  mov     dword ptr [rsp+400h+var_3D8], eax
0x14008d3d7  mov     dword ptr [rsp+400h+var_3E0], ecx
0x14008d3db  mov     r9d, ebx
0x14008d3de  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008d3e5  mov     rcx, [r10+10h]
0x14008d3e9  call    WPP_SF_DDd
0x14008d3ee  jmp     loc_14008D83A
0x14008d3f3  mov     rdx, [rbp+300h+var_380+8]
0x14008d3f7  lea     rcx, [rsp+400h+var_388]
0x14008d3fc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14008d401  nop
0x14008d402  lea     r8, [rbp+300h+var_2B0]
0x14008d406  lea     rdx, [rsp+400h+var_390]
0x14008d40b  lea     rcx, [rsp+400h+var_388]
0x14008d410  call    ?ParseUrl@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@AEAV12@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V3@@2@@Z; ParseUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>> &)
0x14008d415  mov     ebx, eax
0x14008d417  lea     rcx, [rsp+400h+var_388]
0x14008d41c  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14008d421  test    ebx, ebx
0x14008d423  js      loc_14008D83A
0x14008d429  mov     rcx, [rsp+400h+var_3C0]
0x14008d42e  mov     rax, [rcx]
0x14008d431  lea     r8, [rbp+300h+var_350]
0x14008d435  lea     rdx, qword_1400BF680
0x14008d43c  mov     rax, [rax+28h]
0x14008d440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d445  mov     ebx, eax
0x14008d447  mov     r10, cs:WPP_GLOBAL_Control
0x14008d44e  lea     rax, WPP_GLOBAL_Control
0x14008d455  cmp     r10, rax
0x14008d458  jz      short loc_14008D4A2
0x14008d45a  test    [r10+1Ch], r13b
0x14008d45e  jz      short loc_14008D4A2
0x14008d460  mov     ecx, ebx
0x14008d462  sar     ecx, 1Fh
0x14008d465  and     ecx, 0FFFFFFFDh
0x14008d468  add     ecx, 5
0x14008d46b  movzx   eax, byte ptr [r10+19h]
0x14008d470  cmp     eax, ecx
0x14008d472  jb      short loc_14008D49B
0x14008d474  movzx   eax, word ptr [rbp+300h+var_350]
0x14008d478  mov     edx, 0AEh
0x14008d47d  mov     dword ptr [rsp+400h+var_3E0], eax
0x14008d481  mov     r9d, ebx
0x14008d484  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008d48b  mov     rcx, [r10+10h]
0x14008d48f  call    WPP_SF_Dd
0x14008d494  mov     r10, cs:WPP_GLOBAL_Control
0x14008d49b  lea     rax, WPP_GLOBAL_Control
0x14008d4a2  test    ebx, ebx
0x14008d4a4  js      loc_14008D83A
0x14008d4aa  mov     r8, [rbp+300h+var_350+8]
0x14008d4ae  test    r8, r8
0x14008d4b1  jz      loc_14008D80C
0x14008d4b7  mov     ecx, 1Fh
0x14008d4bc  cmp     cx, word ptr [rbp+300h+var_350]
0x14008d4c0  jnz     loc_14008D80C
0x14008d4c6  lea     r9, [rsp+400h+var_3B0]
0x14008d4cb  lea     rdx, [rsp+400h+var_390]
0x14008d4d0  mov     rcx, rdi
0x14008d4d3  call    ?GetObjectW@CMDEContentServer@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAUIWMCUPnPObject@@_N@Z; CMDEContentServer::GetObjectW(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *,IWMCUPnPObject * *,bool)
0x14008d4d8  mov     ebx, eax
0x14008d4da  mov     r10, cs:WPP_GLOBAL_Control
0x14008d4e1  lea     rax, WPP_GLOBAL_Control
0x14008d4e8  cmp     r10, rax
0x14008d4eb  jz      short loc_14008D51F
0x14008d4ed  test    [r10+1Ch], r13b
  ... truncated ...
```
