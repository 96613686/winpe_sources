# MSATokenBroker::GetDeviceTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14007bb94`
- end: `0x14007c29a`
- name: `?GetDeviceTicket@MSATokenBroker@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `1798`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14009415c`

## callees

- `0x140005530`
- `0x1400062f0`
- `0x140006338`
- `0x140009858`
- `0x14000ccac`
- `0x14001f6b4`
- `0x140031ba0`
- `0x140060f58`
- `0x140079a50`
- `0x140079b24`
- `0x14007bb94`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14007be54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14007bedf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14007be54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14007bedf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14007be80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14007be80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007bc07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007bca7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007bcf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007bc07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007bca7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007bcf3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007bcc4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007bcc4`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14007bc26`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14007bc26`

## string_xrefs

- `0x14007bc00`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x14007bca0`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int128 *__fastcall MSATokenBroker::GetDeviceTicket(__int128 *a1, _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int v7; // ebx
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // ebx
  _QWORD *v12; // r14
  __int64 v13; // rbx
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  __int64 (__fastcall *v17)(_QWORD *, PVOID, HSTRING, __int64 *); // r15
  HSTRING v18; // rbx
  HSTRING_HEADER *v19; // rax
  int v20; // ebx
  int v21; // ebx
  HRESULT v22; // edx
  int v23; // ebx
  __int64 v24; // r8
  int (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rdi
  int v26; // ebx
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, __int64 *); // rdi
  __int64 v29; // rcx
  int v30; // ebx
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, _QWORD, __int64 *); // rdi
  __int64 v33; // rcx
  int v34; // ebx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, HSTRING *); // rbx
  int v37; // ebx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  int (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v48; // [rsp+30h] [rbp-89h] BYREF
  HSTRING v49; // [rsp+38h] [rbp-81h] BYREF
  __int64 v50; // [rsp+40h] [rbp-79h] BYREF
  __int64 v51; // [rsp+48h] [rbp-71h] BYREF
  __int64 v52; // [rsp+50h] [rbp-69h] BYREF
  __int64 v53; // [rsp+58h] [rbp-61h] BYREF
  int (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-59h] BYREF
  _QWORD *v55; // [rsp+68h] [rbp-51h] BYREF
  __int128 v56; // [rsp+80h] [rbp-39h] BYREF
  __m128i si128; // [rsp+90h] [rbp-29h]
  HSTRING_HEADER pExceptionObject; // [rsp+A0h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+E0h] [rbp+27h] BYREF

  v48 = 0;
  v52 = 0;
  v55 = 0;
  v54 = 0;
  v53 = 0;
  v51 = 0;
  v50 = 0;
  v49 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
         0x41u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    __debugbreak();
  }
  v48 = 0;
  *(_QWORD *)&v56 = 0;
  v7 = RoActivateInstance(string, &v56);
  if ( v7 >= 0 )
  {
    if ( !memcmp_0(&GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v48 = v56;
    }
    else
    {
      v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v56)(
             v56,
             &GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb,
             &v48);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v56 + 16LL))(v56);
    }
  }
  if ( v7 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        37,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v7);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v7);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  string = 0;
  v8 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
         0x45u,
         &hstringHeader,
         &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v55);
  if ( ActivationFactory < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)ActivationFactory);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, ActivationFactory);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v12 = v55;
  v13 = *v55;
  string = 0;
  v14 = WindowsCreateStringReference(L"MBI_SSL", 7u, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
    __debugbreak();
  }
  v17 = *(__int64 (__fastcall **)(_QWORD *, PVOID, HSTRING, __int64 *))(v13 + 48);
  v18 = string;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  *(_QWORD *)&v56 = a2;
  v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&pExceptionObject, (const WCHAR **)&v56, v16);
  v20 = v17(v12, v19[1].Reserved.Reserved1, v18, &v52);
  if ( v20 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        39,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v20);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v20);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v56 = xmmword_1400B8958;
  v21 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v48 + 72LL))(v48, &v56);
  if ( v21 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        40,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v21);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v21);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v48 + 56LL))(v48, v52, &v54);
  if ( v23 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        41,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v23);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v23);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v25 = v54;
  v26 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
          v54,
          v22,
          v24);
  if ( v26 < 0
    || (v26 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v25)[8])(v25, &v53),
        v26 < 0) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        42,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v26);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v26);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v27 = v53;
  v28 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 48LL);
  v29 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v28(v27, &v51);
  if ( v30 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        43,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v30);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v30);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v31 = v51;
  v32 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v51 + 48LL);
  v33 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v32(v31, 0, &v50);
  if ( v34 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        44,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v34);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v34);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v35 = v50;
  v36 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v50 + 48LL);
  WindowsDeleteString(v49);
  v49 = 0;
  v37 = v36(v35, &v49);
  if ( v37 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        45,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v37);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v37);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v49, 0);
  v56 = 0;
  si128 = 0;
  v39 = -1;
  do
    ++v39;
  while ( StringRawBuffer[v39] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v56, StringRawBuffer, v39);
  *a1 = v56;
  a1[1] = (__int128)si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v56) = 0;
  std::wstring::~wstring((char **)&v56);
  WindowsDeleteString(v49);
  v49 = 0;
  v40 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v54;
  if ( v54 )
  {
    v54 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v43)[2])(v43);
  }
  v44 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
  }
  v45 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  return a1;
}

```

## disassembly

```asm
0x14007bb94  mov     [rsp-8+arg_10], rbx
0x14007bb99  mov     [rsp-8+arg_18], rsi
0x14007bb9e  push    rbp
0x14007bb9f  push    rdi
0x14007bba0  push    r12
0x14007bba2  push    r14
0x14007bba4  push    r15
0x14007bba6  lea     rbp, [rsp-37h]
0x14007bbab  sub     rsp, 0F0h
0x14007bbb2  mov     rax, cs:__security_cookie
0x14007bbb9  xor     rax, rsp
0x14007bbbc  mov     [rbp+57h+var_28], rax
0x14007bbc0  mov     rdi, rdx
0x14007bbc3  mov     rsi, rcx
0x14007bbc6  mov     [rbp+57h+var_C0], rcx
0x14007bbca  xor     r12d, r12d
0x14007bbcd  mov     [rsp+110h+var_E0], r12
0x14007bbd2  mov     [rbp+57h+var_C0], r12
0x14007bbd6  mov     [rbp+57h+var_A8], r12
0x14007bbda  mov     [rbp+57h+var_B0], r12
0x14007bbde  mov     [rbp+57h+var_B8], r12
0x14007bbe2  mov     [rbp+57h+var_C8], r12
0x14007bbe6  mov     [rbp+57h+var_D0], r12
0x14007bbea  mov     [rsp+110h+var_D8], r12
0x14007bbef  mov     [rbp+57h+string], r12
0x14007bbf3  lea     r9, [rbp+57h+string]; string
0x14007bbf7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14007bbfb  lea     edx, [r12+41h]; length
0x14007bc00  lea     rcx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x14007bc07  call    cs:__imp_WindowsCreateStringReference
0x14007bc0d  test    eax, eax
0x14007bc0f  js      loc_14007C067
0x14007bc15  mov     [rsp+110h+var_E0], r12
0x14007bc1a  mov     qword ptr [rbp+57h+var_90], r12
0x14007bc1e  lea     rdx, [rbp+57h+var_90]
0x14007bc22  mov     rcx, [rbp+57h+string]
0x14007bc26  call    cs:__imp_RoActivateInstance
0x14007bc2c  mov     ebx, eax
0x14007bc2e  test    eax, eax
0x14007bc30  js      short loc_14007BC87
0x14007bc32  lea     r8d, [r12+10h]; Size
0x14007bc37  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x14007bc3e  lea     rcx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb; Buf1
0x14007bc45  call    memcmp_0
0x14007bc4a  test    eax, eax
0x14007bc4c  jnz     short loc_14007BC59
0x14007bc4e  mov     rax, qword ptr [rbp+57h+var_90]
0x14007bc52  mov     [rsp+110h+var_E0], rax
0x14007bc57  jmp     short loc_14007BC87
0x14007bc59  mov     rcx, qword ptr [rbp+57h+var_90]
0x14007bc5d  mov     rax, [rcx]
0x14007bc60  lea     r8, [rsp+110h+var_E0]
0x14007bc65  lea     rdx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb
0x14007bc6c  mov     rax, [rax]
0x14007bc6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bc74  mov     ebx, eax
0x14007bc76  mov     rcx, qword ptr [rbp+57h+var_90]
0x14007bc7a  mov     rax, [rcx]
0x14007bc7d  mov     rax, [rax+10h]
0x14007bc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bc86  nop
0x14007bc87  test    ebx, ebx
0x14007bc89  js      loc_14007C06F
0x14007bc8f  mov     [rbp+57h+string], r12
0x14007bc93  lea     r9, [rbp+57h+string]; string
0x14007bc97  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14007bc9b  mov     edx, 45h ; 'E'; length
0x14007bca0  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x14007bca7  call    cs:__imp_WindowsCreateStringReference
0x14007bcad  test    eax, eax
0x14007bcaf  js      loc_14007C0BC
0x14007bcb5  lea     r8, [rbp+57h+var_A8]
0x14007bcb9  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x14007bcc0  mov     rcx, [rbp+57h+string]
0x14007bcc4  call    cs:__imp_RoGetActivationFactory
0x14007bcca  mov     ebx, eax
0x14007bccc  test    eax, eax
0x14007bcce  js      loc_14007C0C4
0x14007bcd4  mov     r14, [rbp+57h+var_A8]
0x14007bcd8  mov     rbx, [r14]
0x14007bcdb  mov     [rbp+57h+string], r12
0x14007bcdf  lea     r9, [rbp+57h+string]; string
0x14007bce3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14007bce7  mov     edx, 7; length
0x14007bcec  lea     rcx, aMbiSsl; "MBI_SSL"
0x14007bcf3  call    cs:__imp_WindowsCreateStringReference
0x14007bcf9  test    eax, eax
0x14007bcfb  js      loc_14007C111
0x14007bd01  mov     r15, [rbx+30h]
0x14007bd05  mov     rbx, [rbp+57h+string]
0x14007bd09  cmp     qword ptr [rdi+18h], 7
0x14007bd0e  jbe     short loc_14007BD13
0x14007bd10  mov     rdi, [rdi]
0x14007bd13  mov     qword ptr [rbp+57h+var_90], rdi
0x14007bd17  lea     rdx, [rbp+57h+var_90]
0x14007bd1b  lea     rcx, [rbp+57h+pExceptionObject]
0x14007bd1f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14007bd24  nop
0x14007bd25  lea     r9, [rbp+57h+var_C0]
0x14007bd29  mov     r8, rbx
0x14007bd2c  mov     rdx, [rax+18h]
0x14007bd30  mov     rcx, r14
0x14007bd33  mov     rax, r15
0x14007bd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bd3b  mov     ebx, eax
0x14007bd3d  test    eax, eax
0x14007bd3f  js      loc_14007C119
0x14007bd45  mov     rcx, [rsp+110h+var_E0]
0x14007bd4a  movups  xmm0, cs:xmmword_1400B8958
0x14007bd51  movdqu  [rbp+57h+var_90], xmm0
0x14007bd56  mov     rax, [rcx]
0x14007bd59  lea     rdx, [rbp+57h+var_90]
0x14007bd5d  mov     rax, [rax+48h]
0x14007bd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bd66  mov     ebx, eax
0x14007bd68  test    eax, eax
0x14007bd6a  js      loc_14007C166
0x14007bd70  mov     rcx, [rsp+110h+var_E0]
0x14007bd75  mov     rax, [rcx]
0x14007bd78  lea     r8, [rbp+57h+var_B0]
0x14007bd7c  mov     rdx, [rbp+57h+var_C0]
0x14007bd80  mov     rax, [rax+38h]
0x14007bd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bd89  mov     ebx, eax
0x14007bd8b  test    eax, eax
0x14007bd8d  js      loc_14007C1B3
0x14007bd93  mov     rdi, [rbp+57h+var_B0]
0x14007bd97  mov     rcx, rdi
0x14007bd9a  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)
0x14007bd9f  mov     ebx, eax
0x14007bda1  test    eax, eax
0x14007bda3  js      loc_14007C01A
0x14007bda9  mov     rax, [rdi]
0x14007bdac  lea     rdx, [rbp+57h+var_B8]
0x14007bdb0  mov     rcx, rdi
0x14007bdb3  mov     rax, [rax+40h]
0x14007bdb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bdbc  mov     ebx, eax
0x14007bdbe  test    eax, eax
0x14007bdc0  js      loc_14007C01A
0x14007bdc6  mov     rbx, [rbp+57h+var_B8]
0x14007bdca  mov     rax, [rbx]
0x14007bdcd  mov     rdi, [rax+30h]
0x14007bdd1  mov     rcx, [rbp+57h+var_C8]
0x14007bdd5  test    rcx, rcx
0x14007bdd8  jz      short loc_14007BDEB
0x14007bdda  mov     [rbp+57h+var_C8], r12
0x14007bdde  mov     rax, [rcx]
0x14007bde1  mov     rax, [rax+10h]
0x14007bde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bdea  nop
0x14007bdeb  lea     rdx, [rbp+57h+var_C8]
0x14007bdef  mov     rcx, rbx
0x14007bdf2  mov     rax, rdi
0x14007bdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bdfa  mov     ebx, eax
0x14007bdfc  test    eax, eax
0x14007bdfe  js      loc_14007C200
0x14007be04  mov     rbx, [rbp+57h+var_C8]
0x14007be08  mov     rax, [rbx]
0x14007be0b  mov     rdi, [rax+30h]
0x14007be0f  mov     rcx, [rbp+57h+var_D0]
0x14007be13  test    rcx, rcx
0x14007be16  jz      short loc_14007BE29
0x14007be18  mov     [rbp+57h+var_D0], r12
0x14007be1c  mov     rax, [rcx]
0x14007be1f  mov     rax, [rax+10h]
0x14007be23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007be28  nop
0x14007be29  lea     r8, [rbp+57h+var_D0]
0x14007be2d  xor     edx, edx
0x14007be2f  mov     rcx, rbx
0x14007be32  mov     rax, rdi
0x14007be35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007be3a  mov     ebx, eax
0x14007be3c  test    eax, eax
0x14007be3e  js      loc_14007C24D
0x14007be44  mov     rdi, [rbp+57h+var_D0]
0x14007be48  mov     rax, [rdi]
0x14007be4b  mov     rbx, [rax+30h]
0x14007be4f  mov     rcx, [rsp+110h+var_D8]; string
0x14007be54  call    cs:__imp_WindowsDeleteString
0x14007be5a  mov     [rsp+110h+var_D8], r12
0x14007be5f  lea     rdx, [rsp+110h+var_D8]
0x14007be64  mov     rcx, rdi
0x14007be67  mov     rax, rbx
0x14007be6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007be6f  mov     ebx, eax
0x14007be71  test    eax, eax
0x14007be73  js      loc_14007BFCD
0x14007be79  xor     edx, edx; length
0x14007be7b  mov     rcx, [rsp+110h+var_D8]; string
0x14007be80  call    cs:__imp_WindowsGetStringRawBuffer
0x14007be86  xorps   xmm0, xmm0
0x14007be89  movups  [rbp+57h+var_90], xmm0
0x14007be8d  xorps   xmm1, xmm1
0x14007be90  movdqu  [rbp+57h+var_80], xmm1
0x14007be95  or      r8, 0FFFFFFFFFFFFFFFFh
0x14007be99  inc     r8
0x14007be9c  cmp     [rax+r8*2], r12w
0x14007bea1  jnz     short loc_14007BE99
0x14007bea3  mov     rdx, rax
0x14007bea6  lea     rcx, [rbp+57h+var_90]
0x14007beaa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14007beaf  movups  xmm0, [rbp+57h+var_90]
0x14007beb3  movups  xmmword ptr [rsi], xmm0
0x14007beb6  movups  xmm1, [rbp+57h+var_80]
0x14007beba  movups  xmmword ptr [rsi+10h], xmm1
0x14007bebe  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14007bec6  movdqu  [rbp+57h+var_80], xmm0
0x14007becb  mov     word ptr [rbp+57h+var_90], r12w
0x14007bed0  lea     rcx, [rbp+57h+var_90]
0x14007bed4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14007bed9  nop
0x14007beda  mov     rcx, [rsp+110h+var_D8]; string
0x14007bedf  call    cs:__imp_WindowsDeleteString
0x14007bee5  mov     [rsp+110h+var_D8], r12
0x14007beea  mov     rcx, [rbp+57h+var_D0]
0x14007beee  test    rcx, rcx
0x14007bef1  jz      short loc_14007BF04
0x14007bef3  mov     [rbp+57h+var_D0], r12
0x14007bef7  mov     rax, [rcx]
0x14007befa  mov     rax, [rax+10h]
0x14007befe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bf03  nop
0x14007bf04  mov     rcx, [rbp+57h+var_C8]
0x14007bf08  test    rcx, rcx
0x14007bf0b  jz      short loc_14007BF1E
0x14007bf0d  mov     [rbp+57h+var_C8], r12
0x14007bf11  mov     rax, [rcx]
0x14007bf14  mov     rax, [rax+10h]
0x14007bf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bf1d  nop
0x14007bf1e  mov     rcx, [rbp+57h+var_B8]
0x14007bf22  test    rcx, rcx
0x14007bf25  jz      short loc_14007BF38
0x14007bf27  mov     [rbp+57h+var_B8], r12
0x14007bf2b  mov     rax, [rcx]
0x14007bf2e  mov     rax, [rax+10h]
0x14007bf32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bf37  nop
0x14007bf38  mov     rcx, [rbp+57h+var_B0]
0x14007bf3c  test    rcx, rcx
0x14007bf3f  jz      short loc_14007BF52
0x14007bf41  mov     [rbp+57h+var_B0], r12
0x14007bf45  mov     rax, [rcx]
0x14007bf48  mov     rax, [rax+10h]
0x14007bf4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bf51  nop
0x14007bf52  mov     rcx, [rbp+57h+var_A8]
0x14007bf56  test    rcx, rcx
0x14007bf59  jz      short loc_14007BF6C
0x14007bf5b  mov     [rbp+57h+var_A8], r12
0x14007bf5f  mov     rax, [rcx]
0x14007bf62  mov     rax, [rax+10h]
0x14007bf66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bf6b  nop
0x14007bf6c  mov     rcx, [rbp+57h+var_C0]
0x14007bf70  test    rcx, rcx
0x14007bf73  jz      short loc_14007BF86
0x14007bf75  mov     [rbp+57h+var_C0], r12
0x14007bf79  mov     rax, [rcx]
0x14007bf7c  mov     rax, [rax+10h]
0x14007bf80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bf85  nop
0x14007bf86  mov     rcx, [rsp+110h+var_E0]
0x14007bf8b  test    rcx, rcx
0x14007bf8e  jz      short loc_14007BFA2
0x14007bf90  mov     [rsp+110h+var_E0], r12
0x14007bf95  mov     rdx, [rcx]
0x14007bf98  mov     rax, [rdx+10h]
0x14007bf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bfa1  nop
0x14007bfa2  mov     rax, rsi
0x14007bfa5  mov     rcx, [rbp+57h+var_28]
0x14007bfa9  xor     rcx, rsp; StackCookie
0x14007bfac  call    __security_check_cookie
0x14007bfb1  lea     r11, [rsp+110h+var_20]
0x14007bfb9  mov     rbx, [r11+40h]
0x14007bfbd  mov     rsi, [r11+48h]
0x14007bfc1  mov     rsp, r11
0x14007bfc4  pop     r15
0x14007bfc6  pop     r14
0x14007bfc8  pop     r12
0x14007bfca  pop     rdi
0x14007bfcb  pop     rbp
0x14007bfcc  retn
0x14007bfcd  lea     rax, WPP_GLOBAL_Control
0x14007bfd4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bfdb  cmp     rcx, rax
0x14007bfde  jz      short loc_14007BFFE
0x14007bfe0  test    byte ptr [rcx+1Ch], 1
0x14007bfe4  jz      short loc_14007BFFE
0x14007bfe6  mov     edx, 2Dh ; '-'
0x14007bfeb  mov     r9d, ebx
0x14007bfee  lea     r8, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x14007bff5  mov     rcx, [rcx+10h]
0x14007bff9  call    WPP_SF_d
0x14007bffe  mov     edx, ebx; int
0x14007c000  lea     rcx, [rbp+57h+pExceptionObject]; this
  ... truncated ...
```
