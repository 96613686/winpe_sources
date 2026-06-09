# TryGetInstalledPackageFullNameFromPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,IUserTokenInternal *,ushort const *,uint,HSTRING__ * *,PackageFamilyErrorDetails *)

- ea: `0x18009f504`
- end: `0x18009fb58`
- name: `?TryGetInstalledPackageFullNameFromPackageFamilyName@@YAJAEAVManager_NoThrow@Cache@StateRepository@@PEAUIUserTokenInternal@@PEBGIPEAPEAUHSTRING__@@PEAW4PackageFamilyErrorDetails@@@Z`
- size: `1620`
- prototype: `int(struct StateRepository::Cache::Manager_NoThrow *, struct IUserTokenInternal *, const unsigned __int16 *, unsigned int, HSTRING *, enum PackageFamilyErrorDetails *)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800d4040`
- `0x1800d5194`

## callees

- `0x18000e0a0`
- `0x18000eccc`
- `0x1800210f8`
- `0x180076ef8`
- `0x180095c0c`
- `0x18009e160`
- `0x18009f504`
- `0x1800a2aec`
- `0x1800ac5a0`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800d3588`
- `0x1800d380c`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009f897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009f906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009f897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009f906`
- `KERNELBASE!FindPackagesByPackageFamily` at `0x18009f63b`
- `KERNELBASE!FindPackagesByPackageFamily` at `0x18009f63b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18009f6a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18009f6a9`

## string_xrefs

- `0x18009f6cb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18009f58a`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f5bc`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f67e`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f6eb`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f783`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f80b`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f91f`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f95b`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f996`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f9e9`: `onecore\com\combase\catalog\services.cxx`
- `0x18009fa6c`: `onecore\com\combase\catalog\services.cxx`
- `0x18009faa8`: `onecore\com\combase\catalog\services.cxx`
- `0x18009fadf`: `onecore\com\combase\catalog\services.cxx`
- `0x18009fb10`: `onecore\com\combase\catalog\services.cxx`
- `0x18009f9ae`: `Family %ls has %d installed packages`

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
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  HRESULT v25; // eax
  unsigned int v26; // esi
  int v27; // eax
  __int64 v28; // rdx
  int v29; // eax
  unsigned int v30; // eax
  int v31; // eax
  int v32; // eax
  int bufferLength; // [rsp+20h] [rbp-E0h]
  int bufferLengtha; // [rsp+20h] [rbp-E0h]
  int bufferLengthb; // [rsp+20h] [rbp-E0h]
  int bufferLengthc; // [rsp+20h] [rbp-E0h]
  int bufferLengthd; // [rsp+20h] [rbp-E0h]
  int bufferLengthe; // [rsp+20h] [rbp-E0h]
  UINT32 *packageProperties; // [rsp+30h] [rbp-D0h]
  _BYTE v40[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v41; // [rsp+44h] [rbp-BCh] BYREF
  UINT32 count; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+58h] [rbp-A8h]
  __int64 v45; // [rsp+60h] [rbp-A0h]
  UINT32 v46; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  PWSTR packageFullNames; // [rsp+78h] [rbp-88h] BYREF
  PCNZWCH sourceString[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+90h] [rbp-70h]
  __int64 v51; // [rsp+98h] [rbp-68h]
  __int64 v52; // [rsp+A0h] [rbp-60h]
  __int64 v53; // [rsp+A8h] [rbp-58h]
  __int64 v54; // [rsp+B0h] [rbp-50h]
  __int64 v55; // [rsp+B8h] [rbp-48h]
  __int128 v56; // [rsp+C0h] [rbp-40h]
  int v57; // [rsp+D0h] [rbp-30h]
  __int64 v58; // [rsp+D8h] [rbp-28h]
  __int64 v59; // [rsp+E0h] [rbp-20h]
  struct StateRepository::Cache::Manager_NoThrow *v60; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v61; // [rsp+F8h] [rbp-8h] BYREF
  char v62; // [rsp+100h] [rbp+0h]
  WCHAR buffer[128]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  if ( (a4 & 0xFFFBFFEF) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  *string = 0;
  v41 = 0;
  if ( a2 )
  {
    v10 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 96LL))(
            a2,
            0,
            &v41);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B3,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v10,
        bufferLength);
      v12 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v41);
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
  v46 = 128;
  PackagesByPackageFamily = FindPackagesByPackageFamily(a3, a4, &count, &packageFullNames, &v46, buffer, 0);
  if ( PackagesByPackageFamily )
  {
    if ( PackagesByPackageFamily != 122 )
    {
      if ( PackagesByPackageFamily == 15701 )
      {
        v30 = wil::details::in1diag3::Return_Win32Msg(
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
          v26 = wil::details::in1diag3::Return_Win32Msg(
                  retaddr,
                  (void *)0x8F7,
                  (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
                  (const char *)0x490,
                  (unsigned int)"Family=%ls",
                  (const char *)a3);
          if ( a2 )
          {
            v31 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v41);
            if ( v31 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x8A8,
                (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
                (const char *)(unsigned int)v31,
                bufferLengthe);
          }
          if ( a6 )
            *(_DWORD *)a6 = 4;
          return v26;
        }
        v30 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)0x8FB,
                (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
                (const char *)PackagesByPackageFamily,
                (unsigned int)"Family=%ls",
                (const char *)a3);
      }
      v26 = v30;
      goto LABEL_77;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v15);
    v28 = 2279;
LABEL_60:
    LODWORD(packageProperties) = count;
    v26 = wil::details::in1diag3::Return_Win32Msg(
            retaddr,
            (void *)v28,
            (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
            (const char *)0x490,
            (unsigned int)"Family %ls has %d installed packages",
            (const char *)a3,
            packageProperties);
    if ( a2 )
    {
      v29 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v41);
      if ( v29 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8A8,
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (const char *)(unsigned int)v29,
          bufferLengthd);
    }
    if ( a6 )
      *(_DWORD *)a6 = 3;
    return v26;
  }
  if ( count )
  {
    if ( count == 1 )
    {
      v24 = -1;
      do
        ++v24;
      while ( packageFullNames[v24] );
      v25 = WindowsCreateString(packageFullNames, v24, string);
      v26 = v25;
      if ( v25 >= 0 )
      {
        if ( a2 )
        {
          v27 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v41);
          if ( v27 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8A8,
              (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
              (const char *)(unsigned int)v27,
              bufferLengthb);
        }
        goto LABEL_56;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8CF,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v25,
        bufferLengthb);
LABEL_77:
      if ( a2 )
      {
        v32 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v41);
        if ( v32 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8A8,
            (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
            (const char *)(unsigned int)v32,
            bufferLengthc);
      }
      if ( a6 )
        *(_DWORD *)a6 = 0;
      return v26;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v15);
    v28 = 2269;
    goto LABEL_60;
  }
  if ( a2 )
  {
    v16 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v41);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8A8,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v16,
        bufferLengthb);
  }
  if ( *(_QWORD *)a1
    || (v60 = a1,
        v61 = 0,
        v62 = 1,
        v17 = SRCacheManager_Open(0, &v61),
        wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v60),
        v17 >= 0) )
  {
    v47 = 0;
    v17 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(a1, a3, &v47);
    if ( v17 < 0 )
    {
      v18 = 2309;
      goto LABEL_18;
    }
    if ( !v47 )
    {
LABEL_25:
      if ( a6 )
        *(_DWORD *)a6 = 2;
      return 0;
    }
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v19 = StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(
            a1,
            v47,
            (struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v43);
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
      wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v43, 0);
      goto LABEL_19;
    }
    v50 = 0;
    *(_OWORD *)sourceString = 0;
    v56 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v40[0] = 0;
    v17 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v43, v20, sourceString, v40);
    if ( v17 < 0 )
    {
      v22 = 2327;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v17,
        bufferLengthb);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
      goto LABEL_29;
    }
    while ( 1 )
    {
      if ( !v40[0] )
      {
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
        wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v43, 0);
        goto LABEL_25;
      }
      if ( ((v51 & 0x100000000000LL) != 0 || (v52 & 0x100) != 0)
        && ((a4 & 0x10) != 0 && (_DWORD)v51 == 1 || (a4 & 0x40000) != 0 && (v51 & 0x8000000000LL) != 0) )
      {
        break;
      }
      ++v44;
      v17 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v43, v21, sourceString, v40);
      if ( v17 < 0 )
      {
        v22 = 2344;
        goto LABEL_32;
      }
    }
    v23 = -1;
    do
      ++v23;
    while ( sourceString[1][v23] );
    v17 = WindowsCreateString(sourceString[1], v23, string);
    if ( v17 < 0 )
    {
      v22 = 2339;
      goto LABEL_32;
    }
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v43, 0);
LABEL_56:
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
0x18009f504  push    rbp
0x18009f506  push    rsi
0x18009f507  push    rdi
0x18009f508  push    r12
0x18009f50a  push    r13
0x18009f50c  push    r14
0x18009f50e  push    r15
0x18009f510  lea     rbp, [rsp-120h]
0x18009f518  sub     rsp, 220h
0x18009f51f  mov     rax, cs:__security_cookie
0x18009f526  xor     rax, rsp
0x18009f529  mov     [rbp+150h+var_40], rax
0x18009f530  mov     r13, [rbp+150h+string]
0x18009f537  mov     r12d, r9d
0x18009f53a  mov     rsi, r8
0x18009f53d  mov     rdi, rdx
0x18009f540  mov     r15, rcx
0x18009f543  test    r9d, 0FFFBFFEFh
0x18009f54a  jz      short loc_18009F551
0x18009f54c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009f551  xor     r14d, r14d
0x18009f554  mov     [r13+0], r14
0x18009f558  mov     [rsp+250h+var_20C], r14d
0x18009f55d  test    rdi, rdi
0x18009f560  jz      loc_18009F5ED
0x18009f566  mov     rax, [rdi]
0x18009f569  lea     r8, [rsp+250h+var_20C]
0x18009f56e  xor     edx, edx
0x18009f570  mov     rcx, rdi
0x18009f573  mov     rax, [rax+60h]
0x18009f577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f57c  mov     r14d, eax
0x18009f57f  test    eax, eax
0x18009f581  jns     short loc_18009F5EA
0x18009f583  mov     rcx, [rbp+158h]; this
0x18009f58a  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009f591  mov     r9d, eax; char *
0x18009f594  mov     edx, 8B3h; void *
0x18009f599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f59e  mov     rcx, [rdi]
0x18009f5a1  mov     edx, [rsp+250h+var_20C]
0x18009f5a5  mov     rax, [rcx+68h]
0x18009f5a9  mov     rcx, rdi
0x18009f5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f5b1  test    eax, eax
0x18009f5b3  jns     short loc_18009F5D0
0x18009f5b5  mov     rcx, [rbp+158h]; this
0x18009f5bc  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009f5c3  mov     r9d, eax; char *
0x18009f5c6  mov     edx, 8A8h; void *
0x18009f5cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009f5d0  mov     rax, [rbp+150h+arg_28]
0x18009f5d7  test    rax, rax
0x18009f5da  jz      short loc_18009F5E2
0x18009f5dc  mov     dword ptr [rax], 0
0x18009f5e2  mov     eax, r14d
0x18009f5e5  jmp     loc_18009FB35
0x18009f5ea  xor     r14d, r14d
0x18009f5ed  xor     edx, edx; Val
0x18009f5ef  mov     [rsp+250h+packageFullNames], r14
0x18009f5f4  mov     r8d, 100h; Size
0x18009f5fa  mov     [rsp+250h+count], 1
0x18009f602  lea     rcx, [rbp+150h+var_140]; void *
0x18009f606  call    memset_0
0x18009f60b  lea     rax, [rbp+150h+var_140]
0x18009f60f  mov     [rsp+250h+packageProperties], r14; packageProperties
0x18009f614  mov     [rsp+250h+buffer], rax; buffer
0x18009f619  lea     r9, [rsp+250h+packageFullNames]; packageFullNames
0x18009f61e  lea     rax, [rsp+250h+var_1E8]
0x18009f623  mov     [rsp+250h+var_1E8], 80h
0x18009f62b  lea     r8, [rsp+250h+count]; count
0x18009f630  mov     [rsp+250h+bufferLength], rax; int
0x18009f635  mov     edx, r12d; packageFilters
0x18009f638  mov     rcx, rsi; packageFamilyName
0x18009f63b  call    cs:__imp_FindPackagesByPackageFamily
0x18009f642  nop     dword ptr [rax+rax+00h]
0x18009f647  test    eax, eax
0x18009f649  jnz     loc_18009FA18
0x18009f64f  mov     eax, [rsp+250h+count]
0x18009f653  test    eax, eax
0x18009f655  jnz     loc_18009F8E7
0x18009f65b  test    rdi, rdi
0x18009f65e  jz      short loc_18009F692
0x18009f660  mov     rax, [rdi]
0x18009f663  mov     rcx, rdi
0x18009f666  mov     edx, [rsp+250h+var_20C]
0x18009f66a  mov     rax, [rax+68h]
0x18009f66e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f673  test    eax, eax
0x18009f675  jns     short loc_18009F692
0x18009f677  mov     rcx, [rbp+158h]; this
0x18009f67e  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009f685  mov     r9d, eax; char *
0x18009f688  mov     edx, 8A8h; void *
0x18009f68d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009f692  cmp     [r15], r14
0x18009f695  jnz     short loc_18009F713
0x18009f697  lea     rdx, [rbp+150h+var_158]
0x18009f69b  mov     [rbp+150h+var_160], r15
0x18009f69f  xor     ecx, ecx
0x18009f6a1  mov     [rbp+150h+var_158], r14
0x18009f6a5  mov     [rbp+150h+var_150], 1
0x18009f6a9  call    cs:__imp_SRCacheManager_Open
0x18009f6b0  nop     dword ptr [rax+rax+00h]
0x18009f6b5  lea     rcx, [rbp+150h+var_160]
0x18009f6b9  mov     edi, eax
0x18009f6bb  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18009f6c0  test    edi, edi
0x18009f6c2  jns     short loc_18009F713
0x18009f6c4  mov     rcx, [rbp+158h]; this
0x18009f6cb  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009f6d2  mov     r9d, edi; char *
0x18009f6d5  mov     edx, 0A5h; void *
0x18009f6da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f6df  mov     edx, 901h; void *
0x18009f6e4  mov     rcx, [rbp+158h]; this
0x18009f6eb  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009f6f2  mov     r9d, edi; char *
0x18009f6f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f6fa  mov     rax, [rbp+150h+arg_28]
0x18009f701  test    rax, rax
0x18009f704  jz      short loc_18009F70C
0x18009f706  mov     dword ptr [rax], 2
0x18009f70c  mov     eax, edi
0x18009f70e  jmp     loc_18009FB35
0x18009f713  lea     r8, [rsp+250h+var_1E0]; __int64 *
0x18009f718  mov     [rsp+250h+var_1E0], r14
0x18009f71d  mov     rdx, rsi; unsigned __int16 *
0x18009f720  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x18009f723  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18009f728  mov     edi, eax
0x18009f72a  test    eax, eax
0x18009f72c  jns     short loc_18009F735
0x18009f72e  mov     edx, 905h
0x18009f733  jmp     short loc_18009F6E4
0x18009f735  mov     rdx, [rsp+250h+var_1E0]; __int64
0x18009f73a  test    rdx, rdx
0x18009f73d  jnz     short loc_18009F75A
0x18009f73f  mov     rax, [rbp+150h+arg_28]
0x18009f746  test    rax, rax
0x18009f749  jz      loc_18009F981
0x18009f74f  mov     dword ptr [rax], 2
0x18009f755  jmp     loc_18009F981
0x18009f75a  lea     r8, [rsp+250h+var_200]; struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *
0x18009f75f  mov     [rsp+250h+var_200], r14
0x18009f764  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x18009f767  mov     [rsp+250h+var_1F8], r14d
0x18009f76c  mov     [rsp+250h+var_1F0], r14
0x18009f771  call    ?FindByPackageFamily@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVPackageIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageIndexIterator_NoThrow &)
0x18009f776  mov     edi, eax
0x18009f778  test    eax, eax
0x18009f77a  jns     short loc_18009F7A8
0x18009f77c  mov     rcx, [rbp+158h]; this
0x18009f783  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009f78a  mov     r9d, eax; char *
0x18009f78d  mov     edx, 90Dh; void *
0x18009f792  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f797  xor     edx, edx
0x18009f799  lea     rcx, [rsp+250h+var_200]
0x18009f79e  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18009f7a3  jmp     loc_18009F6FA
0x18009f7a8  xorps   xmm0, xmm0
0x18009f7ab  mov     [rbp+150h+var_1C0], r14
0x18009f7af  lea     r9, [rsp+250h+var_210]
0x18009f7b4  movdqa  xmmword ptr [rbp+150h+sourceString], xmm0
0x18009f7b9  lea     r8, [rbp+150h+sourceString]
0x18009f7bd  movdqa  [rbp+150h+var_190], xmm0
0x18009f7c2  lea     rcx, [rsp+250h+var_200]
0x18009f7c7  mov     [rbp+150h+var_1B8], 0
0x18009f7cf  mov     [rbp+150h+var_1B0], 0
0x18009f7d7  mov     [rbp+150h+var_1A8], r14
0x18009f7db  mov     [rbp+150h+var_1A0], r14
0x18009f7df  mov     [rbp+150h+var_198], r14
0x18009f7e3  mov     [rbp+150h+var_180], r14d
0x18009f7e7  mov     [rbp+150h+var_178], r14
0x18009f7eb  mov     [rbp+150h+var_170], r14
0x18009f7ef  mov     [rsp+250h+var_210], r14b
0x18009f7f4  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18009f7f9  mov     edi, eax
0x18009f7fb  test    eax, eax
0x18009f7fd  jns     short loc_18009F828
0x18009f7ff  mov     edx, 917h; void *
0x18009f804  mov     rcx, [rbp+158h]; this
0x18009f80b  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009f812  mov     r9d, edi; char *
0x18009f815  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f81a  lea     rcx, [rbp+150h+sourceString]; this
0x18009f81e  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009f823  jmp     loc_18009F797
0x18009f828  cmp     [rsp+250h+var_210], r14b
0x18009f82d  jz      loc_18009F8CD
0x18009f833  test    dword ptr [rbp+150h+var_1B8+4], 1000h
0x18009f83a  jnz     short loc_18009F845
0x18009f83c  test    dword ptr [rbp+150h+var_1B0], 100h
0x18009f843  jz      short loc_18009F85E
0x18009f845  test    r12b, 10h
0x18009f849  jz      short loc_18009F851
0x18009f84b  cmp     dword ptr [rbp+150h+var_1B8], 1
0x18009f84f  jz      short loc_18009F882
0x18009f851  bt      r12d, 12h
0x18009f856  jnb     short loc_18009F85E
0x18009f858  test    byte ptr [rbp+150h+var_1B8+4], 80h
0x18009f85c  jnz     short loc_18009F882
0x18009f85e  inc     [rsp+250h+var_1F8]
0x18009f862  lea     r9, [rsp+250h+var_210]
0x18009f867  lea     r8, [rbp+150h+sourceString]
0x18009f86b  lea     rcx, [rsp+250h+var_200]
0x18009f870  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18009f875  mov     edi, eax
0x18009f877  test    eax, eax
0x18009f879  jns     short loc_18009F828
0x18009f87b  mov     edx, 928h
0x18009f880  jmp     short loc_18009F804
0x18009f882  mov     rcx, [rbp+150h+sourceString+8]; sourceString
0x18009f886  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009f88a  inc     rdx; length
0x18009f88d  cmp     [rcx+rdx*2], r14w
0x18009f892  jnz     short loc_18009F88A
0x18009f894  mov     r8, r13; string
0x18009f897  call    cs:__imp_WindowsCreateString
0x18009f89e  nop     dword ptr [rax+rax+00h]
0x18009f8a3  mov     edi, eax
0x18009f8a5  test    eax, eax
0x18009f8a7  jns     short loc_18009F8B3
0x18009f8a9  mov     edx, 923h
0x18009f8ae  jmp     loc_18009F804
0x18009f8b3  lea     rcx, [rbp+150h+sourceString]; this
0x18009f8b7  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009f8bc  xor     edx, edx
0x18009f8be  lea     rcx, [rsp+250h+var_200]
0x18009f8c3  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18009f8c8  jmp     loc_18009F96F
0x18009f8cd  lea     rcx, [rbp+150h+sourceString]; this
0x18009f8d1  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009f8d6  xor     edx, edx
0x18009f8d8  lea     rcx, [rsp+250h+var_200]
0x18009f8dd  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18009f8e2  jmp     loc_18009F73F
0x18009f8e7  cmp     eax, 1
0x18009f8ea  jnz     loc_18009F988
0x18009f8f0  mov     rcx, [rsp+250h+packageFullNames]; sourceString
0x18009f8f5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009f8f9  inc     rdx; length
0x18009f8fc  cmp     [rcx+rdx*2], r14w
0x18009f901  jnz     short loc_18009F8F9
0x18009f903  mov     r8, r13; string
0x18009f906  call    cs:__imp_WindowsCreateString
0x18009f90d  nop     dword ptr [rax+rax+00h]
0x18009f912  mov     esi, eax
0x18009f914  test    eax, eax
0x18009f916  jns     short loc_18009F938
0x18009f918  mov     rcx, [rbp+158h]; this
0x18009f91f  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009f926  mov     r9d, eax; char *
0x18009f929  mov     edx, 8CFh; void *
0x18009f92e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f933  jmp     loc_18009FAED
0x18009f938  test    rdi, rdi
0x18009f93b  jz      short loc_18009F96F
0x18009f93d  mov     rax, [rdi]
0x18009f940  mov     rcx, rdi
0x18009f943  mov     edx, [rsp+250h+var_20C]
0x18009f947  mov     rax, [rax+68h]
0x18009f94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f950  test    eax, eax
0x18009f952  jns     short loc_18009F96F
0x18009f954  mov     rcx, [rbp+158h]; this
0x18009f95b  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009f962  mov     r9d, eax; char *
0x18009f965  mov     edx, 8A8h; void *
0x18009f96a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009f96f  mov     rax, [rbp+150h+arg_28]
0x18009f976  test    rax, rax
0x18009f979  jz      short loc_18009F981
0x18009f97b  mov     dword ptr [rax], 1
0x18009f981  xor     eax, eax
0x18009f983  jmp     loc_18009FB35
0x18009f988  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009f98d  mov     edx, 8DDh; void *
0x18009f992  mov     eax, [rsp+250h+count]
0x18009f996  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18009f99d  mov     rcx, [rbp+158h]; this
0x18009f9a4  mov     r9d, 490h; char *
0x18009f9aa  mov     dword ptr [rsp+250h+packageProperties], eax
0x18009f9ae  lea     rax, aFamilyLsHasDIn; "Family %ls has %d installed packages"
0x18009f9b5  mov     [rsp+250h+buffer], rsi; char *
0x18009f9ba  mov     [rsp+250h+bufferLength], rax; int
0x18009f9bf  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18009f9c4  mov     esi, eax
0x18009f9c6  test    rdi, rdi
0x18009f9c9  jz      short loc_18009F9FD
0x18009f9cb  mov     rcx, [rdi]
0x18009f9ce  mov     edx, [rsp+250h+var_20C]
0x18009f9d2  mov     rax, [rcx+68h]
0x18009f9d6  mov     rcx, rdi
0x18009f9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f9de  test    eax, eax
0x18009f9e0  jns     short loc_18009F9FD
0x18009f9e2  mov     rcx, [rbp+158h]; this
0x18009f9e9  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
  ... truncated ...
```
