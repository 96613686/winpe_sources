# CVssDeletingWriter::ExpandFilesDirect(CVssDeletingWriter::ToDeleteFile &,bool,std::back_insert_iterator<std::vector<CVssDeletingWriter::ToDeleteFile,std::allocator<CVssDeletingWriter::ToDeleteFile>>>,unsigned __int64,unsigned __int64,bool)

- ea: `0x14000f1d0`
- end: `0x14000fb94`
- name: `?ExpandFilesDirect@CVssDeletingWriter@@IEAAXAEAUToDeleteFile@1@_NV?$back_insert_iterator@V?$vector@UToDeleteFile@CVssDeletingWriter@@V?$allocator@UToDeleteFile@CVssDeletingWriter@@@std@@@std@@@std@@_K31@Z`
- size: `2500`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000c84c`
- `0x14000e670`
- `0x14000f1d0`
- `0x140015fb0`

## callees

- `0x140006020`
- `0x14000bba0`
- `0x14000e188`
- `0x14000e440`
- `0x14000e640`
- `0x14000f1d0`
- `0x140010170`
- `0x140010200`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013c60`
- `0x1400326c0`
- `0x1400330fc`
- `0x140034f10`
- `0x140091560`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400d0890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f4c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f8b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f4c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f8b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000f5bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000f65c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000f6f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000f5bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000f65c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000f6f2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000f3d4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000f3d4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000f4db`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000f4db`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000f4e8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000f4e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000f492`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000f492`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000f2a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000f2a6`
- `VssTrace!__imp_VssTraceMessage` at `0x14000fa34`
- `VssTrace!__imp_VssTraceMessage` at `0x14000fa34`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000f887`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000f887`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000f2ed`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000f2ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f46f`

## string_xrefs

- `0x14000f22a`: `CVssDeletingWriter::ExpandFilesDirect`
- `0x14000f408`: `CVssDeletingWriter::ExpandFilesDirect`
- `0x14000f7c5`: `CVssDeletingWriter::ExpandFilesDirect`
- `0x14000f8ff`: `CVssDeletingWriter::ExpandFilesDirect`
- `0x14000fa57`: `CVssDeletingWriter::ExpandFilesDirect`
- `0x14000f21e`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000f3fc`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000f7b9`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000f8f3`: `base\stor\vss\modules\writers\deletewriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CVssDeletingWriter::ExpandFilesDirect(
        CVssDeletingWriter *a1,
        __int64 a2,
        char a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7)
{
  CVssDeletingWriter *v10; // r14
  __int64 v11; // rax
  int v12; // edi
  __int64 i; // rdi
  void *v14; // rcx
  int v15; // edi
  HANDLE FirstFileW; // r15
  ULONGLONG TickCount64; // rax
  ULONGLONG v18; // rsi
  __int16 *v19; // r14
  __int16 *v20; // rdi
  __int64 v21; // rsi
  unsigned __int64 v22; // rsi
  _WORD *v23; // rdx
  __int64 v24; // rcx
  __int16 v25; // ax
  _WORD *v26; // rcx
  __int64 v27; // rdi
  unsigned __int64 v28; // rdi
  WCHAR *v29; // r8
  __int64 v30; // rcx
  WCHAR *cFileName; // rdx
  WCHAR v32; // ax
  WCHAR *v33; // rcx
  __int64 v34; // rdi
  unsigned __int64 v35; // rdi
  _WORD *v36; // rdx
  __int64 v37; // rcx
  __int16 v38; // ax
  _WORD *v39; // rcx
  struct CVssDebugInfo *v40; // rax
  struct CVssDebugInfo *v41; // rax
  CVssDebugInfo *v42; // rax
  int v43; // edi
  __int64 v44; // r8
  char v45; // r9
  int v46; // r8d
  __int64 pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  CVssDeletingWriter *v49; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v50; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v51; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v52; // [rsp+78h] [rbp-88h]
  int v53; // [rsp+80h] [rbp-80h]
  int v54; // [rsp+84h] [rbp-7Ch]
  int v55; // [rsp+88h] [rbp-78h]
  LPVOID pv[15]; // [rsp+90h] [rbp-70h] BYREF
  int v57; // [rsp+108h] [rbp+8h]
  __int16 v58; // [rsp+110h] [rbp+10h] BYREF
  char v59; // [rsp+112h] [rbp+12h]
  void **v60; // [rsp+118h] [rbp+18h] BYREF
  _WORD *v61; // [rsp+120h] [rbp+20h]
  void **v62; // [rsp+128h] [rbp+28h] BYREF
  WCHAR *v63; // [rsp+130h] [rbp+30h]
  DWORD nFileSizeLow; // [rsp+138h] [rbp+38h]
  DWORD nFileSizeHigh; // [rsp+13Ch] [rbp+3Ch]
  void **v66; // [rsp+140h] [rbp+40h] BYREF
  _WORD *v67; // [rsp+148h] [rbp+48h]
  ULONGLONG v68; // [rsp+150h] [rbp+50h]
  unsigned __int64 v69; // [rsp+160h] [rbp+60h] BYREF
  int v70; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v71; // [rsp+170h] [rbp+70h]
  const unsigned __int16 *v72; // [rsp+178h] [rbp+78h]
  unsigned int v73; // [rsp+180h] [rbp+80h]
  unsigned int v74; // [rsp+184h] [rbp+84h]
  const wchar_t *v75; // [rsp+188h] [rbp+88h]
  unsigned int v76; // [rsp+190h] [rbp+90h]
  DWORD TickCount; // [rsp+194h] [rbp+94h]
  int v78; // [rsp+198h] [rbp+98h]
  __int128 v79; // [rsp+1A0h] [rbp+A0h]
  __int128 v80; // [rsp+1B0h] [rbp+B0h]
  __int64 v81; // [rsp+1C0h] [rbp+C0h]
  void **v82; // [rsp+1D0h] [rbp+D0h]
  HANDLE v83; // [rsp+1D8h] [rbp+D8h]
  char v84[168]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v85[168]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v86[176]; // [rsp+330h] [rbp+230h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+3E0h] [rbp+2E0h] BYREF
  WCHAR FileName[264]; // [rsp+630h] [rbp+530h] BYREF

  v10 = a1;
  v49 = a1;
  pExceptionObject = a5;
  v50 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v51 = L"CVssDeletingWriter::ExpandFilesDirect";
  v52 = L"WRTDELET";
  v53 = 1030;
  v54 = 4;
  v55 = 255;
  v57 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v70 = 0;
  v75 = L"CVssDeletingWriter::ExpandFilesDirect";
  v71 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v72 = L"WRTDELET";
  v73 = 1030;
  v74 = 4;
  TickCount = GetTickCount();
  v78 = 255;
  v69 = 0xFFFFFFFF00000000uLL;
  v81 = 0;
  v79 = 0;
  v80 = 0;
  v48 = 0;
  if ( (int)VssGetTracingContextPerThread(&v48) < 0 || (int)VssSetTracingContextPerThread(&v69) < 0 )
  {
    v11 = v81;
  }
  else
  {
    v11 = v48;
    v81 = v48;
  }
  if ( v11 )
    v76 = *(_DWORD *)(v11 + 48) + 1;
  else
    v76 = 0;
  v12 = 160;
  if ( v78 != 255 )
    v12 = v78;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v69, v74) )
    VssTraceMessage(v71, v72, v73, v76, v74, v75, L"ENTER", v12, 0);
  if ( HIBYTE(v57) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v14 = pv[i];
      if ( v14 )
      {
        CoTaskMemFree(v14);
        pv[i] = 0;
      }
    }
  }
  if ( a7 && !CVssDeletingWriter::FixupSnapshotVolumeSpecification(v10, (struct CVssDeletingWriter::ToDeleteFile *)a2) )
    goto LABEL_26;
  if ( !a3 )
  {
    if ( *(_QWORD *)(a4 + 8) == *(_QWORD *)(a4 + 16) )
    {
      std::vector<CVssDeletingWriter::ToDeleteFile>::_Emplace_reallocate<CVssDeletingWriter::ToDeleteFile const &>(
        (struct CVssDeletingWriter::ToDeleteFile **)a4,
        *(struct CVssDeletingWriter::ToDeleteFile **)(a4 + 8),
        (const struct CVssDeletingWriter::ToDeleteFile *)a2);
    }
    else
    {
      CVssDeletingWriter::ToDeleteFile::ToDeleteFile(
        *(CVssDeletingWriter::ToDeleteFile **)(a4 + 8),
        (const struct CVssDeletingWriter::ToDeleteFile *)a2);
      *(_QWORD *)(a4 + 8) += 72LL;
    }
    goto LABEL_26;
  }
  v15 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", *(_QWORD *)(a2 + 16), L"*");
  v70 = v15;
  if ( v15 < 0 )
  {
    v50 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
    v51 = L"CVssDeletingWriter::ExpandFilesDirect";
    v52 = L"WRTDELET";
    v53 = 1058;
    v54 = 4;
    v55 = 255;
    v57 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::Trace(&v69, &v50, L"StringCchPrintf failed with 0x%08lx", (unsigned int)v15);
    goto LABEL_26;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v82 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int FindClose(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v83 = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v50 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
    v51 = L"CVssDeletingWriter::ExpandFilesDirect";
    v52 = L"WRTDELET";
    v53 = 1066;
    v54 = 4;
    v55 = 255;
    v57 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::Trace(&v69, &v50, L"FindFirstFile(%s) returned nothing", FileName);
    goto LABEL_26;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x400) != 0 )
      goto LABEL_24;
    TickCount64 = GetTickCount64();
    v18 = TickCount64;
    if ( a6 != -1 && TickCount64 > a6 + pExceptionObject )
      break;
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( *(_BYTE *)a2
        && (unsigned int)_o__wcsicmp(FindFileData.cFileName, L".")
        && (unsigned int)_o__wcsicmp(FindFileData.cFileName, L"..") )
      {
        v43 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", *(_QWORD *)(a2 + 16), FindFileData.cFileName);
        v70 = v43;
        if ( v43 >= 0 )
        {
          CVssDeletingWriter::ToDeleteFile::ToDeleteFile(
            (CVssDeletingWriter::ToDeleteFile *)&v58,
            1,
            v44,
            v45,
            v18 - pExceptionObject,
            FileName,
            *(const unsigned __int16 **)(a2 + 32),
            *(const unsigned __int16 **)(a2 + 56));
          LOBYTE(v46) = 1;
          CVssDeletingWriter::ExpandFilesDirect((_DWORD)v10, (unsigned int)&v58, v46, a4, pExceptionObject, a6, 0);
          CVssDeletingWriter::ToDeleteFile::~ToDeleteFile((CVssDeletingWriter::ToDeleteFile *)&v58);
        }
        else
        {
          v50 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
          v51 = L"CVssDeletingWriter::ExpandFilesDirect";
          v52 = L"WRTDELET";
          v53 = 1107;
          v54 = 4;
          v55 = 255;
          v57 = 0x1000000;
          memset_0(pv, 0, sizeof(pv));
          CVssFunctionTracer::Trace(&v69, &v50, L"StringCchPrintf failed with 0x%08lx", (unsigned int)v43);
        }
      }
    }
    else if ( CVssDeletingWriter::WildcardMatches(v10, *(const unsigned __int16 **)(a2 + 32), FindFileData.cFileName) )
    {
      v19 = *(__int16 **)(a2 + 56);
      v20 = *(__int16 **)(a2 + 16);
      v58 = 0;
      v59 = 0;
      v61 = 0;
      v60 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
      v63 = 0;
      v62 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
      nFileSizeLow = FindFileData.nFileSizeLow;
      nFileSizeHigh = FindFileData.nFileSizeHigh;
      v67 = 0;
      v66 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
      v68 = v18 - pExceptionObject;
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v60);
      v22 = v21 + 1;
      v23 = LocalAlloc(0, 2 * v22);
      v61 = v23;
      if ( !v23 )
      {
        LODWORD(pExceptionObject) = -2147024882;
        throw (long *)&pExceptionObject;
      }
      if ( !v22 )
        goto LABEL_90;
      if ( v22 > 0x7FFFFFFF )
      {
        *v23 = 0;
LABEL_90:
        CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v60);
        LODWORD(pExceptionObject) = -2147418113;
        throw (long *)&pExceptionObject;
      }
      v24 = 2147483646;
      do
      {
        if ( !v24 )
          break;
        v25 = *v20;
        if ( !*v20 )
          break;
        ++v20;
        *v23++ = v25;
        --v24;
        --v22;
      }
      while ( v22 );
      v26 = v23 - 1;
      if ( v22 )
        v26 = v23;
      *v26 = 0;
      if ( !v22 )
        goto LABEL_90;
      v27 = -1;
      do
        ++v27;
      while ( FindFileData.cFileName[v27] );
      CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v62);
      v28 = v27 + 1;
      v29 = (WCHAR *)LocalAlloc(0, 2 * v28);
      v63 = v29;
      if ( !v29 )
      {
        LODWORD(pExceptionObject) = -2147024882;
        throw (long *)&pExceptionObject;
      }
      if ( !v28 )
        goto LABEL_87;
      if ( v28 > 0x7FFFFFFF )
      {
        *v29 = 0;
LABEL_87:
        CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v62);
        LODWORD(pExceptionObject) = -2147418113;
        throw (long *)&pExceptionObject;
      }
      v30 = 2147483646;
      cFileName = FindFileData.cFileName;
      do
      {
        if ( !v30 )
          break;
        v32 = *cFileName;
        if ( !*cFileName )
          break;
        ++cFileName;
        *v29++ = v32;
        --v30;
        --v28;
      }
      while ( v28 );
      v33 = v29 - 1;
      if ( v28 )
        v33 = v29;
      *v33 = 0;
      if ( !v28 )
        goto LABEL_87;
      v34 = -1;
      do
        ++v34;
      while ( v19[v34] );
      CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v66);
      v35 = v34 + 1;
      v36 = LocalAlloc(0, 2 * v35);
      v67 = v36;
      if ( !v36 )
      {
        LODWORD(pExceptionObject) = -2147024882;
        throw (long *)&pExceptionObject;
      }
      if ( !v35 )
        goto LABEL_84;
      if ( v35 > 0x7FFFFFFF )
      {
        *v36 = 0;
LABEL_84:
        CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v66);
        LODWORD(pExceptionObject) = -2147418113;
        throw (long *)&pExceptionObject;
      }
      v37 = 2147483646;
      do
      {
        if ( !v37 )
          break;
        v38 = *v19;
        if ( !*v19 )
          break;
        ++v19;
        *v36++ = v38;
        --v37;
        --v35;
      }
      while ( v35 );
      v39 = v36 - 1;
      if ( v35 )
        v39 = v36;
      *v39 = 0;
      if ( !v35 )
        goto LABEL_84;
      if ( *(_QWORD *)(a4 + 8) == *(_QWORD *)(a4 + 16) )
      {
        std::vector<CVssDeletingWriter::ToDeleteFile>::_Emplace_reallocate<CVssDeletingWriter::ToDeleteFile const &>(
          (struct CVssDeletingWriter::ToDeleteFile **)a4,
          *(struct CVssDeletingWriter::ToDeleteFile **)(a4 + 8),
          (const struct CVssDeletingWriter::ToDeleteFile *)&v58);
      }
      else
      {
        CVssDeletingWriter::ToDeleteFile::ToDeleteFile(
          *(CVssDeletingWriter::ToDeleteFile **)(a4 + 8),
          (const struct CVssDeletingWriter::ToDeleteFile *)&v58);
        *(_QWORD *)(a4 + 8) += 72LL;
      }
      CVssDeletingWriter::ToDeleteFile::~ToDeleteFile((CVssDeletingWriter::ToDeleteFile *)&v58);
      v10 = v49;
    }
LABEL_24:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_25;
  }
  v50 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v51 = L"CVssDeletingWriter::ExpandFilesDirect";
  v52 = L"WRTDELET";
  v53 = 1083;
  v54 = 4;
  v55 = 255;
  v57 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v40 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v50, (CVssDebugInfo *)v86, *(_WORD **)(a2 + 16));
  v41 = CVssDebugInfo::operator<<(v40, (CVssDebugInfo *)v85, *(_WORD **)(a2 + 32));
  v42 = CVssDebugInfo::operator<<(v41, (CVssDebugInfo *)v84, *(_WORD **)(a2 + 56));
  CVssFunctionTracer::LogError((__int64)&v69, 0x201Bu, (__int64)v42, 4u);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v85);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v86);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v50);
LABEL_25:
  FindClose(FirstFileW);
LABEL_26:
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v69);
}

```

## disassembly

```asm
0x14000f1d0  mov     [rsp-8+arg_10], rbx
0x14000f1d5  push    rbp
0x14000f1d6  push    rsi
0x14000f1d7  push    rdi
0x14000f1d8  push    r12
0x14000f1da  push    r13
0x14000f1dc  push    r14
0x14000f1de  push    r15
0x14000f1e0  lea     rbp, [rsp-750h]
0x14000f1e8  sub     rsp, 850h
0x14000f1ef  mov     rax, cs:__security_cookie
0x14000f1f6  xor     rax, rsp
0x14000f1f9  mov     [rbp+780h+var_40], rax
0x14000f200  mov     rbx, r9
0x14000f203  movzx   esi, r8b
0x14000f207  mov     r13, rdx
0x14000f20a  mov     r14, rcx
0x14000f20d  mov     [rsp+880h+var_820], rcx
0x14000f212  mov     rax, [rbp+780h+arg_20]
0x14000f219  mov     [rsp+880h+pExceptionObject], rax
0x14000f21e  lea     r15, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x14000f225  mov     [rsp+880h+var_818], r15
0x14000f22a  lea     rax, aCvssdeletingwr_11; "CVssDeletingWriter::ExpandFilesDirect"
0x14000f231  mov     [rsp+880h+var_810], rax
0x14000f236  lea     rax, aWrtdelet; "WRTDELET"
0x14000f23d  mov     [rsp+880h+var_808], rax
0x14000f242  mov     [rbp+780h+var_800], 406h
0x14000f249  mov     [rbp+780h+var_7FC], 4
0x14000f250  mov     [rbp+780h+var_7F8], 0FFh
0x14000f257  xor     r12d, r12d
0x14000f25a  mov     [rbp+780h+var_778], 1000000h
0x14000f261  xor     edx, edx; Val
0x14000f263  mov     r8d, 78h ; 'x'; Size
0x14000f269  lea     rcx, [rbp+780h+pv]; void *
0x14000f26d  call    memset_0
0x14000f272  mov     [rbp+780h+var_718], r12d
0x14000f276  mov     rax, [rsp+880h+var_810]
0x14000f27b  mov     [rbp+780h+var_6F8], rax
0x14000f282  mov     rax, [rsp+880h+var_818]
0x14000f287  mov     [rbp+780h+var_710], rax
0x14000f28b  mov     rax, [rsp+880h+var_808]
0x14000f290  mov     [rbp+780h+var_708], rax
0x14000f294  mov     eax, [rbp+780h+var_800]
0x14000f297  mov     [rbp+780h+var_700], eax
0x14000f29d  mov     eax, [rbp+780h+var_7FC]
0x14000f2a0  mov     [rbp+780h+var_6FC], eax
0x14000f2a6  call    cs:__imp_GetTickCount
0x14000f2ac  mov     [rbp+780h+var_6EC], eax
0x14000f2b2  mov     [rbp+780h+var_71C], 0FFFFFFFFh
0x14000f2b9  mov     eax, [rbp+780h+var_7F8]
0x14000f2bc  mov     [rbp+780h+var_6E8], eax
0x14000f2c2  mov     [rbp+780h+var_720], r12d
0x14000f2c6  mov     [rbp+780h+var_6C0], r12
0x14000f2cd  xorps   xmm0, xmm0
0x14000f2d0  movdqa  [rbp+780h+var_6E0], xmm0
0x14000f2d8  xorps   xmm1, xmm1
0x14000f2db  movdqa  [rbp+780h+var_6D0], xmm1
0x14000f2e3  mov     [rsp+880h+var_828], r12
0x14000f2e8  lea     rcx, [rsp+880h+var_828]
0x14000f2ed  call    cs:__imp_VssGetTracingContextPerThread
0x14000f2f3  test    eax, eax
0x14000f2f5  jns     loc_14000F883
0x14000f2fb  mov     rax, [rbp+780h+var_6C0]
0x14000f302  test    rax, rax
0x14000f305  jz      loc_14000F9C8
0x14000f30b  mov     eax, [rax+30h]
0x14000f30e  inc     eax
0x14000f310  mov     [rbp+780h+var_6F0], eax
0x14000f316  mov     edi, 0A0h
0x14000f31b  cmp     [rbp+780h+var_6E8], 0FFh
0x14000f325  cmovnz  edi, [rbp+780h+var_6E8]
0x14000f32c  mov     edx, [rbp+780h+var_6FC]; unsigned int
0x14000f332  lea     rcx, [rbp+780h+var_720]; this
0x14000f336  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14000f33b  test    eax, eax
0x14000f33d  jnz     loc_14000F9F3
0x14000f343  cmp     byte ptr [rbp+780h+var_778+3], r12b
0x14000f347  jz      short loc_14000F367
0x14000f349  mov     rdi, r12
0x14000f34c  nop     dword ptr [rax+00h]
0x14000f350  mov     rcx, [rbp+rdi*8+780h+pv]; pv
0x14000f355  test    rcx, rcx
0x14000f358  jnz     loc_14000F46F
0x14000f35e  inc     rdi
0x14000f361  cmp     rdi, 0Fh
0x14000f365  jnz     short loc_14000F350
0x14000f367  cmp     [rbp+780h+arg_30], 0
0x14000f36e  jnz     loc_14000F790
0x14000f374  test    sil, sil
0x14000f377  jz      loc_14000F9D4
0x14000f37d  lea     rax, asc_1400FA76C; "*"
0x14000f384  mov     [rsp+880h+var_860], rax
0x14000f389  mov     r9, [r13+10h]
0x14000f38d  lea     r8, aSS; "%s\\%s"
0x14000f394  mov     edx, 104h; unsigned __int64
0x14000f399  lea     rcx, [rbp+780h+FileName]; unsigned __int16 *
0x14000f3a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f3a5  mov     edi, eax
0x14000f3a7  mov     [rbp+780h+var_718], eax
0x14000f3aa  test    eax, eax
0x14000f3ac  js      loc_14000FA52
0x14000f3b2  xor     edx, edx; Val
0x14000f3b4  mov     r8d, 250h; Size
0x14000f3ba  lea     rcx, [rbp+780h+FindFileData]; void *
0x14000f3c1  call    memset_0
0x14000f3c6  lea     rdx, [rbp+780h+FindFileData]; lpFindFileData
0x14000f3cd  lea     rcx, [rbp+780h+FileName]; lpFileName
0x14000f3d4  call    cs:__imp_FindFirstFileW
0x14000f3da  mov     r15, rax
0x14000f3dd  lea     rax, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?FindClose@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&FindClose(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x14000f3e4  mov     [rbp+780h+var_6B0], rax
0x14000f3eb  mov     [rbp+780h+var_6A8], r15
0x14000f3f2  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14000f3f6  jnz     loc_14000F47F
0x14000f3fc  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x14000f403  mov     [rsp+880h+var_818], rax
0x14000f408  lea     rax, aCvssdeletingwr_11; "CVssDeletingWriter::ExpandFilesDirect"
0x14000f40f  mov     [rsp+880h+var_810], rax
0x14000f414  lea     rax, aWrtdelet; "WRTDELET"
0x14000f41b  mov     [rsp+880h+var_808], rax
0x14000f420  mov     [rbp+780h+var_800], 42Ah
0x14000f427  mov     [rbp+780h+var_7FC], 4
0x14000f42e  mov     [rbp+780h+var_7F8], 0FFh
0x14000f435  mov     [rbp+780h+var_778], 1000000h
0x14000f43c  xor     edx, edx; Val
0x14000f43e  mov     r8d, 78h ; 'x'; Size
0x14000f444  lea     rcx, [rbp+780h+pv]; void *
0x14000f448  call    memset_0
0x14000f44d  lea     r9, [rbp+780h+FileName]
0x14000f454  lea     r8, aFindfirstfileS; "FindFirstFile(%s) returned nothing"
0x14000f45b  lea     rdx, [rsp+880h+var_818]
0x14000f460  lea     rcx, [rbp+780h+var_720]
0x14000f464  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14000f469  nop
0x14000f46a  jmp     loc_14000F4EF
0x14000f46f  call    cs:__imp_CoTaskMemFree
0x14000f475  mov     [rbp+rdi*8+780h+pv], r12
0x14000f47a  jmp     loc_14000F35E
0x14000f47f  mov     r12, [rbp+780h+arg_28]
0x14000f486  test    [rbp+780h+FindFileData.dwFileAttributes], 400h
0x14000f490  jnz     short loc_14000F4D1
0x14000f492  call    cs:__imp_GetTickCount64
0x14000f498  mov     rsi, rax
0x14000f49b  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14000f49f  jnz     loc_14000F7A8
0x14000f4a5  test    byte ptr [rbp+780h+FindFileData.dwFileAttributes], 10h
0x14000f4ac  jz      short loc_14000F522
0x14000f4ae  cmp     byte ptr [r13+0], 0
0x14000f4b3  jz      short loc_14000F4D1
0x14000f4b5  lea     rdx, asc_1400F9C8C; "."
0x14000f4bc  lea     rcx, [rbp+780h+FindFileData.cFileName]
0x14000f4c3  call    cs:__imp__o__wcsicmp
0x14000f4c9  test    eax, eax
0x14000f4cb  jnz     loc_14000F8A6
0x14000f4d1  lea     rdx, [rbp+780h+FindFileData]; lpFindFileData
0x14000f4d8  mov     rcx, r15; hFindFile
0x14000f4db  call    cs:__imp_FindNextFileW
0x14000f4e1  test    eax, eax
0x14000f4e3  jnz     short loc_14000F486
0x14000f4e5  mov     rcx, r15; hFindFile
0x14000f4e8  call    cs:__imp_FindClose
0x14000f4ee  nop
0x14000f4ef  lea     rcx, [rbp+780h+var_720]; this
0x14000f4f3  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14000f4f8  mov     rcx, [rbp+780h+var_40]
0x14000f4ff  xor     rcx, rsp; StackCookie
0x14000f502  call    __security_check_cookie
0x14000f507  mov     rbx, [rsp+880h+arg_10]
0x14000f50f  add     rsp, 850h
0x14000f516  pop     r15
0x14000f518  pop     r14
0x14000f51a  pop     r13
0x14000f51c  pop     r12
0x14000f51e  pop     rdi
0x14000f51f  pop     rsi
0x14000f520  pop     rbp
0x14000f521  retn
0x14000f522  lea     r8, [rbp+780h+FindFileData.cFileName]; unsigned __int16 *
0x14000f529  mov     rdx, [r13+20h]; unsigned __int16 *
0x14000f52d  mov     rcx, r14; this
0x14000f530  call    ?WildcardMatches@CVssDeletingWriter@@IEAA_NPEBG0@Z; CVssDeletingWriter::WildcardMatches(ushort const *,ushort const *)
0x14000f535  test    al, al
0x14000f537  jz      short loc_14000F4D1
0x14000f539  mov     r14, [r13+38h]
0x14000f53d  mov     rdi, [r13+10h]
0x14000f541  mov     ecx, [rbp+780h+FindFileData.nFileSizeHigh]
0x14000f547  mov     eax, [rbp+780h+FindFileData.nFileSizeLow]
0x14000f54d  mov     [rbp+780h+var_770], 0
0x14000f553  mov     [rbp+780h+var_76E], 0
0x14000f557  mov     [rbp+780h+var_760], 0
0x14000f55f  lea     rdx, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14000f566  mov     [rbp+780h+var_768], rdx
0x14000f56a  mov     [rbp+780h+var_750], 0
0x14000f572  mov     [rbp+780h+var_758], rdx
0x14000f576  mov     [rbp+780h+var_748], eax
0x14000f579  mov     [rbp+780h+var_744], ecx
0x14000f57c  mov     [rbp+780h+var_738], 0
0x14000f584  mov     [rbp+780h+var_740], rdx
0x14000f588  sub     rsi, [rsp+880h+pExceptionObject]
0x14000f58d  mov     [rbp+780h+var_730], rsi
0x14000f591  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x14000f598  nop     dword ptr [rax+rax+00000000h]
0x14000f5a0  inc     rsi
0x14000f5a3  cmp     word ptr [rdi+rsi*2], 0
0x14000f5a8  jnz     short loc_14000F5A0
0x14000f5aa  lea     rcx, [rbp+780h+var_768]
0x14000f5ae  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void * (*)(void *),&LocalFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x14000f5b3  inc     rsi
0x14000f5b6  lea     rdx, [rsi+rsi]; uBytes
0x14000f5ba  xor     ecx, ecx; uFlags
0x14000f5bc  call    cs:__imp_LocalAlloc
0x14000f5c2  mov     rdx, rax
0x14000f5c5  mov     [rbp+780h+var_760], rax
0x14000f5c9  test    rax, rax
0x14000f5cc  jz      loc_14000FB7A
0x14000f5d2  test    rsi, rsi
0x14000f5d5  jz      loc_14000FB57
0x14000f5db  cmp     rsi, 7FFFFFFFh
0x14000f5e2  ja      loc_14000FB52
0x14000f5e8  mov     ecx, 7FFFFFFEh
0x14000f5ed  nop     dword ptr [rax]
0x14000f5f0  test    rcx, rcx
0x14000f5f3  jz      short loc_14000F611
0x14000f5f5  movzx   eax, word ptr [rdi]
0x14000f5f8  test    ax, ax
0x14000f5fb  jz      short loc_14000F611
0x14000f5fd  add     rdi, 2
0x14000f601  mov     [rdx], ax
0x14000f604  add     rdx, 2
0x14000f608  dec     rcx
0x14000f60b  sub     rsi, 1
0x14000f60f  jnz     short loc_14000F5F0
0x14000f611  lea     rcx, [rdx-2]
0x14000f615  test    rsi, rsi
0x14000f618  cmovnz  rcx, rdx
0x14000f61c  xor     eax, eax
0x14000f61e  mov     [rcx], ax
0x14000f621  test    rsi, rsi
0x14000f624  jz      loc_14000FB57
0x14000f62a  lea     rax, [rbp+780h+FindFileData.cFileName]
0x14000f631  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14000f638  nop     dword ptr [rax+rax+00000000h]
0x14000f640  inc     rdi
0x14000f643  cmp     word ptr [rax+rdi*2], 0
0x14000f648  jnz     short loc_14000F640
0x14000f64a  lea     rcx, [rbp+780h+var_758]
0x14000f64e  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void * (*)(void *),&LocalFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x14000f653  inc     rdi
0x14000f656  lea     rdx, [rdi+rdi]; uBytes
0x14000f65a  xor     ecx, ecx; uFlags
0x14000f65c  call    cs:__imp_LocalAlloc
0x14000f662  mov     r8, rax
0x14000f665  mov     [rbp+780h+var_750], rax
0x14000f669  test    rax, rax
0x14000f66c  jz      loc_14000FB38
0x14000f672  test    rdi, rdi
0x14000f675  jz      loc_14000FB15
0x14000f67b  cmp     rdi, 7FFFFFFFh
0x14000f682  ja      loc_14000FB0F
0x14000f688  mov     ecx, 7FFFFFFEh
0x14000f68d  lea     rdx, [rbp+780h+FindFileData.cFileName]
0x14000f694  test    rcx, rcx
0x14000f697  jz      short loc_14000F6B6
0x14000f699  movzx   eax, word ptr [rdx]
0x14000f69c  test    ax, ax
0x14000f69f  jz      short loc_14000F6B6
0x14000f6a1  add     rdx, 2
0x14000f6a5  mov     [r8], ax
0x14000f6a9  add     r8, 2
0x14000f6ad  dec     rcx
0x14000f6b0  sub     rdi, 1
0x14000f6b4  jnz     short loc_14000F694
0x14000f6b6  lea     rcx, [r8-2]
0x14000f6ba  test    rdi, rdi
0x14000f6bd  cmovnz  rcx, r8
0x14000f6c1  xor     eax, eax
0x14000f6c3  mov     [rcx], ax
0x14000f6c6  test    rdi, rdi
0x14000f6c9  jz      loc_14000FB15
0x14000f6cf  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14000f6d6  inc     rdi
0x14000f6d9  cmp     [r14+rdi*2], ax
0x14000f6de  jnz     short loc_14000F6D6
0x14000f6e0  lea     rcx, [rbp+780h+var_740]
0x14000f6e4  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void * (*)(void *),&LocalFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x14000f6e9  inc     rdi
0x14000f6ec  lea     rdx, [rdi+rdi]; uBytes
0x14000f6f0  xor     ecx, ecx; uFlags
0x14000f6f2  call    cs:__imp_LocalAlloc
0x14000f6f8  mov     rdx, rax
0x14000f6fb  mov     [rbp+780h+var_738], rax
0x14000f6ff  test    rax, rax
0x14000f702  jz      loc_14000FAF5
0x14000f708  test    rdi, rdi
0x14000f70b  jz      loc_14000FAD2
0x14000f711  cmp     rdi, 7FFFFFFFh
0x14000f718  ja      loc_14000FACD
0x14000f71e  mov     ecx, 7FFFFFFEh
0x14000f723  test    rcx, rcx
0x14000f726  jz      short loc_14000F745
  ... truncated ...
```
