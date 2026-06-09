# CVssDeletingWriter::GetNextFileSpecification(ushort const *,ushort * &,ulong *,CVssDeletingWriter::ToDeleteFile &)

- ea: `0x14000b140`
- end: `0x14000bb96`
- name: `?GetNextFileSpecification@CVssDeletingWriter@@IEAA_NPEBGAEAPEAGPEAKAEAUToDeleteFile@1@@Z`
- size: `2646`
- prototype: `bool __fastcall(CVssDeletingWriter *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned int *, struct CVssDeletingWriter::ToDeleteFile *pExceptionObject)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000c84c`

## callees

- `0x14000b140`
- `0x14000e640`
- `0x1400137c0`
- `0x140013c60`
- `0x140028b48`
- `0x1400921dc`
- `0x1400921e8`
- `0x14009c900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000b275`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000b293`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000b800`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000b275`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000b293`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000b800`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14000b257`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14000b2c5`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14000b84b`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14000b895`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14000b257`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14000b2c5`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14000b84b`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14000b895`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14000b228`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14000b228`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b41f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b489`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b5ef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b655`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b41f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b489`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b5ef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000b655`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b199`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b4a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b6a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b199`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b4a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b6a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b468`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b638`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b6bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b468`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b638`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b6bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000b367`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000b542`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000b367`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000b542`
- `VssTrace!__imp_VssTraceMessage` at `0x14000b8db`
- `VssTrace!__imp_VssTraceMessage` at `0x14000b9a9`
- `VssTrace!__imp_VssTraceMessage` at `0x14000b8db`
- `VssTrace!__imp_VssTraceMessage` at `0x14000b9a9`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000b780`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000b7a3`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000b780`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000b7a3`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000b3a5`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000b581`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000b3a5`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000b581`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b747`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b75b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b747`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b75b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CVssDeletingWriter::GetNextFileSpecification(
        CVssDeletingWriter *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned int *a4,
        struct CVssDeletingWriter::ToDeleteFile *pExceptionObject)
{
  unsigned __int16 **v6; // r15
  unsigned int v8; // r14d
  struct CVssDeletingWriter::ToDeleteFile *v9; // rbx
  void *v10; // rcx
  void *v11; // rcx
  __int64 v12; // rsi
  unsigned __int16 *v13; // r13
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  unsigned __int16 *v17; // rax
  wchar_t *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  wchar_t *v21; // rbx
  const WCHAR *v22; // r15
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r14
  __int64 v28; // rax
  wchar_t *v29; // r12
  __int64 v30; // rdx
  __int64 v31; // r8
  unsigned __int16 **v32; // rax
  int v33; // ebx
  __int64 i; // rbx
  void *v35; // rcx
  DWORD v36; // r13d
  struct CVssDeletingWriter::ToDeleteFile *v37; // r12
  void *v38; // rbx
  WCHAR *v39; // rax
  DWORD v40; // eax
  unsigned __int16 **v41; // rax
  int v42; // ebx
  __int64 j; // rbx
  void *v44; // rcx
  DWORD v45; // r13d
  struct CVssDeletingWriter::ToDeleteFile *v46; // r12
  void *v47; // rbx
  WCHAR *v48; // rax
  DWORD v49; // eax
  struct CVssDeletingWriter::ToDeleteFile *v50; // r15
  void *v51; // rcx
  unsigned __int64 v52; // rbx
  _WORD *v53; // rdx
  __int16 v54; // ax
  _WORD *v55; // rcx
  __int64 v57; // rax
  __int64 v58; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v59; // [rsp+50h] [rbp-B0h] BYREF
  int v60; // [rsp+58h] [rbp-A8h]
  const wchar_t *v61; // [rsp+60h] [rbp-A0h]
  const wchar_t *v62; // [rsp+68h] [rbp-98h]
  unsigned int v63; // [rsp+70h] [rbp-90h]
  unsigned int v64; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v65; // [rsp+78h] [rbp-88h]
  unsigned int v66; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  int v68; // [rsp+88h] [rbp-78h]
  __int128 v69; // [rsp+90h] [rbp-70h]
  __int128 v70; // [rsp+A0h] [rbp-60h]
  unsigned __int16 **v71; // [rsp+B0h] [rbp-50h]
  const wchar_t *v72; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v73; // [rsp+C8h] [rbp-38h]
  const wchar_t *v74; // [rsp+D0h] [rbp-30h]
  int v75; // [rsp+D8h] [rbp-28h]
  int v76; // [rsp+DCh] [rbp-24h]
  int v77; // [rsp+E0h] [rbp-20h]
  LPVOID pv[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v79; // [rsp+F8h] [rbp-8h]
  __int128 v80; // [rsp+108h] [rbp+8h]
  __int128 v81; // [rsp+118h] [rbp+18h]
  __int128 v82; // [rsp+128h] [rbp+28h]
  __int128 v83; // [rsp+138h] [rbp+38h]
  __int128 v84; // [rsp+148h] [rbp+48h]
  __int64 v85; // [rsp+158h] [rbp+58h]
  int v86; // [rsp+160h] [rbp+60h]
  void **v87; // [rsp+168h] [rbp+68h] BYREF
  void *v88; // [rsp+170h] [rbp+70h]
  const WCHAR *lpSrc; // [rsp+1C0h] [rbp+C0h]
  unsigned __int16 **v90; // [rsp+1D0h] [rbp+D0h] BYREF

  v90 = a3;
  v6 = a3;
  v8 = *a4;
  v9 = pExceptionObject;
  v10 = (void *)*((_QWORD *)pExceptionObject + 4);
  if ( v10 )
    LocalFree(v10);
  *((_QWORD *)v9 + 4) = 0;
  v11 = (void *)*((_QWORD *)v9 + 2);
  if ( v11 )
    LocalFree(v11);
  *((_QWORD *)v9 + 2) = 0;
  *a4 = 0;
  v12 = 2147483646;
  while ( 1 )
  {
    v13 = *v6;
    lpSrc = *v6;
    if ( !*v6 || v8 - 1 > 0x7FFFFFFE )
      return 0;
    v14 = v8;
    v15 = *v6;
    do
    {
      if ( !*v15 )
        break;
      ++v15;
      --v14;
    }
    while ( v14 );
    v16 = v8 - v14;
    if ( !v14 || !v16 )
      return 0;
    v8 = v14 - 1;
    if ( (_DWORD)v14 == 1 )
      v17 = 0;
    else
      v17 = &v13[v16 + 1];
    *v6 = v17;
    v18 = wcsrchr(v13, 0x5Cu);
    v21 = v18;
    if ( v18 )
    {
      v22 = v18 + 1;
      if ( v18[1] )
      {
        *a4 = v8;
        *v18 = 0;
        if ( (unsigned int)_o_iswspace(*v13, v19, v20) )
        {
          do
            ++v13;
          while ( (unsigned int)_o_iswspace(*v13, v23, v24) );
          lpSrc = v13;
        }
        if ( (unsigned int)_o__wcsnicmp(v13, L"$UserProfile$", 13) )
        {
          if ( !(unsigned int)_o__wcsnicmp(v13, L"$AllVolumes$", 12) )
          {
            *((_BYTE *)pExceptionObject + 2) = 1;
            v13 += 12;
            lpSrc = v13;
            if ( *v13 == 92 )
            {
              ++v13;
              goto LABEL_84;
            }
          }
        }
        else
        {
          *((_BYTE *)pExceptionObject + 1) = 1;
          v57 = 28;
          if ( v13[13] != 92 )
            v57 = 26;
          v13 = (unsigned __int16 *)((char *)v13 + v57);
LABEL_84:
          lpSrc = v13;
        }
        v27 = -1;
        v28 = -1;
        do
          ++v28;
        while ( v22[v28] );
        v29 = &v21[v28];
        if ( (unsigned int)_o_iswspace(*v29, v25, v26) )
        {
          do
            --v29;
          while ( (unsigned int)_o_iswspace(*v29, v30, v31) );
        }
        if ( v29 >= v21 + 4 && !(unsigned int)_o__wcsnicmp(v29 - 2, L" /s", 3) )
        {
          *(_BYTE *)pExceptionObject = 1;
          *(v29 - 2) = 0;
        }
        v72 = L"base\\stor\\vss\\inc\\vs_str.hxx";
        v73 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
        v74 = L"INCSTRH";
        v75 = 271;
        v76 = 11;
        v77 = 255;
        v86 = 0x1000000;
        *(_OWORD *)pv = 0;
        v79 = 0;
        v80 = 0;
        v81 = 0;
        v82 = 0;
        v83 = 0;
        v84 = 0;
        v85 = 0;
        v60 = 0;
        v65 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
        v61 = L"base\\stor\\vss\\inc\\vs_str.hxx";
        v62 = L"INCSTRH";
        v63 = 271;
        v64 = 11;
        TickCount = GetTickCount();
        v68 = 255;
        v59 = 0xFFFFFFFF00000000uLL;
        v71 = 0;
        v69 = 0;
        v70 = 0;
        v90 = 0;
        if ( (int)VssGetTracingContextPerThread(&v90) < 0 || (int)VssSetTracingContextPerThread(&v59) < 0 )
        {
          v32 = v71;
        }
        else
        {
          v32 = v90;
          v71 = v90;
        }
        if ( v32 )
          v66 = *((_DWORD *)v32 + 12) + 1;
        else
          v66 = 0;
        v33 = 160;
        if ( v68 != 255 )
          v33 = v68;
        if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v59, v64) )
          VssTraceMessage(v61, v62, v63, v66, v64, v65, L"ENTER", v33, 0);
        for ( i = 0; i != 15; ++i )
        {
          v35 = pv[i];
          if ( v35 )
          {
            CoTaskMemFree(v35);
            pv[i] = 0;
          }
        }
        v36 = ExpandEnvironmentStringsW(v13, 0, 0);
        if ( !v36 )
        {
          v72 = L"base\\stor\\vss\\inc\\vs_str.hxx";
          v73 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
          v74 = L"INCSTRH";
          v75 = 275;
          v76 = 11;
          v77 = 255;
          v86 = 0x1000000;
          memset_0(pv, 0, 0x78u);
          CVssFunctionTracer::TranslateWin32Error(&v59, &v72, L"ExpandEnvironmentString(%s, NULL, 0)", lpSrc);
        }
        v37 = pExceptionObject;
        v38 = (void *)*((_QWORD *)pExceptionObject + 2);
        *((_QWORD *)pExceptionObject + 2) = 0;
        v88 = v38;
        v87 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
        if ( v36 != 1 )
        {
          v39 = (WCHAR *)LocalAlloc(0, 2LL * (v36 - 1) + 2);
          *((_QWORD *)v37 + 2) = v39;
          if ( !v39 )
          {
            LODWORD(pExceptionObject) = -2147024882;
            throw (long *)&pExceptionObject;
          }
          v40 = ExpandEnvironmentStringsW(lpSrc, v39, v36);
          if ( !v40 || v40 > v36 )
          {
            CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::TransferFrom(
              (char *)v37 + 8,
              &v87);
            v72 = L"base\\stor\\vss\\inc\\vs_str.hxx";
            v73 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
            v74 = L"INCSTRH";
            v75 = 287;
            v76 = 11;
            v77 = 255;
            v86 = 0x1000000;
            memset_0(pv, 0, 0x78u);
            LODWORD(v58) = v36;
            CVssFunctionTracer::TranslateWin32Error(
              &v59,
              &v72,
              L"ExpandEnvironmentString(%s, %p, %d)",
              lpSrc,
              *((_QWORD *)v37 + 2),
              v58);
          }
        }
        if ( v38 )
          LocalFree(v38);
        CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v59);
        v72 = L"base\\stor\\vss\\inc\\vs_str.hxx";
        v73 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
        v74 = L"INCSTRH";
        v75 = 271;
        v76 = 11;
        v77 = 255;
        v86 = 0x1000000;
        *(_OWORD *)pv = 0;
        v79 = 0;
        v80 = 0;
        v81 = 0;
        v82 = 0;
        v83 = 0;
        v84 = 0;
        v85 = 0;
        v60 = 0;
        v65 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
        v61 = L"base\\stor\\vss\\inc\\vs_str.hxx";
        v62 = L"INCSTRH";
        v63 = 271;
        v64 = 11;
        TickCount = GetTickCount();
        v68 = 255;
        v59 = 0xFFFFFFFF00000000uLL;
        v71 = 0;
        v69 = 0;
        v70 = 0;
        v90 = 0;
        if ( (int)VssGetTracingContextPerThread(&v90) < 0 || (int)VssSetTracingContextPerThread(&v59) < 0 )
        {
          v41 = v71;
        }
        else
        {
          v41 = v90;
          v71 = v90;
        }
        if ( v41 )
          v66 = *((_DWORD *)v41 + 12) + 1;
        else
          v66 = 0;
        v42 = 160;
        if ( v68 != 255 )
          v42 = v68;
        if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v59, v64) )
          VssTraceMessage(v61, v62, v63, v66, v64, v65, L"ENTER", v42, 0);
        for ( j = 0; j != 15; ++j )
        {
          v44 = pv[j];
          if ( v44 )
          {
            CoTaskMemFree(v44);
            pv[j] = 0;
          }
        }
        v45 = ExpandEnvironmentStringsW(v22, 0, 0);
        if ( !v45 )
        {
          v72 = L"base\\stor\\vss\\inc\\vs_str.hxx";
          v73 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
          v74 = L"INCSTRH";
          v75 = 275;
          v76 = 11;
          v77 = 255;
          v86 = 0x1000000;
          memset_0(pv, 0, 0x78u);
          CVssFunctionTracer::TranslateWin32Error(&v59, &v72, L"ExpandEnvironmentString(%s, NULL, 0)", v22);
        }
        v46 = pExceptionObject;
        v47 = (void *)*((_QWORD *)pExceptionObject + 4);
        *((_QWORD *)pExceptionObject + 4) = 0;
        v88 = v47;
        v87 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
        if ( v45 != 1 )
        {
          v48 = (WCHAR *)LocalAlloc(0, 2LL * (v45 - 1) + 2);
          *((_QWORD *)v46 + 4) = v48;
          if ( !v48 )
          {
            LODWORD(pExceptionObject) = -2147024882;
            throw (long *)&pExceptionObject;
          }
          v49 = ExpandEnvironmentStringsW(v22, v48, v45);
          if ( !v49 || v49 > v45 )
          {
            CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::TransferFrom(
              (char *)v46 + 24,
              &v87);
            v72 = L"base\\stor\\vss\\inc\\vs_str.hxx";
            v73 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
            v74 = L"INCSTRH";
            v75 = 287;
            v76 = 11;
            v77 = 255;
            v86 = 0x1000000;
            memset_0(pv, 0, 0x78u);
            LODWORD(v58) = v45;
            CVssFunctionTracer::TranslateWin32Error(
              &v59,
              &v72,
              L"ExpandEnvironmentString(%s, %p, %d)",
              v22,
              *((_QWORD *)v46 + 4),
              v58);
          }
        }
        if ( v47 )
          LocalFree(v47);
        CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v59);
        v50 = pExceptionObject;
        do
          ++v27;
        while ( a2[v27] );
        v51 = (void *)*((_QWORD *)pExceptionObject + 7);
        if ( v51 )
          LocalFree(v51);
        *((_QWORD *)v50 + 7) = 0;
        v52 = v27 + 1;
        v53 = LocalAlloc(0, 2 * (v27 + 1));
        *((_QWORD *)v50 + 7) = v53;
        if ( !v53 )
        {
          LODWORD(pExceptionObject) = -2147024882;
          throw (long *)&pExceptionObject;
        }
        if ( v27 != -1 )
        {
          if ( v52 > 0x7FFFFFFF )
          {
            *v53 = 0;
          }
          else
          {
            do
            {
              if ( !v12 )
                break;
              v54 = *a2;
              if ( !*a2 )
                break;
              ++a2;
              *v53++ = v54;
              --v12;
              --v52;
            }
            while ( v52 );
            v55 = v53 - 1;
            if ( v52 )
              v55 = v53;
            *v55 = 0;
            if ( v52 )
              return 1;
          }
        }
        CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close((char *)v50 + 48);
        LODWORD(pExceptionObject) = -2147418113;
        throw (long *)&pExceptionObject;
      }
      v6 = v90;
    }
  }
}

```

## disassembly

```asm
0x14000b140  mov     [rsp-8+arg_8], rbx
0x14000b145  mov     [rsp-8+arg_10], r8
0x14000b14a  mov     [rsp-8+lpSrc], rcx
0x14000b14f  push    rbp
0x14000b150  push    rsi
0x14000b151  push    rdi
0x14000b152  push    r12
0x14000b154  push    r13
0x14000b156  push    r14
0x14000b158  push    r15
0x14000b15a  lea     rbp, [rsp-80h]
0x14000b15f  sub     rsp, 180h
0x14000b166  mov     r12, r9
0x14000b169  mov     r15, r8
0x14000b16c  mov     rdi, rdx
0x14000b16f  mov     r14d, [r9]
0x14000b172  mov     rbx, [rbp+0B0h+pExceptionObject]
0x14000b179  mov     rcx, [rbx+20h]; hMem
0x14000b17d  test    rcx, rcx
0x14000b180  jz      short loc_14000B188
0x14000b182  call    cs:__imp_LocalFree
0x14000b188  mov     qword ptr [rbx+20h], 0
0x14000b190  mov     rcx, [rbx+10h]; hMem
0x14000b194  test    rcx, rcx
0x14000b197  jz      short loc_14000B19F
0x14000b199  call    cs:__imp_LocalFree
0x14000b19f  mov     qword ptr [rbx+10h], 0
0x14000b1a7  mov     dword ptr [r12], 0
0x14000b1af  mov     esi, 7FFFFFFEh
0x14000b1b4  mov     r13, [r15]
0x14000b1b7  mov     [rbp+0B0h+lpSrc], r13
0x14000b1be  test    r13, r13
0x14000b1c1  jz      loc_14000BB8F
0x14000b1c7  lea     eax, [r14-1]
0x14000b1cb  cmp     eax, esi
0x14000b1cd  ja      loc_14000BB8F
0x14000b1d3  mov     ecx, r14d
0x14000b1d6  mov     rax, r13
0x14000b1d9  mov     edx, r14d
0x14000b1dc  nop     dword ptr [rax+00h]
0x14000b1e0  cmp     word ptr [rax], 0
0x14000b1e4  jz      short loc_14000B1F0
0x14000b1e6  add     rax, 2
0x14000b1ea  sub     rcx, 1
0x14000b1ee  jnz     short loc_14000B1E0
0x14000b1f0  sub     rdx, rcx
0x14000b1f3  xor     eax, eax
0x14000b1f5  test    rcx, rcx
0x14000b1f8  cmovz   rdx, rax
0x14000b1fc  jz      loc_14000BB8F
0x14000b202  test    rdx, rdx
0x14000b205  jz      loc_14000BB8F
0x14000b20b  mov     eax, 0FFFFFFFFh
0x14000b210  sub     eax, edx
0x14000b212  add     r14d, eax
0x14000b215  jnz     loc_14000B76B
0x14000b21b  xor     eax, eax
0x14000b21d  mov     [r15], rax
0x14000b220  mov     edx, 5Ch ; '\'; Ch
0x14000b225  mov     rcx, r13; Str
0x14000b228  call    cs:__imp_wcsrchr
0x14000b22e  mov     rbx, rax
0x14000b231  test    rax, rax
0x14000b234  jz      loc_14000B1B4
0x14000b23a  lea     r15, [rax+2]
0x14000b23e  cmp     word ptr [r15], 0
0x14000b243  jz      loc_14000B836
0x14000b249  mov     [r12], r14d
0x14000b24d  xor     ecx, ecx
0x14000b24f  mov     [rax], cx
0x14000b252  movzx   ecx, word ptr [r13+0]
0x14000b257  call    cs:__imp__o_iswspace
0x14000b25d  test    eax, eax
0x14000b25f  jnz     loc_14000B842
0x14000b265  mov     r8d, 0Dh
0x14000b26b  lea     rdx, aUserprofile; "$UserProfile$"
0x14000b272  mov     rcx, r13
0x14000b275  call    cs:__imp__o__wcsnicmp
0x14000b27b  test    eax, eax
0x14000b27d  jz      loc_14000B7C1
0x14000b283  mov     r8d, 0Ch
0x14000b289  lea     rdx, aAllvolumes; "$AllVolumes$"
0x14000b290  mov     rcx, r13
0x14000b293  call    cs:__imp__o__wcsnicmp
0x14000b299  test    eax, eax
0x14000b29b  jz      loc_14000B861
0x14000b2a1  mov     r14, 0FFFFFFFFFFFFFFFFh
0x14000b2a8  mov     rax, r14
0x14000b2ab  nop     dword ptr [rax+rax+00h]
0x14000b2b0  lea     rax, [rax+1]
0x14000b2b4  cmp     word ptr [r15+rax*2], 0
0x14000b2ba  jnz     short loc_14000B2B0
0x14000b2bc  lea     r12, [rbx+rax*2]
0x14000b2c0  movzx   ecx, word ptr [r12]
0x14000b2c5  call    cs:__imp__o_iswspace
0x14000b2cb  test    eax, eax
0x14000b2cd  jnz     loc_14000B88C
0x14000b2d3  lea     rax, [rbx+8]
0x14000b2d7  cmp     r12, rax
0x14000b2da  jnb     loc_14000B7EE
0x14000b2e0  xor     ebx, ebx
0x14000b2e2  lea     rcx, aBaseStorVssInc_1; "base\\stor\\vss\\inc\\vs_str.hxx"
0x14000b2e9  mov     [rbp+0B0h+var_F0], rcx
0x14000b2ed  lea     rdx, aCvssautostring; "CVssAutoString<class CVssAutoLocalPtr<u"...
0x14000b2f4  mov     [rbp+0B0h+var_E8], rdx
0x14000b2f8  lea     r8, aIncstrh; "INCSTRH"
0x14000b2ff  mov     [rbp+0B0h+var_E0], r8
0x14000b303  mov     [rbp+0B0h+var_D8], 10Fh
0x14000b30a  mov     [rbp+0B0h+var_D4], 0Bh
0x14000b311  mov     [rbp+0B0h+var_D0], 0FFh
0x14000b318  mov     [rbp+0B0h+var_50], 1000000h
0x14000b31f  xorps   xmm0, xmm0
0x14000b322  xor     eax, eax
0x14000b324  movups  xmmword ptr [rbp+0B0h+pv], xmm0
0x14000b328  movups  [rbp+0B0h+var_B8], xmm0
0x14000b32c  movups  [rbp+0B0h+var_A8], xmm0
0x14000b330  movups  [rbp+0B0h+var_98], xmm0
0x14000b334  movups  [rbp+0B0h+var_88], xmm0
0x14000b338  movups  [rbp+0B0h+var_78], xmm0
0x14000b33c  movups  [rbp+0B0h+var_68], xmm0
0x14000b340  mov     [rbp+0B0h+var_58], rax
0x14000b344  mov     [rsp+1B0h+var_158], ebx
0x14000b348  mov     [rsp+1B0h+var_138], rdx
0x14000b34d  mov     [rsp+1B0h+var_150], rcx
0x14000b352  mov     [rsp+1B0h+var_148], r8
0x14000b357  mov     [rsp+1B0h+var_140], 10Fh
0x14000b35f  mov     [rsp+1B0h+var_13C], 0Bh
0x14000b367  call    cs:__imp_GetTickCount
0x14000b36d  mov     [rbp+0B0h+var_12C], eax
0x14000b370  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x14000b378  mov     [rbp+0B0h+var_128], 0FFh
0x14000b37f  mov     [rsp+1B0h+var_160], ebx
0x14000b383  mov     [rbp+0B0h+var_100], rbx
0x14000b387  xorps   xmm0, xmm0
0x14000b38a  movdqa  [rbp+0B0h+var_120], xmm0
0x14000b38f  xorps   xmm1, xmm1
0x14000b392  movdqa  [rbp+0B0h+var_110], xmm1
0x14000b397  mov     [rbp+0B0h+arg_10], rbx
0x14000b39e  lea     rcx, [rbp+0B0h+arg_10]
0x14000b3a5  call    cs:__imp_VssGetTracingContextPerThread
0x14000b3ab  test    eax, eax
0x14000b3ad  jns     loc_14000B77B
0x14000b3b3  mov     rax, [rbp+0B0h+var_100]
0x14000b3b7  test    rax, rax
0x14000b3ba  jz      loc_14000B825
0x14000b3c0  mov     eax, [rax+30h]
0x14000b3c3  inc     eax
0x14000b3c5  mov     [rbp+0B0h+var_130], eax
0x14000b3c8  mov     ebx, 0A0h
0x14000b3cd  cmp     [rbp+0B0h+var_128], 0FFh
0x14000b3d4  cmovnz  ebx, [rbp+0B0h+var_128]
0x14000b3d8  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x14000b3dc  lea     rcx, [rsp+1B0h+var_160]; this
0x14000b3e1  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14000b3e6  lea     rcx, aEnter; "ENTER"
0x14000b3ed  test    eax, eax
0x14000b3ef  jnz     loc_14000B8A4
0x14000b3f5  xor     ebx, ebx
0x14000b3f7  nop     word ptr [rax+rax+00000000h]
0x14000b400  mov     rcx, [rbp+rbx*8+0B0h+pv]; pv
0x14000b405  test    rcx, rcx
0x14000b408  jnz     loc_14000B747
0x14000b40e  inc     rbx
0x14000b411  cmp     rbx, 0Fh
0x14000b415  jnz     short loc_14000B400
0x14000b417  xor     r8d, r8d; nSize
0x14000b41a  xor     edx, edx; lpDst
0x14000b41c  mov     rcx, r13; lpSrc
0x14000b41f  call    cs:__imp_ExpandEnvironmentStringsW
0x14000b425  mov     r13d, eax
0x14000b428  test    eax, eax
0x14000b42a  jz      loc_14000B8E6
0x14000b430  mov     r12, [rbp+0B0h+pExceptionObject]
0x14000b437  mov     rbx, [r12+10h]
0x14000b43c  mov     qword ptr [r12+10h], 0
0x14000b445  mov     [rbp+0B0h+var_40], rbx
0x14000b449  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14000b450  mov     [rbp+0B0h+var_48], rax
0x14000b454  cmp     r13d, 1
0x14000b458  jz      short loc_14000B4A0
0x14000b45a  lea     eax, [r13-1]
0x14000b45e  lea     rdx, ds:2[rax*2]; uBytes
0x14000b466  xor     ecx, ecx; uFlags
0x14000b468  call    cs:__imp_LocalAlloc
0x14000b46e  mov     [r12+10h], rax
0x14000b473  test    rax, rax
0x14000b476  jz      loc_14000B951
0x14000b47c  mov     r8d, r13d; nSize
0x14000b47f  mov     rdx, rax; lpDst
0x14000b482  mov     rcx, [rbp+0B0h+lpSrc]; lpSrc
0x14000b489  call    cs:__imp_ExpandEnvironmentStringsW
0x14000b48f  test    eax, eax
0x14000b491  jz      loc_14000BB07
0x14000b497  cmp     eax, r13d
0x14000b49a  ja      loc_14000BB07
0x14000b4a0  test    rbx, rbx
0x14000b4a3  jz      short loc_14000B4AF
0x14000b4a5  mov     rcx, rbx; hMem
0x14000b4a8  call    cs:__imp_LocalFree
0x14000b4ae  nop
0x14000b4af  lea     rcx, [rsp+1B0h+var_160]; this
0x14000b4b4  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14000b4b9  lea     rcx, aBaseStorVssInc_1; "base\\stor\\vss\\inc\\vs_str.hxx"
0x14000b4c0  mov     [rbp+0B0h+var_F0], rcx
0x14000b4c4  lea     rdx, aCvssautostring; "CVssAutoString<class CVssAutoLocalPtr<u"...
0x14000b4cb  mov     [rbp+0B0h+var_E8], rdx
0x14000b4cf  lea     r8, aIncstrh; "INCSTRH"
0x14000b4d6  mov     [rbp+0B0h+var_E0], r8
0x14000b4da  mov     [rbp+0B0h+var_D8], 10Fh
0x14000b4e1  mov     [rbp+0B0h+var_D4], 0Bh
0x14000b4e8  mov     [rbp+0B0h+var_D0], 0FFh
0x14000b4ef  xor     r13d, r13d
0x14000b4f2  mov     [rbp+0B0h+var_50], 1000000h
0x14000b4f9  xorps   xmm0, xmm0
0x14000b4fc  xor     eax, eax
0x14000b4fe  movups  xmmword ptr [rbp+0B0h+pv], xmm0
0x14000b502  movups  [rbp+0B0h+var_B8], xmm0
0x14000b506  movups  [rbp+0B0h+var_A8], xmm0
0x14000b50a  movups  [rbp+0B0h+var_98], xmm0
0x14000b50e  movups  [rbp+0B0h+var_88], xmm0
0x14000b512  movups  [rbp+0B0h+var_78], xmm0
0x14000b516  movups  [rbp+0B0h+var_68], xmm0
0x14000b51a  mov     [rbp+0B0h+var_58], rax
0x14000b51e  mov     [rsp+1B0h+var_158], r13d
0x14000b523  mov     [rsp+1B0h+var_138], rdx
0x14000b528  mov     [rsp+1B0h+var_150], rcx
0x14000b52d  mov     [rsp+1B0h+var_148], r8
0x14000b532  mov     [rsp+1B0h+var_140], 10Fh
0x14000b53a  mov     [rsp+1B0h+var_13C], 0Bh
0x14000b542  call    cs:__imp_GetTickCount
0x14000b548  mov     [rbp+0B0h+var_12C], eax
0x14000b54b  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x14000b553  mov     [rbp+0B0h+var_128], 0FFh
0x14000b55a  mov     [rsp+1B0h+var_160], r13d
0x14000b55f  mov     [rbp+0B0h+var_100], r13
0x14000b563  xorps   xmm0, xmm0
0x14000b566  movdqa  [rbp+0B0h+var_120], xmm0
0x14000b56b  xorps   xmm1, xmm1
0x14000b56e  movdqa  [rbp+0B0h+var_110], xmm1
0x14000b573  mov     [rbp+0B0h+arg_10], r13
0x14000b57a  lea     rcx, [rbp+0B0h+arg_10]
0x14000b581  call    cs:__imp_VssGetTracingContextPerThread
0x14000b587  test    eax, eax
0x14000b589  jns     loc_14000B79E
0x14000b58f  mov     rax, [rbp+0B0h+var_100]
0x14000b593  test    rax, rax
0x14000b596  jz      loc_14000B82D
0x14000b59c  mov     eax, [rax+30h]
0x14000b59f  inc     eax
0x14000b5a1  mov     [rbp+0B0h+var_130], eax
0x14000b5a4  cmp     [rbp+0B0h+var_128], 0FFh
0x14000b5ab  mov     ebx, 0A0h
0x14000b5b0  cmovnz  ebx, [rbp+0B0h+var_128]
0x14000b5b4  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x14000b5b8  lea     rcx, [rsp+1B0h+var_160]; this
0x14000b5bd  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14000b5c2  test    eax, eax
0x14000b5c4  jnz     loc_14000B96F
0x14000b5ca  mov     rbx, r13
0x14000b5cd  nop     dword ptr [rax]
0x14000b5d0  mov     rcx, [rbp+rbx*8+0B0h+pv]; pv
0x14000b5d5  test    rcx, rcx
0x14000b5d8  jnz     loc_14000B75B
0x14000b5de  inc     rbx
0x14000b5e1  cmp     rbx, 0Fh
0x14000b5e5  jnz     short loc_14000B5D0
0x14000b5e7  xor     r8d, r8d; nSize
0x14000b5ea  xor     edx, edx; lpDst
0x14000b5ec  mov     rcx, r15; lpSrc
0x14000b5ef  call    cs:__imp_ExpandEnvironmentStringsW
0x14000b5f5  mov     r13d, eax
0x14000b5f8  test    eax, eax
0x14000b5fa  jz      loc_14000B9B4
0x14000b600  mov     r12, [rbp+0B0h+pExceptionObject]
0x14000b607  mov     rbx, [r12+20h]
0x14000b60c  mov     qword ptr [r12+20h], 0
0x14000b615  mov     [rbp+0B0h+var_40], rbx
0x14000b619  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14000b620  mov     [rbp+0B0h+var_48], rax
0x14000b624  cmp     r13d, 1
0x14000b628  jz      short loc_14000B66C
0x14000b62a  lea     eax, [r13-1]
0x14000b62e  lea     rdx, ds:2[rax*2]; uBytes
0x14000b636  xor     ecx, ecx; uFlags
0x14000b638  call    cs:__imp_LocalAlloc
0x14000b63e  mov     [r12+20h], rax
0x14000b643  test    rax, rax
0x14000b646  jz      loc_14000BA1B
0x14000b64c  mov     r8d, r13d; nSize
0x14000b64f  mov     rdx, rax; lpDst
0x14000b652  mov     rcx, r15; lpSrc
0x14000b655  call    cs:__imp_ExpandEnvironmentStringsW
0x14000b65b  test    eax, eax
0x14000b65d  jz      loc_14000BA83
0x14000b663  cmp     eax, r13d
0x14000b666  ja      loc_14000BA83
0x14000b66c  test    rbx, rbx
0x14000b66f  jz      short loc_14000B67B
0x14000b671  mov     rcx, rbx; hMem
0x14000b674  call    cs:__imp_LocalFree
  ... truncated ...
```
