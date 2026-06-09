# CreateAndCacheIconOverlay(CDSA<FSIconOverlay> *,_DCA *,bool,bool,int,_GUID const *)

- ea: `0x1800a3710`
- end: `0x1800a3f2e`
- name: `?CreateAndCacheIconOverlay@@YAJPEAV?$CDSA@UFSIconOverlay@@@@PEAU_DCA@@_N2HPEBU_GUID@@@Z`
- size: `2078`
- prototype: `__int64 __fastcall(int, int, int, int, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a3620`

## callees

- `0x180038608`
- `0x18003a3e0`
- `0x18003e1e8`
- `0x180055afc`
- `0x180078a24`
- `0x1800a2f24`
- `0x1800a3710`
- `0x1800a3f34`
- `0x1800a3fec`
- `0x1800a4040`
- `0x1800a4ff8`
- `0x1800a5b98`
- `0x1800a5c28`
- `0x1801d0ed8`
- `0x180249490`
- `0x18024a53c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3a09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3c47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3d03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3ed7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3a09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3c47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3d03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3ed7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a397c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a39ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a3cb4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a397c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a39ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a3cb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a392f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3c0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a392f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3c0e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800a3f03`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800a3f03`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1800a38c2`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1800a3ba8`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1800a38c2`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1800a3ba8`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x1800a3eae`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x1800a3eae`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x1800a3a8e`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x1800a3a8e`

## string_xrefs

- `0x1800a38d5`: `CLSID\%s`
- `0x1800a3bbb`: `CLSID\%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CreateAndCacheIconOverlay(HDSA *a1, int a2, char a3, char a4, int a5, struct _GUID *a6)
{
  const struct _GUID *v10; // rdx
  int v11; // ecx
  int v12; // r8d
  int Instance; // eax
  unsigned int ValueW; // ebx
  void *v15; // rcx
  __int64 v17; // rdi
  int v18; // eax
  char v19; // dl
  int v20; // eax
  int v21; // edx
  HKEY v22; // rbx
  void *v23; // rax
  void *v24; // rcx
  __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  WCHAR *v27; // r8
  unsigned __int16 v28; // r9
  WCHAR *v29; // rcx
  void *v30; // rcx
  int v31; // eax
  unsigned int v32; // eax
  void *v33; // rcx
  WCHAR v34; // ax
  bool v35; // sf
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  void *v40; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  void *pitem; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v45; // [rsp+48h] [rbp-B8h]
  int v46; // [rsp+58h] [rbp-A8h]
  int v47; // [rsp+5Ch] [rbp-A4h]
  int v48; // [rsp+60h] [rbp-A0h]
  int v49; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR pszIconFile[260]; // [rsp+68h] [rbp-98h] BYREF
  void *v51; // [rsp+270h] [rbp+170h] BYREF
  int v52; // [rsp+278h] [rbp+178h] BYREF
  DWORD pcbData; // [rsp+280h] [rbp+180h] BYREF
  int v54; // [rsp+288h] [rbp+188h] BYREF
  HKEY hkey[2]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v56[80]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR SubKey[80]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v58[264]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v59[264]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int16 pvData[264]; // [rsp+7B0h] [rbp+6B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9F8h] [rbp+8F8h]

  memset_0(&pitem, 0, 0x230u);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v11, (unsigned int)Shell32_ExternalOverlayDllLoad_Info, v12, 1, (__int64)hkey);
  v51 = 0;
  if ( a4 )
  {
    Instance = ActivateHandlerInHost(a6, v10, &v51);
  }
  else if ( a3 )
  {
    Instance = SHExtCoCreateInstance(a6, 0, 4, 2, &GUID_0c6c4200_c589_11d0_999a_00c04fd655e1, &v51);
  }
  else
  {
    Instance = DCA_SHExtCoCreateInstance(
                 a2,
                 a5,
                 v12,
                 (unsigned int)&GUID_0c6c4200_c589_11d0_999a_00c04fd655e1,
                 (__int64)&v51);
  }
  ValueW = Instance;
  if ( Instance < 0 )
  {
    v15 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return ValueW;
  }
  if ( !a3 && !SHPinDllOfCLSID(a6) )
  {
    ValueW = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E9,
      (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
      (const char *)0x80070490LL,
      phkResult);
    v37 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v37 + 16LL))(v37);
    }
    return ValueW;
  }
  v52 = 0;
  v54 = 0;
  v48 = -1;
  v17 = 260;
  v18 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, __int64, int *))(*(_QWORD *)v51 + 32LL))(
          v51,
          v58,
          260,
          &v54);
  ValueW = v18;
  if ( !v18 )
  {
    v19 = v52;
    if ( (v52 & 1) != 0 )
    {
      v25 = 2147483646;
      v26 = v58;
      v27 = pszIconFile;
      do
      {
        if ( !v25 )
          break;
        v28 = *v26;
        if ( !*v26 )
          break;
        ++v26;
        *v27++ = v28;
        --v25;
        --v17;
      }
      while ( v17 );
      v29 = v27 - 1;
      if ( v17 )
        v29 = v27;
      *v29 = 0;
      if ( !v17 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2F8,
          (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
          (const char *)0x8007007ALL,
          (int)&v52);
        v19 = v52;
      }
      v47 = -1;
      v46 = (v19 & 2) != 0 ? v54 : 0;
    }
    v20 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v51 + 40LL))(v51, &v49);
    v21 = v49;
    if ( v20 < 0 )
      v21 = 100;
    v49 = v21;
    v45 = *a6;
    if ( !a3 )
    {
      hkey[0] = 0;
      SHStringFromGUIDW(a6, v56, 39);
      if ( (int)StringCchPrintfW(SubKey, 0x4Fu, L"CLSID\\%s", v56) >= 0 )
      {
        v22 = hkey[0];
        if ( hkey[0] )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&pcbData);
          RegCloseKey(v22);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&pcbData);
        }
        hkey[0] = 0;
        if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, hkey) >= 0 )
        {
          pcbData = 520;
          if ( RegGetValueW(hkey[0], 0, 0, 2u, 0, pvData, &pcbData) )
            pvData[0] = 0;
          pcbData = 520;
          if ( RegGetValueW(hkey[0], L"InProcServer32", 0, 2u, 0, v59, &pcbData) )
            v59[0] = 0;
          FileExplorerAggregateTelemetry::IconOverlayHandlersAggregate(pvData, v59, v58);
        }
      }
      if ( hkey[0] )
        RegCloseKey(hkey[0]);
    }
LABEL_27:
    v23 = v51;
    v51 = 0;
    pitem = v23;
    DSA_InsertItem(*a1, 0x7FFFFFFF, &pitem);
    v24 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return 0;
  }
  if ( a3 )
  {
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x337,
        (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
        (const char *)(unsigned int)v18,
        (int)&v52);
      v30 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 16LL))(v30);
      }
      return ValueW;
    }
    goto LABEL_27;
  }
  hkey[0] = 0;
  v47 = -1;
  SHStringFromGUIDW(a6, v56, 39);
  v31 = StringCchPrintfW(SubKey, 0x4Fu, L"CLSID\\%s", v56);
  ValueW = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32B,
      (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
      (const char *)(unsigned int)v31,
      (int)&v52);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
    v38 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
    }
    return ValueW;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hkey,
    0);
  v32 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, hkey);
  if ( v32 )
  {
    ValueW = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x32C,
               (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
               (const char *)v32,
               phkResulta);
    if ( hkey[0] )
      RegCloseKey(hkey[0]);
    v33 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return ValueW;
  }
  pcbData = 520;
  ValueW = RegGetValueW(hkey[0], 0, L"DefaultIcon", 2u, 0, pszIconFile, &pcbData);
  if ( ValueW )
  {
    v34 = 0;
    pszIconFile[0] = 0;
    v35 = (ValueW & 0x80000000) != 0;
    if ( (int)ValueW <= 0 )
      goto LABEL_58;
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  else
  {
    v34 = pszIconFile[0];
  }
  v35 = (ValueW & 0x80000000) != 0;
LABEL_58:
  if ( !v35 )
  {
    if ( !v34 )
    {
      ValueW = -2147020590;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x331,
        (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
        (const char *)0x800710D2LL,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
      v40 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v40 + 16LL))(v40);
      }
      return ValueW;
    }
    v46 = PathParseIconLocationW(pszIconFile);
    v45 = *a6;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
    goto LABEL_27;
  }
  if ( ValueW != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x330,
      (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
      (const char *)ValueW,
      phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
    v39 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v39 + 16LL))(v39);
    }
    return ValueW;
  }
  if ( hkey[0] )
    RegCloseKey(hkey[0]);
  v36 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
  }
  return 2147942402LL;
}

```

## disassembly

```asm
0x1800a3710  mov     [rsp-8+arg_10], rbx
0x1800a3715  mov     [rsp-8+arg_18], rsi
0x1800a371a  push    rbp
0x1800a371b  push    rdi
0x1800a371c  push    r12
0x1800a371e  push    r14
0x1800a3720  push    r15
0x1800a3722  lea     rbp, [rsp-8D0h]
0x1800a372a  sub     rsp, 9D0h
0x1800a3731  mov     rax, cs:__security_cookie
0x1800a3738  xor     rax, rsp
0x1800a373b  mov     [rbp+8F0h+var_30], rax
0x1800a3742  mov     bl, r9b
0x1800a3745  mov     r14b, r8b
0x1800a3748  mov     rdi, rdx
0x1800a374b  mov     r15, rcx
0x1800a374e  mov     rsi, [rbp+8F0h+arg_28]
0x1800a3755  xor     edx, edx; Val
0x1800a3757  mov     r8d, 230h; Size
0x1800a375d  lea     rcx, [rsp+9F0h+pitem]; void *
0x1800a3762  call    memset_0
0x1800a3767  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800a376e  jnz     loc_1800A3E88
0x1800a3774  xor     r12d, r12d
0x1800a3777  mov     [rbp+8F0h+var_780], r12
0x1800a377e  test    bl, bl
0x1800a3780  jnz     loc_1800A3A63
0x1800a3786  lea     rax, [rbp+8F0h+var_780]
0x1800a378d  lea     r9, _GUID_0c6c4200_c589_11d0_999a_00c04fd655e1
0x1800a3794  test    r14b, r14b
0x1800a3797  jnz     loc_1800A3A77
0x1800a379d  mov     [rsp+9F0h+phkResult], rax; int
0x1800a37a2  mov     edx, [rbp+8F0h+arg_20]
0x1800a37a8  mov     rcx, rdi
0x1800a37ab  call    DCA_SHExtCoCreateInstance
0x1800a37b0  mov     ebx, eax
0x1800a37b2  test    eax, eax
0x1800a37b4  jns     short loc_1800A3804
0x1800a37b6  mov     rcx, [rbp+8F0h+var_780]
0x1800a37bd  test    rcx, rcx
0x1800a37c0  jz      short loc_1800A37D6
0x1800a37c2  mov     [rbp+8F0h+var_780], r12
0x1800a37c9  mov     rax, [rcx]
0x1800a37cc  mov     rax, [rax+10h]
0x1800a37d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a37d5  nop
0x1800a37d6  mov     eax, ebx
0x1800a37d8  mov     rcx, [rbp+8F0h+var_30]
0x1800a37df  xor     rcx, rsp; StackCookie
0x1800a37e2  call    __security_check_cookie
0x1800a37e7  lea     r11, [rsp+9F0h+var_20]
0x1800a37ef  mov     rbx, [r11+40h]
0x1800a37f3  mov     rsi, [r11+48h]
0x1800a37f7  mov     rsp, r11
0x1800a37fa  pop     r15
0x1800a37fc  pop     r14
0x1800a37fe  pop     r12
0x1800a3800  pop     rdi
0x1800a3801  pop     rbp
0x1800a3802  retn
0x1800a3804  test    r14b, r14b
0x1800a3807  jz      loc_1800A3EAB
0x1800a380d  mov     [rbp+8F0h+var_778], r12d
0x1800a3814  mov     [rbp+8F0h+var_768], r12d
0x1800a381b  mov     [rsp+9F0h+var_990], 0FFFFFFFFh
0x1800a3823  mov     rcx, [rbp+8F0h+var_780]
0x1800a382a  mov     rax, [rcx]
0x1800a382d  lea     rdx, [rbp+8F0h+var_778]
0x1800a3834  mov     [rsp+9F0h+phkResult], rdx; int
0x1800a3839  lea     r9, [rbp+8F0h+var_768]
0x1800a3840  mov     edi, 104h
0x1800a3845  mov     r8d, edi
0x1800a3848  lea     rdx, [rbp+8F0h+var_660]
0x1800a384f  mov     rax, [rax+20h]
0x1800a3853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3858  mov     ebx, eax
0x1800a385a  test    eax, eax
0x1800a385c  jnz     loc_1800A3B3B
0x1800a3862  mov     edx, [rbp+8F0h+var_778]
0x1800a3868  test    dl, 1
0x1800a386b  jnz     loc_1800A3AB9
0x1800a3871  mov     rcx, [rbp+8F0h+var_780]
0x1800a3878  mov     rax, [rcx]
0x1800a387b  lea     rdx, [rsp+9F0h+var_98C]
0x1800a3880  mov     rax, [rax+28h]
0x1800a3884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3889  mov     edx, [rsp+9F0h+var_98C]
0x1800a388d  mov     ecx, 64h ; 'd'
0x1800a3892  test    eax, eax
0x1800a3894  cmovs   edx, ecx
0x1800a3897  mov     [rsp+9F0h+var_98C], edx
0x1800a389b  movups  xmm0, xmmword ptr [rsi]
0x1800a389e  movdqu  [rsp+9F0h+var_9A8], xmm0
0x1800a38a4  test    r14b, r14b
0x1800a38a7  jnz     loc_1800A3A16
0x1800a38ad  mov     [rbp+8F0h+hkey], r12
0x1800a38b4  lea     r8d, [rcx-3Dh]
0x1800a38b8  lea     rdx, [rbp+8F0h+var_750]
0x1800a38bf  mov     rcx, rsi
0x1800a38c2  call    cs:__imp_SHStringFromGUIDW
0x1800a38c9  nop     dword ptr [rax+rax+00h]
0x1800a38ce  lea     r9, [rbp+8F0h+var_750]
0x1800a38d5  lea     r8, aClsidS; "CLSID\\%s"
0x1800a38dc  mov     edx, 4Fh ; 'O'; unsigned __int64
0x1800a38e1  lea     rcx, [rbp+8F0h+SubKey]; unsigned __int16 *
0x1800a38e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a38ed  test    eax, eax
0x1800a38ef  js      loc_1800A39FD
0x1800a38f5  mov     rbx, [rbp+8F0h+hkey]
0x1800a38fc  test    rbx, rbx
0x1800a38ff  jnz     loc_1800A3EC8
0x1800a3905  mov     [rbp+8F0h+hkey], r12
0x1800a390c  lea     rax, [rbp+8F0h+hkey]
0x1800a3913  mov     [rsp+9F0h+phkResult], rax; phkResult
0x1800a3918  mov     r9d, 1; samDesired
0x1800a391e  xor     r8d, r8d; ulOptions
0x1800a3921  lea     rdx, [rbp+8F0h+SubKey]; lpSubKey
0x1800a3928  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800a392f  call    cs:__imp_RegOpenKeyExW
0x1800a3936  nop     dword ptr [rax+rax+00h]
0x1800a393b  test    eax, eax
0x1800a393d  js      loc_1800A39FD
0x1800a3943  mov     [rbp+8F0h+var_770], 208h
0x1800a394d  lea     rax, [rbp+8F0h+var_770]
0x1800a3954  mov     [rsp+9F0h+pcbData], rax; pcbData
0x1800a3959  lea     rax, [rbp+8F0h+var_240]
0x1800a3960  mov     [rsp+9F0h+pvData], rax; pvData
0x1800a3965  mov     [rsp+9F0h+phkResult], r12; pdwType
0x1800a396a  mov     r9d, 2; dwFlags
0x1800a3970  xor     r8d, r8d; lpValue
0x1800a3973  xor     edx, edx; lpSubKey
0x1800a3975  mov     rcx, [rbp+8F0h+hkey]; hkey
0x1800a397c  call    cs:__imp_RegGetValueW
0x1800a3983  nop     dword ptr [rax+rax+00h]
0x1800a3988  test    eax, eax
0x1800a398a  jnz     loc_1800A3A9F
0x1800a3990  mov     [rbp+8F0h+var_770], 208h
0x1800a399a  lea     rax, [rbp+8F0h+var_770]
0x1800a39a1  mov     [rsp+9F0h+pcbData], rax; pcbData
0x1800a39a6  lea     rax, [rbp+8F0h+var_450]
0x1800a39ad  mov     [rsp+9F0h+pvData], rax; pvData
0x1800a39b2  mov     [rsp+9F0h+phkResult], r12; pdwType
0x1800a39b7  mov     r9d, 2; dwFlags
0x1800a39bd  xor     r8d, r8d; lpValue
0x1800a39c0  lea     rdx, aInprocserver32; "InProcServer32"
0x1800a39c7  mov     rcx, [rbp+8F0h+hkey]; hkey
0x1800a39ce  call    cs:__imp_RegGetValueW
0x1800a39d5  nop     dword ptr [rax+rax+00h]
0x1800a39da  test    eax, eax
0x1800a39dc  jnz     loc_1800A3AAC
0x1800a39e2  lea     r8, [rbp+8F0h+var_660]; unsigned __int16 *
0x1800a39e9  lea     rdx, [rbp+8F0h+var_450]; unsigned __int16 *
0x1800a39f0  lea     rcx, [rbp+8F0h+var_240]; unsigned __int16 *
0x1800a39f7  call    ?IconOverlayHandlersAggregate@FileExplorerAggregateTelemetry@@SAXPEBG00@Z; FileExplorerAggregateTelemetry::IconOverlayHandlersAggregate(ushort const *,ushort const *,ushort const *)
0x1800a39fc  nop
0x1800a39fd  mov     rcx, [rbp+8F0h+hkey]; hKey
0x1800a3a04  test    rcx, rcx
0x1800a3a07  jz      short loc_1800A3A16
0x1800a3a09  call    cs:__imp_RegCloseKey
0x1800a3a10  nop     dword ptr [rax+rax+00h]
0x1800a3a15  nop
0x1800a3a16  mov     rax, [rbp+8F0h+var_780]
0x1800a3a1d  mov     [rbp+8F0h+var_780], r12
0x1800a3a24  mov     [rsp+9F0h+pitem], rax
0x1800a3a29  lea     r8, [rsp+9F0h+pitem]; pitem
0x1800a3a2e  mov     edx, 7FFFFFFFh; i
0x1800a3a33  mov     rcx, [r15]; hdsa
0x1800a3a36  call    DSA_InsertItem
0x1800a3a3b  nop
0x1800a3a3c  mov     rcx, [rbp+8F0h+var_780]
0x1800a3a43  test    rcx, rcx
0x1800a3a46  jz      short loc_1800A3A5C
0x1800a3a48  mov     [rbp+8F0h+var_780], r12
0x1800a3a4f  mov     rax, [rcx]
0x1800a3a52  mov     rax, [rax+10h]
0x1800a3a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a5b  nop
0x1800a3a5c  xor     eax, eax
0x1800a3a5e  jmp     loc_1800A37D8
0x1800a3a63  lea     r8, [rbp+8F0h+var_780]; void **
0x1800a3a6a  mov     rcx, rsi; struct _GUID *
0x1800a3a6d  call    ?ActivateHandlerInHost@@YAJAEBU_GUID@@0PEAPEAX@Z; ActivateHandlerInHost(_GUID const &,_GUID const &,void * *)
0x1800a3a72  jmp     loc_1800A37B0
0x1800a3a77  mov     [rsp+9F0h+pvData], rax
0x1800a3a7c  mov     [rsp+9F0h+phkResult], r9
0x1800a3a81  xor     edx, edx
0x1800a3a83  lea     r9d, [rdx+2]
0x1800a3a87  lea     r8d, [rdx+4]
0x1800a3a8b  mov     rcx, rsi
0x1800a3a8e  call    cs:__imp_SHExtCoCreateInstance
0x1800a3a95  nop     dword ptr [rax+rax+00h]
0x1800a3a9a  jmp     loc_1800A37B0
0x1800a3a9f  mov     [rbp+8F0h+var_240], r12w
0x1800a3aa7  jmp     loc_1800A3990
0x1800a3aac  mov     [rbp+8F0h+var_450], r12w
0x1800a3ab4  jmp     loc_1800A39E2
0x1800a3ab9  mov     eax, 7FFFFFFEh
0x1800a3abe  lea     rcx, [rbp+8F0h+var_660]
0x1800a3ac5  lea     r8, [rsp+9F0h+pszIconFile]
0x1800a3aca  test    rax, rax
0x1800a3acd  jz      short loc_1800A3AEE
0x1800a3acf  movzx   r9d, word ptr [rcx]
0x1800a3ad3  test    r9w, r9w
0x1800a3ad7  jz      short loc_1800A3AEE
0x1800a3ad9  add     rcx, 2
0x1800a3add  mov     [r8], r9w
0x1800a3ae1  add     r8, 2
0x1800a3ae5  dec     rax
0x1800a3ae8  sub     rdi, 1
0x1800a3aec  jnz     short loc_1800A3ACA
0x1800a3aee  mov     rax, rdi
0x1800a3af1  neg     rax
0x1800a3af4  sbb     r9d, r9d
0x1800a3af7  not     r9d
0x1800a3afa  and     r9d, 8007007Ah; char *
0x1800a3b01  lea     rcx, [r8-2]
0x1800a3b05  test    rdi, rdi
0x1800a3b08  cmovnz  rcx, r8
0x1800a3b0c  mov     [rcx], r12w
0x1800a3b10  mov     rcx, [rbp+8F8h]; this
0x1800a3b17  jz      loc_1800A3D37
0x1800a3b1d  mov     [rsp+9F0h+var_994], 0FFFFFFFFh
0x1800a3b25  and     dl, 2
0x1800a3b28  neg     dl
0x1800a3b2a  sbb     eax, eax
0x1800a3b2c  and     eax, [rbp+8F0h+var_768]
0x1800a3b32  mov     [rsp+9F0h+var_998], eax
0x1800a3b36  jmp     loc_1800A3871
0x1800a3b3b  test    r14b, r14b
0x1800a3b3e  jz      short loc_1800A3B89
0x1800a3b40  test    ebx, ebx
0x1800a3b42  jns     loc_1800A3A16
0x1800a3b48  mov     rcx, [rbp+8F8h]; this
0x1800a3b4f  mov     r9d, ebx; char *
0x1800a3b52  lea     r8, aShellShell32Ov; "shell\\shell32\\ovrlaymn.cpp"
0x1800a3b59  mov     edx, 337h; void *
0x1800a3b5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3b63  nop
0x1800a3b64  mov     rcx, [rbp+8F0h+var_780]
0x1800a3b6b  test    rcx, rcx
0x1800a3b6e  jz      short loc_1800A3B84
0x1800a3b70  mov     [rbp+8F0h+var_780], r12
0x1800a3b77  mov     rax, [rcx]
0x1800a3b7a  mov     rax, [rax+10h]
0x1800a3b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3b83  nop
0x1800a3b84  jmp     loc_1800A37D6
0x1800a3b89  mov     [rbp+8F0h+hkey], r12
0x1800a3b90  mov     [rsp+9F0h+var_994], 0FFFFFFFFh
0x1800a3b98  mov     r8d, 27h ; '''
0x1800a3b9e  lea     rdx, [rbp+8F0h+var_750]
0x1800a3ba5  mov     rcx, rsi
0x1800a3ba8  call    cs:__imp_SHStringFromGUIDW
0x1800a3baf  nop     dword ptr [rax+rax+00h]
0x1800a3bb4  lea     r9, [rbp+8F0h+var_750]
0x1800a3bbb  lea     r8, aClsidS; "CLSID\\%s"
0x1800a3bc2  mov     edx, 4Fh ; 'O'; unsigned __int64
0x1800a3bc7  lea     rcx, [rbp+8F0h+SubKey]; unsigned __int16 *
0x1800a3bce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3bd3  mov     ebx, eax
0x1800a3bd5  test    eax, eax
0x1800a3bd7  js      loc_1800A3D99
0x1800a3bdd  xor     edx, edx
0x1800a3bdf  lea     rcx, [rbp+8F0h+hkey]
0x1800a3be6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a3beb  lea     rax, [rbp+8F0h+hkey]
0x1800a3bf2  mov     [rsp+9F0h+phkResult], rax; unsigned int
0x1800a3bf7  mov     r9d, 1; samDesired
0x1800a3bfd  xor     r8d, r8d; ulOptions
0x1800a3c00  lea     rdx, [rbp+8F0h+SubKey]; lpSubKey
0x1800a3c07  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800a3c0e  call    cs:__imp_RegOpenKeyExW
0x1800a3c15  nop     dword ptr [rax+rax+00h]
0x1800a3c1a  test    eax, eax
0x1800a3c1c  jz      short loc_1800A3C79
0x1800a3c1e  mov     rcx, [rbp+8F8h]; this
0x1800a3c25  mov     r9d, eax; char *
0x1800a3c28  lea     r8, aShellShell32Ov; "shell\\shell32\\ovrlaymn.cpp"
0x1800a3c2f  mov     edx, 32Ch; void *
0x1800a3c34  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a3c39  mov     ebx, eax
0x1800a3c3b  mov     rcx, [rbp+8F0h+hkey]; hKey
0x1800a3c42  test    rcx, rcx
0x1800a3c45  jz      short loc_1800A3C54
0x1800a3c47  call    cs:__imp_RegCloseKey
0x1800a3c4e  nop     dword ptr [rax+rax+00h]
0x1800a3c53  nop
0x1800a3c54  mov     rcx, [rbp+8F0h+var_780]
0x1800a3c5b  test    rcx, rcx
0x1800a3c5e  jz      short loc_1800A3C74
0x1800a3c60  mov     [rbp+8F0h+var_780], r12
0x1800a3c67  mov     rax, [rcx]
0x1800a3c6a  mov     rax, [rax+10h]
0x1800a3c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3c73  nop
0x1800a3c74  jmp     loc_1800A37D6
0x1800a3c79  mov     [rbp+8F0h+var_770], 208h
0x1800a3c83  lea     rax, [rbp+8F0h+var_770]
0x1800a3c8a  mov     [rsp+9F0h+pcbData], rax; pcbData
0x1800a3c8f  lea     rax, [rsp+9F0h+pszIconFile]
  ... truncated ...
```
