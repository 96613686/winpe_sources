# _GetManagedUrls(Windows::Internal::StateRepository::IApplicationExtension *,Windows::Foundation::Collections::IVector<Windows::Foundation::Uri *> *)

- ea: `0x180065764`
- end: `0x180065dae`
- name: `?_GetManagedUrls@@YAJPEAUIApplicationExtension@StateRepository@Internal@Windows@@PEAU?$IVector@PEAVUri@Foundation@Windows@@@Collections@Foundation@4@@Z`
- size: `1610`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011400`
- `0x18009e3d0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x1800175c0`
- `0x180018720`
- `0x180019be8`
- `0x180019f0c`
- `0x180025c10`
- `0x1800425b0`
- `0x1800439d0`
- `0x180045660`
- `0x18004fdbc`
- `0x18005e730`
- `0x180065764`
- `0x18008e690`
- `0x18009dff8`
- `0x18009e05c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006596f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006596f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180065956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180065956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065ac6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065bec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065ac6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065bec`

## string_xrefs

- `0x1800657dd`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180065819`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180065916`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180065b1f`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180065c33`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180065c69`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180065cc9`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180065d22`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180065d75`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x1800657b1`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall _GetManagedUrls(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int WebAccountProviderElementAttributes; // eax
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, struct IInspectable **); // rbx
  _QWORD *v11; // rax
  int v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, HSTRING, struct IInspectable **); // rdi
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // r9
  unsigned int v21; // edi
  int v22; // eax
  int v23; // eax
  int Inspectable; // eax
  int v26; // eax
  int v27; // eax
  int v28; // [rsp+20h] [rbp-69h] BYREF
  __int64 v29; // [rsp+28h] [rbp-61h] BYREF
  __int64 v30; // [rsp+30h] [rbp-59h] BYREF
  HSTRING v31; // [rsp+38h] [rbp-51h] BYREF
  __int64 v32; // [rsp+40h] [rbp-49h] BYREF
  __int64 v33; // [rsp+48h] [rbp-41h] BYREF
  int v34; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-35h] BYREF
  struct IInspectable *v36; // [rsp+58h] [rbp-31h] BYREF
  RoVariant *v37; // [rsp+60h] [rbp-29h] BYREF
  struct IInspectable *v38; // [rsp+68h] [rbp-21h] BYREF
  RoVariant *v39; // [rsp+70h] [rbp-19h] BYREF
  int v40; // [rsp+78h] [rbp-11h]
  _QWORD v41[2]; // [rsp+80h] [rbp-9h] BYREF
  char v42; // [rsp+90h] [rbp+7h]
  RoVariant *v43; // [rsp+98h] [rbp+Fh] BYREF
  unsigned int v44; // [rsp+A0h] [rbp+17h]
  HSTRING string; // [rsp+A8h] [rbp+1Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v28 = 0;
  v39 = 0;
  v40 = 0;
  v34 = 0;
  v36 = 0;
  v31 = 0;
  v30 = 0;
  v4 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, L"Windows.Foundation.Uri");
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
         *v4,
         &v30);
  v6 = v5;
  v28 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v5,
      v28);
    goto LABEL_50;
  }
  v29 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  WebAccountProviderElementAttributes = _GetWebAccountProviderElementAttributes(a1, &v29);
  v6 = WebAccountProviderElementAttributes;
  v28 = WebAccountProviderElementAttributes;
  if ( WebAccountProviderElementAttributes < 0 )
  {
    v8 = 118;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)WebAccountProviderElementAttributes,
      v28);
    goto LABEL_49;
  }
  v9 = v29;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IInspectable **))(*(_QWORD *)v29 + 48LL);
  v37 = (RoVariant *)&v39;
  v38 = 0;
  v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, L"ManagedUrls");
  v28 = v10(v9, *v11, &v38);
  RoVariant::Attach(v37, v38);
  v6 = v28;
  if ( v28 == -2147483637 )
  {
    if ( (unsigned int)dword_180175000 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180175000,
        qword_1801468F8,
        0,
        0);
    v6 = 0;
    v28 = 0;
    goto LABEL_49;
  }
  if ( v28 < 0 )
  {
LABEL_49:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
LABEL_50:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    if ( v31 )
      WindowsDeleteString(v31);
    goto LABEL_52;
  }
  v37 = v39;
  LODWORD(v38) = v40;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  WebAccountProviderElementAttributes = RoVariant::Accessor::GetInspectable((RoVariant::Accessor *)&v37, &v36);
  v6 = WebAccountProviderElementAttributes;
  v28 = WebAccountProviderElementAttributes;
  if ( WebAccountProviderElementAttributes < 0 )
  {
    v8 = 143;
    goto LABEL_5;
  }
  v33 = 0;
  v12 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
          &v36,
          &v33);
  v6 = v12;
  v28 = v12;
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
    v14 = 145;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)v13,
      v28);
LABEL_61:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    goto LABEL_49;
  }
  v15 = v33;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING, struct IInspectable **))(*(_QWORD *)v33 + 48LL);
  v37 = (RoVariant *)&v39;
  v38 = 0;
  if ( WindowsCreateStringReference(L"Url", 3u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v28 = v16(v15, string, &v38);
  RoVariant::Attach(v37, v38);
  v6 = v28;
  if ( v28 == -2147483637 )
  {
    if ( (unsigned int)dword_180175000 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180175000,
        &unk_1801468C8,
        0,
        0);
    v28 = 0;
    goto LABEL_48;
  }
  if ( v28 < 0 )
    goto LABEL_61;
  v6 = v40;
  if ( v40 < 0 )
  {
    v17 = v40;
LABEL_29:
    v28 = v17;
    v13 = v6;
    v14 = 172;
    goto LABEL_15;
  }
  if ( !v40 )
  {
    v18 = 0;
    goto LABEL_33;
  }
  if ( v40 == 1 || v40 == 3 )
  {
    v18 = 13;
LABEL_33:
    v34 = v18;
    goto LABEL_34;
  }
  v17 = (*(__int64 (__fastcall **)(RoVariant *, int *))(*(_QWORD *)v39 + 48LL))(v39, &v34);
  v6 = v17;
  if ( v17 < 0 )
    goto LABEL_29;
  v6 = v40;
  v18 = v34;
LABEL_34:
  v28 = 0;
  string = (HSTRING)&v28;
  hstringHeader.Reserved.Reserved1 = &v39;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v31;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v30;
  v35 = 0;
  v37 = 0;
  v41[0] = &v37;
  v41[1] = &v35;
  v42 = 1;
  v32 = 0;
  if ( v18 == 13 )
  {
    v43 = v39;
    v44 = v6;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Inspectable = RoVariant::Accessor::GetInspectable((RoVariant::Accessor *)&v43, &v36);
    v6 = Inspectable;
    v28 = Inspectable;
    if ( Inspectable < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)Inspectable,
        v28);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      v42 = 0;
      lambda_6894db7cdfe69ea6bb49dd6715ca0c55_::operator()(v41);
      goto LABEL_61;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v26 = lambda_74d3793ef76711e2824080b833fd539b_::operator()(&string, v36, &v32);
    v6 = v26;
    v28 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)v26,
        v28);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      v42 = 0;
      lambda_6894db7cdfe69ea6bb49dd6715ca0c55_::operator()(v41);
      goto LABEL_61;
    }
    v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 104LL))(a2, v32);
    v6 = v27;
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)v27,
        v28);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      v42 = 0;
      lambda_6894db7cdfe69ea6bb49dd6715ca0c55_::operator()(v41);
      goto LABEL_61;
    }
    goto LABEL_47;
  }
  if ( v18 == 1037 )
  {
    v43 = v39;
    v44 = v6;
    v19 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v43);
    v6 = v19;
    if ( v19 < 0 )
    {
      v28 = v19;
LABEL_42:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)v6,
        v28);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      v42 = 0;
      lambda_6894db7cdfe69ea6bb49dd6715ca0c55_::operator()(v41);
      goto LABEL_61;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *, RoVariant **))(*(_QWORD *)v20 + 304LL))(v20, &v35, &v37);
    v28 = v6;
    if ( (v6 & 0x80000000) != 0 )
      goto LABEL_42;
    v21 = 0;
    if ( v35 )
    {
      while ( 1 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        v22 = lambda_74d3793ef76711e2824080b833fd539b_::operator()(&string, *((_QWORD *)v37 + v21), &v32);
        v6 = v22;
        v28 = v22;
        if ( v22 < 0 )
          break;
        v23 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 104LL))(a2, v32);
        v6 = v23;
        v28 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE0,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
            (const char *)(unsigned int)v23,
            v28);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          v42 = 0;
          lambda_6894db7cdfe69ea6bb49dd6715ca0c55_::operator()(v41);
          goto LABEL_61;
        }
        if ( ++v21 >= v35 )
          goto LABEL_47;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)v22,
        v28);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      v42 = 0;
      lambda_6894db7cdfe69ea6bb49dd6715ca0c55_::operator()(v41);
      goto LABEL_61;
    }
LABEL_47:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v42 = 0;
    lambda_6894db7cdfe69ea6bb49dd6715ca0c55_::operator()(v41);
LABEL_48:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v6 = v28;
    goto LABEL_49;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v42 = 0;
  lambda_6894db7cdfe69ea6bb49dd6715ca0c55_::operator()(v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  if ( v31 )
    WindowsDeleteString(v31);
  v6 = -2147418113;
LABEL_52:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  RoVariant::~RoVariant((RoVariant *)&v39);
  return v6;
}

```

## disassembly

```asm
0x180065764  mov     [rsp-8+arg_10], rbx
0x180065769  mov     [rsp-8+arg_18], rsi
0x18006576e  push    rbp
0x18006576f  push    rdi
0x180065770  push    r14
0x180065772  lea     rbp, [rsp-47h]
0x180065777  sub     rsp, 0D0h
0x18006577e  mov     rax, cs:__security_cookie
0x180065785  xor     rax, rsp
0x180065788  mov     [rbp+57h+var_18], rax
0x18006578c  mov     rsi, rdx
0x18006578f  mov     rdi, rcx
0x180065792  xor     r14d, r14d
0x180065795  mov     [rbp+57h+var_C0], r14d
0x180065799  mov     [rbp+57h+var_70], r14
0x18006579d  mov     [rbp+57h+var_68], r14d
0x1800657a1  mov     [rbp+57h+var_90], r14d
0x1800657a5  mov     [rbp+57h+var_88], r14
0x1800657a9  mov     [rbp+57h+var_A8], r14
0x1800657ad  mov     [rbp+57h+var_B0], r14
0x1800657b1  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800657b8  lea     rcx, [rbp+57h+string]; string
0x1800657bc  call    ??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[23])
0x1800657c1  lea     rdx, [rbp+57h+var_B0]
0x1800657c5  mov     rcx, [rax]
0x1800657c8  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1800657cd  mov     ebx, eax
0x1800657cf  mov     [rbp+57h+var_C0], eax
0x1800657d2  test    eax, eax
0x1800657d4  jns     short loc_1800657F2
0x1800657d6  mov     rcx, [rbp+5Fh]; this
0x1800657da  mov     r9d, eax; char *
0x1800657dd  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800657e4  lea     edx, [r14+6Fh]; void *
0x1800657e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800657ed  jmp     loc_180065BD9
0x1800657f2  mov     [rbp+57h+var_B8], r14
0x1800657f6  lea     rcx, [rbp+57h+var_B8]
0x1800657fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800657ff  lea     rdx, [rbp+57h+var_B8]
0x180065803  mov     rcx, rdi
0x180065806  call    ?_GetWebAccountProviderElementAttributes@@YAJPEAUIApplicationExtension@StateRepository@Internal@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@@Z; _GetWebAccountProviderElementAttributes(Windows::Internal::StateRepository::IApplicationExtension *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18006580b  mov     ebx, eax
0x18006580d  mov     [rbp+57h+var_C0], eax
0x180065810  test    eax, eax
0x180065812  jns     short loc_180065831
0x180065814  mov     edx, 76h ; 'v'; void *
0x180065819  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180065820  mov     r9d, eax; char *
0x180065823  mov     rcx, [rbp+5Fh]; this
0x180065827  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006582c  jmp     loc_180065BCF
0x180065831  mov     rdi, [rbp+57h+var_B8]
0x180065835  mov     rax, [rdi]
0x180065838  mov     rbx, [rax+30h]
0x18006583c  lea     rax, [rbp+57h+var_70]
0x180065840  mov     [rbp+57h+var_80], rax
0x180065844  mov     [rbp+57h+var_78], r14
0x180065848  lea     rdx, aManagedurls; "ManagedUrls"
0x18006584f  lea     rcx, [rbp+57h+string]; string
0x180065853  call    ??$?0$0M@@StringReference@Internal@Windows@@QEAA@AEAY0M@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[12])
0x180065858  lea     r8, [rbp+57h+var_78]
0x18006585c  mov     rdx, [rax]
0x18006585f  mov     rcx, rdi
0x180065862  mov     rax, rbx
0x180065865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006586a  mov     [rbp+57h+var_C0], eax
0x18006586d  mov     rdx, [rbp+57h+var_78]; struct IInspectable *
0x180065871  mov     rcx, [rbp+57h+var_80]; this
0x180065875  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18006587a  nop
0x18006587b  mov     ebx, [rbp+57h+var_C0]
0x18006587e  cmp     ebx, 8000000Bh
0x180065884  jnz     short loc_1800658B5
0x180065886  mov     eax, cs:dword_180175000
0x18006588c  cmp     eax, 5
0x18006588f  jbe     short loc_1800658AA
0x180065891  xor     r9d, r9d
0x180065894  xor     r8d, r8d
0x180065897  lea     rdx, qword_1801468F8
0x18006589e  lea     rcx, dword_180175000
0x1800658a5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800658aa  mov     ebx, r14d
0x1800658ad  mov     [rbp+57h+var_C0], ebx
0x1800658b0  jmp     loc_180065BCF
0x1800658b5  test    ebx, ebx
0x1800658b7  js      loc_180065BCF
0x1800658bd  mov     rax, [rbp+57h+var_70]
0x1800658c1  mov     [rbp+57h+var_80], rax
0x1800658c5  mov     eax, [rbp+57h+var_68]
0x1800658c8  mov     dword ptr [rbp+57h+var_78], eax
0x1800658cb  lea     rcx, [rbp+57h+var_88]
0x1800658cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800658d4  lea     rdx, [rbp+57h+var_88]; struct IInspectable **
0x1800658d8  lea     rcx, [rbp+57h+var_80]; this
0x1800658dc  call    ?GetInspectable@Accessor@RoVariant@@QEBAJPEAPEAUIInspectable@@@Z; RoVariant::Accessor::GetInspectable(IInspectable * *)
0x1800658e1  mov     ebx, eax
0x1800658e3  mov     [rbp+57h+var_C0], eax
0x1800658e6  test    eax, eax
0x1800658e8  jns     short loc_1800658F4
0x1800658ea  mov     edx, 8Fh
0x1800658ef  jmp     loc_180065819
0x1800658f4  mov     [rbp+57h+var_98], r14
0x1800658f8  lea     rdx, [rbp+57h+var_98]
0x1800658fc  lea     rcx, [rbp+57h+var_88]
0x180065900  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180065905  mov     ebx, eax
0x180065907  mov     [rbp+57h+var_C0], eax
0x18006590a  test    eax, eax
0x18006590c  jns     short loc_18006592B
0x18006590e  mov     r9d, eax; char *
0x180065911  mov     edx, 91h; void *
0x180065916  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006591d  mov     rcx, [rbp+5Fh]; this
0x180065921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065926  jmp     loc_180065D9F
0x18006592b  mov     rbx, [rbp+57h+var_98]
0x18006592f  mov     rax, [rbx]
0x180065932  mov     rdi, [rax+30h]
0x180065936  lea     rax, [rbp+57h+var_70]
0x18006593a  mov     [rbp+57h+var_80], rax
0x18006593e  mov     [rbp+57h+var_78], r14
0x180065942  lea     r9, [rbp+57h+string]; string
0x180065946  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006594a  mov     edx, 3; length
0x18006594f  lea     rcx, aUrl_0; "Url"
0x180065956  call    cs:__imp_WindowsCreateStringReference
0x18006595c  test    eax, eax
0x18006595e  jns     short loc_180065975
0x180065960  xor     r9d, r9d; lpArguments
0x180065963  xor     r8d, r8d; nNumberOfArguments
0x180065966  lea     edx, [r9+1]; dwExceptionFlags
0x18006596a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006596f  call    cs:__imp_RaiseException
0x180065975  lea     r8, [rbp+57h+var_78]
0x180065979  mov     rdx, [rbp+57h+string]
0x18006597d  mov     rcx, rbx
0x180065980  mov     rax, rdi
0x180065983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065988  mov     [rbp+57h+var_C0], eax
0x18006598b  mov     rdx, [rbp+57h+var_78]; struct IInspectable *
0x18006598f  mov     rcx, [rbp+57h+var_80]; this
0x180065993  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x180065998  nop
0x180065999  mov     ebx, [rbp+57h+var_C0]
0x18006599c  cmp     ebx, 8000000Bh
0x1800659a2  jnz     short loc_1800659D1
0x1800659a4  mov     eax, cs:dword_180175000
0x1800659aa  cmp     eax, 5
0x1800659ad  jbe     short loc_1800659C8
0x1800659af  xor     r9d, r9d
0x1800659b2  xor     r8d, r8d
0x1800659b5  lea     rdx, unk_1801468C8
0x1800659bc  lea     rcx, dword_180175000
0x1800659c3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800659c8  mov     [rbp+57h+var_C0], r14d
0x1800659cc  jmp     loc_180065BC3
0x1800659d1  test    ebx, ebx
0x1800659d3  js      loc_180065D9F
0x1800659d9  mov     ebx, [rbp+57h+var_68]
0x1800659dc  test    ebx, ebx
0x1800659de  jns     short loc_1800659E4
0x1800659e0  mov     eax, ebx
0x1800659e2  jmp     short loc_180065A0E
0x1800659e4  mov     ecx, ebx
0x1800659e6  test    ebx, ebx
0x1800659e8  jz      short loc_180065A2D
0x1800659ea  sub     ecx, 1
0x1800659ed  jz      short loc_180065A26
0x1800659ef  cmp     ecx, 2
0x1800659f2  jz      short loc_180065A26
0x1800659f4  mov     rcx, [rbp+57h+var_70]
0x1800659f8  mov     rax, [rcx]
0x1800659fb  lea     rdx, [rbp+57h+var_90]
0x1800659ff  mov     rax, [rax+30h]
0x180065a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065a08  mov     ebx, eax
0x180065a0a  test    eax, eax
0x180065a0c  jns     short loc_180065A1E
0x180065a0e  mov     [rbp+57h+var_C0], eax
0x180065a11  mov     r9d, ebx
0x180065a14  mov     edx, 0ACh
0x180065a19  jmp     loc_180065916
0x180065a1e  mov     ebx, [rbp+57h+var_68]
0x180065a21  mov     eax, [rbp+57h+var_90]
0x180065a24  jmp     short loc_180065A33
0x180065a26  mov     eax, 0Dh
0x180065a2b  jmp     short loc_180065A30
0x180065a2d  mov     eax, r14d
0x180065a30  mov     [rbp+57h+var_90], eax
0x180065a33  mov     [rbp+57h+var_C0], r14d
0x180065a37  lea     rcx, [rbp+57h+var_C0]
0x180065a3b  mov     [rbp+57h+string], rcx
0x180065a3f  lea     rcx, [rbp+57h+var_70]
0x180065a43  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rcx
0x180065a47  lea     rcx, [rbp+57h+var_A8]
0x180065a4b  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rcx
0x180065a4f  lea     rcx, [rbp+57h+var_B0]
0x180065a53  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rcx
0x180065a57  mov     [rbp+57h+var_8C], r14d
0x180065a5b  mov     [rbp+57h+var_80], r14
0x180065a5f  lea     rcx, [rbp+57h+var_80]
0x180065a63  mov     [rbp+57h+var_60], rcx
0x180065a67  lea     rcx, [rbp+57h+var_8C]
0x180065a6b  mov     [rbp+57h+var_58], rcx
0x180065a6f  mov     [rbp+57h+var_50], 1
0x180065a73  mov     [rbp+57h+var_A0], r14
0x180065a77  cmp     eax, 0Dh
0x180065a7a  jz      loc_180065C98
0x180065a80  cmp     eax, 40Dh
0x180065a85  jz      short loc_180065AD6
0x180065a87  lea     rcx, [rbp+57h+var_A0]
0x180065a8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065a90  nop
0x180065a91  mov     [rbp+57h+var_50], r14b
0x180065a95  lea     rcx, [rbp+57h+var_60]
0x180065a99  call    _lambda_6894db7cdfe69ea6bb49dd6715ca0c55___operator__
0x180065a9e  nop
0x180065a9f  lea     rcx, [rbp+57h+var_98]
0x180065aa3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065aa8  nop
0x180065aa9  lea     rcx, [rbp+57h+var_B8]
0x180065aad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065ab2  nop
0x180065ab3  lea     rcx, [rbp+57h+var_B0]
0x180065ab7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065abc  nop
0x180065abd  mov     rcx, [rbp+57h+var_A8]; string
0x180065ac1  test    rcx, rcx
0x180065ac4  jz      short loc_180065ACC
0x180065ac6  call    cs:__imp_WindowsDeleteString
0x180065acc  mov     ebx, 8000FFFFh
0x180065ad1  jmp     loc_180065BF3
0x180065ad6  mov     r9, [rbp+57h+var_70]
0x180065ada  mov     [rbp+57h+var_48], r9
0x180065ade  mov     [rbp+57h+var_40], ebx
0x180065ae1  lea     rcx, [rbp+57h+var_48]; this
0x180065ae5  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180065aea  mov     ebx, eax
0x180065aec  test    eax, eax
0x180065aee  jns     short loc_180065AF5
0x180065af0  mov     [rbp+57h+var_C0], eax
0x180065af3  jmp     short loc_180065B18
0x180065af5  mov     rax, [r9]
0x180065af8  lea     r8, [rbp+57h+var_80]
0x180065afc  lea     rdx, [rbp+57h+var_8C]
0x180065b00  mov     rcx, r9
0x180065b03  mov     rax, [rax+130h]
0x180065b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065b0f  mov     ebx, eax
0x180065b11  mov     [rbp+57h+var_C0], eax
0x180065b14  test    eax, eax
0x180065b16  jns     short loc_180065B4E
0x180065b18  mov     rcx, [rbp+5Fh]; this
0x180065b1c  mov     r9d, ebx; char *
0x180065b1f  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180065b26  mov     edx, 0DAh; void *
0x180065b2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065b30  nop
0x180065b31  lea     rcx, [rbp+57h+var_A0]
0x180065b35  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065b3a  nop
0x180065b3b  mov     [rbp+57h+var_50], r14b
0x180065b3f  lea     rcx, [rbp+57h+var_60]
0x180065b43  call    _lambda_6894db7cdfe69ea6bb49dd6715ca0c55___operator__
0x180065b48  nop
0x180065b49  jmp     loc_180065D9F
0x180065b4e  mov     edi, r14d
0x180065b51  cmp     [rbp+57h+var_8C], r14d
0x180065b55  jbe     short loc_180065BAB
0x180065b57  lea     rcx, [rbp+57h+var_A0]
0x180065b5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065b60  mov     eax, edi
0x180065b62  lea     r8, [rbp+57h+var_A0]
0x180065b66  mov     rdx, [rbp+57h+var_80]
0x180065b6a  mov     rdx, [rdx+rax*8]
0x180065b6e  lea     rcx, [rbp+57h+string]
0x180065b72  call    _lambda_74d3793ef76711e2824080b833fd539b___operator__
0x180065b77  mov     ebx, eax
0x180065b79  mov     [rbp+57h+var_C0], eax
0x180065b7c  test    eax, eax
0x180065b7e  js      loc_180065C62
0x180065b84  mov     rax, [rsi]
0x180065b87  mov     rdx, [rbp+57h+var_A0]
0x180065b8b  mov     rcx, rsi
0x180065b8e  mov     rax, [rax+68h]
0x180065b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065b97  mov     ebx, eax
0x180065b99  mov     [rbp+57h+var_C0], eax
0x180065b9c  test    eax, eax
0x180065b9e  js      loc_180065C2C
0x180065ba4  inc     edi
0x180065ba6  cmp     edi, [rbp+57h+var_8C]
0x180065ba9  jb      short loc_180065B57
0x180065bab  lea     rcx, [rbp+57h+var_A0]
0x180065baf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065bb4  nop
0x180065bb5  mov     [rbp+57h+var_50], r14b
0x180065bb9  lea     rcx, [rbp+57h+var_60]
0x180065bbd  call    _lambda_6894db7cdfe69ea6bb49dd6715ca0c55___operator__
  ... truncated ...
```
