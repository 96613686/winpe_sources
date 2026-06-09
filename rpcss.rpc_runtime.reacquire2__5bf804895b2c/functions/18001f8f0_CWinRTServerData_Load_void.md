# CWinRTServerData::Load(void)

- ea: `0x18001f8f0`
- end: `0x18002056d`
- name: `?Load@CWinRTServerData@@QEAAJXZ`
- size: `3197`
- prototype: `__int64 __fastcall(CWinRTServerData *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180065988`

## callees

- `0x180003194`
- `0x18000fb8c`
- `0x18001f340`
- `0x18001f8f0`
- `0x180020574`
- `0x1800210f8`
- `0x180025950`
- `0x1800535d0`
- `0x18005ad10`
- `0x180093f20`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x180114010`

## import_xrefs

- `ntdll!RtlCreateVirtualAccountSid` at `0x1800204f8`
- `ntdll!RtlCreateVirtualAccountSid` at `0x1800204f8`
- `ntdll!RtlInitUnicodeString` at `0x1800204d6`
- `ntdll!RtlInitUnicodeString` at `0x1800204d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f99a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fc52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fcae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f99a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fc52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fcae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f97b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f97b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001faa5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001faa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f98c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fca0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f98c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fca0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ffce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ffce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180020021`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180020021`
- `KERNELBASE!LocalAlloc` at `0x180020452`
- `KERNELBASE!LocalAlloc` at `0x180020452`
- `KERNELBASE!ParseApplicationUserModelId` at `0x18001fff4`
- `KERNELBASE!ParseApplicationUserModelId` at `0x18001fff4`

## string_xrefs

- `0x18001fb23`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001feac`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001feea`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001ff0a`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001ff4d`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020114`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020196`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x1800201c4`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x1800201f8`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020218`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020238`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020258`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020278`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x1800202a2`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x1800202cc`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002031e`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020381`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x1800203a1`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x1800203c1`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020411`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020471`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180020513`: `onecore\com\combase\rpcss\olescm\clsid.cxx`

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
0x18001f8f0  push    rbp
0x18001f8f2  push    rbx
0x18001f8f3  push    rdi
0x18001f8f4  push    r13
0x18001f8f6  lea     rbp, [rsp-0C8h]
0x18001f8fe  sub     rsp, 1C8h
0x18001f905  mov     rax, cs:__security_cookie
0x18001f90c  xor     rax, rsp
0x18001f90f  mov     [rbp+0E0h+var_30], rax
0x18001f916  mov     rdi, rcx
0x18001f919  lea     r8, [rsp+1E0h+var_1B0]
0x18001f91e  mov     rcx, [rcx+10h]
0x18001f922  lea     rdx, _GUID_430be197_0244_2f7b_80fd_c7c473983ad0
0x18001f929  xor     r13d, r13d
0x18001f92c  mov     [rsp+1E0h+var_1B0], r13
0x18001f931  mov     rax, [rcx]
0x18001f934  mov     rax, [rax]
0x18001f937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f93c  mov     ebx, eax
0x18001f93e  test    eax, eax
0x18001f940  js      loc_1800201BD
0x18001f946  mov     [rsp+1E0h+arg_8], rsi
0x18001f94e  mov     [rsp+1E0h+arg_10], r12
0x18001f956  mov     [rsp+1E0h+arg_18], r14
0x18001f95e  mov     r14, [rdi+40h]
0x18001f962  mov     [rsp+1E0h+var_20], r15
0x18001f96a  mov     r15, [rsp+1E0h+var_1B0]
0x18001f96f  mov     rax, [r15]
0x18001f972  mov     r12, [rax+20h]
0x18001f976  test    r14, r14
0x18001f979  jz      short loc_18001F9A6
0x18001f97b  call    cs:__imp_GetLastError
0x18001f982  nop     dword ptr [rax+rax+00h]
0x18001f987  mov     rcx, r14; string
0x18001f98a  mov     ebx, eax
0x18001f98c  call    cs:__imp_WindowsDeleteString
0x18001f993  nop     dword ptr [rax+rax+00h]
0x18001f998  mov     ecx, ebx; dwErrCode
0x18001f99a  call    cs:__imp_SetLastError
0x18001f9a1  nop     dword ptr [rax+rax+00h]
0x18001f9a6  lea     rdx, [rdi+40h]
0x18001f9aa  mov     [rdi+40h], r13
0x18001f9ae  mov     rcx, r15
0x18001f9b1  mov     rax, r12
0x18001f9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9b9  mov     ebx, eax
0x18001f9bb  test    eax, eax
0x18001f9bd  js      loc_1800201F1
0x18001f9c3  mov     rcx, [rsp+1E0h+var_1B0]
0x18001f9c8  lea     rdx, [rdi+48h]
0x18001f9cc  mov     rax, [rcx]
0x18001f9cf  mov     rax, [rax+28h]
0x18001f9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9d8  mov     ebx, eax
0x18001f9da  test    eax, eax
0x18001f9dc  js      loc_180020211
0x18001f9e2  mov     rcx, [rdi+10h]
0x18001f9e6  lea     rdx, [rdi+18h]
0x18001f9ea  mov     rax, [rcx]
0x18001f9ed  mov     rax, [rax+18h]
0x18001f9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9f6  mov     ebx, eax
0x18001f9f8  test    eax, eax
0x18001f9fa  js      loc_180020231
0x18001fa00  mov     rcx, [rdi+10h]
0x18001fa04  lea     rdx, [rbp+0E0h+var_160]
0x18001fa08  mov     [rbp+0E0h+var_160], r13
0x18001fa0c  mov     rax, [rcx]
0x18001fa0f  mov     rax, [rax+88h]
0x18001fa16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa1b  mov     rdx, [rbp+0E0h+var_160]; unsigned __int16 *
0x18001fa1f  test    rdx, rdx
0x18001fa22  jnz     loc_18001FE76
0x18001fa28  mov     rcx, [rdi+10h]
0x18001fa2c  lea     rdx, [rsp+1E0h+var_180]
0x18001fa31  mov     [rsp+1E0h+var_180], r13d
0x18001fa36  mov     rax, [rcx]
0x18001fa39  mov     rax, [rax+60h]
0x18001fa3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa42  mov     ebx, eax
0x18001fa44  test    eax, eax
0x18001fa46  js      loc_180020251
0x18001fa4c  mov     eax, [rsp+1E0h+var_180]
0x18001fa50  mov     [rdi+70h], eax
0x18001fa53  cmp     eax, 1
0x18001fa56  jz      loc_18001FEC5
0x18001fa5c  cmp     eax, 2
0x18001fa5f  jz      loc_180020041
0x18001fa65  mov     rax, [rdi+28h]
0x18001fa69  test    rax, rax
0x18001fa6c  jz      loc_18001FBD3
0x18001fa72  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001fa79  mov     rbx, rcx
0x18001fa7c  nop     dword ptr [rax+00h]
0x18001fa80  inc     rbx
0x18001fa83  cmp     [rax+rbx*2], r13w
0x18001fa88  jnz     short loc_18001FA80
0x18001fa8a  inc     rbx
0x18001fa8d  mov     eax, 2
0x18001fa92  mul     rbx
0x18001fa95  cmovb   rax, rcx
0x18001fa99  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001faa0  mov     r8, rax; dwBytes
0x18001faa3  xor     edx, edx; dwFlags
0x18001faa5  call    cs:__imp_HeapAlloc
0x18001faac  nop     dword ptr [rax+rax+00h]
0x18001fab1  mov     [rdi+38h], rax
0x18001fab5  mov     r8, rax
0x18001fab8  test    rax, rax
0x18001fabb  jz      loc_18001FF03
0x18001fac1  test    rbx, rbx
0x18001fac4  jz      loc_180020178
0x18001faca  cmp     rbx, 7FFFFFFFh
0x18001fad1  ja      loc_180020300
0x18001fad7  mov     rdx, [rdi+28h]
0x18001fadb  mov     eax, 7FFFFFFEh
0x18001fae0  test    rax, rax
0x18001fae3  jz      short loc_18001FB02
0x18001fae5  movzx   ecx, word ptr [rdx]
0x18001fae8  test    cx, cx
0x18001faeb  jz      short loc_18001FB02
0x18001faed  mov     [r8], cx
0x18001faf1  add     rdx, 2
0x18001faf5  add     r8, 2
0x18001faf9  dec     rax
0x18001fafc  sub     rbx, 1
0x18001fb00  jnz     short loc_18001FAE0
0x18001fb02  test    rbx, rbx
0x18001fb05  lea     rcx, [r8-2]
0x18001fb09  mov     esi, 8007007Ah
0x18001fb0e  cmovnz  rcx, r8
0x18001fb12  cmovnz  esi, r13d
0x18001fb16  mov     [rcx], r13w
0x18001fb1a  jnz     short loc_18001FB8C
0x18001fb1c  mov     rcx, [rbp+0E8h]; this
0x18001fb23  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18001fb2a  mov     r9d, esi; char *
0x18001fb2d  mov     edx, 0D1Ah; void *
0x18001fb32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb37  mov     rcx, [rsp+1E0h+var_1B0]
0x18001fb3c  test    rcx, rcx
0x18001fb3f  jnz     loc_180020369
0x18001fb45  mov     rcx, rdi; this
0x18001fb48  call    ?Purge@CWinRTServerData@@QEAAXXZ; CWinRTServerData::Purge(void)
0x18001fb4d  mov     eax, esi
0x18001fb4f  mov     r14, [rsp+1E0h+arg_18]
0x18001fb57  mov     r12, [rsp+1E0h+arg_10]
0x18001fb5f  mov     rsi, [rsp+1E0h+arg_8]
0x18001fb67  mov     r15, [rsp+1E0h+var_20]
0x18001fb6f  mov     rcx, [rbp+0E0h+var_30]
0x18001fb76  xor     rcx, rsp; StackCookie
0x18001fb79  call    __security_check_cookie
0x18001fb7e  add     rsp, 1C8h
0x18001fb85  pop     r13
0x18001fb87  pop     rdi
0x18001fb88  pop     rbx
0x18001fb89  pop     rbp
0x18001fb8a  retn
0x18001fb8c  mov     rcx, [rdi+38h]
0x18001fb90  movzx   eax, word ptr [rcx]
0x18001fb93  test    ax, ax
0x18001fb96  jz      short loc_18001FBAB
0x18001fb98  cmp     ax, 5Ch ; '\'
0x18001fb9c  jz      short loc_18001FBAB
0x18001fb9e  movzx   eax, word ptr [rcx+2]
0x18001fba2  add     rcx, 2
0x18001fba6  test    ax, ax
0x18001fba9  jnz     short loc_18001FB98
0x18001fbab  cmp     [rcx], r13w
0x18001fbaf  jz      loc_18002030A
0x18001fbb5  mov     [rcx], r13w
0x18001fbb9  mov     rax, [rdi+38h]
0x18001fbbd  mov     [rdi+30h], rax
0x18001fbc1  lea     rax, [rcx+2]
0x18001fbc5  mov     [rdi+38h], rax
0x18001fbc9  cmp     [rax], r13w
0x18001fbcd  jz      loc_18002031A
0x18001fbd3  mov     rcx, [rdi+10h]
0x18001fbd7  lea     r8, [rsp+1E0h+var_1A0]
0x18001fbdc  mov     [rsp+1E0h+var_1A0], r13
0x18001fbe1  lea     rdx, _GUID_000001ed_0000_0000_c000_000000000046
0x18001fbe8  mov     rax, [rcx]
0x18001fbeb  mov     rax, [rax]
0x18001fbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbf3  mov     ebx, eax
0x18001fbf5  test    eax, eax
0x18001fbf7  js      loc_18002016E
0x18001fbfd  mov     rcx, [rsp+1E0h+var_1A0]
0x18001fc02  lea     rdx, [rdi+100h]
0x18001fc09  mov     rax, [rcx]
0x18001fc0c  mov     rax, [rax+50h]
0x18001fc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc15  mov     ebx, eax
0x18001fc17  test    eax, eax
0x18001fc19  js      loc_18001FF41
0x18001fc1f  mov     r14, [rdi+10h]
0x18001fc23  mov     r15, [rdi+50h]
0x18001fc27  mov     rax, [r14]
0x18001fc2a  mov     r12, [rax+40h]
0x18001fc2e  test    r15, r15
0x18001fc31  jz      short loc_18001FC5E
0x18001fc33  call    cs:__imp_GetLastError
0x18001fc3a  nop     dword ptr [rax+rax+00h]
0x18001fc3f  mov     rcx, r15; string
0x18001fc42  mov     ebx, eax
0x18001fc44  call    cs:__imp_WindowsDeleteString
0x18001fc4b  nop     dword ptr [rax+rax+00h]
0x18001fc50  mov     ecx, ebx; dwErrCode
0x18001fc52  call    cs:__imp_SetLastError
0x18001fc59  nop     dword ptr [rax+rax+00h]
0x18001fc5e  lea     rdx, [rdi+50h]
0x18001fc62  mov     [rdi+50h], r13
0x18001fc66  mov     rcx, r14
0x18001fc69  mov     rax, r12
0x18001fc6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc71  mov     ebx, eax
0x18001fc73  test    eax, eax
0x18001fc75  js      loc_18002037A
0x18001fc7b  mov     r14, [rdi+10h]
0x18001fc7f  mov     r15, [rdi+60h]
0x18001fc83  mov     rax, [r14]
0x18001fc86  mov     r12, [rax+48h]
0x18001fc8a  test    r15, r15
0x18001fc8d  jz      short loc_18001FCBA
0x18001fc8f  call    cs:__imp_GetLastError
0x18001fc96  nop     dword ptr [rax+rax+00h]
0x18001fc9b  mov     rcx, r15; string
0x18001fc9e  mov     ebx, eax
0x18001fca0  call    cs:__imp_WindowsDeleteString
0x18001fca7  nop     dword ptr [rax+rax+00h]
0x18001fcac  mov     ecx, ebx; dwErrCode
0x18001fcae  call    cs:__imp_SetLastError
0x18001fcb5  nop     dword ptr [rax+rax+00h]
0x18001fcba  lea     rdx, [rdi+60h]
0x18001fcbe  mov     [rdi+60h], r13
0x18001fcc2  mov     rcx, r14
0x18001fcc5  mov     rax, r12
0x18001fcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fccd  mov     ebx, eax
0x18001fccf  test    eax, eax
0x18001fcd1  js      loc_18002039A
0x18001fcd7  mov     rbx, [rdi+60h]
0x18001fcdb  test    rbx, rbx
0x18001fcde  jnz     loc_18001FF8F
0x18001fce4  mov     rcx, [rdi+10h]
0x18001fce8  lea     rdx, [rsp+1E0h+var_178]
0x18001fced  mov     [rsp+1E0h+var_178], r13d
0x18001fcf2  mov     rax, [rcx]
0x18001fcf5  mov     rax, [rax+90h]
0x18001fcfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd01  mov     eax, [rsp+1E0h+var_178]
0x18001fd05  lea     rdx, [rdi+78h]
0x18001fd09  mov     rcx, [rdi+10h]
0x18001fd0d  mov     [rdi+74h], eax
0x18001fd10  mov     rax, [rcx]
0x18001fd13  mov     rax, [rax+68h]
0x18001fd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd1c  mov     rcx, [rdi+10h]
0x18001fd20  lea     rdx, [rdi+68h]
0x18001fd24  mov     rax, [rcx]
0x18001fd27  mov     rax, [rax+70h]
0x18001fd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd30  mov     rcx, [rdi+10h]
0x18001fd34  lea     r8, [rsp+1E0h+var_188]
0x18001fd39  mov     [rsp+1E0h+var_188], r13
0x18001fd3e  lea     rdx, _GUID_6acfc1bf_3882_45b1_96a3_ab948a267d38
0x18001fd45  mov     rax, [rcx]
0x18001fd48  mov     rax, [rax]
0x18001fd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd50  mov     ebx, eax
0x18001fd52  test    eax, eax
0x18001fd54  js      loc_18002018F
0x18001fd5a  mov     rcx, [rsp+1E0h+var_188]
0x18001fd5f  lea     rdx, [rdi+7Ch]
0x18001fd63  mov     rax, [rcx]
0x18001fd66  mov     rax, [rax+0A8h]
0x18001fd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd72  not     eax
0x18001fd74  lea     r8, [rsp+1E0h+var_190]
0x18001fd79  shr     eax, 1Fh
0x18001fd7c  lea     rdx, _GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680
0x18001fd83  mov     [rdi+80h], eax
0x18001fd89  mov     rcx, [rdi+10h]
0x18001fd8d  mov     [rsp+1E0h+var_190], r13
0x18001fd92  mov     rax, [rcx]
0x18001fd95  mov     rax, [rax]
0x18001fd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd9d  mov     ebx, eax
0x18001fd9f  test    eax, eax
0x18001fda1  js      loc_18002010D
0x18001fda7  mov     rcx, [rsp+1E0h+var_190]
0x18001fdac  lea     rdx, [rdi+84h]
0x18001fdb3  mov     rax, [rcx]
0x18001fdb6  mov     rax, [rax+0B8h]
0x18001fdbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdc2  mov     rcx, [rsp+1E0h+var_190]
0x18001fdc7  lea     rdx, [rdi+88h]
0x18001fdce  mov     rax, [rcx]
0x18001fdd1  mov     rax, [rax+0C0h]
0x18001fdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
