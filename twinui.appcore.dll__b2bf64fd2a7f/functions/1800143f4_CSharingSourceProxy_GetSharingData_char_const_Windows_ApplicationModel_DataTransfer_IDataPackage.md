# CSharingSourceProxy::GetSharingData(char const *,Windows::ApplicationModel::DataTransfer::IDataPackage * *)

- ea: `0x1800143f4`
- end: `0x180014a01`
- name: `?GetSharingData@CSharingSourceProxy@@QEAAJPEBDPEAPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@@Z`
- size: `1549`
- prototype: `__int64 __fastcall(CSharingSourceProxy *__hidden this, const char *, struct Windows::ApplicationModel::DataTransfer::IDataPackage **)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006d978`

## callees

- `0x180003d24`
- `0x180012450`
- `0x1800143f4`
- `0x1800177a4`
- `0x1800192a8`
- `0x18001d95c`
- `0x180022f48`
- `0x1800231c8`
- `0x180024a00`
- `0x180026498`
- `0x1800299c8`
- `0x18002b1b0`
- `0x18002b1e0`
- `0x18004ffec`
- `0x18005f54c`
- `0x180062420`
- `0x180062c48`
- `0x1800656b8`
- `0x18006575c`
- `0x1800660b8`
- `0x180066158`
- `0x180067f48`
- `0x18006c2b8`
- `0x18006f470`
- `0x180070170`
- `0x180070504`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014493`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180014881`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180014881`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014662`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014662`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180014738`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180014738`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x1800147f1`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x1800147f1`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x1800147bd`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x1800147bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CSharingSourceProxy::GetSharingData(
        CSharingSourceProxy *this,
        const char *a2,
        struct Windows::ApplicationModel::DataTransfer::IDataPackage **a3)
{
  __int64 v6; // rbx
  CSharingRequestPriv *v7; // rax
  __int64 v8; // r8
  int Error; // ebx
  CSharingRequestPriv *v10; // r14
  HANDLE EventW; // rbx
  __int64 v12; // rcx
  HWND v13; // rcx
  unsigned int v14; // edx
  unsigned int v15; // eax
  HRESULT v16; // eax
  CSharingRequestPriv *v17; // rbx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  HANDLE v20; // rdi
  __int64 (__fastcall *v21)(HANDLE, _QWORD); // rbx
  __int64 v22; // rax
  HRESULT v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdi
  CSharingRequestPriv *v27; // rcx
  LPDWORD lpdwindex; // [rsp+20h] [rbp-69h]
  unsigned int v30; // [rsp+28h] [rbp-61h]
  DWORD dwindex[2]; // [rsp+30h] [rbp-59h] BYREF
  CSharingRequestPriv *v32; // [rsp+38h] [rbp-51h] BYREF
  __int64 v33; // [rsp+40h] [rbp-49h] BYREF
  CSharingRequestPriv *v34; // [rsp+48h] [rbp-41h] BYREF
  HANDLE pHandles[3]; // [rsp+50h] [rbp-39h] BYREF
  void *v36; // [rsp+68h] [rbp-21h] BYREF
  __int64 v37; // [rsp+70h] [rbp-19h] BYREF
  __int64 v38; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v39[32]; // [rsp+80h] [rbp-9h] BYREF

  *a3 = 0;
  v32 = 0;
  v6 = *((_QWORD *)this + 3);
  Microsoft::WRL::ComPtr<CSharingRequestPriv>::InternalRelease(&v32);
  v32 = 0;
  v7 = (CSharingRequestPriv *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
  {
    Error = -2147024882;
LABEL_72:
    v13 = (HWND)WPP_GLOBAL_Control;
    goto LABEL_73;
  }
  v10 = CSharingRequestPriv::CSharingRequestPriv(v7);
  v34 = v10;
  pHandles[0] = 0;
  Microsoft::WRL::ComPtr<ISharePlatformHost>::operator=((char *)v10 + 72, v6);
  EventW = CreateEventW(0, 1, 0, 0);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)v10 + 48);
  *((_QWORD *)v10 + 6) = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v10 + 2) + 8LL))((__int64)v10 + 16);
    v32 = v10;
    Error = 0;
  }
  Microsoft::WRL::ComPtr<CSharingRequestPriv>::InternalRelease(&v34);
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(pHandles);
  if ( Error < 0 )
    goto LABEL_72;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_cc4239f610b1355862d418c222e868a6_Traceguids, this);
  }
  v33 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  v12 = *((_QWORD *)this + 4);
  if ( v12 )
  {
    Error = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v12 + 24LL))(
              v12,
              &GUID_252e6571_8157_4809_8e2a_94aaa9e5de60,
              &v33);
  }
  else
  {
    v33 = 0;
    Error = 0;
  }
  if ( Error >= 0 )
  {
    CRPCTimeout::CRPCTimeout((CRPCTimeout *)pHandles, 0x64u);
    Error = (*(__int64 (__fastcall **)(__int64, const char *, unsigned __int64))(*(_QWORD *)v33 + 48LL))(
              v33,
              a2,
              ((unsigned __int64)v32 + 16) & -(__int64)(v32 != 0));
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)pHandles);
  }
  v13 = (HWND)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_cc4239f610b1355862d418c222e868a6_Traceguids, this, Error);
    v13 = (HWND)WPP_GLOBAL_Control;
  }
  if ( Error >= 0 || Error == -2147417825 || Error == -2147418110 )
  {
    if ( !*((_QWORD *)v32 + 6) )
      goto LABEL_47;
    pHandles[0] = *((HANDLE *)v32 + 6);
    pHandles[1] = *((HANDLE *)this + 6);
    v14 = *((_DWORD *)this + 2);
    if ( *((_BYTE *)this + 56) )
    {
      v15 = SHProcessMessagesUntilEventsEx(v13, pHandles, 2u, v14, (unsigned int)lpdwindex, v30);
      if ( v15 )
      {
        Error = -2147467259;
        if ( v15 == 258 )
          Error = -2147417825;
      }
      else
      {
        Error = 0;
      }
    }
    else
    {
      dwindex[0] = 0;
      v16 = CoWaitForMultipleHandles(0, v14, 2u, pHandles, dwindex);
      Error = v16;
      if ( v16 == -2147417835 )
      {
        Error = -2147417825;
      }
      else if ( v16 >= 0 )
      {
        if ( dwindex[0] == 1 )
          v16 = -2147467259;
        Error = v16;
      }
    }
    v13 = (HWND)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      LODWORD(lpdwindex) = Error;
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        22,
        WPP_cc4239f610b1355862d418c222e868a6_Traceguids,
        this,
        lpdwindex);
      v13 = (HWND)WPP_GLOBAL_Control;
    }
    if ( Error != -2147417825 )
    {
LABEL_47:
      if ( Error < 0 )
        goto LABEL_69;
      *(_QWORD *)dwindex = 0;
      v17 = v32;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(dwindex);
      Error = CSharingRequestPriv::ValidateAndGetSharingContent(
                v17,
                (struct Windows::ApplicationModel::DataTransfer::IDataPackage **)dwindex);
      if ( Error < 0 )
        goto LABEL_63;
      if ( !(unsigned int)EdpGetIsManaged() )
        goto LABEL_62;
      v37 = 0;
      v18 = *(_QWORD *)dwindex;
      v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)dwindex + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      Error = v19(v18, &v37);
      if ( Error >= 0 )
      {
        pHandles[0] = 0;
        Error = Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet>::As<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet3>(
                  &v37,
                  pHandles);
        if ( Error >= 0 )
        {
          v34 = 0;
          if ( (int)Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackage>::As<IDataPackagePriv>(
                      dwindex,
                      &v34) >= 0 )
          {
            v36 = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v36,
              0);
            if ( (int)EdpGetAppLockerUniqueAppIdentifier(*((unsigned int *)this + 3), &v36) >= 0 )
              (*(void (__fastcall **)(CSharingRequestPriv *, void *))(*(_QWORD *)v34 + 104LL))(v34, v36);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
          }
          v38 = 0;
          Error = EdpGetContextForProcess(*((unsigned int *)this + 3), &v38);
          if ( Error >= 0 && *(_QWORD *)(v38 + 8) )
          {
            v20 = pHandles[0];
            v21 = *(__int64 (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)pHandles[0] + 56LL);
            v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v39, v38 + 8);
            Error = v21(v20, *(_QWORD *)(v22 + 24));
          }
          wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&v38);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(pHandles);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      if ( Error < 0 )
      {
LABEL_63:
        pHandles[0] = 0;
        v23 = WindowsDuplicateString(*((HSTRING *)v32 + 5), (HSTRING *)pHandles);
        Windows::Internal::String::FreeAndAssignOnSuccess(v23, (HSTRING)pHandles[0], (HSTRING *)this + 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          LODWORD(lpdwindex) = Error;
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            24,
            WPP_cc4239f610b1355862d418c222e868a6_Traceguids,
            this,
            lpdwindex);
        }
      }
      else
      {
LABEL_62:
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(dwindex);
        *a3 = *(struct Windows::ApplicationModel::DataTransfer::IDataPackage **)dwindex;
        Error = 0;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(dwindex);
      goto LABEL_68;
    }
    Error = -2144927166;
    if ( v13 != (HWND)&WPP_GLOBAL_Control && ((_BYTE)v13[17] & 1) != 0 && *((_BYTE *)v13 + 65) >= 2u )
    {
      LODWORD(lpdwindex) = -2144927166;
      WPP_SF_qd(*((_QWORD *)v13 + 7), 23, WPP_cc4239f610b1355862d418c222e868a6_Traceguids, this, lpdwindex);
LABEL_68:
      v13 = (HWND)WPP_GLOBAL_Control;
    }
  }
LABEL_69:
  v24 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v13 = (HWND)WPP_GLOBAL_Control;
  }
LABEL_73:
  if ( Error == -2147418110 )
  {
    if ( v13 != (HWND)&WPP_GLOBAL_Control && ((_BYTE)v13[17] & 1) != 0 && *((_BYTE *)v13 + 65) >= 2u )
      WPP_SF_qdd(*((_QWORD *)v13 + 7), 25, v8, this, -2147418110, *((_DWORD *)this + 2));
    v25 = *((_QWORD *)this + 4);
    v26 = *((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v25;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    wil::com_ptr_t<IAgileReference,wil::err_returncode_policy>::reset((char *)this + 32);
    v13 = (HWND)WPP_GLOBAL_Control;
  }
  if ( v13 != (HWND)&WPP_GLOBAL_Control && ((_BYTE)v13[17] & 1) != 0 && *((_BYTE *)v13 + 65) >= 4u )
    WPP_SF_qdd(*((_QWORD *)v13 + 7), 26, v8, this, Error, *((_DWORD *)this + 2));
  v27 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v27 + 2) + 16LL))((__int64)v27 + 16);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800143f4  mov     [rsp-8+arg_18], rbx
0x1800143f9  push    rbp
0x1800143fa  push    rsi
0x1800143fb  push    rdi
0x1800143fc  push    r12
0x1800143fe  push    r13
0x180014400  push    r14
0x180014402  push    r15
0x180014404  lea     rbp, [rsp-27h]
0x180014409  sub     rsp, 0B0h
0x180014410  mov     rax, cs:__security_cookie
0x180014417  xor     rax, rsp
0x18001441a  mov     [rbp+57h+var_40], rax
0x18001441e  mov     r12, r8
0x180014421  mov     r15, rdx
0x180014424  mov     rsi, rcx
0x180014427  xor     r13d, r13d
0x18001442a  mov     [r8], r13
0x18001442d  mov     [rbp+57h+var_A8], r13
0x180014431  mov     rbx, [rcx+18h]
0x180014435  lea     rcx, [rbp+57h+var_A8]
0x180014439  call    ?InternalRelease@?$ComPtr@VCSharingRequestPriv@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSharingRequestPriv>::InternalRelease(void)
0x18001443e  mov     [rbp+57h+var_A8], r13
0x180014442  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014449  lea     ecx, [r13+58h]; unsigned __int64
0x18001444d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014452  lea     r14, WPP_GLOBAL_Control
0x180014459  test    rax, rax
0x18001445c  jnz     short loc_180014468
0x18001445e  mov     ebx, 8007000Eh
0x180014463  jmp     loc_180014907
0x180014468  mov     rcx, rax; this
0x18001446b  call    ??0CSharingRequestPriv@@QEAA@XZ; CSharingRequestPriv::CSharingRequestPriv(void)
0x180014470  mov     r14, rax
0x180014473  mov     [rbp+57h+var_98], rax
0x180014477  mov     [rbp+57h+pHandles], r13
0x18001447b  lea     rcx, [rax+48h]
0x18001447f  mov     rdx, rbx
0x180014482  call    ??4?$ComPtr@UISharePlatformHost@@@WRL@Microsoft@@QEAAAEAV012@PEAUISharePlatformHost@@@Z; Microsoft::WRL::ComPtr<ISharePlatformHost>::operator=(ISharePlatformHost *)
0x180014487  xor     r9d, r9d; lpName
0x18001448a  xor     r8d, r8d; bInitialState
0x18001448d  lea     edx, [r9+1]; bManualReset
0x180014491  xor     ecx, ecx; lpEventAttributes
0x180014493  call    cs:__imp_CreateEventW
0x180014499  mov     rbx, rax
0x18001449c  lea     rcx, [r14+30h]
0x1800144a0  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800144a5  mov     [r14+30h], rbx
0x1800144a9  lea     rax, [rbx+1]
0x1800144ad  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800144b3  jnz     short loc_1800144C0
0x1800144b5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800144ba  mov     ebx, eax
0x1800144bc  test    eax, eax
0x1800144be  js      short loc_1800144DD
0x1800144c0  test    r14, r14
0x1800144c3  jz      short loc_1800144D6
0x1800144c5  lea     rcx, [r14+10h]
0x1800144c9  mov     rax, [rcx]
0x1800144cc  mov     rax, [rax+8]
0x1800144d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144d5  nop
0x1800144d6  mov     [rbp+57h+var_A8], r14
0x1800144da  mov     ebx, r13d
0x1800144dd  lea     rcx, [rbp+57h+var_98]
0x1800144e1  lea     rdi, [rbp+57h+pHandles]
0x1800144e5  call    ?InternalRelease@?$ComPtr@VCSharingRequestPriv@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSharingRequestPriv>::InternalRelease(void)
0x1800144ea  mov     rcx, rdi
0x1800144ed  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x1800144f2  test    ebx, ebx
0x1800144f4  js      loc_180014900
0x1800144fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180014501  lea     r14, WPP_GLOBAL_Control
0x180014508  cmp     rcx, r14
0x18001450b  jz      short loc_180014531
0x18001450d  test    byte ptr [rcx+44h], 1
0x180014511  jz      short loc_180014531
0x180014513  cmp     byte ptr [rcx+41h], 4
0x180014517  jb      short loc_180014531
0x180014519  mov     edx, 14h
0x18001451e  mov     r9, rsi
0x180014521  lea     r8, WPP_cc4239f610b1355862d418c222e868a6_Traceguids
0x180014528  mov     rcx, [rcx+38h]
0x18001452c  call    WPP_SF_q
0x180014531  mov     [rbp+57h+var_A0], r13
0x180014535  lea     rcx, [rbp+57h+var_A0]
0x180014539  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001453e  mov     rcx, [rsi+20h]
0x180014542  test    rcx, rcx
0x180014545  jz      short loc_180014562
0x180014547  mov     rax, [rcx]
0x18001454a  lea     r8, [rbp+57h+var_A0]
0x18001454e  lea     rdx, _GUID_252e6571_8157_4809_8e2a_94aaa9e5de60
0x180014555  mov     rax, [rax+18h]
0x180014559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001455e  mov     ebx, eax
0x180014560  jmp     short loc_180014569
0x180014562  mov     [rbp+57h+var_A0], r13
0x180014566  mov     ebx, r13d
0x180014569  test    ebx, ebx
0x18001456b  js      short loc_1800145AB
0x18001456d  mov     edx, 64h ; 'd'; DueTime
0x180014572  lea     rcx, [rbp+57h+pHandles]; this
0x180014576  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18001457b  nop
0x18001457c  mov     rcx, [rbp+57h+var_A0]
0x180014580  mov     r8, [rbp+57h+var_A8]
0x180014584  mov     r9, [rcx]
0x180014587  lea     rax, [r8+10h]
0x18001458b  neg     r8
0x18001458e  sbb     r8, r8
0x180014591  and     r8, rax
0x180014594  mov     rdx, r15
0x180014597  mov     rax, [r9+30h]
0x18001459b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145a0  mov     ebx, eax
0x1800145a2  lea     rcx, [rbp+57h+pHandles]; this
0x1800145a6  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1800145ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145b2  cmp     rcx, r14
0x1800145b5  jz      short loc_1800145E6
0x1800145b7  test    byte ptr [rcx+44h], 1
0x1800145bb  jz      short loc_1800145E6
0x1800145bd  cmp     byte ptr [rcx+41h], 4
0x1800145c1  jb      short loc_1800145E6
0x1800145c3  mov     edx, 15h
0x1800145c8  mov     dword ptr [rsp+0E0h+lpdwindex], ebx; unsigned int
0x1800145cc  mov     r9, rsi
0x1800145cf  lea     r8, WPP_cc4239f610b1355862d418c222e868a6_Traceguids
0x1800145d6  mov     rcx, [rcx+38h]
0x1800145da  call    WPP_SF_qd
0x1800145df  mov     rcx, cs:WPP_GLOBAL_Control; HWND
0x1800145e6  mov     edi, 8001011Fh
0x1800145eb  test    ebx, ebx
0x1800145ed  jns     short loc_1800145FF
0x1800145ef  cmp     ebx, edi
0x1800145f1  jz      short loc_1800145FF
0x1800145f3  cmp     ebx, 80010002h
0x1800145f9  jnz     loc_1800148DB
0x1800145ff  mov     rax, [rbp+57h+var_A8]
0x180014603  mov     rdx, [rax+30h]
0x180014607  test    rdx, rdx
0x18001460a  jz      loc_180014709
0x180014610  mov     [rbp+57h+pHandles], rdx
0x180014614  mov     rax, [rsi+30h]
0x180014618  mov     [rbp+57h+var_88], rax
0x18001461c  mov     edx, [rsi+8]; dwTimeout
0x18001461f  mov     r8d, 2; unsigned int
0x180014625  cmp     [rsi+38h], r13b
0x180014629  jz      short loc_18001464F
0x18001462b  mov     r9d, edx; unsigned int
0x18001462e  lea     rdx, [rbp+57h+pHandles]; void **
0x180014632  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x180014637  test    eax, eax
0x180014639  jnz     short loc_180014640
0x18001463b  mov     ebx, r13d
0x18001463e  jmp     short loc_180014687
0x180014640  mov     ebx, 80004005h
0x180014645  cmp     eax, 102h
0x18001464a  cmovz   ebx, edi
0x18001464d  jmp     short loc_180014687
0x18001464f  mov     [rbp+57h+dwindex], r13d
0x180014653  lea     rax, [rbp+57h+dwindex]
0x180014657  mov     [rsp+0E0h+lpdwindex], rax; lpdwindex
0x18001465c  lea     r9, [rbp+57h+pHandles]; pHandles
0x180014660  xor     ecx, ecx; dwFlags
0x180014662  call    cs:__imp_CoWaitForMultipleHandles
0x180014668  mov     ebx, eax
0x18001466a  cmp     eax, 80010115h
0x18001466f  jnz     short loc_180014675
0x180014671  mov     ebx, edi
0x180014673  jmp     short loc_180014687
0x180014675  test    eax, eax
0x180014677  js      short loc_180014687
0x180014679  mov     ebx, 80004005h
0x18001467e  cmp     [rbp+57h+dwindex], 1
0x180014682  cmovz   eax, ebx
0x180014685  mov     ebx, eax
0x180014687  mov     rcx, cs:WPP_GLOBAL_Control
0x18001468e  cmp     rcx, r14
0x180014691  jz      short loc_1800146C2
0x180014693  test    byte ptr [rcx+44h], 1
0x180014697  jz      short loc_1800146C2
0x180014699  cmp     byte ptr [rcx+41h], 4
0x18001469d  jb      short loc_1800146C2
0x18001469f  mov     edx, 16h
0x1800146a4  mov     dword ptr [rsp+0E0h+lpdwindex], ebx
0x1800146a8  mov     r9, rsi
0x1800146ab  lea     r8, WPP_cc4239f610b1355862d418c222e868a6_Traceguids
0x1800146b2  mov     rcx, [rcx+38h]
0x1800146b6  call    WPP_SF_qd
0x1800146bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146c2  cmp     ebx, edi
0x1800146c4  jnz     short loc_180014709
0x1800146c6  mov     ebx, 80270242h
0x1800146cb  cmp     rcx, r14
0x1800146ce  jz      loc_1800148DB
0x1800146d4  test    byte ptr [rcx+44h], 1
0x1800146d8  jz      loc_1800148DB
0x1800146de  cmp     byte ptr [rcx+41h], 2
0x1800146e2  jb      loc_1800148DB
0x1800146e8  mov     edx, 17h
0x1800146ed  mov     dword ptr [rsp+0E0h+lpdwindex], ebx
0x1800146f1  mov     r9, rsi
0x1800146f4  lea     r8, WPP_cc4239f610b1355862d418c222e868a6_Traceguids
0x1800146fb  mov     rcx, [rcx+38h]
0x1800146ff  call    WPP_SF_qd
0x180014704  jmp     loc_1800148D4
0x180014709  test    ebx, ebx
0x18001470b  js      loc_1800148DB
0x180014711  mov     qword ptr [rbp+57h+dwindex], r13
0x180014715  mov     rbx, [rbp+57h+var_A8]
0x180014719  lea     rcx, [rbp+57h+dwindex]
0x18001471d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014722  lea     rdx, [rbp+57h+dwindex]; struct Windows::ApplicationModel::DataTransfer::IDataPackage **
0x180014726  mov     rcx, rbx; this
0x180014729  call    ?ValidateAndGetSharingContent@CSharingRequestPriv@@QEAAJPEAPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@@Z; CSharingRequestPriv::ValidateAndGetSharingContent(Windows::ApplicationModel::DataTransfer::IDataPackage * *)
0x18001472e  mov     ebx, eax
0x180014730  test    eax, eax
0x180014732  js      loc_180014871
0x180014738  call    cs:__imp_EdpGetIsManaged
0x18001473e  test    eax, eax
0x180014740  jz      loc_18001485B
0x180014746  mov     [rbp+57h+var_70], r13
0x18001474a  mov     rdi, qword ptr [rbp+57h+dwindex]
0x18001474e  mov     rax, [rdi]
0x180014751  mov     rbx, [rax+38h]
0x180014755  lea     rcx, [rbp+57h+var_70]
0x180014759  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001475e  lea     rdx, [rbp+57h+var_70]
0x180014762  mov     rcx, rdi
0x180014765  mov     rax, rbx
0x180014768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001476d  mov     ebx, eax
0x18001476f  test    eax, eax
0x180014771  js      loc_18001484E
0x180014777  mov     [rbp+57h+pHandles], r13
0x18001477b  lea     rdx, [rbp+57h+pHandles]
0x18001477f  lea     rcx, [rbp+57h+var_70]
0x180014783  call    ??$As@UIDataPackagePropertySet3@DataTransfer@ApplicationModel@Windows@@@?$ComPtr@UIDataPackagePropertySet@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDataPackagePropertySet3@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet>::As<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet3>>)
0x180014788  mov     ebx, eax
0x18001478a  test    eax, eax
0x18001478c  js      loc_180014844
0x180014792  mov     [rbp+57h+var_98], r13
0x180014796  lea     rdx, [rbp+57h+var_98]
0x18001479a  lea     rcx, [rbp+57h+dwindex]
0x18001479e  call    ??$As@UIDataPackagePriv@@@?$ComPtr@UIDataPackage@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDataPackagePriv@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackage>::As<IDataPackagePriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDataPackagePriv>>)
0x1800147a3  test    eax, eax
0x1800147a5  js      short loc_1800147E6
0x1800147a7  mov     [rbp+57h+var_78], r13
0x1800147ab  xor     edx, edx
0x1800147ad  lea     rcx, [rbp+57h+var_78]
0x1800147b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800147b6  lea     rdx, [rbp+57h+var_78]
0x1800147ba  mov     ecx, [rsi+0Ch]
0x1800147bd  call    cs:__imp_EdpGetAppLockerUniqueAppIdentifier
0x1800147c3  test    eax, eax
0x1800147c5  js      short loc_1800147DC
0x1800147c7  mov     rcx, [rbp+57h+var_98]
0x1800147cb  mov     rax, [rcx]
0x1800147ce  mov     rdx, [rbp+57h+var_78]
0x1800147d2  mov     rax, [rax+68h]
0x1800147d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147db  nop
0x1800147dc  lea     rcx, [rbp+57h+var_78]
0x1800147e0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800147e5  nop
0x1800147e6  mov     [rbp+57h+var_68], r13
0x1800147ea  lea     rdx, [rbp+57h+var_68]
0x1800147ee  mov     ecx, [rsi+0Ch]
0x1800147f1  call    cs:__imp_EdpGetContextForProcess
0x1800147f7  mov     ebx, eax
0x1800147f9  test    eax, eax
0x1800147fb  js      short loc_180014830
0x1800147fd  mov     rdx, [rbp+57h+var_68]
0x180014801  add     rdx, 8
0x180014805  cmp     [rdx], r13
0x180014808  jz      short loc_180014830
0x18001480a  mov     rdi, [rbp+57h+pHandles]
0x18001480e  mov     rax, [rdi]
0x180014811  mov     rbx, [rax+38h]
0x180014815  lea     rcx, [rbp+57h+var_60]
0x180014819  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001481e  nop
0x18001481f  mov     rdx, [rax+18h]
0x180014823  mov     rcx, rdi
0x180014826  mov     rax, rbx
0x180014829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001482e  mov     ebx, eax
0x180014830  lea     rcx, [rbp+57h+var_68]
0x180014834  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x180014839  nop
0x18001483a  lea     rcx, [rbp+57h+var_98]
0x18001483e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014843  nop
0x180014844  lea     rcx, [rbp+57h+pHandles]
0x180014848  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001484d  nop
0x18001484e  lea     rcx, [rbp+57h+var_70]
0x180014852  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
