# CWUTelemetryScanEvent::GetAADDeviceTicketInfo(wchar_t * *)

- ea: `0x18015fd94`
- end: `0x180160252`
- name: `?GetAADDeviceTicketInfo@CWUTelemetryScanEvent@@IEAAJPEAPEA_W@Z`
- size: `1214`
- prototype: `__int64 __fastcall(CWUTelemetryScanEvent *__hidden this, wchar_t **)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180160660`
- `0x180161b00`
- `0x1801630b0`
- `0x180163730`
- `0x1801639b0`

## callees

- `0x18000def4`
- `0x18007b8a4`
- `0x180110914`
- `0x180112904`
- `0x180113ae8`
- `0x18011fff0`
- `0x18015fd94`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fe26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fe80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015ff6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015ffc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180160089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fe26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015fe80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015ff6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015ffc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180160089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801601a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801601a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180160171`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180160171`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18015feba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18015feba`

## string_xrefs

- `0x18015fe1f`: `Windows.Data.Json.JsonObject`
- `0x18015fe79`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
__int64 __fastcall CWUTelemetryScanEvent::GetAADDeviceTicketInfo(CWUTelemetryScanEvent *this, wchar_t **a2)
{
  int v4; // ebx
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int v9; // eax
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  HSTRING v13; // rbx
  __int64 v14; // rcx
  int ActivationFactory; // eax
  unsigned int v16; // r8d
  WCHAR *v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, HSTRING, _QWORD **); // rsi
  _QWORD *v21; // rcx
  unsigned __int64 v22; // rdx
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v27)(_QWORD, GUID *, _QWORD **); // r14
  _QWORD *v28; // rsi
  HRESULT v29; // eax
  int v30; // edx
  unsigned int v31; // r8d
  _QWORD *v32; // rdx
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, _QWORD *, _QWORD **); // rsi
  __int64 (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v36)(_QWORD, GUID *, _QWORD **); // r14
  _QWORD *v37; // rsi
  HRESULT v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  _QWORD *v41; // rdx
  __int64 (__fastcall ***v42)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v43)(_QWORD, GUID *, _QWORD **); // rsi
  __int64 v44; // rdx
  _QWORD *v45; // rbx
  __int64 (__fastcall *v46)(_QWORD *, HSTRING *); // rsi
  PCWSTR StringRawBuffer; // rax
  _QWORD *v48; // rcx
  __int64 v49; // rcx
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  PCWSTR sourceString; // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v54; // [rsp+48h] [rbp-28h] BYREF
  __int64 v55; // [rsp+50h] [rbp-20h] BYREF
  HSTRING v56; // [rsp+58h] [rbp-18h] BYREF
  __int64 (__fastcall ***v57)(_QWORD, GUID *, _QWORD **); // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  if ( !a2 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovScanEvents.cpp",
      (const char *)0x80004003LL,
      (int)hstringHeader.Reserved.Reserved1);
    return (unsigned int)v4;
  }
  v57 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v6 < 0 )
    goto LABEL_60;
  v9 = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(
         string,
         &v57);
  v4 = v9;
  if ( v9 >= 0 )
  {
    v55 = 0;
    string = 0;
    v10 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
    if ( v10 < 0 )
    {
LABEL_61:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
      goto LABEL_62;
    }
    v13 = string;
    v14 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    ActivationFactory = RoGetActivationFactory(v13, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v55);
    v4 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovScanEvents.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_53:
      v49 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      goto LABEL_55;
    }
    v54 = 0;
    sourceString = 0;
    v4 = AADDeviceTicketStateToString((CWUTelemetryScanEvent *)((char *)this + 440), (wchar_t **)&sourceString);
    v17 = (WCHAR *)sourceString;
    if ( v4 < 0 )
    {
      v18 = 206;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovScanEvents.cpp",
        (const char *)(unsigned int)v4,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_49:
      if ( v17 )
        SusFree(v17);
      v48 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
      }
      goto LABEL_53;
    }
    v19 = v55;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD **))(*(_QWORD *)v55 + 80LL);
    v21 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    string = 0;
    v22 = -1;
    do
      ++v22;
    while ( v17[v22] );
    if ( v22 <= 0xFFFFFFFF )
    {
      if ( (int)v22 + 1 >= (unsigned int)v22 )
      {
        v23 = WindowsCreateStringReference(v17, v22, &hstringHeader, &string);
        if ( v23 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
          __debugbreak();
        }
        v4 = v20(v19, string, &v54);
        if ( v4 < 0 )
        {
          v18 = 210;
          goto LABEL_35;
        }
        v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
        v27 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v57)[7];
        v28 = v54;
        string = 0;
        v29 = WindowsCreateStringReference(L"Result", 6u, &hstringHeader, &string);
        if ( v29 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v31);
          JUMPOUT(0x180160251LL);
        }
        v4 = v27(v26, (GUID *)string, v28);
        if ( v4 < 0 )
        {
          v18 = 211;
          goto LABEL_35;
        }
        v32 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
          v32 = v54;
        }
        v33 = v55;
        v34 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD **))(*(_QWORD *)v55 + 72LL);
        if ( v32 )
        {
          v54 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
        }
        v4 = v34(v33, v32, &v54);
        if ( v4 < 0 )
        {
          v18 = 215;
          goto LABEL_35;
        }
        v35 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
        v36 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v57)[7];
        v37 = v54;
        string = 0;
        v38 = WindowsCreateStringReference(L"RetryCount", 0xAu, &hstringHeader, &string);
        if ( v38 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
          __debugbreak();
        }
        v4 = v36(v35, (GUID *)string, v37);
        if ( v4 < 0 )
        {
          v18 = 216;
          goto LABEL_35;
        }
        v41 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v41 + 16LL))(v41);
          v41 = v54;
        }
        v56 = 0;
        v42 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
        v43 = **v57;
        if ( v41 )
        {
          v54 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v41 + 16LL))(v41);
        }
        v4 = v43(v42, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v54);
        if ( v4 >= 0 )
        {
          v45 = v54;
          v46 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v54 + 56LL);
          WindowsDeleteString(v56);
          v56 = 0;
          v4 = v46(v45, &v56);
          if ( v4 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v56, 0);
            v4 = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer, a2);
            if ( v4 >= 0 )
            {
              v4 = 0;
              goto LABEL_48;
            }
            v44 = 222;
          }
          else
          {
            v44 = 221;
          }
        }
        else
        {
          v44 = 220;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v44,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovScanEvents.cpp",
          (const char *)(unsigned int)v4,
          (int)hstringHeader.Reserved.Reserved1);
LABEL_48:
        WindowsDeleteString(v56);
        v56 = 0;
        goto LABEL_49;
      }
LABEL_62:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v16);
      __debugbreak();
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v16);
LABEL_60:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    goto LABEL_61;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC3,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovScanEvents.cpp",
    (const char *)(unsigned int)v9,
    (int)hstringHeader.Reserved.Reserved1);
LABEL_55:
  v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
  if ( v57 )
  {
    v57 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v50)[2])(v50);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18015fd94  mov     [rsp-38h+arg_10], rbx
0x18015fd99  push    rbp
0x18015fd9a  push    rsi
0x18015fd9b  push    rdi
0x18015fd9c  push    r12
0x18015fd9e  push    r13
0x18015fda0  push    r14
0x18015fda2  push    r15
0x18015fda4  mov     rbp, rsp
0x18015fda7  sub     rsp, 70h
0x18015fdab  mov     rax, cs:__security_cookie
0x18015fdb2  xor     rax, rsp
0x18015fdb5  mov     [rbp+var_8], rax
0x18015fdb9  mov     r12, rdx
0x18015fdbc  mov     r15, rcx
0x18015fdbf  xor     r13d, r13d
0x18015fdc2  test    rdx, rdx
0x18015fdc5  jnz     short loc_18015FE0A
0x18015fdc7  mov     rcx, [rbp+38h]; this
0x18015fdcb  mov     ebx, 80004003h
0x18015fdd0  mov     r9d, ebx; char *
0x18015fdd3  lea     r8, aCW1SSrcClientE_65; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x18015fdda  mov     edx, 0C0h; void *
0x18015fddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015fde4  mov     eax, ebx
0x18015fde6  mov     rcx, [rbp+var_8]
0x18015fdea  xor     rcx, rsp; StackCookie
0x18015fded  call    __security_check_cookie
0x18015fdf2  mov     rbx, [rsp+70h+arg_10]
0x18015fdfa  add     rsp, 70h
0x18015fdfe  pop     r15
0x18015fe00  pop     r14
0x18015fe02  pop     r13
0x18015fe04  pop     r12
0x18015fe06  pop     rdi
0x18015fe07  pop     rsi
0x18015fe08  pop     rbp
0x18015fe09  retn
0x18015fe0a  mov     [rbp+var_10], r13
0x18015fe0e  mov     [rbp+string], r13
0x18015fe12  lea     r9, [rbp+string]; string
0x18015fe16  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18015fe1a  mov     edx, 1Ch; length
0x18015fe1f  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x18015fe26  call    cs:__imp_WindowsCreateStringReference
0x18015fe2c  test    eax, eax
0x18015fe2e  js      loc_180160227
0x18015fe34  lea     rdx, [rbp+var_10]
0x18015fe38  mov     rcx, [rbp+string]
0x18015fe3c  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>)
0x18015fe41  mov     ebx, eax
0x18015fe43  test    eax, eax
0x18015fe45  jns     short loc_18015FE64
0x18015fe47  mov     rcx, [rbp+38h]; this
0x18015fe4b  mov     r9d, eax; char *
0x18015fe4e  lea     r8, aCW1SSrcClientE_65; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x18015fe55  mov     edx, 0C3h; void *
0x18015fe5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015fe5f  jmp     loc_1801601F5
0x18015fe64  mov     [rbp+var_20], r13
0x18015fe68  mov     [rbp+string], r13
0x18015fe6c  lea     r9, [rbp+string]; string
0x18015fe70  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18015fe74  mov     edx, 1Bh; length
0x18015fe79  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x18015fe80  call    cs:__imp_WindowsCreateStringReference
0x18015fe86  test    eax, eax
0x18015fe88  js      loc_18016022F
0x18015fe8e  mov     rbx, [rbp+string]
0x18015fe92  mov     rcx, [rbp+var_20]
0x18015fe96  test    rcx, rcx
0x18015fe99  jz      short loc_18015FEAC
0x18015fe9b  mov     [rbp+var_20], r13
0x18015fe9f  mov     rax, [rcx]
0x18015fea2  mov     rax, [rax+10h]
0x18015fea6  call    _guard_dispatch_icall
0x18015feab  nop
0x18015feac  lea     r8, [rbp+var_20]
0x18015feb0  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18015feb7  mov     rcx, rbx
0x18015feba  call    cs:__imp_RoGetActivationFactory
0x18015fec0  mov     ebx, eax
0x18015fec2  test    eax, eax
0x18015fec4  jns     short loc_18015FEE3
0x18015fec6  mov     rcx, [rbp+38h]; this
0x18015feca  mov     r9d, eax; char *
0x18015fecd  lea     r8, aCW1SSrcClientE_65; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x18015fed4  mov     edx, 0C7h; void *
0x18015fed9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015fede  jmp     loc_1801601DB
0x18015fee3  mov     [rbp+var_28], r13
0x18015fee7  mov     [rbp+sourceString], r13
0x18015feeb  lea     rcx, [r15+1B8h]; struct tagAADDeviceTicketState *
0x18015fef2  lea     rdx, [rbp+sourceString]; wchar_t **
0x18015fef6  call    ?AADDeviceTicketStateToString@@YAJAEBUtagAADDeviceTicketState@@PEAPEA_W@Z; AADDeviceTicketStateToString(tagAADDeviceTicketState const &,wchar_t * *)
0x18015fefb  mov     ebx, eax
0x18015fefd  mov     rdi, [rbp+sourceString]
0x18015ff01  test    eax, eax
0x18015ff03  jns     short loc_18015FF0F
0x18015ff05  mov     edx, 0CEh
0x18015ff0a  jmp     loc_1801600B4
0x18015ff0f  mov     rbx, [rbp+var_20]
0x18015ff13  mov     rax, [rbx]
0x18015ff16  mov     rsi, [rax+50h]
0x18015ff1a  mov     rcx, [rbp+var_28]
0x18015ff1e  test    rcx, rcx
0x18015ff21  jz      short loc_18015FF34
0x18015ff23  mov     [rbp+var_28], r13
0x18015ff27  mov     rax, [rcx]
0x18015ff2a  mov     rax, [rax+10h]
0x18015ff2e  call    _guard_dispatch_icall
0x18015ff33  nop
0x18015ff34  mov     [rbp+string], r13
0x18015ff38  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18015ff3c  inc     rdx; int
0x18015ff3f  cmp     [rdi+rdx*2], r13w
0x18015ff44  jnz     short loc_18015FF3C
0x18015ff46  mov     eax, 0FFFFFFFFh
0x18015ff4b  cmp     rdx, rax
0x18015ff4e  ja      loc_18016021C
0x18015ff54  lea     eax, [rdx+1]
0x18015ff57  cmp     eax, edx
0x18015ff59  jb      loc_180160237
0x18015ff5f  lea     r9, [rbp+string]; string
0x18015ff63  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18015ff67  mov     rcx, rdi; sourceString
0x18015ff6a  call    cs:__imp_WindowsCreateStringReference
0x18015ff70  test    eax, eax
0x18015ff72  js      loc_180160242
0x18015ff78  lea     r8, [rbp+var_28]
0x18015ff7c  mov     rdx, [rbp+string]
0x18015ff80  mov     rcx, rbx
0x18015ff83  mov     rax, rsi
0x18015ff86  call    _guard_dispatch_icall
0x18015ff8b  mov     ebx, eax
0x18015ff8d  test    eax, eax
0x18015ff8f  jns     short loc_18015FF9B
0x18015ff91  mov     edx, 0D2h
0x18015ff96  jmp     loc_1801600B4
0x18015ff9b  mov     rbx, [rbp+var_10]
0x18015ff9f  mov     rax, [rbx]
0x18015ffa2  mov     r14, [rax+38h]
0x18015ffa6  mov     rsi, [rbp+var_28]
0x18015ffaa  mov     [rbp+string], r13
0x18015ffae  lea     r9, [rbp+string]; string
0x18015ffb2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18015ffb6  mov     edx, 6; length
0x18015ffbb  lea     rcx, aResult; "Result"
0x18015ffc2  call    cs:__imp_WindowsCreateStringReference
0x18015ffc8  test    eax, eax
0x18015ffca  js      loc_18016024A
0x18015ffd0  mov     r8, rsi
0x18015ffd3  mov     rdx, [rbp+string]
0x18015ffd7  mov     rcx, rbx
0x18015ffda  mov     rax, r14
0x18015ffdd  call    _guard_dispatch_icall
0x18015ffe2  mov     ebx, eax
0x18015ffe4  test    eax, eax
0x18015ffe6  jns     short loc_18015FFF2
0x18015ffe8  mov     edx, 0D3h
0x18015ffed  jmp     loc_1801600B4
0x18015fff2  mov     rdx, [rbp+var_28]
0x18015fff6  test    rdx, rdx
0x18015fff9  jz      short loc_180160012
0x18015fffb  mov     [rbp+var_28], r13
0x18015ffff  mov     rax, [rdx]
0x180160002  mov     rcx, rdx
0x180160005  mov     rax, [rax+10h]
0x180160009  call    _guard_dispatch_icall
0x18016000e  mov     rdx, [rbp+var_28]
0x180160012  mov     rbx, [rbp+var_20]
0x180160016  mov     rax, [rbx]
0x180160019  mov     rsi, [rax+48h]
0x18016001d  test    rdx, rdx
0x180160020  jz      short loc_180160036
0x180160022  mov     [rbp+var_28], r13
0x180160026  mov     rcx, [rdx]
0x180160029  mov     rax, [rcx+10h]
0x18016002d  mov     rcx, rdx
0x180160030  call    _guard_dispatch_icall
0x180160035  nop
0x180160036  movzx   ecx, word ptr [r15+1C0h]
0x18016003e  movd    xmm1, ecx
0x180160042  cvtdq2pd xmm1, xmm1
0x180160046  lea     r8, [rbp+var_28]
0x18016004a  mov     rcx, rbx
0x18016004d  mov     rax, rsi
0x180160050  call    _guard_dispatch_icall
0x180160055  mov     ebx, eax
0x180160057  test    eax, eax
0x180160059  jns     short loc_180160062
0x18016005b  mov     edx, 0D7h
0x180160060  jmp     short loc_1801600B4
0x180160062  mov     rbx, [rbp+var_10]
0x180160066  mov     rax, [rbx]
0x180160069  mov     r14, [rax+38h]
0x18016006d  mov     rsi, [rbp+var_28]
0x180160071  mov     [rbp+string], r13
0x180160075  lea     r9, [rbp+string]; string
0x180160079  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18016007d  mov     edx, 0Ah; length
0x180160082  lea     rcx, aRetrycount; "RetryCount"
0x180160089  call    cs:__imp_WindowsCreateStringReference
0x18016008f  test    eax, eax
0x180160091  js      loc_180160214
0x180160097  mov     r8, rsi
0x18016009a  mov     rdx, [rbp+string]
0x18016009e  mov     rcx, rbx
0x1801600a1  mov     rax, r14
0x1801600a4  call    _guard_dispatch_icall
0x1801600a9  mov     ebx, eax
0x1801600ab  test    eax, eax
0x1801600ad  jns     short loc_1801600CC
0x1801600af  mov     edx, 0D8h; void *
0x1801600b4  mov     rcx, [rbp+38h]; this
0x1801600b8  mov     r9d, ebx; char *
0x1801600bb  lea     r8, aCW1SSrcClientE_65; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x1801600c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801600c7  jmp     loc_1801601B3
0x1801600cc  mov     rdx, [rbp+var_28]
0x1801600d0  test    rdx, rdx
0x1801600d3  jz      short loc_1801600EC
0x1801600d5  mov     [rbp+var_28], r13
0x1801600d9  mov     rax, [rdx]
0x1801600dc  mov     rcx, rdx
0x1801600df  mov     rax, [rax+10h]
0x1801600e3  call    _guard_dispatch_icall
0x1801600e8  mov     rdx, [rbp+var_28]
0x1801600ec  mov     [rbp+var_18], r13
0x1801600f0  mov     rbx, [rbp+var_10]
0x1801600f4  mov     rax, [rbx]
0x1801600f7  mov     rsi, [rax]
0x1801600fa  test    rdx, rdx
0x1801600fd  jz      short loc_180160113
0x1801600ff  mov     [rbp+var_28], r13
0x180160103  mov     rcx, [rdx]
0x180160106  mov     rax, [rcx+10h]
0x18016010a  mov     rcx, rdx
0x18016010d  call    _guard_dispatch_icall
0x180160112  nop
0x180160113  lea     r8, [rbp+var_28]
0x180160117  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18016011e  mov     rcx, rbx
0x180160121  mov     rax, rsi
0x180160124  call    _guard_dispatch_icall
0x180160129  mov     ebx, eax
0x18016012b  test    eax, eax
0x18016012d  jns     short loc_180160136
0x18016012f  mov     edx, 0DCh
0x180160134  jmp     short loc_18016018D
0x180160136  mov     rbx, [rbp+var_28]
0x18016013a  mov     rax, [rbx]
0x18016013d  mov     rsi, [rax+38h]
0x180160141  mov     rcx, [rbp+var_18]; string
0x180160145  call    cs:__imp_WindowsDeleteString
0x18016014b  mov     [rbp+var_18], r13
0x18016014f  lea     rdx, [rbp+var_18]
0x180160153  mov     rcx, rbx
0x180160156  mov     rax, rsi
0x180160159  call    _guard_dispatch_icall
0x18016015e  mov     ebx, eax
0x180160160  test    eax, eax
0x180160162  jns     short loc_18016016B
0x180160164  mov     edx, 0DDh
0x180160169  jmp     short loc_18016018D
0x18016016b  xor     edx, edx; length
0x18016016d  mov     rcx, [rbp+var_18]; string
0x180160171  call    cs:__imp_WindowsGetStringRawBuffer
0x180160177  mov     rdx, r12
0x18016017a  mov     rcx, rax
0x18016017d  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x180160182  mov     ebx, eax
0x180160184  test    eax, eax
0x180160186  jns     short loc_1801601A2
0x180160188  mov     edx, 0DEh; void *
0x18016018d  mov     rcx, [rbp+38h]; this
0x180160191  mov     r9d, ebx; char *
0x180160194  lea     r8, aCW1SSrcClientE_65; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x18016019b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801601a0  jmp     short loc_1801601A5
0x1801601a2  mov     ebx, r13d
0x1801601a5  mov     rcx, [rbp+var_18]; string
0x1801601a9  call    cs:__imp_WindowsDeleteString
0x1801601af  mov     [rbp+var_18], r13
0x1801601b3  test    rdi, rdi
0x1801601b6  jz      short loc_1801601C1
0x1801601b8  mov     rcx, rdi; lpMem
0x1801601bb  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1801601c0  nop
0x1801601c1  mov     rcx, [rbp+var_28]
0x1801601c5  test    rcx, rcx
0x1801601c8  jz      short loc_1801601DB
0x1801601ca  mov     [rbp+var_28], r13
0x1801601ce  mov     rax, [rcx]
0x1801601d1  mov     rax, [rax+10h]
0x1801601d5  call    _guard_dispatch_icall
0x1801601da  nop
0x1801601db  mov     rcx, [rbp+var_20]
0x1801601df  test    rcx, rcx
0x1801601e2  jz      short loc_1801601F5
  ... truncated ...
```
