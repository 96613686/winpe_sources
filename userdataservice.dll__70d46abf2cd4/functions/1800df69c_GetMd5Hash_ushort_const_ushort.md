# GetMd5Hash(ushort const *,ushort * *)

- ea: `0x1800df69c`
- end: `0x1800dfafa`
- name: `?GetMd5Hash@@YAJPEBGPEAPEAG@Z`
- size: `1118`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800deb88`

## callees

- `0x180004658`
- `0x180008f0c`
- `0x180042d18`
- `0x180064880`
- `0x18006f0a8`
- `0x1800977ac`
- `0x1800df69c`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `UserDataTypeHelperUtil!DupString` at `0x1800dfa02`
- `UserDataTypeHelperUtil!DupString` at `0x1800dfa02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df82b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df9d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dfa46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dfa8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df82b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df9d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dfa46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dfa8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df9ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df9ea`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800df6fd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800df7da`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800df8a4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800df6fd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800df7da`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800df8a4`

## string_xrefs

- `0x1800df70f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df788`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df7ec`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df850`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df8b6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df90f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df965`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df9bd`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800dfa14`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df7b3`: `Windows.Security.Cryptography.Core.HashAlgorithmNames`
- `0x1800df87d`: `Windows.Security.Cryptography.Core.HashAlgorithmProvider`
- `0x1800df6d2`: `Windows.Security.Cryptography.CryptographicBuffer`

## pseudocode

```c
__int64 __fastcall GetMd5Hash(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, PVOID, _QWORD, __int64 *); // rbx
  HSTRING_HEADER *v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, HSTRING *); // rbx
  int v23; // eax
  PCWSTR StringRawBuffer; // rbx
  __int64 v25; // rax
  int v26; // eax
  HSTRING v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // [rsp+30h] [rbp-39h] BYREF
  __int64 v33; // [rsp+38h] [rbp-31h] BYREF
  HSTRING string; // [rsp+40h] [rbp-29h] BYREF
  __int64 v35; // [rsp+48h] [rbp-21h] BYREF
  __int64 v36; // [rsp+50h] [rbp-19h] BYREF
  __int64 v37; // [rsp+58h] [rbp-11h] BYREF
  HSTRING v38; // [rsp+60h] [rbp-9h] BYREF
  __int64 v39; // [rsp+68h] [rbp-1h] BYREF
  void *Block; // [rsp+70h] [rbp+7h] BYREF
  const WCHAR *v41; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+17h] BYREF
  __int64 v43; // [rsp+98h] [rbp+2Fh]

  v41 = a1;
  v32 = 0;
  v43 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Cryptography.CryptographicBuffer",
    0x32u,
    0x31u);
  ActivationFactory = RoGetActivationFactory(v43, &GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb, &v32);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent(
      (unsigned int)ActivationFactory,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      423);
LABEL_3:
    v5 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return v4;
  }
  v7 = v32;
  v37 = 0;
  v8 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD, __int64 *))(*(_QWORD *)v32 + 120LL);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v37);
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v41);
  v10 = v8(v7, v9[1].Reserved.Reserved1, 0, &v37);
  v4 = v10;
  if ( v10 < 0 )
  {
    Log_HREvent(
      (unsigned int)v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      429);
LABEL_8:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v37);
    goto LABEL_3;
  }
  v33 = 0;
  v43 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Cryptography.Core.HashAlgorithmNames",
    0x36u,
    0x35u);
  v11 = RoGetActivationFactory(v43, &GUID_6b5e0516_de96_4f0a_8d57_dcc9dae36c76, &v33);
  v4 = v11;
  if ( v11 < 0 )
  {
    Log_HREvent(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      435);
    goto LABEL_11;
  }
  v13 = v33;
  string = 0;
  v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v15 = v14(v13, &string);
  v4 = v15;
  if ( v15 < 0 )
  {
    Log_HREvent(
      (unsigned int)v15,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      438);
LABEL_15:
    WindowsDeleteString(string);
    string = 0;
LABEL_11:
    v12 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_8;
  }
  v35 = 0;
  v43 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Cryptography.Core.HashAlgorithmProvider",
    0x39u,
    0x38u);
  v16 = RoGetActivationFactory(v43, &GUID_9fac9741_5cc4_4336_ae38_6212b75a915a, &v35);
  v4 = v16;
  if ( v16 < 0 )
  {
    Log_HREvent(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      444);
LABEL_18:
    v17 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_15;
  }
  v36 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v35 + 48LL))(v35, string, &v36);
  v4 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent(
      (unsigned int)v18,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      449);
    goto LABEL_22;
  }
  v39 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v36 + 64LL))(v36, v37, &v39);
  v4 = v20;
  if ( v20 < 0 )
  {
    Log_HREvent(
      (unsigned int)v20,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      454);
LABEL_26:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v39);
LABEL_22:
    v19 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_18;
  }
  v21 = v32;
  v38 = 0;
  v22 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v32 + 96LL);
  WindowsDeleteString(0);
  v38 = 0;
  v23 = v22(v21, v39, &v38);
  v4 = v23;
  if ( v23 < 0 )
  {
    Log_HREvent(
      (unsigned int)v23,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      460);
LABEL_29:
    WindowsDeleteString(v38);
    v38 = 0;
    goto LABEL_26;
  }
  Block = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
  v25 = tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>((__int64)&Block);
  v26 = DupString(v25, StringRawBuffer);
  v4 = v26;
  if ( v26 < 0 )
  {
    Log_HREvent(
      (unsigned int)v26,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      463);
    if ( Block )
      operator delete(Block);
    goto LABEL_29;
  }
  v27 = v38;
  *a2 = (unsigned __int16 *)Block;
  Block = 0;
  WindowsDeleteString(v27);
  v38 = 0;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v39);
  v28 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  WindowsDeleteString(string);
  v30 = v33;
  string = 0;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v37);
  v31 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return 0;
}

```

## disassembly

```asm
0x1800df69c  mov     [rsp-8+arg_10], rbx
0x1800df6a1  mov     [rsp-8+arg_18], rsi
0x1800df6a6  push    rbp
0x1800df6a7  push    rdi
0x1800df6a8  push    r14
0x1800df6aa  lea     rbp, [rsp-47h]
0x1800df6af  sub     rsp, 0B0h
0x1800df6b6  mov     rax, cs:__security_cookie
0x1800df6bd  xor     rax, rsp
0x1800df6c0  mov     [rbp+57h+var_20], rax
0x1800df6c4  xor     r14d, r14d
0x1800df6c7  mov     [rbp+57h+var_48], rcx
0x1800df6cb  mov     rsi, rdx
0x1800df6ce  mov     [rbp+57h+var_90], r14
0x1800df6d2  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_CryptographicBuffer@@3QBGB; "Windows.Security.Cryptography.Cryptogra"...
0x1800df6d9  mov     [rbp+57h+var_28], r14
0x1800df6dd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800df6e1  lea     r9d, [r14+31h]; unsigned int
0x1800df6e5  lea     r8d, [r14+32h]; unsigned int
0x1800df6e9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800df6ee  mov     rcx, [rbp+57h+var_28]
0x1800df6f2  lea     r8, [rbp+57h+var_90]
0x1800df6f6  lea     rdx, _GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb
0x1800df6fd  call    cs:__imp_RoGetActivationFactory
0x1800df703  mov     ebx, eax
0x1800df705  test    eax, eax
0x1800df707  jns     short loc_1800DF741
0x1800df709  mov     r9d, 1A7h
0x1800df70f  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df716  lea     edx, [r14+1]
0x1800df71a  mov     ecx, eax
0x1800df71c  call    Log_HREvent
0x1800df721  mov     rcx, [rbp+57h+var_90]
0x1800df725  test    rcx, rcx
0x1800df728  jz      short loc_1800DF73A
0x1800df72a  mov     [rbp+57h+var_90], r14
0x1800df72e  mov     rax, [rcx]
0x1800df731  mov     rax, [rax+10h]
0x1800df735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df73a  mov     eax, ebx
0x1800df73c  jmp     loc_1800DFAD6
0x1800df741  mov     rdi, [rbp+57h+var_90]
0x1800df745  lea     rcx, [rbp+57h+var_68]
0x1800df749  mov     [rbp+57h+var_68], r14
0x1800df74d  mov     rax, [rdi]
0x1800df750  mov     rbx, [rax+78h]
0x1800df754  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800df759  lea     rdx, [rbp+57h+var_48]
0x1800df75d  lea     rcx, [rbp+57h+hstringHeader]
0x1800df761  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800df766  lea     r9, [rbp+57h+var_68]
0x1800df76a  xor     r8d, r8d
0x1800df76d  mov     rcx, rdi
0x1800df770  mov     rdx, [rax+18h]
0x1800df774  mov     rax, rbx
0x1800df777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df77c  mov     ebx, eax
0x1800df77e  test    eax, eax
0x1800df780  jns     short loc_1800DF7A9
0x1800df782  mov     r9d, 1ADh
0x1800df788  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df78f  mov     edx, 1
0x1800df794  mov     ecx, eax
0x1800df796  call    Log_HREvent
0x1800df79b  lea     rcx, [rbp+57h+var_68]
0x1800df79f  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800df7a4  jmp     loc_1800DF721
0x1800df7a9  mov     r9d, 35h ; '5'; unsigned int
0x1800df7af  mov     [rbp+57h+var_88], r14
0x1800df7b3  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_Core_HashAlgorithmNames@@3QBGB; "Windows.Security.Cryptography.Core.Hash"...
0x1800df7ba  mov     [rbp+57h+var_28], r14
0x1800df7be  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800df7c2  lea     r8d, [r9+1]; unsigned int
0x1800df7c6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800df7cb  mov     rcx, [rbp+57h+var_28]
0x1800df7cf  lea     r8, [rbp+57h+var_88]
0x1800df7d3  lea     rdx, _GUID_6b5e0516_de96_4f0a_8d57_dcc9dae36c76
0x1800df7da  call    cs:__imp_RoGetActivationFactory
0x1800df7e0  mov     ebx, eax
0x1800df7e2  test    eax, eax
0x1800df7e4  jns     short loc_1800DF81A
0x1800df7e6  mov     r9d, 1B3h
0x1800df7ec  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df7f3  mov     edx, 1
0x1800df7f8  mov     ecx, eax
0x1800df7fa  call    Log_HREvent
0x1800df7ff  mov     rcx, [rbp+57h+var_88]
0x1800df803  test    rcx, rcx
0x1800df806  jz      short loc_1800DF79B
0x1800df808  mov     [rbp+57h+var_88], r14
0x1800df80c  mov     rax, [rcx]
0x1800df80f  mov     rax, [rax+10h]
0x1800df813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df818  jmp     short loc_1800DF79B
0x1800df81a  mov     rdi, [rbp+57h+var_88]
0x1800df81e  xor     ecx, ecx; string
0x1800df820  mov     [rbp+57h+string], r14
0x1800df824  mov     rax, [rdi]
0x1800df827  mov     rbx, [rax+30h]
0x1800df82b  call    cs:__imp_WindowsDeleteString
0x1800df831  lea     rdx, [rbp+57h+string]
0x1800df835  mov     [rbp+57h+string], r14
0x1800df839  mov     rcx, rdi
0x1800df83c  mov     rax, rbx
0x1800df83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df844  mov     ebx, eax
0x1800df846  test    eax, eax
0x1800df848  jns     short loc_1800DF873
0x1800df84a  mov     r9d, 1B6h
0x1800df850  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df857  mov     edx, 1
0x1800df85c  mov     ecx, eax
0x1800df85e  call    Log_HREvent
0x1800df863  mov     rcx, [rbp+57h+string]; string
0x1800df867  call    cs:__imp_WindowsDeleteString
0x1800df86d  mov     [rbp+57h+string], r14
0x1800df871  jmp     short loc_1800DF7FF
0x1800df873  mov     r9d, 38h ; '8'; unsigned int
0x1800df879  mov     [rbp+57h+var_78], r14
0x1800df87d  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_Core_HashAlgorithmProvider@@3QBGB; "Windows.Security.Cryptography.Core.Hash"...
0x1800df884  mov     [rbp+57h+var_28], r14
0x1800df888  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800df88c  lea     r8d, [r9+1]; unsigned int
0x1800df890  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800df895  mov     rcx, [rbp+57h+var_28]
0x1800df899  lea     r8, [rbp+57h+var_78]
0x1800df89d  lea     rdx, _GUID_9fac9741_5cc4_4336_ae38_6212b75a915a
0x1800df8a4  call    cs:__imp_RoGetActivationFactory
0x1800df8aa  mov     ebx, eax
0x1800df8ac  test    eax, eax
0x1800df8ae  jns     short loc_1800DF8E7
0x1800df8b0  mov     r9d, 1BCh
0x1800df8b6  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df8bd  mov     edx, 1
0x1800df8c2  mov     ecx, eax
0x1800df8c4  call    Log_HREvent
0x1800df8c9  mov     rcx, [rbp+57h+var_78]
0x1800df8cd  test    rcx, rcx
0x1800df8d0  jz      short loc_1800DF863
0x1800df8d2  mov     [rbp+57h+var_78], r14
0x1800df8d6  mov     rax, [rcx]
0x1800df8d9  mov     rax, [rax+10h]
0x1800df8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df8e2  jmp     loc_1800DF863
0x1800df8e7  mov     rcx, [rbp+57h+var_78]
0x1800df8eb  lea     r8, [rbp+57h+var_70]
0x1800df8ef  mov     rdx, [rbp+57h+string]
0x1800df8f3  mov     [rbp+57h+var_70], r14
0x1800df8f7  mov     rax, [rcx]
0x1800df8fa  mov     rax, [rax+30h]
0x1800df8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df903  mov     ebx, eax
0x1800df905  test    eax, eax
0x1800df907  jns     short loc_1800DF93D
0x1800df909  mov     r9d, 1C1h
0x1800df90f  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df916  mov     edx, 1
0x1800df91b  mov     ecx, eax
0x1800df91d  call    Log_HREvent
0x1800df922  mov     rcx, [rbp+57h+var_70]
0x1800df926  test    rcx, rcx
0x1800df929  jz      short loc_1800DF8C9
0x1800df92b  mov     [rbp+57h+var_70], r14
0x1800df92f  mov     rax, [rcx]
0x1800df932  mov     rax, [rax+10h]
0x1800df936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df93b  jmp     short loc_1800DF8C9
0x1800df93d  mov     rcx, [rbp+57h+var_70]
0x1800df941  lea     r8, [rbp+57h+var_58]
0x1800df945  mov     rdx, [rbp+57h+var_68]
0x1800df949  mov     [rbp+57h+var_58], r14
0x1800df94d  mov     rax, [rcx]
0x1800df950  mov     rax, [rax+40h]
0x1800df954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df959  mov     ebx, eax
0x1800df95b  test    eax, eax
0x1800df95d  jns     short loc_1800DF983
0x1800df95f  mov     r9d, 1C6h
0x1800df965  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df96c  mov     edx, 1
0x1800df971  mov     ecx, eax
0x1800df973  call    Log_HREvent
0x1800df978  lea     rcx, [rbp+57h+var_58]
0x1800df97c  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800df981  jmp     short loc_1800DF922
0x1800df983  mov     rdi, [rbp+57h+var_90]
0x1800df987  xor     ecx, ecx; string
0x1800df989  mov     [rbp+57h+var_60], r14
0x1800df98d  mov     rax, [rdi]
0x1800df990  mov     rbx, [rax+60h]
0x1800df994  call    cs:__imp_WindowsDeleteString
0x1800df99a  mov     rdx, [rbp+57h+var_58]
0x1800df99e  lea     r8, [rbp+57h+var_60]
0x1800df9a2  mov     rcx, rdi
0x1800df9a5  mov     [rbp+57h+var_60], r14
0x1800df9a9  mov     rax, rbx
0x1800df9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df9b1  mov     ebx, eax
0x1800df9b3  test    eax, eax
0x1800df9b5  jns     short loc_1800DF9E0
0x1800df9b7  mov     r9d, 1CCh
0x1800df9bd  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df9c4  mov     edx, 1
0x1800df9c9  mov     ecx, eax
0x1800df9cb  call    Log_HREvent
0x1800df9d0  mov     rcx, [rbp+57h+var_60]; string
0x1800df9d4  call    cs:__imp_WindowsDeleteString
0x1800df9da  mov     [rbp+57h+var_60], r14
0x1800df9de  jmp     short loc_1800DF978
0x1800df9e0  mov     rcx, [rbp+57h+var_60]; string
0x1800df9e4  xor     edx, edx; length
0x1800df9e6  mov     [rbp+57h+Block], r14
0x1800df9ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800df9f0  lea     rcx, [rbp+57h+Block]
0x1800df9f4  mov     rbx, rax
0x1800df9f7  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x1800df9fc  mov     rdx, rbx
0x1800df9ff  mov     rcx, rax
0x1800dfa02  call    cs:__imp_DupString
0x1800dfa08  mov     ebx, eax
0x1800dfa0a  test    eax, eax
0x1800dfa0c  jns     short loc_1800DFA37
0x1800dfa0e  mov     r9d, 1CFh
0x1800dfa14  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800dfa1b  mov     edx, 1
0x1800dfa20  mov     ecx, eax
0x1800dfa22  call    Log_HREvent
0x1800dfa27  mov     rcx, [rbp+57h+Block]; Block
0x1800dfa2b  test    rcx, rcx
0x1800dfa2e  jz      short loc_1800DF9D0
0x1800dfa30  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dfa35  jmp     short loc_1800DF9D0
0x1800dfa37  mov     rax, [rbp+57h+Block]
0x1800dfa3b  mov     rcx, [rbp+57h+var_60]; string
0x1800dfa3f  mov     [rsi], rax
0x1800dfa42  mov     [rbp+57h+Block], r14
0x1800dfa46  call    cs:__imp_WindowsDeleteString
0x1800dfa4c  lea     rcx, [rbp+57h+var_58]
0x1800dfa50  mov     [rbp+57h+var_60], r14
0x1800dfa54  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800dfa59  mov     rcx, [rbp+57h+var_70]
0x1800dfa5d  test    rcx, rcx
0x1800dfa60  jz      short loc_1800DFA72
0x1800dfa62  mov     [rbp+57h+var_70], r14
0x1800dfa66  mov     rax, [rcx]
0x1800dfa69  mov     rax, [rax+10h]
0x1800dfa6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfa72  mov     rcx, [rbp+57h+var_78]
0x1800dfa76  test    rcx, rcx
0x1800dfa79  jz      short loc_1800DFA8B
0x1800dfa7b  mov     [rbp+57h+var_78], r14
0x1800dfa7f  mov     rax, [rcx]
0x1800dfa82  mov     rax, [rax+10h]
0x1800dfa86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfa8b  mov     rcx, [rbp+57h+string]; string
0x1800dfa8f  call    cs:__imp_WindowsDeleteString
0x1800dfa95  mov     rcx, [rbp+57h+var_88]
0x1800dfa99  mov     [rbp+57h+string], r14
0x1800dfa9d  test    rcx, rcx
0x1800dfaa0  jz      short loc_1800DFAB2
0x1800dfaa2  mov     [rbp+57h+var_88], r14
0x1800dfaa6  mov     rax, [rcx]
0x1800dfaa9  mov     rax, [rax+10h]
0x1800dfaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfab2  lea     rcx, [rbp+57h+var_68]
0x1800dfab6  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800dfabb  mov     rcx, [rbp+57h+var_90]
0x1800dfabf  test    rcx, rcx
0x1800dfac2  jz      short loc_1800DFAD4
0x1800dfac4  mov     [rbp+57h+var_90], r14
0x1800dfac8  mov     rax, [rcx]
0x1800dfacb  mov     rax, [rax+10h]
0x1800dfacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfad4  xor     eax, eax
0x1800dfad6  mov     rcx, [rbp+57h+var_20]
0x1800dfada  xor     rcx, rsp; StackCookie
0x1800dfadd  call    __security_check_cookie
0x1800dfae2  lea     r11, [rsp+0C0h+var_10]
0x1800dfaea  mov     rbx, [r11+30h]
0x1800dfaee  mov     rsi, [r11+38h]
0x1800dfaf2  mov     rsp, r11
0x1800dfaf5  pop     r14
0x1800dfaf7  pop     rdi
0x1800dfaf8  pop     rbp
0x1800dfaf9  retn
```
