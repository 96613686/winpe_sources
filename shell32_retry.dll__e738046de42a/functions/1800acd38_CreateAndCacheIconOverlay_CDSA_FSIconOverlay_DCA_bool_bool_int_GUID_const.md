# CreateAndCacheIconOverlay(CDSA<FSIconOverlay> *,_DCA *,bool,bool,int,_GUID const *)

- ea: `0x1800acd38`
- end: `0x1800ad531`
- name: `?CreateAndCacheIconOverlay@@YAJPEAV?$CDSA@UFSIconOverlay@@@@PEAU_DCA@@_N2HPEBU_GUID@@@Z`
- size: `2041`
- prototype: `__int64 __fastcall(int, int, int, int, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800acc54`

## callees

- `0x18003cd64`
- `0x18003eab0`
- `0x1800426e8`
- `0x1800960ec`
- `0x180096170`
- `0x1800a7264`
- `0x1800ac89c`
- `0x1800acd38`
- `0x1800ad538`
- `0x1800ad5e0`
- `0x1800ad62c`
- `0x1800bb328`
- `0x1801bb5e4`
- `0x180233280`
- `0x1802342fc`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acf50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ad214`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acf50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ad214`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad018`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad247`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad2f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad4bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad4e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad018`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad247`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad2f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad4bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad4e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acf97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acfe3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ad2ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acf97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acfe3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ad2ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800ad50c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800ad50c`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1800acee9`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1800ad1ab`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1800acee9`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1800ad1ab`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x1800ad49c`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x1800ad49c`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x1800ad097`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x1800ad097`

## string_xrefs

- `0x1800acef6`: `CLSID\%s`
- `0x1800ad1b8`: `CLSID\%s`

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
  HKEY v32; // rbx
  unsigned int v33; // eax
  void *v34; // rcx
  WCHAR v35; // ax
  bool v36; // sf
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  void *pitem; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v46; // [rsp+48h] [rbp-B8h]
  int v47; // [rsp+58h] [rbp-A8h]
  int v48; // [rsp+5Ch] [rbp-A4h]
  int v49; // [rsp+60h] [rbp-A0h]
  int v50; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR pszIconFile[260]; // [rsp+68h] [rbp-98h] BYREF
  void *v52; // [rsp+270h] [rbp+170h] BYREF
  DWORD pcbData; // [rsp+278h] [rbp+178h] BYREF
  int v54; // [rsp+280h] [rbp+180h] BYREF
  int v55; // [rsp+284h] [rbp+184h] BYREF
  HKEY hkey[3]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v57[80]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR SubKey[80]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v59[264]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v60[264]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int16 pvData[264]; // [rsp+7B0h] [rbp+6B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9F8h] [rbp+8F8h]

  memset_0(&pitem, 0, 0x230u);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v11,
      (unsigned int)&Shell32_ExternalOverlayDllLoad_Info,
      v12,
      1,
      (__int64)hkey);
  v52 = 0;
  if ( a4 )
  {
    Instance = ActivateHandlerInHost(a6, v10, &v52);
  }
  else if ( a3 )
  {
    Instance = SHExtCoCreateInstance(a6, 0, 4, 2, &GUID_0c6c4200_c589_11d0_999a_00c04fd655e1, &v52);
  }
  else
  {
    Instance = DCA_SHExtCoCreateInstance(
                 a2,
                 a5,
                 v12,
                 (unsigned int)&GUID_0c6c4200_c589_11d0_999a_00c04fd655e1,
                 (__int64)&v52);
  }
  ValueW = Instance;
  if ( Instance < 0 )
  {
    v15 = v52;
    if ( v52 )
    {
      v52 = 0;
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
    v38 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
    }
    return ValueW;
  }
  v54 = 0;
  v55 = 0;
  v49 = -1;
  v17 = 260;
  v18 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, __int64, int *))(*(_QWORD *)v52 + 32LL))(
          v52,
          v59,
          260,
          &v55);
  ValueW = v18;
  if ( !v18 )
  {
    v19 = v54;
    if ( (v54 & 1) != 0 )
    {
      v25 = 2147483646;
      v26 = v59;
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
          (int)&v54);
        v19 = v54;
      }
      v48 = -1;
      v47 = (v19 & 2) != 0 ? v55 : 0;
    }
    v20 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v52 + 40LL))(v52, &v50);
    v21 = v50;
    if ( v20 < 0 )
      v21 = 100;
    v50 = v21;
    v46 = *a6;
    if ( !a3 )
    {
      hkey[0] = 0;
      SHStringFromGUIDW(a6, v57, 39);
      if ( (int)StringCchPrintfW(SubKey, 0x4Fu, L"CLSID\\%s", v57) >= 0 )
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
          if ( RegGetValueW(hkey[0], L"InProcServer32", 0, 2u, 0, v60, &pcbData) )
            v60[0] = 0;
          FileExplorerAggregateTelemetry::IconOverlayHandlersAggregate(pvData, v60, v59);
        }
      }
      if ( hkey[0] )
        RegCloseKey(hkey[0]);
    }
LABEL_27:
    v23 = v52;
    v52 = 0;
    pitem = v23;
    DSA_InsertItem(*a1, 0x7FFFFFFF, &pitem);
    v24 = v52;
    if ( v52 )
    {
      v52 = 0;
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
        (int)&v54);
      v30 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 16LL))(v30);
      }
      return ValueW;
    }
    goto LABEL_27;
  }
  hkey[0] = 0;
  v48 = -1;
  SHStringFromGUIDW(a6, v57, 39);
  v31 = StringCchPrintfW(SubKey, 0x4Fu, L"CLSID\\%s", v57);
  ValueW = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32B,
      (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
      (const char *)(unsigned int)v31,
      (int)&v54);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
    v39 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v39 + 16LL))(v39);
    }
    return ValueW;
  }
  v32 = hkey[0];
  if ( hkey[0] )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&pcbData);
    RegCloseKey(v32);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&pcbData);
  }
  hkey[0] = 0;
  v33 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, hkey);
  if ( v33 )
  {
    ValueW = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x32C,
               (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
               (const char *)v33,
               phkResulta);
    if ( hkey[0] )
      RegCloseKey(hkey[0]);
    v34 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
    }
    return ValueW;
  }
  pcbData = 520;
  ValueW = RegGetValueW(hkey[0], 0, L"DefaultIcon", 2u, 0, pszIconFile, &pcbData);
  if ( ValueW )
  {
    v35 = 0;
    pszIconFile[0] = 0;
    v36 = (ValueW & 0x80000000) != 0;
    if ( (int)ValueW <= 0 )
      goto LABEL_60;
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  else
  {
    v35 = pszIconFile[0];
  }
  v36 = (ValueW & 0x80000000) != 0;
LABEL_60:
  if ( !v36 )
  {
    if ( !v35 )
    {
      ValueW = -2147020590;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x331,
        (unsigned int)"shell\\shell32\\ovrlaymn.cpp",
        (const char *)0x800710D2LL,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
      v41 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
      }
      return ValueW;
    }
    v47 = PathParseIconLocationW(pszIconFile);
    v46 = *a6;
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
    v40 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return ValueW;
  }
  if ( hkey[0] )
    RegCloseKey(hkey[0]);
  v37 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v37 + 16LL))(v37);
  }
  return 2147942402LL;
}

```

## disassembly

```asm
0x1800acd38  mov     [rsp-8+arg_10], rbx
0x1800acd3d  mov     [rsp-8+arg_18], rsi
0x1800acd42  push    rbp
0x1800acd43  push    rdi
0x1800acd44  push    r12
0x1800acd46  push    r14
0x1800acd48  push    r15
0x1800acd4a  lea     rbp, [rsp-8D0h]
0x1800acd52  sub     rsp, 9D0h
0x1800acd59  mov     rax, cs:__security_cookie
0x1800acd60  xor     rax, rsp
0x1800acd63  mov     [rbp+8F0h+var_30], rax
0x1800acd6a  mov     bl, r9b
0x1800acd6d  mov     r14b, r8b
0x1800acd70  mov     rdi, rdx
0x1800acd73  mov     r15, rcx
0x1800acd76  mov     rsi, [rbp+8F0h+arg_28]
0x1800acd7d  xor     edx, edx; Val
0x1800acd7f  mov     r8d, 230h; Size
0x1800acd85  lea     rcx, [rsp+9F0h+pitem]; void *
0x1800acd8a  call    memset_0
0x1800acd8f  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800acd96  jnz     loc_1800AD476
0x1800acd9c  xor     r12d, r12d
0x1800acd9f  mov     [rbp+8F0h+var_780], r12
0x1800acda6  test    bl, bl
0x1800acda8  jnz     loc_1800AD06C
0x1800acdae  lea     rax, [rbp+8F0h+var_780]
0x1800acdb5  lea     r9, _GUID_0c6c4200_c589_11d0_999a_00c04fd655e1
0x1800acdbc  test    r14b, r14b
0x1800acdbf  jnz     loc_1800AD080
0x1800acdc5  mov     [rsp+9F0h+phkResult], rax; int
0x1800acdca  mov     edx, [rbp+8F0h+arg_20]
0x1800acdd0  mov     rcx, rdi
0x1800acdd3  call    DCA_SHExtCoCreateInstance
0x1800acdd8  mov     ebx, eax
0x1800acdda  test    eax, eax
0x1800acddc  jns     short loc_1800ACE2B
0x1800acdde  mov     rcx, [rbp+8F0h+var_780]
0x1800acde5  test    rcx, rcx
0x1800acde8  jz      short loc_1800ACDFE
0x1800acdea  mov     [rbp+8F0h+var_780], r12
0x1800acdf1  mov     rax, [rcx]
0x1800acdf4  mov     rax, [rax+10h]
0x1800acdf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acdfd  nop
0x1800acdfe  mov     eax, ebx
0x1800ace00  mov     rcx, [rbp+8F0h+var_30]
0x1800ace07  xor     rcx, rsp; StackCookie
0x1800ace0a  call    __security_check_cookie
0x1800ace0f  lea     r11, [rsp+9F0h+var_20]
0x1800ace17  mov     rbx, [r11+40h]
0x1800ace1b  mov     rsi, [r11+48h]
0x1800ace1f  mov     rsp, r11
0x1800ace22  pop     r15
0x1800ace24  pop     r14
0x1800ace26  pop     r12
0x1800ace28  pop     rdi
0x1800ace29  pop     rbp
0x1800ace2a  retn
0x1800ace2b  test    r14b, r14b
0x1800ace2e  jz      loc_1800AD499
0x1800ace34  mov     [rbp+8F0h+var_770], r12d
0x1800ace3b  mov     [rbp+8F0h+var_76C], r12d
0x1800ace42  mov     [rsp+9F0h+var_990], 0FFFFFFFFh
0x1800ace4a  mov     rcx, [rbp+8F0h+var_780]
0x1800ace51  mov     rax, [rcx]
0x1800ace54  lea     rdx, [rbp+8F0h+var_770]
0x1800ace5b  mov     [rsp+9F0h+phkResult], rdx; int
0x1800ace60  lea     r9, [rbp+8F0h+var_76C]
0x1800ace67  mov     edi, 104h
0x1800ace6c  mov     r8d, edi
0x1800ace6f  lea     rdx, [rbp+8F0h+var_660]
0x1800ace76  mov     rax, [rax+20h]
0x1800ace7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace7f  mov     ebx, eax
0x1800ace81  test    eax, eax
0x1800ace83  jnz     loc_1800AD13E
0x1800ace89  mov     edx, [rbp+8F0h+var_770]
0x1800ace8f  test    dl, 1
0x1800ace92  jnz     loc_1800AD0BC
0x1800ace98  mov     rcx, [rbp+8F0h+var_780]
0x1800ace9f  mov     rax, [rcx]
0x1800acea2  lea     rdx, [rsp+9F0h+var_98C]
0x1800acea7  mov     rax, [rax+28h]
0x1800aceab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aceb0  mov     edx, [rsp+9F0h+var_98C]
0x1800aceb4  mov     ecx, 64h ; 'd'
0x1800aceb9  test    eax, eax
0x1800acebb  cmovs   edx, ecx
0x1800acebe  mov     [rsp+9F0h+var_98C], edx
0x1800acec2  movups  xmm0, xmmword ptr [rsi]
0x1800acec5  movdqu  [rsp+9F0h+var_9A8], xmm0
0x1800acecb  test    r14b, r14b
0x1800acece  jnz     loc_1800AD01F
0x1800aced4  mov     [rbp+8F0h+hkey], r12
0x1800acedb  lea     r8d, [rcx-3Dh]
0x1800acedf  lea     rdx, [rbp+8F0h+var_750]
0x1800acee6  mov     rcx, rsi
0x1800acee9  call    cs:__imp_SHStringFromGUIDW
0x1800aceef  lea     r9, [rbp+8F0h+var_750]
0x1800acef6  lea     r8, aClsidS; "CLSID\\%s"
0x1800acefd  mov     edx, 4Fh ; 'O'; unsigned __int64
0x1800acf02  lea     rcx, [rbp+8F0h+SubKey]; unsigned __int16 *
0x1800acf09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800acf0e  test    eax, eax
0x1800acf10  js      loc_1800AD00C
0x1800acf16  mov     rbx, [rbp+8F0h+hkey]
0x1800acf1d  test    rbx, rbx
0x1800acf20  jnz     loc_1800AD4B0
0x1800acf26  mov     [rbp+8F0h+hkey], r12
0x1800acf2d  lea     rax, [rbp+8F0h+hkey]
0x1800acf34  mov     [rsp+9F0h+phkResult], rax; phkResult
0x1800acf39  mov     r9d, 1; samDesired
0x1800acf3f  xor     r8d, r8d; ulOptions
0x1800acf42  lea     rdx, [rbp+8F0h+SubKey]; lpSubKey
0x1800acf49  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800acf50  call    cs:__imp_RegOpenKeyExW
0x1800acf56  test    eax, eax
0x1800acf58  js      loc_1800AD00C
0x1800acf5e  mov     [rbp+8F0h+var_778], 208h
0x1800acf68  lea     rax, [rbp+8F0h+var_778]
0x1800acf6f  mov     [rsp+9F0h+pcbData], rax; pcbData
0x1800acf74  lea     rax, [rbp+8F0h+var_240]
0x1800acf7b  mov     [rsp+9F0h+pvData], rax; pvData
0x1800acf80  mov     [rsp+9F0h+phkResult], r12; pdwType
0x1800acf85  mov     r9d, 2; dwFlags
0x1800acf8b  xor     r8d, r8d; lpValue
0x1800acf8e  xor     edx, edx; lpSubKey
0x1800acf90  mov     rcx, [rbp+8F0h+hkey]; hkey
0x1800acf97  call    cs:__imp_RegGetValueW
0x1800acf9d  test    eax, eax
0x1800acf9f  jnz     loc_1800AD0A2
0x1800acfa5  mov     [rbp+8F0h+var_778], 208h
0x1800acfaf  lea     rax, [rbp+8F0h+var_778]
0x1800acfb6  mov     [rsp+9F0h+pcbData], rax; pcbData
0x1800acfbb  lea     rax, [rbp+8F0h+var_450]
0x1800acfc2  mov     [rsp+9F0h+pvData], rax; pvData
0x1800acfc7  mov     [rsp+9F0h+phkResult], r12; pdwType
0x1800acfcc  mov     r9d, 2; dwFlags
0x1800acfd2  xor     r8d, r8d; lpValue
0x1800acfd5  lea     rdx, aInprocserver32; "InProcServer32"
0x1800acfdc  mov     rcx, [rbp+8F0h+hkey]; hkey
0x1800acfe3  call    cs:__imp_RegGetValueW
0x1800acfe9  test    eax, eax
0x1800acfeb  jnz     loc_1800AD0AF
0x1800acff1  lea     r8, [rbp+8F0h+var_660]; unsigned __int16 *
0x1800acff8  lea     rdx, [rbp+8F0h+var_450]; unsigned __int16 *
0x1800acfff  lea     rcx, [rbp+8F0h+var_240]; unsigned __int16 *
0x1800ad006  call    ?IconOverlayHandlersAggregate@FileExplorerAggregateTelemetry@@SAXPEBG00@Z; FileExplorerAggregateTelemetry::IconOverlayHandlersAggregate(ushort const *,ushort const *,ushort const *)
0x1800ad00b  nop
0x1800ad00c  mov     rcx, [rbp+8F0h+hkey]; hKey
0x1800ad013  test    rcx, rcx
0x1800ad016  jz      short loc_1800AD01F
0x1800ad018  call    cs:__imp_RegCloseKey
0x1800ad01e  nop
0x1800ad01f  mov     rax, [rbp+8F0h+var_780]
0x1800ad026  mov     [rbp+8F0h+var_780], r12
0x1800ad02d  mov     [rsp+9F0h+pitem], rax
0x1800ad032  lea     r8, [rsp+9F0h+pitem]; pitem
0x1800ad037  mov     edx, 7FFFFFFFh; i
0x1800ad03c  mov     rcx, [r15]; hdsa
0x1800ad03f  call    DSA_InsertItem
0x1800ad044  nop
0x1800ad045  mov     rcx, [rbp+8F0h+var_780]
0x1800ad04c  test    rcx, rcx
0x1800ad04f  jz      short loc_1800AD065
0x1800ad051  mov     [rbp+8F0h+var_780], r12
0x1800ad058  mov     rax, [rcx]
0x1800ad05b  mov     rax, [rax+10h]
0x1800ad05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad064  nop
0x1800ad065  xor     eax, eax
0x1800ad067  jmp     loc_1800ACE00
0x1800ad06c  lea     r8, [rbp+8F0h+var_780]; void **
0x1800ad073  mov     rcx, rsi; struct _GUID *
0x1800ad076  call    ?ActivateHandlerInHost@@YAJAEBU_GUID@@0PEAPEAX@Z; ActivateHandlerInHost(_GUID const &,_GUID const &,void * *)
0x1800ad07b  jmp     loc_1800ACDD8
0x1800ad080  mov     [rsp+9F0h+pvData], rax
0x1800ad085  mov     [rsp+9F0h+phkResult], r9
0x1800ad08a  xor     edx, edx
0x1800ad08c  lea     r9d, [rdx+2]
0x1800ad090  lea     r8d, [rdx+4]
0x1800ad094  mov     rcx, rsi
0x1800ad097  call    cs:__imp_SHExtCoCreateInstance
0x1800ad09d  jmp     loc_1800ACDD8
0x1800ad0a2  mov     [rbp+8F0h+var_240], r12w
0x1800ad0aa  jmp     loc_1800ACFA5
0x1800ad0af  mov     [rbp+8F0h+var_450], r12w
0x1800ad0b7  jmp     loc_1800ACFF1
0x1800ad0bc  mov     eax, 7FFFFFFEh
0x1800ad0c1  lea     rcx, [rbp+8F0h+var_660]
0x1800ad0c8  lea     r8, [rsp+9F0h+pszIconFile]
0x1800ad0cd  test    rax, rax
0x1800ad0d0  jz      short loc_1800AD0F1
0x1800ad0d2  movzx   r9d, word ptr [rcx]
0x1800ad0d6  test    r9w, r9w
0x1800ad0da  jz      short loc_1800AD0F1
0x1800ad0dc  add     rcx, 2
0x1800ad0e0  mov     [r8], r9w
0x1800ad0e4  add     r8, 2
0x1800ad0e8  dec     rax
0x1800ad0eb  sub     rdi, 1
0x1800ad0ef  jnz     short loc_1800AD0CD
0x1800ad0f1  mov     rax, rdi
0x1800ad0f4  neg     rax
0x1800ad0f7  sbb     r9d, r9d
0x1800ad0fa  not     r9d
0x1800ad0fd  and     r9d, 8007007Ah; char *
0x1800ad104  lea     rcx, [r8-2]
0x1800ad108  test    rdi, rdi
0x1800ad10b  cmovnz  rcx, r8
0x1800ad10f  mov     [rcx], r12w
0x1800ad113  mov     rcx, [rbp+8F8h]; this
0x1800ad11a  jz      loc_1800AD325
0x1800ad120  mov     [rsp+9F0h+var_994], 0FFFFFFFFh
0x1800ad128  and     dl, 2
0x1800ad12b  neg     dl
0x1800ad12d  sbb     eax, eax
0x1800ad12f  and     eax, [rbp+8F0h+var_76C]
0x1800ad135  mov     [rsp+9F0h+var_998], eax
0x1800ad139  jmp     loc_1800ACE98
0x1800ad13e  test    r14b, r14b
0x1800ad141  jz      short loc_1800AD18C
0x1800ad143  test    ebx, ebx
0x1800ad145  jns     loc_1800AD01F
0x1800ad14b  mov     rcx, [rbp+8F8h]; this
0x1800ad152  mov     r9d, ebx; char *
0x1800ad155  lea     r8, aShellShell32Ov; "shell\\shell32\\ovrlaymn.cpp"
0x1800ad15c  mov     edx, 337h; void *
0x1800ad161  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad166  nop
0x1800ad167  mov     rcx, [rbp+8F0h+var_780]
0x1800ad16e  test    rcx, rcx
0x1800ad171  jz      short loc_1800AD187
0x1800ad173  mov     [rbp+8F0h+var_780], r12
0x1800ad17a  mov     rax, [rcx]
0x1800ad17d  mov     rax, [rax+10h]
0x1800ad181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad186  nop
0x1800ad187  jmp     loc_1800ACDFE
0x1800ad18c  mov     [rbp+8F0h+hkey], r12
0x1800ad193  mov     [rsp+9F0h+var_994], 0FFFFFFFFh
0x1800ad19b  mov     r8d, 27h ; '''
0x1800ad1a1  lea     rdx, [rbp+8F0h+var_750]
0x1800ad1a8  mov     rcx, rsi
0x1800ad1ab  call    cs:__imp_SHStringFromGUIDW
0x1800ad1b1  lea     r9, [rbp+8F0h+var_750]
0x1800ad1b8  lea     r8, aClsidS; "CLSID\\%s"
0x1800ad1bf  mov     edx, 4Fh ; 'O'; unsigned __int64
0x1800ad1c4  lea     rcx, [rbp+8F0h+SubKey]; unsigned __int16 *
0x1800ad1cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad1d0  mov     ebx, eax
0x1800ad1d2  test    eax, eax
0x1800ad1d4  js      loc_1800AD387
0x1800ad1da  mov     rbx, [rbp+8F0h+hkey]
0x1800ad1e1  test    rbx, rbx
0x1800ad1e4  jnz     loc_1800AD4D7
0x1800ad1ea  mov     [rbp+8F0h+hkey], r12
0x1800ad1f1  lea     rax, [rbp+8F0h+hkey]
0x1800ad1f8  mov     [rsp+9F0h+phkResult], rax; unsigned int
0x1800ad1fd  mov     r9d, 1; samDesired
0x1800ad203  xor     r8d, r8d; ulOptions
0x1800ad206  lea     rdx, [rbp+8F0h+SubKey]; lpSubKey
0x1800ad20d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800ad214  call    cs:__imp_RegOpenKeyExW
0x1800ad21a  test    eax, eax
0x1800ad21c  jz      short loc_1800AD273
0x1800ad21e  mov     rcx, [rbp+8F8h]; this
0x1800ad225  mov     r9d, eax; char *
0x1800ad228  lea     r8, aShellShell32Ov; "shell\\shell32\\ovrlaymn.cpp"
0x1800ad22f  mov     edx, 32Ch; void *
0x1800ad234  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ad239  mov     ebx, eax
0x1800ad23b  mov     rcx, [rbp+8F0h+hkey]; hKey
0x1800ad242  test    rcx, rcx
0x1800ad245  jz      short loc_1800AD24E
0x1800ad247  call    cs:__imp_RegCloseKey
0x1800ad24d  nop
0x1800ad24e  mov     rcx, [rbp+8F0h+var_780]
0x1800ad255  test    rcx, rcx
0x1800ad258  jz      short loc_1800AD26E
0x1800ad25a  mov     [rbp+8F0h+var_780], r12
0x1800ad261  mov     rax, [rcx]
0x1800ad264  mov     rax, [rax+10h]
0x1800ad268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad26d  nop
0x1800ad26e  jmp     loc_1800ACDFE
0x1800ad273  mov     [rbp+8F0h+var_778], 208h
0x1800ad27d  lea     rax, [rbp+8F0h+var_778]
0x1800ad284  mov     [rsp+9F0h+pcbData], rax; pcbData
0x1800ad289  lea     rax, [rsp+9F0h+pszIconFile]
0x1800ad28e  mov     [rsp+9F0h+pvData], rax; pvData
0x1800ad293  mov     [rsp+9F0h+phkResult], r12; int
0x1800ad298  mov     r9d, 2; dwFlags
0x1800ad29e  lea     r8, c_szDefaultIcon; "DefaultIcon"
0x1800ad2a5  xor     edx, edx; lpSubKey
0x1800ad2a7  mov     rcx, [rbp+8F0h+hkey]; hkey
0x1800ad2ae  call    cs:__imp_RegGetValueW
0x1800ad2b4  mov     ebx, eax
  ... truncated ...
```
