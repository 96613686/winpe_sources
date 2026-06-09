# CVssDeletingWriter::ExpandFilesProfile(CVssDeletingWriter::ToDeleteFile &,ushort *,bool,bool,__int64,__int64,__int64,std::back_insert_iterator<std::vector<CVssDeletingWriter::ToDeleteFile,std::allocator<CVssDeletingWriter::ToDeleteFile>>>)

- ea: `0x140015fb0`
- end: `0x140016701`
- name: `?ExpandFilesProfile@CVssDeletingWriter@@IEAAXAEAUToDeleteFile@1@PEAG_N2_J33V?$back_insert_iterator@V?$vector@UToDeleteFile@CVssDeletingWriter@@V?$allocator@UToDeleteFile@CVssDeletingWriter@@@std@@@std@@@std@@@Z`
- size: `1873`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000c84c`

## callees

- `0x140008908`
- `0x14000bba0`
- `0x14000e188`
- `0x14000f1d0`
- `0x140010170`
- `0x140011ae0`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013c60`
- `0x140014650`
- `0x140015480`
- `0x140015fb0`
- `0x140016a10`
- `0x140027690`
- `0x14003a09c`
- `0x14003b1d8`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016406`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016631`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016631`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x140016338`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x140016338`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400163f8`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400163f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001607d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001607d`
- `VssTrace!__imp_VssTraceMessage` at `0x140016178`
- `VssTrace!__imp_VssTraceMessage` at `0x140016178`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400160d1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400160d1`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400160c3`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400160c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001619a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400161fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016549`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001619a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400161fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016549`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016652`

## string_xrefs

- `0x140015ff7`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14001634e`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14001640e`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14001647d`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14001630a`: `ProfileImagePath`
- `0x140016002`: `CVssDeletingWriter::ExpandFilesProfile`
- `0x140016359`: `CVssDeletingWriter::ExpandFilesProfile`
- `0x140016419`: `CVssDeletingWriter::ExpandFilesProfile`
- `0x140016488`: `CVssDeletingWriter::ExpandFilesProfile`
- `0x1400163a3`: `GetVolumePathName(%s) failed with %d`
- `0x140016469`: `GetVolumeNameForVolumeMountPoint(%s) failed with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CVssDeletingWriter::ExpandFilesProfile(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int8 a4,
        char a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v9; // rax
  int v10; // ebx
  __int64 i; // rbx
  void *v12; // rcx
  unsigned int v13; // r14d
  unsigned int v14; // esi
  const unsigned __int16 *CurrentKeyName; // rax
  CVssDeletingWriter *v16; // rcx
  unsigned __int16 *v17; // rax
  bool v18; // r9
  WCHAR *v19; // rdi
  DWORD LastError; // ebx
  DWORD v21; // ebx
  HLOCAL v22; // rbx
  __int64 v23; // r8
  char v24; // r9
  __int64 v25; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  void **v28; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpszFileName; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v30[2]; // [rsp+70h] [rbp-90h] BYREF
  void **v31; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+90h] [rbp-70h]
  void **v34; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-60h]
  _QWORD v36[2]; // [rsp+A8h] [rbp-58h] BYREF
  void **v37; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID v38; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v39; // [rsp+C8h] [rbp-38h] BYREF
  const wchar_t *v40; // [rsp+D0h] [rbp-30h]
  const unsigned __int16 *v41; // [rsp+D8h] [rbp-28h]
  int v42; // [rsp+E0h] [rbp-20h]
  int v43; // [rsp+E4h] [rbp-1Ch]
  int v44; // [rsp+E8h] [rbp-18h]
  LPVOID pv[15]; // [rsp+F0h] [rbp-10h] BYREF
  int v46; // [rsp+168h] [rbp+68h]
  unsigned __int64 v47; // [rsp+170h] [rbp+70h] BYREF
  int v48; // [rsp+178h] [rbp+78h]
  const unsigned __int16 *v49; // [rsp+180h] [rbp+80h]
  const unsigned __int16 *v50; // [rsp+188h] [rbp+88h]
  unsigned int v51; // [rsp+190h] [rbp+90h]
  unsigned int v52; // [rsp+194h] [rbp+94h]
  const wchar_t *v53; // [rsp+198h] [rbp+98h]
  unsigned int v54; // [rsp+1A0h] [rbp+A0h]
  DWORD TickCount; // [rsp+1A4h] [rbp+A4h]
  int v56; // [rsp+1A8h] [rbp+A8h]
  __int128 v57; // [rsp+1B0h] [rbp+B0h]
  __int128 v58; // [rsp+1C0h] [rbp+C0h]
  __int64 v59; // [rsp+1D0h] [rbp+D0h]
  __int64 v60; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v61; // [rsp+1E8h] [rbp+E8h]
  int v62; // [rsp+1F0h] [rbp+F0h]
  _QWORD v63[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  char v64; // [rsp+208h] [rbp+108h]
  unsigned __int16 *v65; // [rsp+210h] [rbp+110h]
  __int64 v66; // [rsp+218h] [rbp+118h]
  _BYTE v67[80]; // [rsp+220h] [rbp+120h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v69[264]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v70[264]; // [rsp+690h] [rbp+590h] BYREF
  WCHAR szVolumeName[264]; // [rsp+8A0h] [rbp+7A0h] BYREF

  v65 = a3;
  v33 = a2;
  v66 = a1;
  v39 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v40 = L"CVssDeletingWriter::ExpandFilesProfile";
  v41 = L"WRTDELET";
  v42 = 700;
  v43 = 4;
  v44 = 255;
  v46 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v48 = 0;
  v53 = L"CVssDeletingWriter::ExpandFilesProfile";
  v49 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v50 = L"WRTDELET";
  v51 = 700;
  v52 = 4;
  TickCount = GetTickCount();
  v56 = 255;
  v47 = 0xFFFFFFFF00000000uLL;
  v59 = 0;
  v57 = 0;
  v58 = 0;
  v27 = 0;
  if ( (int)VssGetTracingContextPerThread(&v27) < 0 || (int)VssSetTracingContextPerThread(&v47) < 0 )
  {
    v9 = v59;
  }
  else
  {
    v9 = v27;
    v59 = v27;
  }
  if ( v9 )
    v54 = *(_DWORD *)(v9 + 48) + 1;
  else
    v54 = 0;
  v10 = 160;
  if ( v56 != 255 )
    v10 = v56;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v47, v52) )
    VssTraceMessage(v49, v50, v51, v54, v52, v53, L"ENTER", v10, 0);
  if ( HIBYTE(v46) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v12 = pv[i];
      if ( v12 )
      {
        CoTaskMemFree(v12);
        pv[i] = 0;
      }
    }
  }
  v38 = 0;
  v37 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
  v36[1] = 0;
  v36[0] = 131097;
  if ( CVssRegistryKey::Open(
         (REGSAM *)v36,
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList") )
  {
    v63[0] = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63[1] = 0;
    v64 = 0;
    CVssRegistryKeyIterator::Attach((CVssRegistryKeyIterator *)&v60, (struct CVssRegistryKey *)v36);
    v13 = v61;
    v14 = HIDWORD(v61);
    while ( 1 )
    {
      if ( v14 >= v13 )
      {
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(v63);
        CVssRegistryKey::Close((CVssRegistryKey *)v36);
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v37);
        goto LABEL_46;
      }
      v32 = 0;
      v31 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
      v30[1] = 0;
      v30[0] = 131097;
      lpszFileName = 0;
      v28 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
      CurrentKeyName = CVssRegistryKeyIterator::GetCurrentKeyName((CVssRegistryKeyIterator *)&v60);
      if ( CVssDeletingWriter::IsSystemAccountSID(v16, CurrentKeyName) )
        break;
      v17 = CVssRegistryKeyIterator::GetCurrentKeyName((CVssRegistryKeyIterator *)&v60);
      v48 = StringCchPrintfW(
              v69,
              0x104u,
              L"%s\\%s",
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
              v17);
      if ( v48 < 0 || !CVssRegistryKey::Open((REGSAM *)v30, HKEY_LOCAL_MACHINE, v69) )
      {
        lpszFileName = 0;
        v28 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
LABEL_43:
        CVssRegistryKey::Close((CVssRegistryKey *)v30);
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v31);
        goto LABEL_44;
      }
      lpszFileName = 0;
      if ( !CVssRegistryKey::GetValue(
              (CVssRegistryKey *)v30,
              L"ProfileImagePath",
              (unsigned __int16 **)&lpszFileName,
              v18) )
        break;
      v19 = (WCHAR *)lpszFileName;
      if ( !GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u) )
      {
        LastError = GetLastError();
        v39 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v40 = L"CVssDeletingWriter::ExpandFilesProfile";
        v41 = L"WRTDELET";
        v42 = 741;
        v43 = 4;
        v44 = 255;
        v46 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        LODWORD(v25) = LastError;
        CVssFunctionTracer::Trace(&v47, &v39, L"GetVolumePathName(%s) failed with %d", v19, v25);
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v28);
        CVssRegistryKey::Close((CVssRegistryKey *)v30);
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v31);
        goto LABEL_44;
      }
      if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
      {
        v21 = GetLastError();
        v39 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v40 = L"CVssDeletingWriter::ExpandFilesProfile";
        v41 = L"WRTDELET";
        v42 = 752;
        v43 = 4;
        v44 = 255;
        v46 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        LODWORD(v25) = v21;
        CVssFunctionTracer::Trace(
          &v47,
          &v39,
          L"GetVolumeNameForVolumeMountPoint(%s) failed with %d",
          szVolumePathName,
          v25);
        v39 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v40 = L"CVssDeletingWriter::ExpandFilesProfile";
        v41 = L"WRTDELET";
        v42 = 757;
        v43 = 4;
        v44 = 255;
        v46 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        CVssFunctionTracer::Trace(&v47, &v39, L"This might not be a local volume");
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v28);
        goto LABEL_30;
      }
      v48 = StringCchPrintfW(v70, 0x104u, L"%s\\%s", v19, *(_QWORD *)(v33 + 16));
      if ( v48 >= 0 )
      {
        hMem = 0;
        v34 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
        CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::ExpandEnvironmentStringsW(&v34, v70);
        v22 = hMem;
        CVssDeletingWriter::ToDeleteFile::ToDeleteFile(
          (CVssDeletingWriter::ToDeleteFile *)v67,
          *(_BYTE *)v33,
          v23,
          v24,
          a6,
          (const unsigned __int16 *)hMem,
          *(const unsigned __int16 **)(v33 + 32),
          v65);
        CVssDeletingWriter::ExpandFilesDirect(v66, (unsigned int)v67, a4, a9, a7, a8, a5);
        CVssDeletingWriter::ToDeleteFile::~ToDeleteFile((CVssDeletingWriter::ToDeleteFile *)v67);
        if ( v22 )
          LocalFree(v22);
        hMem = 0;
        v34 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
        if ( v19 )
          CoTaskMemFree(v19);
        lpszFileName = 0;
        v28 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
LABEL_30:
        CVssRegistryKey::Close((CVssRegistryKey *)v30);
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v31);
        HIDWORD(v61) = ++v14;
      }
      else
      {
        if ( v19 )
          CoTaskMemFree(v19);
        lpszFileName = 0;
        v28 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
        CVssRegistryKey::Close((CVssRegistryKey *)v30);
        if ( v32 )
        {
          CoTaskMemFree(v32);
          HIDWORD(v61) = ++v14;
        }
        else
        {
LABEL_44:
          HIDWORD(v61) = ++v14;
        }
      }
    }
    CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v28);
    goto LABEL_43;
  }
  CVssRegistryKey::Close((CVssRegistryKey *)v36);
  if ( v38 )
    CoTaskMemFree(v38);
LABEL_46:
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v47);
}

```

## disassembly

```asm
0x140015fb0  mov     [rsp-8+arg_18], rbx
0x140015fb5  push    rbp
0x140015fb6  push    rsi
0x140015fb7  push    rdi
0x140015fb8  push    r12
0x140015fba  push    r13
0x140015fbc  push    r14
0x140015fbe  push    r15
0x140015fc0  lea     rbp, [rsp-9C0h]
0x140015fc8  sub     rsp, 0AC0h
0x140015fcf  mov     rax, cs:__security_cookie
0x140015fd6  xor     rax, rsp
0x140015fd9  mov     [rbp+9F0h+var_40], rax
0x140015fe0  mov     [rsp+0AF0h+var_AA0], r9b
0x140015fe5  mov     [rbp+9F0h+var_8E0], r8
0x140015fec  mov     [rbp+9F0h+var_A60], rdx
0x140015ff0  mov     [rbp+9F0h+var_8D8], rcx
0x140015ff7  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x140015ffe  mov     [rbp+9F0h+var_A28], rax
0x140016002  lea     rax, aCvssdeletingwr_12; "CVssDeletingWriter::ExpandFilesProfile"
0x140016009  mov     [rbp+9F0h+var_A20], rax
0x14001600d  lea     rax, aWrtdelet; "WRTDELET"
0x140016014  mov     [rbp+9F0h+var_A18], rax
0x140016018  mov     [rbp+9F0h+var_A10], 2BCh
0x14001601f  mov     [rbp+9F0h+var_A0C], 4
0x140016026  mov     [rbp+9F0h+var_A08], 0FFh
0x14001602d  xor     edi, edi
0x14001602f  mov     [rbp+9F0h+var_988], 1000000h
0x140016036  xor     edx, edx; Val
0x140016038  mov     r8d, 78h ; 'x'; Size
0x14001603e  lea     rcx, [rbp+9F0h+pv]; void *
0x140016042  call    memset_0
0x140016047  mov     [rbp+9F0h+var_978], edi
0x14001604a  mov     rax, [rbp+9F0h+var_A20]
0x14001604e  mov     [rbp+9F0h+var_958], rax
0x140016055  mov     rax, [rbp+9F0h+var_A28]
0x140016059  mov     [rbp+9F0h+var_970], rax
0x140016060  mov     rax, [rbp+9F0h+var_A18]
0x140016064  mov     [rbp+9F0h+var_968], rax
0x14001606b  mov     eax, [rbp+9F0h+var_A10]
0x14001606e  mov     [rbp+9F0h+var_960], eax
0x140016074  mov     eax, [rbp+9F0h+var_A0C]
0x140016077  mov     [rbp+9F0h+var_95C], eax
0x14001607d  call    cs:__imp_GetTickCount
0x140016083  mov     [rbp+9F0h+var_94C], eax
0x140016089  mov     [rbp+9F0h+var_97C], 0FFFFFFFFh
0x140016090  mov     eax, [rbp+9F0h+var_A08]
0x140016093  mov     [rbp+9F0h+var_948], eax
0x140016099  mov     [rbp+9F0h+var_980], edi
0x14001609c  mov     [rbp+9F0h+var_920], rdi
0x1400160a3  xorps   xmm0, xmm0
0x1400160a6  movdqa  [rbp+9F0h+var_940], xmm0
0x1400160ae  xorps   xmm1, xmm1
0x1400160b1  movdqa  [rbp+9F0h+var_930], xmm1
0x1400160b9  mov     [rsp+0AF0h+var_A98], rdi
0x1400160be  lea     rcx, [rsp+0AF0h+var_A98]
0x1400160c3  call    cs:__imp_VssGetTracingContextPerThread
0x1400160c9  test    eax, eax
0x1400160cb  js      short loc_1400160E9
0x1400160cd  lea     rcx, [rbp+9F0h+var_980]
0x1400160d1  call    cs:__imp_VssSetTracingContextPerThread
0x1400160d7  test    eax, eax
0x1400160d9  js      short loc_1400160E9
0x1400160db  mov     rax, [rsp+0AF0h+var_A98]
0x1400160e0  mov     [rbp+9F0h+var_920], rax
0x1400160e7  jmp     short loc_1400160F0
0x1400160e9  mov     rax, [rbp+9F0h+var_920]
0x1400160f0  test    rax, rax
0x1400160f3  jz      short loc_140016102
0x1400160f5  mov     eax, [rax+30h]
0x1400160f8  inc     eax
0x1400160fa  mov     [rbp+9F0h+var_950], eax
0x140016100  jmp     short loc_140016108
0x140016102  mov     [rbp+9F0h+var_950], edi
0x140016108  mov     ebx, 0A0h
0x14001610d  cmp     [rbp+9F0h+var_948], 0FFh
0x140016117  cmovnz  ebx, [rbp+9F0h+var_948]
0x14001611e  mov     edx, [rbp+9F0h+var_95C]; unsigned int
0x140016124  lea     rcx, [rbp+9F0h+var_980]; this
0x140016128  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14001612d  test    eax, eax
0x14001612f  jz      short loc_14001617E
0x140016131  mov     [rsp+0AF0h+var_AB0], rdi
0x140016136  mov     dword ptr [rsp+0AF0h+var_AB8], ebx
0x14001613a  lea     rax, aEnter; "ENTER"
0x140016141  mov     [rsp+0AF0h+var_AC0], rax
0x140016146  mov     rax, [rbp+9F0h+var_958]
0x14001614d  mov     [rsp+0AF0h+var_AC8], rax
0x140016152  mov     eax, [rbp+9F0h+var_95C]
0x140016158  mov     dword ptr [rsp+0AF0h+var_AD0], eax
0x14001615c  mov     r9d, [rbp+9F0h+var_950]
0x140016163  mov     r8d, [rbp+9F0h+var_960]
0x14001616a  mov     rdx, [rbp+9F0h+var_968]
0x140016171  mov     rcx, [rbp+9F0h+var_970]
0x140016178  call    cs:__imp_VssTraceMessage
0x14001617e  cmp     byte ptr [rbp+9F0h+var_988+3], dil
0x140016182  jz      short loc_1400161AE
0x140016184  mov     rbx, rdi
0x140016187  nop     word ptr [rax+rax+00000000h]
0x140016190  mov     rcx, [rbp+rbx*8+9F0h+pv]; pv
0x140016195  test    rcx, rcx
0x140016198  jz      short loc_1400161A5
0x14001619a  call    cs:__imp_CoTaskMemFree
0x1400161a0  mov     [rbp+rbx*8+9F0h+pv], rdi
0x1400161a5  inc     rbx
0x1400161a8  cmp     rbx, 0Fh
0x1400161ac  jnz     short loc_140016190
0x1400161ae  mov     [rbp+9F0h+var_A30], rdi
0x1400161b2  lea     rbx, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x1400161b9  mov     [rbp+9F0h+var_A38], rbx
0x1400161bd  mov     [rbp+9F0h+var_A40], rdi
0x1400161c1  mov     [rbp+9F0h+var_A48], 20019h
0x1400161c9  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400161d0  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1400161d7  lea     rcx, [rbp+9F0h+var_A48]; this
0x1400161db  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x1400161e0  test    al, al
0x1400161e2  jnz     short loc_140016205
0x1400161e4  lea     rcx, [rbp+9F0h+var_A48]; this
0x1400161e8  call    ?Close@CVssRegistryKey@@QEAAXXZ; CVssRegistryKey::Close(void)
0x1400161ed  mov     rcx, [rbp+9F0h+var_A30]; pv
0x1400161f1  test    rcx, rcx
0x1400161f4  jz      loc_1400166CE
0x1400161fa  call    cs:__imp_CoTaskMemFree
0x140016200  jmp     loc_1400166CE
0x140016205  mov     [rbp+9F0h+var_8F8], rbx
0x14001620c  mov     [rbp+9F0h+var_910], rdi
0x140016213  mov     [rbp+9F0h+var_908], rdi
0x14001621a  mov     [rbp+9F0h+var_900], edi
0x140016220  mov     [rbp+9F0h+var_8F0], rdi
0x140016227  mov     [rbp+9F0h+var_8E8], 0
0x14001622e  lea     rdx, [rbp+9F0h+var_A48]; struct CVssRegistryKey *
0x140016232  lea     rcx, [rbp+9F0h+var_910]; this
0x140016239  call    ?Attach@CVssRegistryKeyIterator@@QEAAXAEAVCVssRegistryKey@@@Z; CVssRegistryKeyIterator::Attach(CVssRegistryKey &)
0x14001623e  mov     r15, [rbp+9F0h+arg_38]
0x140016245  mov     r12, [rbp+9F0h+arg_30]
0x14001624c  mov     r13, [rbp+9F0h+arg_28]
0x140016253  mov     r14d, dword ptr [rbp+9F0h+var_908]
0x14001625a  mov     esi, dword ptr [rbp+9F0h+var_908+4]
0x140016260  cmp     esi, r14d
0x140016263  jnb     loc_1400166AE
0x140016269  mov     [rbp+9F0h+var_A68], rdi
0x14001626d  mov     [rbp+9F0h+var_A70], rbx
0x140016271  mov     [rsp+0AF0h+var_A78], rdi
0x140016276  mov     [rsp+0AF0h+var_A80], 20019h
0x14001627f  mov     [rsp+0AF0h+lpszFileName], rdi
0x140016284  mov     [rsp+0AF0h+var_A90], rbx
0x140016289  lea     rcx, [rbp+9F0h+var_910]; this
0x140016290  call    ?GetCurrentKeyName@CVssRegistryKeyIterator@@QEAAPEAGXZ; CVssRegistryKeyIterator::GetCurrentKeyName(void)
0x140016295  mov     rdx, rax; unsigned __int16 *
0x140016298  call    ?IsSystemAccountSID@CVssDeletingWriter@@IEAA_NPEBG@Z; CVssDeletingWriter::IsSystemAccountSID(ushort const *)
0x14001629d  test    al, al
0x14001629f  jnz     loc_140016683
0x1400162a5  lea     rcx, [rbp+9F0h+var_910]; this
0x1400162ac  call    ?GetCurrentKeyName@CVssRegistryKeyIterator@@QEAAPEAGXZ; CVssRegistryKeyIterator::GetCurrentKeyName(void)
0x1400162b1  mov     [rsp+0AF0h+var_AD0], rax
0x1400162b6  lea     r9, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400162bd  lea     r8, aSS; "%s\\%s"
0x1400162c4  mov     edx, 104h; unsigned __int64
0x1400162c9  lea     rcx, [rbp+9F0h+var_670]; unsigned __int16 *
0x1400162d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400162d5  mov     [rbp+9F0h+var_978], eax
0x1400162d8  test    eax, eax
0x1400162da  js      loc_140016670
0x1400162e0  lea     r8, [rbp+9F0h+var_670]; unsigned __int16 *
0x1400162e7  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1400162ee  lea     rcx, [rsp+0AF0h+var_A80]; this
0x1400162f3  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x1400162f8  test    al, al
0x1400162fa  jz      loc_140016670
0x140016300  mov     [rsp+0AF0h+lpszFileName], rdi
0x140016305  lea     r8, [rsp+0AF0h+lpszFileName]; unsigned __int16 **
0x14001630a  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x140016311  lea     rcx, [rsp+0AF0h+var_A80]; this
0x140016316  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAPEAG_N@Z; CVssRegistryKey::GetValue(ushort const *,ushort * &,bool)
0x14001631b  test    al, al
0x14001631d  jz      loc_140016683
0x140016323  mov     rdi, [rsp+0AF0h+lpszFileName]
0x140016328  mov     r8d, 104h; cchBufferLength
0x14001632e  lea     rdx, [rbp+9F0h+szVolumePathName]; lpszVolumePathName
0x140016335  mov     rcx, rdi; lpszFileName
0x140016338  call    cs:__imp_GetVolumePathNameW
0x14001633e  test    eax, eax
0x140016340  jnz     loc_1400163E4
0x140016346  call    cs:__imp_GetLastError
0x14001634c  mov     ebx, eax
0x14001634e  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x140016355  mov     [rbp+9F0h+var_A28], rax
0x140016359  lea     rax, aCvssdeletingwr_12; "CVssDeletingWriter::ExpandFilesProfile"
0x140016360  mov     [rbp+9F0h+var_A20], rax
0x140016364  lea     rax, aWrtdelet; "WRTDELET"
0x14001636b  mov     [rbp+9F0h+var_A18], rax
0x14001636f  mov     [rbp+9F0h+var_A10], 2E5h
0x140016376  mov     [rbp+9F0h+var_A0C], 4
0x14001637d  mov     [rbp+9F0h+var_A08], 0FFh
0x140016384  mov     [rbp+9F0h+var_988], 1000000h
0x14001638b  xor     edx, edx; Val
0x14001638d  mov     r8d, 78h ; 'x'; Size
0x140016393  lea     rcx, [rbp+9F0h+pv]; void *
0x140016397  call    memset_0
0x14001639c  mov     dword ptr [rsp+0AF0h+var_AD0], ebx
0x1400163a0  mov     r9, rdi
0x1400163a3  lea     r8, aGetvolumepathn_4; "GetVolumePathName(%s) failed with %d"
0x1400163aa  lea     rdx, [rbp+9F0h+var_A28]
0x1400163ae  lea     rcx, [rbp+9F0h+var_980]
0x1400163b2  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400163b7  nop
0x1400163b8  lea     rcx, [rsp+0AF0h+var_A90]
0x1400163bd  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x1400163c2  nop
0x1400163c3  lea     rcx, [rsp+0AF0h+var_A80]; this
0x1400163c8  call    ?Close@CVssRegistryKey@@QEAAXXZ; CVssRegistryKey::Close(void)
0x1400163cd  lea     rcx, [rbp+9F0h+var_A70]
0x1400163d1  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x1400163d6  xor     edi, edi
0x1400163d8  lea     rbx, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x1400163df  jmp     loc_1400166A1
0x1400163e4  mov     r8d, 104h; cchBufferLength
0x1400163ea  lea     rdx, [rbp+9F0h+szVolumeName]; lpszVolumeName
0x1400163f1  lea     rcx, [rbp+9F0h+szVolumePathName]; lpszVolumeMountPoint
0x1400163f8  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1400163fe  test    eax, eax
0x140016400  jnz     loc_140016512
0x140016406  call    cs:__imp_GetLastError
0x14001640c  mov     ebx, eax
0x14001640e  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x140016415  mov     [rbp+9F0h+var_A28], rax
0x140016419  lea     rax, aCvssdeletingwr_12; "CVssDeletingWriter::ExpandFilesProfile"
0x140016420  mov     [rbp+9F0h+var_A20], rax
0x140016424  lea     rax, aWrtdelet; "WRTDELET"
0x14001642b  mov     [rbp+9F0h+var_A18], rax
0x14001642f  mov     [rbp+9F0h+var_A10], 2F0h
0x140016436  mov     [rbp+9F0h+var_A0C], 4
0x14001643d  mov     [rbp+9F0h+var_A08], 0FFh
0x140016444  xor     edi, edi
0x140016446  mov     [rbp+9F0h+var_988], 1000000h
0x14001644d  xor     edx, edx; Val
0x14001644f  mov     r8d, 78h ; 'x'; Size
0x140016455  lea     rcx, [rbp+9F0h+pv]; void *
0x140016459  call    memset_0
0x14001645e  mov     dword ptr [rsp+0AF0h+var_AD0], ebx
0x140016462  lea     r9, [rbp+9F0h+szVolumePathName]
0x140016469  lea     r8, aGetvolumenamef_0; "GetVolumeNameForVolumeMountPoint(%s) fa"...
0x140016470  lea     rdx, [rbp+9F0h+var_A28]
0x140016474  lea     rcx, [rbp+9F0h+var_980]
0x140016478  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14001647d  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x140016484  mov     [rbp+9F0h+var_A28], rax
0x140016488  lea     rax, aCvssdeletingwr_12; "CVssDeletingWriter::ExpandFilesProfile"
0x14001648f  mov     [rbp+9F0h+var_A20], rax
0x140016493  lea     rax, aWrtdelet; "WRTDELET"
0x14001649a  mov     [rbp+9F0h+var_A18], rax
0x14001649e  mov     [rbp+9F0h+var_A10], 2F5h
0x1400164a5  mov     [rbp+9F0h+var_A0C], 4
0x1400164ac  mov     [rbp+9F0h+var_A08], 0FFh
0x1400164b3  mov     [rbp+9F0h+var_988], 1000000h
0x1400164ba  xor     edx, edx; Val
0x1400164bc  mov     r8d, 78h ; 'x'; Size
0x1400164c2  lea     rcx, [rbp+9F0h+pv]; void *
0x1400164c6  call    memset_0
0x1400164cb  lea     r8, aThisMightNotBe; "This might not be a local volume"
0x1400164d2  lea     rdx, [rbp+9F0h+var_A28]
0x1400164d6  lea     rcx, [rbp+9F0h+var_980]
0x1400164da  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400164df  nop
0x1400164e0  lea     rcx, [rsp+0AF0h+var_A90]
0x1400164e5  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x1400164ea  nop
0x1400164eb  lea     rcx, [rsp+0AF0h+var_A80]; this
0x1400164f0  call    ?Close@CVssRegistryKey@@QEAAXXZ; CVssRegistryKey::Close(void)
0x1400164f5  lea     rcx, [rbp+9F0h+var_A70]
0x1400164f9  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x1400164fe  lea     rbx, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x140016505  inc     esi
0x140016507  mov     dword ptr [rbp+9F0h+var_908+4], esi
0x14001650d  jmp     loc_140016260
0x140016512  mov     rax, [rbp+9F0h+var_A60]
0x140016516  mov     rax, [rax+10h]
0x14001651a  mov     [rsp+0AF0h+var_AD0], rax
0x14001651f  mov     r9, rdi
0x140016522  lea     r8, aSS; "%s\\%s"
0x140016529  mov     edx, 104h; unsigned __int64
0x14001652e  lea     rcx, [rbp+9F0h+var_460]; unsigned __int16 *
0x140016535  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001653a  mov     [rbp+9F0h+var_978], eax
0x14001653d  test    eax, eax
0x14001653f  jns     short loc_14001658C
0x140016541  test    rdi, rdi
0x140016544  jz      short loc_14001654F
0x140016546  mov     rcx, rdi; pv
0x140016549  call    cs:__imp_CoTaskMemFree
0x14001654f  xor     edi, edi
0x140016551  mov     [rsp+0AF0h+lpszFileName], rdi
0x140016556  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x14001655d  mov     [rsp+0AF0h+var_A90], rax
0x140016562  lea     rcx, [rsp+0AF0h+var_A80]; this
0x140016567  call    ?Close@CVssRegistryKey@@QEAAXXZ; CVssRegistryKey::Close(void)
0x14001656c  mov     rcx, [rbp+9F0h+var_A68]; pv
0x140016570  test    rcx, rcx
0x140016573  jz      loc_1400166A1
  ... truncated ...
```
