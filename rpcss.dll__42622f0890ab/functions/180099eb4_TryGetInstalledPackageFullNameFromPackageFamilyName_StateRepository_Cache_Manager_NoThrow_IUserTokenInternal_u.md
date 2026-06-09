# TryGetInstalledPackageFullNameFromPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,IUserTokenInternal *,ushort const *,uint,HSTRING__ * *,PackageFamilyErrorDetails *)

- ea: `0x180099eb4`
- end: `0x18009a516`
- name: `?TryGetInstalledPackageFullNameFromPackageFamilyName@@YAJAEAVManager_NoThrow@Cache@StateRepository@@PEAUIUserTokenInternal@@PEBGIPEAPEAUHSTRING__@@PEAW4PackageFamilyErrorDetails@@@Z`
- size: `1634`
- prototype: `int(struct StateRepository::Cache::Manager_NoThrow *, struct IUserTokenInternal *, const unsigned __int16 *, unsigned int, HSTRING *, enum PackageFamilyErrorDetails *)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800cdda8`
- `0x1800cea3c`

## callees

- `0x180020598`
- `0x18002ba28`
- `0x1800728d4`
- `0x18008e98c`
- `0x180098b54`
- `0x180099eb4`
- `0x18009d39c`
- `0x1800a7500`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800cd2f0`
- `0x1800cd5c0`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009a248`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009a2cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009a248`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009a2cb`
- `KERNELBASE!FindPackagesByPackageFamily` at `0x180099feb`
- `KERNELBASE!FindPackagesByPackageFamily` at `0x180099feb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a14e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a27a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a2a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a14e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a27a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a2a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18009a053`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18009a053`

## string_xrefs

- `0x180099f3a`: `onecore\com\combase\catalog\services.cxx`
- `0x180099f6c`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a028`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a08f`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a127`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a1bc`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a2de`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a31a`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a355`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a3a8`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a42b`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a467`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a49e`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a4cf`: `onecore\com\combase\catalog\services.cxx`
- `0x18009a06f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18009a36d`: `Family %ls has %d installed packages`

## pseudocode

```c
__int64 __fastcall TryGetInstalledPackageFullNameFromPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        struct IUserTokenInternal *a2,
        const unsigned __int16 *a3,
        UINT32 a4,
        HSTRING *string,
        enum PackageFamilyErrorDetails *a6)
{
  int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  unsigned int PackagesByPackageFamily; // eax
  __int64 v15; // rcx
  int v16; // eax
  HRESULT v17; // edi
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  HRESULT v31; // eax
  unsigned int v32; // esi
  int v33; // eax
  __int64 v34; // rdx
  int v35; // eax
  unsigned int v36; // eax
  int v37; // eax
  int v38; // eax
  int bufferLength; // [rsp+20h] [rbp-E0h]
  int bufferLengtha; // [rsp+20h] [rbp-E0h]
  int bufferLengthb; // [rsp+20h] [rbp-E0h]
  int bufferLengthc; // [rsp+20h] [rbp-E0h]
  int bufferLengthd; // [rsp+20h] [rbp-E0h]
  int bufferLengthe; // [rsp+20h] [rbp-E0h]
  UINT32 *packageProperties; // [rsp+30h] [rbp-D0h]
  _BYTE v46[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v47; // [rsp+44h] [rbp-BCh] BYREF
  UINT32 count; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  int v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  UINT32 v52; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  PWSTR packageFullNames; // [rsp+78h] [rbp-88h] BYREF
  PCNZWCH sourceString[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v56; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  __int64 v60; // [rsp+B0h] [rbp-50h]
  __int64 v61; // [rsp+B8h] [rbp-48h]
  __int128 v62; // [rsp+C0h] [rbp-40h]
  int v63; // [rsp+D0h] [rbp-30h]
  __int64 v64; // [rsp+D8h] [rbp-28h]
  __int64 v65; // [rsp+E0h] [rbp-20h]
  struct StateRepository::Cache::Manager_NoThrow *v66; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v67; // [rsp+F8h] [rbp-8h] BYREF
  char v68; // [rsp+100h] [rbp+0h]
  WCHAR buffer[128]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  if ( (a4 & 0xFFFBFFEF) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  *string = 0;
  v47 = 0;
  if ( a2 )
  {
    v10 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 96LL))(
            a2,
            0,
            &v47);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B3,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v10,
        bufferLength);
      v12 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v47);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8A8,
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (const char *)(unsigned int)v12,
          bufferLengtha);
      if ( a6 )
        *(_DWORD *)a6 = 0;
      return v11;
    }
  }
  packageFullNames = 0;
  count = 1;
  memset_0(buffer, 0, sizeof(buffer));
  v52 = 128;
  PackagesByPackageFamily = FindPackagesByPackageFamily(a3, a4, &count, &packageFullNames, &v52, buffer, 0);
  if ( PackagesByPackageFamily )
  {
    if ( PackagesByPackageFamily != 122 )
    {
      if ( PackagesByPackageFamily == 15701 )
      {
        v36 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)0x8EC,
                (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
                (const char *)0x490,
                (unsigned int)"State for package family %ls is corrupt",
                (const char *)a3);
      }
      else
      {
        if ( PackagesByPackageFamily == 87 )
        {
          v32 = wil::details::in1diag3::Return_Win32Msg(
                  retaddr,
                  (void *)0x8F7,
                  (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
                  (const char *)0x490,
                  (unsigned int)"Family=%ls",
                  (const char *)a3);
          if ( a2 )
          {
            v37 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v47);
            if ( v37 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x8A8,
                (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
                (const char *)(unsigned int)v37,
                bufferLengthe);
          }
          if ( a6 )
            *(_DWORD *)a6 = 4;
          return v32;
        }
        v36 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)0x8FB,
                (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
                (const char *)PackagesByPackageFamily,
                (unsigned int)"Family=%ls",
                (const char *)a3);
      }
      v32 = v36;
      goto LABEL_80;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v15);
    v34 = 2279;
LABEL_63:
    LODWORD(packageProperties) = count;
    v32 = wil::details::in1diag3::Return_Win32Msg(
            retaddr,
            (void *)v34,
            (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
            (const char *)0x490,
            (unsigned int)"Family %ls has %d installed packages",
            (const char *)a3,
            packageProperties);
    if ( a2 )
    {
      v35 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v47);
      if ( v35 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8A8,
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (const char *)(unsigned int)v35,
          bufferLengthd);
    }
    if ( a6 )
      *(_DWORD *)a6 = 3;
    return v32;
  }
  if ( count )
  {
    if ( count == 1 )
    {
      v30 = -1;
      do
        ++v30;
      while ( packageFullNames[v30] );
      v31 = WindowsCreateString(packageFullNames, v30, string);
      v32 = v31;
      if ( v31 >= 0 )
      {
        if ( a2 )
        {
          v33 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v47);
          if ( v33 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8A8,
              (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
              (const char *)(unsigned int)v33,
              bufferLengthb);
        }
        goto LABEL_59;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8CF,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v31,
        bufferLengthb);
LABEL_80:
      if ( a2 )
      {
        v38 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v47);
        if ( v38 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8A8,
            (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
            (const char *)(unsigned int)v38,
            bufferLengthc);
      }
      if ( a6 )
        *(_DWORD *)a6 = 0;
      return v32;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v15);
    v34 = 2269;
    goto LABEL_63;
  }
  if ( a2 )
  {
    v16 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v47);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8A8,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v16,
        bufferLengthb);
  }
  if ( *(_QWORD *)a1
    || (v66 = a1,
        v67 = 0,
        v68 = 1,
        v17 = SRCacheManager_Open(0, &v67),
        wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v66),
        v17 >= 0) )
  {
    v53 = 0;
    v17 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(a1, a3, &v53);
    if ( v17 < 0 )
    {
      v18 = 2309;
      goto LABEL_18;
    }
    if ( !v53 )
    {
LABEL_25:
      if ( a6 )
        *(_DWORD *)a6 = 2;
      return 0;
    }
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v19 = StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(
            a1,
            v53,
            (struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v49);
    v17 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90D,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v19,
        bufferLengthb);
LABEL_29:
      v22 = v49;
      v49 = 0;
      if ( v22 )
        SRCacheContext_Close(v22, v21);
      goto LABEL_19;
    }
    v56 = 0;
    *(_OWORD *)sourceString = 0;
    v62 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v46[0] = 0;
    v17 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v49, v20, sourceString, v46);
    if ( v17 < 0 )
    {
      v24 = 2327;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v17,
        bufferLengthb);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
      goto LABEL_29;
    }
    while ( 1 )
    {
      if ( !v46[0] )
      {
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
        v29 = v49;
        v49 = 0;
        if ( v29 )
          SRCacheContext_Close(v29, v28);
        goto LABEL_25;
      }
      if ( ((v57 & 0x100000000000LL) != 0 || (v58 & 0x100) != 0)
        && ((a4 & 0x10) != 0 && (_DWORD)v57 == 1 || (a4 & 0x40000) != 0 && (v57 & 0x8000000000LL) != 0) )
      {
        break;
      }
      ++v50;
      v17 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v49, v23, sourceString, v46);
      if ( v17 < 0 )
      {
        v24 = 2344;
        goto LABEL_33;
      }
    }
    v25 = -1;
    do
      ++v25;
    while ( sourceString[1][v25] );
    v17 = WindowsCreateString(sourceString[1], v25, string);
    if ( v17 < 0 )
    {
      v24 = 2339;
      goto LABEL_33;
    }
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
    v27 = v49;
    v49 = 0;
    if ( v27 )
      SRCacheContext_Close(v27, v26);
LABEL_59:
    if ( a6 )
      *(_DWORD *)a6 = 1;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA5,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
    (const char *)(unsigned int)v17,
    bufferLengthb);
  v18 = 2305;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
    (const char *)(unsigned int)v17,
    bufferLengthb);
LABEL_19:
  if ( a6 )
    *(_DWORD *)a6 = 2;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180099eb4  push    rbp
0x180099eb6  push    rsi
0x180099eb7  push    rdi
0x180099eb8  push    r12
0x180099eba  push    r13
0x180099ebc  push    r14
0x180099ebe  push    r15
0x180099ec0  lea     rbp, [rsp-120h]
0x180099ec8  sub     rsp, 220h
0x180099ecf  mov     rax, cs:__security_cookie
0x180099ed6  xor     rax, rsp
0x180099ed9  mov     [rbp+150h+var_40], rax
0x180099ee0  mov     r13, [rbp+150h+string]
0x180099ee7  mov     r12d, r9d
0x180099eea  mov     rsi, r8
0x180099eed  mov     rdi, rdx
0x180099ef0  mov     r15, rcx
0x180099ef3  test    r9d, 0FFFBFFEFh
0x180099efa  jz      short loc_180099F01
0x180099efc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180099f01  xor     r14d, r14d
0x180099f04  mov     [r13+0], r14
0x180099f08  mov     [rsp+250h+var_20C], r14d
0x180099f0d  test    rdi, rdi
0x180099f10  jz      loc_180099F9D
0x180099f16  mov     rax, [rdi]
0x180099f19  lea     r8, [rsp+250h+var_20C]
0x180099f1e  xor     edx, edx
0x180099f20  mov     rcx, rdi
0x180099f23  mov     rax, [rax+60h]
0x180099f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f2c  mov     r14d, eax
0x180099f2f  test    eax, eax
0x180099f31  jns     short loc_180099F9A
0x180099f33  mov     rcx, [rbp+158h]; this
0x180099f3a  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180099f41  mov     r9d, eax; char *
0x180099f44  mov     edx, 8B3h; void *
0x180099f49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099f4e  mov     rcx, [rdi]
0x180099f51  mov     edx, [rsp+250h+var_20C]
0x180099f55  mov     rax, [rcx+68h]
0x180099f59  mov     rcx, rdi
0x180099f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f61  test    eax, eax
0x180099f63  jns     short loc_180099F80
0x180099f65  mov     rcx, [rbp+158h]; this
0x180099f6c  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180099f73  mov     r9d, eax; char *
0x180099f76  mov     edx, 8A8h; void *
0x180099f7b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180099f80  mov     rax, [rbp+150h+arg_28]
0x180099f87  test    rax, rax
0x180099f8a  jz      short loc_180099F92
0x180099f8c  mov     dword ptr [rax], 0
0x180099f92  mov     eax, r14d
0x180099f95  jmp     loc_18009A4F4
0x180099f9a  xor     r14d, r14d
0x180099f9d  xor     edx, edx; Val
0x180099f9f  mov     [rsp+250h+packageFullNames], r14
0x180099fa4  mov     r8d, 100h; Size
0x180099faa  mov     [rsp+250h+count], 1
0x180099fb2  lea     rcx, [rbp+150h+var_140]; void *
0x180099fb6  call    memset_0
0x180099fbb  lea     rax, [rbp+150h+var_140]
0x180099fbf  mov     [rsp+250h+packageProperties], r14; packageProperties
0x180099fc4  mov     [rsp+250h+buffer], rax; buffer
0x180099fc9  lea     r9, [rsp+250h+packageFullNames]; packageFullNames
0x180099fce  lea     rax, [rsp+250h+var_1E8]
0x180099fd3  mov     [rsp+250h+var_1E8], 80h
0x180099fdb  lea     r8, [rsp+250h+count]; count
0x180099fe0  mov     [rsp+250h+bufferLength], rax; int
0x180099fe5  mov     edx, r12d; packageFilters
0x180099fe8  mov     rcx, rsi; packageFamilyName
0x180099feb  call    cs:__imp_FindPackagesByPackageFamily
0x180099ff1  test    eax, eax
0x180099ff3  jnz     loc_18009A3D7
0x180099ff9  mov     eax, [rsp+250h+count]
0x180099ffd  test    eax, eax
0x180099fff  jnz     loc_18009A2AC
0x18009a005  test    rdi, rdi
0x18009a008  jz      short loc_18009A03C
0x18009a00a  mov     rax, [rdi]
0x18009a00d  mov     rcx, rdi
0x18009a010  mov     edx, [rsp+250h+var_20C]
0x18009a014  mov     rax, [rax+68h]
0x18009a018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a01d  test    eax, eax
0x18009a01f  jns     short loc_18009A03C
0x18009a021  mov     rcx, [rbp+158h]; this
0x18009a028  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009a02f  mov     r9d, eax; char *
0x18009a032  mov     edx, 8A8h; void *
0x18009a037  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009a03c  cmp     [r15], r14
0x18009a03f  jnz     short loc_18009A0B7
0x18009a041  lea     rdx, [rbp+150h+var_158]
0x18009a045  mov     [rbp+150h+var_160], r15
0x18009a049  xor     ecx, ecx
0x18009a04b  mov     [rbp+150h+var_158], r14
0x18009a04f  mov     [rbp+150h+var_150], 1
0x18009a053  call    cs:__imp_SRCacheManager_Open
0x18009a059  lea     rcx, [rbp+150h+var_160]
0x18009a05d  mov     edi, eax
0x18009a05f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18009a064  test    edi, edi
0x18009a066  jns     short loc_18009A0B7
0x18009a068  mov     rcx, [rbp+158h]; this
0x18009a06f  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009a076  mov     r9d, edi; char *
0x18009a079  mov     edx, 0A5h; void *
0x18009a07e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a083  mov     edx, 901h; void *
0x18009a088  mov     rcx, [rbp+158h]; this
0x18009a08f  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009a096  mov     r9d, edi; char *
0x18009a099  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a09e  mov     rax, [rbp+150h+arg_28]
0x18009a0a5  test    rax, rax
0x18009a0a8  jz      short loc_18009A0B0
0x18009a0aa  mov     dword ptr [rax], 2
0x18009a0b0  mov     eax, edi
0x18009a0b2  jmp     loc_18009A4F4
0x18009a0b7  lea     r8, [rsp+250h+var_1E0]; __int64 *
0x18009a0bc  mov     [rsp+250h+var_1E0], r14
0x18009a0c1  mov     rdx, rsi; unsigned __int16 *
0x18009a0c4  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x18009a0c7  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18009a0cc  mov     edi, eax
0x18009a0ce  test    eax, eax
0x18009a0d0  jns     short loc_18009A0D9
0x18009a0d2  mov     edx, 905h
0x18009a0d7  jmp     short loc_18009A088
0x18009a0d9  mov     rdx, [rsp+250h+var_1E0]; __int64
0x18009a0de  test    rdx, rdx
0x18009a0e1  jnz     short loc_18009A0FE
0x18009a0e3  mov     rax, [rbp+150h+arg_28]
0x18009a0ea  test    rax, rax
0x18009a0ed  jz      loc_18009A340
0x18009a0f3  mov     dword ptr [rax], 2
0x18009a0f9  jmp     loc_18009A340
0x18009a0fe  lea     r8, [rsp+250h+var_200]; this
0x18009a103  mov     [rsp+250h+var_200], r14
0x18009a108  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x18009a10b  mov     [rsp+250h+var_1F8], r14d
0x18009a110  mov     [rsp+250h+var_1F0], r14
0x18009a115  call    ?FindByPackageFamily@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVPackageIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageIndexIterator_NoThrow &)
0x18009a11a  mov     edi, eax
0x18009a11c  test    eax, eax
0x18009a11e  jns     short loc_18009A159
0x18009a120  mov     rcx, [rbp+158h]; this
0x18009a127  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009a12e  mov     r9d, eax; char *
0x18009a131  mov     edx, 90Dh; void *
0x18009a136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a13b  mov     rcx, [rsp+250h+var_200]
0x18009a140  mov     [rsp+250h+var_200], r14
0x18009a145  test    rcx, rcx
0x18009a148  jz      loc_18009A09E
0x18009a14e  call    cs:__imp_SRCacheContext_Close
0x18009a154  jmp     loc_18009A09E
0x18009a159  xorps   xmm0, xmm0
0x18009a15c  mov     [rbp+150h+var_1C0], r14
0x18009a160  lea     r9, [rsp+250h+var_210]
0x18009a165  movdqa  xmmword ptr [rbp+150h+sourceString], xmm0
0x18009a16a  lea     r8, [rbp+150h+sourceString]
0x18009a16e  movdqa  [rbp+150h+var_190], xmm0
0x18009a173  lea     rcx, [rsp+250h+var_200]
0x18009a178  mov     [rbp+150h+var_1B8], 0
0x18009a180  mov     [rbp+150h+var_1B0], 0
0x18009a188  mov     [rbp+150h+var_1A8], r14
0x18009a18c  mov     [rbp+150h+var_1A0], r14
0x18009a190  mov     [rbp+150h+var_198], r14
0x18009a194  mov     [rbp+150h+var_180], r14d
0x18009a198  mov     [rbp+150h+var_178], r14
0x18009a19c  mov     [rbp+150h+var_170], r14
0x18009a1a0  mov     [rsp+250h+var_210], r14b
0x18009a1a5  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18009a1aa  mov     edi, eax
0x18009a1ac  test    eax, eax
0x18009a1ae  jns     short loc_18009A1D9
0x18009a1b0  mov     edx, 917h; void *
0x18009a1b5  mov     rcx, [rbp+158h]; this
0x18009a1bc  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009a1c3  mov     r9d, edi; char *
0x18009a1c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a1cb  lea     rcx, [rbp+150h+sourceString]; this
0x18009a1cf  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009a1d4  jmp     loc_18009A13B
0x18009a1d9  cmp     [rsp+250h+var_210], r14b
0x18009a1de  jz      loc_18009A285
0x18009a1e4  test    dword ptr [rbp+150h+var_1B8+4], 1000h
0x18009a1eb  jnz     short loc_18009A1F6
0x18009a1ed  test    dword ptr [rbp+150h+var_1B0], 100h
0x18009a1f4  jz      short loc_18009A20F
0x18009a1f6  test    r12b, 10h
0x18009a1fa  jz      short loc_18009A202
0x18009a1fc  cmp     dword ptr [rbp+150h+var_1B8], 1
0x18009a200  jz      short loc_18009A233
0x18009a202  bt      r12d, 12h
0x18009a207  jnb     short loc_18009A20F
0x18009a209  test    byte ptr [rbp+150h+var_1B8+4], 80h
0x18009a20d  jnz     short loc_18009A233
0x18009a20f  inc     [rsp+250h+var_1F8]
0x18009a213  lea     r9, [rsp+250h+var_210]
0x18009a218  lea     r8, [rbp+150h+sourceString]
0x18009a21c  lea     rcx, [rsp+250h+var_200]
0x18009a221  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18009a226  mov     edi, eax
0x18009a228  test    eax, eax
0x18009a22a  jns     short loc_18009A1D9
0x18009a22c  mov     edx, 928h
0x18009a231  jmp     short loc_18009A1B5
0x18009a233  mov     rcx, [rbp+150h+sourceString+8]; sourceString
0x18009a237  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009a23b  inc     rdx; length
0x18009a23e  cmp     [rcx+rdx*2], r14w
0x18009a243  jnz     short loc_18009A23B
0x18009a245  mov     r8, r13; string
0x18009a248  call    cs:__imp_WindowsCreateString
0x18009a24e  mov     edi, eax
0x18009a250  test    eax, eax
0x18009a252  jns     short loc_18009A25E
0x18009a254  mov     edx, 923h
0x18009a259  jmp     loc_18009A1B5
0x18009a25e  lea     rcx, [rbp+150h+sourceString]; this
0x18009a262  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009a267  mov     rcx, [rsp+250h+var_200]
0x18009a26c  mov     [rsp+250h+var_200], r14
0x18009a271  test    rcx, rcx
0x18009a274  jz      loc_18009A32E
0x18009a27a  call    cs:__imp_SRCacheContext_Close
0x18009a280  jmp     loc_18009A32E
0x18009a285  lea     rcx, [rbp+150h+sourceString]; this
0x18009a289  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009a28e  mov     rcx, [rsp+250h+var_200]
0x18009a293  mov     [rsp+250h+var_200], r14
0x18009a298  test    rcx, rcx
0x18009a29b  jz      loc_18009A0E3
0x18009a2a1  call    cs:__imp_SRCacheContext_Close
0x18009a2a7  jmp     loc_18009A0E3
0x18009a2ac  cmp     eax, 1
0x18009a2af  jnz     loc_18009A347
0x18009a2b5  mov     rcx, [rsp+250h+packageFullNames]; sourceString
0x18009a2ba  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009a2be  inc     rdx; length
0x18009a2c1  cmp     [rcx+rdx*2], r14w
0x18009a2c6  jnz     short loc_18009A2BE
0x18009a2c8  mov     r8, r13; string
0x18009a2cb  call    cs:__imp_WindowsCreateString
0x18009a2d1  mov     esi, eax
0x18009a2d3  test    eax, eax
0x18009a2d5  jns     short loc_18009A2F7
0x18009a2d7  mov     rcx, [rbp+158h]; this
0x18009a2de  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009a2e5  mov     r9d, eax; char *
0x18009a2e8  mov     edx, 8CFh; void *
0x18009a2ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a2f2  jmp     loc_18009A4AC
0x18009a2f7  test    rdi, rdi
0x18009a2fa  jz      short loc_18009A32E
0x18009a2fc  mov     rax, [rdi]
0x18009a2ff  mov     rcx, rdi
0x18009a302  mov     edx, [rsp+250h+var_20C]
0x18009a306  mov     rax, [rax+68h]
0x18009a30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a30f  test    eax, eax
0x18009a311  jns     short loc_18009A32E
0x18009a313  mov     rcx, [rbp+158h]; this
0x18009a31a  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009a321  mov     r9d, eax; char *
0x18009a324  mov     edx, 8A8h; void *
0x18009a329  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009a32e  mov     rax, [rbp+150h+arg_28]
0x18009a335  test    rax, rax
0x18009a338  jz      short loc_18009A340
0x18009a33a  mov     dword ptr [rax], 1
0x18009a340  xor     eax, eax
0x18009a342  jmp     loc_18009A4F4
0x18009a347  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a34c  mov     edx, 8DDh; void *
0x18009a351  mov     eax, [rsp+250h+count]
0x18009a355  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009a35c  mov     rcx, [rbp+158h]; this
0x18009a363  mov     r9d, 490h; char *
0x18009a369  mov     dword ptr [rsp+250h+packageProperties], eax
0x18009a36d  lea     rax, aFamilyLsHasDIn; "Family %ls has %d installed packages"
0x18009a374  mov     [rsp+250h+buffer], rsi; char *
0x18009a379  mov     [rsp+250h+bufferLength], rax; int
0x18009a37e  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18009a383  mov     esi, eax
0x18009a385  test    rdi, rdi
0x18009a388  jz      short loc_18009A3BC
0x18009a38a  mov     rcx, [rdi]
0x18009a38d  mov     edx, [rsp+250h+var_20C]
0x18009a391  mov     rax, [rcx+68h]
0x18009a395  mov     rcx, rdi
0x18009a398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a39d  test    eax, eax
0x18009a39f  jns     short loc_18009A3BC
  ... truncated ...
```
