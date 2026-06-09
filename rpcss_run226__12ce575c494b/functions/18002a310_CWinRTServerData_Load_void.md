# CWinRTServerData::Load(void)

- ea: `0x18002a310`
- end: `0x18002af34`
- name: `?Load@CWinRTServerData@@QEAAJXZ`
- size: `3108`
- prototype: `__int64 __fastcall(CWinRTServerData *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180060644`

## callees

- `0x180003064`
- `0x18000b428`
- `0x180029db0`
- `0x18002a310`
- `0x18002af3c`
- `0x18002ba28`
- `0x18002f8cc`
- `0x180043850`
- `0x180054b7c`
- `0x18008cd90`
- `0x1800b27e0`
- `0x1800b3128`
- `0x18010b010`

## import_xrefs

- `ntdll!RtlCreateVirtualAccountSid` at `0x18002aec5`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18002aec5`
- `ntdll!RtlInitUnicodeString` at `0x18002aea9`
- `ntdll!RtlInitUnicodeString` at `0x18002aea9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a3ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a655`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a69f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a3ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a655`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a69f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a39b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a68c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a39b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a68c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a4b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a4b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a3a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a64d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a3a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a64d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a9b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a9b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002aa00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002aa00`
- `KERNELBASE!LocalAlloc` at `0x18002ae2b`
- `KERNELBASE!LocalAlloc` at `0x18002ae2b`
- `KERNELBASE!ParseApplicationUserModelId` at `0x18002a9d9`
- `KERNELBASE!ParseApplicationUserModelId` at `0x18002a9d9`

## string_xrefs

- `0x18002a533`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a897`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a8d5`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a8f5`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a938`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002aaed`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ab6f`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ab9d`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002abd1`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002abf1`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ac11`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ac31`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ac51`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ac7b`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002aca5`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002acf7`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ad5a`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ad7a`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ad9a`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002adea`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002ae44`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002aeda`: `onecore\com\combase\rpcss\olescm\clsid.cxx`

## pseudocode

```c
__int64 __fastcall CWinRTServerData::Load(CWinRTServerData *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  int v3; // eax
  unsigned int v4; // ebx
  HSTRING v5; // r14
  __int64 v6; // r15
  __int64 (__fastcall *v7)(__int64, char *); // r12
  DWORD LastError; // ebx
  int v9; // eax
  HRESULT String; // ebx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rbx
  unsigned __int64 v19; // rbx
  SIZE_T v20; // rax
  _WORD *v21; // rax
  _WORD *v22; // r8
  _WORD *v23; // rdx
  __int64 v24; // rax
  _WORD *v25; // rcx
  unsigned int v26; // esi
  __int16 *v28; // rcx
  __int16 i; // ax
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v31; // r14
  HSTRING v32; // r15
  __int64 (__fastcall *v33)(__int64, char *); // r12
  DWORD v34; // ebx
  int v35; // eax
  __int64 v36; // r14
  HSTRING v37; // r15
  __int64 (__fastcall *v38)(__int64, char *); // r12
  DWORD v39; // ebx
  int v40; // eax
  HSTRING v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // rcx
  int v45; // eax
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // rcx
  int v47; // eax
  const struct _GUID *v48; // rcx
  int UserServiceNameIfAvailable; // eax
  int v50; // eax
  __int64 v51; // rdx
  void (*v52)(void); // rax
  const WCHAR *StringRawBuffer; // rax
  unsigned int v54; // eax
  void (__fastcall ***v55)(_QWORD, GUID *, struct _UNICODE_STRING *); // rcx
  int v56; // eax
  __int64 v57; // rcx
  int v58; // eax
  __int64 v59; // rcx
  int v60; // eax
  __int64 v61; // rcx
  void (*v62)(void); // rax
  int v63; // eax
  HLOCAL v64; // rax
  int v65; // eax
  int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  __int64 v67; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v69; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v71; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v72; // [rsp+58h] [rbp-A8h] BYREF
  int v73; // [rsp+60h] [rbp-A0h] BYREF
  int v74; // [rsp+64h] [rbp-9Ch] BYREF
  int v75; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v77; // [rsp+80h] [rbp-80h] BYREF
  WCHAR sourceString[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v79[140]; // [rsp+94h] [rbp-6Ch] BYREF
  WCHAR packageFamilyName[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v81[140]; // [rsp+124h] [rbp+24h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
  v67 = 0;
  v3 = (**v2)(v2, &GUID_430be197_0244_2f7b_80fd_c7c473983ad0, &v67);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE5,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)(unsigned int)v3,
      packageRelativeApplicationId);
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v67);
    CWinRTServerData::Purge(this);
    return v4;
  }
  v5 = (HSTRING)*((_QWORD *)this + 8);
  v6 = v67;
  v7 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v67 + 32LL);
  if ( v5 )
  {
    LastError = GetLastError();
    WindowsDeleteString(v5);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 8) = 0;
  v9 = v7(v6, (char *)this + 64);
  String = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCED,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)(unsigned int)v9,
      packageRelativeApplicationId);
    goto LABEL_113;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v67 + 40LL))(v67, (char *)this + 72);
  String = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCEE,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)(unsigned int)v11,
      packageRelativeApplicationId);
    goto LABEL_113;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 2) + 24LL))(
          *((_QWORD *)this + 2),
          (char *)this + 24);
  String = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF1,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)(unsigned int)v12,
      packageRelativeApplicationId);
    goto LABEL_113;
  }
  v13 = *((_QWORD *)this + 2);
  v77 = 0;
  (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v13 + 136LL))(v13, &v77);
  if ( v77 )
  {
    UserServiceNameIfAvailable = GetUserServiceNameIfAvailable(
                                   *((struct IUnknown **)this + 2),
                                   v77,
                                   *(struct CToken **)this,
                                   *((_QWORD *)this + 1),
                                   (unsigned __int16 **)this + 4,
                                   (bool *)this + 240);
    String = UserServiceNameIfAvailable;
    if ( UserServiceNameIfAvailable < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCF7,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
        (const char *)(unsigned int)UserServiceNameIfAvailable,
        packageRelativeApplicationId);
LABEL_113:
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v67);
LABEL_71:
      CWinRTServerData::Purge(this);
      return (unsigned int)String;
    }
  }
  v14 = *((_QWORD *)this + 2);
  v73 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 96LL))(v14, &v73);
  String = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCFB,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)(unsigned int)v15,
      packageRelativeApplicationId);
    goto LABEL_113;
  }
  v16 = v73;
  *((_DWORD *)this + 28) = v73;
  if ( v16 == 1 )
  {
    v50 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 2) + 88LL))(
            *((_QWORD *)this + 2),
            (char *)this + 40);
    String = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD01,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
        (const char *)(unsigned int)v50,
        packageRelativeApplicationId);
      goto LABEL_113;
    }
  }
  else if ( v16 == 2 )
  {
    v55 = (void (__fastcall ***)(_QWORD, GUID *, struct _UNICODE_STRING *))*((_QWORD *)this + 2);
    v74 = 0;
    *(_QWORD *)&DestinationString.Length = 0;
    (**v55)(v55, &GUID_6c41cb64_51a5_4177_b4ae_3e1d2e3f0157, &DestinationString);
    v56 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)&DestinationString.Length + 24LL))(
            *(_QWORD *)&DestinationString.Length,
            &v74);
    String = v56;
    if ( v56 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD08,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
        (const char *)(unsigned int)v56,
        packageRelativeApplicationId);
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&DestinationString);
      goto LABEL_113;
    }
    v57 = *(_QWORD *)&DestinationString.Length;
    *((_DWORD *)this + 62) = v74;
    packageFamilyNameLength = 0;
    v58 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v57 + 32LL))(v57, &packageFamilyNameLength);
    String = v58;
    if ( v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD0C,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
        (const char *)(unsigned int)v58,
        packageRelativeApplicationId);
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&DestinationString);
      goto LABEL_113;
    }
    v59 = *(_QWORD *)&DestinationString.Length;
    *((_DWORD *)this + 61) = packageFamilyNameLength;
    packageRelativeApplicationIdLength = 0;
    v60 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v59 + 40LL))(
            v59,
            &packageRelativeApplicationIdLength);
    String = v60;
    if ( v60 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD10,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
        (const char *)(unsigned int)v60,
        packageRelativeApplicationId);
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&DestinationString);
      goto LABEL_113;
    }
    v61 = *(_QWORD *)&DestinationString.Length;
    *((_DWORD *)this + 63) = packageRelativeApplicationIdLength;
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  }
  v17 = *((_QWORD *)this + 5);
  if ( !v17 )
    goto LABEL_34;
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)(v17 + 2 * v18) );
  v19 = v18 + 1;
  v20 = 2 * v19;
  if ( !is_mul_ok(v19, 2u) )
    v20 = -1;
  v21 = HeapAlloc(g_hHeap, 0, v20);
  *((_QWORD *)this + 7) = v21;
  v22 = v21;
  if ( v21 )
  {
    if ( v19 )
    {
      if ( v19 <= 0x7FFFFFFF )
      {
        v23 = (_WORD *)*((_QWORD *)this + 5);
        v24 = 2147483646;
        do
        {
          if ( !v24 )
            break;
          if ( !*v23 )
            break;
          *v22++ = *v23++;
          --v24;
          --v19;
        }
        while ( v19 );
        v25 = v22 - 1;
        v26 = -2147024774;
        if ( v19 )
        {
          v25 = v22;
          v26 = 0;
        }
        *v25 = 0;
        if ( !v19 )
          goto LABEL_26;
        v28 = (__int16 *)*((_QWORD *)this + 7);
        for ( i = *v28; i; ++v28 )
        {
          if ( i == 92 )
            break;
          i = v28[1];
        }
        if ( *v28 )
        {
          *v28 = 0;
          *((_QWORD *)this + 6) = *((_QWORD *)this + 7);
          *((_QWORD *)this + 7) = v28 + 1;
          if ( !v28[1] )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0xD37,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
              (const char *)0x80004005LL,
              (int)"Server:%ls",
              *((const char **)this + 3));
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v67);
            CWinRTServerData::Purge(this);
            return 2147500037LL;
          }
        }
        else
        {
          *((_QWORD *)this + 6) = L".";
        }
LABEL_34:
        v30 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
        v69 = 0;
        String = (**v30)(v30, &GUID_000001ed_0000_0000_c000_000000000046, &v69);
        if ( String < 0 )
        {
          v51 = 3389;
          goto LABEL_66;
        }
        String = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v69 + 80LL))(v69, (char *)this + 256);
        if ( String < 0 )
        {
          v51 = 3390;
LABEL_66:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v51,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
            (const char *)(unsigned int)String,
            packageRelativeApplicationId);
          if ( !v69 )
            goto LABEL_69;
          v52 = *(void (**)(void))(*(_QWORD *)v69 + 16LL);
          goto LABEL_68;
        }
        v31 = *((_QWORD *)this + 2);
        v32 = (HSTRING)*((_QWORD *)this + 10);
        v33 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v31 + 64LL);
        if ( v32 )
        {
          v34 = GetLastError();
          WindowsDeleteString(v32);
          SetLastError(v34);
        }
        *((_QWORD *)this + 10) = 0;
        v35 = v33(v31, (char *)this + 80);
        String = v35;
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD41,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
            (const char *)(unsigned int)v35,
            packageRelativeApplicationId);
          goto LABEL_112;
        }
        v36 = *((_QWORD *)this + 2);
        v37 = (HSTRING)*((_QWORD *)this + 12);
        v38 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v36 + 72LL);
        if ( v37 )
        {
          v39 = GetLastError();
          WindowsDeleteString(v37);
          SetLastError(v39);
        }
        *((_QWORD *)this + 12) = 0;
        v40 = v38(v36, (char *)this + 96);
        String = v40;
        if ( v40 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD44,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
            (const char *)(unsigned int)v40,
            packageRelativeApplicationId);
          goto LABEL_112;
        }
        v41 = (HSTRING)*((_QWORD *)this + 12);
        if ( v41 )
        {
          *(_DWORD *)packageFamilyName = 0;
          memset_0(v81, 0, 0x7Eu);
          *(_DWORD *)sourceString = 0;
          memset_0(v79, 0, 0x80u);
          packageFamilyNameLength = 65;
          packageRelativeApplicationIdLength = 66;
          StringRawBuffer = WindowsGetStringRawBuffer(v41, 0);
          v54 = ParseApplicationUserModelId(
                  StringRawBuffer,
                  &packageFamilyNameLength,
                  packageFamilyName,
                  &packageRelativeApplicationIdLength,
                  sourceString);
          if ( v54 )
          {
            String = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0xD4C,
                       (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
                       (const char *)v54,
                       packageRelativeApplicationId);
            goto LABEL_112;
          }
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
            (char *)this + 88,
            0);
          String = WindowsCreateString(sourceString, packageRelativeApplicationIdLength - 1, (HSTRING *)this + 11);
          if ( String < 0 )
          {
            v51 = 3406;
            goto LABEL_66;
          }
        }
        v42 = *((_QWORD *)this + 2);
        v75 = 0;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 144LL))(v42, &v75);
        v43 = *((_QWORD *)this + 2);
        *((_DWORD *)this + 29) = v75;
        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v43 + 104LL))(v43, (char *)this + 120);
        (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 2) + 112LL))(
          *((_QWORD *)this + 2),
          (char *)this + 104);
        v44 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
        v72 = 0;
        v45 = (**v44)(v44, &GUID_6acfc1bf_3882_45b1_96a3_ab948a267d38, &v72);
        String = v45;
        if ( v45 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD5E,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
            (const char *)(unsigned int)v45,
            packageRelativeApplicationId);
          if ( !v72 )
            goto LABEL_85;
          v62 = *(void (**)(void))(*(_QWORD *)v72 + 16LL);
        }
        else
        {
          *((_DWORD *)this + 32) = (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v72 + 168LL))(
                                     v72,
                                     (char *)this + 124) >= 0;
          v46 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
          v71 = 0;
          v47 = (**v46)(v46, &GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680, &v71);
          String = v47;
          if ( v47 >= 0 )
          {
            (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v71 + 184LL))(v71, (char *)this + 132);
            (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v71 + 192LL))(v71, (char *)this + 136);
            if ( !*((_QWORD *)this + 5) || (*((_BYTE *)this + 136) & 2) == 0 )
            {
              (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 2) + 32LL))(
                *((_QWORD *)this + 2),
                (char *)this + 144);
              v48 = (const struct _GUID *)*((_QWORD *)this + 18);
              if ( v48 )
                wStringFromGUID2(v48, (unsigned __int16 *)this + 76, 39);
LABEL_49:
              if ( v71 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
              if ( v72 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
              if ( v69 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
              if ( v67 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
              return 0;
            }
            v63 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 2) + 32LL))(
                    *((_QWORD *)this + 2),
                    (char *)this + 144);
            String = v63;
            if ( v63 >= 0 )
            {
              wStringFromGUID2(*((const struct _GUID **)this + 18), (unsigned __int16 *)this + 76, 39);
              packageRelativeApplicationIdLength = 68;
              v64 = LocalAlloc(0, 0x44u);
              *((_QWORD *)this + 29) = v64;
              if ( !v64 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xD78,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
                  (const char *)0x8007000ELL,
                  packageRelativeApplicationId);
                wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v71);
                wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v72);
                wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v69);
                wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v67);
                CWinRTServerData::Purge(this);
                return 2147942414LL;
              }
              DestinationString = 0;
              RtlInitUnicodeString(&DestinationString, (PCWSTR)this + 76);
              v65 = RtlCreateVirtualAccountSid(
                      &DestinationString,
                      89,
                      *((_QWORD *)this + 29),
                      &packageRelativeApplicationIdLength);
              if ( v65 >= 0 )
                goto LABEL_49;
              String = wil::details::in1diag3::Return_NtStatus(
                         retaddr,
                         (void *)0xD7B,
                         (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
                         (const char *)(unsigned int)v65,
                         packageRelativeApplicationId);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD73,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
                (const char *)(unsigned int)v63,
                packageRelativeApplicationId);
            }
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v71);
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v72);
LABEL_112:
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v69);
            goto LABEL_113;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD6C,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
            (const char *)(unsigned int)v47,
            packageRelativeApplicationId);
          if ( v71 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
          if ( !v72 )
          {
LABEL_85:
            if ( !v69 )
            {
LABEL_69:
              if ( v67 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
              goto LABEL_71;
            }
            v52 = *(void (**)(void))(*(_QWORD *)v69 + 16LL);
LABEL_68:
            v52();
            goto LABEL_69;
          }
          v62 = *(void (**)(void))(*(_QWORD *)v72 + 16LL);
        }
        v62();
        goto LABEL_85;
      }
      v26 = -2147024809;
      *v21 = 0;
    }
    else
    {
      v26 = -2147024809;
    }
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1A,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)v26,
      packageRelativeApplicationId);
    if ( v67 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    CWinRTServerData::Purge(this);
    return v26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD18,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
    (const char *)0x8007000ELL,
    packageRelativeApplicationId);
  if ( v67 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  CWinRTServerData::Purge(this);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002a310  push    rbp
0x18002a312  push    rbx
0x18002a313  push    rdi
0x18002a314  push    r13
0x18002a316  lea     rbp, [rsp-0C8h]
0x18002a31e  sub     rsp, 1C8h
0x18002a325  mov     rax, cs:__security_cookie
0x18002a32c  xor     rax, rsp
0x18002a32f  mov     [rbp+0E0h+var_30], rax
0x18002a336  mov     rdi, rcx
0x18002a339  lea     r8, [rsp+1E0h+var_1B0]
0x18002a33e  mov     rcx, [rcx+10h]
0x18002a342  lea     rdx, _GUID_430be197_0244_2f7b_80fd_c7c473983ad0
0x18002a349  xor     r13d, r13d
0x18002a34c  mov     [rsp+1E0h+var_1B0], r13
0x18002a351  mov     rax, [rcx]
0x18002a354  mov     rax, [rax]
0x18002a357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a35c  mov     ebx, eax
0x18002a35e  test    eax, eax
0x18002a360  js      loc_18002AB96
0x18002a366  mov     [rsp+1E0h+arg_8], rsi
0x18002a36e  mov     [rsp+1E0h+arg_10], r12
0x18002a376  mov     [rsp+1E0h+arg_18], r14
0x18002a37e  mov     r14, [rdi+40h]
0x18002a382  mov     [rsp+1E0h+var_20], r15
0x18002a38a  mov     r15, [rsp+1E0h+var_1B0]
0x18002a38f  mov     rax, [r15]
0x18002a392  mov     r12, [rax+20h]
0x18002a396  test    r14, r14
0x18002a399  jz      short loc_18002A3B4
0x18002a39b  call    cs:__imp_GetLastError
0x18002a3a1  mov     rcx, r14; string
0x18002a3a4  mov     ebx, eax
0x18002a3a6  call    cs:__imp_WindowsDeleteString
0x18002a3ac  mov     ecx, ebx; dwErrCode
0x18002a3ae  call    cs:__imp_SetLastError
0x18002a3b4  lea     rdx, [rdi+40h]
0x18002a3b8  mov     [rdi+40h], r13
0x18002a3bc  mov     rcx, r15
0x18002a3bf  mov     rax, r12
0x18002a3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3c7  mov     ebx, eax
0x18002a3c9  test    eax, eax
0x18002a3cb  js      loc_18002ABCA
0x18002a3d1  mov     rcx, [rsp+1E0h+var_1B0]
0x18002a3d6  lea     rdx, [rdi+48h]
0x18002a3da  mov     rax, [rcx]
0x18002a3dd  mov     rax, [rax+28h]
0x18002a3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3e6  mov     ebx, eax
0x18002a3e8  test    eax, eax
0x18002a3ea  js      loc_18002ABEA
0x18002a3f0  mov     rcx, [rdi+10h]
0x18002a3f4  lea     rdx, [rdi+18h]
0x18002a3f8  mov     rax, [rcx]
0x18002a3fb  mov     rax, [rax+18h]
0x18002a3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a404  mov     ebx, eax
0x18002a406  test    eax, eax
0x18002a408  js      loc_18002AC0A
0x18002a40e  mov     rcx, [rdi+10h]
0x18002a412  lea     rdx, [rbp+0E0h+var_160]
0x18002a416  mov     [rbp+0E0h+var_160], r13
0x18002a41a  mov     rax, [rcx]
0x18002a41d  mov     rax, [rax+88h]
0x18002a424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a429  mov     rdx, [rbp+0E0h+var_160]; unsigned __int16 *
0x18002a42d  test    rdx, rdx
0x18002a430  jnz     loc_18002A861
0x18002a436  mov     rcx, [rdi+10h]
0x18002a43a  lea     rdx, [rsp+1E0h+var_180]
0x18002a43f  mov     [rsp+1E0h+var_180], r13d
0x18002a444  mov     rax, [rcx]
0x18002a447  mov     rax, [rax+60h]
0x18002a44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a450  mov     ebx, eax
0x18002a452  test    eax, eax
0x18002a454  js      loc_18002AC2A
0x18002a45a  mov     eax, [rsp+1E0h+var_180]
0x18002a45e  mov     [rdi+70h], eax
0x18002a461  cmp     eax, 1
0x18002a464  jz      loc_18002A8B0
0x18002a46a  cmp     eax, 2
0x18002a46d  jz      loc_18002AA1A
0x18002a473  mov     rax, [rdi+28h]
0x18002a477  test    rax, rax
0x18002a47a  jz      loc_18002A5E2
0x18002a480  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a487  mov     rbx, rcx
0x18002a48a  nop     word ptr [rax+rax+00h]
0x18002a490  inc     rbx
0x18002a493  cmp     [rax+rbx*2], r13w
0x18002a498  jnz     short loc_18002A490
0x18002a49a  inc     rbx
0x18002a49d  mov     eax, 2
0x18002a4a2  mul     rbx
0x18002a4a5  cmovb   rax, rcx
0x18002a4a9  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002a4b0  mov     r8, rax; dwBytes
0x18002a4b3  xor     edx, edx; dwFlags
0x18002a4b5  call    cs:__imp_HeapAlloc
0x18002a4bb  mov     [rdi+38h], rax
0x18002a4bf  mov     r8, rax
0x18002a4c2  test    rax, rax
0x18002a4c5  jz      loc_18002A8EE
0x18002a4cb  test    rbx, rbx
0x18002a4ce  jz      loc_18002AB51
0x18002a4d4  cmp     rbx, 7FFFFFFFh
0x18002a4db  ja      loc_18002ACD9
0x18002a4e1  mov     rdx, [rdi+28h]
0x18002a4e5  mov     eax, 7FFFFFFEh
0x18002a4ea  nop     word ptr [rax+rax+00h]
0x18002a4f0  test    rax, rax
0x18002a4f3  jz      short loc_18002A512
0x18002a4f5  movzx   ecx, word ptr [rdx]
0x18002a4f8  test    cx, cx
0x18002a4fb  jz      short loc_18002A512
0x18002a4fd  mov     [r8], cx
0x18002a501  add     rdx, 2
0x18002a505  add     r8, 2
0x18002a509  dec     rax
0x18002a50c  sub     rbx, 1
0x18002a510  jnz     short loc_18002A4F0
0x18002a512  test    rbx, rbx
0x18002a515  lea     rcx, [r8-2]
0x18002a519  mov     esi, 8007007Ah
0x18002a51e  cmovnz  rcx, r8
0x18002a522  cmovnz  esi, r13d
0x18002a526  mov     [rcx], r13w
0x18002a52a  jnz     short loc_18002A59B
0x18002a52c  mov     rcx, [rbp+0E8h]; this
0x18002a533  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18002a53a  mov     r9d, esi; char *
0x18002a53d  mov     edx, 0D1Ah; void *
0x18002a542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a547  mov     rcx, [rsp+1E0h+var_1B0]
0x18002a54c  test    rcx, rcx
0x18002a54f  jnz     loc_18002AD42
0x18002a555  mov     rcx, rdi; this
0x18002a558  call    ?Purge@CWinRTServerData@@QEAAXXZ; CWinRTServerData::Purge(void)
0x18002a55d  mov     eax, esi
0x18002a55f  mov     r14, [rsp+1E0h+arg_18]
0x18002a567  mov     r12, [rsp+1E0h+arg_10]
0x18002a56f  mov     rsi, [rsp+1E0h+arg_8]
0x18002a577  mov     r15, [rsp+1E0h+var_20]
0x18002a57f  mov     rcx, [rbp+0E0h+var_30]
0x18002a586  xor     rcx, rsp; StackCookie
0x18002a589  call    __security_check_cookie
0x18002a58e  add     rsp, 1C8h
0x18002a595  pop     r13
0x18002a597  pop     rdi
0x18002a598  pop     rbx
0x18002a599  pop     rbp
0x18002a59a  retn
0x18002a59b  mov     rcx, [rdi+38h]
0x18002a59f  movzx   eax, word ptr [rcx]
0x18002a5a2  test    ax, ax
0x18002a5a5  jz      short loc_18002A5BA
0x18002a5a7  cmp     ax, 5Ch ; '\'
0x18002a5ab  jz      short loc_18002A5BA
0x18002a5ad  movzx   eax, word ptr [rcx+2]
0x18002a5b1  add     rcx, 2
0x18002a5b5  test    ax, ax
0x18002a5b8  jnz     short loc_18002A5A7
0x18002a5ba  cmp     [rcx], r13w
0x18002a5be  jz      loc_18002ACE3
0x18002a5c4  mov     [rcx], r13w
0x18002a5c8  mov     rax, [rdi+38h]
0x18002a5cc  mov     [rdi+30h], rax
0x18002a5d0  lea     rax, [rcx+2]
0x18002a5d4  mov     [rdi+38h], rax
0x18002a5d8  cmp     [rax], r13w
0x18002a5dc  jz      loc_18002ACF3
0x18002a5e2  mov     rcx, [rdi+10h]
0x18002a5e6  lea     r8, [rsp+1E0h+var_1A0]
0x18002a5eb  mov     [rsp+1E0h+var_1A0], r13
0x18002a5f0  lea     rdx, _GUID_000001ed_0000_0000_c000_000000000046
0x18002a5f7  mov     rax, [rcx]
0x18002a5fa  mov     rax, [rax]
0x18002a5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a602  mov     ebx, eax
0x18002a604  test    eax, eax
0x18002a606  js      loc_18002AB47
0x18002a60c  mov     rcx, [rsp+1E0h+var_1A0]
0x18002a611  lea     rdx, [rdi+100h]
0x18002a618  mov     rax, [rcx]
0x18002a61b  mov     rax, [rax+50h]
0x18002a61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a624  mov     ebx, eax
0x18002a626  test    eax, eax
0x18002a628  js      loc_18002A92C
0x18002a62e  mov     r14, [rdi+10h]
0x18002a632  mov     r15, [rdi+50h]
0x18002a636  mov     rax, [r14]
0x18002a639  mov     r12, [rax+40h]
0x18002a63d  test    r15, r15
0x18002a640  jz      short loc_18002A65B
0x18002a642  call    cs:__imp_GetLastError
0x18002a648  mov     rcx, r15; string
0x18002a64b  mov     ebx, eax
0x18002a64d  call    cs:__imp_WindowsDeleteString
0x18002a653  mov     ecx, ebx; dwErrCode
0x18002a655  call    cs:__imp_SetLastError
0x18002a65b  lea     rdx, [rdi+50h]
0x18002a65f  mov     [rdi+50h], r13
0x18002a663  mov     rcx, r14
0x18002a666  mov     rax, r12
0x18002a669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a66e  mov     ebx, eax
0x18002a670  test    eax, eax
0x18002a672  js      loc_18002AD53
0x18002a678  mov     r14, [rdi+10h]
0x18002a67c  mov     r15, [rdi+60h]
0x18002a680  mov     rax, [r14]
0x18002a683  mov     r12, [rax+48h]
0x18002a687  test    r15, r15
0x18002a68a  jz      short loc_18002A6A5
0x18002a68c  call    cs:__imp_GetLastError
0x18002a692  mov     rcx, r15; string
0x18002a695  mov     ebx, eax
0x18002a697  call    cs:__imp_WindowsDeleteString
0x18002a69d  mov     ecx, ebx; dwErrCode
0x18002a69f  call    cs:__imp_SetLastError
0x18002a6a5  lea     rdx, [rdi+60h]
0x18002a6a9  mov     [rdi+60h], r13
0x18002a6ad  mov     rcx, r14
0x18002a6b0  mov     rax, r12
0x18002a6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6b8  mov     ebx, eax
0x18002a6ba  test    eax, eax
0x18002a6bc  js      loc_18002AD73
0x18002a6c2  mov     rbx, [rdi+60h]
0x18002a6c6  test    rbx, rbx
0x18002a6c9  jnz     loc_18002A97A
0x18002a6cf  mov     rcx, [rdi+10h]
0x18002a6d3  lea     rdx, [rsp+1E0h+var_178]
0x18002a6d8  mov     [rsp+1E0h+var_178], r13d
0x18002a6dd  mov     rax, [rcx]
0x18002a6e0  mov     rax, [rax+90h]
0x18002a6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6ec  mov     eax, [rsp+1E0h+var_178]
0x18002a6f0  lea     rdx, [rdi+78h]
0x18002a6f4  mov     rcx, [rdi+10h]
0x18002a6f8  mov     [rdi+74h], eax
0x18002a6fb  mov     rax, [rcx]
0x18002a6fe  mov     rax, [rax+68h]
0x18002a702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a707  mov     rcx, [rdi+10h]
0x18002a70b  lea     rdx, [rdi+68h]
0x18002a70f  mov     rax, [rcx]
0x18002a712  mov     rax, [rax+70h]
0x18002a716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a71b  mov     rcx, [rdi+10h]
0x18002a71f  lea     r8, [rsp+1E0h+var_188]
0x18002a724  mov     [rsp+1E0h+var_188], r13
0x18002a729  lea     rdx, _GUID_6acfc1bf_3882_45b1_96a3_ab948a267d38
0x18002a730  mov     rax, [rcx]
0x18002a733  mov     rax, [rax]
0x18002a736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a73b  mov     ebx, eax
0x18002a73d  test    eax, eax
0x18002a73f  js      loc_18002AB68
0x18002a745  mov     rcx, [rsp+1E0h+var_188]
0x18002a74a  lea     rdx, [rdi+7Ch]
0x18002a74e  mov     rax, [rcx]
0x18002a751  mov     rax, [rax+0A8h]
0x18002a758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a75d  not     eax
0x18002a75f  lea     r8, [rsp+1E0h+var_190]
0x18002a764  shr     eax, 1Fh
0x18002a767  lea     rdx, _GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680
0x18002a76e  mov     [rdi+80h], eax
0x18002a774  mov     rcx, [rdi+10h]
0x18002a778  mov     [rsp+1E0h+var_190], r13
0x18002a77d  mov     rax, [rcx]
0x18002a780  mov     rax, [rax]
0x18002a783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a788  mov     ebx, eax
0x18002a78a  test    eax, eax
0x18002a78c  js      loc_18002AAE6
0x18002a792  mov     rcx, [rsp+1E0h+var_190]
0x18002a797  lea     rdx, [rdi+84h]
0x18002a79e  mov     rax, [rcx]
0x18002a7a1  mov     rax, [rax+0B8h]
0x18002a7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7ad  mov     rcx, [rsp+1E0h+var_190]
0x18002a7b2  lea     rdx, [rdi+88h]
0x18002a7b9  mov     rax, [rcx]
0x18002a7bc  mov     rax, [rax+0C0h]
0x18002a7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7c8  cmp     [rdi+28h], r13
0x18002a7cc  jz      short loc_18002A7DB
0x18002a7ce  test    byte ptr [rdi+88h], 2
0x18002a7d5  jnz     loc_18002ADC6
0x18002a7db  mov     rcx, [rdi+10h]
0x18002a7df  lea     rdx, [rdi+90h]
0x18002a7e6  mov     rax, [rcx]
0x18002a7e9  mov     rax, [rax+20h]
0x18002a7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
