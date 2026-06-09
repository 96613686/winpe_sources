# _lambda_9821f77c8078defda8eb326c50a5516d_::operator()(IInspectable *)

- ea: `0x18007ac94`
- end: `0x18007b101`
- name: `??R_lambda_9821f77c8078defda8eb326c50a5516d_@@QEBA@PEAUIInspectable@@@Z`
- size: `1133`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007b108`

## callees

- `0x18000f6cc`
- `0x180038608`
- `0x18007a73c`
- `0x18007ac94`
- `0x18007b9b0`
- `0x18007b9dc`
- `0x18007c0f4`
- `0x18007c7e0`
- `0x18007c880`
- `0x1801b6558`
- `0x1801d29a8`
- `0x180249490`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b0cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b0cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ae59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007aeaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007aed1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007af46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007af6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b0e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ae59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007aeaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007aed1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007af46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007af6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b0e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ae12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007af13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007afde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ae12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007af13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007afde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007ad25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007ad7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007ad25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007ad7a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007aee8`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007aee8`

## string_xrefs

- `0x18007afb5`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007aff1`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b010`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b043`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b075`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b098`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007ad73`: `@ShellNewCommandParameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _lambda_9821f77c8078defda8eb326c50a5516d_::operator()(__int64 a1, StateRepoHelpers *a2)
{
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v3; // r15
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(StateRepoHelpers *, GUID *, HSTRING *); // rbx
  int v6; // eax
  unsigned int InfoForShellNewEntry; // ebx
  HSTRING v8; // rbx
  __int64 v9; // rsi
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  int v13; // eax
  HSTRING v14; // rbx
  __int64 v15; // rsi
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  char v19; // bl
  HSTRING v20; // rcx
  HSTRING *v22; // r9
  int v23; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int Reserved1; // edx
  NewMenuEntry *v26; // rcx
  __int64 v27; // rcx
  const WCHAR *v28; // rax
  unsigned int v29; // edx
  NewMenuEntry *v30; // rcx
  __int64 v31; // rax
  NewMenuEntry *v32; // rbx
  const unsigned __int16 *v33; // rax
  StateRepoNewMenuCache *v34; // rcx
  unsigned int v35; // edx
  NewMenuEntry *v36; // rcx
  HSTRING v37; // rcx
  __int64 v38; // rdx
  int v39; // [rsp+20h] [rbp-60h]
  int v40; // [rsp+20h] [rbp-60h]
  int v41; // [rsp+20h] [rbp-60h]
  int v42; // [rsp+20h] [rbp-60h]
  void *v43; // [rsp+30h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  LPWSTR ppwsz; // [rsp+58h] [rbp-28h] BYREF
  char v47; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v48[7]; // [rsp+61h] [rbp-1Fh] BYREF
  HSTRING v49; // [rsp+68h] [rbp-18h] BYREF
  NewMenuEntry *v50; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v3 = **(struct Windows::Internal::StateRepository::IFileTypeAssociation ***)(a1 + 16);
  v4 = *(_QWORD *)(a1 + 8);
  v49 = 0;
  v5 = **(__int64 (__fastcall ***)(StateRepoHelpers *, GUID *, HSTRING *))a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v6 = v5(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v49);
  InfoForShellNewEntry = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v6,
      v39);
    v37 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v37 + 16LL))(v37);
    }
    goto LABEL_36;
  }
  v47 = 0;
  v8 = v49;
  v9 = *(_QWORD *)v49;
  string = 0;
  v10 = WindowsCreateStringReference(L"@ShellNewFileName", 0x11u, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    __debugbreak();
  }
  v13 = (*(__int64 (__fastcall **)(HSTRING, HSTRING, char *))(v9 + 64))(v8, string, &v47);
  InfoForShellNewEntry = v13;
  if ( v13 < 0 )
  {
    v38 = 213;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v13,
      v39);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)InfoForShellNewEntry,
      v42);
    goto LABEL_33;
  }
  v48[0] = 0;
  v14 = v49;
  v15 = *(_QWORD *)v49;
  string = 0;
  v16 = WindowsCreateStringReference(L"@ShellNewCommandParameters", 0x1Au, &hstringHeader, &string);
  if ( v16 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
    __debugbreak();
  }
  v13 = (*(__int64 (__fastcall **)(HSTRING, HSTRING, _BYTE *))(v15 + 64))(v14, string, v48);
  InfoForShellNewEntry = v13;
  if ( v13 < 0 )
  {
    v38 = 215;
    goto LABEL_41;
  }
  if ( v47 || (v19 = 0, v48[0]) )
    v19 = 1;
  v20 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( !v19 )
    return 0;
  v49 = 0;
  WindowsDeleteString(0);
  v49 = 0;
  v23 = StateRepoHelpers::LookupStringInPropertySet(
          a2,
          (struct IInspectable *)&stru_180619028,
          (const unsigned __int16 *)&v49,
          v22);
  InfoForShellNewEntry = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v23,
      v39);
  }
  else
  {
    v50 = 0;
    hstringHeader.Reserved.Reserved1 = &v50;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    StringRawBuffer = WindowsGetStringRawBuffer(v49, 0);
    InfoForShellNewEntry = StateRepoNewMenuCache::GetInfoForShellNewEntry(
                             (StateRepoNewMenuCache *)&hstringHeader.Reserved.Reserved2[8],
                             StringRawBuffer,
                             v3,
                             (struct IInspectable *)a2,
                             (struct NewMenuEntry **)&hstringHeader.Reserved.Reserved2[8]);
    if ( hstringHeader.Reserved.Reserved2[16] )
    {
      Reserved1 = (unsigned int)hstringHeader.Reserved.Reserved1;
      v26 = *(NewMenuEntry **)hstringHeader.Reserved.Reserved1;
      *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
      if ( v26 )
        NewMenuEntry::`scalar deleting destructor'(v26, Reserved1);
    }
    if ( (InfoForShellNewEntry & 0x80000000) == 0 )
    {
      ppwsz = (LPWSTR)WindowsGetStringRawBuffer(v49, 0);
      v27 = *(_QWORD *)(v4 + 16);
      if ( v27
        && (v31 = CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(
                    v27,
                    *(unsigned int *)(v4 + 4),
                    &ppwsz),
            *(_DWORD *)v31 == 1) )
      {
        v32 = *(NewMenuEntry **)(v31 + 16);
        v33 = WindowsGetStringRawBuffer(v49, 0);
        if ( StateRepoNewMenuCache::IsDefaultHandler(v34, v33, v3) )
        {
          ppwsz = (LPWSTR)v50;
          v43 = (void *)WindowsGetStringRawBuffer(v49, 0);
          if ( (int)CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                      v4,
                      0,
                      &v43,
                      &ppwsz) >= 0 )
          {
            if ( v32 )
              NewMenuEntry::`scalar deleting destructor'(v32, v29);
            goto LABEL_29;
          }
        }
      }
      else
      {
        v43 = v50;
        v28 = WindowsGetStringRawBuffer(v49, 0);
        ppwsz = 0;
        if ( SHStrDupW(v28, &ppwsz) >= 0 )
        {
          if ( (int)CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                      v4,
                      1,
                      &ppwsz,
                      &v43) >= 0 )
          {
            v43 = (void *)WindowsGetStringRawBuffer(v49, 0);
            FileExplorerTelemetry::ShellNew_CentennialExtCached<unsigned short const *>(&v43);
LABEL_29:
            v30 = 0;
            goto LABEL_20;
          }
          CoTaskMemFree(ppwsz);
        }
      }
      v30 = v50;
LABEL_20:
      v50 = 0;
      if ( v30 )
        NewMenuEntry::`scalar deleting destructor'(v30, v29);
      WindowsDeleteString(v49);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CE,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)InfoForShellNewEntry,
      v40);
    v36 = v50;
    v50 = 0;
    if ( v36 )
      NewMenuEntry::`scalar deleting destructor'(v36, v35);
  }
  WindowsDeleteString(v49);
LABEL_33:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x205,
    (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
    (const char *)InfoForShellNewEntry,
    v41);
  return InfoForShellNewEntry;
}

```

## disassembly

```asm
0x18007ac94  mov     [rsp-28h+arg_10], rbx
0x18007ac99  mov     [rsp-28h+arg_18], rsi
0x18007ac9e  push    rbp
0x18007ac9f  push    rdi
0x18007aca0  push    r12
0x18007aca2  push    r14
0x18007aca4  push    r15
0x18007aca6  mov     rbp, rsp
0x18007aca9  sub     rsp, 80h
0x18007acb0  mov     rax, cs:__security_cookie
0x18007acb7  xor     rax, rsp
0x18007acba  mov     [rbp+var_8], rax
0x18007acbe  mov     r14, rdx
0x18007acc1  mov     rax, [rcx+10h]
0x18007acc5  mov     r15, [rax]
0x18007acc8  mov     rdi, [rcx+8]
0x18007accc  xor     r12d, r12d
0x18007accf  mov     [rbp+var_18], r12
0x18007acd3  mov     rax, [rdx]
0x18007acd6  mov     rbx, [rax]
0x18007acd9  lea     rcx, [rbp+var_18]
0x18007acdd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ace2  lea     r8, [rbp+var_18]
0x18007ace6  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18007aced  mov     rcx, r14
0x18007acf0  mov     rax, rbx
0x18007acf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007acf8  mov     ebx, eax
0x18007acfa  test    eax, eax
0x18007acfc  js      loc_18007B009
0x18007ad02  mov     [rbp+var_20], r12b
0x18007ad06  mov     rbx, [rbp+var_18]
0x18007ad0a  mov     rsi, [rbx]
0x18007ad0d  mov     [rbp+string], r12
0x18007ad11  lea     r9, [rbp+string]; string
0x18007ad15  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007ad19  lea     edx, [r12+11h]; length
0x18007ad1e  lea     rcx, sourceString; "@ShellNewFileName"
0x18007ad25  call    cs:__imp_WindowsCreateStringReference
0x18007ad2c  nop     dword ptr [rax+rax+00h]
0x18007ad31  test    eax, eax
0x18007ad33  js      loc_18007B056
0x18007ad39  lea     r8, [rbp+var_20]
0x18007ad3d  mov     rdx, [rbp+string]
0x18007ad41  mov     rcx, rbx
0x18007ad44  mov     rax, [rsi+40h]
0x18007ad48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad4d  mov     ebx, eax
0x18007ad4f  test    eax, eax
0x18007ad51  js      loc_18007B05E
0x18007ad57  mov     [rbp+var_1F], r12b
0x18007ad5b  mov     rbx, [rbp+var_18]
0x18007ad5f  mov     rsi, [rbx]
0x18007ad62  mov     [rbp+string], r12
0x18007ad66  lea     r9, [rbp+string]; string
0x18007ad6a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007ad6e  lea     edx, [r12+1Ah]; length
0x18007ad73  lea     rcx, aShellnewcomman; "@ShellNewCommandParameters"
0x18007ad7a  call    cs:__imp_WindowsCreateStringReference
0x18007ad81  nop     dword ptr [rax+rax+00h]
0x18007ad86  test    eax, eax
0x18007ad88  js      loc_18007B065
0x18007ad8e  lea     r8, [rbp+var_1F]
0x18007ad92  mov     rdx, [rbp+string]
0x18007ad96  mov     rcx, rbx
0x18007ad99  mov     rax, [rsi+40h]
0x18007ad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ada2  mov     ebx, eax
0x18007ada4  test    eax, eax
0x18007ada6  js      loc_18007B06D
0x18007adac  cmp     [rbp+var_20], r12b
0x18007adb0  jnz     loc_18007AF24
0x18007adb6  cmp     [rbp+var_1F], r12b
0x18007adba  mov     bl, r12b
0x18007adbd  jnz     loc_18007AF24
0x18007adc3  mov     rcx, [rbp+var_18]
0x18007adc7  test    rcx, rcx
0x18007adca  jz      short loc_18007ADDD
0x18007adcc  mov     [rbp+var_18], r12
0x18007add0  mov     rax, [rcx]
0x18007add3  mov     rax, [rax+10h]
0x18007add7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007addc  nop
0x18007addd  test    bl, bl
0x18007addf  jnz     short loc_18007AE0C
0x18007ade1  xor     eax, eax
0x18007ade3  mov     rcx, [rbp+var_8]
0x18007ade7  xor     rcx, rsp; StackCookie
0x18007adea  call    __security_check_cookie
0x18007adef  lea     r11, [rsp+80h+var_s0]
0x18007adf7  mov     rbx, [r11+40h]
0x18007adfb  mov     rsi, [r11+48h]
0x18007adff  mov     rsp, r11
0x18007ae02  pop     r15
0x18007ae04  pop     r14
0x18007ae06  pop     r12
0x18007ae08  pop     rdi
0x18007ae09  pop     rbp
0x18007ae0a  retn
0x18007ae0c  mov     [rbp+var_18], r12
0x18007ae10  xor     ecx, ecx; string
0x18007ae12  call    cs:__imp_WindowsDeleteString
0x18007ae19  nop     dword ptr [rax+rax+00h]
0x18007ae1e  mov     [rbp+var_18], r12
0x18007ae22  lea     r8, [rbp+var_18]; unsigned __int16 *
0x18007ae26  lea     rdx, stru_180619028; struct IInspectable *
0x18007ae2d  mov     rcx, r14; this
0x18007ae30  call    ?LookupStringInPropertySet@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGPEAPEAUHSTRING__@@@Z; StateRepoHelpers::LookupStringInPropertySet(IInspectable *,ushort const *,HSTRING__ * *)
0x18007ae35  mov     ebx, eax
0x18007ae37  test    eax, eax
0x18007ae39  js      loc_18007B091
0x18007ae3f  mov     [rbp+var_10], r12
0x18007ae43  lea     rax, [rbp+var_10]
0x18007ae47  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x18007ae4b  mov     qword ptr [rbp+hstringHeader.Reserved+8], r12
0x18007ae4f  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x18007ae53  xor     edx, edx; length
0x18007ae55  mov     rcx, [rbp+var_18]; string
0x18007ae59  call    cs:__imp_WindowsGetStringRawBuffer
0x18007ae60  nop     dword ptr [rax+rax+00h]
0x18007ae65  lea     rcx, [rbp+hstringHeader.Reserved+8]; this
0x18007ae69  mov     qword ptr [rsp+80h+var_60], rcx; int
0x18007ae6e  mov     r9, r14; struct IInspectable *
0x18007ae71  mov     r8, r15; struct Windows::Internal::StateRepository::IFileTypeAssociation *
0x18007ae74  mov     rdx, rax; unsigned __int16 *
0x18007ae77  call    ?GetInfoForShellNewEntry@StateRepoNewMenuCache@@AEAAJPEBGPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@PEAUIInspectable@@PEAPEAUNewMenuEntry@@@Z; StateRepoNewMenuCache::GetInfoForShellNewEntry(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation *,IInspectable *,NewMenuEntry * *)
0x18007ae7c  mov     ebx, eax
0x18007ae7e  cmp     byte ptr [rbp+hstringHeader.Reserved+10h], r12b
0x18007ae82  jz      short loc_18007AE9C
0x18007ae84  mov     rdx, qword ptr [rbp+hstringHeader.Reserved]; unsigned int
0x18007ae88  mov     rcx, [rdx]; this
0x18007ae8b  mov     rax, qword ptr [rbp+hstringHeader.Reserved+8]
0x18007ae8f  mov     [rdx], rax
0x18007ae92  test    rcx, rcx
0x18007ae95  jz      short loc_18007AE9C
0x18007ae97  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007ae9c  test    ebx, ebx
0x18007ae9e  js      loc_18007AFAE
0x18007aea4  xor     edx, edx; length
0x18007aea6  mov     rcx, [rbp+var_18]; string
0x18007aeaa  call    cs:__imp_WindowsGetStringRawBuffer
0x18007aeb1  nop     dword ptr [rax+rax+00h]
0x18007aeb6  mov     [rbp+ppwsz], rax
0x18007aeba  mov     rcx, [rdi+10h]
0x18007aebe  test    rcx, rcx
0x18007aec1  jnz     short loc_18007AF2B
0x18007aec3  mov     rax, [rbp+var_10]
0x18007aec7  mov     [rbp+var_50], rax
0x18007aecb  xor     edx, edx; length
0x18007aecd  mov     rcx, [rbp+var_18]; string
0x18007aed1  call    cs:__imp_WindowsGetStringRawBuffer
0x18007aed8  nop     dword ptr [rax+rax+00h]
0x18007aedd  mov     [rbp+ppwsz], r12
0x18007aee1  lea     rdx, [rbp+ppwsz]; ppwsz
0x18007aee5  mov     rcx, rax; psz
0x18007aee8  call    cs:__imp_SHStrDupW
0x18007aeef  nop     dword ptr [rax+rax+00h]
0x18007aef4  test    eax, eax
0x18007aef6  jns     loc_18007B0AE
0x18007aefc  mov     rcx, [rbp+var_10]; this
0x18007af00  mov     [rbp+var_10], r12
0x18007af04  test    rcx, rcx
0x18007af07  jz      short loc_18007AF0F
0x18007af09  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007af0e  nop
0x18007af0f  mov     rcx, [rbp+var_18]; string
0x18007af13  call    cs:__imp_WindowsDeleteString
0x18007af1a  nop     dword ptr [rax+rax+00h]
0x18007af1f  jmp     loc_18007ADE1
0x18007af24  mov     bl, 1
0x18007af26  jmp     loc_18007ADC3
0x18007af2b  lea     r8, [rbp+ppwsz]
0x18007af2f  mov     edx, [rdi+4]
0x18007af32  call    ?s_LookupEntry@?$CSimpleHashTable@PEBGPEAUNewMenuEntry@@VCCaseInsensitiveStringHashPolicy@@VCCaseInsensitiveStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@CAAEAVHashBucket@1@PEAV21@IAEBQEBG@Z; CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::HashBucket *,uint,ushort const * const &)
0x18007af37  cmp     dword ptr [rax], 1
0x18007af3a  jnz     short loc_18007AEC3
0x18007af3c  mov     rbx, [rax+10h]
0x18007af40  xor     edx, edx; length
0x18007af42  mov     rcx, [rbp+var_18]; string
0x18007af46  call    cs:__imp_WindowsGetStringRawBuffer
0x18007af4d  nop     dword ptr [rax+rax+00h]
0x18007af52  mov     r8, r15; struct Windows::Internal::StateRepository::IFileTypeAssociation *
0x18007af55  mov     rdx, rax; unsigned __int16 *
0x18007af58  call    ?IsDefaultHandler@StateRepoNewMenuCache@@AEAA_NPEBGPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@@Z; StateRepoNewMenuCache::IsDefaultHandler(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation *)
0x18007af5d  test    al, al
0x18007af5f  jz      short loc_18007AEFC
0x18007af61  mov     rax, [rbp+var_10]
0x18007af65  mov     [rbp+ppwsz], rax
0x18007af69  xor     edx, edx; length
0x18007af6b  mov     rcx, [rbp+var_18]; string
0x18007af6f  call    cs:__imp_WindowsGetStringRawBuffer
0x18007af76  nop     dword ptr [rax+rax+00h]
0x18007af7b  mov     [rbp+var_50], rax
0x18007af7f  lea     r9, [rbp+ppwsz]
0x18007af83  lea     r8, [rbp+var_50]
0x18007af87  xor     edx, edx
0x18007af89  mov     rcx, rdi
0x18007af8c  call    ?_AddUpdateItem@?$CSimpleHashTable@PEBGPEAUNewMenuEntry@@VCCaseInsensitiveStringHashPolicy@@VCCaseInsensitiveStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBQEBGAEBQEAUNewMenuEntry@@PEAPEAU2@@Z; CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,ushort const * const &,NewMenuEntry * const &,NewMenuEntry * *)
0x18007af91  test    eax, eax
0x18007af93  js      loc_18007AEFC
0x18007af99  test    rbx, rbx
0x18007af9c  jz      short loc_18007AFA6
0x18007af9e  mov     rcx, rbx; this
0x18007afa1  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007afa6  mov     rcx, r12
0x18007afa9  jmp     loc_18007AF00
0x18007afae  mov     rcx, [rbp+28h]; this
0x18007afb2  mov     r9d, ebx; char *
0x18007afb5  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007afbc  mov     edx, 1CEh; void *
0x18007afc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007afc6  nop
0x18007afc7  mov     rcx, [rbp+var_10]; this
0x18007afcb  mov     [rbp+var_10], r12
0x18007afcf  test    rcx, rcx
0x18007afd2  jz      short loc_18007AFDA
0x18007afd4  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007afd9  nop
0x18007afda  mov     rcx, [rbp+var_18]; string
0x18007afde  call    cs:__imp_WindowsDeleteString
0x18007afe5  nop     dword ptr [rax+rax+00h]
0x18007afea  mov     rcx, [rbp+28h]; this
0x18007afee  mov     r9d, ebx; char *
0x18007aff1  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007aff8  mov     edx, 205h; void *
0x18007affd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b002  mov     eax, ebx
0x18007b004  jmp     loc_18007ADE3
0x18007b009  mov     rcx, [rbp+28h]; this
0x18007b00d  mov     r9d, eax; char *
0x18007b010  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007b017  mov     edx, 0D0h; void *
0x18007b01c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b021  nop
0x18007b022  mov     rcx, [rbp+var_18]
0x18007b026  test    rcx, rcx
0x18007b029  jz      short loc_18007B03C
0x18007b02b  mov     [rbp+var_18], r12
0x18007b02f  mov     rax, [rcx]
0x18007b032  mov     rax, [rax+10h]
0x18007b036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b03b  nop
0x18007b03c  mov     rcx, [rbp+28h]; this
0x18007b040  mov     r9d, ebx; char *
0x18007b043  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007b04a  mov     edx, 1C6h; void *
0x18007b04f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b054  jmp     short loc_18007AFEA
0x18007b056  mov     ecx, eax; this
0x18007b058  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007b05d  int     3; Trap to Debugger
0x18007b05e  mov     edx, 0D5h
0x18007b063  jmp     short loc_18007B072
0x18007b065  mov     ecx, eax; this
0x18007b067  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007b06c  int     3; Trap to Debugger
0x18007b06d  mov     edx, 0D7h; void *
0x18007b072  mov     r9d, eax; char *
0x18007b075  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007b07c  mov     rcx, [rbp+28h]; this
0x18007b080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b085  nop
0x18007b086  lea     rcx, [rbp+var_18]
0x18007b08a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b08f  jmp     short loc_18007B03C
0x18007b091  mov     rcx, [rbp+28h]; this
0x18007b095  mov     r9d, eax; char *
0x18007b098  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007b09f  mov     edx, 1CBh; void *
0x18007b0a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b0a9  jmp     loc_18007AFDA
0x18007b0ae  lea     r9, [rbp+var_50]
0x18007b0b2  lea     r8, [rbp+ppwsz]
0x18007b0b6  mov     edx, 1
0x18007b0bb  mov     rcx, rdi
0x18007b0be  call    ?_AddUpdateItem@?$CSimpleHashTable@PEBGPEAUNewMenuEntry@@VCCaseInsensitiveStringHashPolicy@@VCCaseInsensitiveStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBQEBGAEBQEAUNewMenuEntry@@PEAPEAU2@@Z; CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,ushort const * const &,NewMenuEntry * const &,NewMenuEntry * *)
0x18007b0c3  test    eax, eax
0x18007b0c5  jns     short loc_18007B0DC
0x18007b0c7  mov     rcx, [rbp+ppwsz]; pv
0x18007b0cb  call    cs:__imp_CoTaskMemFree
0x18007b0d2  nop     dword ptr [rax+rax+00h]
0x18007b0d7  jmp     loc_18007AEFC
0x18007b0dc  xor     edx, edx; length
0x18007b0de  mov     rcx, [rbp+var_18]; string
0x18007b0e2  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b0e9  nop     dword ptr [rax+rax+00h]
0x18007b0ee  mov     [rbp+var_50], rax
0x18007b0f2  lea     rcx, [rbp+var_50]
0x18007b0f6  call    ??$ShellNew_CentennialExtCached@PEBG@FileExplorerTelemetry@@SAX$$QEAPEBG@Z; FileExplorerTelemetry::ShellNew_CentennialExtCached<ushort const *>(ushort const * &&)
0x18007b0fb  jmp     loc_18007AFA6
```
