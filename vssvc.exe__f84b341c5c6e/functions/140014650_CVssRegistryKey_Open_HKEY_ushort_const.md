# CVssRegistryKey::Open(HKEY__ *,ushort const *,...)

- ea: `0x140014650`
- end: `0x140014fe5`
- name: `?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ`
- size: `2453`
- prototype: `bool(CVssRegistryKey *__hidden this, HKEY, const unsigned __int16 *, ...)`
- caller_count: `13`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c84c`
- `0x14000fba0`
- `0x140015fb0`
- `0x140027cb0`
- `0x140028d60`
- `0x14002b160`
- `0x140042688`
- `0x140055bec`
- `0x1400965c0`
- `0x14009b4ac`
- `0x1400a57d4`
- `0x1400b7c08`
- `0x1400bf05c`

## callees

- `0x1400137c0`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140014650`
- `0x14003b4ec`
- `0x140049ec4`
- `0x140091560`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400921f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014836`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014836`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400149a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014edd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400149a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014edd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140014713`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400148f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140014a00`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140014bb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140014713`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400148f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140014a00`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140014bb9`
- `VssTrace!__imp_VssTraceMessage` at `0x140014ec5`
- `VssTrace!__imp_VssTraceMessage` at `0x140014f1d`
- `VssTrace!__imp_VssTraceMessage` at `0x140014ec5`
- `VssTrace!__imp_VssTraceMessage` at `0x140014f1d`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140014ab9`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140014c76`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140014cca`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140014cea`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140014ab9`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140014c76`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140014cca`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140014cea`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001474e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001492e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001474e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001492e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140014af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140014af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400149cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400149da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400149e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400149f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014b85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014b93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014ba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014ca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014d11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400149cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400149da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400149e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400149f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014b85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014b93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014ba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014ca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014d11`

## string_xrefs

- `0x14001468c`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140014697`: `CVssRegistryKey::Open`
- `0x140014d33`: `CVssRegistryKey::Open`
- `0x140014e12`: `CVssRegistryKey::Open`
- `0x140014856`: `CVssRegistryKey::Close`
- `0x140014e7b`: `RegOpenKeyExW(%ld,%s,...)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char CVssRegistryKey::Open(REGSAM *this, HKEY a2, const unsigned __int16 *a3, ...)
{
  _DWORD *v5; // rax
  unsigned int v6; // r15d
  unsigned int v7; // ebx
  __int64 i; // rbx
  void *v9; // rcx
  unsigned int v10; // eax
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  _DWORD *v13; // rax
  int v14; // ebx
  __int64 j; // rbx
  void *v16; // rcx
  HKEY v17; // rcx
  LSTATUS v18; // ebx
  void *v19; // rcx
  DWORD v20; // edi
  unsigned int v21; // r8d
  __int64 v22; // rbx
  void *v23; // rcx
  wchar_t *v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // r8
  wchar_t *v27; // r9
  wchar_t v28; // dx
  wchar_t *v29; // rdx
  DWORD v30; // r14d
  __int16 v32; // ax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+28h] [rbp-D8h]
  __int64 v36; // [rsp+28h] [rbp-D8h]
  __int64 v37; // [rsp+30h] [rbp-D0h]
  __int64 v38; // [rsp+30h] [rbp-D0h]
  __int64 v39; // [rsp+38h] [rbp-C8h]
  __int64 v40; // [rsp+38h] [rbp-C8h]
  __int64 v41; // [rsp+40h] [rbp-C0h]
  __int64 v42; // [rsp+40h] [rbp-C0h]
  __int64 v43; // [rsp+48h] [rbp-B8h]
  _DWORD *pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  void **v45; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  int v48; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v49; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v50; // [rsp+88h] [rbp-78h]
  unsigned int v51; // [rsp+90h] [rbp-70h]
  unsigned int v52; // [rsp+94h] [rbp-6Ch]
  const wchar_t *v53; // [rsp+98h] [rbp-68h]
  unsigned int v54; // [rsp+A0h] [rbp-60h]
  DWORD TickCount; // [rsp+A4h] [rbp-5Ch]
  unsigned int v56; // [rsp+A8h] [rbp-58h]
  LPVOID v57[2]; // [rsp+B0h] [rbp-50h]
  LPVOID v58[2]; // [rsp+C0h] [rbp-40h]
  _DWORD *v59; // [rsp+D0h] [rbp-30h]
  const unsigned __int16 *v60; // [rsp+E0h] [rbp-20h] BYREF
  const wchar_t *v61; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v62; // [rsp+F0h] [rbp-10h]
  __int64 v63; // [rsp+F8h] [rbp-8h]
  unsigned int v64; // [rsp+100h] [rbp+0h]
  unsigned int v65; // [rsp+104h] [rbp+4h]
  LPVOID v66[2]; // [rsp+108h] [rbp+8h]
  LPVOID pv[6]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v68; // [rsp+148h] [rbp+48h]
  __int128 v69; // [rsp+158h] [rbp+58h]
  __int128 v70; // [rsp+168h] [rbp+68h]
  __int64 v71; // [rsp+178h] [rbp+78h]
  int v72; // [rsp+180h] [rbp+80h]
  const unsigned __int16 *v73; // [rsp+190h] [rbp+90h] BYREF
  const wchar_t *v74; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v75; // [rsp+1A0h] [rbp+A0h]
  int v76; // [rsp+1A8h] [rbp+A8h]
  int v77; // [rsp+1ACh] [rbp+ACh]
  int v78; // [rsp+1B0h] [rbp+B0h]
  LPVOID v79[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v80; // [rsp+1C8h] [rbp+C8h]
  __int128 v81; // [rsp+1D8h] [rbp+D8h]
  __int128 v82; // [rsp+1E8h] [rbp+E8h]
  __int128 v83; // [rsp+1F8h] [rbp+F8h]
  __int128 v84; // [rsp+208h] [rbp+108h]
  __int128 v85; // [rsp+218h] [rbp+118h]
  __int64 v86; // [rsp+228h] [rbp+128h]
  int v87; // [rsp+230h] [rbp+130h]
  wchar_t Buffer[259]; // [rsp+240h] [rbp+140h] BYREF
  __int16 v89; // [rsp+446h] [rbp+346h]
  va_list Args; // [rsp+4C8h] [rbp+3C8h] BYREF

  va_start(Args, a3);
  v60 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v61 = L"CVssRegistryKey::Open";
  v62 = L"REGREGSC";
  v63 = 0xB0000007FLL;
  v64 = 255;
  v72 = 0x1000000;
  *(_OWORD *)v66 = 0;
  memset(pv, 0, sizeof(pv));
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v48 = 0;
  v53 = L"CVssRegistryKey::Open";
  v49 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v50 = L"REGREGSC";
  v51 = 127;
  v52 = 11;
  TickCount = GetTickCount();
  v56 = 255;
  v47 = 0xFFFFFFFF00000000uLL;
  v59 = 0;
  *(_OWORD *)v57 = 0;
  *(_OWORD *)v58 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(&v47) < 0 )
  {
    v5 = v59;
  }
  else
  {
    v5 = pExceptionObject;
    v59 = pExceptionObject;
  }
  if ( v5 )
    v54 = v5[12] + 1;
  else
    v54 = 0;
  v6 = 160;
  v7 = 160;
  if ( v56 != 255 )
    v7 = v56;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v47, v52) )
    VssTraceMessage(v49, v50, v51, v54, v52, v53, L"ENTER", v7, 0);
  for ( i = 0; i != 15; ++i )
  {
    v9 = v66[i];
    if ( v9 )
    {
      CoTaskMemFree(v9);
      v66[i] = 0;
    }
  }
  pExceptionObject = 0;
  v10 = vsnwprintf(Buffer, 0x103u, a3, Args);
  if ( v10 >= 0x104 )
  {
    v89 = 0;
    v48 = -2147024774;
    v73 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v74 = L"CVssRegistryKey::Open";
    v75 = L"REGREGSC";
    v76 = 139;
    v77 = 11;
    v78 = 255;
    v87 = 0x1000000;
    memset_0(v79, 0, 0x78u);
    v32 = 15;
    do
      --v32;
    while ( v32 );
    CVssFunctionTracer::TranslateGenericError(&v47, &v73, 2147942522LL, L"StringCchVPrintfW()");
  }
  if ( v10 == 259 )
    v89 = 0;
  v48 = 0;
  v45 = &CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable';
  hKey = 0;
  v11 = RegOpenKeyExW(a2, Buffer, 0, *this, &hKey);
  v12 = v11;
  if ( v11 != 2 )
  {
    if ( v11 )
    {
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      v73 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v74 = L"CVssRegistryKey::Open";
      v75 = L"REGREGSC";
      v76 = 154;
      v77 = 11;
      v78 = 255;
      v87 = 0x1000000;
      memset_0(v79, 0, 0x78u);
      CVssFunctionTracer::TranslateGenericError(&v47, &v73, v12, L"RegOpenKeyExW(%ld,%s,...)", a2, Buffer);
    }
    v73 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v74 = L"CVssRegistryKey::Close";
    v75 = L"REGREGSC";
    v76 = 668;
    v77 = 11;
    v78 = 255;
    v87 = 0x1000000;
    *(_OWORD *)v79 = 0;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    v83 = 0;
    v84 = 0;
    v85 = 0;
    v86 = 0;
    LODWORD(v61) = 0;
    v66[0] = L"CVssRegistryKey::Close";
    v62 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v63 = (__int64)L"REGREGSC";
    v64 = 668;
    v65 = 11;
    HIDWORD(v66[1]) = GetTickCount();
    LODWORD(pv[0]) = 255;
    v60 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
    memset(&pv[1], 0, 40);
    pExceptionObject = 0;
    if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(&v60) < 0 )
    {
      v13 = pv[5];
    }
    else
    {
      v13 = pExceptionObject;
      pv[5] = pExceptionObject;
    }
    if ( v13 )
      LODWORD(v66[1]) = v13[12] + 1;
    else
      LODWORD(v66[1]) = 0;
    v14 = 160;
    if ( LODWORD(pv[0]) != 255 )
      v14 = (int)pv[0];
    if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v60, v65) )
      VssTraceMessage(v62, v63, v64, LODWORD(v66[1]), v65, v66[0], L"ENTER", v14, 0);
    for ( j = 0; j != 15; ++j )
    {
      v16 = v79[j];
      if ( v16 )
      {
        CoTaskMemFree(v16);
        v79[j] = 0;
      }
    }
    v17 = (HKEY)*((_QWORD *)this + 1);
    if ( v17 )
    {
      v18 = RegCloseKey(v17);
      if ( v18 )
      {
        v73 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
        v74 = L"CVssRegistryKey::Close";
        v75 = L"REGREGSC";
        v76 = 675;
        v77 = 11;
        v78 = 255;
        v87 = 0x1000000;
        memset_0(v79, 0, 0x78u);
        LODWORD(phkResult) = v18;
        CVssFunctionTracer::Trace(
          &v60,
          &v73,
          L"Error on closing key with name %s. lRes == 0x%08lx",
          *((_QWORD *)this + 3),
          phkResult);
      }
      *((_QWORD *)this + 1) = 0;
    }
    v19 = (void *)*((_QWORD *)this + 3);
    if ( v19 )
      CoTaskMemFree(v19);
    *((_QWORD *)this + 3) = 0;
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
    CoTaskMemFree(pv[2]);
    pv[2] = 0;
    CoTaskMemFree(pv[3]);
    pv[3] = 0;
    CoTaskMemFree(pv[4]);
    pv[4] = 0;
    v20 = GetTickCount() - HIDWORD(v66[1]);
    v21 = 160;
    if ( LODWORD(pv[0]) != 255 )
      v21 = (unsigned int)pv[0];
    LODWORD(v41) = v20;
    LODWORD(v39) = v20 % 0x3E8;
    LODWORD(v37) = v20 / 0x3E8 % 0x3C;
    LODWORD(v35) = v20 / 0xEA60 % 0x3C;
    LODWORD(phkResult) = v20 / 0x36EE80 % 0x3C;
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v60,
      L"EXIT",
      v21,
      L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
      phkResult,
      v35,
      v37,
      v39,
      v41,
      (_DWORD)v61);
    VssSetTracingContextPerThread(pv[5]);
    v22 = -1;
    do
      ++v22;
    while ( Buffer[v22] );
    v23 = (void *)*((_QWORD *)this + 3);
    if ( v23 )
      CoTaskMemFree(v23);
    *((_QWORD *)this + 3) = 0;
    v24 = (wchar_t *)CoTaskMemAlloc(2 * v22 + 2);
    *((_QWORD *)this + 3) = v24;
    if ( !v24 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v25 = v22 + 1;
    if ( v22 != -1 )
    {
      if ( v25 > 0x7FFFFFFF )
      {
        *v24 = 0;
      }
      else
      {
        v26 = 2147483646;
        v27 = Buffer;
        do
        {
          if ( !v26 )
            break;
          v28 = *v27;
          if ( !*v27 )
            break;
          ++v27;
          *v24++ = v28;
          --v26;
          --v25;
        }
        while ( v25 );
        v29 = v24 - 1;
        if ( v25 )
          v29 = v24;
        *v29 = 0;
        if ( v25 )
        {
          *((_QWORD *)this + 1) = hKey;
          hKey = 0;
          v45 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
          CoTaskMemFree(v57[0]);
          v57[0] = 0;
          CoTaskMemFree(v57[1]);
          v57[1] = 0;
          CoTaskMemFree(v58[0]);
          v58[0] = 0;
          CoTaskMemFree(v58[1]);
          v58[1] = 0;
          v30 = GetTickCount() - TickCount;
          if ( v56 != 255 )
            v6 = v56;
          LODWORD(v43) = v48;
          LODWORD(v42) = v30;
          LODWORD(v40) = v30 % 0x3E8;
          LODWORD(v38) = v30 / 0x3E8 % 0x3C;
          LODWORD(v36) = v30 / 0xEA60 % 0x3C;
          LODWORD(phkResulta) = v30 / 0x36EE80 % 0x3C;
          CVssFunctionTracer::TraceInternalWithFormat(
            (CVssFunctionTracer *)&v47,
            L"EXIT",
            v6,
            L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
            phkResulta,
            v36,
            v38,
            v40,
            v42,
            v43);
          VssSetTracingContextPerThread(v59);
          return 1;
        }
      }
    }
    CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(this + 4);
    LODWORD(pExceptionObject) = -2147418113;
    throw (long *)&pExceptionObject;
  }
  v45 = &CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable';
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v45 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v47);
  return 0;
}

```

## disassembly

```asm
0x140014650  mov     [rsp-8+Format], r8
0x140014655  mov     qword ptr [rsp-8+Args], r9
0x14001465a  push    rbp
0x14001465b  push    rbx
0x14001465c  push    rsi
0x14001465d  push    rdi
0x14001465e  push    r12
0x140014660  push    r13
0x140014662  push    r14
0x140014664  push    r15
0x140014666  lea     rbp, [rsp-368h]
0x14001466e  sub     rsp, 468h
0x140014675  mov     rax, cs:__security_cookie
0x14001467c  xor     rax, rsp
0x14001467f  mov     [rbp+3A0h+var_50], rax
0x140014686  mov     rdi, rdx
0x140014689  mov     rsi, rcx
0x14001468c  lea     r13, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140014693  mov     [rbp+3A0h+var_3C0], r13
0x140014697  lea     rdx, aCvssregistryke_0; "CVssRegistryKey::Open"
0x14001469e  mov     [rbp+3A0h+var_3B8], rdx
0x1400146a2  lea     rcx, aRegregsc; "REGREGSC"
0x1400146a9  mov     [rbp+3A0h+var_3B0], rcx
0x1400146ad  mov     dword ptr [rbp+3A0h+var_3A8], 7Fh
0x1400146b4  mov     dword ptr [rbp+3A0h+var_3A8+4], 0Bh
0x1400146bb  mov     [rbp+3A0h+var_3A0], 0FFh
0x1400146c2  xor     r14d, r14d
0x1400146c5  mov     [rbp+3A0h+var_320], 1000000h
0x1400146cf  xorps   xmm0, xmm0
0x1400146d2  xor     eax, eax
0x1400146d4  movups  xmmword ptr [rbp+3A0h+var_398], xmm0
0x1400146d8  movups  xmmword ptr [rbp+3A0h+pv], xmm0
0x1400146dc  movups  xmmword ptr [rbp+3A0h+var_378], xmm0
0x1400146e0  movups  xmmword ptr [rbp+3A0h+var_368], xmm0
0x1400146e4  movups  [rbp+3A0h+var_358], xmm0
0x1400146e8  movups  [rbp+3A0h+var_348], xmm0
0x1400146ec  movups  [rbp+3A0h+var_338], xmm0
0x1400146f0  mov     [rbp+3A0h+var_328], rax
0x1400146f4  mov     [rsp+4A0h+var_428], r14d
0x1400146f9  mov     [rbp+3A0h+var_408], rdx
0x1400146fd  mov     [rbp+3A0h+var_420], r13
0x140014701  mov     [rbp+3A0h+var_418], rcx
0x140014705  mov     [rbp+3A0h+var_410], 7Fh
0x14001470c  mov     [rbp+3A0h+var_40C], 0Bh
0x140014713  call    cs:__imp_GetTickCount
0x140014719  mov     [rbp+3A0h+var_3FC], eax
0x14001471c  mov     [rsp+4A0h+var_42C], 0FFFFFFFFh
0x140014724  mov     [rbp+3A0h+var_3F8], 0FFh
0x14001472b  mov     [rsp+4A0h+var_430], r14d
0x140014730  mov     [rbp+3A0h+var_3D0], r14
0x140014734  xorps   xmm0, xmm0
0x140014737  movdqa  xmmword ptr [rbp+3A0h+var_3F0], xmm0
0x14001473c  xorps   xmm1, xmm1
0x14001473f  movdqa  xmmword ptr [rbp+3A0h+var_3E0], xmm1
0x140014744  mov     [rsp+4A0h+pExceptionObject], r14
0x140014749  lea     rcx, [rsp+4A0h+pExceptionObject]
0x14001474e  call    cs:__imp_VssGetTracingContextPerThread
0x140014754  test    eax, eax
0x140014756  jns     loc_140014CC5
0x14001475c  mov     rax, [rbp+3A0h+var_3D0]
0x140014760  test    rax, rax
0x140014763  jz      loc_140014DB9
0x140014769  mov     eax, [rax+30h]
0x14001476c  inc     eax
0x14001476e  mov     [rbp+3A0h+var_400], eax
0x140014771  mov     r15d, 0A0h
0x140014777  mov     ebx, r15d
0x14001477a  cmp     [rbp+3A0h+var_3F8], 0FFh
0x140014781  cmovnz  ebx, [rbp+3A0h+var_3F8]
0x140014785  mov     edx, [rbp+3A0h+var_40C]; unsigned int
0x140014788  lea     rcx, [rsp+4A0h+var_430]; this
0x14001478d  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140014792  lea     rcx, aEnter; "ENTER"
0x140014799  test    eax, eax
0x14001479b  jnz     loc_140014E97
0x1400147a1  mov     rbx, r14
0x1400147a4  nop     dword ptr [rax+00h]
0x1400147a8  nop     dword ptr [rax+rax+00000000h]
0x1400147b0  mov     rcx, [rbp+rbx*8+3A0h+var_398]; pv
0x1400147b5  test    rcx, rcx
0x1400147b8  jnz     loc_140014CA1
0x1400147be  inc     rbx
0x1400147c1  cmp     rbx, 0Fh
0x1400147c5  jnz     short loc_1400147B0
0x1400147c7  mov     [rsp+4A0h+pExceptionObject], r14
0x1400147cc  lea     r9, [rbp+3A0h+Args]; Args
0x1400147d3  mov     r8, [rbp+3A0h+Format]; Format
0x1400147da  mov     edx, 103h; BufferCount
0x1400147df  lea     rcx, [rbp+3A0h+Buffer]; Buffer
0x1400147e6  call    _vsnwprintf
0x1400147eb  test    eax, eax
0x1400147ed  js      loc_140014D1C
0x1400147f3  cmp     eax, 103h
0x1400147f8  ja      loc_140014D1C
0x1400147fe  mov     eax, r14d
0x140014801  jz      loc_140014ED0
0x140014807  mov     [rsp+4A0h+var_428], eax
0x14001480b  lea     r12, ??_7?$CVssAuto@PEAUHKEY__@@V?$CVssAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@6B@; const CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable'
0x140014812  mov     [rsp+4A0h+var_448], r12
0x140014817  mov     [rsp+4A0h+hKey], r14
0x14001481c  lea     rax, [rsp+4A0h+hKey]
0x140014821  mov     [rsp+4A0h+phkResult], rax; phkResult
0x140014826  mov     r9d, [rsi]; samDesired
0x140014829  xor     r8d, r8d; ulOptions
0x14001482c  lea     rdx, [rbp+3A0h+Buffer]; lpSubKey
0x140014833  mov     rcx, rdi; hKey
0x140014836  call    cs:__imp_RegOpenKeyExW
0x14001483c  mov     ebx, eax
0x14001483e  cmp     eax, 2
0x140014841  jz      loc_140014DCB
0x140014847  test    eax, eax
0x140014849  jnz     loc_140014E00
0x14001484f  mov     [rbp+3A0h+var_310], r13
0x140014856  lea     r12, aCvssregistryke_1; "CVssRegistryKey::Close"
0x14001485d  mov     [rbp+3A0h+var_308], r12
0x140014864  lea     rcx, aRegregsc; "REGREGSC"
0x14001486b  mov     [rbp+3A0h+var_300], rcx
0x140014872  mov     [rbp+3A0h+var_2F8], 29Ch
0x14001487c  mov     [rbp+3A0h+var_2F4], 0Bh
0x140014886  mov     [rbp+3A0h+var_2F0], 0FFh
0x140014890  mov     [rbp+3A0h+var_270], 1000000h
0x14001489a  xorps   xmm0, xmm0
0x14001489d  xor     eax, eax
0x14001489f  movups  xmmword ptr [rbp+3A0h+var_2E8], xmm0
0x1400148a6  movups  [rbp+3A0h+var_2D8], xmm0
0x1400148ad  movups  [rbp+3A0h+var_2C8], xmm0
0x1400148b4  movups  [rbp+3A0h+var_2B8], xmm0
0x1400148bb  movups  [rbp+3A0h+var_2A8], xmm0
0x1400148c2  movups  [rbp+3A0h+var_298], xmm0
0x1400148c9  movups  [rbp+3A0h+var_288], xmm0
0x1400148d0  mov     [rbp+3A0h+var_278], rax
0x1400148d7  mov     dword ptr [rbp+3A0h+var_3B8], r14d
0x1400148db  mov     [rbp+3A0h+var_398], r12
0x1400148df  mov     [rbp+3A0h+var_3B0], r13
0x1400148e3  mov     [rbp+3A0h+var_3A8], rcx
0x1400148e7  mov     [rbp+3A0h+var_3A0], 29Ch
0x1400148ee  mov     [rbp+3A0h+var_39C], 0Bh
0x1400148f5  call    cs:__imp_GetTickCount
0x1400148fb  mov     dword ptr [rbp+3A0h+var_398+0Ch], eax
0x1400148fe  mov     dword ptr [rbp+3A0h+var_3C0+4], 0FFFFFFFFh
0x140014905  mov     dword ptr [rbp+3A0h+pv], 0FFh
0x14001490c  mov     dword ptr [rbp+3A0h+var_3C0], r14d
0x140014910  mov     [rbp+3A0h+var_368+8], r14
0x140014914  xorps   xmm0, xmm0
0x140014917  movdqa  xmmword ptr [rbp+3A0h+pv+8], xmm0
0x14001491c  xorps   xmm1, xmm1
0x14001491f  movdqa  xmmword ptr [rbp+3A0h+var_378+8], xmm1
0x140014924  mov     [rsp+4A0h+pExceptionObject], r14
0x140014929  lea     rcx, [rsp+4A0h+pExceptionObject]
0x14001492e  call    cs:__imp_VssGetTracingContextPerThread
0x140014934  test    eax, eax
0x140014936  jns     loc_140014CE6
0x14001493c  mov     rax, [rbp+3A0h+var_368+8]
0x140014940  test    rax, rax
0x140014943  jz      loc_140014DC2
0x140014949  mov     eax, [rax+30h]
0x14001494c  inc     eax
0x14001494e  mov     dword ptr [rbp+3A0h+var_398+8], eax
0x140014951  mov     ebx, r15d
0x140014954  cmp     dword ptr [rbp+3A0h+pv], 0FFh
0x14001495b  cmovnz  ebx, dword ptr [rbp+3A0h+pv]
0x14001495f  mov     edx, [rbp+3A0h+var_39C]; unsigned int
0x140014962  lea     rcx, [rbp+3A0h+var_3C0]; this
0x140014966  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14001496b  test    eax, eax
0x14001496d  jnz     loc_140014EE8
0x140014973  mov     rbx, r14
0x140014976  nop     word ptr [rax+rax+00000000h]
0x140014980  mov     rcx, [rbp+rbx*8+3A0h+var_2E8]; pv
0x140014988  test    rcx, rcx
0x14001498b  jnz     loc_140014CB1
0x140014991  inc     rbx
0x140014994  cmp     rbx, 0Fh
0x140014998  jnz     short loc_140014980
0x14001499a  mov     rcx, [rsi+8]; hKey
0x14001499e  test    rcx, rcx
0x1400149a1  jz      short loc_1400149B7
0x1400149a3  call    cs:__imp_RegCloseKey
0x1400149a9  mov     ebx, eax
0x1400149ab  test    eax, eax
0x1400149ad  jnz     loc_140014F28
0x1400149b3  mov     [rsi+8], r14
0x1400149b7  mov     rcx, [rsi+18h]; pv
0x1400149bb  test    rcx, rcx
0x1400149be  jnz     loc_140014D06
0x1400149c4  mov     [rsi+18h], r14
0x1400149c8  mov     rcx, [rbp+3A0h+pv+8]; pv
0x1400149cc  call    cs:__imp_CoTaskMemFree
0x1400149d2  mov     [rbp+3A0h+pv+8], r14
0x1400149d6  mov     rcx, [rbp+3A0h+var_378]; pv
0x1400149da  call    cs:__imp_CoTaskMemFree
0x1400149e0  mov     [rbp+3A0h+var_378], r14
0x1400149e4  mov     rcx, [rbp+3A0h+var_378+8]; pv
0x1400149e8  call    cs:__imp_CoTaskMemFree
0x1400149ee  mov     [rbp+3A0h+var_378+8], r14
0x1400149f2  mov     rcx, [rbp+3A0h+var_368]; pv
0x1400149f6  call    cs:__imp_CoTaskMemFree
0x1400149fc  mov     [rbp+3A0h+var_368], r14
0x140014a00  call    cs:__imp_GetTickCount
0x140014a06  mov     edi, eax
0x140014a08  sub     edi, dword ptr [rbp+3A0h+var_398+0Ch]
0x140014a0b  mov     eax, 10624DD3h
0x140014a10  mul     edi
0x140014a12  mov     ecx, edx
0x140014a14  shr     ecx, 6
0x140014a17  mov     eax, 88888889h
0x140014a1c  mul     ecx
0x140014a1e  shr     edx, 5
0x140014a21  imul    eax, edx, 3Ch ; '<'
0x140014a24  mov     ebx, ecx
0x140014a26  sub     ebx, eax
0x140014a28  mov     eax, 45E7B273h
0x140014a2d  mul     edi
0x140014a2f  mov     r11d, edx
0x140014a32  shr     r11d, 0Eh
0x140014a36  mov     eax, 88888889h
0x140014a3b  mul     r11d
0x140014a3e  shr     edx, 5
0x140014a41  imul    eax, edx, 3Ch ; '<'
0x140014a44  sub     r11d, eax
0x140014a47  mov     eax, 95217CB1h
0x140014a4c  mul     edi
0x140014a4e  mov     r10d, edx
0x140014a51  shr     r10d, 15h
0x140014a55  mov     eax, 88888889h
0x140014a5a  mul     r10d
0x140014a5d  shr     edx, 5
0x140014a60  imul    eax, edx, 3Ch ; '<'
0x140014a63  sub     r10d, eax
0x140014a66  mov     r9d, dword ptr [rbp+3A0h+var_3B8]
0x140014a6a  mov     r8d, r15d
0x140014a6d  cmp     dword ptr [rbp+3A0h+pv], 0FFh
0x140014a74  cmovnz  r8d, dword ptr [rbp+3A0h+pv]; unsigned int
0x140014a79  imul    eax, ecx, 3E8h
0x140014a7f  mov     ecx, edi
0x140014a81  sub     ecx, eax
0x140014a83  mov     dword ptr [rsp+4A0h+var_458], r9d
0x140014a88  mov     dword ptr [rsp+4A0h+var_460], edi
0x140014a8c  mov     dword ptr [rsp+4A0h+var_468], ecx
0x140014a90  mov     dword ptr [rsp+4A0h+var_470], ebx
0x140014a94  mov     dword ptr [rsp+4A0h+var_478], r11d
0x140014a99  mov     dword ptr [rsp+4A0h+phkResult], r10d
0x140014a9e  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140014aa5  lea     rdx, aExit; "EXIT"
0x140014aac  lea     rcx, [rbp+3A0h+var_3C0]; this
0x140014ab0  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140014ab5  mov     rcx, [rbp+3A0h+var_368+8]
0x140014ab9  call    cs:__imp_VssSetTracingContextPerThread
0x140014abf  lea     rax, [rbp+3A0h+Buffer]
0x140014ac6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140014acd  nop     dword ptr [rax]
0x140014ad0  lea     rbx, [rbx+1]
0x140014ad4  cmp     word ptr [rax+rbx*2], 0
0x140014ad9  jnz     short loc_140014AD0
0x140014adb  mov     rcx, [rsi+18h]; pv
0x140014adf  test    rcx, rcx
0x140014ae2  jnz     loc_140014D11
0x140014ae8  mov     [rsi+18h], r14
0x140014aec  lea     rcx, ds:2[rbx*2]; cb
0x140014af4  call    cs:__imp_CoTaskMemAlloc
0x140014afa  mov     rcx, rax
0x140014afd  mov     [rsi+18h], rax
0x140014b01  test    rax, rax
0x140014b04  jz      loc_140014FA4
0x140014b0a  lea     rax, [rbx+1]
0x140014b0e  test    rax, rax
0x140014b11  jz      loc_140014FC2
0x140014b17  cmp     rax, 7FFFFFFFh
0x140014b1d  ja      loc_140014FBE
0x140014b23  mov     r8d, 7FFFFFFEh
0x140014b29  lea     r9, [rbp+3A0h+Buffer]
0x140014b30  test    r8, r8
0x140014b33  jz      short loc_140014B52
0x140014b35  movzx   edx, word ptr [r9]
0x140014b39  test    dx, dx
0x140014b3c  jz      short loc_140014B52
0x140014b3e  add     r9, 2
0x140014b42  mov     [rcx], dx
0x140014b45  add     rcx, 2
0x140014b49  dec     r8
0x140014b4c  sub     rax, 1
0x140014b50  jnz     short loc_140014B30
0x140014b52  lea     rdx, [rcx-2]
0x140014b56  test    rax, rax
0x140014b59  cmovnz  rdx, rcx
0x140014b5d  mov     [rdx], r14w
0x140014b61  jz      loc_140014FC2
0x140014b67  mov     rax, [rsp+4A0h+hKey]
0x140014b6c  mov     [rsi+8], rax
0x140014b70  mov     [rsp+4A0h+hKey], r14
0x140014b75  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x140014b7c  mov     [rsp+4A0h+var_448], rax
0x140014b81  mov     rcx, [rbp+3A0h+var_3F0]; pv
0x140014b85  call    cs:__imp_CoTaskMemFree
0x140014b8b  mov     [rbp+3A0h+var_3F0], r14
0x140014b8f  mov     rcx, [rbp+3A0h+var_3F0+8]; pv
0x140014b93  call    cs:__imp_CoTaskMemFree
0x140014b99  mov     [rbp+3A0h+var_3F0+8], r14
0x140014b9d  mov     rcx, [rbp+3A0h+var_3E0]; pv
0x140014ba1  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
