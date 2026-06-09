# GetBspCatalogSCMObject(_GUID const &,void * *)

- ea: `0x1800d2884`
- end: `0x1800d2c7e`
- name: `?GetBspCatalogSCMObject@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `1018`
- prototype: `int(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d26f0`

## callees

- `0x180003064`
- `0x18000f1b8`
- `0x18002834c`
- `0x18002ba28`
- `0x18002f8cc`
- `0x180039068`
- `0x18006e06c`
- `0x180080a90`
- `0x18008cd90`
- `0x1800a0e14`
- `0x1800c74f8`
- `0x1800d25f4`
- `0x1800d2668`
- `0x1800d2884`
- `0x1800d3674`
- `0x1800d37c0`

## import_xrefs

- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x1800d2976`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x1800d2a52`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x1800d2976`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x1800d2a52`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d28f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d29e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d2ae5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d2b35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d28f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d29e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d2ae5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d2b35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d29ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2acb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d29ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2acb`

## string_xrefs

- `0x1800d28c9`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d2933`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d2984`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d2a1b`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d2a60`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d2a82`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d2bca`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1800d2c22`: `onecore\com\combase\catalog\bspcatalog.cpp`

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
0x1800d2884  mov     [rsp-28h+arg_8], rbx
0x1800d2889  mov     [rsp-28h+arg_0], rcx
0x1800d288e  push    rbp
0x1800d288f  push    rdi
0x1800d2890  push    r13
0x1800d2892  push    r14
0x1800d2894  push    r15
0x1800d2896  mov     rbp, rsp
0x1800d2899  sub     rsp, 50h
0x1800d289d  mov     r15, rdx
0x1800d28a0  mov     [rbp+hKey], 0
0x1800d28a8  xor     edx, edx
0x1800d28aa  lea     rcx, [rbp+hKey]
0x1800d28ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d28b3  lea     rcx, [rbp+hKey]; phkResult
0x1800d28b7  call    ?GetClassesRootFromBspAPI@@YAJPEAPEAUHKEY__@@@Z; GetClassesRootFromBspAPI(HKEY__ * *)
0x1800d28bc  test    eax, eax
0x1800d28be  jz      short loc_1800D28E7
0x1800d28c0  cmp     eax, 2
0x1800d28c3  jz      short loc_1800D28DD
0x1800d28c5  mov     rcx, [rbp+28h]; this
0x1800d28c9  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d28d0  mov     r9d, eax; char *
0x1800d28d3  mov     edx, 60h ; '`'; void *
0x1800d28d8  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800d28dd  mov     ebx, 80004021h
0x1800d28e2  jmp     loc_1800D2C5E
0x1800d28e7  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d28ee  mov     r13d, 30h ; '0'
0x1800d28f4  mov     r8d, r13d; dwBytes
0x1800d28f7  xor     edx, edx; dwFlags
0x1800d28f9  call    cs:__imp_HeapAlloc
0x1800d28ff  mov     rbx, rax
0x1800d2902  test    rax, rax
0x1800d2905  jz      short loc_1800D291C
0x1800d2907  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x1800d290c  mov     rdx, [rbp+hKey]; HKEY
0x1800d2910  movzx   r8d, ax; unsigned __int16
0x1800d2914  mov     rcx, rbx; this
0x1800d2917  call    ??0MachineWideRegCatalog@@QEAA@PEAUHKEY__@@G@Z; MachineWideRegCatalog::MachineWideRegCatalog(HKEY__ *,ushort)
0x1800d291c  mov     rdx, rax
0x1800d291f  lea     rcx, [rbp+arg_18]
0x1800d2923  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x1800d2928  cmp     [rbp+arg_18], 0
0x1800d292d  jnz     short loc_1800D2951
0x1800d292f  mov     rcx, [rbp+28h]; this
0x1800d2933  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d293a  mov     ebx, 8007000Eh
0x1800d293f  mov     edx, 67h ; 'g'; void *
0x1800d2944  mov     r9d, ebx; char *
0x1800d2947  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d294c  jmp     loc_1800D2C55
0x1800d2951  mov     r14, [rbp+hKey]
0x1800d2955  lea     rdx, [rbp+arg_0]
0x1800d2959  xor     edi, edi
0x1800d295b  mov     [rbp+hKey], 0
0x1800d2963  mov     ebx, 14Ch
0x1800d2968  mov     byte ptr [rbp+arg_0], 0
0x1800d296c  mov     ecx, ebx
0x1800d296e  mov     [rbp+var_20], rdi
0x1800d2972  mov     [rbp+arg_10], rdi
0x1800d2976  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x1800d297c  test    eax, eax
0x1800d297e  jns     short loc_1800D299D
0x1800d2980  mov     rcx, [rbp+28h]; this
0x1800d2984  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d298b  mov     r9d, eax; char *
0x1800d298e  lea     edx, [rdi+6Dh]; void *
0x1800d2991  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800d2996  mov     ebx, eax
0x1800d2998  jmp     loc_1800D2C43
0x1800d299d  cmp     byte ptr [rbp+arg_0], dil
0x1800d29a1  jz      loc_1800D2A3F
0x1800d29a7  xor     edx, edx
0x1800d29a9  lea     rcx, [rbp+arg_10]
0x1800d29ad  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d29b2  lea     rax, [rbp+arg_10]
0x1800d29b6  mov     r9d, 20019h; samDesired
0x1800d29bc  xor     r8d, r8d; ulOptions
0x1800d29bf  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x1800d29c4  lea     rdx, aWow6432node; "WOW6432Node"
0x1800d29cb  mov     rcx, r14; hKey
0x1800d29ce  call    cs:__imp_RegOpenKeyExW
0x1800d29d4  test    eax, eax
0x1800d29d6  jnz     loc_1800D2A79
0x1800d29dc  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d29e3  mov     r8, r13; dwBytes
0x1800d29e6  xor     edx, edx; dwFlags
0x1800d29e8  call    cs:__imp_HeapAlloc
0x1800d29ee  test    rax, rax
0x1800d29f1  jz      short loc_1800D2A02
0x1800d29f3  mov     rdx, [rbp+arg_10]; HKEY
0x1800d29f7  mov     r8d, ebx; unsigned __int16
0x1800d29fa  mov     rcx, rax; this
0x1800d29fd  call    ??0MachineWideRegCatalog@@QEAA@PEAUHKEY__@@G@Z; MachineWideRegCatalog::MachineWideRegCatalog(HKEY__ *,ushort)
0x1800d2a02  mov     rdx, rax
0x1800d2a05  lea     rcx, [rbp+var_20]
0x1800d2a09  call    ??4?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIComCatalogInternal@@@Z; wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(IComCatalogInternal *)
0x1800d2a0e  mov     rdi, [rbp+var_20]
0x1800d2a12  test    rdi, rdi
0x1800d2a15  jnz     short loc_1800D2A37
0x1800d2a17  mov     rcx, [rbp+28h]; this
0x1800d2a1b  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d2a22  mov     ebx, 8007000Eh
0x1800d2a27  lea     edx, [rdi+74h]; void *
0x1800d2a2a  mov     r9d, ebx; char *
0x1800d2a2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2a32  jmp     loc_1800D2C43
0x1800d2a37  mov     [rbp+arg_10], 0
0x1800d2a3f  xor     ebx, ebx
0x1800d2a41  lea     rdx, [rbp+arg_0]
0x1800d2a45  mov     ecx, 1C4h
0x1800d2a4a  mov     [rbp+var_10], rbx
0x1800d2a4e  mov     [rbp+var_18], rbx
0x1800d2a52  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x1800d2a58  test    eax, eax
0x1800d2a5a  jns     short loc_1800D2A9B
0x1800d2a5c  mov     rcx, [rbp+28h]; this
0x1800d2a60  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d2a67  mov     r9d, eax; char *
0x1800d2a6a  lea     edx, [rbx+7Fh]; void *
0x1800d2a6d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800d2a72  mov     ebx, eax
0x1800d2a74  jmp     loc_1800D2C31
0x1800d2a79  cmp     eax, 2
0x1800d2a7c  jz      short loc_1800D2A3F
0x1800d2a7e  mov     rcx, [rbp+28h]; this
0x1800d2a82  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d2a89  mov     r9d, eax; char *
0x1800d2a8c  mov     edx, 79h ; 'y'; void *
0x1800d2a91  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d2a96  jmp     loc_1800D2996
0x1800d2a9b  cmp     byte ptr [rbp+arg_0], bl
0x1800d2a9e  jz      loc_1800D2B29
0x1800d2aa4  xor     edx, edx
0x1800d2aa6  lea     rcx, [rbp+var_18]
0x1800d2aaa  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d2aaf  lea     rax, [rbp+var_18]
0x1800d2ab3  mov     r9d, 20019h; samDesired
0x1800d2ab9  xor     r8d, r8d; ulOptions
0x1800d2abc  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800d2ac1  lea     rdx, aWowaa32node; "WowAA32Node"
0x1800d2ac8  mov     rcx, r14; hKey
0x1800d2acb  call    cs:__imp_RegOpenKeyExW
0x1800d2ad1  test    eax, eax
0x1800d2ad3  jnz     loc_1800D2BBD
0x1800d2ad9  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d2ae0  mov     r8, r13; dwBytes
0x1800d2ae3  xor     edx, edx; dwFlags
0x1800d2ae5  call    cs:__imp_HeapAlloc
0x1800d2aeb  test    rax, rax
0x1800d2aee  jz      short loc_1800D2B02
0x1800d2af0  mov     rdx, [rbp+var_18]; HKEY
0x1800d2af4  mov     r8d, 1C4h; unsigned __int16
0x1800d2afa  mov     rcx, rax; this
0x1800d2afd  call    ??0MachineWideRegCatalog@@QEAA@PEAUHKEY__@@G@Z; MachineWideRegCatalog::MachineWideRegCatalog(HKEY__ *,ushort)
0x1800d2b02  mov     rdx, rax
0x1800d2b05  lea     rcx, [rbp+var_10]
0x1800d2b09  call    ??4?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIComCatalogInternal@@@Z; wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(IComCatalogInternal *)
0x1800d2b0e  mov     rbx, [rbp+var_10]
0x1800d2b12  test    rbx, rbx
0x1800d2b15  jnz     short loc_1800D2B21
0x1800d2b17  mov     edx, 86h
0x1800d2b1c  jmp     loc_1800D2C19
0x1800d2b21  mov     [rbp+var_18], 0
0x1800d2b29  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d2b30  mov     r8, r13; dwBytes
0x1800d2b33  xor     edx, edx; dwFlags
0x1800d2b35  call    cs:__imp_HeapAlloc
0x1800d2b3b  mov     r14, rax
0x1800d2b3e  test    rax, rax
0x1800d2b41  jz      loc_1800D2C14
0x1800d2b47  mov     rcx, rax; this
0x1800d2b4a  call    ??0IComCatalogInternalImpl@@QEAA@XZ; IComCatalogInternalImpl::IComCatalogInternalImpl(void)
0x1800d2b4f  mov     rdx, [rbp+arg_18]
0x1800d2b53  lea     rcx, ??_7BspCatalogSCM@@6BIComCatalogInternalImpl@@@; const BspCatalogSCM::`vftable'{for `IComCatalogInternalImpl'}
0x1800d2b5a  mov     [r14], rcx
0x1800d2b5d  lea     rax, ??_7BspCatalogSCM@@6BIGetProcessInfoInternal@@@; const BspCatalogSCM::`vftable'{for `IGetProcessInfoInternal'}
0x1800d2b64  lea     rcx, [r14+18h]
0x1800d2b68  mov     [r14+8], rax
0x1800d2b6c  mov     dword ptr [r14+10h], 0
0x1800d2b74  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x1800d2b79  lea     rcx, [r14+20h]
0x1800d2b7d  mov     rdx, rdi
0x1800d2b80  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x1800d2b85  lea     rcx, [r14+28h]
0x1800d2b89  mov     rdx, rbx
0x1800d2b8c  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x1800d2b91  lock inc dword ptr [r14+10h]
0x1800d2b96  mov     r8, r15; void **
0x1800d2b99  lea     rdx, _GUID_a6304910_4115_11d2_8133_0060089f5fed; struct _GUID *
0x1800d2ba0  mov     rcx, r14; this
0x1800d2ba3  call    ?QueryInterface@BspCatalogSCM@@UEAAJAEBU_GUID@@PEAPEAX@Z; BspCatalogSCM::QueryInterface(_GUID const &,void * *)
0x1800d2ba8  mov     rcx, r14; this
0x1800d2bab  mov     ebx, eax
0x1800d2bad  call    ?Release@BspCatalogSCM@@UEAAKXZ; BspCatalogSCM::Release(void)
0x1800d2bb2  test    ebx, ebx
0x1800d2bb4  jns     short loc_1800D2BE3
0x1800d2bb6  mov     edx, 94h
0x1800d2bbb  jmp     short loc_1800D2C1E
0x1800d2bbd  cmp     eax, 2
0x1800d2bc0  jz      loc_1800D2B29
0x1800d2bc6  mov     rcx, [rbp+28h]; this
0x1800d2bca  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d2bd1  mov     r9d, eax; char *
0x1800d2bd4  mov     edx, 8Bh; void *
0x1800d2bd9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d2bde  jmp     loc_1800D2A72
0x1800d2be3  lea     rcx, [rbp+var_18]
0x1800d2be7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2bec  lea     rcx, [rbp+var_10]
0x1800d2bf0  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d2bf5  lea     rcx, [rbp+arg_10]
0x1800d2bf9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2bfe  lea     rcx, [rbp+var_20]
0x1800d2c02  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d2c07  lea     rcx, [rbp+arg_18]
0x1800d2c0b  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d2c10  xor     ebx, ebx
0x1800d2c12  jmp     short loc_1800D2C5E
0x1800d2c14  mov     edx, 90h; void *
0x1800d2c19  mov     ebx, 8007000Eh
0x1800d2c1e  mov     rcx, [rbp+28h]; this
0x1800d2c22  lea     r8, aOnecoreComComb_95; "onecore\\com\\combase\\catalog\\bspcata"...
0x1800d2c29  mov     r9d, ebx; char *
0x1800d2c2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2c31  lea     rcx, [rbp+var_18]
0x1800d2c35  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2c3a  lea     rcx, [rbp+var_10]
0x1800d2c3e  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d2c43  lea     rcx, [rbp+arg_10]
0x1800d2c47  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2c4c  lea     rcx, [rbp+var_20]
0x1800d2c50  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d2c55  lea     rcx, [rbp+arg_18]
0x1800d2c59  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800d2c5e  lea     rcx, [rbp+hKey]
0x1800d2c62  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2c67  mov     eax, ebx
0x1800d2c69  mov     rbx, [rsp+50h+arg_8]
0x1800d2c71  add     rsp, 50h
0x1800d2c75  pop     r15
0x1800d2c77  pop     r14
0x1800d2c79  pop     r13
0x1800d2c7b  pop     rdi
0x1800d2c7c  pop     rbp
0x1800d2c7d  retn
```
