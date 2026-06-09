# CPackagedComCatalog::GetProcessInfo(ulong,IUserTokenInternal *,_GUID const &,ushort const *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const,_GUID const &,void * *)

- ea: `0x1800e5f00`
- end: `0x1800e620a`
- name: `?GetProcessInfo@CPackagedComCatalog@@UEAAJKPEAUIUserTokenInternal@@AEBU_GUID@@PEBG2IQEBQEAUHSTRING__@@I31PEAPEAX@Z`
- size: `778`
- prototype: `__int64 __fastcall(CPackagedComCatalog *__hidden this, unsigned int, struct IUserTokenInternal *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, HSTRING *const, unsigned int, HSTRING *const, const struct _GUID *, HSTRING newString)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003194`
- `0x18000fb8c`
- `0x180016948`
- `0x1800210f8`
- `0x1800581c0`
- `0x180095c0c`
- `0x1800989a0`
- `0x1800d43cc`
- `0x1800e5f00`
- `0x1800e64cc`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5fff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5fff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6168`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800e5f93`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800e5f93`

## string_xrefs

- `0x1800e5f5b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e5fa9`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e5fec`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e6152`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e6198`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e61d5`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e61c1`: `Client-side GetProcessInfo not implemented for Packaged COM`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetProcessInfo(
        CPackagedComCatalog *this,
        __int64 a2,
        struct IUserTokenInternal *a3,
        struct _GUID *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned int a7,
        HSTRING *const a8,
        unsigned int a9,
        HSTRING *const a10,
        const struct _GUID *a11,
        HSTRING newString)
{
  void **v12; // r15
  __int64 v13; // rdx
  int v17; // eax
  unsigned int v18; // ebx
  int RegistrationStoreContext; // eax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  int PossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph; // eax
  __int64 v24; // r9
  __int64 v25; // rdx
  const struct _GUID *v26; // r13
  unsigned int v27; // r14d
  __int64 v28; // r12
  int v29; // esi
  int ProcessInfoWorker; // eax
  __int64 v31; // rdx
  int v33; // [rsp+20h] [rbp-30h]
  struct IPackagedComCatalogContext **v34; // [rsp+20h] [rbp-30h]
  void **v35; // [rsp+28h] [rbp-28h]
  struct IPackagedComCatalogContext *v36; // [rsp+30h] [rbp-20h] BYREF
  __int64 v37; // [rsp+38h] [rbp-18h] BYREF
  __int64 v38; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v39; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  HSTRING string; // [rsp+A0h] [rbp+50h] BYREF
  struct _GUID *v42; // [rsp+A8h] [rbp+58h]

  v42 = a4;
  v12 = (void **)newString;
  v13 = 0;
  v37 = 0;
  *(_QWORD *)newString = 0;
  if ( a3 )
  {
    v17 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v37);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD21,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)v17,
        v33);
      return v18;
    }
    v13 = v37;
  }
  v36 = 0;
  v34 = &v36;
  RegistrationStoreContext = RoGetRegistrationStoreContext(1, v13, 0, &GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada);
  v18 = RegistrationStoreContext;
  if ( RegistrationStoreContext < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD26,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)RegistrationStoreContext,
      (int)&v36);
LABEL_33:
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v36);
    return v18;
  }
  if ( !a5 )
  {
    if ( *((_BYTE *)this + 16) )
    {
      v38 = 0;
      v39 = 0;
      PossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph = GetPossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph(
                                                                           a3,
                                                                           a7,
                                                                           a8,
                                                                           &v38);
      v18 = PossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph;
      if ( PossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph >= 0 )
      {
        v26 = a11;
        v27 = 0;
        v28 = v38;
        v18 = -2147221164;
        while ( v27 < v39 )
        {
          newString = 0;
          v29 = Microsoft::WRL::Wrappers::HString::Set(&newString, (HSTRING *)(v28 + 8LL * v27));
          if ( v29 < 0 )
          {
            v31 = 3388;
            goto LABEL_27;
          }
          ProcessInfoWorker = CPackagedComCatalog::GetProcessInfoWorker(
                                a3,
                                v36,
                                (const struct OpaqueString *)&newString,
                                v42,
                                v26,
                                v12);
          v29 = ProcessInfoWorker;
          if ( ProcessInfoWorker >= 0 )
          {
            WindowsDeleteString(newString);
            wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(&v38);
            goto LABEL_25;
          }
          if ( ProcessInfoWorker != -2147221164 )
          {
            v31 = 3398;
LABEL_27:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v31,
              (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
              (const char *)(unsigned int)v29,
              (int)v34);
            WindowsDeleteString(newString);
            newString = 0;
            wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(&v38);
            v18 = v29;
            goto LABEL_33;
          }
          WindowsDeleteString(newString);
          ++v27;
        }
        v24 = 2147746132LL;
        v25 = 3406;
      }
      else
      {
        v24 = (unsigned int)PossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph;
        v25 = 3382;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)v24,
        (int)v34);
      wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(&v38);
    }
    else
    {
      if ( !g_bInSCM )
        MicrosoftTelemetryAssertTriggeredNoArgs(v20);
      v18 = -2147221164;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xD61,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)0x80040154LL,
        (int)"Client-side GetProcessInfo not implemented for Packaged COM",
        (const char *)v35);
    }
    goto LABEL_33;
  }
  string = 0;
  v21 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string);
  v18 = v21;
  if ( v21 < 0 )
  {
    v22 = 3372;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v21,
      (int)v34);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_33;
  }
  v21 = CPackagedComCatalog::GetProcessInfoWorker(a3, v36, (const struct OpaqueString *)&string, a4, a11, v12);
  v18 = v21;
  if ( v21 < 0 )
  {
    v22 = 3374;
    goto LABEL_10;
  }
  WindowsDeleteString(string);
LABEL_25:
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v36);
  return 0;
}

```

## disassembly

```asm
0x1800e5f00  mov     [rsp-38h+arg_0], rbx
0x1800e5f05  mov     [rsp-38h+arg_18], r9
0x1800e5f0a  push    rbp
0x1800e5f0b  push    rsi
0x1800e5f0c  push    rdi
0x1800e5f0d  push    r12
0x1800e5f0f  push    r13
0x1800e5f11  push    r14
0x1800e5f13  push    r15
0x1800e5f15  mov     rbp, rsp
0x1800e5f18  sub     rsp, 50h
0x1800e5f1c  mov     r15, [rbp+newString]
0x1800e5f23  xor     r12d, r12d
0x1800e5f26  mov     edx, r12d
0x1800e5f29  mov     r14, r9
0x1800e5f2c  mov     [rbp+var_18], rdx
0x1800e5f30  mov     rdi, r8
0x1800e5f33  mov     rsi, rcx
0x1800e5f36  mov     [r15], r12
0x1800e5f39  test    r8, r8
0x1800e5f3c  jz      short loc_1800E5F78
0x1800e5f3e  mov     rax, [r8]
0x1800e5f41  lea     rdx, [rbp+var_18]
0x1800e5f45  mov     rcx, r8
0x1800e5f48  mov     rax, [rax+30h]
0x1800e5f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5f51  mov     ebx, eax
0x1800e5f53  test    eax, eax
0x1800e5f55  jns     short loc_1800E5F74
0x1800e5f57  mov     rcx, [rbp+38h]; this
0x1800e5f5b  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e5f62  mov     r9d, eax; char *
0x1800e5f65  mov     edx, 0D21h; void *
0x1800e5f6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5f6f  jmp     loc_1800E61EF
0x1800e5f74  mov     rdx, [rbp+var_18]
0x1800e5f78  xor     r8d, r8d
0x1800e5f7b  mov     [rbp+var_20], r12
0x1800e5f7f  lea     rax, [rbp+var_20]
0x1800e5f83  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800e5f8a  mov     [rsp+50h+var_30], rax; int
0x1800e5f8f  lea     ecx, [r8+1]
0x1800e5f93  call    cs:__imp_RoGetRegistrationStoreContext
0x1800e5f9a  nop     dword ptr [rax+rax+00h]
0x1800e5f9f  mov     ebx, eax
0x1800e5fa1  test    eax, eax
0x1800e5fa3  jns     short loc_1800E5FC2
0x1800e5fa5  mov     rcx, [rbp+38h]; this
0x1800e5fa9  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e5fb0  mov     r9d, eax; char *
0x1800e5fb3  mov     edx, 0D26h; void *
0x1800e5fb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5fbd  jmp     loc_1800E61E6
0x1800e5fc2  cmp     [rbp+arg_20], r12
0x1800e5fc6  jz      loc_1800E605A
0x1800e5fcc  lea     rdx, [rbp+arg_20]
0x1800e5fd0  mov     [rbp+string], r12
0x1800e5fd4  lea     rcx, [rbp+string]; string
0x1800e5fd8  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e5fdd  mov     ebx, eax
0x1800e5fdf  test    eax, eax
0x1800e5fe1  jns     short loc_1800E6014
0x1800e5fe3  mov     edx, 0D2Ch; void *
0x1800e5fe8  mov     rcx, [rbp+38h]; this
0x1800e5fec  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e5ff3  mov     r9d, eax; char *
0x1800e5ff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5ffb  mov     rcx, [rbp+string]; string
0x1800e5fff  call    cs:__imp_WindowsDeleteString
0x1800e6006  nop     dword ptr [rax+rax+00h]
0x1800e600b  mov     [rbp+string], r12
0x1800e600f  jmp     loc_1800E61E6
0x1800e6014  mov     rax, [rbp+arg_50]
0x1800e601b  lea     r8, [rbp+string]; struct OpaqueString *
0x1800e601f  mov     rdx, [rbp+var_20]; struct IPackagedComCatalogContext *
0x1800e6023  mov     r9, r14; struct _GUID *
0x1800e6026  mov     [rsp+50h+var_28], r15; void **
0x1800e602b  mov     rcx, rdi; struct IUserTokenInternal *
0x1800e602e  mov     [rsp+50h+var_30], rax; struct _GUID *
0x1800e6033  call    ?GetProcessInfoWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@3PEAPEAX@Z; CPackagedComCatalog::GetProcessInfoWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,_GUID const &,void * *)
0x1800e6038  mov     ebx, eax
0x1800e603a  test    eax, eax
0x1800e603c  jns     short loc_1800E6045
0x1800e603e  mov     edx, 0D2Eh
0x1800e6043  jmp     short loc_1800E5FE8
0x1800e6045  mov     rcx, [rbp+string]; string
0x1800e6049  call    cs:__imp_WindowsDeleteString
0x1800e6050  nop     dword ptr [rax+rax+00h]
0x1800e6055  jmp     loc_1800E6139
0x1800e605a  cmp     [rsi+10h], r12b
0x1800e605e  jz      loc_1800E61AF
0x1800e6064  mov     r8, [rbp+arg_38]
0x1800e6068  lea     r9, [rbp+var_10]
0x1800e606c  mov     edx, [rbp+arg_30]
0x1800e606f  mov     rcx, rdi
0x1800e6072  mov     [rbp+var_10], r12
0x1800e6076  mov     [rbp+var_8], r12
0x1800e607a  call    ?GetPossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph@@YAJPEAUIUserTokenInternal@@IQEBQEAUHSTRING__@@AEAV?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@@Z; GetPossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph(IUserTokenInternal *,uint,HSTRING__ * const * const,wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64> &)
0x1800e607f  mov     ebx, eax
0x1800e6081  test    eax, eax
0x1800e6083  jns     short loc_1800E6092
0x1800e6085  mov     r9d, eax
0x1800e6088  mov     edx, 0D36h
0x1800e608d  jmp     loc_1800E6194
0x1800e6092  mov     r13, [rbp+arg_50]
0x1800e6099  mov     r14d, r12d
0x1800e609c  mov     r12, [rbp+var_10]
0x1800e60a0  mov     ebx, 80040154h
0x1800e60a5  mov     eax, r14d
0x1800e60a8  cmp     rax, [rbp+var_8]
0x1800e60ac  jnb     loc_1800E618C
0x1800e60b2  lea     rdx, [r12+rax*8]; HSTRING *
0x1800e60b6  mov     [rbp+newString], 0
0x1800e60c1  lea     rcx, [rbp+newString]; newString
0x1800e60c8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800e60cd  mov     esi, eax
0x1800e60cf  test    eax, eax
0x1800e60d1  js      short loc_1800E6149
0x1800e60d3  mov     r9, [rbp+arg_18]; struct _GUID *
0x1800e60d7  lea     r8, [rbp+newString]; struct OpaqueString *
0x1800e60de  mov     rdx, [rbp+var_20]; struct IPackagedComCatalogContext *
0x1800e60e2  mov     rcx, rdi; struct IUserTokenInternal *
0x1800e60e5  mov     [rsp+50h+var_28], r15; void **
0x1800e60ea  mov     [rsp+50h+var_30], r13; struct _GUID *
0x1800e60ef  call    ?GetProcessInfoWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@3PEAPEAX@Z; CPackagedComCatalog::GetProcessInfoWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,_GUID const &,void * *)
0x1800e60f4  mov     esi, eax
0x1800e60f6  test    eax, eax
0x1800e60f8  jns     short loc_1800E611D
0x1800e60fa  cmp     eax, ebx
0x1800e60fc  jnz     short loc_1800E6116
0x1800e60fe  mov     rcx, [rbp+newString]; string
0x1800e6105  call    cs:__imp_WindowsDeleteString
0x1800e610c  nop     dword ptr [rax+rax+00h]
0x1800e6111  inc     r14d
0x1800e6114  jmp     short loc_1800E60A5
0x1800e6116  mov     edx, 0D46h
0x1800e611b  jmp     short loc_1800E614E
0x1800e611d  mov     rcx, [rbp+newString]; string
0x1800e6124  call    cs:__imp_WindowsDeleteString
0x1800e612b  nop     dword ptr [rax+rax+00h]
0x1800e6130  lea     rcx, [rbp+var_10]
0x1800e6134  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x1800e6139  lea     rcx, [rbp+var_20]
0x1800e613d  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800e6142  xor     eax, eax
0x1800e6144  jmp     loc_1800E61F1
0x1800e6149  mov     edx, 0D3Ch; void *
0x1800e614e  mov     rcx, [rbp+38h]; this
0x1800e6152  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e6159  mov     r9d, esi; char *
0x1800e615c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6161  mov     rcx, [rbp+newString]; string
0x1800e6168  call    cs:__imp_WindowsDeleteString
0x1800e616f  nop     dword ptr [rax+rax+00h]
0x1800e6174  lea     rcx, [rbp+var_10]
0x1800e6178  mov     [rbp+newString], 0
0x1800e6183  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x1800e6188  mov     ebx, esi
0x1800e618a  jmp     short loc_1800E61E6
0x1800e618c  mov     r9d, ebx; char *
0x1800e618f  mov     edx, 0D4Eh; void *
0x1800e6194  mov     rcx, [rbp+38h]; this
0x1800e6198  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e619f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e61a4  lea     rcx, [rbp+var_10]
0x1800e61a8  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x1800e61ad  jmp     short loc_1800E61E6
0x1800e61af  cmp     cs:?g_bInSCM@@3JA, r12d; long g_bInSCM
0x1800e61b6  jnz     short loc_1800E61BD
0x1800e61b8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e61bd  mov     rcx, [rbp+38h]; this
0x1800e61c1  lea     rax, aClientSideGetp; "Client-side GetProcessInfo not implemen"...
0x1800e61c8  mov     ebx, 80040154h
0x1800e61cd  mov     [rsp+50h+var_30], rax; int
0x1800e61d2  mov     r9d, ebx; char *
0x1800e61d5  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e61dc  mov     edx, 0D61h; void *
0x1800e61e1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800e61e6  lea     rcx, [rbp+var_20]
0x1800e61ea  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800e61ef  mov     eax, ebx
0x1800e61f1  mov     rbx, [rsp+50h+arg_0]
0x1800e61f9  add     rsp, 50h
0x1800e61fd  pop     r15
0x1800e61ff  pop     r14
0x1800e6201  pop     r13
0x1800e6203  pop     r12
0x1800e6205  pop     rdi
0x1800e6206  pop     rsi
0x1800e6207  pop     rbp
0x1800e6208  retn
```
