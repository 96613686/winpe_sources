# NotificationParser::ConvertAdaptiveImage(Windows::Internal::Notifications::IAdaptiveImage *,ushort const *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x18001afb0`
- end: `0x18001b48b`
- name: `?ConvertAdaptiveImage@NotificationParser@@AEAAXPEAUIAdaptiveImage@Notifications@Internal@Windows@@PEBG11W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@5@@Z`
- size: `1243`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001a65c`

## callees

- `0x180005670`
- `0x180008390`
- `0x18000b440`
- `0x18000bbf0`
- `0x18000dc30`
- `0x180013fc0`
- `0x180014500`
- `0x180014550`
- `0x1800153b4`
- `0x18001afb0`
- `0x18001b848`
- `0x18001ff00`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b1c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b42f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b43d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b1c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b42f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b43d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NotificationParser::ConvertAdaptiveImage(
        __int64 **a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        int a6,
        int a7,
        _QWORD *a8)
{
  __int64 v11; // rcx
  __int64 *v12; // rdi
  __int64 (__fastcall *v13)(__int64 *, _QWORD, __int64 *); // rbx
  _QWORD *v14; // rax
  int v15; // eax
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v18; // rbx
  _QWORD *v19; // rax
  int v20; // eax
  __int64 *v21; // rdi
  __int64 (__fastcall *v22)(__int64 *, HSTRING, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v26; // rbx
  _QWORD *v27; // rax
  int v28; // eax
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  int v30; // eax
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rbx
  int v32; // eax
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  int v34; // eax
  __int64 *v35; // rdi
  void (__fastcall *v36)(__int64 *, HSTRING, __int64 *); // rbx
  __int64 v37; // rsi
  void (__fastcall *v38)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v39; // rbx
  _QWORD *v40; // rax
  __int64 *v41; // rdi
  void (__fastcall *v42)(__int64 *, HSTRING, __int64 *); // rbx
  __int64 v43; // rsi
  void (__fastcall *v44)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v45; // rbx
  _QWORD *v46; // rax
  const wchar_t *StringRawBuffer; // rax
  int v48; // eax
  __int64 *v49; // rbx
  __int64 v50; // rdi
  _QWORD *v51; // rax
  __int64 v52; // rsi
  void (__fastcall *v53)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v54; // rbx
  _QWORD *v55; // rax
  __int64 v56; // rsi
  void (__fastcall *v57)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v58; // rbx
  _QWORD *v59; // rax
  __int64 v60; // rax
  int v62; // [rsp+20h] [rbp-89h]
  _BYTE v63[8]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v64; // [rsp+48h] [rbp-61h] BYREF
  __int64 v65; // [rsp+50h] [rbp-59h] BYREF
  HSTRING v66; // [rsp+58h] [rbp-51h] BYREF
  HSTRING v67; // [rsp+60h] [rbp-49h] BYREF
  HSTRING string; // [rsp+68h] [rbp-41h] BYREF
  __int64 v69; // [rsp+70h] [rbp-39h] BYREF
  _QWORD *v70; // [rsp+78h] [rbp-31h]
  HSTRING v71[4]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+3Fh]

  v70 = a8;
  v69 = 0;
  v65 = 0;
  v64 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
  NotificationParser::CreateValueSet(v11, &v69, &v65);
  v63[0] = 0;
  string = 0;
  v67 = 0;
  v66 = 0;
  v12 = *a1;
  v13 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(**a1 + 144);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  v14 = (_QWORD *)Windows::Internal::StringReference::StringReference(v71, L"image");
  v15 = v13(v12, *v14, &v64);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x151,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v15,
      v62);
  v16 = v65;
  v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v65 + 80LL);
  v18 = v64;
  v19 = (_QWORD *)Windows::Internal::StringReference::StringReference(v71, L"item-type");
  v20 = v17(v16, *v19, v18, v63);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v20,
      v62);
  v21 = *a1;
  v22 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(**a1 + 144);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v71, a5);
  v23 = v22(v21, v71[0], &v64);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v23,
      v62);
  v24 = v65;
  v25 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v65 + 80LL);
  v26 = v64;
  v27 = (_QWORD *)Windows::Internal::StringReference::StringReference(v71, L"placement");
  v28 = v25(v24, *v27, v26, v63);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v28,
      v62);
  v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(string);
  string = 0;
  v30 = v29(a2, &string);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v30,
      v62);
  v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 64LL);
  WindowsDeleteString(v67);
  v67 = 0;
  v32 = v31(a2, &v67);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v32,
      v62);
  v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(v66);
  v66 = 0;
  v34 = v33(a2, &v66);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v34,
      v62);
  if ( string )
  {
    v35 = *a1;
    v36 = *(void (__fastcall **)(__int64 *, HSTRING, __int64 *))(**a1 + 144);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    v36(v35, string, &v64);
    v37 = v65;
    v38 = *(void (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v65 + 80LL);
    v39 = v64;
    v40 = (_QWORD *)Windows::Internal::StringReference::StringReference(v71, L"src");
    v38(v37, *v40, v39, v63);
  }
  if ( v67 )
  {
    v41 = *a1;
    v42 = *(void (__fastcall **)(__int64 *, HSTRING, __int64 *))(**a1 + 144);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    v42(v41, v67, &v64);
    v43 = v65;
    v44 = *(void (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v65 + 80LL);
    v45 = v64;
    v46 = (_QWORD *)Windows::Internal::StringReference::StringReference(v71, L"alt");
    v44(v43, *v46, v45, v63);
  }
  if ( v66 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v66, 0);
    v48 = wcscmp_0(StringRawBuffer, L"person");
    v49 = *a1;
    v50 = **a1;
    if ( v48 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
      (*(void (__fastcall **)(__int64 *, HSTRING, __int64 *))(v50 + 144))(v49, v66, &v64);
      v56 = v65;
      v57 = *(void (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v65 + 80LL);
      v58 = v64;
      v59 = (_QWORD *)Windows::Internal::StringReference::StringReference(v71, L"style");
      v57(v56, *v59, v58, v63);
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
      v51 = (_QWORD *)Windows::Internal::StringReference::StringReference(v71, L"circle");
      (*(void (__fastcall **)(__int64 *, _QWORD, __int64 *))(v50 + 144))(v49, *v51, &v64);
      v52 = v65;
      v53 = *(void (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v65 + 80LL);
      v54 = v64;
      v55 = (_QWORD *)Windows::Internal::StringReference::StringReference(v71, L"hint-crop");
      v53(v52, *v55, v54, v63);
    }
  }
  NotificationParser::ResolveImageElement((__int64)a1, v65, L"src", a3, v62, a6, a7, 1);
  NotificationParser::ResolveTextElement(a1, v65, L"alt", (__int64)a3);
  v60 = v69;
  v69 = 0;
  *v70 = v60;
  WindowsDeleteString(v66);
  v66 = 0;
  WindowsDeleteString(v67);
  v67 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
}

```

## disassembly

```asm
0x18001afb0  mov     [rsp-8+arg_18], rbx
0x18001afb5  push    rbp
0x18001afb6  push    rsi
0x18001afb7  push    rdi
0x18001afb8  push    r12
0x18001afba  push    r13
0x18001afbc  push    r14
0x18001afbe  push    r15
0x18001afc0  lea     rbp, [rsp-7]
0x18001afc5  sub     rsp, 0B0h
0x18001afcc  mov     rax, cs:__security_cookie
0x18001afd3  xor     rax, rsp
0x18001afd6  mov     [rbp+37h+var_40], rax
0x18001afda  mov     r13, r8
0x18001afdd  mov     r14, rdx
0x18001afe0  mov     r15, rcx
0x18001afe3  mov     r12, [rbp+37h+arg_20]
0x18001afe7  mov     rax, [rbp+37h+arg_38]
0x18001afeb  mov     [rbp+37h+var_68], rax
0x18001afef  xor     esi, esi
0x18001aff1  mov     [rbp+37h+var_70], rsi
0x18001aff5  mov     [rbp+37h+var_90], rsi
0x18001aff9  mov     [rbp+37h+var_98], rsi
0x18001affd  lea     rcx, [rbp+37h+var_90]
0x18001b001  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b006  lea     rcx, [rbp+37h+var_70]
0x18001b00a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b00f  lea     r8, [rbp+37h+var_90]
0x18001b013  lea     rdx, [rbp+37h+var_70]
0x18001b017  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18001b01c  mov     [rbp+37h+var_A0], sil
0x18001b020  mov     [rbp+37h+string], rsi
0x18001b024  mov     [rbp+37h+var_80], rsi
0x18001b028  mov     [rbp+37h+var_88], rsi
0x18001b02c  mov     rdi, [r15]
0x18001b02f  mov     rax, [rdi]
0x18001b032  mov     rbx, [rax+90h]
0x18001b039  lea     rcx, [rbp+37h+var_98]
0x18001b03d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b042  lea     rdx, aImage; "image"
0x18001b049  lea     rcx, [rbp+37h+var_60]; string
0x18001b04d  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x18001b052  lea     r8, [rbp+37h+var_98]
0x18001b056  mov     rdx, [rax]
0x18001b059  mov     rcx, rdi
0x18001b05c  mov     rax, rbx
0x18001b05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b064  mov     rcx, [rbp+3Fh]; this
0x18001b068  test    eax, eax
0x18001b06a  jns     short loc_18001B081
0x18001b06c  mov     r9d, eax; char *
0x18001b06f  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b076  mov     edx, 151h; void *
0x18001b07b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b081  mov     rsi, [rbp+37h+var_90]
0x18001b085  mov     rax, [rsi]
0x18001b088  mov     rdi, [rax+50h]
0x18001b08c  mov     rbx, [rbp+37h+var_98]
0x18001b090  lea     rdx, aItemType; "item-type"
0x18001b097  lea     rcx, [rbp+37h+var_60]; string
0x18001b09b  call    ??$?0$09@StringReference@Internal@Windows@@QEAA@AEAY09$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[10])
0x18001b0a0  lea     r9, [rbp+37h+var_A0]
0x18001b0a4  mov     r8, rbx
0x18001b0a7  mov     rdx, [rax]
0x18001b0aa  mov     rcx, rsi
0x18001b0ad  mov     rax, rdi
0x18001b0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0b5  mov     rcx, [rbp+3Fh]; this
0x18001b0b9  test    eax, eax
0x18001b0bb  jns     short loc_18001B0D2
0x18001b0bd  mov     r9d, eax; char *
0x18001b0c0  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b0c7  mov     edx, 152h; void *
0x18001b0cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b0d2  mov     rdi, [r15]
0x18001b0d5  mov     rax, [rdi]
0x18001b0d8  mov     rbx, [rax+90h]
0x18001b0df  lea     rcx, [rbp+37h+var_98]
0x18001b0e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b0e8  mov     rdx, r12; unsigned __int16 *
0x18001b0eb  lea     rcx, [rbp+37h+var_60]; this
0x18001b0ef  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001b0f4  lea     r8, [rbp+37h+var_98]
0x18001b0f8  mov     rdx, [rbp+37h+var_60]
0x18001b0fc  mov     rcx, rdi
0x18001b0ff  mov     rax, rbx
0x18001b102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b107  mov     rcx, [rbp+3Fh]; this
0x18001b10b  xor     r12d, r12d
0x18001b10e  test    eax, eax
0x18001b110  jns     short loc_18001B127
0x18001b112  mov     r9d, eax; char *
0x18001b115  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b11c  mov     edx, 154h; void *
0x18001b121  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b127  mov     rsi, [rbp+37h+var_90]
0x18001b12b  mov     rax, [rsi]
0x18001b12e  mov     rdi, [rax+50h]
0x18001b132  mov     rbx, [rbp+37h+var_98]
0x18001b136  lea     rdx, aPlacement; "placement"
0x18001b13d  lea     rcx, [rbp+37h+var_60]; string
0x18001b141  call    ??$?0$09@StringReference@Internal@Windows@@QEAA@AEAY09$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[10])
0x18001b146  lea     r9, [rbp+37h+var_A0]
0x18001b14a  mov     r8, rbx
0x18001b14d  mov     rdx, [rax]
0x18001b150  mov     rcx, rsi
0x18001b153  mov     rax, rdi
0x18001b156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b15b  mov     rcx, [rbp+3Fh]; this
0x18001b15f  test    eax, eax
0x18001b161  jns     short loc_18001B178
0x18001b163  mov     r9d, eax; char *
0x18001b166  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b16d  mov     edx, 155h; void *
0x18001b172  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b178  mov     rax, [r14]
0x18001b17b  mov     rbx, [rax+30h]
0x18001b17f  mov     rcx, [rbp+37h+string]; string
0x18001b183  call    cs:__imp_WindowsDeleteString
0x18001b189  mov     [rbp+37h+string], r12
0x18001b18d  lea     rdx, [rbp+37h+string]
0x18001b191  mov     rcx, r14
0x18001b194  mov     rax, rbx
0x18001b197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b19c  mov     rcx, [rbp+3Fh]; this
0x18001b1a0  test    eax, eax
0x18001b1a2  jns     short loc_18001B1B9
0x18001b1a4  mov     r9d, eax; char *
0x18001b1a7  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b1ae  mov     edx, 157h; void *
0x18001b1b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b1b9  mov     rax, [r14]
0x18001b1bc  mov     rbx, [rax+40h]
0x18001b1c0  mov     rcx, [rbp+37h+var_80]; string
0x18001b1c4  call    cs:__imp_WindowsDeleteString
0x18001b1ca  mov     [rbp+37h+var_80], r12
0x18001b1ce  lea     rdx, [rbp+37h+var_80]
0x18001b1d2  mov     rcx, r14
0x18001b1d5  mov     rax, rbx
0x18001b1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1dd  mov     rcx, [rbp+3Fh]; this
0x18001b1e1  test    eax, eax
0x18001b1e3  jns     short loc_18001B1FA
0x18001b1e5  mov     r9d, eax; char *
0x18001b1e8  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b1ef  mov     edx, 158h; void *
0x18001b1f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b1fa  mov     rax, [r14]
0x18001b1fd  mov     rbx, [rax+38h]
0x18001b201  mov     rcx, [rbp+37h+var_88]; string
0x18001b205  call    cs:__imp_WindowsDeleteString
0x18001b20b  mov     [rbp+37h+var_88], r12
0x18001b20f  lea     rdx, [rbp+37h+var_88]
0x18001b213  mov     rcx, r14
0x18001b216  mov     rax, rbx
0x18001b219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b21e  mov     rcx, [rbp+3Fh]; this
0x18001b222  test    eax, eax
0x18001b224  jns     short loc_18001B23B
0x18001b226  mov     r9d, eax; char *
0x18001b229  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b230  mov     edx, 159h; void *
0x18001b235  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b23b  cmp     [rbp+37h+string], r12
0x18001b23f  jz      short loc_18001B29E
0x18001b241  mov     rdi, [r15]
0x18001b244  mov     rax, [rdi]
0x18001b247  mov     rbx, [rax+90h]
0x18001b24e  lea     rcx, [rbp+37h+var_98]
0x18001b252  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b257  lea     r8, [rbp+37h+var_98]
0x18001b25b  mov     rdx, [rbp+37h+string]
0x18001b25f  mov     rcx, rdi
0x18001b262  mov     rax, rbx
0x18001b265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b26a  mov     rsi, [rbp+37h+var_90]
0x18001b26e  mov     rax, [rsi]
0x18001b271  mov     rdi, [rax+50h]
0x18001b275  mov     rbx, [rbp+37h+var_98]
0x18001b279  lea     rdx, aSrc; "src"
0x18001b280  lea     rcx, [rbp+37h+var_60]; string
0x18001b284  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x18001b289  lea     r9, [rbp+37h+var_A0]
0x18001b28d  mov     r8, rbx
0x18001b290  mov     rdx, [rax]
0x18001b293  mov     rcx, rsi
0x18001b296  mov     rax, rdi
0x18001b299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b29e  cmp     [rbp+37h+var_80], r12
0x18001b2a2  jz      short loc_18001B301
0x18001b2a4  mov     rdi, [r15]
0x18001b2a7  mov     rax, [rdi]
0x18001b2aa  mov     rbx, [rax+90h]
0x18001b2b1  lea     rcx, [rbp+37h+var_98]
0x18001b2b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b2ba  lea     r8, [rbp+37h+var_98]
0x18001b2be  mov     rdx, [rbp+37h+var_80]
0x18001b2c2  mov     rcx, rdi
0x18001b2c5  mov     rax, rbx
0x18001b2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2cd  mov     rsi, [rbp+37h+var_90]
0x18001b2d1  mov     rax, [rsi]
0x18001b2d4  mov     rdi, [rax+50h]
0x18001b2d8  mov     rbx, [rbp+37h+var_98]
0x18001b2dc  lea     rdx, aAlt; "alt"
0x18001b2e3  lea     rcx, [rbp+37h+var_60]; string
0x18001b2e7  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x18001b2ec  lea     r9, [rbp+37h+var_A0]
0x18001b2f0  mov     r8, rbx
0x18001b2f3  mov     rdx, [rax]
0x18001b2f6  mov     rcx, rsi
0x18001b2f9  mov     rax, rdi
0x18001b2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b301  mov     rcx, [rbp+37h+var_88]; string
0x18001b305  test    rcx, rcx
0x18001b308  jz      loc_18001B3CF
0x18001b30e  xor     edx, edx; length
0x18001b310  call    cs:__imp_WindowsGetStringRawBuffer
0x18001b316  lea     rdx, aPerson; "person"
0x18001b31d  mov     rcx, rax; String1
0x18001b320  call    wcscmp_0
0x18001b325  mov     rbx, [r15]
0x18001b328  mov     rdi, [rbx]
0x18001b32b  lea     rcx, [rbp+37h+var_98]
0x18001b32f  test    eax, eax
0x18001b331  jnz     short loc_18001B37F
0x18001b333  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b338  lea     rdx, aCircle; "circle"
0x18001b33f  lea     rcx, [rbp+37h+var_60]; string
0x18001b343  call    ??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[7])
0x18001b348  lea     r8, [rbp+37h+var_98]
0x18001b34c  mov     rdx, [rax]
0x18001b34f  mov     rcx, rbx
0x18001b352  mov     rax, [rdi+90h]
0x18001b359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b35e  mov     rsi, [rbp+37h+var_90]
0x18001b362  mov     rax, [rsi]
0x18001b365  mov     rdi, [rax+50h]
0x18001b369  mov     rbx, [rbp+37h+var_98]
0x18001b36d  lea     rdx, aHintCrop; "hint-crop"
0x18001b374  lea     rcx, [rbp+37h+var_60]; string
0x18001b378  call    ??$?0$09@StringReference@Internal@Windows@@QEAA@AEAY09$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[10])
0x18001b37d  jmp     short loc_18001B3BA
0x18001b37f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b384  lea     r8, [rbp+37h+var_98]
0x18001b388  mov     rdx, [rbp+37h+var_88]
0x18001b38c  mov     rcx, rbx
0x18001b38f  mov     rax, [rdi+90h]
0x18001b396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b39b  mov     rsi, [rbp+37h+var_90]
0x18001b39f  mov     rax, [rsi]
0x18001b3a2  mov     rdi, [rax+50h]
0x18001b3a6  mov     rbx, [rbp+37h+var_98]
0x18001b3aa  lea     rdx, aStyle; "style"
0x18001b3b1  lea     rcx, [rbp+37h+var_60]; string
0x18001b3b5  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x18001b3ba  mov     rdx, [rax]
0x18001b3bd  lea     r9, [rbp+37h+var_A0]
0x18001b3c1  mov     r8, rbx
0x18001b3c4  mov     rcx, rsi
0x18001b3c7  mov     rax, rdi
0x18001b3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3cf  mov     [rsp+0E0h+var_A8], 1
0x18001b3d4  mov     eax, [rbp+37h+arg_30]
0x18001b3d7  mov     [rsp+0E0h+var_B0], eax
0x18001b3db  mov     eax, [rbp+37h+arg_28]
0x18001b3de  mov     [rsp+0E0h+var_B8], eax
0x18001b3e2  mov     r9, r13
0x18001b3e5  lea     r8, aSrc; "src"
0x18001b3ec  mov     rdx, [rbp+37h+var_90]
0x18001b3f0  mov     rcx, r15
0x18001b3f3  call    ?ResolveImageElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@_N@Z; NotificationParser::ResolveImageElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,bool)
0x18001b3f8  mov     r9, r13
0x18001b3fb  lea     r8, aAlt; "alt"
0x18001b402  mov     rdx, [rbp+37h+var_90]
0x18001b406  mov     rcx, r15
0x18001b409  call    ?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z; NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)
0x18001b40e  mov     rax, [rbp+37h+var_70]
0x18001b412  mov     [rbp+37h+var_70], r12
0x18001b416  mov     rcx, [rbp+37h+var_68]
0x18001b41a  mov     [rcx], rax
0x18001b41d  mov     rcx, [rbp+37h+var_88]; string
0x18001b421  call    cs:__imp_WindowsDeleteString
0x18001b427  mov     [rbp+37h+var_88], r12
0x18001b42b  mov     rcx, [rbp+37h+var_80]; string
0x18001b42f  call    cs:__imp_WindowsDeleteString
0x18001b435  mov     [rbp+37h+var_80], r12
0x18001b439  mov     rcx, [rbp+37h+string]; string
0x18001b43d  call    cs:__imp_WindowsDeleteString
0x18001b443  mov     [rbp+37h+string], r12
0x18001b447  lea     rcx, [rbp+37h+var_98]
0x18001b44b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b450  nop
0x18001b451  lea     rcx, [rbp+37h+var_90]
0x18001b455  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b45a  nop
0x18001b45b  lea     rcx, [rbp+37h+var_70]
0x18001b45f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b464  mov     rcx, [rbp+37h+var_40]
0x18001b468  xor     rcx, rsp; StackCookie
  ... truncated ...
```
