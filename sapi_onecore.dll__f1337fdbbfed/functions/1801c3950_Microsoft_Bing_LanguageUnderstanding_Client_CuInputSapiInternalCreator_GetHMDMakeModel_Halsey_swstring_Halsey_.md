# Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternalCreator::GetHMDMakeModel(Halsey::swstring &,Halsey::swstring &)

- ea: `0x1801c3950`
- end: `0x1801c3ce9`
- name: `?GetHMDMakeModel@CuInputSapiInternalCreator@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAVswstring@Halsey@@0@Z`
- size: `921`
- prototype: `__int64 __fastcall(Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternalCreator *__hidden this, struct Halsey::swstring *, struct Halsey::swstring *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800341dc`

## callees

- `0x18001ce70`
- `0x180021944`
- `0x180026508`
- `0x180029860`
- `0x18002b750`
- `0x180057e28`
- `0x18006a378`
- `0x180079e30`
- `0x1801c340c`
- `0x1801c37c4`
- `0x1801c3950`
- `0x1801c3e20`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3b3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3bab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3c5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3c69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3c81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3b3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3bab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3c5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3c69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3c81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c3b5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c3c2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c3c45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c3b5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c3c2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c3c45`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801c39ba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801c39ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternalCreator::GetHMDMakeModel(
        Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternalCreator *this,
        struct Halsey::swstring *a2,
        struct Halsey::swstring *a3)
{
  __int64 v5; // rbx
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v20; // eax
  __int64 v21; // rcx
  PCWSTR v22; // rax
  PCWSTR v23; // rax
  __int64 v24; // rcx
  __int64 v26; // [rsp+20h] [rbp-69h] BYREF
  __int64 v27; // [rsp+28h] [rbp-61h] BYREF
  int v28; // [rsp+30h] [rbp-59h] BYREF
  HSTRING string; // [rsp+38h] [rbp-51h] BYREF
  HSTRING v30; // [rsp+40h] [rbp-49h] BYREF
  __int64 v31; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v32; // [rsp+50h] [rbp-39h] BYREF
  __int64 v33; // [rsp+58h] [rbp-31h] BYREF
  const wchar_t *v34; // [rsp+60h] [rbp-29h] BYREF
  int v35; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v36[32]; // [rsp+70h] [rbp-19h] BYREF
  int v37; // [rsp+90h] [rbp+7h]
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v39; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v33 = 0;
  v39 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Devices.Enumeration.DeviceInformation",
    0x2Eu,
    0x2Du);
  v5 = v39;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_c17f100e_3a46_4a78_8013_769dc9b97390, &v33);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuinputsapiinternalcreator.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v26);
    goto LABEL_21;
  }
  v27 = 0;
  v34 = L"(System.Devices.InterfaceClassGuid:=\"{43f57110-467b-47d9-9c4b-264af0b54cfa}\" AND System.Devices.InterfaceEnabl"
         "ed:=System.StructuredQueryType.Boolean#True) OR (System.Devices.InterfaceClassGuid:=\"{deac60ab-66e2-42a4-ad9b-"
         "557ee33ae2d5}\" AND System.Devices.InterfaceEnabled:=System.StructuredQueryType.Boolean#True)";
  v8 = v33;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v34);
  v11 = v9(v8, *(_QWORD *)(v10 + 24), &v27);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuinputsapiinternalcreator.cpp",
      (const char *)(unsigned int)v11,
      v26);
LABEL_5:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    goto LABEL_21;
  }
  wil::wait_for_completion<Windows::Devices::Enumeration::DeviceInformationCollection *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Devices::Enumeration::DeviceInformation *>>>(
    &v26,
    v27);
  v28 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 56LL))(v26, &v28);
  if ( !v28 )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuinputsapiinternalcreator.cpp",
      (const char *)0x8000FFFFLL,
      v26);
    v12 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_5;
  }
  v31 = 0;
  v13 = v26;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v15 = v14(v13, 0, &v31);
  v7 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuinputsapiinternalcreator.cpp",
      (const char *)(unsigned int)v15,
      v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v16 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_5;
  }
  string = 0;
  v17 = v31;
  v18 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v18(v17, &string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v35 = 0;
  std::wstring::wstring(v36, StringRawBuffer);
  v37 = 0;
  v20 = DevicePropertyHelpers::DevicePropertyHelper::Initialize((DevicePropertyHelpers::DevicePropertyHelper *)&v35);
  v7 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuinputsapiinternalcreator.cpp",
      (const char *)(unsigned int)v20,
      v26);
    std::wstring::_Tidy_deallocate(v36);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v21 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_5;
  }
  v32 = 0;
  v30 = 0;
  WindowsDeleteString(0);
  v32 = 0;
  DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(
    (DevicePropertyHelpers::DevicePropertyHelper *)&v35,
    (struct _DEVPROPKEY *)&DEVPKEY_Device_Manufacturer,
    &v32);
  WindowsDeleteString(v30);
  v30 = 0;
  DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(
    (DevicePropertyHelpers::DevicePropertyHelper *)&v35,
    (struct _DEVPROPKEY *)&DEVPKEY_Device_Model,
    &v30);
  v22 = WindowsGetStringRawBuffer(v32, 0);
  Halsey::swstring::operator=(a2, v22);
  v23 = WindowsGetStringRawBuffer(v30, 0);
  Halsey::swstring::operator=(a3, v23);
  WindowsDeleteString(v30);
  v30 = 0;
  WindowsDeleteString(v32);
  v32 = 0;
  std::wstring::_Tidy_deallocate(v36);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v24 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  v7 = 0;
LABEL_21:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  return v7;
}

```

## disassembly

```asm
0x1801c3950  mov     [rsp-8+arg_0], rbx
0x1801c3955  push    rbp
0x1801c3956  push    rsi
0x1801c3957  push    rdi
0x1801c3958  push    r14
0x1801c395a  push    r15
0x1801c395c  lea     rbp, [rsp-37h]
0x1801c3961  sub     rsp, 0C0h
0x1801c3968  mov     rax, cs:__security_cookie
0x1801c396f  xor     rax, rsp
0x1801c3972  mov     [rbp+57h+var_28], rax
0x1801c3976  mov     r14, r8
0x1801c3979  mov     rsi, rdx
0x1801c397c  xor     r15d, r15d
0x1801c397f  mov     [rbp+57h+var_88], r15
0x1801c3983  mov     [rbp+57h+var_30], r15
0x1801c3987  lea     r9d, [r15+2Dh]; unsigned int
0x1801c398b  lea     r8d, [r15+2Eh]; unsigned int
0x1801c398f  lea     rdx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x1801c3996  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801c399a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801c399f  mov     rbx, [rbp+57h+var_30]
0x1801c39a3  lea     rcx, [rbp+57h+var_88]
0x1801c39a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c39ac  lea     r8, [rbp+57h+var_88]
0x1801c39b0  lea     rdx, _GUID_c17f100e_3a46_4a78_8013_769dc9b97390
0x1801c39b7  mov     rcx, rbx
0x1801c39ba  call    cs:__imp_RoGetActivationFactory
0x1801c39c0  mov     ebx, eax
0x1801c39c2  test    eax, eax
0x1801c39c4  jns     short loc_1801C39E3
0x1801c39c6  mov     rcx, [rbp+5Fh]; this
0x1801c39ca  mov     r9d, eax; char *
0x1801c39cd  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c39d4  mov     edx, 81h; void *
0x1801c39d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c39de  jmp     loc_1801C3CBB
0x1801c39e3  mov     [rbp+57h+var_B8], r15
0x1801c39e7  lea     rax, aSystemDevicesI; "(System.Devices.InterfaceClassGuid:=\"{"...
0x1801c39ee  mov     [rbp+57h+var_80], rax
0x1801c39f2  mov     rdi, [rbp+57h+var_88]
0x1801c39f6  mov     rax, [rdi]
0x1801c39f9  mov     rbx, [rax+50h]
0x1801c39fd  lea     rcx, [rbp+57h+var_B8]
0x1801c3a01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c3a06  lea     rdx, [rbp+57h+var_80]
0x1801c3a0a  lea     rcx, [rbp+57h+hstringHeader]
0x1801c3a0e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801c3a13  nop
0x1801c3a14  lea     r8, [rbp+57h+var_B8]
0x1801c3a18  mov     rdx, [rax+18h]
0x1801c3a1c  mov     rcx, rdi
0x1801c3a1f  mov     rax, rbx
0x1801c3a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3a27  mov     ebx, eax
0x1801c3a29  test    eax, eax
0x1801c3a2b  jns     short loc_1801C3A54
0x1801c3a2d  mov     rcx, [rbp+5Fh]; this
0x1801c3a31  mov     r9d, eax; char *
0x1801c3a34  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c3a3b  mov     edx, 84h; void *
0x1801c3a40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c3a45  nop
0x1801c3a46  lea     rcx, [rbp+57h+var_B8]
0x1801c3a4a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c3a4f  jmp     loc_1801C3CBB
0x1801c3a54  mov     rdx, [rbp+57h+var_B8]
0x1801c3a58  lea     rcx, [rbp+57h+var_C0]
0x1801c3a5c  call    ??$wait_for_completion@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@V?$ComPtr@U?$IVectorView@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@U?$IVectorView@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Devices::Enumeration::DeviceInformationCollection *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Devices::Enumeration::DeviceInformation *>>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS)
0x1801c3a61  nop
0x1801c3a62  mov     [rbp+57h+var_B0], r15d
0x1801c3a66  mov     rcx, [rbp+57h+var_C0]
0x1801c3a6a  mov     rax, [rcx]
0x1801c3a6d  lea     rdx, [rbp+57h+var_B0]
0x1801c3a71  mov     rax, [rax+38h]
0x1801c3a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3a7a  cmp     [rbp+57h+var_B0], r15d
0x1801c3a7e  jnz     short loc_1801C3ABA
0x1801c3a80  mov     rcx, [rbp+5Fh]; this
0x1801c3a84  mov     ebx, 8000FFFFh
0x1801c3a89  mov     r9d, ebx; char *
0x1801c3a8c  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c3a93  mov     edx, 89h; void *
0x1801c3a98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c3a9d  nop
0x1801c3a9e  mov     rcx, [rbp+57h+var_C0]
0x1801c3aa2  test    rcx, rcx
0x1801c3aa5  jz      short loc_1801C3AB8
0x1801c3aa7  mov     [rbp+57h+var_C0], r15
0x1801c3aab  mov     rax, [rcx]
0x1801c3aae  mov     rax, [rax+10h]
0x1801c3ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3ab7  nop
0x1801c3ab8  jmp     short loc_1801C3A46
0x1801c3aba  mov     [rbp+57h+var_98], r15
0x1801c3abe  mov     rdi, [rbp+57h+var_C0]
0x1801c3ac2  mov     rax, [rdi]
0x1801c3ac5  mov     rbx, [rax+30h]
0x1801c3ac9  lea     rcx, [rbp+57h+var_98]
0x1801c3acd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c3ad2  lea     r8, [rbp+57h+var_98]
0x1801c3ad6  xor     edx, edx
0x1801c3ad8  mov     rcx, rdi
0x1801c3adb  mov     rax, rbx
0x1801c3ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3ae3  mov     ebx, eax
0x1801c3ae5  test    eax, eax
0x1801c3ae7  jns     short loc_1801C3B2B
0x1801c3ae9  mov     rcx, [rbp+5Fh]; this
0x1801c3aed  mov     r9d, eax; char *
0x1801c3af0  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c3af7  mov     edx, 8Dh; void *
0x1801c3afc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c3b01  nop
0x1801c3b02  lea     rcx, [rbp+57h+var_98]
0x1801c3b06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c3b0b  nop
0x1801c3b0c  mov     rcx, [rbp+57h+var_C0]
0x1801c3b10  test    rcx, rcx
0x1801c3b13  jz      short loc_1801C3B26
0x1801c3b15  mov     [rbp+57h+var_C0], r15
0x1801c3b19  mov     rax, [rcx]
0x1801c3b1c  mov     rax, [rax+10h]
0x1801c3b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3b25  nop
0x1801c3b26  jmp     loc_1801C3A46
0x1801c3b2b  mov     [rbp+57h+string], r15
0x1801c3b2f  mov     rdi, [rbp+57h+var_98]
0x1801c3b33  mov     rax, [rdi]
0x1801c3b36  mov     rbx, [rax+30h]
0x1801c3b3a  xor     ecx, ecx; string
0x1801c3b3c  call    cs:__imp_WindowsDeleteString
0x1801c3b42  mov     [rbp+57h+string], r15
0x1801c3b46  lea     rdx, [rbp+57h+string]
0x1801c3b4a  mov     rcx, rdi
0x1801c3b4d  mov     rax, rbx
0x1801c3b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3b55  xor     edx, edx; length
0x1801c3b57  mov     rcx, [rbp+57h+string]; string
0x1801c3b5b  call    cs:__imp_WindowsGetStringRawBuffer
0x1801c3b61  mov     [rbp+57h+var_78], r15d
0x1801c3b65  mov     rdx, rax
0x1801c3b68  lea     rcx, [rbp+57h+var_70]
0x1801c3b6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801c3b71  mov     [rbp+57h+var_50], r15d
0x1801c3b75  lea     rcx, [rbp+57h+var_78]; this
0x1801c3b79  call    ?Initialize@DevicePropertyHelper@DevicePropertyHelpers@@QEAAJXZ; DevicePropertyHelpers::DevicePropertyHelper::Initialize(void)
0x1801c3b7e  mov     ebx, eax
0x1801c3b80  test    eax, eax
0x1801c3b82  jns     short loc_1801C3BDE
0x1801c3b84  mov     rcx, [rbp+5Fh]; this
0x1801c3b88  mov     r9d, eax; char *
0x1801c3b8b  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c3b92  mov     edx, 91h; void *
0x1801c3b97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c3b9c  nop
0x1801c3b9d  lea     rcx, [rbp+57h+var_70]
0x1801c3ba1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801c3ba6  nop
0x1801c3ba7  mov     rcx, [rbp+57h+string]; string
0x1801c3bab  call    cs:__imp_WindowsDeleteString
0x1801c3bb1  mov     [rbp+57h+string], r15
0x1801c3bb5  lea     rcx, [rbp+57h+var_98]
0x1801c3bb9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c3bbe  nop
0x1801c3bbf  mov     rcx, [rbp+57h+var_C0]
0x1801c3bc3  test    rcx, rcx
0x1801c3bc6  jz      short loc_1801C3BD9
0x1801c3bc8  mov     [rbp+57h+var_C0], r15
0x1801c3bcc  mov     rax, [rcx]
0x1801c3bcf  mov     rax, [rax+10h]
0x1801c3bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3bd8  nop
0x1801c3bd9  jmp     loc_1801C3A46
0x1801c3bde  mov     [rbp+57h+var_90], r15
0x1801c3be2  mov     [rbp+57h+var_A0], r15
0x1801c3be6  xor     ecx, ecx; string
0x1801c3be8  call    cs:__imp_WindowsDeleteString
0x1801c3bee  mov     [rbp+57h+var_90], r15
0x1801c3bf2  lea     r8, [rbp+57h+var_90]
0x1801c3bf6  lea     rdx, DEVPKEY_Device_Manufacturer
0x1801c3bfd  lea     rcx, [rbp+57h+var_78]
0x1801c3c01  call    ??$GetDriverProperty@PEAUHSTRING__@@@DevicePropertyHelper@DevicePropertyHelpers@@QEBAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(_DEVPROPKEY const &,HSTRING__ * *)
0x1801c3c06  mov     rcx, [rbp+57h+var_A0]; string
0x1801c3c0a  call    cs:__imp_WindowsDeleteString
0x1801c3c10  mov     [rbp+57h+var_A0], r15
0x1801c3c14  lea     r8, [rbp+57h+var_A0]
0x1801c3c18  lea     rdx, DEVPKEY_Device_Model
0x1801c3c1f  lea     rcx, [rbp+57h+var_78]
0x1801c3c23  call    ??$GetDriverProperty@PEAUHSTRING__@@@DevicePropertyHelper@DevicePropertyHelpers@@QEBAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(_DEVPROPKEY const &,HSTRING__ * *)
0x1801c3c28  xor     edx, edx; length
0x1801c3c2a  mov     rcx, [rbp+57h+var_90]; string
0x1801c3c2e  call    cs:__imp_WindowsGetStringRawBuffer
0x1801c3c34  mov     rdx, rax
0x1801c3c37  mov     rcx, rsi
0x1801c3c3a  call    ??4swstring@Halsey@@QEAAAEBV01@PEBG@Z; Halsey::swstring::operator=(ushort const *)
0x1801c3c3f  xor     edx, edx; length
0x1801c3c41  mov     rcx, [rbp+57h+var_A0]; string
0x1801c3c45  call    cs:__imp_WindowsGetStringRawBuffer
0x1801c3c4b  mov     rdx, rax
0x1801c3c4e  mov     rcx, r14
0x1801c3c51  call    ??4swstring@Halsey@@QEAAAEBV01@PEBG@Z; Halsey::swstring::operator=(ushort const *)
0x1801c3c56  nop
0x1801c3c57  mov     rcx, [rbp+57h+var_A0]; string
0x1801c3c5b  call    cs:__imp_WindowsDeleteString
0x1801c3c61  mov     [rbp+57h+var_A0], r15
0x1801c3c65  mov     rcx, [rbp+57h+var_90]; string
0x1801c3c69  call    cs:__imp_WindowsDeleteString
0x1801c3c6f  mov     [rbp+57h+var_90], r15
0x1801c3c73  lea     rcx, [rbp+57h+var_70]
0x1801c3c77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801c3c7c  nop
0x1801c3c7d  mov     rcx, [rbp+57h+string]; string
0x1801c3c81  call    cs:__imp_WindowsDeleteString
0x1801c3c87  mov     [rbp+57h+string], r15
0x1801c3c8b  lea     rcx, [rbp+57h+var_98]
0x1801c3c8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c3c94  nop
0x1801c3c95  mov     rcx, [rbp+57h+var_C0]
0x1801c3c99  test    rcx, rcx
0x1801c3c9c  jz      short loc_1801C3CAF
0x1801c3c9e  mov     [rbp+57h+var_C0], r15
0x1801c3ca2  mov     rax, [rcx]
0x1801c3ca5  mov     rax, [rax+10h]
0x1801c3ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3cae  nop
0x1801c3caf  lea     rcx, [rbp+57h+var_B8]
0x1801c3cb3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c3cb8  mov     ebx, r15d
0x1801c3cbb  lea     rcx, [rbp+57h+var_88]
0x1801c3cbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c3cc4  mov     eax, ebx
0x1801c3cc6  mov     rcx, [rbp+57h+var_28]
0x1801c3cca  xor     rcx, rsp; StackCookie
0x1801c3ccd  call    __security_check_cookie
0x1801c3cd2  mov     rbx, [rsp+0E0h+arg_0]
0x1801c3cda  add     rsp, 0C0h
0x1801c3ce1  pop     r15
0x1801c3ce3  pop     r14
0x1801c3ce5  pop     rdi
0x1801c3ce6  pop     rsi
0x1801c3ce7  pop     rbp
0x1801c3ce8  retn
```
