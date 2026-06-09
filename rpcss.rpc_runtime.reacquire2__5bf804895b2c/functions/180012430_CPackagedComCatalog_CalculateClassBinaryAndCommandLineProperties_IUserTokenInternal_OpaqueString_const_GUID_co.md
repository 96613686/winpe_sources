# CPackagedComCatalog::CalculateClassBinaryAndCommandLineProperties(IUserTokenInternal *,OpaqueString const &,_GUID const &,tagCLSCTX,ComClassRegistrationEntryProperties const &,CPackagedComCatalog::CServerRegistration const *,OpaqueString &,OpaqueString &,CPackagedComCatalog::ExecutablePathAndCommandLine &)

- ea: `0x180012430`
- end: `0x180012bf8`
- name: `?CalculateClassBinaryAndCommandLineProperties@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@AEBVOpaqueString@@AEBU_GUID@@W4tagCLSCTX@@AEBUComClassRegistrationEntryProperties@@PEBVCServerRegistration@1@AEAV3@6AEAUExecutablePathAndCommandLine@1@@Z`
- size: `1992`
- prototype: `__int64 __fastcall(struct IUserTokenInternal *, const struct OpaqueString *, const struct _GUID *, enum tagCLSCTX, const struct ComClassRegistrationEntryProperties *, const struct CPackagedComCatalog::CServerRegistration *, struct OpaqueString *, struct OpaqueString *, struct CPackagedComCatalog::ExecutablePathAndCommandLine *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011ff8`

## callees

- `0x18001037c`
- `0x18001186c`
- `0x180012430`
- `0x180012c00`
- `0x180012c20`
- `0x180012cb8`
- `0x180012ce8`
- `0x180012d7c`
- `0x180012e10`
- `0x180012f50`
- `0x180013080`
- `0x1800137b0`
- `0x1800210f8`
- `0x18004b0f0`
- `0x18004bf1c`
- `0x180057bc0`
- `0x180091a10`
- `0x180095c0c`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800127a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800127a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001249f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001258c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800126d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012825`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800128d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012978`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800129c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800129dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012aad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001249f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001258c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800126d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012825`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800128d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012978`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800129c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800129dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012aad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18001276e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800128c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18001276e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800128c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18001264d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800128ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18001264d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800128ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180012693`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180012933`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180012693`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180012933`

## string_xrefs

- `0x1800126b1`: ` /Processid:`
- `0x18001279a`: `DllHost.exe`
- `0x1800128a2`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180012a02`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180012a6b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180012aed`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180012b1d`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180012b82`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::CalculateClassBinaryAndCommandLineProperties(
        struct IUserTokenInternal *a1,
        const struct OpaqueString *a2,
        struct _GUID *a3,
        enum tagCLSCTX a4,
        const struct ComClassRegistrationEntryProperties *a5,
        const struct CPackagedComCatalog::CServerRegistration *a6,
        HSTRING *a7,
        struct OpaqueString *a8,
        HSTRING *a9)
{
  struct IUserTokenInternal *v9; // rbx
  char v10; // r12
  HSTRING v11; // rcx
  HSTRING *v12; // r14
  int PackagedFilePath; // eax
  unsigned int v14; // ebx
  const WCHAR *StringRawBuffer; // rax
  CPackagedComCatalog::CServerRegistration *v16; // rcx
  HSTRING *v17; // rbx
  HSTRING *v18; // rbx
  PCWSTR v19; // r12
  UINT32 v20; // r15d
  HRESULT v21; // eax
  GUID *v22; // rcx
  int v23; // eax
  HSTRING_BUFFER v24; // rcx
  struct OpaqueString *v25; // rdi
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  HSTRING v30; // rbx
  unsigned __int64 v31; // r9
  __int64 v32; // rdx
  HSTRING *ExecutableAbsolutePath; // rbx
  HSTRING *CommandLineW; // rbx
  HSTRING v35; // rcx
  UINT32 v36; // edi
  HRESULT hstring_from_buffer_nothrow; // eax
  HSTRING *p_string; // rdx
  int SystemFilePath; // eax
  HSTRING v40; // r8
  __int64 v41; // rdx
  __int64 v42; // rdx
  HSTRING_BUFFER *p_bufferHandle; // rcx
  __int64 v44; // rdx
  int v45; // eax
  OLECHAR *v46; // [rsp+20h] [rbp-E0h]
  HSTRING_BUFFER bufferHandle; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v49; // [rsp+40h] [rbp-C0h]
  UINT32 length; // [rsp+44h] [rbp-BCh] BYREF
  HSTRING v51; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING_BUFFER v52; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v53; // [rsp+58h] [rbp-A8h] BYREF
  struct OpaqueString *v54; // [rsp+60h] [rbp-A0h]
  enum tagCLSCTX v55; // [rsp+68h] [rbp-98h]
  struct IUserTokenInternal *v56; // [rsp+70h] [rbp-90h]
  WCHAR *charBuffer; // [rsp+78h] [rbp-88h] BYREF
  struct OpaqueString *v58; // [rsp+80h] [rbp-80h]
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v60; // [rsp+A0h] [rbp-60h] BYREF
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
  v49 = 0;
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
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v51 = 0;
  PackagedFilePath = CPackagedComCatalog::GetPackagedFilePath(
                       v9,
                       v54,
                       (const struct ComClassRegistrationEntryProperties *)((char *)a5 + 248),
                       (struct OpaqueString *)a7);
  v14 = PackagedFilePath;
  if ( PackagedFilePath < 0 )
  {
    v32 = 6673;
    goto LABEL_43;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*a7, 0);
  PackagedFilePath = CoGetModuleArchitecture(StringRawBuffer);
  v14 = PackagedFilePath;
  if ( PackagedFilePath < 0 )
  {
    v32 = 6675;
    goto LABEL_43;
  }
  if ( CPackagedComCatalog::CServerRegistration::HasSystemSurrogate(a6) )
  {
    if ( CPackagedComCatalog::CServerRegistration::HasCustomSurrogate(v16) )
    {
      p_string = (HSTRING *)((char *)a6 + 144);
      string = 0;
      if ( !*((_BYTE *)a6 + 136) )
        p_string = &string;
      OpaqueString::OpaqueString((HSTRING *)&bufferHandle, (const struct OpaqueString *)p_string);
      WindowsDeleteString(0);
      v30 = (HSTRING)bufferHandle;
      WindowsDeleteString((HSTRING)bufferHandle);
      bufferHandle = 0;
    }
    else
    {
      v60 = 0;
      v27 = WindowsCreateStringReference(L"DllHost.exe", 0xBu, &hstringHeader, &v60);
      if ( v27 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
        __debugbreak();
      }
      v30 = v60;
      v60 = 0;
    }
    PackagedFilePath = CPackagedComCatalog::GetSystemFilePath(v49, v30, (struct OpaqueString *)a9);
    v14 = PackagedFilePath;
    if ( PackagedFilePath >= 0 )
    {
      string = 0;
      v14 = CPackagedComCatalog::ConstructCommandLine(
              (const struct OpaqueString *)a9,
              (const struct OpaqueString *)&string,
              (struct OpaqueString *)&v51);
      WindowsDeleteString(0);
      if ( (v14 & 0x80000000) == 0 )
        goto LABEL_9;
      v31 = v14;
      v32 = 6689;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)v31,
        (int)v46);
      goto LABEL_32;
    }
    v32 = 6687;
LABEL_43:
    v31 = (unsigned int)PackagedFilePath;
    goto LABEL_44;
  }
  v17 = (HSTRING *)CPackagedComCatalog::CServerRegistration::GetExecutableAbsolutePath(v16, &string);
  WindowsDeleteString(*a9);
  *a9 = 0;
  *a9 = *v17;
  *v17 = 0;
  WindowsDeleteString(string);
  v18 = (HSTRING *)CPackagedComCatalog::CServerRegistration::GetCommandLineW(a6, &string);
  WindowsDeleteString(v51);
  v51 = 0;
  v51 = *v18;
  *v18 = 0;
  WindowsDeleteString(string);
LABEL_9:
  length = 0;
  v19 = WindowsGetStringRawBuffer(v51, &length);
  if ( CPackagedComCatalog::CServerRegistration::HasCustomSurrogate(a6) )
  {
    v36 = length;
    charBuffer = 0;
    v52 = 0;
    hstring_from_buffer_nothrow = WindowsPreallocateStringBuffer(length + 50, &charBuffer, &v52);
    v14 = hstring_from_buffer_nothrow;
    if ( hstring_from_buffer_nothrow < 0 )
    {
      v42 = 6709;
    }
    else
    {
      memset_0(v61, 0, 0x4Eu);
      StringFromGUID2((const GUID *const)v53, v61, 39);
      v46 = v61;
      hstring_from_buffer_nothrow = StringCchPrintfW(charBuffer, v36 + 51, L"%s %s%s", v19);
      v14 = hstring_from_buffer_nothrow;
      if ( hstring_from_buffer_nothrow < 0 )
      {
        v42 = 6714;
      }
      else
      {
        WindowsDeleteString(*v12);
        *v12 = 0;
        hstring_from_buffer_nothrow = wil::make_hstring_from_buffer_nothrow(&v52, v12);
        v14 = hstring_from_buffer_nothrow;
        if ( hstring_from_buffer_nothrow >= 0 )
        {
          v24 = v52;
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
    v20 = length;
    string = 0;
    bufferHandle = 0;
    v21 = WindowsPreallocateStringBuffer(length + 50, (WCHAR **)&string, &bufferHandle);
    v14 = v21;
    if ( v21 < 0 )
    {
      v44 = 6727;
    }
    else
    {
      memset_0(sz, 0, 0x4Eu);
      v22 = (GUID *)((char *)a6 + 188);
      if ( !*((_BYTE *)a6 + 184) )
        v22 = &GUID_NULL;
      StringFromGUID2(v22, sz, 39);
      v46 = (OLECHAR *)L" /Processid:";
      v23 = StringCchPrintfW((unsigned __int16 *)string, v20 + 51, L"%s%s%s", v19);
      v14 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A4D,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v23,
          (int)L" /Processid:");
        if ( bufferHandle )
          WindowsDeleteStringBuffer(bufferHandle);
        goto LABEL_32;
      }
      WindowsDeleteString(*v12);
      *v12 = 0;
      v21 = wil::make_hstring_from_buffer_nothrow(&bufferHandle, v12);
      v14 = v21;
      if ( v21 >= 0 )
      {
        v24 = bufferHandle;
LABEL_16:
        if ( v24 )
          WindowsDeleteStringBuffer(v24);
        WindowsDeleteString(v51);
        v10 = v55;
        v9 = v56;
LABEL_19:
        if ( (v10 & 2) != 0 )
        {
          if ( g_bInSCM )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v25 = v54;
          if ( *((_BYTE *)a5 + 360) )
          {
            v45 = CPackagedComCatalog::GetPackagedFilePath(
                    v9,
                    v54,
                    (const struct ComClassRegistrationEntryProperties *)((char *)a5 + 368),
                    v58);
            v14 = v45;
            if ( v45 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A65,
                (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
                (const char *)(unsigned int)v45,
                (int)v46);
              return v14;
            }
          }
        }
        else
        {
          v25 = v54;
        }
        if ( (v10 & 1) != 0 )
        {
          if ( g_bInSCM )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( *((_BYTE *)a5 + 288) )
          {
            bufferHandle = 0;
            if ( *((_BYTE *)a5 + 336) && *((_BYTE *)a5 + 337) )
            {
              SystemFilePath = CPackagedComCatalog::GetSystemFilePath(
                                 0x8664u,
                                 *((HSTRING *)a5 + 37),
                                 (struct OpaqueString *)&bufferHandle);
              v14 = SystemFilePath;
              if ( SystemFilePath < 0 )
              {
                v41 = 6788;
                goto LABEL_49;
              }
            }
            else
            {
              SystemFilePath = CPackagedComCatalog::GetPackagedFilePath(
                                 v56,
                                 v25,
                                 (const struct ComClassRegistrationEntryProperties *)((char *)a5 + 296),
                                 (struct OpaqueString *)&bufferHandle);
              v14 = SystemFilePath;
              if ( SystemFilePath < 0 )
              {
                v41 = 6794;
LABEL_49:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v41,
                  (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
                  (const char *)(unsigned int)SystemFilePath,
                  (int)v46);
                v35 = (HSTRING)bufferHandle;
                goto LABEL_33;
              }
            }
            if ( v49 == 34404 )
            {
              if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                   (Microsoft::WRL::Wrappers::Details *)*a7,
                                   (HSTRING)bufferHandle,
                                   v40) )
                MicrosoftTelemetryAssertTriggeredNoArgs();
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
      (const char *)(unsigned int)v21,
      (int)v46);
    p_bufferHandle = &bufferHandle;
  }
  wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(p_bufferHandle);
LABEL_32:
  v35 = v51;
LABEL_33:
  WindowsDeleteString(v35);
  return v14;
}

```

## disassembly

```asm
0x180012430  mov     [rsp-8+arg_18], rbx
0x180012435  push    rbp
0x180012436  push    rsi
0x180012437  push    rdi
0x180012438  push    r12
0x18001243a  push    r13
0x18001243c  push    r14
0x18001243e  push    r15
0x180012440  lea     rbp, [rsp-60h]
0x180012445  sub     rsp, 160h
0x18001244c  mov     rax, cs:__security_cookie
0x180012453  xor     rax, rsp
0x180012456  mov     [rbp+90h+var_40], rax
0x18001245a  mov     r13, [rbp+90h+arg_30]
0x180012461  mov     rbx, rcx
0x180012464  mov     r14, [rbp+90h+arg_38]
0x18001246b  mov     r12d, r9d
0x18001246e  mov     r15, [rbp+90h+arg_40]
0x180012475  mov     rsi, [rbp+90h+arg_20]
0x18001247c  mov     rdi, [rbp+90h+arg_28]
0x180012483  mov     [rsp+190h+var_120], rcx
0x180012488  mov     rcx, [r13+0]; string
0x18001248c  mov     [rsp+190h+var_128], r9d
0x180012491  mov     [rsp+190h+var_138], r8
0x180012496  mov     [rsp+190h+var_130], rdx
0x18001249b  mov     [rbp+90h+var_110], r14
0x18001249f  call    cs:__imp_WindowsDeleteString
0x1800124a6  nop     dword ptr [rax+rax+00h]
0x1800124ab  mov     qword ptr [r13+0], 0
0x1800124b3  mov     rcx, [r14]; string
0x1800124b6  call    cs:__imp_WindowsDeleteString
0x1800124bd  nop     dword ptr [rax+rax+00h]
0x1800124c2  mov     qword ptr [r14], 0
0x1800124c9  mov     rcx, [r15]; string
0x1800124cc  call    cs:__imp_WindowsDeleteString
0x1800124d3  nop     dword ptr [rax+rax+00h]
0x1800124d8  mov     qword ptr [r15], 0
0x1800124df  lea     r14, [r15+8]
0x1800124e3  mov     rcx, [r14]; string
0x1800124e6  call    cs:__imp_WindowsDeleteString
0x1800124ed  nop     dword ptr [rax+rax+00h]
0x1800124f2  xor     eax, eax
0x1800124f4  mov     [r14], rax
0x1800124f7  mov     [rsp+190h+var_150], eax
0x1800124fb  test    rdi, rdi
0x1800124fe  jz      loc_180012728
0x180012504  cmp     [rdi+0B8h], al
0x18001250a  jz      loc_180012812
0x180012510  test    r12b, 4
0x180012514  jz      loc_180012ABE
0x18001251a  mov     rdx, [rsp+190h+var_130]; struct OpaqueString *
0x18001251f  lea     r8, [rsi+0F8h]; struct OpaqueString *
0x180012526  xor     r12d, r12d
0x180012529  mov     r9, r13; struct OpaqueString *
0x18001252c  mov     rcx, rbx; struct IUserTokenInternal *
0x18001252f  mov     [rsp+190h+var_148], r12
0x180012534  call    ?GetPackagedFilePath@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@AEBVOpaqueString@@1AEAV3@@Z; CPackagedComCatalog::GetPackagedFilePath(IUserTokenInternal *,OpaqueString const &,OpaqueString const &,OpaqueString &)
0x180012539  mov     ebx, eax
0x18001253b  test    eax, eax
0x18001253d  js      loc_1800129F3
0x180012543  mov     rcx, [r13+0]; string
0x180012547  xor     edx, edx; length
0x180012549  call    cs:__imp_WindowsGetStringRawBuffer
0x180012550  nop     dword ptr [rax+rax+00h]
0x180012555  mov     rcx, rax; lpFileName
0x180012558  lea     rdx, [rsp+190h+var_150]
0x18001255d  call    CoGetModuleArchitecture
0x180012562  mov     ebx, eax
0x180012564  test    eax, eax
0x180012566  js      loc_180012AC8
0x18001256c  mov     rcx, rdi; this
0x18001256f  call    ?HasSystemSurrogate@CServerRegistration@CPackagedComCatalog@@QEBA_NXZ; CPackagedComCatalog::CServerRegistration::HasSystemSurrogate(void)
0x180012574  test    al, al
0x180012576  jnz     loc_18001277C
0x18001257c  lea     rdx, [rsp+190h+string]
0x180012581  call    ?GetExecutableAbsolutePath@CServerRegistration@CPackagedComCatalog@@QEBA?AVOpaqueString@@XZ; CPackagedComCatalog::CServerRegistration::GetExecutableAbsolutePath(void)
0x180012586  mov     rcx, [r15]; string
0x180012589  mov     rbx, rax
0x18001258c  call    cs:__imp_WindowsDeleteString
0x180012593  nop     dword ptr [rax+rax+00h]
0x180012598  mov     [r15], r12
0x18001259b  mov     rcx, [rbx]
0x18001259e  mov     [r15], rcx
0x1800125a1  mov     [rbx], r12
0x1800125a4  mov     rcx, [rsp+190h+string]; string
0x1800125a9  call    cs:__imp_WindowsDeleteString
0x1800125b0  nop     dword ptr [rax+rax+00h]
0x1800125b5  lea     rdx, [rsp+190h+string]
0x1800125ba  mov     rcx, rdi
0x1800125bd  call    ?GetCommandLineW@CServerRegistration@CPackagedComCatalog@@QEBA?AVOpaqueString@@XZ; CPackagedComCatalog::CServerRegistration::GetCommandLineW(void)
0x1800125c2  mov     rcx, [rsp+190h+var_148]; string
0x1800125c7  mov     rbx, rax
0x1800125ca  call    cs:__imp_WindowsDeleteString
0x1800125d1  nop     dword ptr [rax+rax+00h]
0x1800125d6  mov     [rsp+190h+var_148], r12
0x1800125db  mov     rcx, [rbx]
0x1800125de  mov     [rsp+190h+var_148], rcx
0x1800125e3  mov     [rbx], r12
0x1800125e6  mov     rcx, [rsp+190h+string]; string
0x1800125eb  call    cs:__imp_WindowsDeleteString
0x1800125f2  nop     dword ptr [rax+rax+00h]
0x1800125f7  mov     rcx, [rsp+190h+var_148]; string
0x1800125fc  lea     rdx, [rsp+190h+length]; length
0x180012601  mov     [rsp+190h+length], r12d
0x180012606  call    cs:__imp_WindowsGetStringRawBuffer
0x18001260d  nop     dword ptr [rax+rax+00h]
0x180012612  mov     rcx, rdi; this
0x180012615  mov     r12, rax
0x180012618  call    ?HasCustomSurrogate@CServerRegistration@CPackagedComCatalog@@QEBA_NXZ; CPackagedComCatalog::CServerRegistration::HasCustomSurrogate(void)
0x18001261d  xor     r15d, r15d
0x180012620  test    al, al
0x180012622  jnz     loc_1800128E4
0x180012628  mov     r15d, [rsp+190h+length]
0x18001262d  lea     r8, [rsp+190h+bufferHandle]; bufferHandle
0x180012632  lea     rdx, [rsp+190h+string]; charBuffer
0x180012637  mov     [rsp+190h+string], 0
0x180012640  mov     [rsp+190h+bufferHandle], 0
0x180012649  lea     ecx, [r15+32h]; length
0x18001264d  call    cs:__imp_WindowsPreallocateStringBuffer
0x180012654  nop     dword ptr [rax+rax+00h]
0x180012659  mov     ebx, eax
0x18001265b  test    eax, eax
0x18001265d  js      loc_180012B0A
0x180012663  xor     edx, edx; Val
0x180012665  lea     rcx, [rbp+90h+sz]; void *
0x180012669  lea     r8d, [rdx+4Eh]; Size
0x18001266d  call    memset_0
0x180012672  cmp     byte ptr [rdi+0B8h], 0
0x180012679  lea     rcx, [rdi+0BCh]
0x180012680  jnz     short loc_180012689
0x180012682  lea     rcx, GUID_NULL; rguid
0x180012689  mov     r8d, 27h ; '''; cchMax
0x18001268f  lea     rdx, [rbp+90h+sz]; lpsz
0x180012693  call    cs:__imp_StringFromGUID2
0x18001269a  nop     dword ptr [rax+rax+00h]
0x18001269f  mov     rcx, [rsp+190h+string]; unsigned __int16 *
0x1800126a4  lea     rax, [rbp+90h+sz]
0x1800126a8  mov     [rsp+190h+var_168], rax
0x1800126ad  lea     edx, [r15+33h]; unsigned __int64
0x1800126b1  lea     rax, ?g_wszSlashProcessId@@3QBGB; " /Processid:"
0x1800126b8  mov     r9, r12
0x1800126bb  lea     r8, aSSS; "%s%s%s"
0x1800126c2  mov     qword ptr [rsp+190h+var_170], rax; int
0x1800126c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800126cc  mov     ebx, eax
0x1800126ce  test    eax, eax
0x1800126d0  js      loc_18001289B
0x1800126d6  mov     rcx, [r14]; string
0x1800126d9  call    cs:__imp_WindowsDeleteString
0x1800126e0  nop     dword ptr [rax+rax+00h]
0x1800126e5  mov     rdx, r14
0x1800126e8  mov     qword ptr [r14], 0
0x1800126ef  lea     rcx, [rsp+190h+bufferHandle]
0x1800126f4  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x1800126f9  mov     ebx, eax
0x1800126fb  test    eax, eax
0x1800126fd  js      loc_180012B11
0x180012703  mov     rcx, [rsp+190h+bufferHandle]; bufferHandle
0x180012708  test    rcx, rcx
0x18001270b  jnz     short loc_18001276E
0x18001270d  mov     rcx, [rsp+190h+var_148]; string
0x180012712  call    cs:__imp_WindowsDeleteString
0x180012719  nop     dword ptr [rax+rax+00h]
0x18001271e  mov     r12d, [rsp+190h+var_128]
0x180012723  mov     rbx, [rsp+190h+var_120]
0x180012728  xor     r15d, r15d
0x18001272b  test    r12b, 2
0x18001272f  jnz     loc_180012B3B
0x180012735  mov     rdi, [rsp+190h+var_130]
0x18001273a  test    r12b, 1
0x18001273e  jnz     loc_180012B9B
0x180012744  xor     eax, eax
0x180012746  mov     rcx, [rbp+90h+var_40]
0x18001274a  xor     rcx, rsp; StackCookie
0x18001274d  call    __security_check_cookie
0x180012752  mov     rbx, [rsp+190h+arg_18]
0x18001275a  add     rsp, 160h
0x180012761  pop     r15
0x180012763  pop     r14
0x180012765  pop     r13
0x180012767  pop     r12
0x180012769  pop     rdi
0x18001276a  pop     rsi
0x18001276b  pop     rbp
0x18001276c  retn
0x18001276e  call    cs:__imp_WindowsDeleteStringBuffer
0x180012775  nop     dword ptr [rax+rax+00h]
0x18001277a  jmp     short loc_18001270D
0x18001277c  call    ?HasCustomSurrogate@CServerRegistration@CPackagedComCatalog@@QEBA_NXZ; CPackagedComCatalog::CServerRegistration::HasCustomSurrogate(void)
0x180012781  test    al, al
0x180012783  jnz     loc_1800129A8
0x180012789  lea     r9, [rbp+90h+var_F0]; string
0x18001278d  mov     [rbp+90h+var_F0], r12
0x180012791  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x180012795  mov     edx, 0Bh; length
0x18001279a  lea     rcx, ?g_wszDllHost@@3QBGB; "DllHost.exe"
0x1800127a1  call    cs:__imp_WindowsCreateStringReference
0x1800127a8  nop     dword ptr [rax+rax+00h]
0x1800127ad  test    eax, eax
0x1800127af  js      loc_180012AD2
0x1800127b5  mov     rbx, [rbp+90h+var_F0]
0x1800127b9  mov     [rbp+90h+var_F0], r12
0x1800127bd  mov     ecx, [rsp+190h+var_150]; unsigned int
0x1800127c1  mov     r8, r15; struct OpaqueString *
0x1800127c4  mov     rdx, rbx; HSTRING
0x1800127c7  call    ?GetSystemFilePath@CPackagedComCatalog@@CAJKPEAUHSTRING__@@AEAVOpaqueString@@@Z; CPackagedComCatalog::GetSystemFilePath(ulong,HSTRING__ *,OpaqueString &)
0x1800127cc  mov     ebx, eax
0x1800127ce  test    eax, eax
0x1800127d0  js      loc_180012A1A
0x1800127d6  lea     r8, [rsp+190h+var_148]; struct OpaqueString *
0x1800127db  mov     [rsp+190h+string], r12
0x1800127e0  lea     rdx, [rsp+190h+string]; struct OpaqueString *
0x1800127e5  mov     rcx, r15; struct OpaqueString *
0x1800127e8  call    ?ConstructCommandLine@CPackagedComCatalog@@CAJAEBVOpaqueString@@0AEAV2@@Z; CPackagedComCatalog::ConstructCommandLine(OpaqueString const &,OpaqueString const &,OpaqueString &)
0x1800127ed  xor     ecx, ecx; string
0x1800127ef  mov     ebx, eax
0x1800127f1  call    cs:__imp_WindowsDeleteString
0x1800127f8  nop     dword ptr [rax+rax+00h]
0x1800127fd  test    ebx, ebx
0x1800127ff  jns     loc_1800125F7
0x180012805  mov     r9d, ebx
0x180012808  mov     edx, 1A21h
0x18001280d  jmp     loc_1800129FB
0x180012812  lea     rdx, [rsp+190h+var_138]
0x180012817  mov     rcx, rdi
0x18001281a  call    ?GetExecutableAbsolutePath@CServerRegistration@CPackagedComCatalog@@QEBA?AVOpaqueString@@XZ; CPackagedComCatalog::CServerRegistration::GetExecutableAbsolutePath(void)
0x18001281f  mov     rcx, [r15]; string
0x180012822  mov     rbx, rax
0x180012825  call    cs:__imp_WindowsDeleteString
0x18001282c  nop     dword ptr [rax+rax+00h]
0x180012831  mov     qword ptr [r15], 0
0x180012838  mov     rcx, [rbx]
0x18001283b  mov     [r15], rcx
0x18001283e  xor     r15d, r15d
0x180012841  mov     [rbx], r15
0x180012844  mov     rcx, [rsp+190h+var_138]; string
0x180012849  call    cs:__imp_WindowsDeleteString
0x180012850  nop     dword ptr [rax+rax+00h]
0x180012855  lea     rdx, [rsp+190h+var_138]
0x18001285a  mov     rcx, rdi
0x18001285d  call    ?GetCommandLineW@CServerRegistration@CPackagedComCatalog@@QEBA?AVOpaqueString@@XZ; CPackagedComCatalog::CServerRegistration::GetCommandLineW(void)
0x180012862  mov     rcx, [r14]; string
0x180012865  mov     rbx, rax
0x180012868  call    cs:__imp_WindowsDeleteString
0x18001286f  nop     dword ptr [rax+rax+00h]
0x180012874  mov     [r14], r15
0x180012877  mov     rcx, [rbx]
0x18001287a  mov     [r14], rcx
0x18001287d  mov     [rbx], r15
0x180012880  mov     rcx, [rsp+190h+var_138]; string
0x180012885  call    cs:__imp_WindowsDeleteString
0x18001288c  nop     dword ptr [rax+rax+00h]
0x180012891  mov     rbx, [rsp+190h+var_120]
0x180012896  jmp     loc_18001272B
0x18001289b  mov     rcx, [rbp+98h]; this
0x1800128a2  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800128a9  mov     r9d, eax; char *
0x1800128ac  mov     edx, 1A4Dh; void *
0x1800128b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800128b6  mov     rcx, [rsp+190h+bufferHandle]; bufferHandle
0x1800128bb  test    rcx, rcx
0x1800128be  jz      short loc_1800128CC
0x1800128c0  call    cs:__imp_WindowsDeleteStringBuffer
0x1800128c7  nop     dword ptr [rax+rax+00h]
0x1800128cc  mov     rcx, [rsp+190h+var_148]; string
0x1800128d1  call    cs:__imp_WindowsDeleteString
0x1800128d8  nop     dword ptr [rax+rax+00h]
0x1800128dd  mov     eax, ebx
0x1800128df  jmp     loc_180012746
0x1800128e4  mov     edi, [rsp+190h+length]
0x1800128e8  lea     r8, [rsp+190h+var_140]; bufferHandle
0x1800128ed  lea     rdx, [rsp+190h+charBuffer]; charBuffer
0x1800128f2  mov     [rsp+190h+charBuffer], r15
0x1800128f7  mov     [rsp+190h+var_140], r15
0x1800128fc  lea     ecx, [rdi+32h]; length
0x1800128ff  call    cs:__imp_WindowsPreallocateStringBuffer
0x180012906  nop     dword ptr [rax+rax+00h]
0x18001290b  mov     ebx, eax
0x18001290d  test    eax, eax
0x18001290f  js      loc_180012ADA
0x180012915  xor     edx, edx; Val
0x180012917  lea     rcx, [rbp+90h+var_E0]; void *
0x18001291b  lea     r8d, [rdx+4Eh]; Size
0x18001291f  call    memset_0
0x180012924  mov     rcx, [rsp+190h+var_138]; rguid
0x180012929  lea     rdx, [rbp+90h+var_E0]; lpsz
0x18001292d  mov     r8d, 27h ; '''; cchMax
0x180012933  call    cs:__imp_StringFromGUID2
0x18001293a  nop     dword ptr [rax+rax+00h]
0x18001293f  mov     rcx, [rsp+190h+charBuffer]; unsigned __int16 *
0x180012944  lea     rax, ?g_wszEmbedding@@3QBGB; " -Embedding"
0x18001294b  mov     [rsp+190h+var_168], rax
0x180012950  lea     edx, [rdi+33h]; unsigned __int64
0x180012953  lea     rax, [rbp+90h+var_E0]
0x180012957  mov     r9, r12
0x18001295a  lea     r8, aSSS_0; "%s %s%s"
0x180012961  mov     qword ptr [rsp+190h+var_170], rax; int
0x180012966  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001296b  mov     ebx, eax
0x18001296d  test    eax, eax
  ... truncated ...
```
