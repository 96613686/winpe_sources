# CPackagedComCatalog::CalculateClassBinaryAndCommandLineProperties(IUserTokenInternal *,OpaqueString const &,_GUID const &,tagCLSCTX,ComClassRegistrationEntryProperties const &,CPackagedComCatalog::CServerRegistration const *,OpaqueString &,OpaqueString &,CPackagedComCatalog::ExecutablePathAndCommandLine &)

- ea: `0x18000c674`
- end: `0x18000cda4`
- name: `?CalculateClassBinaryAndCommandLineProperties@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@AEBVOpaqueString@@AEBU_GUID@@W4tagCLSCTX@@AEBUComClassRegistrationEntryProperties@@PEBVCServerRegistration@1@AEAV3@6AEAUExecutablePathAndCommandLine@1@@Z`
- size: `1840`
- prototype: `__int64 __fastcall(struct IUserTokenInternal *, const struct OpaqueString *, const struct _GUID *, enum tagCLSCTX, const struct ComClassRegistrationEntryProperties *, const struct CPackagedComCatalog::CServerRegistration *, struct OpaqueString *, struct OpaqueString *, struct CPackagedComCatalog::ExecutablePathAndCommandLine *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c278`

## callees

- `0x18000ae40`
- `0x18000bbe8`
- `0x18000c674`
- `0x18000cdac`
- `0x18000cdc8`
- `0x18000ce4c`
- `0x18000ce7c`
- `0x18000cf24`
- `0x18000cfcc`
- `0x18000d0dc`
- `0x18000ee80`
- `0x18002ba28`
- `0x1800414d0`
- `0x180042270`
- `0x18004c030`
- `0x18008e98c`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cc7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c98a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c98a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c8d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c908`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c7ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c8d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c908`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000cb76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000cb76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18000c95d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18000ca85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18000c95d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18000ca85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18000c855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18000cab6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18000c855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18000cab6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c895`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cae4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c895`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cae4`

## string_xrefs

- `0x18000c8ad`: ` /Processid:`
- `0x18000c983`: `DllHost.exe`
- `0x18000ca67`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18000cbab`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18000cc12`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18000cc99`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18000ccc9`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18000cd2e`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::CalculateClassBinaryAndCommandLineProperties(
        struct IUserTokenInternal *a1,
        const struct OpaqueString *a2,
        struct _GUID *a3,
        enum tagCLSCTX a4,
        HSTRING *a5,
        HSTRING *a6,
        HSTRING *a7,
        struct OpaqueString *a8,
        HSTRING *a9)
{
  struct IUserTokenInternal *v9; // rbx
  char v10; // r12
  HSTRING v11; // rcx
  HSTRING *v12; // r14
  __int64 v13; // rcx
  int PackagedFilePath; // eax
  unsigned int v15; // ebx
  const WCHAR *StringRawBuffer; // rax
  CPackagedComCatalog::CServerRegistration *v17; // rcx
  HSTRING *v18; // rbx
  HSTRING *v19; // rbx
  PCWSTR v20; // r12
  UINT32 v21; // r15d
  HRESULT v22; // eax
  GUID *v23; // rcx
  int v24; // eax
  HSTRING_BUFFER v25; // rcx
  HSTRING *v26; // rdi
  HRESULT v28; // eax
  HSTRING v29; // rbx
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  HSTRING *ExecutableAbsolutePath; // rbx
  HSTRING *CommandLineW; // rbx
  HSTRING v34; // rcx
  UINT32 v35; // edi
  HRESULT hstring_from_buffer_nothrow; // eax
  HSTRING v37; // rbx
  int SystemFilePath; // eax
  HSTRING v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rdx
  HSTRING_BUFFER *p_bufferHandle; // rcx
  __int64 v44; // rdx
  int v45; // eax
  OLECHAR *v46; // [rsp+20h] [rbp-E0h]
  HSTRING_BUFFER bufferHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v48; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 length; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v51; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_BUFFER v52; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v53; // [rsp+60h] [rbp-A0h] BYREF
  struct OpaqueString *v54; // [rsp+68h] [rbp-98h]
  enum tagCLSCTX v55; // [rsp+70h] [rbp-90h]
  struct IUserTokenInternal *v56; // [rsp+78h] [rbp-88h]
  WCHAR *charBuffer; // [rsp+80h] [rbp-80h] BYREF
  struct OpaqueString *v58; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-70h] BYREF
  HSTRING v60; // [rsp+A8h] [rbp-58h] BYREF
  OLECHAR v61[40]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[40]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v9 = a1;
  v10 = a4;
  v56 = a1;
  v11 = *a7;
  v55 = a4;
  v53 = (HSTRING)a3;
  v54 = a2;
  v58 = a8;
  WindowsDeleteString(v11);
  *a7 = 0;
  WindowsDeleteString(*(HSTRING *)a8);
  *(_QWORD *)a8 = 0;
  WindowsDeleteString(*a9);
  *a9 = 0;
  v12 = a9 + 1;
  WindowsDeleteString(a9[1]);
  a9[1] = 0;
  v48 = 0;
  if ( !a6 )
    goto LABEL_19;
  if ( !*((_BYTE *)a6 + 184) )
  {
    ExecutableAbsolutePath = (HSTRING *)CPackagedComCatalog::CServerRegistration::GetExecutableAbsolutePath(a6, &v53);
    WindowsDeleteString(*a9);
    *a9 = 0;
    *a9 = *ExecutableAbsolutePath;
    *ExecutableAbsolutePath = 0;
    WindowsDeleteString(v53);
    CommandLineW = (HSTRING *)CPackagedComCatalog::CServerRegistration::GetCommandLineW(a6, &v53);
    WindowsDeleteString(*v12);
    *v12 = 0;
    *v12 = *CommandLineW;
    *CommandLineW = 0;
    WindowsDeleteString(v53);
    v9 = v56;
    goto LABEL_19;
  }
  if ( (v10 & 4) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
  v51 = 0;
  PackagedFilePath = CPackagedComCatalog::GetPackagedFilePath(v9, (HSTRING *)v54, a5 + 31, a7);
  v15 = PackagedFilePath;
  if ( PackagedFilePath < 0 )
  {
    v31 = 6673;
    goto LABEL_43;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*a7, 0);
  PackagedFilePath = CoGetModuleArchitecture(StringRawBuffer, &v48);
  v15 = PackagedFilePath;
  if ( PackagedFilePath < 0 )
  {
    v31 = 6675;
    goto LABEL_43;
  }
  if ( CPackagedComCatalog::CServerRegistration::HasSystemSurrogate((CPackagedComCatalog::CServerRegistration *)a6) )
  {
    if ( CPackagedComCatalog::CServerRegistration::HasCustomSurrogate(v17) )
    {
      if ( *((_BYTE *)a6 + 136) )
        v37 = a6[18];
      else
        v37 = 0;
      WindowsDeleteString(0);
      bufferHandle = 0;
      WindowsDuplicateString(v37, (HSTRING *)&bufferHandle);
      WindowsDeleteString(0);
      v29 = (HSTRING)bufferHandle;
      WindowsDeleteString((HSTRING)bufferHandle);
      bufferHandle = 0;
    }
    else
    {
      v60 = 0;
      v28 = WindowsCreateStringReference(L"DllHost.exe", 0xBu, &hstringHeader, &v60);
      if ( v28 < 0 )
      {
        RaiseException(v28, 1u, 0, 0);
        __debugbreak();
      }
      v29 = v60;
      v60 = 0;
    }
    PackagedFilePath = CPackagedComCatalog::GetSystemFilePath(v48, v29, a9);
    v15 = PackagedFilePath;
    if ( PackagedFilePath >= 0 )
    {
      string = 0;
      v15 = CPackagedComCatalog::ConstructCommandLine(a9, &string, &v51);
      WindowsDeleteString(0);
      if ( (v15 & 0x80000000) == 0 )
        goto LABEL_9;
      v30 = v15;
      v31 = 6689;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)v30,
        (int)v46);
      goto LABEL_32;
    }
    v31 = 6687;
LABEL_43:
    v30 = (unsigned int)PackagedFilePath;
    goto LABEL_44;
  }
  v18 = (HSTRING *)CPackagedComCatalog::CServerRegistration::GetExecutableAbsolutePath(v17, &string);
  WindowsDeleteString(*a9);
  *a9 = 0;
  *a9 = *v18;
  *v18 = 0;
  WindowsDeleteString(string);
  v19 = (HSTRING *)CPackagedComCatalog::CServerRegistration::GetCommandLineW(a6, &string);
  WindowsDeleteString(v51);
  v51 = 0;
  v51 = *v19;
  *v19 = 0;
  WindowsDeleteString(string);
LABEL_9:
  length = 0;
  v20 = WindowsGetStringRawBuffer(v51, &length);
  if ( CPackagedComCatalog::CServerRegistration::HasCustomSurrogate((CPackagedComCatalog::CServerRegistration *)a6) )
  {
    v35 = length;
    charBuffer = 0;
    v52 = 0;
    hstring_from_buffer_nothrow = WindowsPreallocateStringBuffer(length + 50, &charBuffer, &v52);
    v15 = hstring_from_buffer_nothrow;
    if ( hstring_from_buffer_nothrow < 0 )
    {
      v42 = 6709;
    }
    else
    {
      memset_0(v61, 0, 0x4Eu);
      StringFromGUID2((const GUID *const)v53, v61, 39);
      v46 = v61;
      hstring_from_buffer_nothrow = StringCchPrintfW(charBuffer, v35 + 51, L"%s %s%s", v20);
      v15 = hstring_from_buffer_nothrow;
      if ( hstring_from_buffer_nothrow < 0 )
      {
        v42 = 6714;
      }
      else
      {
        WindowsDeleteString(*v12);
        *v12 = 0;
        hstring_from_buffer_nothrow = wil::make_hstring_from_buffer_nothrow(&v52, v12);
        v15 = hstring_from_buffer_nothrow;
        if ( hstring_from_buffer_nothrow >= 0 )
        {
          v25 = v52;
          goto LABEL_16;
        }
        v42 = 6716;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)hstring_from_buffer_nothrow,
      (int)v46);
    p_bufferHandle = &v52;
  }
  else
  {
    v21 = length;
    string = 0;
    bufferHandle = 0;
    v22 = WindowsPreallocateStringBuffer(length + 50, (WCHAR **)&string, &bufferHandle);
    v15 = v22;
    if ( v22 < 0 )
    {
      v44 = 6727;
    }
    else
    {
      memset_0(sz, 0, 0x4Eu);
      v23 = (GUID *)((char *)a6 + 188);
      if ( !*((_BYTE *)a6 + 184) )
        v23 = &GUID_NULL;
      StringFromGUID2(v23, sz, 39);
      v46 = (OLECHAR *)L" /Processid:";
      v24 = StringCchPrintfW((unsigned __int16 *)string, v21 + 51, L"%s%s%s", v20);
      v15 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A4D,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v24,
          (int)L" /Processid:");
        if ( bufferHandle )
          WindowsDeleteStringBuffer(bufferHandle);
        goto LABEL_32;
      }
      WindowsDeleteString(*v12);
      *v12 = 0;
      v22 = wil::make_hstring_from_buffer_nothrow(&bufferHandle, v12);
      v15 = v22;
      if ( v22 >= 0 )
      {
        v25 = bufferHandle;
LABEL_16:
        if ( v25 )
          WindowsDeleteStringBuffer(v25);
        WindowsDeleteString(v51);
        v10 = v55;
        v9 = v56;
LABEL_19:
        if ( (v10 & 2) != 0 )
        {
          if ( g_bInSCM )
            MicrosoftTelemetryAssertTriggeredNoArgs(v13);
          v26 = (HSTRING *)v54;
          if ( *((_BYTE *)a5 + 360) )
          {
            v45 = CPackagedComCatalog::GetPackagedFilePath(v9, (HSTRING *)v54, a5 + 46, (HSTRING *)v58);
            v15 = v45;
            if ( v45 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A65,
                (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
                (const char *)(unsigned int)v45,
                (int)v46);
              return v15;
            }
          }
        }
        else
        {
          v26 = (HSTRING *)v54;
        }
        if ( (v10 & 1) != 0 )
        {
          if ( g_bInSCM )
            MicrosoftTelemetryAssertTriggeredNoArgs(v13);
          if ( *((_BYTE *)a5 + 288) )
          {
            bufferHandle = 0;
            if ( *((_BYTE *)a5 + 336) && *((_BYTE *)a5 + 337) )
            {
              SystemFilePath = CPackagedComCatalog::GetSystemFilePath(34404, a5[37], (HSTRING *)&bufferHandle);
              v15 = SystemFilePath;
              if ( SystemFilePath < 0 )
              {
                v40 = 6788;
                goto LABEL_50;
              }
            }
            else
            {
              SystemFilePath = CPackagedComCatalog::GetPackagedFilePath(v56, v26, a5 + 37, (HSTRING *)&bufferHandle);
              v15 = SystemFilePath;
              if ( SystemFilePath < 0 )
              {
                v40 = 6794;
LABEL_50:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v40,
                  (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
                  (const char *)(unsigned int)SystemFilePath,
                  (int)v46);
                v34 = (HSTRING)bufferHandle;
                goto LABEL_33;
              }
            }
            if ( v48 == 34404 )
            {
              if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                   (Microsoft::WRL::Wrappers::Details *)*a7,
                                   (HSTRING)bufferHandle,
                                   v39) )
                MicrosoftTelemetryAssertTriggeredNoArgs(v41);
            }
            OpaqueString::operator=(a7, &bufferHandle);
            WindowsDeleteString((HSTRING)bufferHandle);
          }
        }
        return 0;
      }
      v44 = 6735;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v22,
      (int)v46);
    p_bufferHandle = &bufferHandle;
  }
  wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(p_bufferHandle);
LABEL_32:
  v34 = v51;
LABEL_33:
  WindowsDeleteString(v34);
  return v15;
}

```

## disassembly

```asm
0x18000c674  mov     [rsp-8+arg_18], rbx
0x18000c679  push    rbp
0x18000c67a  push    rsi
0x18000c67b  push    rdi
0x18000c67c  push    r12
0x18000c67e  push    r13
0x18000c680  push    r14
0x18000c682  push    r15
0x18000c684  lea     rbp, [rsp-60h]
0x18000c689  sub     rsp, 160h
0x18000c690  mov     rax, cs:__security_cookie
0x18000c697  xor     rax, rsp
0x18000c69a  mov     [rbp+90h+var_40], rax
0x18000c69e  mov     r13, [rbp+90h+arg_30]
0x18000c6a5  mov     rbx, rcx
0x18000c6a8  mov     r14, [rbp+90h+arg_38]
0x18000c6af  mov     r12d, r9d
0x18000c6b2  mov     r15, [rbp+90h+arg_40]
0x18000c6b9  mov     rsi, [rbp+90h+arg_20]
0x18000c6c0  mov     rdi, [rbp+90h+arg_28]
0x18000c6c7  mov     [rsp+190h+var_118], rcx
0x18000c6cc  mov     rcx, [r13+0]; string
0x18000c6d0  mov     [rsp+190h+var_120], r9d
0x18000c6d5  mov     [rsp+190h+var_130], r8
0x18000c6da  mov     [rsp+190h+var_128], rdx
0x18000c6df  mov     [rbp+90h+var_108], r14
0x18000c6e3  call    cs:__imp_WindowsDeleteString
0x18000c6e9  mov     qword ptr [r13+0], 0
0x18000c6f1  mov     rcx, [r14]; string
0x18000c6f4  call    cs:__imp_WindowsDeleteString
0x18000c6fa  mov     qword ptr [r14], 0
0x18000c701  mov     rcx, [r15]; string
0x18000c704  call    cs:__imp_WindowsDeleteString
0x18000c70a  mov     qword ptr [r15], 0
0x18000c711  lea     r14, [r15+8]
0x18000c715  mov     rcx, [r14]; string
0x18000c718  call    cs:__imp_WindowsDeleteString
0x18000c71e  xor     eax, eax
0x18000c720  mov     [r14], rax
0x18000c723  mov     [rsp+190h+var_158], eax
0x18000c727  test    rdi, rdi
0x18000c72a  jz      loc_18000C918
0x18000c730  cmp     [rdi+0B8h], al
0x18000c736  jz      loc_18000C9EF
0x18000c73c  test    r12b, 4
0x18000c740  jz      loc_18000CC5F
0x18000c746  mov     rdx, [rsp+190h+var_128]; struct OpaqueString *
0x18000c74b  lea     r8, [rsi+0F8h]; struct OpaqueString *
0x18000c752  xor     r12d, r12d
0x18000c755  mov     r9, r13; struct OpaqueString *
0x18000c758  mov     rcx, rbx; struct IUserTokenInternal *
0x18000c75b  mov     [rsp+190h+var_140], r12
0x18000c760  call    ?GetPackagedFilePath@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@AEBVOpaqueString@@1AEAV3@@Z; CPackagedComCatalog::GetPackagedFilePath(IUserTokenInternal *,OpaqueString const &,OpaqueString const &,OpaqueString &)
0x18000c765  mov     ebx, eax
0x18000c767  test    eax, eax
0x18000c769  js      loc_18000CB9C
0x18000c76f  mov     rcx, [r13+0]; string
0x18000c773  xor     edx, edx; length
0x18000c775  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c77b  mov     rcx, rax; lpFileName
0x18000c77e  lea     rdx, [rsp+190h+var_158]
0x18000c783  call    CoGetModuleArchitecture
0x18000c788  mov     ebx, eax
0x18000c78a  test    eax, eax
0x18000c78c  js      loc_18000CC69
0x18000c792  mov     rcx, rdi; this
0x18000c795  call    ?HasSystemSurrogate@CServerRegistration@CPackagedComCatalog@@QEBA_NXZ; CPackagedComCatalog::CServerRegistration::HasSystemSurrogate(void)
0x18000c79a  test    al, al
0x18000c79c  jnz     loc_18000C965
0x18000c7a2  lea     rdx, [rsp+190h+string]
0x18000c7a7  call    ?GetExecutableAbsolutePath@CServerRegistration@CPackagedComCatalog@@QEBA?AVOpaqueString@@XZ; CPackagedComCatalog::CServerRegistration::GetExecutableAbsolutePath(void)
0x18000c7ac  mov     rcx, [r15]; string
0x18000c7af  mov     rbx, rax
0x18000c7b2  call    cs:__imp_WindowsDeleteString
0x18000c7b8  mov     [r15], r12
0x18000c7bb  mov     rcx, [rbx]
0x18000c7be  mov     [r15], rcx
0x18000c7c1  mov     [rbx], r12
0x18000c7c4  mov     rcx, [rsp+190h+string]; string
0x18000c7c9  call    cs:__imp_WindowsDeleteString
0x18000c7cf  lea     rdx, [rsp+190h+string]
0x18000c7d4  mov     rcx, rdi
0x18000c7d7  call    ?GetCommandLineW@CServerRegistration@CPackagedComCatalog@@QEBA?AVOpaqueString@@XZ; CPackagedComCatalog::CServerRegistration::GetCommandLineW(void)
0x18000c7dc  mov     rcx, [rsp+190h+var_140]; string
0x18000c7e1  mov     rbx, rax
0x18000c7e4  call    cs:__imp_WindowsDeleteString
0x18000c7ea  mov     [rsp+190h+var_140], r12
0x18000c7ef  mov     rcx, [rbx]
0x18000c7f2  mov     [rsp+190h+var_140], rcx
0x18000c7f7  mov     [rbx], r12
0x18000c7fa  mov     rcx, [rsp+190h+string]; string
0x18000c7ff  call    cs:__imp_WindowsDeleteString
0x18000c805  mov     rcx, [rsp+190h+var_140]; string
0x18000c80a  lea     rdx, [rsp+190h+length]; length
0x18000c80f  mov     [rsp+190h+length], r12d
0x18000c814  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c81a  mov     rcx, rdi; this
0x18000c81d  mov     r12, rax
0x18000c820  call    ?HasCustomSurrogate@CServerRegistration@CPackagedComCatalog@@QEBA_NXZ; CPackagedComCatalog::CServerRegistration::HasCustomSurrogate(void)
0x18000c825  xor     r15d, r15d
0x18000c828  test    al, al
0x18000c82a  jnz     loc_18000CA9D
0x18000c830  mov     r15d, [rsp+190h+length]
0x18000c835  lea     r8, [rsp+190h+bufferHandle]; bufferHandle
0x18000c83a  lea     rdx, [rsp+190h+string]; charBuffer
0x18000c83f  mov     [rsp+190h+string], 0
0x18000c848  mov     [rsp+190h+bufferHandle], 0
0x18000c851  lea     ecx, [r15+32h]; length
0x18000c855  call    cs:__imp_WindowsPreallocateStringBuffer
0x18000c85b  mov     ebx, eax
0x18000c85d  test    eax, eax
0x18000c85f  js      loc_18000CCB6
0x18000c865  xor     edx, edx; Val
0x18000c867  lea     rcx, [rbp+90h+sz]; void *
0x18000c86b  lea     r8d, [rdx+4Eh]; Size
0x18000c86f  call    memset_0
0x18000c874  cmp     byte ptr [rdi+0B8h], 0
0x18000c87b  lea     rcx, [rdi+0BCh]
0x18000c882  jnz     short loc_18000C88B
0x18000c884  lea     rcx, GUID_NULL; rguid
0x18000c88b  mov     r8d, 27h ; '''; cchMax
0x18000c891  lea     rdx, [rbp+90h+sz]; lpsz
0x18000c895  call    cs:__imp_StringFromGUID2
0x18000c89b  mov     rcx, [rsp+190h+string]; unsigned __int16 *
0x18000c8a0  lea     rax, [rbp+90h+sz]
0x18000c8a4  mov     [rsp+190h+var_168], rax
0x18000c8a9  lea     edx, [r15+33h]; unsigned __int64
0x18000c8ad  lea     rax, ?g_wszSlashProcessId@@3QBGB; " /Processid:"
0x18000c8b4  mov     r9, r12
0x18000c8b7  lea     r8, aSSS; "%s%s%s"
0x18000c8be  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000c8c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c8c8  mov     ebx, eax
0x18000c8ca  test    eax, eax
0x18000c8cc  js      loc_18000CA60
0x18000c8d2  mov     rcx, [r14]; string
0x18000c8d5  call    cs:__imp_WindowsDeleteString
0x18000c8db  mov     rdx, r14
0x18000c8de  mov     qword ptr [r14], 0
0x18000c8e5  lea     rcx, [rsp+190h+bufferHandle]
0x18000c8ea  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x18000c8ef  mov     ebx, eax
0x18000c8f1  test    eax, eax
0x18000c8f3  js      loc_18000CCBD
0x18000c8f9  mov     rcx, [rsp+190h+bufferHandle]; bufferHandle
0x18000c8fe  test    rcx, rcx
0x18000c901  jnz     short loc_18000C95D
0x18000c903  mov     rcx, [rsp+190h+var_140]; string
0x18000c908  call    cs:__imp_WindowsDeleteString
0x18000c90e  mov     r12d, [rsp+190h+var_120]
0x18000c913  mov     rbx, [rsp+190h+var_118]
0x18000c918  xor     r15d, r15d
0x18000c91b  test    r12b, 2
0x18000c91f  jnz     loc_18000CCE7
0x18000c925  mov     rdi, [rsp+190h+var_128]
0x18000c92a  test    r12b, 1
0x18000c92e  jnz     loc_18000CD47
0x18000c934  xor     eax, eax
0x18000c936  mov     rcx, [rbp+90h+var_40]
0x18000c93a  xor     rcx, rsp; StackCookie
0x18000c93d  call    __security_check_cookie
0x18000c942  mov     rbx, [rsp+190h+arg_18]
0x18000c94a  add     rsp, 160h
0x18000c951  pop     r15
0x18000c953  pop     r14
0x18000c955  pop     r13
0x18000c957  pop     r12
0x18000c959  pop     rdi
0x18000c95a  pop     rsi
0x18000c95b  pop     rbp
0x18000c95c  retn
0x18000c95d  call    cs:__imp_WindowsDeleteStringBuffer
0x18000c963  jmp     short loc_18000C903
0x18000c965  call    ?HasCustomSurrogate@CServerRegistration@CPackagedComCatalog@@QEBA_NXZ; CPackagedComCatalog::CServerRegistration::HasCustomSurrogate(void)
0x18000c96a  test    al, al
0x18000c96c  jnz     loc_18000CB4C
0x18000c972  lea     r9, [rbp+90h+var_E8]; string
0x18000c976  mov     [rbp+90h+var_E8], r12
0x18000c97a  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000c97e  mov     edx, 0Bh; length
0x18000c983  lea     rcx, ?g_wszDllHost@@3QBGB; "DllHost.exe"
0x18000c98a  call    cs:__imp_WindowsCreateStringReference
0x18000c990  test    eax, eax
0x18000c992  js      loc_18000CC73
0x18000c998  mov     rbx, [rbp+90h+var_E8]
0x18000c99c  mov     [rbp+90h+var_E8], r12
0x18000c9a0  mov     ecx, [rsp+190h+var_158]; unsigned int
0x18000c9a4  mov     r8, r15; struct OpaqueString *
0x18000c9a7  mov     rdx, rbx; HSTRING
0x18000c9aa  call    ?GetSystemFilePath@CPackagedComCatalog@@CAJKPEAUHSTRING__@@AEAVOpaqueString@@@Z; CPackagedComCatalog::GetSystemFilePath(ulong,HSTRING__ *,OpaqueString &)
0x18000c9af  mov     ebx, eax
0x18000c9b1  test    eax, eax
0x18000c9b3  js      loc_18000CBC1
0x18000c9b9  lea     r8, [rsp+190h+var_140]; struct OpaqueString *
0x18000c9be  mov     [rsp+190h+string], r12
0x18000c9c3  lea     rdx, [rsp+190h+string]; struct OpaqueString *
0x18000c9c8  mov     rcx, r15; struct OpaqueString *
0x18000c9cb  call    ?ConstructCommandLine@CPackagedComCatalog@@CAJAEBVOpaqueString@@0AEAV2@@Z; CPackagedComCatalog::ConstructCommandLine(OpaqueString const &,OpaqueString const &,OpaqueString &)
0x18000c9d0  xor     ecx, ecx; string
0x18000c9d2  mov     ebx, eax
0x18000c9d4  call    cs:__imp_WindowsDeleteString
0x18000c9da  test    ebx, ebx
0x18000c9dc  jns     loc_18000C805
0x18000c9e2  mov     r9d, ebx
0x18000c9e5  mov     edx, 1A21h
0x18000c9ea  jmp     loc_18000CBA4
0x18000c9ef  lea     rdx, [rsp+190h+var_130]
0x18000c9f4  mov     rcx, rdi
0x18000c9f7  call    ?GetExecutableAbsolutePath@CServerRegistration@CPackagedComCatalog@@QEBA?AVOpaqueString@@XZ; CPackagedComCatalog::CServerRegistration::GetExecutableAbsolutePath(void)
0x18000c9fc  mov     rcx, [r15]; string
0x18000c9ff  mov     rbx, rax
0x18000ca02  call    cs:__imp_WindowsDeleteString
0x18000ca08  mov     qword ptr [r15], 0
0x18000ca0f  mov     rcx, [rbx]
0x18000ca12  mov     [r15], rcx
0x18000ca15  xor     r15d, r15d
0x18000ca18  mov     [rbx], r15
0x18000ca1b  mov     rcx, [rsp+190h+var_130]; string
0x18000ca20  call    cs:__imp_WindowsDeleteString
0x18000ca26  lea     rdx, [rsp+190h+var_130]
0x18000ca2b  mov     rcx, rdi
0x18000ca2e  call    ?GetCommandLineW@CServerRegistration@CPackagedComCatalog@@QEBA?AVOpaqueString@@XZ; CPackagedComCatalog::CServerRegistration::GetCommandLineW(void)
0x18000ca33  mov     rcx, [r14]; string
0x18000ca36  mov     rbx, rax
0x18000ca39  call    cs:__imp_WindowsDeleteString
0x18000ca3f  mov     [r14], r15
0x18000ca42  mov     rcx, [rbx]
0x18000ca45  mov     [r14], rcx
0x18000ca48  mov     [rbx], r15
0x18000ca4b  mov     rcx, [rsp+190h+var_130]; string
0x18000ca50  call    cs:__imp_WindowsDeleteString
0x18000ca56  mov     rbx, [rsp+190h+var_118]
0x18000ca5b  jmp     loc_18000C91B
0x18000ca60  mov     rcx, [rbp+98h]; this
0x18000ca67  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18000ca6e  mov     r9d, eax; char *
0x18000ca71  mov     edx, 1A4Dh; void *
0x18000ca76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca7b  mov     rcx, [rsp+190h+bufferHandle]; bufferHandle
0x18000ca80  test    rcx, rcx
0x18000ca83  jz      short loc_18000CA8B
0x18000ca85  call    cs:__imp_WindowsDeleteStringBuffer
0x18000ca8b  mov     rcx, [rsp+190h+var_140]; string
0x18000ca90  call    cs:__imp_WindowsDeleteString
0x18000ca96  mov     eax, ebx
0x18000ca98  jmp     loc_18000C936
0x18000ca9d  mov     edi, [rsp+190h+length]
0x18000caa1  lea     r8, [rsp+190h+var_138]; bufferHandle
0x18000caa6  lea     rdx, [rbp+90h+charBuffer]; charBuffer
0x18000caaa  mov     [rbp+90h+charBuffer], r15
0x18000caae  mov     [rsp+190h+var_138], r15
0x18000cab3  lea     ecx, [rdi+32h]; length
0x18000cab6  call    cs:__imp_WindowsPreallocateStringBuffer
0x18000cabc  mov     ebx, eax
0x18000cabe  test    eax, eax
0x18000cac0  js      loc_18000CC86
0x18000cac6  xor     edx, edx; Val
0x18000cac8  lea     rcx, [rbp+90h+var_E0]; void *
0x18000cacc  lea     r8d, [rdx+4Eh]; Size
0x18000cad0  call    memset_0
0x18000cad5  mov     rcx, [rsp+190h+var_130]; rguid
0x18000cada  lea     rdx, [rbp+90h+var_E0]; lpsz
0x18000cade  mov     r8d, 27h ; '''; cchMax
0x18000cae4  call    cs:__imp_StringFromGUID2
0x18000caea  mov     rcx, [rbp+90h+charBuffer]; unsigned __int16 *
0x18000caee  lea     rax, ?g_wszEmbedding@@3QBGB; " -Embedding"
0x18000caf5  mov     [rsp+190h+var_168], rax
0x18000cafa  lea     edx, [rdi+33h]; unsigned __int64
0x18000cafd  lea     rax, [rbp+90h+var_E0]
0x18000cb01  mov     r9, r12
0x18000cb04  lea     r8, aSSS_0; "%s %s%s"
0x18000cb0b  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000cb10  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cb15  mov     ebx, eax
0x18000cb17  test    eax, eax
0x18000cb19  js      loc_18000CCAF
0x18000cb1f  mov     rcx, [r14]; string
0x18000cb22  call    cs:__imp_WindowsDeleteString
0x18000cb28  mov     rdx, r14
0x18000cb2b  mov     [r14], r15
0x18000cb2e  lea     rcx, [rsp+190h+var_138]
0x18000cb33  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x18000cb38  mov     ebx, eax
0x18000cb3a  test    eax, eax
0x18000cb3c  js      loc_18000CC8D
0x18000cb42  mov     rcx, [rsp+190h+var_138]
0x18000cb47  jmp     loc_18000C8FE
0x18000cb4c  cmp     [rdi+88h], r12b
0x18000cb53  jz      short loc_18000CBBC
0x18000cb55  mov     rbx, [rdi+90h]
0x18000cb5c  xor     ecx, ecx; string
0x18000cb5e  mov     [rsp+190h+bufferHandle], r12
0x18000cb63  call    cs:__imp_WindowsDeleteString
0x18000cb69  lea     rdx, [rsp+190h+bufferHandle]; newString
0x18000cb6e  mov     [rsp+190h+bufferHandle], r12
0x18000cb73  mov     rcx, rbx; string
0x18000cb76  call    cs:__imp_WindowsDuplicateString
0x18000cb7c  xor     ecx, ecx; string
0x18000cb7e  call    cs:__imp_WindowsDeleteString
0x18000cb84  mov     rbx, [rsp+190h+bufferHandle]
  ... truncated ...
```
