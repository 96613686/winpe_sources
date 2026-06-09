# CVssDeletingWriter::ExpandFilesAllVolumes(CVssDeletingWriter::ToDeleteFile &,ushort *,bool,bool,__int64,__int64,__int64,std::back_insert_iterator<std::vector<CVssDeletingWriter::ToDeleteFile,std::allocator<CVssDeletingWriter::ToDeleteFile>>>)

- ea: `0x14000e670`
- end: `0x14000f1bc`
- name: `?ExpandFilesAllVolumes@CVssDeletingWriter@@IEAAXAEAUToDeleteFile@1@PEAG_N2_J33V?$back_insert_iterator@V?$vector@UToDeleteFile@CVssDeletingWriter@@V?$allocator@UToDeleteFile@CVssDeletingWriter@@@std@@@std@@@std@@@Z`
- size: `2892`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x14000c84c`

## callees

- `0x14000bba0`
- `0x14000e188`
- `0x14000e640`
- `0x14000e670`
- `0x14000f1d0`
- `0x140010170`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140025b00`
- `0x14003ade4`
- `0x140091560`
- `0x1400916f0`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000eb57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ec8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f06c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f0f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000eb57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ec8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f06c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f0f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000eac2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ead2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000eae2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000eac2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ead2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000eae2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000e8f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000e984`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000ea13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000e8f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000e984`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000ea13`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x14000eaff`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x14000eaff`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x14000eb1a`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x14000eb1a`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x14000e808`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x14000e808`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x14000e841`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x14000e841`

## string_xrefs

- `0x14000e6c5`: `CVssDeletingWriter::ExpandFilesAllVolumes`
- `0x14000eae8`: `CVssDeletingWriter::ExpandFilesAllVolumes`
- `0x14000eb70`: `CVssDeletingWriter::ExpandFilesAllVolumes`
- `0x14000ec9f`: `CVssDeletingWriter::ExpandFilesAllVolumes`
- `0x14000efdf`: `CVssDeletingWriter::ExpandFilesAllVolumes`
- `0x14000f07f`: `CVssDeletingWriter::ExpandFilesAllVolumes`
- `0x14000f10d`: `CVssDeletingWriter::ExpandFilesAllVolumes`
- `0x14000e6ba`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000eb65`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000ec94`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000ee5d`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000f074`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000f0ff`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000f0d6`: `StringCchCopy fails with 0x%08lx, winerror %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CVssDeletingWriter::ExpandFilesAllVolumes(
        CVssDeletingWriter *a1,
        char *a2,
        unsigned __int16 *a3,
        char a4,
        char a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v13; // rcx
  HANDLE FirstVolumeW; // r12
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  __int16 *v18; // rsi
  __int64 v19; // rdi
  unsigned __int64 v20; // rdi
  unsigned __int16 *v21; // r8
  __int64 v22; // rcx
  unsigned __int16 *v23; // rdx
  unsigned __int16 v24; // ax
  unsigned __int16 *v25; // rcx
  __int64 v26; // rdi
  unsigned __int64 v27; // rdi
  _WORD *v28; // rdx
  __int64 v29; // rcx
  __int16 v30; // ax
  _WORD *v31; // rcx
  __int64 v32; // rdi
  unsigned __int64 v33; // rdi
  unsigned __int16 *v34; // r8
  __int64 v35; // rcx
  unsigned __int16 *v36; // rdx
  unsigned __int16 v37; // ax
  unsigned __int16 *v38; // rcx
  DWORD v39; // edi
  int v40; // esi
  __int64 v41; // rdx
  __int64 v42; // r8
  char v43; // r9
  __int64 v44; // rax
  const unsigned __int16 *v45; // r10
  unsigned __int64 v46; // rcx
  unsigned __int16 v47; // ax
  __int64 v48; // rcx
  unsigned __int16 *v49; // rax
  int v50; // edx
  __int64 v51; // r8
  DWORD v52; // ebx
  __int64 v53; // rbx
  unsigned int v54; // r15d
  const unsigned __int16 **v55; // r14
  __int64 v56; // rcx
  const wchar_t *v57; // r9
  __int64 v58; // rdx
  unsigned __int16 *v59; // rax
  unsigned __int16 *v60; // rcx
  int v61; // ecx
  wchar_t v62; // r8
  DWORD v63; // edi
  __int64 v64; // rcx
  unsigned int v65; // esi
  DWORD LastError; // ebx
  DWORD v67; // ebx
  __int64 v68; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v69; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v70; // [rsp+30h] [rbp-D0h]
  _QWORD pExceptionObject[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v72; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v73; // [rsp+51h] [rbp-AFh]
  void **v74; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v75; // [rsp+60h] [rbp-A0h]
  void **v76; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v77; // [rsp+70h] [rbp-90h]
  __int64 v78; // [rsp+78h] [rbp-88h]
  void **v79; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  __int64 v81; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v82; // [rsp+A0h] [rbp-60h]
  CVssDeletingWriter *v83; // [rsp+A8h] [rbp-58h]
  HANDLE v84; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v85; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v86; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v87; // [rsp+C8h] [rbp-38h]
  int v88; // [rsp+D0h] [rbp-30h]
  int v89; // [rsp+D4h] [rbp-2Ch]
  int v90; // [rsp+D8h] [rbp-28h]
  _BYTE v91[120]; // [rsp+E0h] [rbp-20h] BYREF
  int v92; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v93; // [rsp+160h] [rbp+60h] BYREF
  const wchar_t *v94; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v95; // [rsp+170h] [rbp+70h]
  int v96; // [rsp+178h] [rbp+78h]
  int v97; // [rsp+17Ch] [rbp+7Ch]
  int v98; // [rsp+180h] [rbp+80h]
  _BYTE v99[120]; // [rsp+188h] [rbp+88h] BYREF
  int v100; // [rsp+200h] [rbp+100h]
  LPVOID v101; // [rsp+210h] [rbp+110h] BYREF
  int v102; // [rsp+218h] [rbp+118h]
  WCHAR szVolumeName[4]; // [rsp+280h] [rbp+180h] BYREF
  const wchar_t *v104; // [rsp+288h] [rbp+188h]
  const unsigned __int16 *v105; // [rsp+290h] [rbp+190h]
  int v106; // [rsp+298h] [rbp+198h]
  int v107; // [rsp+29Ch] [rbp+19Ch]
  int v108; // [rsp+2A0h] [rbp+1A0h]
  _BYTE v109[120]; // [rsp+2A8h] [rbp+1A8h] BYREF
  int v110; // [rsp+320h] [rbp+220h]
  unsigned __int16 v111[264]; // [rsp+490h] [rbp+390h] BYREF

  v82 = a3;
  pExceptionObject[0] = a2;
  v83 = a1;
  v85 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v86 = L"CVssDeletingWriter::ExpandFilesAllVolumes";
  v87 = L"WRTDELET";
  v88 = 818;
  v89 = 4;
  v90 = 255;
  v92 = 0x1000000;
  memset_0(v91, 0, sizeof(v91));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v101, (__int64)&v85, 0);
  if ( a4 )
  {
    v13 = *((_QWORD *)a1 + 1);
    if ( !v13
      || (v55 = (const unsigned __int16 **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 56LL))(v13)) == 0 )
    {
      *(_QWORD *)szVolumeName = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
      v104 = L"CVssDeletingWriter::ExpandFilesAllVolumes";
      v105 = L"WRTDELET";
      v106 = 913;
      v107 = 4;
      v108 = 255;
      v110 = 0x1000000;
      memset_0(v109, 0, sizeof(v109));
      CVssFunctionTracer::Trace(&v101, szVolumeName, L"GetCurrentVolumeArray returns NULL");
      goto LABEL_4;
    }
    v64 = *((_QWORD *)a1 + 1);
    if ( v64 )
      v65 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 64LL))(v64);
    else
      v65 = 0;
    if ( !v65 )
    {
      v93 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
      v94 = L"CVssDeletingWriter::ExpandFilesAllVolumes";
      v95 = L"WRTDELET";
      v96 = 920;
      v97 = 4;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::Trace(&v101, &v93, L"GetCurrentVolumeArray returns 0");
      goto LABEL_4;
    }
    memset_0(v111, 0, 0x208u);
    v54 = 0;
    v53 = pExceptionObject[0];
    while ( 1 )
    {
      if ( v54 >= v65 )
        goto LABEL_4;
      v102 = StringCchCopyW(v111, 0x104u, *v55);
      if ( v102 < 0 )
      {
        LastError = GetLastError();
        v93 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v94 = L"CVssDeletingWriter::ExpandFilesAllVolumes";
        v95 = L"WRTDELET";
        v96 = 936;
        v97 = 4;
        v98 = 255;
        v100 = 0x1000000;
        memset_0(v99, 0, sizeof(v99));
        LODWORD(v68) = LastError;
        CVssFunctionTracer::Trace(
          &v101,
          &v93,
          L"StringCchCopy fails with 0x%08lx, winerror %d",
          (unsigned int)v102,
          v68);
        v53 = pExceptionObject[0];
      }
      else
      {
        v44 = -1;
        do
          ++v44;
        while ( v111[v44] );
        v45 = *(const unsigned __int16 **)(v53 + 16);
        v46 = (unsigned int)(v44 - 1);
        v47 = v111[v46];
        if ( !v45 )
        {
          if ( v47 == 92 )
          {
            if ( v46 >= 260 )
              _report_rangecheckfailure(v46 * 2, v41);
            v111[v46] = 0;
          }
LABEL_81:
          CVssDeletingWriter::ToDeleteFile::ToDeleteFile(
            (CVssDeletingWriter::ToDeleteFile *)&v72,
            *(_BYTE *)v53,
            v42,
            v43,
            a6,
            v111,
            *(const unsigned __int16 **)(v53 + 32),
            v82);
          CVssDeletingWriter::ExpandFilesDirect(v83, (__int64)&v72, a4, a9, a7, a8, a5);
          CVssDeletingWriter::ToDeleteFile::~ToDeleteFile((CVssDeletingWriter::ToDeleteFile *)&v72);
          goto LABEL_72;
        }
        if ( v47 != 92 )
        {
          v48 = 260;
          v49 = v111;
          do
          {
            if ( !*v49 )
              break;
            ++v49;
            --v48;
          }
          while ( v48 );
          v50 = -2147024809;
          if ( v48 )
            v50 = 0;
          v51 = 260 - v48;
          if ( !v48 )
          {
            v102 = v50;
LABEL_71:
            v52 = GetLastError();
            v85 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
            v86 = L"CVssDeletingWriter::ExpandFilesAllVolumes";
            v87 = L"WRTDELET";
            v88 = 957;
            v89 = 4;
            v90 = 255;
            v92 = 0x1000000;
            memset_0(v91, 0, sizeof(v91));
            LODWORD(v68) = v52;
            CVssFunctionTracer::Trace(
              &v101,
              &v85,
              L"StringCchCat fails with 0x%08lx, winerror %d",
              (unsigned int)v102,
              v68);
            v53 = pExceptionObject[0];
            goto LABEL_72;
          }
          v56 = 2147483646;
          v57 = L"\\";
          v58 = 260 - v51;
          v59 = &v111[v51];
          if ( v51 != 260 )
          {
            do
            {
              if ( !v56 )
                break;
              v62 = *v57;
              if ( !*v57 )
                break;
              ++v57;
              *v59++ = v62;
              --v56;
              --v58;
            }
            while ( v58 );
          }
          v60 = v59 - 1;
          if ( v58 )
            v60 = v59;
          *v60 = 0;
          v61 = -2147024774;
          if ( v58 )
            v61 = 0;
          v102 = v61;
          if ( !v58 )
            goto LABEL_71;
        }
        v102 = StringCchCatW(v111, 0x104u, v45);
        if ( v102 >= 0 )
          goto LABEL_81;
        v67 = GetLastError();
        *(_QWORD *)szVolumeName = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v104 = L"CVssDeletingWriter::ExpandFilesAllVolumes";
        v105 = L"WRTDELET";
        v106 = 973;
        v107 = 4;
        v108 = 255;
        v110 = 0x1000000;
        memset_0(v109, 0, sizeof(v109));
        LODWORD(v68) = v67;
        CVssFunctionTracer::Trace(
          &v101,
          szVolumeName,
          L"StringCchCat failed with 0x%08lx, winerror %d",
          (unsigned int)v102,
          v68);
        v53 = pExceptionObject[0];
      }
LABEL_72:
      ++v54;
      ++v55;
    }
  }
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(v111, 0, 0x208u);
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  v83 = (CVssDeletingWriter *)&CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int FindVolumeClose(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v84 = FirstVolumeW;
  while ( FirstVolumeW != (HANDLE)-1LL )
  {
    if ( GetDriveTypeW(szVolumeName) == 3 )
    {
      v16 = -1;
      do
        ++v16;
      while ( szVolumeName[v16] );
      v17 = (unsigned int)(v16 - 1);
      if ( szVolumeName[v17] == 92 )
      {
        if ( v17 >= 260 )
          _report_rangecheckfailure(v17 * 2, v15);
        szVolumeName[(unsigned int)(v16 - 1)] = 0;
      }
      if ( *((_QWORD *)a2 + 2)
        && (v102 = StringCchPrintfW(v111, 0x104u, L"%s\\%s", szVolumeName, *((_QWORD *)a2 + 2)), v102 < 0) )
      {
        v39 = GetLastError();
        v40 = v102;
        v85 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v86 = L"CVssDeletingWriter::ExpandFilesAllVolumes";
        v87 = L"WRTDELET";
        v88 = 871;
        v89 = 4;
        v90 = 255;
        v92 = 0x1000000;
        memset_0(v91, 0, sizeof(v91));
        LODWORD(v70) = v39;
        LODWORD(v69) = v40;
        CVssFunctionTracer::Trace(
          &v101,
          &v85,
          L"StringCchPrintf fails for %s\\%s with 0x%08lx winerror %d",
          szVolumeName,
          *((_QWORD *)a2 + 2),
          v69,
          v70);
      }
      else
      {
        v18 = (__int16 *)*((_QWORD *)a2 + 4);
        v72 = *a2;
        v73 = 0;
        v74 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
        v77 = 0;
        v76 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
        v78 = 0;
        hMem = 0;
        v79 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
        v81 = a6;
        v19 = -1;
        do
          ++v19;
        while ( v111[v19] );
        v20 = v19 + 1;
        v21 = (unsigned __int16 *)LocalAlloc(0, 2 * v20);
        v75 = v21;
        if ( !v21 )
        {
          LODWORD(pExceptionObject[0]) = -2147024882;
          throw (long *)pExceptionObject;
        }
        if ( !v20 )
          goto LABEL_97;
        if ( v20 > 0x7FFFFFFF )
        {
          *v21 = 0;
LABEL_97:
          CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v74);
          LODWORD(pExceptionObject[0]) = -2147418113;
          throw (long *)pExceptionObject;
        }
        v22 = 2147483646;
        v23 = v111;
        do
        {
          if ( !v22 )
            break;
          v24 = *v23;
          if ( !*v23 )
            break;
          ++v23;
          *v21++ = v24;
          --v22;
          --v20;
        }
        while ( v20 );
        v25 = v21 - 1;
        if ( v20 )
          v25 = v21;
        *v25 = 0;
        if ( !v20 )
          goto LABEL_97;
        v26 = -1;
        do
          ++v26;
        while ( v18[v26] );
        v27 = v26 + 1;
        v28 = LocalAlloc(0, 2 * v27);
        v77 = v28;
        if ( !v28 )
        {
          LODWORD(pExceptionObject[0]) = -2147024882;
          throw (long *)pExceptionObject;
        }
        if ( !v27 )
          goto LABEL_94;
        if ( v27 > 0x7FFFFFFF )
        {
          *v28 = 0;
LABEL_94:
          CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v76);
          LODWORD(pExceptionObject[0]) = -2147418113;
          throw (long *)pExceptionObject;
        }
        v29 = 2147483646;
        do
        {
          if ( !v29 )
            break;
          v30 = *v18;
          if ( !*v18 )
            break;
          ++v18;
          *v28++ = v30;
          --v29;
          --v27;
        }
        while ( v27 );
        v31 = v28 - 1;
        if ( v27 )
          v31 = v28;
        *v31 = 0;
        if ( !v27 )
          goto LABEL_94;
        v32 = -1;
        do
          ++v32;
        while ( a3[v32] );
        v33 = v32 + 1;
        v34 = (unsigned __int16 *)LocalAlloc(0, 2 * v33);
        hMem = v34;
        if ( !v34 )
        {
          LODWORD(pExceptionObject[0]) = -2147024882;
          throw (long *)pExceptionObject;
        }
        if ( !v33 )
          goto LABEL_91;
        if ( v33 > 0x7FFFFFFF )
        {
          *v34 = 0;
LABEL_91:
          CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v79);
          LODWORD(pExceptionObject[0]) = -2147418113;
          throw (long *)pExceptionObject;
        }
        v35 = 2147483646;
        v36 = a3;
        do
        {
          if ( !v35 )
            break;
          v37 = *v36;
          if ( !*v36 )
            break;
          ++v36;
          *v34++ = v37;
          --v35;
          --v33;
        }
        while ( v33 );
        v38 = v34 - 1;
        if ( v33 )
          v38 = v34;
        *v38 = 0;
        if ( !v33 )
          goto LABEL_91;
        CVssDeletingWriter::ExpandFilesDirect(a1, (__int64)&v72, 0, a9, a7, a8, a5);
        if ( hMem )
          LocalFree(hMem);
        if ( v77 )
          LocalFree(v77);
        if ( v75 )
          LocalFree(v75);
      }
    }
LABEL_54:
    if ( !FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) )
      goto LABEL_55;
  }
  if ( GetLastError() != 18 )
  {
    v63 = GetLastError();
    v93 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
    v94 = L"CVssDeletingWriter::ExpandFilesAllVolumes";
    v95 = L"WRTDELET";
    v96 = 839;
    v97 = 4;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    LODWORD(v68) = v63;
    CVssFunctionTracer::Trace(
      &v101,
      &v93,
      L"FindFirstVolumeW/FindNextVolumeW fails with 0x%08lx winerror %d",
      (unsigned int)v102,
      v68);
    goto LABEL_54;
  }
LABEL_55:
  if ( FirstVolumeW != (HANDLE)-1LL )
    FindVolumeClose(FirstVolumeW);
LABEL_4:
  CVssFunctionTracer::~CVssFunctionTracer(&v101);
}

```

## disassembly

```asm
0x14000e670  mov     [rsp-8+arg_18], rbx
0x14000e675  push    rbp
0x14000e676  push    rsi
0x14000e677  push    rdi
0x14000e678  push    r12
0x14000e67a  push    r13
0x14000e67c  push    r14
0x14000e67e  push    r15
0x14000e680  lea     rbp, [rsp-5B0h]
0x14000e688  sub     rsp, 6B0h
0x14000e68f  mov     rax, cs:__security_cookie
0x14000e696  xor     rax, rsp
0x14000e699  mov     [rbp+5E0h+var_40], rax
0x14000e6a0  movzx   edi, r9b
0x14000e6a4  mov     r14, r8
0x14000e6a7  mov     [rbp+5E0h+var_640], r8
0x14000e6ab  mov     r15, rdx
0x14000e6ae  mov     [rsp+6E0h+pExceptionObject], rdx
0x14000e6b3  mov     r13, rcx
0x14000e6b6  mov     [rbp+5E0h+var_638], rcx
0x14000e6ba  lea     rbx, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x14000e6c1  mov     [rbp+5E0h+var_628], rbx
0x14000e6c5  lea     rsi, aCvssdeletingwr_9; "CVssDeletingWriter::ExpandFilesAllVolum"...
0x14000e6cc  mov     [rbp+5E0h+var_620], rsi
0x14000e6d0  lea     r12, aWrtdelet; "WRTDELET"
0x14000e6d7  mov     [rbp+5E0h+var_618], r12
0x14000e6db  mov     [rbp+5E0h+var_610], 332h
0x14000e6e2  mov     [rbp+5E0h+var_60C], 4
0x14000e6e9  mov     [rbp+5E0h+var_608], 0FFh
0x14000e6f0  mov     [rbp+5E0h+var_588], 1000000h
0x14000e6f7  xor     edx, edx; Val
0x14000e6f9  mov     r8d, 78h ; 'x'; Size
0x14000e6ff  lea     rcx, [rbp+5E0h+var_600]; void *
0x14000e703  call    memset_0
0x14000e708  xor     r8d, r8d
0x14000e70b  lea     rdx, [rbp+5E0h+var_628]
0x14000e70f  lea     rcx, [rbp+5E0h+var_4D0]
0x14000e716  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14000e71b  nop
0x14000e71c  test    dil, dil
0x14000e71f  jz      loc_14000E7D4
0x14000e725  mov     rcx, [r13+8]
0x14000e729  test    rcx, rcx
0x14000e72c  jnz     loc_14000EFA4
0x14000e732  mov     qword ptr [rbp+5E0h+szVolumeName], rbx
0x14000e739  mov     [rbp+5E0h+var_458], rsi
0x14000e740  mov     [rbp+5E0h+var_450], r12
0x14000e747  mov     [rbp+5E0h+var_448], 391h
0x14000e751  mov     [rbp+5E0h+var_444], 4
0x14000e75b  mov     [rbp+5E0h+var_440], 0FFh
0x14000e765  mov     [rbp+5E0h+var_3C0], 1000000h
0x14000e76f  xor     edx, edx; Val
0x14000e771  mov     r8d, 78h ; 'x'; Size
0x14000e777  lea     rcx, [rbp+5E0h+var_438]; void *
0x14000e77e  call    memset_0
0x14000e783  lea     r8, aGetcurrentvolu_0; "GetCurrentVolumeArray returns NULL"
0x14000e78a  lea     rdx, [rbp+5E0h+szVolumeName]
0x14000e791  lea     rcx, [rbp+5E0h+var_4D0]
0x14000e798  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14000e79d  nop
0x14000e79e  lea     rcx, [rbp+5E0h+var_4D0]; this
0x14000e7a5  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14000e7aa  mov     rcx, [rbp+5E0h+var_40]
0x14000e7b1  xor     rcx, rsp; StackCookie
0x14000e7b4  call    __security_check_cookie
0x14000e7b9  mov     rbx, [rsp+6E0h+arg_18]
0x14000e7c1  add     rsp, 6B0h
0x14000e7c8  pop     r15
0x14000e7ca  pop     r14
0x14000e7cc  pop     r13
0x14000e7ce  pop     r12
0x14000e7d0  pop     rdi
0x14000e7d1  pop     rsi
0x14000e7d2  pop     rbp
0x14000e7d3  retn
0x14000e7d4  xor     edx, edx; Val
0x14000e7d6  mov     r8d, 208h; Size
0x14000e7dc  lea     rcx, [rbp+5E0h+szVolumeName]; void *
0x14000e7e3  call    memset_0
0x14000e7e8  xor     edx, edx; Val
0x14000e7ea  mov     r8d, 208h; Size
0x14000e7f0  lea     rcx, [rbp+5E0h+var_250]; void *
0x14000e7f7  call    memset_0
0x14000e7fc  mov     edx, 104h; cchBufferLength
0x14000e801  lea     rcx, [rbp+5E0h+szVolumeName]; lpszVolumeName
0x14000e808  call    cs:__imp_FindFirstVolumeW
0x14000e80e  mov     r12, rax
0x14000e811  lea     rax, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?FindVolumeClose@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&FindVolumeClose(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x14000e818  mov     [rbp+5E0h+var_638], rax
0x14000e81c  mov     [rbp+5E0h+var_630], r12
0x14000e820  mov     rbx, [rbp+5E0h+arg_40]
0x14000e827  nop     word ptr [rax+rax+00000000h]
0x14000e830  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14000e834  jz      loc_14000EE46
0x14000e83a  lea     rcx, [rbp+5E0h+szVolumeName]; lpRootPathName
0x14000e841  call    cs:__imp_GetDriveTypeW
0x14000e847  cmp     eax, 3
0x14000e84a  jnz     loc_14000EAEF
0x14000e850  lea     rcx, [rbp+5E0h+szVolumeName]
0x14000e857  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000e85e  xchg    ax, ax
0x14000e860  lea     rax, [rax+1]
0x14000e864  cmp     word ptr [rcx+rax*2], 0
0x14000e869  jnz     short loc_14000E860
0x14000e86b  lea     ecx, [rax-1]
0x14000e86e  add     rcx, rcx
0x14000e871  cmp     [rbp+rcx+5E0h+szVolumeName], 5Ch ; '\'
0x14000e87a  jz      loc_14000EE2A
0x14000e880  xor     edi, edi
0x14000e882  mov     rax, [r15+10h]
0x14000e886  test    rax, rax
0x14000e889  jnz     loc_14000EB25
0x14000e88f  mov     rsi, [r15+20h]
0x14000e893  movzx   eax, byte ptr [r15]
0x14000e897  mov     [rsp+6E0h+var_690], al
0x14000e89b  mov     [rsp+6E0h+var_68F], 0
0x14000e8a2  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14000e8a9  mov     [rsp+6E0h+var_688], rax
0x14000e8ae  mov     [rsp+6E0h+var_670], rdi
0x14000e8b3  mov     [rsp+6E0h+var_678], rax
0x14000e8b8  mov     [rsp+6E0h+var_668], 0
0x14000e8c1  mov     [rbp+5E0h+hMem], rdi
0x14000e8c5  mov     [rbp+5E0h+var_660], rax
0x14000e8c9  mov     rax, [rbp+5E0h+arg_28]
0x14000e8d0  mov     [rbp+5E0h+var_650], rax
0x14000e8d4  lea     rax, [rbp+5E0h+var_250]
0x14000e8db  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14000e8e2  inc     rdi
0x14000e8e5  cmp     word ptr [rax+rdi*2], 0
0x14000e8ea  jnz     short loc_14000E8E2
0x14000e8ec  inc     rdi
0x14000e8ef  lea     rdx, [rdi+rdi]; uBytes
0x14000e8f3  xor     ecx, ecx; uFlags
0x14000e8f5  call    cs:__imp_LocalAlloc
0x14000e8fb  mov     r8, rax
0x14000e8fe  mov     [rsp+6E0h+var_680], rax
0x14000e903  test    rax, rax
0x14000e906  jz      loc_14000EF8A
0x14000e90c  test    rdi, rdi
0x14000e90f  jz      loc_14000EF66
0x14000e915  cmp     rdi, 7FFFFFFFh
0x14000e91c  ja      loc_14000EF60
0x14000e922  mov     ecx, 7FFFFFFEh
0x14000e927  lea     rdx, [rbp+5E0h+var_250]
0x14000e92e  xchg    ax, ax
0x14000e930  test    rcx, rcx
0x14000e933  jz      short loc_14000E952
0x14000e935  movzx   eax, word ptr [rdx]
0x14000e938  test    ax, ax
0x14000e93b  jz      short loc_14000E952
0x14000e93d  add     rdx, 2
0x14000e941  mov     [r8], ax
0x14000e945  add     r8, 2
0x14000e949  dec     rcx
0x14000e94c  sub     rdi, 1
0x14000e950  jnz     short loc_14000E930
0x14000e952  lea     rcx, [r8-2]
0x14000e956  test    rdi, rdi
0x14000e959  cmovnz  rcx, r8
0x14000e95d  xor     eax, eax
0x14000e95f  mov     [rcx], ax
0x14000e962  test    rdi, rdi
0x14000e965  jz      loc_14000EF66
0x14000e96b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14000e972  inc     rdi
0x14000e975  cmp     [rsi+rdi*2], ax
0x14000e979  jnz     short loc_14000E972
0x14000e97b  inc     rdi
0x14000e97e  lea     rdx, [rdi+rdi]; uBytes
0x14000e982  xor     ecx, ecx; uFlags
0x14000e984  call    cs:__imp_LocalAlloc
0x14000e98a  mov     rdx, rax
0x14000e98d  mov     [rsp+6E0h+var_670], rax
0x14000e992  test    rax, rax
0x14000e995  jz      loc_14000EF46
0x14000e99b  test    rdi, rdi
0x14000e99e  jz      loc_14000EF22
0x14000e9a4  cmp     rdi, 7FFFFFFFh
0x14000e9ab  ja      loc_14000EF1D
0x14000e9b1  mov     ecx, 7FFFFFFEh
0x14000e9b6  test    rcx, rcx
0x14000e9b9  jz      short loc_14000E9D7
0x14000e9bb  movzx   eax, word ptr [rsi]
0x14000e9be  test    ax, ax
0x14000e9c1  jz      short loc_14000E9D7
0x14000e9c3  add     rsi, 2
0x14000e9c7  mov     [rdx], ax
0x14000e9ca  add     rdx, 2
0x14000e9ce  dec     rcx
0x14000e9d1  sub     rdi, 1
0x14000e9d5  jnz     short loc_14000E9B6
0x14000e9d7  lea     rcx, [rdx-2]
0x14000e9db  test    rdi, rdi
0x14000e9de  cmovnz  rcx, rdx
0x14000e9e2  xor     eax, eax
0x14000e9e4  mov     [rcx], ax
0x14000e9e7  test    rdi, rdi
0x14000e9ea  jz      loc_14000EF22
0x14000e9f0  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14000e9f7  nop     word ptr [rax+rax+00000000h]
0x14000ea00  inc     rdi
0x14000ea03  cmp     [r14+rdi*2], ax
0x14000ea08  jnz     short loc_14000EA00
0x14000ea0a  inc     rdi
0x14000ea0d  lea     rdx, [rdi+rdi]; uBytes
0x14000ea11  xor     ecx, ecx; uFlags
0x14000ea13  call    cs:__imp_LocalAlloc
0x14000ea19  mov     r8, rax
0x14000ea1c  mov     [rbp+5E0h+hMem], rax
0x14000ea20  test    rax, rax
0x14000ea23  jz      loc_14000EF03
0x14000ea29  test    rdi, rdi
0x14000ea2c  jz      loc_14000EEE0
0x14000ea32  cmp     rdi, 7FFFFFFFh
0x14000ea39  ja      loc_14000EEDA
0x14000ea3f  mov     ecx, 7FFFFFFEh
0x14000ea44  mov     rdx, r14
0x14000ea47  test    rcx, rcx
0x14000ea4a  jz      short loc_14000EA69
0x14000ea4c  movzx   eax, word ptr [rdx]
0x14000ea4f  test    ax, ax
0x14000ea52  jz      short loc_14000EA69
0x14000ea54  add     rdx, 2
0x14000ea58  mov     [r8], ax
0x14000ea5c  add     r8, 2
0x14000ea60  dec     rcx
0x14000ea63  sub     rdi, 1
0x14000ea67  jnz     short loc_14000EA47
0x14000ea69  lea     rcx, [r8-2]
0x14000ea6d  test    rdi, rdi
0x14000ea70  cmovnz  rcx, r8
0x14000ea74  xor     eax, eax
0x14000ea76  mov     [rcx], ax
0x14000ea79  test    rdi, rdi
0x14000ea7c  jz      loc_14000EEE0
0x14000ea82  movzx   eax, [rbp+5E0h+arg_20]
0x14000ea89  mov     byte ptr [rsp+6E0h+var_6B0], al
0x14000ea8d  mov     rax, [rbp+5E0h+arg_38]
0x14000ea94  mov     [rsp+6E0h+var_6B8], rax
0x14000ea99  mov     rax, [rbp+5E0h+arg_30]
0x14000eaa0  mov     [rsp+6E0h+var_6C0], rax
0x14000eaa5  mov     r9, rbx
0x14000eaa8  xor     r8d, r8d
0x14000eaab  lea     rdx, [rsp+6E0h+var_690]
0x14000eab0  mov     rcx, r13
0x14000eab3  call    ?ExpandFilesDirect@CVssDeletingWriter@@IEAAXAEAUToDeleteFile@1@_NV?$back_insert_iterator@V?$vector@UToDeleteFile@CVssDeletingWriter@@V?$allocator@UToDeleteFile@CVssDeletingWriter@@@std@@@std@@@std@@_K31@Z; CVssDeletingWriter::ExpandFilesDirect(CVssDeletingWriter::ToDeleteFile &,bool,std::back_insert_iterator<std::vector<CVssDeletingWriter::ToDeleteFile>>,unsigned __int64,unsigned __int64,bool)
0x14000eab8  nop
0x14000eab9  mov     rcx, [rbp+5E0h+hMem]; hMem
0x14000eabd  test    rcx, rcx
0x14000eac0  jz      short loc_14000EAC8
0x14000eac2  call    cs:__imp_LocalFree
0x14000eac8  mov     rcx, [rsp+6E0h+var_670]; hMem
0x14000eacd  test    rcx, rcx
0x14000ead0  jz      short loc_14000EAD8
0x14000ead2  call    cs:__imp_LocalFree
0x14000ead8  mov     rcx, [rsp+6E0h+var_680]; hMem
0x14000eadd  test    rcx, rcx
0x14000eae0  jz      short loc_14000EAE8
0x14000eae2  call    cs:__imp_LocalFree
0x14000eae8  lea     rsi, aCvssdeletingwr_9; "CVssDeletingWriter::ExpandFilesAllVolum"...
0x14000eaef  mov     r8d, 104h; cchBufferLength
0x14000eaf5  lea     rdx, [rbp+5E0h+szVolumeName]; lpszVolumeName
0x14000eafc  mov     rcx, r12; hFindVolume
0x14000eaff  call    cs:__imp_FindNextVolumeW
0x14000eb05  test    eax, eax
0x14000eb07  jnz     loc_14000E830
0x14000eb0d  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14000eb11  jz      loc_14000E79E
0x14000eb17  mov     rcx, r12; hFindVolume
0x14000eb1a  call    cs:__imp_FindVolumeClose
0x14000eb20  jmp     loc_14000E79E
0x14000eb25  mov     [rsp+6E0h+var_6C0], rax
0x14000eb2a  lea     r9, [rbp+5E0h+szVolumeName]
0x14000eb31  lea     r8, aSS; "%s\\%s"
0x14000eb38  mov     edx, 104h; unsigned __int64
0x14000eb3d  lea     rcx, [rbp+5E0h+var_250]; unsigned __int16 *
0x14000eb44  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000eb49  mov     [rbp+5E0h+var_4C8], eax
0x14000eb4f  test    eax, eax
0x14000eb51  jns     loc_14000E88F
0x14000eb57  call    cs:__imp_GetLastError
0x14000eb5d  mov     edi, eax
0x14000eb5f  mov     esi, [rbp+5E0h+var_4C8]
0x14000eb65  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x14000eb6c  mov     [rbp+5E0h+var_628], rax
0x14000eb70  lea     rax, aCvssdeletingwr_9; "CVssDeletingWriter::ExpandFilesAllVolum"...
0x14000eb77  mov     [rbp+5E0h+var_620], rax
0x14000eb7b  lea     rax, aWrtdelet; "WRTDELET"
0x14000eb82  mov     [rbp+5E0h+var_618], rax
0x14000eb86  mov     [rbp+5E0h+var_610], 367h
0x14000eb8d  mov     [rbp+5E0h+var_60C], 4
0x14000eb94  mov     [rbp+5E0h+var_608], 0FFh
0x14000eb9b  mov     [rbp+5E0h+var_588], 1000000h
0x14000eba2  xor     edx, edx; Val
0x14000eba4  mov     r8d, 78h ; 'x'; Size
0x14000ebaa  lea     rcx, [rbp+5E0h+var_600]; void *
0x14000ebae  call    memset_0
0x14000ebb3  mov     dword ptr [rsp+6E0h+var_6B0], edi
0x14000ebb7  mov     dword ptr [rsp+6E0h+var_6B8], esi
0x14000ebbb  mov     rax, [r15+10h]
  ... truncated ...
```
