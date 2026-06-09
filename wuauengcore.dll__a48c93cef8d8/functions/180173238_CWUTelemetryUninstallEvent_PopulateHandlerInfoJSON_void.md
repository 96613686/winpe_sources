# CWUTelemetryUninstallEvent::PopulateHandlerInfoJSON(void)

- ea: `0x180173238`
- end: `0x1801735aa`
- name: `?PopulateHandlerInfoJSON@CWUTelemetryUninstallEvent@@IEAAJXZ`
- size: `882`
- prototype: `__int64 __fastcall(CWUTelemetryUninstallEvent *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180173210`

## callees

- `0x18000def4`
- `0x18007b8a4`
- `0x1800b30b8`
- `0x180110914`
- `0x180113ae8`
- `0x18011fff0`
- `0x180173238`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180173358`
- `OLEAUT32!__imp_SysStringLen` at `0x180173358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801732a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801732eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801733ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801732a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801732eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801733ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017348e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017350e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017348e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017350e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801734d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801734d2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180173325`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180173325`

## string_xrefs

- `0x1801732a1`: `Windows.Data.Json.JsonObject`
- `0x1801732e4`: `Windows.Data.Json.JsonValue`
- `0x1801734f9`: `C:\__w\1\s\src\Client\Engine\Reporting\AsimovInstallEvents.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall CWUTelemetryUninstallEvent::PopulateHandlerInfoJSON(CWUTelemetryUninstallEvent *this)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // ebx
  __int64 v6; // rdx
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  HSTRING v10; // rbx
  __int64 v11; // rcx
  OLECHAR *v12; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD **); // rdi
  _QWORD *v15; // rcx
  __int64 v16; // rax
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v18)(_QWORD, GUID *, _QWORD **); // r14
  _QWORD *v19; // rdi
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  _QWORD *v23; // rcx
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v25)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v26; // rcx
  _QWORD *v27; // rbx
  __int64 (__fastcall *v28)(_QWORD *, HSTRING *); // rdi
  void *v29; // rcx
  PCWSTR StringRawBuffer; // rax
  _QWORD *v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v33; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  __int64 v37; // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v38; // [rsp+48h] [rbp-28h] BYREF
  HSTRING v39; // [rsp+50h] [rbp-20h] BYREF
  __int64 v40; // [rsp+58h] [rbp-18h] BYREF
  __int64 (__fastcall ***v41)(_QWORD, GUID *, _QWORD **); // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( !*((_BYTE *)this + 664) || *((_DWORD *)this + 127) != 4 )
    return 0;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  v39 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    __debugbreak();
  }
  ActivationFactory = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(
                        string,
                        &v41);
  if ( ActivationFactory >= 0 )
  {
    string = 0;
    v7 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
    if ( v7 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
      JUMPOUT(0x1801735A9LL);
    }
    v10 = string;
    v11 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    ActivationFactory = RoGetActivationFactory(v10, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v40);
    if ( ActivationFactory >= 0 )
    {
      if ( *((_DWORD *)this + 127) == 4 )
      {
        v12 = (OLECHAR *)*((_QWORD *)this + 61);
        if ( v12 )
        {
          if ( SysStringLen(v12) )
          {
            v13 = v40;
            v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v40 + 80LL);
            v15 = v38;
            if ( v38 )
            {
              v38 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
            }
            v37 = *((_QWORD *)this + 61);
            v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v37);
            ActivationFactory = v14(v13, *(_QWORD *)(v16 + 24), &v38);
            if ( ActivationFactory < 0 )
            {
              v6 = 475;
              goto LABEL_33;
            }
            v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
            v18 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v41)[7];
            v19 = v38;
            string = 0;
            v20 = WindowsCreateStringReference(L"DriverRecoveryIds", 0x11u, &hstringHeader, &string);
            if ( v20 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
              __debugbreak();
            }
            ActivationFactory = v18(v17, (GUID *)string, v19);
            if ( ActivationFactory < 0 )
            {
              v6 = 476;
              goto LABEL_33;
            }
            v23 = v38;
            if ( v38 )
            {
              v38 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
            }
          }
        }
      }
      v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
      v25 = **v41;
      v26 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
      }
      ActivationFactory = v25(v24, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v38);
      if ( ActivationFactory >= 0 )
      {
        v27 = v38;
        v28 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v38 + 56LL);
        WindowsDeleteString(v39);
        v39 = 0;
        ActivationFactory = v28(v27, &v39);
        if ( ActivationFactory >= 0 )
        {
          v29 = (void *)*((_QWORD *)this + 82);
          if ( v29 )
          {
            SusFree(v29);
            *((_QWORD *)this + 82) = 0;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(v39, 0);
          ActivationFactory = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer, (char *)this + 656);
          if ( ActivationFactory >= 0 )
          {
            ActivationFactory = 0;
            goto LABEL_35;
          }
          v6 = 483;
        }
        else
        {
          v6 = 482;
        }
      }
      else
      {
        v6 = 481;
      }
    }
    else
    {
      v6 = 468;
    }
  }
  else
  {
    v6 = 466;
  }
LABEL_33:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Reporting\\AsimovInstallEvents.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)hstringHeader.Reserved.Reserved1);
LABEL_35:
  WindowsDeleteString(v39);
  v39 = 0;
  v31 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
  }
  v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
  if ( v41 )
  {
    v41 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v32)[2])(v32);
  }
  v33 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180173238  mov     [rsp-18h+arg_8], rbx
0x18017323d  mov     [rsp-18h+arg_10], rsi
0x180173242  mov     [rsp-18h+arg_18], rdi
0x180173247  push    rbp
0x180173248  push    r14
0x18017324a  push    r15
0x18017324c  mov     rbp, rsp
0x18017324f  sub     rsp, 70h
0x180173253  mov     rax, cs:__security_cookie
0x18017325a  xor     rax, rsp
0x18017325d  mov     [rbp+var_8], rax
0x180173261  mov     rsi, rcx
0x180173264  xor     r15d, r15d
0x180173267  cmp     [rcx+298h], r15b
0x18017326e  jz      loc_18017356A
0x180173274  cmp     dword ptr [rcx+1FCh], 4
0x18017327b  jnz     loc_18017356A
0x180173281  mov     [rbp+var_18], r15
0x180173285  mov     [rbp+var_10], r15
0x180173289  mov     [rbp+var_28], r15
0x18017328d  mov     [rbp+var_20], r15
0x180173291  mov     [rbp+string], r15
0x180173295  lea     r9, [rbp+string]; string
0x180173299  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18017329d  lea     edx, [r15+1Ch]; length
0x1801732a1  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x1801732a8  call    cs:__imp_WindowsCreateStringReference
0x1801732ae  test    eax, eax
0x1801732b0  js      loc_18017359A
0x1801732b6  lea     rdx, [rbp+var_10]
0x1801732ba  mov     rcx, [rbp+string]
0x1801732be  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>)
0x1801732c3  mov     ebx, eax
0x1801732c5  test    eax, eax
0x1801732c7  jns     short loc_1801732D3
0x1801732c9  mov     edx, 1D2h
0x1801732ce  jmp     loc_1801734F2
0x1801732d3  mov     [rbp+string], r15
0x1801732d7  lea     r9, [rbp+string]; string
0x1801732db  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1801732df  mov     edx, 1Bh; length
0x1801732e4  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x1801732eb  call    cs:__imp_WindowsCreateStringReference
0x1801732f1  test    eax, eax
0x1801732f3  js      loc_1801735A2
0x1801732f9  mov     rbx, [rbp+string]
0x1801732fd  mov     rcx, [rbp+var_18]
0x180173301  test    rcx, rcx
0x180173304  jz      short loc_180173317
0x180173306  mov     [rbp+var_18], r15
0x18017330a  mov     rax, [rcx]
0x18017330d  mov     rax, [rax+10h]
0x180173311  call    _guard_dispatch_icall
0x180173316  nop
0x180173317  lea     r8, [rbp+var_18]
0x18017331b  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180173322  mov     rcx, rbx
0x180173325  call    cs:__imp_RoGetActivationFactory
0x18017332b  mov     ebx, eax
0x18017332d  test    eax, eax
0x18017332f  jns     short loc_18017333B
0x180173331  mov     edx, 1D4h
0x180173336  jmp     loc_1801734F2
0x18017333b  cmp     dword ptr [rsi+1FCh], 4
0x180173342  jnz     loc_180173438
0x180173348  mov     rcx, [rsi+1E8h]; pbstr
0x18017334f  test    rcx, rcx
0x180173352  jz      loc_180173438
0x180173358  call    cs:__imp_SysStringLen
0x18017335e  test    eax, eax
0x180173360  jz      loc_180173438
0x180173366  mov     rbx, [rbp+var_18]
0x18017336a  mov     rax, [rbx]
0x18017336d  mov     rdi, [rax+50h]
0x180173371  mov     rcx, [rbp+var_28]
0x180173375  test    rcx, rcx
0x180173378  jz      short loc_18017338B
0x18017337a  mov     [rbp+var_28], r15
0x18017337e  mov     rax, [rcx]
0x180173381  mov     rax, [rax+10h]
0x180173385  call    _guard_dispatch_icall
0x18017338a  nop
0x18017338b  mov     rcx, [rsi+1E8h]
0x180173392  mov     [rbp+var_30], rcx
0x180173396  lea     rdx, [rbp+var_30]
0x18017339a  lea     rcx, [rbp+hstringHeader]
0x18017339e  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x1801733a3  nop
0x1801733a4  lea     r8, [rbp+var_28]
0x1801733a8  mov     rdx, [rax+18h]
0x1801733ac  mov     rcx, rbx
0x1801733af  mov     rax, rdi
0x1801733b2  call    _guard_dispatch_icall
0x1801733b7  mov     ebx, eax
0x1801733b9  test    eax, eax
0x1801733bb  jns     short loc_1801733C7
0x1801733bd  mov     edx, 1DBh
0x1801733c2  jmp     loc_1801734F2
0x1801733c7  mov     rbx, [rbp+var_10]
0x1801733cb  mov     rax, [rbx]
0x1801733ce  mov     r14, [rax+38h]
0x1801733d2  mov     rdi, [rbp+var_28]
0x1801733d6  mov     [rbp+string], r15
0x1801733da  lea     r9, [rbp+string]; string
0x1801733de  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1801733e2  mov     edx, 11h; length
0x1801733e7  lea     rcx, aDriverrecovery_2; "DriverRecoveryIds"
0x1801733ee  call    cs:__imp_WindowsCreateStringReference
0x1801733f4  test    eax, eax
0x1801733f6  js      loc_180173592
0x1801733fc  mov     r8, rdi
0x1801733ff  mov     rdx, [rbp+string]
0x180173403  mov     rcx, rbx
0x180173406  mov     rax, r14
0x180173409  call    _guard_dispatch_icall
0x18017340e  mov     ebx, eax
0x180173410  test    eax, eax
0x180173412  jns     short loc_18017341E
0x180173414  mov     edx, 1DCh
0x180173419  jmp     loc_1801734F2
0x18017341e  mov     rcx, [rbp+var_28]
0x180173422  test    rcx, rcx
0x180173425  jz      short loc_180173438
0x180173427  mov     [rbp+var_28], r15
0x18017342b  mov     rax, [rcx]
0x18017342e  mov     rax, [rax+10h]
0x180173432  call    _guard_dispatch_icall
0x180173437  nop
0x180173438  mov     rbx, [rbp+var_10]
0x18017343c  mov     rax, [rbx]
0x18017343f  mov     rdi, [rax]
0x180173442  mov     rcx, [rbp+var_28]
0x180173446  test    rcx, rcx
0x180173449  jz      short loc_18017345C
0x18017344b  mov     [rbp+var_28], r15
0x18017344f  mov     rdx, [rcx]
0x180173452  mov     rax, [rdx+10h]
0x180173456  call    _guard_dispatch_icall
0x18017345b  nop
0x18017345c  lea     r8, [rbp+var_28]
0x180173460  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180173467  mov     rcx, rbx
0x18017346a  mov     rax, rdi
0x18017346d  call    _guard_dispatch_icall
0x180173472  mov     ebx, eax
0x180173474  test    eax, eax
0x180173476  jns     short loc_18017347F
0x180173478  mov     edx, 1E1h
0x18017347d  jmp     short loc_1801734F2
0x18017347f  mov     rbx, [rbp+var_28]
0x180173483  mov     rax, [rbx]
0x180173486  mov     rdi, [rax+38h]
0x18017348a  mov     rcx, [rbp+var_20]; string
0x18017348e  call    cs:__imp_WindowsDeleteString
0x180173494  mov     [rbp+var_20], r15
0x180173498  lea     rdx, [rbp+var_20]
0x18017349c  mov     rcx, rbx
0x18017349f  mov     rax, rdi
0x1801734a2  call    _guard_dispatch_icall
0x1801734a7  mov     ebx, eax
0x1801734a9  test    eax, eax
0x1801734ab  jns     short loc_1801734B4
0x1801734ad  mov     edx, 1E2h
0x1801734b2  jmp     short loc_1801734F2
0x1801734b4  mov     rcx, [rsi+290h]; lpMem
0x1801734bb  test    rcx, rcx
0x1801734be  jz      short loc_1801734CC
0x1801734c0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1801734c5  mov     [rsi+290h], r15
0x1801734cc  xor     edx, edx; length
0x1801734ce  mov     rcx, [rbp+var_20]; string
0x1801734d2  call    cs:__imp_WindowsGetStringRawBuffer
0x1801734d8  lea     rdx, [rsi+290h]
0x1801734df  mov     rcx, rax
0x1801734e2  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x1801734e7  mov     ebx, eax
0x1801734e9  test    eax, eax
0x1801734eb  jns     short loc_180173507
0x1801734ed  mov     edx, 1E3h; void *
0x1801734f2  mov     rcx, [rbp+18h]; this
0x1801734f6  mov     r9d, ebx; char *
0x1801734f9  lea     r8, aCW1SSrcClientE_12; "C:\\__w\\1\\s\\src\\Client\\Engine\\Rep"...
0x180173500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180173505  jmp     short loc_18017350A
0x180173507  mov     ebx, r15d
0x18017350a  mov     rcx, [rbp+var_20]; string
0x18017350e  call    cs:__imp_WindowsDeleteString
0x180173514  mov     [rbp+var_20], r15
0x180173518  mov     rcx, [rbp+var_28]
0x18017351c  test    rcx, rcx
0x18017351f  jz      short loc_180173532
0x180173521  mov     [rbp+var_28], r15
0x180173525  mov     rax, [rcx]
0x180173528  mov     rax, [rax+10h]
0x18017352c  call    _guard_dispatch_icall
0x180173531  nop
0x180173532  mov     rcx, [rbp+var_10]
0x180173536  test    rcx, rcx
0x180173539  jz      short loc_18017354C
0x18017353b  mov     [rbp+var_10], r15
0x18017353f  mov     rax, [rcx]
0x180173542  mov     rax, [rax+10h]
0x180173546  call    _guard_dispatch_icall
0x18017354b  nop
0x18017354c  mov     rcx, [rbp+var_18]
0x180173550  test    rcx, rcx
0x180173553  jz      short loc_180173566
0x180173555  mov     [rbp+var_18], r15
0x180173559  mov     rdx, [rcx]
0x18017355c  mov     rax, [rdx+10h]
0x180173560  call    _guard_dispatch_icall
0x180173565  nop
0x180173566  mov     eax, ebx
0x180173568  jmp     short loc_18017356C
0x18017356a  xor     eax, eax
0x18017356c  mov     rcx, [rbp+var_8]
0x180173570  xor     rcx, rsp; StackCookie
0x180173573  call    __security_check_cookie
0x180173578  lea     r11, [rsp+70h+var_s0]
0x18017357d  mov     rbx, [r11+28h]
0x180173581  mov     rsi, [r11+30h]
0x180173585  mov     rdi, [r11+38h]
0x180173589  mov     rsp, r11
0x18017358c  pop     r15
0x18017358e  pop     r14
0x180173590  pop     rbp
0x180173591  retn
0x180173592  mov     ecx, eax; this
0x180173594  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180173599  int     3; Trap to Debugger
0x18017359a  mov     ecx, eax; this
0x18017359c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1801735a1  int     3; Trap to Debugger
0x1801735a2  mov     ecx, eax; this
0x1801735a4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
