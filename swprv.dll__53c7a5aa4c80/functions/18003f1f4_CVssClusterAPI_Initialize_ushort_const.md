# CVssClusterAPI::Initialize(ushort const *)

- ea: `0x18003f1f4`
- end: `0x18003f525`
- name: `?Initialize@CVssClusterAPI@@QEAA_NPEBG@Z`
- size: `817`
- prototype: `char __fastcall(CVssClusterAPI *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027ca0`
- `0x180028aa0`
- `0x18002d1f0`

## callees

- `0x180001580`
- `0x18000212c`
- `0x18001febc`
- `0x18002e79c`
- `0x1800332c0`
- `0x1800336cc`
- `0x180033a8c`
- `0x180033c78`
- `0x180033da4`
- `0x1800367b8`
- `0x1800377c4`
- `0x180037e24`
- `0x180039718`
- `0x18003a05c`
- `0x18003f1f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f393`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003f417`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003f417`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x18003f380`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x18003f380`

## string_xrefs

- `0x18003f3ea`: `OpenCluster(%s) [0x%08lx]`
- `0x18003f469`: `GetWindowsDirectory failed.`
- `0x18003f499`: `\system32\RESUTILS.DLL`
- `0x18003f2df`: `SYSTEM\CurrentControlSet\Services\VSS\Settings`

## pseudocode

```c
char __fastcall CVssClusterAPI::Initialize(CVssClusterAPI *this, const unsigned __int16 *a2)
{
  char v3; // r9
  char v4; // r9
  HCLUSTER v5; // rax
  DWORD LastError; // ebx
  char v7; // dl
  __int64 v8; // rax
  __int64 v9; // rax
  char v10; // bl
  DWORD v12; // [rsp+20h] [rbp-3E8h]
  unsigned int v13; // [rsp+40h] [rbp-3C8h] BYREF
  CVssClusterAPI *v14; // [rsp+48h] [rbp-3C0h]
  CVssClusterAPI *v15; // [rsp+50h] [rbp-3B8h]
  unsigned int v16; // [rsp+58h] [rbp-3B0h] BYREF
  const unsigned __int16 *v17; // [rsp+60h] [rbp-3A8h] BYREF
  const unsigned __int16 *v18; // [rsp+68h] [rbp-3A0h]
  const unsigned __int16 *v19; // [rsp+70h] [rbp-398h]
  int v20; // [rsp+78h] [rbp-390h]
  int v21; // [rsp+7Ch] [rbp-38Ch]
  int v22; // [rsp+80h] [rbp-388h]
  _BYTE v23[120]; // [rsp+88h] [rbp-380h] BYREF
  int v24; // [rsp+100h] [rbp-308h]
  LPVOID v25[4]; // [rsp+110h] [rbp-2F8h] BYREF
  unsigned int v26; // [rsp+134h] [rbp-2D4h]
  _com_error *v27; // [rsp+180h] [rbp-288h] BYREF
  const std::exception *v28; // [rsp+188h] [rbp-280h] BYREF
  HKEY v29[4]; // [rsp+190h] [rbp-278h] BYREF
  _QWORD v30[4]; // [rsp+1B0h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+1D0h] [rbp-238h] BYREF

  v14 = this;
  v15 = this;
  v17 = L"base\\stor\\vss\\modules\\cluster\\cluster.cxx";
  v18 = L"CVssClusterAPI::Initialize";
  v19 = L"CLUCLUSC";
  v20 = 129;
  v21 = 11;
  v22 = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v25, (__int64)&v17, 0);
  memset_0(Buffer, 0, 0x208u);
  try
  {
    v29[3] = 0;
    v29[2] = (HKEY)&CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v29[1] = 0;
    v29[0] = (HKEY)131097;
    if ( CVssRegistryKey::Open(
           (CVssRegistryKey *)v29,
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Settings") )
    {
      v13 = 0;
      if ( CVssRegistryKey::GetValue(v29, L"ClusterOnlineTimeout", &v13, v3) )
        *((_DWORD *)this + 3) = v13;
      v13 = 0;
      if ( CVssRegistryKey::GetValue(v29, L"ClusterOfflineTimeout", &v13, v4) )
        *((_DWORD *)v15 + 2) = v13;
    }
    CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)v29);
  }
  catch ( long v16 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)v25,
      v16,
      L"base\\stor\\vss\\modules\\cluster\\cluster.cxx",
      L"CLUCLUSC",
      L"CVssClusterAPI::Initialize",
      0x96u,
      v26);
  }
  catch ( _com_error *v27 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)v25,
      v27,
      L"base\\stor\\vss\\modules\\cluster\\cluster.cxx",
      L"CLUCLUSC",
      L"CVssClusterAPI::Initialize",
      0x96u,
      v26);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)v25,
      L"base\\stor\\vss\\modules\\cluster\\cluster.cxx",
      L"CLUCLUSC",
      L"CVssClusterAPI::Initialize",
      0x96u,
      v26);
  }
  catch ( const std::exception *v28 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)v25,
      v28,
      L"base\\stor\\vss\\modules\\cluster\\cluster.cxx",
      L"CLUCLUSC",
      L"CVssClusterAPI::Initialize",
      0x96u,
      v26);
  }
  v29[3] = 0;
  v29[2] = (HKEY)&CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v29[1] = 0;
  v29[0] = (HKEY)131097;
  if ( CVssRegistryKey::Open(
         (CVssRegistryKey *)v29,
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Settings") )
  {
    v13 = 0;
    if ( CVssRegistryKey::GetValue(v29, L"ClusterOnlineTimeout", &v13, v3) )
      *((_DWORD *)this + 3) = v13;
    v13 = 0;
    if ( CVssRegistryKey::GetValue(v29, L"ClusterOfflineTimeout", &v13, v4) )
      *((_DWORD *)v15 + 2) = v13;
  }
  CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)v29);
}

```

## disassembly

```asm
0x18003f1f4  mov     [rsp+arg_8], rbx
0x18003f1f9  mov     [rsp+arg_10], rsi
0x18003f1fe  push    rdi
0x18003f1ff  push    r14
0x18003f201  push    r15
0x18003f203  sub     rsp, 3F0h
0x18003f20a  mov     rax, cs:__security_cookie
0x18003f211  xor     rax, rsp
0x18003f214  mov     [rsp+408h+var_28], rax
0x18003f21c  mov     rbx, rcx
0x18003f21f  mov     [rsp+408h+var_3C0], rcx
0x18003f224  mov     [rsp+408h+var_3B8], rcx
0x18003f229  lea     rsi, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003f230  mov     [rsp+408h+var_3A8], rsi
0x18003f235  lea     r14, aCvssclusterapi_0; "CVssClusterAPI::Initialize"
0x18003f23c  mov     [rsp+408h+var_3A0], r14
0x18003f241  lea     r15, aCluclusc; "CLUCLUSC"
0x18003f248  mov     [rsp+408h+var_398], r15
0x18003f24d  mov     [rsp+408h+var_390], 81h
0x18003f255  mov     [rsp+408h+var_38C], 0Bh
0x18003f25d  mov     [rsp+408h+var_388], 0FFh
0x18003f268  xor     edi, edi
0x18003f26a  mov     [rsp+408h+var_308], 1000000h
0x18003f275  xor     edx, edx; Val
0x18003f277  lea     r8d, [rdi+78h]; Size
0x18003f27b  lea     rcx, [rsp+408h+var_380]; void *
0x18003f283  call    memset_0
0x18003f288  xor     r8d, r8d
0x18003f28b  lea     rdx, [rsp+408h+var_3A8]
0x18003f290  lea     rcx, [rsp+408h+var_2F8]
0x18003f298  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003f29d  nop
0x18003f29e  xor     edx, edx; Val
0x18003f2a0  mov     r8d, 208h; Size
0x18003f2a6  lea     rcx, [rsp+408h+Buffer]; void *
0x18003f2ae  call    memset_0
0x18003f2b3  nop
0x18003f2b4  mov     [rsp+408h+var_260], rdi
0x18003f2bc  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18003f2c3  mov     [rsp+408h+var_268], rax
0x18003f2cb  mov     [rsp+408h+var_270], rdi
0x18003f2d3  mov     [rsp+408h+var_278], 20019h
0x18003f2df  lea     r8, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x18003f2e6  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18003f2ed  lea     rcx, [rsp+408h+var_278]; this
0x18003f2f5  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18003f2fa  test    al, al
0x18003f2fc  jz      short loc_18003F353
0x18003f2fe  mov     [rsp+408h+var_3C8], edi
0x18003f302  lea     r8, [rsp+408h+var_3C8]; unsigned int *
0x18003f307  lea     rdx, aClusteronlinet; "ClusterOnlineTimeout"
0x18003f30e  lea     rcx, [rsp+408h+var_278]; this
0x18003f316  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z; CVssRegistryKey::GetValue(ushort const *,ulong &,bool)
0x18003f31b  test    al, al
0x18003f31d  jz      short loc_18003F326
0x18003f31f  mov     eax, [rsp+408h+var_3C8]
0x18003f323  mov     [rbx+0Ch], eax
0x18003f326  mov     [rsp+408h+var_3C8], edi
0x18003f32a  lea     r8, [rsp+408h+var_3C8]; unsigned int *
0x18003f32f  lea     rdx, aClusteroffline; "ClusterOfflineTimeout"
0x18003f336  lea     rcx, [rsp+408h+var_278]; this
0x18003f33e  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z; CVssRegistryKey::GetValue(ushort const *,ulong &,bool)
0x18003f343  test    al, al
0x18003f345  jz      short loc_18003F353
0x18003f347  mov     rcx, [rsp+408h+var_3B8]
0x18003f34c  mov     eax, [rsp+408h+var_3C8]
0x18003f350  mov     [rcx+8], eax
0x18003f353  lea     rcx, [rsp+408h+var_278]; this
0x18003f35b  call    ??1CVssRegistryKey@@QEAA@XZ; CVssRegistryKey::~CVssRegistryKey(void)
0x18003f360  nop
0x18003f361  jmp     short loc_18003F37E
0x18003f363  jmp     short loc_18003F369
0x18003f365  jmp     short loc_18003F369
0x18003f367  jmp     short $+2
0x18003f369  lea     r15, aCluclusc; "CLUCLUSC"
0x18003f370  lea     r14, aCvssclusterapi_0; "CVssClusterAPI::Initialize"
0x18003f377  lea     rsi, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\cluster\\clus"...
0x18003f37e  xor     ecx, ecx; lpszClusterName
0x18003f380  call    cs:__imp_OpenCluster
0x18003f386  mov     rcx, [rsp+408h+var_3C0]
0x18003f38b  mov     [rcx], rax
0x18003f38e  test    rax, rax
0x18003f391  jnz     short loc_18003F40A
0x18003f393  call    cs:__imp_GetLastError
0x18003f399  mov     ebx, eax
0x18003f39b  mov     [rsp+408h+var_3A8], rsi
0x18003f3a0  mov     [rsp+408h+var_3A0], r14
0x18003f3a5  mov     [rsp+408h+var_398], r15
0x18003f3aa  mov     [rsp+408h+var_390], 9Ch
0x18003f3b2  mov     [rsp+408h+var_38C], 0Bh
0x18003f3ba  mov     [rsp+408h+var_388], 0FFh
0x18003f3c5  mov     [rsp+408h+var_308], 1000000h
0x18003f3d0  xor     edx, edx; Val
0x18003f3d2  lea     r8d, [rdx+78h]; Size
0x18003f3d6  lea     rcx, [rsp+408h+var_380]; void *
0x18003f3de  call    memset_0
0x18003f3e3  mov     [rsp+408h+var_3E8], ebx
0x18003f3e7  xor     r9d, r9d
0x18003f3ea  lea     r8, aOpenclusterS0x; "OpenCluster(%s) [0x%08lx]"
0x18003f3f1  lea     rdx, [rsp+408h+var_3A8]
0x18003f3f6  lea     rcx, [rsp+408h+var_2F8]
0x18003f3fe  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003f403  xor     edx, edx
0x18003f405  jmp     loc_18003F4DE
0x18003f40a  mov     edx, 104h; uSize
0x18003f40f  lea     rcx, [rsp+408h+Buffer]; lpBuffer
0x18003f417  call    cs:__imp_GetWindowsDirectoryW
0x18003f41d  test    eax, eax
0x18003f41f  jnz     short loc_18003F483
0x18003f421  mov     [rsp+408h+var_3A8], rsi
0x18003f426  mov     [rsp+408h+var_3A0], r14
0x18003f42b  mov     [rsp+408h+var_398], r15
0x18003f430  mov     [rsp+408h+var_390], 0A2h
0x18003f438  mov     [rsp+408h+var_38C], 0Bh
0x18003f440  mov     [rsp+408h+var_388], 0FFh
0x18003f44b  mov     [rsp+408h+var_308], 1000000h
0x18003f456  xor     edx, edx; Val
0x18003f458  lea     r8d, [rax+78h]; Size
0x18003f45c  lea     rcx, [rsp+408h+var_380]; void *
0x18003f464  call    memset_0
0x18003f469  lea     r8, aGetwindowsdire; "GetWindowsDirectory failed."
0x18003f470  lea     rdx, [rsp+408h+var_3A8]
0x18003f475  lea     rcx, [rsp+408h+var_2F8]
0x18003f47d  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x18003f483  lea     rdx, [rsp+408h+Buffer]
0x18003f48b  lea     rcx, [rsp+408h+var_258]
0x18003f493  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003f498  nop
0x18003f499  lea     r8, aSystem32Resuti; "\\system32\\RESUTILS.DLL"
0x18003f4a0  mov     rdx, rax
0x18003f4a3  lea     rcx, [rsp+408h+var_278]
0x18003f4ab  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003f4b0  mov     rcx, [rsp+408h+var_3B8]
0x18003f4b5  add     rcx, 10h
0x18003f4b9  mov     rdx, rax
0x18003f4bc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003f4c1  lea     rcx, [rsp+408h+var_278]
0x18003f4c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f4ce  nop
0x18003f4cf  lea     rcx, [rsp+408h+var_258]
0x18003f4d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f4dc  mov     dl, 1; bool
0x18003f4de  lea     rcx, [rsp+408h+var_2F8]; this
0x18003f4e6  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x18003f4eb  mov     bl, al
0x18003f4ed  lea     rcx, [rsp+408h+var_2F8]; this
0x18003f4f5  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003f4fa  mov     al, bl
0x18003f4fc  mov     rcx, [rsp+408h+var_28]
0x18003f504  xor     rcx, rsp; StackCookie
0x18003f507  call    __security_check_cookie
0x18003f50c  lea     r11, [rsp+408h+var_18]
0x18003f514  mov     rbx, [r11+28h]
0x18003f518  mov     rsi, [r11+30h]
0x18003f51c  mov     rsp, r11
0x18003f51f  pop     r15
0x18003f521  pop     r14
0x18003f523  pop     rdi
0x18003f524  retn
```
