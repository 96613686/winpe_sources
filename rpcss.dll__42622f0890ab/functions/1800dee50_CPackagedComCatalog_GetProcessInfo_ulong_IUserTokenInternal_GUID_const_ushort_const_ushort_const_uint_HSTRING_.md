# CPackagedComCatalog::GetProcessInfo(ulong,IUserTokenInternal *,_GUID const &,ushort const *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const,_GUID const &,void * *)

- ea: `0x1800dee50`
- end: `0x1800df135`
- name: `?GetProcessInfo@CPackagedComCatalog@@UEAAJKPEAUIUserTokenInternal@@AEBU_GUID@@PEBG2IQEBQEAUHSTRING__@@I31PEAPEAX@Z`
- size: `741`
- prototype: `__int64 __fastcall(CPackagedComCatalog *__hidden this, unsigned int, struct IUserTokenInternal *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, HSTRING *const, unsigned int, HSTRING *const, const struct _GUID *, HSTRING newString)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003064`
- `0x18000b428`
- `0x1800128b8`
- `0x18002ba28`
- `0x18004c4e0`
- `0x18008e98c`
- `0x1800933b0`
- `0x1800ce12c`
- `0x1800dee50`
- `0x1800df3d8`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800def49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800def8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df043`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df05c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df09a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800def49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800def8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df043`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df05c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df09a`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800deee3`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800deee3`

## string_xrefs

- `0x1800deeab`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800deef3`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800def36`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800df084`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800df0c4`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800df101`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800df0ed`: `Client-side GetProcessInfo not implemented for Packaged COM`

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
0x1800dee50  mov     [rsp-38h+arg_0], rbx
0x1800dee55  mov     [rsp-38h+arg_18], r9
0x1800dee5a  push    rbp
0x1800dee5b  push    rsi
0x1800dee5c  push    rdi
0x1800dee5d  push    r12
0x1800dee5f  push    r13
0x1800dee61  push    r14
0x1800dee63  push    r15
0x1800dee65  mov     rbp, rsp
0x1800dee68  sub     rsp, 50h
0x1800dee6c  mov     r15, [rbp+newString]
0x1800dee73  xor     r12d, r12d
0x1800dee76  mov     edx, r12d
0x1800dee79  mov     r14, r9
0x1800dee7c  mov     [rbp+var_18], rdx
0x1800dee80  mov     rdi, r8
0x1800dee83  mov     rsi, rcx
0x1800dee86  mov     [r15], r12
0x1800dee89  test    r8, r8
0x1800dee8c  jz      short loc_1800DEEC8
0x1800dee8e  mov     rax, [r8]
0x1800dee91  lea     rdx, [rbp+var_18]
0x1800dee95  mov     rcx, r8
0x1800dee98  mov     rax, [rax+30h]
0x1800dee9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deea1  mov     ebx, eax
0x1800deea3  test    eax, eax
0x1800deea5  jns     short loc_1800DEEC4
0x1800deea7  mov     rcx, [rbp+38h]; this
0x1800deeab  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800deeb2  mov     r9d, eax; char *
0x1800deeb5  mov     edx, 0D21h; void *
0x1800deeba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800deebf  jmp     loc_1800DF11B
0x1800deec4  mov     rdx, [rbp+var_18]
0x1800deec8  xor     r8d, r8d
0x1800deecb  mov     [rbp+var_20], r12
0x1800deecf  lea     rax, [rbp+var_20]
0x1800deed3  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800deeda  mov     [rsp+50h+var_30], rax; int
0x1800deedf  lea     ecx, [r8+1]
0x1800deee3  call    cs:__imp_RoGetRegistrationStoreContext
0x1800deee9  mov     ebx, eax
0x1800deeeb  test    eax, eax
0x1800deeed  jns     short loc_1800DEF0C
0x1800deeef  mov     rcx, [rbp+38h]; this
0x1800deef3  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800deefa  mov     r9d, eax; char *
0x1800deefd  mov     edx, 0D26h; void *
0x1800def02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800def07  jmp     loc_1800DF112
0x1800def0c  cmp     [rbp+arg_20], r12
0x1800def10  jz      loc_1800DEF98
0x1800def16  lea     rdx, [rbp+arg_20]
0x1800def1a  mov     [rbp+string], r12
0x1800def1e  lea     rcx, [rbp+string]; string
0x1800def22  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800def27  mov     ebx, eax
0x1800def29  test    eax, eax
0x1800def2b  jns     short loc_1800DEF58
0x1800def2d  mov     edx, 0D2Ch; void *
0x1800def32  mov     rcx, [rbp+38h]; this
0x1800def36  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800def3d  mov     r9d, eax; char *
0x1800def40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800def45  mov     rcx, [rbp+string]; string
0x1800def49  call    cs:__imp_WindowsDeleteString
0x1800def4f  mov     [rbp+string], r12
0x1800def53  jmp     loc_1800DF112
0x1800def58  mov     rax, [rbp+arg_50]
0x1800def5f  lea     r8, [rbp+string]; struct OpaqueString *
0x1800def63  mov     rdx, [rbp+var_20]; struct IPackagedComCatalogContext *
0x1800def67  mov     r9, r14; struct _GUID *
0x1800def6a  mov     [rsp+50h+var_28], r15; void **
0x1800def6f  mov     rcx, rdi; struct IUserTokenInternal *
0x1800def72  mov     [rsp+50h+var_30], rax; struct _GUID *
0x1800def77  call    ?GetProcessInfoWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@3PEAPEAX@Z; CPackagedComCatalog::GetProcessInfoWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,_GUID const &,void * *)
0x1800def7c  mov     ebx, eax
0x1800def7e  test    eax, eax
0x1800def80  jns     short loc_1800DEF89
0x1800def82  mov     edx, 0D2Eh
0x1800def87  jmp     short loc_1800DEF32
0x1800def89  mov     rcx, [rbp+string]; string
0x1800def8d  call    cs:__imp_WindowsDeleteString
0x1800def93  jmp     loc_1800DF06B
0x1800def98  cmp     [rsi+10h], r12b
0x1800def9c  jz      loc_1800DF0DB
0x1800defa2  mov     r8, [rbp+arg_38]
0x1800defa6  lea     r9, [rbp+var_10]
0x1800defaa  mov     edx, [rbp+arg_30]
0x1800defad  mov     rcx, rdi
0x1800defb0  mov     [rbp+var_10], r12
0x1800defb4  mov     [rbp+var_8], r12
0x1800defb8  call    ?GetPossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph@@YAJPEAUIUserTokenInternal@@IQEBQEAUHSTRING__@@AEAV?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@@Z; GetPossibleRegistrationSourcePackageFullNamesForCurrentPackageGraph(IUserTokenInternal *,uint,HSTRING__ * const * const,wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64> &)
0x1800defbd  mov     ebx, eax
0x1800defbf  test    eax, eax
0x1800defc1  jns     short loc_1800DEFD0
0x1800defc3  mov     r9d, eax
0x1800defc6  mov     edx, 0D36h
0x1800defcb  jmp     loc_1800DF0C0
0x1800defd0  mov     r13, [rbp+arg_50]
0x1800defd7  mov     r14d, r12d
0x1800defda  mov     r12, [rbp+var_10]
0x1800defde  mov     ebx, 80040154h
0x1800defe3  mov     eax, r14d
0x1800defe6  cmp     rax, [rbp+var_8]
0x1800defea  jnb     loc_1800DF0B8
0x1800deff0  lea     rdx, [r12+rax*8]; HSTRING *
0x1800deff4  mov     [rbp+newString], 0
0x1800defff  lea     rcx, [rbp+newString]; newString
0x1800df006  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800df00b  mov     esi, eax
0x1800df00d  test    eax, eax
0x1800df00f  js      short loc_1800DF07B
0x1800df011  mov     r9, [rbp+arg_18]; struct _GUID *
0x1800df015  lea     r8, [rbp+newString]; struct OpaqueString *
0x1800df01c  mov     rdx, [rbp+var_20]; struct IPackagedComCatalogContext *
0x1800df020  mov     rcx, rdi; struct IUserTokenInternal *
0x1800df023  mov     [rsp+50h+var_28], r15; void **
0x1800df028  mov     [rsp+50h+var_30], r13; struct _GUID *
0x1800df02d  call    ?GetProcessInfoWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@3PEAPEAX@Z; CPackagedComCatalog::GetProcessInfoWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,_GUID const &,void * *)
0x1800df032  mov     esi, eax
0x1800df034  test    eax, eax
0x1800df036  jns     short loc_1800DF055
0x1800df038  cmp     eax, ebx
0x1800df03a  jnz     short loc_1800DF04E
0x1800df03c  mov     rcx, [rbp+newString]; string
0x1800df043  call    cs:__imp_WindowsDeleteString
0x1800df049  inc     r14d
0x1800df04c  jmp     short loc_1800DEFE3
0x1800df04e  mov     edx, 0D46h
0x1800df053  jmp     short loc_1800DF080
0x1800df055  mov     rcx, [rbp+newString]; string
0x1800df05c  call    cs:__imp_WindowsDeleteString
0x1800df062  lea     rcx, [rbp+var_10]
0x1800df066  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x1800df06b  lea     rcx, [rbp+var_20]
0x1800df06f  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800df074  xor     eax, eax
0x1800df076  jmp     loc_1800DF11D
0x1800df07b  mov     edx, 0D3Ch; void *
0x1800df080  mov     rcx, [rbp+38h]; this
0x1800df084  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800df08b  mov     r9d, esi; char *
0x1800df08e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df093  mov     rcx, [rbp+newString]; string
0x1800df09a  call    cs:__imp_WindowsDeleteString
0x1800df0a0  lea     rcx, [rbp+var_10]
0x1800df0a4  mov     [rbp+newString], 0
0x1800df0af  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x1800df0b4  mov     ebx, esi
0x1800df0b6  jmp     short loc_1800DF112
0x1800df0b8  mov     r9d, ebx; char *
0x1800df0bb  mov     edx, 0D4Eh; void *
0x1800df0c0  mov     rcx, [rbp+38h]; this
0x1800df0c4  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800df0cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df0d0  lea     rcx, [rbp+var_10]
0x1800df0d4  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x1800df0d9  jmp     short loc_1800DF112
0x1800df0db  cmp     cs:?g_bInSCM@@3JA, r12d; long g_bInSCM
0x1800df0e2  jnz     short loc_1800DF0E9
0x1800df0e4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800df0e9  mov     rcx, [rbp+38h]; this
0x1800df0ed  lea     rax, aClientSideGetp; "Client-side GetProcessInfo not implemen"...
0x1800df0f4  mov     ebx, 80040154h
0x1800df0f9  mov     [rsp+50h+var_30], rax; int
0x1800df0fe  mov     r9d, ebx; char *
0x1800df101  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800df108  mov     edx, 0D61h; void *
0x1800df10d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800df112  lea     rcx, [rbp+var_20]
0x1800df116  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800df11b  mov     eax, ebx
0x1800df11d  mov     rbx, [rsp+50h+arg_0]
0x1800df125  add     rsp, 50h
0x1800df129  pop     r15
0x1800df12b  pop     r14
0x1800df12d  pop     r13
0x1800df12f  pop     r12
0x1800df131  pop     rdi
0x1800df132  pop     rsi
0x1800df133  pop     rbp
0x1800df134  retn
```
