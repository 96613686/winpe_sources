# GetBspCatalogSCMObject(_GUID const &,void * *)

- ea: `0x1800d91f4`
- end: `0x1800d961f`
- name: `?GetBspCatalogSCMObject@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `1067`
- prototype: `int(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d9050`

## callees

- `0x180003194`
- `0x180013b18`
- `0x1800210f8`
- `0x180025950`
- `0x1800375e0`
- `0x18003f468`
- `0x180040548`
- `0x180085540`
- `0x180093f20`
- `0x1800a5408`
- `0x1800cd554`
- `0x1800d8f54`
- `0x1800d8fcc`
- `0x1800d91f4`
- `0x1800da014`
- `0x1800da170`

## import_xrefs

- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x1800d92ec`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x1800d93da`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x1800d92ec`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x1800d93da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d9269`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d936a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d9479`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d94cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d9269`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d936a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d9479`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d94cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d934a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d9459`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d934a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d9459`

## string_xrefs

- `0x1800d9239`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d92a9`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d9300`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d93a3`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d93ee`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d9410`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d956a`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d95c2`: `onecore\com\combase\catalog\bspcatalog.cpp`

## pseudocode

```c
__int64 __fastcall GetBspCatalogSCMObject(const struct _GUID *a1, void **a2)
{
  unsigned int ClassesRootFromBspAPI; // eax
  int Interface; // ebx
  MachineWideRegCatalog *v5; // rax
  MachineWideRegCatalog *v6; // rbx
  unsigned __int16 NativeArchitecture; // ax
  HKEY v8; // r14
  __int64 v9; // rdi
  int IsWowGuestMachineSupported; // eax
  int v11; // eax
  unsigned int v12; // eax
  MachineWideRegCatalog *v13; // rax
  __int64 v14; // rbx
  int v15; // eax
  int v16; // eax
  unsigned int v17; // eax
  MachineWideRegCatalog *v18; // rax
  __int64 v19; // rdx
  IComCatalogInternalImpl *v20; // rax
  IComCatalogInternalImpl *v21; // r14
  __int64 v22; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  __int64 v25; // [rsp+30h] [rbp-20h] BYREF
  HKEY v26; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  const struct _GUID *v30; // [rsp+80h] [rbp+30h] BYREF
  HKEY v31; // [rsp+90h] [rbp+40h] BYREF
  __int64 v32; // [rsp+98h] [rbp+48h] BYREF

  v30 = a1;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ClassesRootFromBspAPI = GetClassesRootFromBspAPI(&hKey);
  if ( !ClassesRootFromBspAPI )
  {
    v5 = (MachineWideRegCatalog *)HeapAlloc(g_hHeap, 0, 0x30u);
    v6 = v5;
    if ( v5 )
    {
      NativeArchitecture = GetNativeArchitecture();
      v5 = MachineWideRegCatalog::MachineWideRegCatalog(v6, hKey, NativeArchitecture);
    }
    wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(
      &v32,
      v5);
    if ( !v32 )
    {
      Interface = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\com\\combase\\catalog\\bspcatalog.cpp",
        (const char *)0x8007000ELL,
        phkResult);
LABEL_42:
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v32);
      goto LABEL_43;
    }
    v8 = hKey;
    v9 = 0;
    hKey = 0;
    LOBYTE(v30) = 0;
    v25 = 0;
    v31 = 0;
    IsWowGuestMachineSupported = RtlWow64IsWowGuestMachineSupported(332, &v30);
    if ( IsWowGuestMachineSupported < 0 )
    {
      v11 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x6D,
              (unsigned int)"onecore\\com\\combase\\catalog\\bspcatalog.cpp",
              (const char *)(unsigned int)IsWowGuestMachineSupported,
              phkResult);
LABEL_11:
      Interface = v11;
LABEL_41:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v25);
      goto LABEL_42;
    }
    if ( (_BYTE)v30 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v31,
        0);
      v12 = RegOpenKeyExW(v8, L"WOW6432Node", 0, 0x20019u, &v31);
      if ( v12 )
      {
        if ( v12 != 2 )
        {
          v11 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x79,
                  (unsigned int)"onecore\\com\\combase\\catalog\\bspcatalog.cpp",
                  (const char *)v12,
                  phkResult);
          goto LABEL_11;
        }
      }
      else
      {
        v13 = (MachineWideRegCatalog *)HeapAlloc(g_hHeap, 0, 0x30u);
        if ( v13 )
          v13 = MachineWideRegCatalog::MachineWideRegCatalog(v13, v31, 0x14Cu);
        wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(&v25, v13);
        v9 = v25;
        if ( !v25 )
        {
          Interface = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x74,
            (unsigned int)"onecore\\com\\combase\\catalog\\bspcatalog.cpp",
            (const char *)0x8007000ELL,
            phkResult);
          goto LABEL_41;
        }
        v31 = 0;
      }
    }
    v14 = 0;
    v27 = 0;
    v26 = 0;
    v15 = RtlWow64IsWowGuestMachineSupported(452, &v30);
    if ( v15 < 0 )
    {
      v16 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x7F,
              (unsigned int)"onecore\\com\\combase\\catalog\\bspcatalog.cpp",
              (const char *)(unsigned int)v15,
              phkResult);
LABEL_21:
      Interface = v16;
LABEL_40:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v27);
      goto LABEL_41;
    }
    if ( (_BYTE)v30 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v26,
        0);
      v17 = RegOpenKeyExW(v8, L"WowAA32Node", 0, 0x20019u, &v26);
      if ( v17 )
      {
        if ( v17 != 2 )
        {
          v16 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x8B,
                  (unsigned int)"onecore\\com\\combase\\catalog\\bspcatalog.cpp",
                  (const char *)v17,
                  phkResult);
          goto LABEL_21;
        }
      }
      else
      {
        v18 = (MachineWideRegCatalog *)HeapAlloc(g_hHeap, 0, 0x30u);
        if ( v18 )
          v18 = MachineWideRegCatalog::MachineWideRegCatalog(v18, v26, 0x1C4u);
        wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(&v27, v18);
        v14 = v27;
        if ( !v27 )
        {
          v19 = 134;
          goto LABEL_38;
        }
        v26 = 0;
      }
    }
    v20 = (IComCatalogInternalImpl *)HeapAlloc(g_hHeap, 0, 0x30u);
    v21 = v20;
    if ( v20 )
    {
      IComCatalogInternalImpl::IComCatalogInternalImpl(v20);
      v22 = v32;
      *(_QWORD *)v21 = &BspCatalogSCM::`vftable'{for `IComCatalogInternalImpl'};
      *((_QWORD *)v21 + 1) = &BspCatalogSCM::`vftable'{for `IGetProcessInfoInternal'};
      *((_DWORD *)v21 + 4) = 0;
      wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(
        (char *)v21 + 24,
        v22);
      wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(
        (char *)v21 + 32,
        v9);
      wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(
        (char *)v21 + 40,
        v14);
      _InterlockedIncrement((volatile signed __int32 *)v21 + 4);
      Interface = BspCatalogSCM::QueryInterface(v21, &GUID_a6304910_4115_11d2_8133_0060089f5fed, a2);
      BspCatalogSCM::Release(v21);
      if ( Interface >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v27);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v25);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v32);
        Interface = 0;
        goto LABEL_43;
      }
      v19 = 148;
      goto LABEL_39;
    }
    v19 = 144;
LABEL_38:
    Interface = -2147024882;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\com\\combase\\catalog\\bspcatalog.cpp",
      (const char *)(unsigned int)Interface,
      phkResult);
    goto LABEL_40;
  }
  if ( ClassesRootFromBspAPI != 2 )
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\com\\combase\\catalog\\bspcatalog.cpp",
      (const char *)ClassesRootFromBspAPI,
      phkResult);
  Interface = -2147467231;
LABEL_43:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x1800d91f4  mov     [rsp-28h+arg_8], rbx
0x1800d91f9  mov     [rsp-28h+arg_0], rcx
0x1800d91fe  push    rbp
0x1800d91ff  push    rdi
0x1800d9200  push    r13
0x1800d9202  push    r14
0x1800d9204  push    r15
0x1800d9206  mov     rbp, rsp
0x1800d9209  sub     rsp, 50h
0x1800d920d  mov     r15, rdx
0x1800d9210  mov     [rbp+hKey], 0
0x1800d9218  xor     edx, edx
0x1800d921a  lea     rcx, [rbp+hKey]
0x1800d921e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d9223  lea     rcx, [rbp+hKey]; phkResult
0x1800d9227  call    ?GetClassesRootFromBspAPI@@YAJPEAPEAUHKEY__@@@Z; GetClassesRootFromBspAPI(HKEY__ * *)
0x1800d922c  test    eax, eax
0x1800d922e  jz      short loc_1800D9257
0x1800d9230  cmp     eax, 2
0x1800d9233  jz      short loc_1800D924D
0x1800d9235  mov     rcx, [rbp+28h]; this
0x1800d9239  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d9240  mov     r9d, eax; char *
0x1800d9243  mov     edx, 60h ; '`'; void *
0x1800d9248  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800d924d  mov     ebx, 80004021h
0x1800d9252  jmp     loc_1800D95FE
0x1800d9257  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d925e  mov     r13d, 30h ; '0'
0x1800d9264  mov     r8d, r13d; dwBytes
0x1800d9267  xor     edx, edx; dwFlags
0x1800d9269  call    cs:__imp_HeapAlloc
0x1800d9270  nop     dword ptr [rax+rax+00h]
0x1800d9275  mov     rbx, rax
0x1800d9278  test    rax, rax
0x1800d927b  jz      short loc_1800D9292
0x1800d927d  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x1800d9282  mov     rdx, [rbp+hKey]; HKEY
0x1800d9286  movzx   r8d, ax; unsigned __int16
0x1800d928a  mov     rcx, rbx; this
0x1800d928d  call    ??0MachineWideRegCatalog@@QEAA@PEAUHKEY__@@G@Z; MachineWideRegCatalog::MachineWideRegCatalog(HKEY__ *,ushort)
0x1800d9292  mov     rdx, rax
0x1800d9295  lea     rcx, [rbp+arg_18]
0x1800d9299  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x1800d929e  cmp     [rbp+arg_18], 0
0x1800d92a3  jnz     short loc_1800D92C7
0x1800d92a5  mov     rcx, [rbp+28h]; this
0x1800d92a9  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d92b0  mov     ebx, 8007000Eh
0x1800d92b5  mov     edx, 67h ; 'g'; void *
0x1800d92ba  mov     r9d, ebx; char *
0x1800d92bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d92c2  jmp     loc_1800D95F5
0x1800d92c7  mov     r14, [rbp+hKey]
0x1800d92cb  lea     rdx, [rbp+arg_0]
0x1800d92cf  xor     edi, edi
0x1800d92d1  mov     [rbp+hKey], 0
0x1800d92d9  mov     ebx, 14Ch
0x1800d92de  mov     byte ptr [rbp+arg_0], 0
0x1800d92e2  mov     ecx, ebx
0x1800d92e4  mov     [rbp+var_20], rdi
0x1800d92e8  mov     [rbp+arg_10], rdi
0x1800d92ec  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x1800d92f3  nop     dword ptr [rax+rax+00h]
0x1800d92f8  test    eax, eax
0x1800d92fa  jns     short loc_1800D9319
0x1800d92fc  mov     rcx, [rbp+28h]; this
0x1800d9300  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d9307  mov     r9d, eax; char *
0x1800d930a  lea     edx, [rdi+6Dh]; void *
0x1800d930d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800d9312  mov     ebx, eax
0x1800d9314  jmp     loc_1800D95E3
0x1800d9319  cmp     byte ptr [rbp+arg_0], dil
0x1800d931d  jz      loc_1800D93C7
0x1800d9323  xor     edx, edx
0x1800d9325  lea     rcx, [rbp+arg_10]
0x1800d9329  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d932e  lea     rax, [rbp+arg_10]
0x1800d9332  mov     r9d, 20019h; samDesired
0x1800d9338  xor     r8d, r8d; ulOptions
0x1800d933b  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x1800d9340  lea     rdx, aWow6432node; "WOW6432Node"
0x1800d9347  mov     rcx, r14; hKey
0x1800d934a  call    cs:__imp_RegOpenKeyExW
0x1800d9351  nop     dword ptr [rax+rax+00h]
0x1800d9356  test    eax, eax
0x1800d9358  jnz     loc_1800D9407
0x1800d935e  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d9365  mov     r8, r13; dwBytes
0x1800d9368  xor     edx, edx; dwFlags
0x1800d936a  call    cs:__imp_HeapAlloc
0x1800d9371  nop     dword ptr [rax+rax+00h]
0x1800d9376  test    rax, rax
0x1800d9379  jz      short loc_1800D938A
0x1800d937b  mov     rdx, [rbp+arg_10]; HKEY
0x1800d937f  mov     r8d, ebx; unsigned __int16
0x1800d9382  mov     rcx, rax; this
0x1800d9385  call    ??0MachineWideRegCatalog@@QEAA@PEAUHKEY__@@G@Z; MachineWideRegCatalog::MachineWideRegCatalog(HKEY__ *,ushort)
0x1800d938a  mov     rdx, rax
0x1800d938d  lea     rcx, [rbp+var_20]
0x1800d9391  call    ??4?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIComCatalogInternal@@@Z; wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(IComCatalogInternal *)
0x1800d9396  mov     rdi, [rbp+var_20]
0x1800d939a  test    rdi, rdi
0x1800d939d  jnz     short loc_1800D93BF
0x1800d939f  mov     rcx, [rbp+28h]; this
0x1800d93a3  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d93aa  mov     ebx, 8007000Eh
0x1800d93af  lea     edx, [rdi+74h]; void *
0x1800d93b2  mov     r9d, ebx; char *
0x1800d93b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d93ba  jmp     loc_1800D95E3
0x1800d93bf  mov     [rbp+arg_10], 0
0x1800d93c7  xor     ebx, ebx
0x1800d93c9  lea     rdx, [rbp+arg_0]
0x1800d93cd  mov     ecx, 1C4h
0x1800d93d2  mov     [rbp+var_10], rbx
0x1800d93d6  mov     [rbp+var_18], rbx
0x1800d93da  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x1800d93e1  nop     dword ptr [rax+rax+00h]
0x1800d93e6  test    eax, eax
0x1800d93e8  jns     short loc_1800D9429
0x1800d93ea  mov     rcx, [rbp+28h]; this
0x1800d93ee  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d93f5  mov     r9d, eax; char *
0x1800d93f8  lea     edx, [rbx+7Fh]; void *
0x1800d93fb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800d9400  mov     ebx, eax
0x1800d9402  jmp     loc_1800D95D1
0x1800d9407  cmp     eax, 2
0x1800d940a  jz      short loc_1800D93C7
0x1800d940c  mov     rcx, [rbp+28h]; this
0x1800d9410  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d9417  mov     r9d, eax; char *
0x1800d941a  mov     edx, 79h ; 'y'; void *
0x1800d941f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d9424  jmp     loc_1800D9312
0x1800d9429  cmp     byte ptr [rbp+arg_0], bl
0x1800d942c  jz      loc_1800D94C3
0x1800d9432  xor     edx, edx
0x1800d9434  lea     rcx, [rbp+var_18]
0x1800d9438  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d943d  lea     rax, [rbp+var_18]
0x1800d9441  mov     r9d, 20019h; samDesired
0x1800d9447  xor     r8d, r8d; ulOptions
0x1800d944a  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800d944f  lea     rdx, aWowaa32node; "WowAA32Node"
0x1800d9456  mov     rcx, r14; hKey
0x1800d9459  call    cs:__imp_RegOpenKeyExW
0x1800d9460  nop     dword ptr [rax+rax+00h]
0x1800d9465  test    eax, eax
0x1800d9467  jnz     loc_1800D955D
0x1800d946d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d9474  mov     r8, r13; dwBytes
0x1800d9477  xor     edx, edx; dwFlags
0x1800d9479  call    cs:__imp_HeapAlloc
0x1800d9480  nop     dword ptr [rax+rax+00h]
0x1800d9485  test    rax, rax
0x1800d9488  jz      short loc_1800D949C
0x1800d948a  mov     rdx, [rbp+var_18]; HKEY
0x1800d948e  mov     r8d, 1C4h; unsigned __int16
0x1800d9494  mov     rcx, rax; this
0x1800d9497  call    ??0MachineWideRegCatalog@@QEAA@PEAUHKEY__@@G@Z; MachineWideRegCatalog::MachineWideRegCatalog(HKEY__ *,ushort)
0x1800d949c  mov     rdx, rax
0x1800d949f  lea     rcx, [rbp+var_10]
0x1800d94a3  call    ??4?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIComCatalogInternal@@@Z; wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(IComCatalogInternal *)
0x1800d94a8  mov     rbx, [rbp+var_10]
0x1800d94ac  test    rbx, rbx
0x1800d94af  jnz     short loc_1800D94BB
0x1800d94b1  mov     edx, 86h
0x1800d94b6  jmp     loc_1800D95B9
0x1800d94bb  mov     [rbp+var_18], 0
0x1800d94c3  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d94ca  mov     r8, r13; dwBytes
0x1800d94cd  xor     edx, edx; dwFlags
0x1800d94cf  call    cs:__imp_HeapAlloc
0x1800d94d6  nop     dword ptr [rax+rax+00h]
0x1800d94db  mov     r14, rax
0x1800d94de  test    rax, rax
0x1800d94e1  jz      loc_1800D95B4
0x1800d94e7  mov     rcx, rax; this
0x1800d94ea  call    ??0IComCatalogInternalImpl@@QEAA@XZ; IComCatalogInternalImpl::IComCatalogInternalImpl(void)
0x1800d94ef  mov     rdx, [rbp+arg_18]
0x1800d94f3  lea     rcx, ??_7BspCatalogSCM@@6BIComCatalogInternalImpl@@@; const BspCatalogSCM::`vftable'{for `IComCatalogInternalImpl'}
0x1800d94fa  mov     [r14], rcx
0x1800d94fd  lea     rax, ??_7BspCatalogSCM@@6BIGetProcessInfoInternal@@@; const BspCatalogSCM::`vftable'{for `IGetProcessInfoInternal'}
0x1800d9504  lea     rcx, [r14+18h]
0x1800d9508  mov     [r14+8], rax
0x1800d950c  mov     dword ptr [r14+10h], 0
0x1800d9514  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x1800d9519  lea     rcx, [r14+20h]
0x1800d951d  mov     rdx, rdi
0x1800d9520  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x1800d9525  lea     rcx, [r14+28h]
0x1800d9529  mov     rdx, rbx
0x1800d952c  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x1800d9531  lock inc dword ptr [r14+10h]
0x1800d9536  mov     r8, r15; void **
0x1800d9539  lea     rdx, _GUID_a6304910_4115_11d2_8133_0060089f5fed; struct _GUID *
0x1800d9540  mov     rcx, r14; this
0x1800d9543  call    ?QueryInterface@BspCatalogSCM@@UEAAJAEBU_GUID@@PEAPEAX@Z; BspCatalogSCM::QueryInterface(_GUID const &,void * *)
0x1800d9548  mov     rcx, r14; this
0x1800d954b  mov     ebx, eax
0x1800d954d  call    ?Release@BspCatalogSCM@@UEAAKXZ; BspCatalogSCM::Release(void)
0x1800d9552  test    ebx, ebx
0x1800d9554  jns     short loc_1800D9583
0x1800d9556  mov     edx, 94h
0x1800d955b  jmp     short loc_1800D95BE
0x1800d955d  cmp     eax, 2
0x1800d9560  jz      loc_1800D94C3
0x1800d9566  mov     rcx, [rbp+28h]; this
0x1800d956a  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d9571  mov     r9d, eax; char *
0x1800d9574  mov     edx, 8Bh; void *
0x1800d9579  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d957e  jmp     loc_1800D9400
0x1800d9583  lea     rcx, [rbp+var_18]
0x1800d9587  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d958c  lea     rcx, [rbp+var_10]
0x1800d9590  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d9595  lea     rcx, [rbp+arg_10]
0x1800d9599  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d959e  lea     rcx, [rbp+var_20]
0x1800d95a2  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d95a7  lea     rcx, [rbp+arg_18]
0x1800d95ab  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d95b0  xor     ebx, ebx
0x1800d95b2  jmp     short loc_1800D95FE
0x1800d95b4  mov     edx, 90h; void *
0x1800d95b9  mov     ebx, 8007000Eh
0x1800d95be  mov     rcx, [rbp+28h]; this
0x1800d95c2  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d95c9  mov     r9d, ebx; char *
0x1800d95cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d95d1  lea     rcx, [rbp+var_18]
0x1800d95d5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d95da  lea     rcx, [rbp+var_10]
0x1800d95de  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d95e3  lea     rcx, [rbp+arg_10]
0x1800d95e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d95ec  lea     rcx, [rbp+var_20]
0x1800d95f0  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d95f5  lea     rcx, [rbp+arg_18]
0x1800d95f9  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d95fe  lea     rcx, [rbp+hKey]
0x1800d9602  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d9607  mov     eax, ebx
0x1800d9609  mov     rbx, [rsp+50h+arg_8]
0x1800d9611  add     rsp, 50h
0x1800d9615  pop     r15
0x1800d9617  pop     r14
0x1800d9619  pop     r13
0x1800d961b  pop     rdi
0x1800d961c  pop     rbp
0x1800d961d  retn
```
