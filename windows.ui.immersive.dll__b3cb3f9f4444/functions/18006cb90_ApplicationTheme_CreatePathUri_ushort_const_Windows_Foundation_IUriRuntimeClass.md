# ApplicationTheme::CreatePathUri(ushort const *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x18006cb90`
- end: `0x18006ce49`
- name: `?CreatePathUri@ApplicationTheme@@YAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `697`
- prototype: `__int64 __fastcall(ApplicationTheme *__hidden this, const unsigned __int16 *, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18004eb60`
- `0x18006e1a0`

## callees

- `0x1800138d4`
- `0x180013f14`
- `0x18004c5e4`
- `0x1800668a8`
- `0x18006cb5c`
- `0x18006cb90`
- `0x18006f60c`
- `0x18006f650`
- `0x18006f694`
- `0x180070600`
- `0x180070724`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006cd66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006cd66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006cc0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006cc46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006cc97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006ccdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006cc0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006cc46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006cc97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006ccdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cd46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cdc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cd46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cdc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18006cd27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18006cd27`

## string_xrefs

- `0x18006cd5f`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall ApplicationTheme::CreatePathUri(
        ApplicationTheme *this,
        unsigned __int16 *a2,
        struct Windows::Foundation::IUriRuntimeClass **a3)
{
  HSTRING v4; // rbx
  struct Windows::Internal::String *v5; // rdx
  HRESULT AppInstallFolderPath; // edi
  HRESULT AppDataFolderPath; // eax
  UINT32 StringLen; // eax
  unsigned int v9; // edx
  struct Windows::Internal::String *v10; // rdx
  UINT32 v11; // eax
  const unsigned __int16 *v12; // rdx
  UINT32 v13; // eax
  unsigned int v14; // edx
  UINT32 v15; // eax
  HRESULT v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING, __int64 *); // rbx
  __int64 v20; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string1; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string2; // [rsp+38h] [rbp-38h] BYREF
  HSTRING v24; // [rsp+40h] [rbp-30h] BYREF
  __int64 v25; // [rsp+48h] [rbp-28h] BYREF
  HSTRING v26; // [rsp+50h] [rbp-20h] BYREF
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF
  __int64 v28; // [rsp+60h] [rbp-10h] BYREF
  HSTRING newString; // [rsp+68h] [rbp-8h] BYREF
  HSTRING v30; // [rsp+A0h] [rbp+30h] BYREF
  HSTRING v31; // [rsp+A8h] [rbp+38h] BYREF

  v31 = 0;
  v4 = 0;
  v24 = 0;
  v28 = 0;
  string2 = 0;
  string = 0;
  v27 = 0;
  string1 = 0;
  v26 = 0;
  v25 = 0;
  v20 = 0;
  v30 = 0;
  if ( this )
  {
    AppInstallFolderPath = Windows::Internal::String::_InitializeHelper(&v31, (const unsigned __int16 *)this);
    if ( AppInstallFolderPath >= 0 )
    {
      AppDataFolderPath = ApplicationThemeHelper::GetAppDataFolderPath(&v24, v5);
      v4 = v24;
      AppInstallFolderPath = AppDataFolderPath;
    }
  }
  else
  {
    AppInstallFolderPath = -2147467261;
  }
  StringLen = WindowsGetStringLen(v4);
  if ( Windows::Internal::String::Substring(
         (Windows::Internal::String *)&v31,
         v9,
         StringLen,
         (struct Windows::Internal::String *)&v28) < 0
    || (unsigned int)Windows::Internal::String::CompareOrdinal(
                       (Windows::Internal::String *)&v24,
                       (const struct Windows::Internal::String *)&v28) )
  {
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    AppInstallFolderPath = ApplicationThemeHelper::GetAppInstallFolderPath(&string, v10);
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    v13 = WindowsGetStringLen(string);
    AppInstallFolderPath = Windows::Internal::String::Substring(
                             (Windows::Internal::String *)&v31,
                             v14,
                             v13,
                             (struct Windows::Internal::String *)&v27);
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                         (Windows::Internal::String *)&string,
                         (const struct Windows::Internal::String *)&v27) )
    {
      AppInstallFolderPath = -2147024809;
      goto LABEL_23;
    }
    v15 = WindowsGetStringLen(string);
    AppInstallFolderPath = Windows::Internal::String::Substring(
                             (Windows::Internal::String *)&v31,
                             v15 + 1,
                             (struct Windows::Internal::String *)&string2);
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    v12 = L"ms-appx:///";
  }
  else
  {
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    v11 = WindowsGetStringLen(v4);
    AppInstallFolderPath = Windows::Internal::String::Substring(
                             (Windows::Internal::String *)&v31,
                             v11 + 1,
                             (struct Windows::Internal::String *)&string2);
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    v12 = L"ms-appdata:///Local/";
  }
  if ( v12 )
    Windows::Internal::String::_InitializeHelper(&string1, v12);
  newString = 0;
  v16 = WindowsConcatString(string1, string2, &newString);
  Windows::Internal::String::FreeAndAssignOnSuccess(v16, newString, &v26);
  WindowsDeleteString(v30);
  v30 = 0;
  AppInstallFolderPath = WindowsCreateString(L"Windows.Foundation.Uri", 0x16u, &v30);
  if ( AppInstallFolderPath >= 0 )
  {
    AppInstallFolderPath = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                             v30,
                             &v25);
    if ( AppInstallFolderPath >= 0 )
    {
      v17 = v25;
      v18 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v25 + 48LL);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v20);
      AppInstallFolderPath = v18(v17, v26, &v20);
      if ( AppInstallFolderPath >= 0 )
      {
        *(_QWORD *)a2 = v20;
        v20 = 0;
      }
    }
  }
LABEL_23:
  WindowsDeleteString(v30);
  v30 = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v25);
  Windows::Internal::String::~String((Windows::Internal::String *)&v26);
  Windows::Internal::String::~String((Windows::Internal::String *)&string1);
  Windows::Internal::String::~String((Windows::Internal::String *)&v27);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Windows::Internal::String::~String((Windows::Internal::String *)&string2);
  Windows::Internal::String::~String((Windows::Internal::String *)&v28);
  Windows::Internal::String::~String((Windows::Internal::String *)&v24);
  Windows::Internal::String::~String((Windows::Internal::String *)&v31);
  return (unsigned int)AppInstallFolderPath;
}

```

## disassembly

```asm
0x18006cb90  mov     [rsp-18h+arg_0], rbx
0x18006cb95  mov     [rsp-18h+arg_8], rsi
0x18006cb9a  push    rbp
0x18006cb9b  push    rdi
0x18006cb9c  push    r14
0x18006cb9e  mov     rbp, rsp
0x18006cba1  sub     rsp, 70h
0x18006cba5  xor     r14d, r14d
0x18006cba8  mov     rsi, rdx
0x18006cbab  mov     [rbp+arg_18], r14
0x18006cbaf  mov     ebx, r14d
0x18006cbb2  mov     [rbp+var_30], rbx
0x18006cbb6  mov     [rbp+var_10], r14
0x18006cbba  mov     [rbp+string2], r14
0x18006cbbe  mov     [rbp+string], r14
0x18006cbc2  mov     [rbp+var_18], r14
0x18006cbc6  mov     [rbp+string1], r14
0x18006cbca  mov     [rbp+var_20], r14
0x18006cbce  mov     [rbp+var_28], r14
0x18006cbd2  mov     [rbp+var_50], r14
0x18006cbd6  mov     [rbp+arg_10], r14
0x18006cbda  test    rcx, rcx
0x18006cbdd  jz      short loc_18006CC02
0x18006cbdf  mov     rdx, rcx; unsigned __int16 *
0x18006cbe2  lea     rcx, [rbp+arg_18]; this
0x18006cbe6  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18006cbeb  mov     edi, eax
0x18006cbed  test    eax, eax
0x18006cbef  js      short loc_18006CC07
0x18006cbf1  lea     rcx, [rbp+var_30]; this
0x18006cbf5  call    ?GetAppDataFolderPath@ApplicationThemeHelper@@YAJPEAVString@Internal@Windows@@@Z; ApplicationThemeHelper::GetAppDataFolderPath(Windows::Internal::String *)
0x18006cbfa  mov     rbx, [rbp+var_30]
0x18006cbfe  mov     edi, eax
0x18006cc00  jmp     short loc_18006CC07
0x18006cc02  mov     edi, 80004003h
0x18006cc07  mov     rcx, rbx; string
0x18006cc0a  call    cs:__imp_WindowsGetStringLen
0x18006cc11  nop     dword ptr [rax+rax+00h]
0x18006cc16  mov     r8d, eax; unsigned int
0x18006cc19  lea     r9, [rbp+var_10]; struct Windows::Internal::String *
0x18006cc1d  lea     rcx, [rbp+arg_18]; this
0x18006cc21  call    ?Substring@String@Internal@Windows@@QEBAJIIPEAV123@@Z; Windows::Internal::String::Substring(uint,uint,Windows::Internal::String *)
0x18006cc26  test    eax, eax
0x18006cc28  js      short loc_18006CC78
0x18006cc2a  lea     rdx, [rbp+var_10]; struct Windows::Internal::String *
0x18006cc2e  lea     rcx, [rbp+var_30]; this
0x18006cc32  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x18006cc37  test    eax, eax
0x18006cc39  jnz     short loc_18006CC78
0x18006cc3b  test    edi, edi
0x18006cc3d  js      loc_18006CDC3
0x18006cc43  mov     rcx, rbx; string
0x18006cc46  call    cs:__imp_WindowsGetStringLen
0x18006cc4d  nop     dword ptr [rax+rax+00h]
0x18006cc52  lea     r8, [rbp+string2]; struct Windows::Internal::String *
0x18006cc56  lea     rcx, [rbp+arg_18]; this
0x18006cc5a  lea     edx, [rax+1]; unsigned int
0x18006cc5d  call    ?Substring@String@Internal@Windows@@QEBAJIPEAV123@@Z; Windows::Internal::String::Substring(uint,Windows::Internal::String *)
0x18006cc62  mov     edi, eax
0x18006cc64  test    eax, eax
0x18006cc66  js      loc_18006CDC3
0x18006cc6c  mov     rdx, cs:off_1800FFEB8; "ms-appdata:///Local/"
0x18006cc73  jmp     loc_18006CD09
0x18006cc78  test    edi, edi
0x18006cc7a  js      loc_18006CDC3
0x18006cc80  lea     rcx, [rbp+string]; this
0x18006cc84  call    ?GetAppInstallFolderPath@ApplicationThemeHelper@@YAJPEAVString@Internal@Windows@@@Z; ApplicationThemeHelper::GetAppInstallFolderPath(Windows::Internal::String *)
0x18006cc89  mov     edi, eax
0x18006cc8b  test    eax, eax
0x18006cc8d  js      loc_18006CDC3
0x18006cc93  mov     rcx, [rbp+string]; string
0x18006cc97  call    cs:__imp_WindowsGetStringLen
0x18006cc9e  nop     dword ptr [rax+rax+00h]
0x18006cca3  mov     r8d, eax; unsigned int
0x18006cca6  lea     r9, [rbp+var_18]; struct Windows::Internal::String *
0x18006ccaa  lea     rcx, [rbp+arg_18]; this
0x18006ccae  call    ?Substring@String@Internal@Windows@@QEBAJIIPEAV123@@Z; Windows::Internal::String::Substring(uint,uint,Windows::Internal::String *)
0x18006ccb3  mov     edi, eax
0x18006ccb5  test    eax, eax
0x18006ccb7  js      loc_18006CDC3
0x18006ccbd  lea     rdx, [rbp+var_18]; struct Windows::Internal::String *
0x18006ccc1  lea     rcx, [rbp+string]; this
0x18006ccc5  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x18006ccca  test    eax, eax
0x18006cccc  jz      short loc_18006CCD8
0x18006ccce  mov     edi, 80070057h
0x18006ccd3  jmp     loc_18006CDC3
0x18006ccd8  mov     rcx, [rbp+string]; string
0x18006ccdc  call    cs:__imp_WindowsGetStringLen
0x18006cce3  nop     dword ptr [rax+rax+00h]
0x18006cce8  lea     r8, [rbp+string2]; struct Windows::Internal::String *
0x18006ccec  lea     rcx, [rbp+arg_18]; this
0x18006ccf0  lea     edx, [rax+1]; unsigned int
0x18006ccf3  call    ?Substring@String@Internal@Windows@@QEBAJIPEAV123@@Z; Windows::Internal::String::Substring(uint,Windows::Internal::String *)
0x18006ccf8  mov     edi, eax
0x18006ccfa  test    eax, eax
0x18006ccfc  js      loc_18006CDC3
0x18006cd02  mov     rdx, cs:off_1800FFEB0; unsigned __int16 *
0x18006cd09  test    rdx, rdx
0x18006cd0c  jz      short loc_18006CD17
0x18006cd0e  lea     rcx, [rbp+string1]; this
0x18006cd12  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18006cd17  mov     rdx, [rbp+string2]; string2
0x18006cd1b  lea     r8, [rbp+newString]; newString
0x18006cd1f  mov     rcx, [rbp+string1]; string1
0x18006cd23  mov     [rbp+newString], r14
0x18006cd27  call    cs:__imp_WindowsConcatString
0x18006cd2e  nop     dword ptr [rax+rax+00h]
0x18006cd33  mov     rdx, [rbp+newString]; HSTRING
0x18006cd37  lea     r8, [rbp+var_20]; HSTRING *
0x18006cd3b  mov     ecx, eax; int
0x18006cd3d  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18006cd42  mov     rcx, [rbp+arg_10]; string
0x18006cd46  call    cs:__imp_WindowsDeleteString
0x18006cd4d  nop     dword ptr [rax+rax+00h]
0x18006cd52  lea     r8, [rbp+arg_10]; string
0x18006cd56  mov     [rbp+arg_10], r14
0x18006cd5a  mov     edx, 16h; length
0x18006cd5f  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18006cd66  call    cs:__imp_WindowsCreateString
0x18006cd6d  nop     dword ptr [rax+rax+00h]
0x18006cd72  mov     edi, eax
0x18006cd74  test    eax, eax
0x18006cd76  js      short loc_18006CDC3
0x18006cd78  mov     rcx, [rbp+arg_10]
0x18006cd7c  lea     rdx, [rbp+var_28]
0x18006cd80  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18006cd85  mov     edi, eax
0x18006cd87  test    eax, eax
0x18006cd89  js      short loc_18006CDC3
0x18006cd8b  mov     rdi, [rbp+var_28]
0x18006cd8f  lea     rcx, [rbp+var_50]
0x18006cd93  mov     rax, [rdi]
0x18006cd96  mov     rbx, [rax+30h]
0x18006cd9a  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006cd9f  mov     rdx, [rbp+var_20]
0x18006cda3  lea     r8, [rbp+var_50]
0x18006cda7  mov     rcx, rdi
0x18006cdaa  mov     rax, rbx
0x18006cdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cdb2  mov     edi, eax
0x18006cdb4  test    eax, eax
0x18006cdb6  js      short loc_18006CDC3
0x18006cdb8  mov     rax, [rbp+var_50]
0x18006cdbc  mov     [rsi], rax
0x18006cdbf  mov     [rbp+var_50], r14
0x18006cdc3  mov     rcx, [rbp+arg_10]; string
0x18006cdc7  call    cs:__imp_WindowsDeleteString
0x18006cdce  nop     dword ptr [rax+rax+00h]
0x18006cdd3  lea     rcx, [rbp+var_50]
0x18006cdd7  mov     [rbp+arg_10], r14
0x18006cddb  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006cde0  lea     rcx, [rbp+var_28]
0x18006cde4  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006cde9  lea     rcx, [rbp+var_20]; this
0x18006cded  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006cdf2  lea     rcx, [rbp+string1]; this
0x18006cdf6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006cdfb  lea     rcx, [rbp+var_18]; this
0x18006cdff  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006ce04  lea     rcx, [rbp+string]; this
0x18006ce08  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006ce0d  lea     rcx, [rbp+string2]; this
0x18006ce11  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006ce16  lea     rcx, [rbp+var_10]; this
0x18006ce1a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006ce1f  lea     rcx, [rbp+var_30]; this
0x18006ce23  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006ce28  lea     rcx, [rbp+arg_18]; this
0x18006ce2c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006ce31  lea     r11, [rsp+70h+var_s0]
0x18006ce36  mov     eax, edi
0x18006ce38  mov     rbx, [r11+20h]
0x18006ce3c  mov     rsi, [r11+28h]
0x18006ce40  mov     rsp, r11
0x18006ce43  pop     r14
0x18006ce45  pop     rdi
0x18006ce46  pop     rbp
0x18006ce47  retn
```
