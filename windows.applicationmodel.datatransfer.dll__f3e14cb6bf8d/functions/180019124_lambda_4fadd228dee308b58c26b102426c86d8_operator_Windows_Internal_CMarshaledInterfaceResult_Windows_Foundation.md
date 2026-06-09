# _lambda_4fadd228dee308b58c26b102426c86d8_::operator()(Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *>> &)

- ea: `0x180019124`
- end: `0x1800195ee`
- name: `??R_lambda_4fadd228dee308b58c26b102426c86d8_@@QEBAJAEAV?$CMarshaledInterfaceResult@U?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Internal@Windows@@@Z`
- size: `1226`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800492d0`

## callees

- `0x180002ad0`
- `0x180005504`
- `0x180006fcc`
- `0x180007028`
- `0x180007974`
- `0x1800143c4`
- `0x180019124`
- `0x180043b6c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001927d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001927d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001923b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001926c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001931d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800194b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800194be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001923b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001926c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001931d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800194b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800194be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019355`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800191ac`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800191ac`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180019563`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180019563`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall _lambda_4fadd228dee308b58c26b102426c86d8_::operator()(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  HRESULT ActivationFactory; // edi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  HSTRING v10; // rbx
  HSTRING Reserved1; // rdi
  char *v12; // rax
  char *v13; // rbx
  _QWORD *v14; // rsi
  _QWORD *v15; // rdi
  __int64 v16; // rsi
  HRESULT v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rsi
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rdi
  __int64 *v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // rcx
  _QWORD *v35; // rcx
  __int64 v36; // rcx
  _QWORD *v38; // [rsp+30h] [rbp-69h] BYREF
  __int64 v39; // [rsp+38h] [rbp-61h] BYREF
  __int64 v40; // [rsp+40h] [rbp-59h] BYREF
  __int64 v41; // [rsp+48h] [rbp-51h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-49h] BYREF
  __int64 v43; // [rsp+58h] [rbp-41h] BYREF
  HSTRING v44; // [rsp+60h] [rbp-39h] BYREF
  __int64 v45; // [rsp+68h] [rbp-31h] BYREF
  __int64 v46; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v47[2]; // [rsp+78h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-11h] BYREF
  HSTRING string; // [rsp+A0h] [rbp+7h] BYREF
  HSTRING_HEADER v50; // [rsp+A8h] [rbp+Fh] BYREF
  HSTRING v51; // [rsp+C0h] [rbp+27h] BYREF

  v39 = 0;
  v38 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Storage.StorageFile", 0x1Bu, &hstringHeader, &string);
  if ( v4 < 0 )
    goto LABEL_57;
  ActivationFactory = RoGetActivationFactory(string, &GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f, &v38);
  string = 0;
  if ( ActivationFactory < 0 )
    goto LABEL_51;
  v47[0] = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(*(_QWORD *)a1 + 152LL) + 152LL))(
                        *(_QWORD *)(*(_QWORD *)a1 + 152LL),
                        v47);
  if ( ActivationFactory >= 0 )
  {
    v46 = 0;
    ActivationFactory = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *>>(
                          v47[0],
                          &v46);
    if ( ActivationFactory < 0 )
    {
LABEL_38:
      v29 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      goto LABEL_40;
    }
    v45 = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v46 + 48LL))(v46, 0, &v45);
    if ( ActivationFactory < 0 )
    {
LABEL_36:
      v28 = v45;
      if ( v45 )
      {
        v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      goto LABEL_38;
    }
    v44 = 0;
    v8 = v45;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 88LL);
    WindowsDeleteString(0);
    v44 = 0;
    ActivationFactory = v9(v8, &v44);
    if ( ActivationFactory < 0 )
    {
LABEL_35:
      WindowsDeleteString(v44);
      goto LABEL_36;
    }
    hstringHeader.Reserved.Reserved1 = 0;
    hstringHeader.Reserved.Reserved2[8] = 0;
    v10 = v44;
    WindowsDeleteString(0);
    hstringHeader.Reserved.Reserved1 = 0;
    ActivationFactory = WindowsDuplicateString(v10, (HSTRING *)&hstringHeader);
    if ( ActivationFactory < 0 )
    {
LABEL_34:
      WindowsDeleteString((HSTRING)hstringHeader.Reserved.Reserved1);
      goto LABEL_35;
    }
    Reserved1 = (HSTRING)hstringHeader.Reserved.Reserved1;
    hstringHeader.Reserved.Reserved1 = 0;
    hstringHeader.Reserved.Reserved2[8] = 1;
    v12 = (char *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
    v13 = v12;
    if ( v12 )
    {
      v14 = v12 + 8;
      Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v12 + 8));
      *((_DWORD *)v13 + 15) = 1;
      *(_QWORD *)v13 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>>::`vftable'{for `Windows::Storage::IStreamedFileDataRequestedHandler'};
      *v14 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Storage::IStreamedFileDataRequestedHandler::*)(Windows::Storage::Streams::IOutputStream *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>,_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_,-1,Windows::Storage::Streams::IOutputStream *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *((_QWORD *)v13 + 8) = Reserved1;
      v13[72] = 0;
      *(_QWORD *)v13 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Storage::IStreamedFileDataRequestedHandler::*)(Windows::Storage::Streams::IOutputStream *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>,_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_,-1,Windows::Storage::Streams::IOutputStream *>::`vftable'{for `Windows::Storage::IStreamedFileDataRequestedHandler'};
      *v14 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Storage::IStreamedFileDataRequestedHandler::*)(Windows::Storage::Streams::IOutputStream *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>,_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_,-1,Windows::Storage::Streams::IOutputStream *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      Reserved1 = 0;
    }
    else
    {
      v13 = 0;
    }
    v47[1] = v13;
    WindowsDeleteString(Reserved1);
    if ( !v13 )
    {
      ActivationFactory = -2147024882;
LABEL_32:
      if ( v13 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 16LL))(v13);
      goto LABEL_34;
    }
    v43 = 0;
    v15 = v38;
    v16 = *v38;
    v51 = 0;
    v17 = WindowsCreateStringReference(L"RestrictedFile.txt", 0x12u, &v50, &v51);
    if ( v17 >= 0 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, char *, _QWORD, __int64 *))(v16 + 64))(
                            v15,
                            v51,
                            v13,
                            0,
                            &v43);
      if ( ActivationFactory >= 0 )
      {
        v42 = 0;
        ActivationFactory = BlockOnCompletionAndGetResults<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile>(
                              v43,
                              &v42);
        if ( ActivationFactory >= 0 )
        {
          v40 = 0;
          ActivationFactory = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::Vector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::IStorageItem *>>>(
                                v20,
                                &v40);
          if ( ActivationFactory >= 0 )
          {
            v41 = 0;
            ActivationFactory = (**v42)(v42, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v41);
            if ( ActivationFactory >= 0 )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 104LL))(v40, v41);
              if ( ActivationFactory >= 0 )
              {
                v21 = v40;
                v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 64LL);
                v23 = v39;
                if ( v39 )
                {
                  v39 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                }
                ActivationFactory = v22(v21, &v39);
              }
            }
            v24 = v41;
            if ( v41 )
            {
              v41 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            }
          }
          v25 = v40;
          if ( v40 )
          {
            v40 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
        }
        v26 = v42;
        if ( v42 )
        {
          v42 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v26)[2])(v26);
        }
      }
      v27 = v43;
      if ( v43 )
      {
        v43 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      goto LABEL_32;
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
LABEL_57:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x1800195EDLL);
  }
LABEL_40:
  v30 = v47[0];
  if ( v47[0] )
  {
    v47[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  if ( ActivationFactory >= 0 )
  {
    v31 = v39;
    v32 = (__int64 *)(a2 + 16);
    v33 = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 0;
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v34 = *v32;
    if ( v31 )
    {
      if ( v34 )
      {
        *v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      ActivationFactory = RoGetAgileReference(0, &GUID_85575a41_06cb_58d0_b98a_7c8f06e6e9d7, v31, a2 + 16);
    }
    else
    {
      ActivationFactory = 0;
      *v32 = 0;
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
  }
LABEL_51:
  v35 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
  }
  v36 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180019124  mov     [rsp-8+arg_10], rbx
0x180019129  push    rbp
0x18001912a  push    rsi
0x18001912b  push    rdi
0x18001912c  push    r14
0x18001912e  push    r15
0x180019130  lea     rbp, [rsp-37h]
0x180019135  sub     rsp, 0D0h
0x18001913c  mov     rax, cs:__security_cookie
0x180019143  xor     rax, rsp
0x180019146  mov     [rbp+57h+var_28], rax
0x18001914a  mov     r14, rdx
0x18001914d  mov     rsi, rcx
0x180019150  xor     r15d, r15d
0x180019153  mov     [rbp+57h+var_B8], r15
0x180019157  mov     [rbp+57h+var_C0], r15
0x18001915b  mov     [rbp+57h+string], r15
0x18001915f  lea     r9, [rbp+57h+string]; string
0x180019163  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180019167  lea     edx, [r15+1Bh]; length
0x18001916b  lea     rcx, ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x180019172  call    cs:__imp_WindowsCreateStringReference
0x180019178  test    eax, eax
0x18001917a  js      loc_1800195E6
0x180019180  mov     rbx, [rbp+57h+string]
0x180019184  mov     rcx, [rbp+57h+var_C0]
0x180019188  test    rcx, rcx
0x18001918b  jz      short loc_18001919E
0x18001918d  mov     [rbp+57h+var_C0], r15
0x180019191  mov     rax, [rcx]
0x180019194  mov     rax, [rax+10h]
0x180019198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001919d  nop
0x18001919e  lea     r8, [rbp+57h+var_C0]
0x1800191a2  lea     rdx, _GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f
0x1800191a9  mov     rcx, rbx
0x1800191ac  call    cs:__imp_RoGetActivationFactory
0x1800191b2  mov     edi, eax
0x1800191b4  mov     [rbp+57h+string], r15
0x1800191b8  test    eax, eax
0x1800191ba  js      loc_180019585
0x1800191c0  mov     [rbp+57h+var_78], r15
0x1800191c4  mov     rax, [rsi]
0x1800191c7  mov     rcx, [rax+98h]
0x1800191ce  mov     rax, [rcx]
0x1800191d1  lea     rdx, [rbp+57h+var_78]
0x1800191d5  mov     rax, [rax+98h]
0x1800191dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191e1  mov     edi, eax
0x1800191e3  test    eax, eax
0x1800191e5  js      loc_1800194F9
0x1800191eb  mov     [rbp+57h+var_80], r15
0x1800191ef  lea     rdx, [rbp+57h+var_80]
0x1800191f3  mov     rcx, [rbp+57h+var_78]
0x1800191f7  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@23@U?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@U?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *>>>,tagCOWAIT_FLAGS,void *)
0x1800191fc  mov     edi, eax
0x1800191fe  test    eax, eax
0x180019200  js      loc_1800194DF
0x180019206  mov     [rbp+57h+var_88], r15
0x18001920a  mov     rcx, [rbp+57h+var_80]
0x18001920e  mov     rax, [rcx]
0x180019211  lea     r8, [rbp+57h+var_88]
0x180019215  xor     edx, edx
0x180019217  mov     rax, [rax+30h]
0x18001921b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019220  mov     edi, eax
0x180019222  test    eax, eax
0x180019224  js      loc_1800194C5
0x18001922a  mov     [rbp+57h+var_90], r15
0x18001922e  mov     rdi, [rbp+57h+var_88]
0x180019232  mov     rax, [rdi]
0x180019235  mov     rbx, [rax+58h]
0x180019239  xor     ecx, ecx; string
0x18001923b  call    cs:__imp_WindowsDeleteString
0x180019241  mov     [rbp+57h+var_90], r15
0x180019245  lea     rdx, [rbp+57h+var_90]
0x180019249  mov     rcx, rdi
0x18001924c  mov     rax, rbx
0x18001924f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019254  mov     edi, eax
0x180019256  test    eax, eax
0x180019258  js      loc_1800194BA
0x18001925e  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r15
0x180019262  mov     byte ptr [rbp+57h+hstringHeader.Reserved+8], r15b
0x180019266  mov     rbx, [rbp+57h+var_90]
0x18001926a  xor     ecx, ecx; string
0x18001926c  call    cs:__imp_WindowsDeleteString
0x180019272  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r15
0x180019276  lea     rdx, [rbp+57h+hstringHeader]; newString
0x18001927a  mov     rcx, rbx; string
0x18001927d  call    cs:__imp_WindowsDuplicateString
0x180019283  mov     edi, eax
0x180019285  test    eax, eax
0x180019287  js      loc_1800194AF
0x18001928d  mov     rdi, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180019291  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r15
0x180019295  mov     byte ptr [rbp+57h+hstringHeader.Reserved+8], 1
0x180019299  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800192a0  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800192a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800192aa  mov     rbx, rax
0x1800192ad  test    rax, rax
0x1800192b0  jz      short loc_180019313
0x1800192b2  lea     rsi, [rax+8]
0x1800192b6  mov     rcx, rsi; this
0x1800192b9  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800192be  mov     dword ptr [rbx+3Ch], 1
0x1800192c5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStreamedFileDataRequestedHandler@Storage@Windows@@VFtmBase@23@@23@@WRL@Microsoft@@6BIStreamedFileDataRequestedHandler@Storage@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>>::`vftable'{for `Windows::Storage::IStreamedFileDataRequestedHandler'}
0x1800192cc  mov     [rbx], rax
0x1800192cf  lea     rax, ??_7?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStreamedFileDataRequestedHandler@Storage@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_@@$0?0PEAUIOutputStream@Streams@Storage@Windows@@@?$DelegateArgTraits@P8IStreamedFileDataRequestedHandler@Storage@Windows@@EAAJPEAUIOutputStream@Streams@23@@Z@Details@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@234@@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Storage::IStreamedFileDataRequestedHandler::*)(Windows::Storage::Streams::IOutputStream *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>,_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_,-1,Windows::Storage::Streams::IOutputStream *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800192d6  mov     [rsi], rax
0x1800192d9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800192e0  test    rcx, rcx
0x1800192e3  jz      short loc_1800192F2
0x1800192e5  mov     rax, [rcx]
0x1800192e8  mov     rax, [rax+8]
0x1800192ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192f1  nop
0x1800192f2  mov     [rbx+40h], rdi
0x1800192f6  mov     [rbx+48h], r15b
0x1800192fa  lea     rax, ??_7?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStreamedFileDataRequestedHandler@Storage@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_@@$0?0PEAUIOutputStream@Streams@Storage@Windows@@@?$DelegateArgTraits@P8IStreamedFileDataRequestedHandler@Storage@Windows@@EAAJPEAUIOutputStream@Streams@23@@Z@Details@WRL@Microsoft@@6BIStreamedFileDataRequestedHandler@Storage@Windows@@@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Storage::IStreamedFileDataRequestedHandler::*)(Windows::Storage::Streams::IOutputStream *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>,_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_,-1,Windows::Storage::Streams::IOutputStream *>::`vftable'{for `Windows::Storage::IStreamedFileDataRequestedHandler'}
0x180019301  mov     [rbx], rax
0x180019304  lea     rax, ??_7?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStreamedFileDataRequestedHandler@Storage@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_@@$0?0PEAUIOutputStream@Streams@Storage@Windows@@@?$DelegateArgTraits@P8IStreamedFileDataRequestedHandler@Storage@Windows@@EAAJPEAUIOutputStream@Streams@23@@Z@Details@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@234@@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Storage::IStreamedFileDataRequestedHandler::*)(Windows::Storage::Streams::IOutputStream *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>,_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_,-1,Windows::Storage::Streams::IOutputStream *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001930b  mov     [rsi], rax
0x18001930e  mov     rdi, r15
0x180019311  jmp     short loc_180019316
0x180019313  mov     rbx, r15
0x180019316  mov     [rbp+57h+var_70], rbx
0x18001931a  mov     rcx, rdi; string
0x18001931d  call    cs:__imp_WindowsDeleteString
0x180019323  test    rbx, rbx
0x180019326  jnz     short loc_180019332
0x180019328  mov     edi, 8007000Eh
0x18001932d  jmp     loc_18001949A
0x180019332  mov     [rbp+57h+var_98], r15
0x180019336  mov     rdi, [rbp+57h+var_C0]
0x18001933a  mov     rsi, [rdi]
0x18001933d  mov     [rbp+57h+var_30], r15
0x180019341  lea     r9, [rbp+57h+var_30]; string
0x180019345  lea     r8, [rbp+57h+var_48]; hstringHeader
0x180019349  mov     edx, 12h; length
0x18001934e  lea     rcx, aRestrictedfile; "RestrictedFile.txt"
0x180019355  call    cs:__imp_WindowsCreateStringReference
0x18001935b  test    eax, eax
0x18001935d  js      loc_1800195DE
0x180019363  lea     rax, [rbp+57h+var_98]
0x180019367  mov     [rsp+0F0h+var_D0], rax
0x18001936c  xor     r9d, r9d
0x18001936f  mov     r8, rbx
0x180019372  mov     rdx, [rbp+57h+var_30]
0x180019376  mov     rcx, rdi
0x180019379  mov     rax, [rsi+40h]
0x18001937d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019382  mov     edi, eax
0x180019384  test    eax, eax
0x180019386  js      loc_180019480
0x18001938c  mov     [rbp+57h+var_A0], r15
0x180019390  lea     rdx, [rbp+57h+var_A0]
0x180019394  mov     rcx, [rbp+57h+var_98]
0x180019398  call    ??$BlockOnCompletionAndGetResults@PEAVStorageFile@Storage@Windows@@UIStorageFile@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIStorageFile@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile>>,tagCOWAIT_FLAGS,void *)
0x18001939d  mov     edi, eax
0x18001939f  test    eax, eax
0x1800193a1  js      loc_180019466
0x1800193a7  mov     [rbp+57h+var_B0], r15
0x1800193ab  lea     rdx, [rbp+57h+var_B0]
0x1800193af  call    ??$CreateExternalObjectVector@UIStorageItem@Storage@Windows@@V?$Vector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@U?$DefaultVectorOptions@PEAUIStorageItem@Storage@Windows@@@5673@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@U?$DefaultVectorOptions@PEAUIStorageItem@Storage@Windows@@@5673@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::Vector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::IStorageItem *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::IStorageItem *>> * *)
0x1800193b4  mov     edi, eax
0x1800193b6  test    eax, eax
0x1800193b8  js      loc_18001944C
0x1800193be  mov     [rbp+57h+var_A8], r15
0x1800193c2  mov     rcx, [rbp+57h+var_A0]
0x1800193c6  mov     rax, [rcx]
0x1800193c9  lea     r8, [rbp+57h+var_A8]
0x1800193cd  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800193d4  mov     rax, [rax]
0x1800193d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193dc  mov     edi, eax
0x1800193de  test    eax, eax
0x1800193e0  js      short loc_180019432
0x1800193e2  mov     rcx, [rbp+57h+var_B0]
0x1800193e6  mov     rax, [rcx]
0x1800193e9  mov     rdx, [rbp+57h+var_A8]
0x1800193ed  mov     rax, [rax+68h]
0x1800193f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193f6  mov     edi, eax
0x1800193f8  test    eax, eax
0x1800193fa  js      short loc_180019432
0x1800193fc  mov     rdi, [rbp+57h+var_B0]
0x180019400  mov     rax, [rdi]
0x180019403  mov     rsi, [rax+40h]
0x180019407  mov     rcx, [rbp+57h+var_B8]
0x18001940b  test    rcx, rcx
0x18001940e  jz      short loc_180019421
0x180019410  mov     [rbp+57h+var_B8], r15
0x180019414  mov     rdx, [rcx]
0x180019417  mov     rax, [rdx+10h]
0x18001941b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019420  nop
0x180019421  lea     rdx, [rbp+57h+var_B8]
0x180019425  mov     rcx, rdi
0x180019428  mov     rax, rsi
0x18001942b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019430  mov     edi, eax
0x180019432  mov     rcx, [rbp+57h+var_A8]
0x180019436  test    rcx, rcx
0x180019439  jz      short loc_18001944C
0x18001943b  mov     [rbp+57h+var_A8], r15
0x18001943f  mov     rax, [rcx]
0x180019442  mov     rax, [rax+10h]
0x180019446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001944b  nop
0x18001944c  mov     rcx, [rbp+57h+var_B0]
0x180019450  test    rcx, rcx
0x180019453  jz      short loc_180019466
0x180019455  mov     [rbp+57h+var_B0], r15
0x180019459  mov     rax, [rcx]
0x18001945c  mov     rax, [rax+10h]
0x180019460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019465  nop
0x180019466  mov     rcx, [rbp+57h+var_A0]
0x18001946a  test    rcx, rcx
0x18001946d  jz      short loc_180019480
0x18001946f  mov     [rbp+57h+var_A0], r15
0x180019473  mov     rax, [rcx]
0x180019476  mov     rax, [rax+10h]
0x18001947a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001947f  nop
0x180019480  mov     rcx, [rbp+57h+var_98]
0x180019484  test    rcx, rcx
0x180019487  jz      short loc_18001949A
0x180019489  mov     [rbp+57h+var_98], r15
0x18001948d  mov     rax, [rcx]
0x180019490  mov     rax, [rax+10h]
0x180019494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019499  nop
0x18001949a  test    rbx, rbx
0x18001949d  jz      short loc_1800194AF
0x18001949f  mov     rax, [rbx]
0x1800194a2  mov     rcx, rbx
0x1800194a5  mov     rax, [rax+10h]
0x1800194a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194ae  nop
0x1800194af  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]; string
0x1800194b3  call    cs:__imp_WindowsDeleteString
0x1800194b9  nop
0x1800194ba  mov     rcx, [rbp+57h+var_90]; string
0x1800194be  call    cs:__imp_WindowsDeleteString
0x1800194c4  nop
0x1800194c5  mov     rcx, [rbp+57h+var_88]
0x1800194c9  test    rcx, rcx
0x1800194cc  jz      short loc_1800194DF
0x1800194ce  mov     [rbp+57h+var_88], r15
0x1800194d2  mov     rax, [rcx]
0x1800194d5  mov     rax, [rax+10h]
0x1800194d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194de  nop
0x1800194df  mov     rcx, [rbp+57h+var_80]
0x1800194e3  test    rcx, rcx
0x1800194e6  jz      short loc_1800194F9
0x1800194e8  mov     [rbp+57h+var_80], r15
0x1800194ec  mov     rax, [rcx]
0x1800194ef  mov     rax, [rax+10h]
0x1800194f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194f8  nop
0x1800194f9  mov     rcx, [rbp+57h+var_78]
0x1800194fd  test    rcx, rcx
0x180019500  jz      short loc_180019513
0x180019502  mov     [rbp+57h+var_78], r15
0x180019506  mov     rax, [rcx]
0x180019509  mov     rax, [rax+10h]
0x18001950d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019512  nop
0x180019513  test    edi, edi
0x180019515  js      short loc_180019585
0x180019517  mov     rdi, [rbp+57h+var_B8]
0x18001951b  lea     rbx, [r14+10h]
0x18001951f  mov     rcx, [rbx]
0x180019522  mov     [rbx], r15
0x180019525  test    rcx, rcx
0x180019528  jz      short loc_180019537
0x18001952a  mov     rax, [rcx]
0x18001952d  mov     rax, [rax+10h]
0x180019531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019536  nop
0x180019537  mov     rcx, [rbx]
0x18001953a  test    rdi, rdi
0x18001953d  jz      short loc_18001956D
0x18001953f  test    rcx, rcx
0x180019542  jz      short loc_180019554
0x180019544  mov     [rbx], r15
0x180019547  mov     rax, [rcx]
0x18001954a  mov     rax, [rax+10h]
0x18001954e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019553  nop
0x180019554  mov     r9, rbx
0x180019557  mov     r8, rdi
0x18001955a  lea     rdx, _GUID_85575a41_06cb_58d0_b98a_7c8f06e6e9d7
0x180019561  xor     ecx, ecx
0x180019563  call    cs:__imp_RoGetAgileReference
0x180019569  mov     edi, eax
  ... truncated ...
```
