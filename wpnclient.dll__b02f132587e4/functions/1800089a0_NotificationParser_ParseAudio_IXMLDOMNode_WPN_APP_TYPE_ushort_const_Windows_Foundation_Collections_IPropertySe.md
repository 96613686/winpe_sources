# NotificationParser::ParseAudio(IXMLDOMNode *,WPN_APP_TYPE,ushort const *,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x1800089a0`
- end: `0x180008fcf`
- name: `?ParseAudio@NotificationParser@@AEAAXPEAUIXMLDOMNode@@W4WPN_APP_TYPE@@PEBGPEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1583`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180005670`
- `0x1800089a0`
- `0x180008fe0`
- `0x18000e4c0`
- `0x18001b848`
- `0x18001ff00`
- `0x1800307c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008d07`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ddc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ecb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008f25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008f6a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008faf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008d07`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ddc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ecb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008f25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008f6a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008faf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800089fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008d1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008d69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008def`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800089fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008d1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008d69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008def`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008ead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008ead`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180008a2c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180008a2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ea1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ea1`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall NotificationParser::ParseAudio(__int64 *a1, __int64 a2, unsigned int a3, __int64 a4, HSTRING *a5)
{
  HSTRING v9; // rbx
  int v10; // edi
  HSTRING v11; // rbx
  __int64 (__fastcall *v12)(HSTRING, GUID *, HSTRING *); // rdi
  int v13; // eax
  HSTRING v14; // rax
  HSTRING v15; // rcx
  HSTRING v16; // rdx
  HSTRING v17; // rsi
  int v18; // eax
  __int64 v19; // rbx
  int (__fastcall *v20)(__int64, HSTRING, __int64 *); // rdi
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  unsigned __int64 v27; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v29; // r15
  __int64 (__fastcall *v30)(__int64, HSTRING, HSTRING *); // r12
  WCHAR *v31; // r14
  unsigned __int64 v32; // rdi
  int v33; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, HSTRING, HSTRING, char *); // r12
  HSTRING v36; // r15
  int v37; // eax
  __int64 v38; // r15
  __int64 (__fastcall *v39)(__int64, HSTRING, HSTRING *); // r12
  WCHAR *v40; // rdi
  int v41; // eax
  __int64 v42; // rbx
  __int64 (__fastcall *v43)(__int64, HSTRING, HSTRING, char *); // r12
  HSTRING v44; // r15
  int v45; // eax
  HSTRING v46; // rcx
  int v47; // [rsp+20h] [rbp-A1h]
  char v48[8]; // [rsp+30h] [rbp-91h] BYREF
  HSTRING v49; // [rsp+38h] [rbp-89h] BYREF
  HSTRING v50; // [rsp+40h] [rbp-81h] BYREF
  __int64 v51; // [rsp+48h] [rbp-79h] BYREF
  HSTRING v52; // [rsp+50h] [rbp-71h]
  __int64 v53; // [rsp+58h] [rbp-69h] BYREF
  HSTRING v54; // [rsp+60h] [rbp-61h]
  HSTRING v55; // [rsp+68h] [rbp-59h] BYREF
  PCWSTR sourceString[3]; // [rsp+70h] [rbp-51h] BYREF
  HSTRING v57; // [rsp+88h] [rbp-39h] BYREF
  HSTRING_HEADER v58; // [rsp+90h] [rbp-31h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v52 = 0;
  v54 = 0;
  v49 = 0;
  v55 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v9 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  v49 = 0;
  v50 = 0;
  v10 = RoActivateInstance(v9, &v50);
  if ( v10 < 0 )
    goto LABEL_6;
  if ( memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
  {
    v10 = (**(__int64 (__fastcall ***)(HSTRING, GUID *, HSTRING *))v50)(
            v50,
            &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
            &v49);
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v50 + 16LL))(v50);
LABEL_6:
    v11 = v49;
    goto LABEL_7;
  }
  v11 = v50;
  v49 = v50;
LABEL_7:
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v10,
      v47);
  v12 = **(__int64 (__fastcall ***)(HSTRING, GUID *, HSTRING *))v11;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  v13 = v12(v11, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v55);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6EB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v13,
      v47);
  v52 = v49;
  v54 = v55;
  NotificationParser::GetAttributes(a1, a2);
  v14 = v52;
  v15 = 0;
  v52 = 0;
  *a5 = v14;
  v16 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v16 + 16LL))(v16);
    v15 = v52;
  }
  if ( v15 )
  {
    v52 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v17 = *a5;
  v54 = v17;
  if ( v17 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v17 + 8LL))(v17);
  v51 = 0;
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(
          (__int64)v17,
          &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
          &v51);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v18,
      v47);
  v53 = 0;
  v19 = v51;
  v20 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v51 + 48LL);
  if ( WindowsCreateStringReference(L"src", 3u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( v20(v19, string, &v53) >= 0 )
  {
    v50 = 0;
    v24 = v53;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v53 + 152LL);
    WindowsDeleteString(0);
    v50 = 0;
    v26 = v25(v24, &v50);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3CF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v26,
        v47);
    sourceString[0] = 0;
    string = 0;
    v27 = -1;
    hstringHeader.Reserved.Reserved1 = (PVOID)-1LL;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
    sourceString[1] = (PCWSTR)-1LL;
    sourceString[2] = (PCWSTR)-1LL;
    StringRawBuffer = WindowsGetStringRawBuffer(v50, 0);
    NotificationParser::ParseSoundUri(a1, StringRawBuffer, a3, a4);
    v49 = 0;
    v29 = *a1;
    v30 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a1 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v31 = (WCHAR *)sourceString[0];
    v32 = -1;
    do
      ++v32;
    while ( sourceString[0][v32] );
    if ( v32 > 0xFFFFFFFF )
    {
      LODWORD(v32) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v31, v32, &v58, &v57);
    v33 = v30(v29, v57, &v49);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v33,
        (int)sourceString);
    v48[0] = 0;
    v34 = v51;
    v35 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, char *))(*(_QWORD *)v51 + 80LL);
    v36 = v49;
    if ( WindowsCreateStringReference(L"src", 3u, &v58, &v57) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v37 = v35(v34, v57, v36, v48);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3DB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v37,
        (int)sourceString);
    v38 = *a1;
    v39 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a1 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v40 = (WCHAR *)string;
    do
      ++v27;
    while ( *((_WORD *)string + v27) );
    if ( v27 > 0xFFFFFFFF )
    {
      LODWORD(v27) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v40, v27, &v58, &v57);
    v41 = v39(v38, v57, &v49);
    if ( v41 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3DE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v41,
        (int)sourceString);
    v42 = v51;
    v43 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, char *))(*(_QWORD *)v51 + 80LL);
    v44 = v49;
    if ( WindowsCreateStringReference(L"prefix", 6u, &v58, &v57) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v45 = v43(v42, v57, v44, v48);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v45,
        (int)sourceString);
    v46 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v46 + 16LL))(v46);
    }
    if ( v40 )
      CoTaskMemFree(v40);
    if ( v31 )
      CoTaskMemFree(v31);
    WindowsDeleteString(v50);
  }
  v21 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)v17 + 16LL))(v17);
}

```

## disassembly

```asm
0x1800089a0  push    rbp
0x1800089a2  push    rbx
0x1800089a3  push    rsi
0x1800089a4  push    rdi
0x1800089a5  push    r12
0x1800089a7  push    r13
0x1800089a9  push    r14
0x1800089ab  push    r15
0x1800089ad  lea     rbp, [rsp-17h]
0x1800089b2  sub     rsp, 0D8h
0x1800089b9  mov     rax, cs:__security_cookie
0x1800089c0  xor     rax, rsp
0x1800089c3  mov     [rbp+4Fh+var_48], rax
0x1800089c7  mov     r12, r9
0x1800089ca  mov     r15d, r8d
0x1800089cd  mov     r14, rdx
0x1800089d0  mov     r13, rcx
0x1800089d3  mov     rsi, [rbp+4Fh+arg_20]
0x1800089d7  xor     edi, edi
0x1800089d9  mov     [rbp+4Fh+var_C0], rdi
0x1800089dd  mov     [rbp+4Fh+var_B0], rdi
0x1800089e1  mov     [rsp+110h+var_D8], rdi
0x1800089e6  mov     [rbp+4Fh+var_A8], rdi
0x1800089ea  lea     r9, [rbp+4Fh+string]; string
0x1800089ee  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800089f2  mov     edx, 27h ; '''; length
0x1800089f7  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x1800089fe  call    cs:__imp_WindowsCreateStringReference
0x180008a04  test    eax, eax
0x180008a06  js      loc_180008EBB
0x180008a0c  mov     rbx, [rbp+4Fh+string]
0x180008a10  lea     rcx, [rsp+110h+var_D8]
0x180008a15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008a1a  mov     [rsp+110h+var_D8], rdi
0x180008a1f  mov     [rsp+110h+var_D0], rdi
0x180008a24  lea     rdx, [rsp+110h+var_D0]
0x180008a29  mov     rcx, rbx
0x180008a2c  call    cs:__imp_RoActivateInstance
0x180008a32  mov     edi, eax
0x180008a34  test    eax, eax
0x180008a36  js      short loc_180008A88
0x180008a38  mov     r8d, 10h; Size
0x180008a3e  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180008a45  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x180008a4c  call    memcmp_0
0x180008a51  test    eax, eax
0x180008a53  jz      loc_180008C20
0x180008a59  mov     rcx, [rsp+110h+var_D0]
0x180008a5e  mov     rax, [rcx]
0x180008a61  lea     r8, [rsp+110h+var_D8]
0x180008a66  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x180008a6d  mov     rax, [rax]
0x180008a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a75  mov     edi, eax
0x180008a77  mov     rcx, [rsp+110h+var_D0]
0x180008a7c  mov     rax, [rcx]
0x180008a7f  mov     rax, [rax+10h]
0x180008a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a88  mov     rbx, [rsp+110h+var_D8]
0x180008a8d  mov     rcx, [rbp+57h]; this
0x180008a91  test    edi, edi
0x180008a93  js      loc_180008ED6
0x180008a99  mov     rax, [rbx]
0x180008a9c  mov     rdi, [rax]
0x180008a9f  lea     rcx, [rbp+4Fh+var_A8]
0x180008aa3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008aa8  lea     r8, [rbp+4Fh+var_A8]
0x180008aac  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180008ab3  mov     rcx, rbx
0x180008ab6  mov     rax, rdi
0x180008ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008abe  nop
0x180008abf  mov     rcx, [rbp+57h]; this
0x180008ac3  test    eax, eax
0x180008ac5  js      loc_180008EEB
0x180008acb  mov     rax, [rsp+110h+var_D8]
0x180008ad0  mov     [rbp+4Fh+var_C0], rax
0x180008ad4  mov     r8, [rbp+4Fh+var_A8]
0x180008ad8  mov     [rbp+4Fh+var_B0], r8
0x180008adc  mov     rdx, r14
0x180008adf  mov     rcx, r13
0x180008ae2  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x180008ae7  mov     rax, [rbp+4Fh+var_C0]
0x180008aeb  xor     r14d, r14d
0x180008aee  mov     ecx, r14d
0x180008af1  mov     [rbp+4Fh+var_C0], rcx
0x180008af5  mov     [rsi], rax
0x180008af8  mov     rdx, [rbp+4Fh+var_B0]
0x180008afc  test    rdx, rdx
0x180008aff  jz      short loc_180008B18
0x180008b01  mov     [rbp+4Fh+var_B0], r14
0x180008b05  mov     rax, [rdx]
0x180008b08  mov     rcx, rdx
0x180008b0b  mov     rax, [rax+10h]
0x180008b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b14  mov     rcx, [rbp+4Fh+var_C0]
0x180008b18  test    rcx, rcx
0x180008b1b  jz      short loc_180008B2E
0x180008b1d  mov     [rbp+4Fh+var_C0], r14
0x180008b21  mov     rax, [rcx]
0x180008b24  mov     rax, [rax+10h]
0x180008b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b2d  nop
0x180008b2e  mov     rsi, [rsi]
0x180008b31  mov     [rbp+4Fh+var_B0], rsi
0x180008b35  test    rsi, rsi
0x180008b38  jz      short loc_180008B4A
0x180008b3a  mov     rax, [rsi]
0x180008b3d  mov     rcx, rsi
0x180008b40  mov     rax, [rax+8]
0x180008b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b49  nop
0x180008b4a  mov     [rbp+4Fh+var_C8], r14
0x180008b4e  mov     rax, [rsi]
0x180008b51  lea     r8, [rbp+4Fh+var_C8]
0x180008b55  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180008b5c  mov     rcx, rsi
0x180008b5f  mov     rax, [rax]
0x180008b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b67  nop
0x180008b68  mov     rcx, [rbp+57h]; this
0x180008b6c  test    eax, eax
0x180008b6e  js      loc_180008F00
0x180008b74  mov     [rbp+4Fh+var_B8], r14
0x180008b78  mov     rbx, [rbp+4Fh+var_C8]
0x180008b7c  mov     rax, [rbx]
0x180008b7f  mov     rdi, [rax+30h]
0x180008b83  lea     r9, [rbp+4Fh+string]; string
0x180008b87  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180008b8b  mov     edx, 3; length
0x180008b90  lea     rcx, aSrc; "src"
0x180008b97  call    cs:__imp_WindowsCreateStringReference
0x180008b9d  test    eax, eax
0x180008b9f  js      loc_180008F15
0x180008ba5  lea     r8, [rbp+4Fh+var_B8]
0x180008ba9  mov     rdx, [rbp+4Fh+string]
0x180008bad  mov     rcx, rbx
0x180008bb0  mov     rax, rdi
0x180008bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bb8  test    eax, eax
0x180008bba  jns     short loc_180008C2F
0x180008bbc  mov     rcx, [rbp+4Fh+var_B8]
0x180008bc0  test    rcx, rcx
0x180008bc3  jz      short loc_180008BD6
0x180008bc5  mov     [rbp+4Fh+var_B8], r14
0x180008bc9  mov     rax, [rcx]
0x180008bcc  mov     rax, [rax+10h]
0x180008bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd5  nop
0x180008bd6  mov     rcx, [rbp+4Fh+var_C8]
0x180008bda  test    rcx, rcx
0x180008bdd  jz      short loc_180008BF0
0x180008bdf  mov     [rbp+4Fh+var_C8], r14
0x180008be3  mov     rax, [rcx]
0x180008be6  mov     rax, [rax+10h]
0x180008bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bef  nop
0x180008bf0  mov     rax, [rsi]
0x180008bf3  mov     rcx, rsi
0x180008bf6  mov     rax, [rax+10h]
0x180008bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bff  nop
0x180008c00  mov     rcx, [rbp+4Fh+var_48]
0x180008c04  xor     rcx, rsp; StackCookie
0x180008c07  call    __security_check_cookie
0x180008c0c  add     rsp, 0D8h
0x180008c13  pop     r15
0x180008c15  pop     r14
0x180008c17  pop     r13
0x180008c19  pop     r12
0x180008c1b  pop     rdi
0x180008c1c  pop     rsi
0x180008c1d  pop     rbx
0x180008c1e  pop     rbp
0x180008c1f  retn
0x180008c20  mov     rbx, [rsp+110h+var_D0]
0x180008c25  mov     [rsp+110h+var_D8], rbx
0x180008c2a  jmp     loc_180008A8D
0x180008c2f  mov     [rsp+110h+var_D0], r14
0x180008c34  mov     rdi, [rbp+4Fh+var_B8]
0x180008c38  mov     rax, [rdi]
0x180008c3b  mov     rbx, [rax+98h]
0x180008c42  xor     ecx, ecx; string
0x180008c44  call    cs:__imp_WindowsDeleteString
0x180008c4a  mov     [rsp+110h+var_D0], r14
0x180008c4f  lea     rdx, [rsp+110h+var_D0]
0x180008c54  mov     rcx, rdi
0x180008c57  mov     rax, rbx
0x180008c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c5f  mov     rcx, [rbp+57h]; this
0x180008c63  test    eax, eax
0x180008c65  js      loc_180008F30
0x180008c6b  mov     [rbp+4Fh+sourceString], r14
0x180008c6f  mov     [rbp+4Fh+string], r14
0x180008c73  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180008c7a  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved], rbx
0x180008c7e  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+8], rbx
0x180008c82  mov     [rbp+4Fh+var_98], rbx
0x180008c86  mov     [rbp+4Fh+var_90], rbx
0x180008c8a  xor     edx, edx; length
0x180008c8c  mov     rcx, [rsp+110h+var_D0]; string
0x180008c91  call    cs:__imp_WindowsGetStringRawBuffer
0x180008c97  lea     rcx, [rbp+4Fh+string]
0x180008c9b  mov     [rsp+110h+var_E8], rcx
0x180008ca0  lea     rcx, [rbp+4Fh+sourceString]
0x180008ca4  mov     qword ptr [rsp+110h+var_F0], rcx; int
0x180008ca9  mov     r9, r12
0x180008cac  mov     r8d, r15d
0x180008caf  mov     rdx, rax
0x180008cb2  mov     rcx, r13
0x180008cb5  call    ?ParseSoundUri@NotificationParser@@AEAAXPEBGW4WPN_APP_TYPE@@0PEAPEAG2@Z; NotificationParser::ParseSoundUri(ushort const *,WPN_APP_TYPE,ushort const *,ushort * *,ushort * *)
0x180008cba  mov     [rsp+110h+var_D8], r14
0x180008cbf  mov     r15, [r13+0]
0x180008cc3  mov     rax, [r15]
0x180008cc6  mov     r12, [rax+90h]
0x180008ccd  lea     rcx, [rsp+110h+var_D8]
0x180008cd2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008cd7  mov     r14, [rbp+4Fh+sourceString]
0x180008cdb  mov     rdi, rbx
0x180008cde  xchg    ax, ax
0x180008ce0  inc     rdi
0x180008ce3  cmp     word ptr [r14+rdi*2], 0
0x180008ce9  jnz     short loc_180008CE0
0x180008ceb  mov     eax, 0FFFFFFFFh
0x180008cf0  cmp     rdi, rax
0x180008cf3  jbe     short loc_180008D0D
0x180008cf5  mov     edi, eax
0x180008cf7  xor     r9d, r9d; lpArguments
0x180008cfa  xor     r8d, r8d; nNumberOfArguments
0x180008cfd  mov     edx, 1; dwExceptionFlags
0x180008d02  mov     ecx, 0C000000Dh; dwExceptionCode
0x180008d07  call    cs:__imp_RaiseException
0x180008d0d  lea     r9, [rbp+4Fh+var_88]; string
0x180008d11  lea     r8, [rbp+4Fh+var_80]; hstringHeader
0x180008d15  mov     edx, edi; length
0x180008d17  mov     rcx, r14; sourceString
0x180008d1a  call    cs:__imp_WindowsCreateStringReference
0x180008d20  lea     r8, [rsp+110h+var_D8]
0x180008d25  mov     rdx, [rbp+4Fh+var_88]
0x180008d29  mov     rcx, r15
0x180008d2c  mov     rax, r12
0x180008d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d34  mov     rcx, [rbp+57h]; this
0x180008d38  test    eax, eax
0x180008d3a  js      loc_180008F45
0x180008d40  mov     [rsp+110h+var_E0], 0
0x180008d45  mov     rdi, [rbp+4Fh+var_C8]
0x180008d49  mov     rax, [rdi]
0x180008d4c  mov     r12, [rax+50h]
0x180008d50  mov     r15, [rsp+110h+var_D8]
0x180008d55  lea     r9, [rbp+4Fh+var_88]; string
0x180008d59  lea     r8, [rbp+4Fh+var_80]; hstringHeader
0x180008d5d  mov     edx, 3; length
0x180008d62  lea     rcx, aSrc; "src"
0x180008d69  call    cs:__imp_WindowsCreateStringReference
0x180008d6f  test    eax, eax
0x180008d71  js      loc_180008F5A
0x180008d77  lea     r9, [rsp+110h+var_E0]
0x180008d7c  mov     r8, r15
0x180008d7f  mov     rdx, [rbp+4Fh+var_88]
0x180008d83  mov     rcx, rdi
0x180008d86  mov     rax, r12
0x180008d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d8e  mov     rcx, [rbp+57h]; this
0x180008d92  test    eax, eax
0x180008d94  js      loc_180008F75
0x180008d9a  mov     r15, [r13+0]
0x180008d9e  mov     rax, [r15]
0x180008da1  mov     r12, [rax+90h]
0x180008da8  lea     rcx, [rsp+110h+var_D8]
0x180008dad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008db2  mov     rdi, [rbp+4Fh+string]
0x180008db6  inc     rbx
0x180008db9  cmp     word ptr [rdi+rbx*2], 0
0x180008dbe  jnz     short loc_180008DB6
0x180008dc0  mov     eax, 0FFFFFFFFh
0x180008dc5  cmp     rbx, rax
0x180008dc8  jbe     short loc_180008DE2
0x180008dca  mov     ebx, eax
0x180008dcc  xor     r9d, r9d; lpArguments
0x180008dcf  xor     r8d, r8d; nNumberOfArguments
0x180008dd2  mov     edx, 1; dwExceptionFlags
0x180008dd7  mov     ecx, 0C000000Dh; dwExceptionCode
0x180008ddc  call    cs:__imp_RaiseException
0x180008de2  lea     r9, [rbp+4Fh+var_88]; string
0x180008de6  lea     r8, [rbp+4Fh+var_80]; hstringHeader
0x180008dea  mov     edx, ebx; length
0x180008dec  mov     rcx, rdi; sourceString
0x180008def  call    cs:__imp_WindowsCreateStringReference
0x180008df5  lea     r8, [rsp+110h+var_D8]
0x180008dfa  mov     rdx, [rbp+4Fh+var_88]
0x180008dfe  mov     rcx, r15
0x180008e01  mov     rax, r12
0x180008e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e09  mov     rcx, [rbp+57h]; this
0x180008e0d  test    eax, eax
0x180008e0f  js      loc_180008F8A
0x180008e15  mov     rbx, [rbp+4Fh+var_C8]
0x180008e19  mov     rax, [rbx]
0x180008e1c  mov     r12, [rax+50h]
  ... truncated ...
```
