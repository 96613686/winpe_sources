# _lambda_a3d66e65fe9a74e278f1f3c9f4f62a5d_::operator()

- ea: `0x180040c4c`
- end: `0x180041117`
- name: `_lambda_a3d66e65fe9a74e278f1f3c9f4f62a5d_::operator()`
- size: `1227`
- prototype: `__int64 __fastcall(_QWORD **, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800406c8`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180006b9c`
- `0x18000e5ac`
- `0x180010130`
- `0x180019c58`
- `0x180019d84`
- `0x180040c4c`
- `0x1800415dc`
- `0x180041614`
- `0x18004f75c`
- `0x18004f854`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040e7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040f1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040fbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040ff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040e7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040f1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040fbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040ff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040ed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041020`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040ed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041020`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x180040f0f`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x180040f0f`

## string_xrefs

- `0x180040e3c`: `The specified OneSettings Payload registry path is not known (%ws)`
- `0x180040caf`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x180040cf9`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x180040dab`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x180040e50`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x180040ea3`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x180040fe6`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x180041100`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_a3d66e65fe9a74e278f1f3c9f4f62a5d_::operator()(_QWORD **a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rbx
  HKEY v15; // rax
  const char *v16; // rax
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  PCWSTR StringRawBuffer; // rax
  LPWSTR v21; // rsi
  __int64 v22; // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rbx
  __int64 v25; // rax
  int v26; // eax
  int (__fastcall *v27)(__int64, HSTRING *); // rdi
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, PCWSTR); // rbx
  PCWSTR v34; // rax
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD); // rbx
  __int64 v37; // rax
  int v39; // eax
  int v40; // [rsp+20h] [rbp-59h]
  __int64 v41; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v42; // [rsp+38h] [rbp-41h] BYREF
  HSTRING v43; // [rsp+40h] [rbp-39h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  __int64 v45; // [rsp+50h] [rbp-29h] BYREF
  void *v46; // [rsp+58h] [rbp-21h] BYREF
  __int64 v47; // [rsp+60h] [rbp-19h] BYREF
  LPWSTR lpsz; // [rsp+68h] [rbp-11h] BYREF
  DWORD cchLength[2]; // [rsp+70h] [rbp-9h]
  __int64 v50; // [rsp+78h] [rbp-1h]
  _BYTE v51[32]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  LODWORD(v42) = 0;
  v47 = 0;
  v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  v5 = v4(a2, &v47);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v43 = 0;
    v7 = v47;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v47 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    v9 = v8(v7, &v43);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
        (const char *)(unsigned int)v9,
        v40);
LABEL_5:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      goto LABEL_38;
    }
    v41 = 0;
    v10 = (*a1)[1];
    if ( v10 )
    {
      string = (HSTRING)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 72LL))(v10, 0);
      v42 = (HSTRING)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(*a1)[1] + 64LL))((*a1)[1]);
      v46 = v43;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      v11 = Microsoft::WRL::Details::MakeAndInitialize<RegistryJson,RegValet::IRegistryJson,Windows::Data::Json::IJsonObject * &,HKEY__ * &,unsigned short const * &>(
              &v41,
              &v46,
              &v42,
              &string);
    }
    else
    {
      string = v43;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      v46 = 0;
      v11 = Microsoft::WRL::Details::MakeAndInitialize<RegistryJson,RegValet::IRegistryJson,Windows::Data::Json::IJsonObject * &,HKEY__ * &,std::nullptr_t>(
              &v41,
              &string,
              v12,
              &v46);
    }
    v6 = v11;
    if ( v11 < 0 )
    {
      v13 = 153;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
        (const char *)v6,
        v40);
LABEL_12:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      goto LABEL_5;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v41 + 32LL))(v41) )
    {
      v6 = -2147024883;
      v13 = 154;
      goto LABEL_11;
    }
    v14 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 72LL))(v41, 0);
    v15 = (HKEY)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 64LL))(v41);
    if ( !RegistryPayloadHandler::IsPathKnown(v15, v14) )
    {
      v16 = (const char *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 72LL))(v41, 0);
      v6 = -2147024891;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
        (const char *)0x80070005LL,
        (int)"The specified OneSettings Payload registry path is not known (%ws)",
        v16);
      goto LABEL_12;
    }
    lpsz = 0;
    *(_QWORD *)cchLength = 0;
    v50 = 0;
    string = 0;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v18 = v17(a2, &string);
    v6 = v18;
    if ( v18 < 0 )
    {
      v19 = 163;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
        (const char *)(unsigned int)v18,
        v40);
      WindowsDeleteString(string);
      string = 0;
LABEL_20:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
      goto LABEL_12;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &lpsz,
            StringRawBuffer,
            -1);
    v6 = v18;
    if ( v18 < 0 )
    {
      v19 = 166;
      goto LABEL_19;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
    v21 = lpsz;
    CharUpperBuffW(lpsz, cchLength[0]);
    WindowsDeleteString(string);
    v22 = 0;
    v45 = 0;
    v23 = *a1[1];
    if ( v23 )
    {
      v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      v46 = v21;
      v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, &v46);
      LODWORD(v42) = 1;
      v26 = v24(v23, *(_QWORD *)(v25 + 24), &v45);
      v22 = v45;
    }
    else
    {
      v26 = -2147467261;
    }
    if ( v26 < 0 )
    {
      v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 56LL))(v41);
      v6 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC8,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
          (const char *)(unsigned int)v39,
          v40);
        goto LABEL_31;
      }
    }
    else
    {
      v42 = 0;
      v27 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 64LL);
      WindowsDeleteString(0);
      v42 = 0;
      if ( v27(v22, &v42) < 0 )
      {
        v28 = v45;
        v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 56LL);
        WindowsDeleteString(v42);
        v42 = 0;
        v30 = v29(v28, &v42);
        v6 = v30;
        if ( v30 < 0 )
        {
          v31 = 184;
LABEL_30:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v31,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
            (const char *)(unsigned int)v30,
            v40);
          WindowsDeleteString(v42);
          v42 = 0;
LABEL_31:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          goto LABEL_20;
        }
      }
      v32 = v41;
      v33 = *(__int64 (__fastcall **)(__int64, PCWSTR))(*(_QWORD *)v41 + 48LL);
      v34 = WindowsGetStringRawBuffer(v42, 0);
      v30 = v33(v32, v34);
      v6 = v30;
      if ( v30 < 0 )
      {
        v31 = 189;
        goto LABEL_30;
      }
      v35 = *a1[2];
      v36 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v35 + 88LL);
      v46 = v21;
      v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, &v46);
      v30 = v36(v35, *(_QWORD *)(v37 + 24));
      v6 = v30;
      if ( v30 < 0 )
      {
        v31 = 194;
        goto LABEL_30;
      }
      WindowsDeleteString(v42);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    v6 = 0;
    goto LABEL_38;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8D,
    (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
    (const char *)(unsigned int)v5,
    v40);
LABEL_38:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  return v6;
}

```

## disassembly

```asm
0x180040c4c  mov     [rsp-8+arg_10], rbx
0x180040c51  push    rbp
0x180040c52  push    rsi
0x180040c53  push    rdi
0x180040c54  push    r14
0x180040c56  push    r15
0x180040c58  lea     rbp, [rsp-37h]
0x180040c5d  sub     rsp, 0B0h
0x180040c64  mov     rax, cs:__security_cookie
0x180040c6b  xor     rax, rsp
0x180040c6e  mov     [rbp+57h+var_30], rax
0x180040c72  mov     rsi, rdx
0x180040c75  mov     r14, rcx
0x180040c78  xor     r15d, r15d
0x180040c7b  mov     dword ptr [rbp+57h+var_98], r15d
0x180040c7f  mov     [rbp+57h+var_70], r15
0x180040c83  mov     rax, [rdx]
0x180040c86  mov     rbx, [rax+38h]
0x180040c8a  lea     rcx, [rbp+57h+var_70]
0x180040c8e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040c93  lea     rdx, [rbp+57h+var_70]
0x180040c97  mov     rcx, rsi
0x180040c9a  mov     rax, rbx
0x180040c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ca2  mov     ebx, eax
0x180040ca4  test    eax, eax
0x180040ca6  jns     short loc_180040CC5
0x180040ca8  mov     rcx, [rbp+5Fh]; this
0x180040cac  mov     r9d, eax; char *
0x180040caf  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x180040cb6  mov     edx, 8Dh; void *
0x180040cbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040cc0  jmp     loc_1800410B5
0x180040cc5  mov     [rbp+57h+var_90], r15
0x180040cc9  mov     rdi, [rbp+57h+var_70]
0x180040ccd  mov     rax, [rdi]
0x180040cd0  mov     rbx, [rax+60h]
0x180040cd4  lea     rcx, [rbp+57h+var_90]
0x180040cd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040cdd  lea     rdx, [rbp+57h+var_90]
0x180040ce1  mov     rcx, rdi
0x180040ce4  mov     rax, rbx
0x180040ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cec  mov     ebx, eax
0x180040cee  test    eax, eax
0x180040cf0  jns     short loc_180040D19
0x180040cf2  mov     rcx, [rbp+5Fh]; this
0x180040cf6  mov     r9d, eax; char *
0x180040cf9  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x180040d00  mov     edx, 92h; void *
0x180040d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040d0a  nop
0x180040d0b  lea     rcx, [rbp+57h+var_90]
0x180040d0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040d14  jmp     loc_1800410B5
0x180040d19  mov     [rbp+57h+var_A0], r15
0x180040d1d  mov     rax, [r14]
0x180040d20  mov     rcx, [rax+8]
0x180040d24  test    rcx, rcx
0x180040d27  jz      short loc_180040D7A
0x180040d29  mov     rax, [rcx]
0x180040d2c  xor     edx, edx
0x180040d2e  mov     rax, [rax+48h]
0x180040d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d37  mov     [rbp+57h+string], rax
0x180040d3b  mov     rax, [r14]
0x180040d3e  mov     rcx, [rax+8]
0x180040d42  mov     rax, [rcx]
0x180040d45  mov     rax, [rax+40h]
0x180040d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d4e  mov     [rbp+57h+var_98], rax
0x180040d52  mov     rax, [rbp+57h+var_90]
0x180040d56  mov     [rbp+57h+var_78], rax
0x180040d5a  lea     rcx, [rbp+57h+var_A0]
0x180040d5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040d63  lea     r9, [rbp+57h+string]
0x180040d67  lea     r8, [rbp+57h+var_98]
0x180040d6b  lea     rdx, [rbp+57h+var_78]
0x180040d6f  lea     rcx, [rbp+57h+var_A0]
0x180040d73  call    ??$MakeAndInitialize@VRegistryJson@@UIRegistryJson@RegValet@@AEAPEAUIJsonObject@Json@Data@Windows@@AEAPEAUHKEY__@@AEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAUIRegistryJson@RegValet@@AEAPEAUIJsonObject@Json@Data@Windows@@AEAPEAUHKEY__@@AEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<RegistryJson,RegValet::IRegistryJson,Windows::Data::Json::IJsonObject * &,HKEY__ * &,ushort const * &>(RegValet::IRegistryJson * *,Windows::Data::Json::IJsonObject * &,HKEY__ * &,ushort const * &)
0x180040d78  jmp     short loc_180040DA0
0x180040d7a  mov     rax, [rbp+57h+var_90]
0x180040d7e  mov     [rbp+57h+string], rax
0x180040d82  lea     rcx, [rbp+57h+var_A0]
0x180040d86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040d8b  mov     [rbp+57h+var_78], r15
0x180040d8f  lea     r9, [rbp+57h+var_78]
0x180040d93  lea     rdx, [rbp+57h+string]
0x180040d97  lea     rcx, [rbp+57h+var_A0]
0x180040d9b  call    ??$MakeAndInitialize@VRegistryJson@@UIRegistryJson@RegValet@@AEAPEAUIJsonObject@Json@Data@Windows@@AEAPEAUHKEY__@@$$T@Details@WRL@Microsoft@@YAJPEAPEAUIRegistryJson@RegValet@@AEAPEAUIJsonObject@Json@Data@Windows@@AEAPEAUHKEY__@@$$QEA$$T@Z
0x180040da0  mov     ebx, eax
0x180040da2  test    eax, eax
0x180040da4  jns     short loc_180040DCD
0x180040da6  mov     edx, 99h; void *
0x180040dab  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x180040db2  mov     r9d, ebx; char *
0x180040db5  mov     rcx, [rbp+5Fh]; this
0x180040db9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040dbe  nop
0x180040dbf  lea     rcx, [rbp+57h+var_A0]
0x180040dc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040dc8  jmp     loc_180040D0B
0x180040dcd  mov     rcx, [rbp+57h+var_A0]
0x180040dd1  mov     rax, [rcx]
0x180040dd4  mov     rax, [rax+20h]
0x180040dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ddd  test    al, al
0x180040ddf  jnz     short loc_180040DED
0x180040de1  mov     ebx, 8007000Dh
0x180040de6  mov     edx, 9Ah
0x180040deb  jmp     short loc_180040DAB
0x180040ded  mov     rcx, [rbp+57h+var_A0]
0x180040df1  mov     rax, [rcx]
0x180040df4  xor     edx, edx
0x180040df6  mov     rax, [rax+48h]
0x180040dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dff  mov     rbx, rax
0x180040e02  mov     rcx, [rbp+57h+var_A0]
0x180040e06  mov     rdx, [rcx]
0x180040e09  mov     rax, [rdx+40h]
0x180040e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e12  mov     rdx, rbx; unsigned __int16 *
0x180040e15  mov     rcx, rax; HKEY
0x180040e18  call    ?IsPathKnown@RegistryPayloadHandler@@CA_NPEAUHKEY__@@PEBG@Z; RegistryPayloadHandler::IsPathKnown(HKEY__ *,ushort const *)
0x180040e1d  test    al, al
0x180040e1f  jnz     short loc_180040E66
0x180040e21  mov     rcx, [rbp+57h+var_A0]
0x180040e25  mov     rax, [rcx]
0x180040e28  xor     edx, edx
0x180040e2a  mov     rax, [rax+48h]
0x180040e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e33  mov     rcx, [rbp+5Fh]; this
0x180040e37  mov     [rsp+0D0h+var_A8], rax; char *
0x180040e3c  lea     rax, aTheSpecifiedOn_0; "The specified OneSettings Payload regis"...
0x180040e43  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180040e48  mov     ebx, 80070005h
0x180040e4d  mov     r9d, ebx; char *
0x180040e50  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x180040e57  mov     edx, 9Bh; void *
0x180040e5c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180040e61  jmp     loc_180040DBF
0x180040e66  mov     [rbp+57h+lpsz], r15
0x180040e6a  mov     qword ptr [rbp+57h+cchLength], r15
0x180040e6e  mov     [rbp+57h+var_58], r15
0x180040e72  mov     [rbp+57h+string], r15
0x180040e76  mov     rax, [rsi]
0x180040e79  mov     rbx, [rax+30h]
0x180040e7d  xor     ecx, ecx; string
0x180040e7f  call    cs:__imp_WindowsDeleteString
0x180040e85  mov     [rbp+57h+string], r15
0x180040e89  lea     rdx, [rbp+57h+string]
0x180040e8d  mov     rcx, rsi
0x180040e90  mov     rax, rbx
0x180040e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e98  mov     ebx, eax
0x180040e9a  test    eax, eax
0x180040e9c  jns     short loc_180040ED3
0x180040e9e  mov     edx, 0A3h; void *
0x180040ea3  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x180040eaa  mov     r9d, eax; char *
0x180040ead  mov     rcx, [rbp+5Fh]; this
0x180040eb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040eb6  nop
0x180040eb7  mov     rcx, [rbp+57h+string]; string
0x180040ebb  call    cs:__imp_WindowsDeleteString
0x180040ec1  mov     [rbp+57h+string], r15
0x180040ec5  lea     rcx, [rbp+57h+lpsz]
0x180040ec9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180040ece  jmp     loc_180040DBF
0x180040ed3  xor     edx, edx; length
0x180040ed5  mov     rcx, [rbp+57h+string]; string
0x180040ed9  call    cs:__imp_WindowsGetStringRawBuffer
0x180040edf  or      r8, 0FFFFFFFFFFFFFFFFh
0x180040ee3  mov     rdx, rax
0x180040ee6  lea     rcx, [rbp+57h+lpsz]
0x180040eea  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180040eef  mov     ebx, eax
0x180040ef1  test    eax, eax
0x180040ef3  jns     short loc_180040EFC
0x180040ef5  mov     edx, 0A6h
0x180040efa  jmp     short loc_180040EA3
0x180040efc  lea     rcx, [rbp+57h+lpsz]
0x180040f00  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180040f05  mov     edx, [rbp+57h+cchLength]; cchLength
0x180040f08  mov     rsi, [rbp+57h+lpsz]
0x180040f0c  mov     rcx, rsi; lpsz
0x180040f0f  call    cs:__imp_CharUpperBuffW
0x180040f15  nop
0x180040f16  mov     rcx, [rbp+57h+string]; string
0x180040f1a  call    cs:__imp_WindowsDeleteString
0x180040f20  mov     rbx, r15
0x180040f23  mov     [rbp+57h+var_80], rbx
0x180040f27  mov     rax, [r14+8]
0x180040f2b  mov     rdi, [rax]
0x180040f2e  test    rdi, rdi
0x180040f31  jz      short loc_180040F75
0x180040f33  mov     rax, [rdi]
0x180040f36  mov     rbx, [rax+30h]
0x180040f3a  lea     rcx, [rbp+57h+var_80]
0x180040f3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040f43  mov     [rbp+57h+var_78], rsi
0x180040f47  lea     rdx, [rbp+57h+var_78]
0x180040f4b  lea     rcx, [rbp+57h+var_50]
0x180040f4f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180040f54  nop
0x180040f55  mov     dword ptr [rbp+57h+var_98], 1
0x180040f5c  lea     r8, [rbp+57h+var_80]
0x180040f60  mov     rdx, [rax+18h]
0x180040f64  mov     rcx, rdi
0x180040f67  mov     rax, rbx
0x180040f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f6f  mov     rbx, [rbp+57h+var_80]
0x180040f73  jmp     short loc_180040F7A
0x180040f75  mov     eax, 80004003h
0x180040f7a  test    eax, eax
0x180040f7c  js      loc_1800410E3
0x180040f82  mov     [rbp+57h+var_98], r15
0x180040f86  mov     rax, [rbx]
0x180040f89  mov     rdi, [rax+40h]
0x180040f8d  xor     ecx, ecx; string
0x180040f8f  call    cs:__imp_WindowsDeleteString
0x180040f95  mov     [rbp+57h+var_98], r15
0x180040f99  lea     rdx, [rbp+57h+var_98]
0x180040f9d  mov     rcx, rbx
0x180040fa0  mov     rax, rdi
0x180040fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fa8  test    eax, eax
0x180040faa  jns     short loc_18004100F
0x180040fac  mov     rdi, [rbp+57h+var_80]
0x180040fb0  mov     rax, [rdi]
0x180040fb3  mov     rbx, [rax+38h]
0x180040fb7  mov     rcx, [rbp+57h+var_98]; string
0x180040fbb  call    cs:__imp_WindowsDeleteString
0x180040fc1  mov     [rbp+57h+var_98], r15
0x180040fc5  lea     rdx, [rbp+57h+var_98]
0x180040fc9  mov     rcx, rdi
0x180040fcc  mov     rax, rbx
0x180040fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fd4  mov     ebx, eax
0x180040fd6  test    eax, eax
0x180040fd8  jns     short loc_18004100F
0x180040fda  mov     edx, 0B8h; void *
0x180040fdf  mov     rcx, [rbp+5Fh]; this
0x180040fe3  mov     r9d, eax; char *
0x180040fe6  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x180040fed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040ff2  nop
0x180040ff3  mov     rcx, [rbp+57h+var_98]; string
0x180040ff7  call    cs:__imp_WindowsDeleteString
0x180040ffd  mov     [rbp+57h+var_98], r15
0x180041001  lea     rcx, [rbp+57h+var_80]
0x180041005  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004100a  jmp     loc_180040EC5
0x18004100f  mov     rdi, [rbp+57h+var_A0]
0x180041013  mov     rax, [rdi]
0x180041016  mov     rbx, [rax+30h]
0x18004101a  xor     edx, edx; length
0x18004101c  mov     rcx, [rbp+57h+var_98]; string
0x180041020  call    cs:__imp_WindowsGetStringRawBuffer
0x180041026  mov     rdx, rax
0x180041029  mov     rcx, rdi
0x18004102c  mov     rax, rbx
0x18004102f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041034  mov     ebx, eax
0x180041036  test    eax, eax
0x180041038  jns     short loc_180041041
0x18004103a  mov     edx, 0BDh
0x18004103f  jmp     short loc_180040FDF
0x180041041  mov     rax, [r14+10h]
0x180041045  mov     rdi, [rax]
0x180041048  mov     rax, [rdi]
0x18004104b  mov     rbx, [rax+58h]
0x18004104f  mov     [rbp+57h+var_78], rsi
0x180041053  lea     rdx, [rbp+57h+var_78]
0x180041057  lea     rcx, [rbp+57h+var_50]
0x18004105b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180041060  nop
0x180041061  mov     rdx, [rax+18h]
0x180041065  mov     rcx, rdi
0x180041068  mov     rax, rbx
0x18004106b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041070  mov     ebx, eax
0x180041072  test    eax, eax
0x180041074  jns     short loc_180041080
0x180041076  mov     edx, 0C2h
0x18004107b  jmp     loc_180040FDF
0x180041080  mov     rcx, [rbp+57h+var_98]; string
0x180041084  call    cs:__imp_WindowsDeleteString
0x18004108a  nop
0x18004108b  lea     rcx, [rbp+57h+var_80]
0x18004108f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041094  nop
0x180041095  lea     rcx, [rbp+57h+lpsz]
0x180041099  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004109e  nop
0x18004109f  lea     rcx, [rbp+57h+var_A0]
0x1800410a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800410a8  nop
0x1800410a9  lea     rcx, [rbp+57h+var_90]
0x1800410ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
  ... truncated ...
```
