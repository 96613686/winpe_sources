# InitBdcRootCA(void)

- ea: `0x10043a840`
- end: `0x10043b66e`
- name: `?InitBdcRootCA@@YAXXZ`
- size: `3630`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x100412470`

## callees

- `0x1004012e0`
- `0x100401580`
- `0x1004019a0`
- `0x100402ec0`
- `0x100403f80`
- `0x100404060`
- `0x10043a840`
- `0x100440340`
- `0x1004403d0`
- `0x1004534f8`

## import_xrefs

- `CRYPT32!CryptStringToBinaryA` at `0x10043ad04`
- `CRYPT32!CryptStringToBinaryA` at `0x10043ad99`
- `CRYPT32!CryptStringToBinaryA` at `0x10043ad04`
- `CRYPT32!CryptStringToBinaryA` at `0x10043ad99`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x10043adfd`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x10043adfd`
- `CRYPT32!CertCloseStore` at `0x10043aaf4`
- `CRYPT32!CertOpenStore` at `0x10043adc6`
- `CRYPT32!CertOpenStore` at `0x10043adc6`
- `KERNEL32!FindFirstFileW` at `0x10043ab3d`
- `KERNEL32!FindFirstFileW` at `0x10043ab3d`
- `KERNEL32!CreateFileW` at `0x10043ac38`
- `KERNEL32!CreateFileW` at `0x10043ac38`
- `KERNEL32!ReadFile` at `0x10043accf`
- `KERNEL32!ReadFile` at `0x10043accf`
- `KERNEL32!FindNextFileW` at `0x10043ae12`
- `KERNEL32!FindNextFileW` at `0x10043ae12`
- `KERNEL32!CloseHandle` at `0x10043ae31`
- `KERNEL32!CloseHandle` at `0x10043ae85`
- `KERNEL32!CloseHandle` at `0x10043af3f`
- `KERNEL32!CloseHandle` at `0x10043b097`
- `KERNEL32!CloseHandle` at `0x10043b157`
- `KERNEL32!CloseHandle` at `0x10043b217`
- `KERNEL32!CloseHandle` at `0x10043b2d7`
- `KERNEL32!CloseHandle` at `0x10043ae31`
- `KERNEL32!CloseHandle` at `0x10043ae85`
- `KERNEL32!CloseHandle` at `0x10043af3f`
- `KERNEL32!CloseHandle` at `0x10043b097`
- `KERNEL32!CloseHandle` at `0x10043b157`
- `KERNEL32!CloseHandle` at `0x10043b217`
- `KERNEL32!CloseHandle` at `0x10043b2d7`
- `KERNEL32!GetLastError` at `0x10043ae1f`
- `KERNEL32!GetLastError` at `0x10043ae50`
- `KERNEL32!GetLastError` at `0x10043b062`
- `KERNEL32!GetLastError` at `0x10043b122`
- `KERNEL32!GetLastError` at `0x10043b1e2`
- `KERNEL32!GetLastError` at `0x10043b2a2`
- `KERNEL32!GetLastError` at `0x10043b362`
- `KERNEL32!GetLastError` at `0x10043b580`
- `KERNEL32!GetLastError` at `0x10043ae1f`
- `KERNEL32!GetLastError` at `0x10043ae50`
- `KERNEL32!GetLastError` at `0x10043b062`
- `KERNEL32!GetLastError` at `0x10043b122`
- `KERNEL32!GetLastError` at `0x10043b1e2`
- `KERNEL32!GetLastError` at `0x10043b2a2`
- `KERNEL32!GetLastError` at `0x10043b362`
- `KERNEL32!GetLastError` at `0x10043b580`
- `KERNEL32!FindClose` at `0x10043ae8f`
- `KERNEL32!FindClose` at `0x10043af49`
- `KERNEL32!FindClose` at `0x10043afe1`
- `KERNEL32!FindClose` at `0x10043b0a1`
- `KERNEL32!FindClose` at `0x10043b161`
- `KERNEL32!FindClose` at `0x10043b221`
- `KERNEL32!FindClose` at `0x10043b2e1`
- `KERNEL32!FindClose` at `0x10043b397`
- `KERNEL32!FindClose` at `0x10043b44b`
- `KERNEL32!FindClose` at `0x10043b4ff`
- `KERNEL32!FindClose` at `0x10043ae8f`
- `KERNEL32!FindClose` at `0x10043af49`
- `KERNEL32!FindClose` at `0x10043afe1`
- `KERNEL32!FindClose` at `0x10043b0a1`
- `KERNEL32!FindClose` at `0x10043b161`
- `KERNEL32!FindClose` at `0x10043b221`
- `KERNEL32!FindClose` at `0x10043b2e1`
- `KERNEL32!FindClose` at `0x10043b397`
- `KERNEL32!FindClose` at `0x10043b44b`
- `KERNEL32!FindClose` at `0x10043b4ff`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10043afca`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043ac82`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043ad43`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043aeb2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043aebc`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043af6c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043af76`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b004`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b00e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b0c4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b0ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b184`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b18e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b244`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b24e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b304`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b30e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b3ba`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b3c4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b46f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b47a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b522`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b52c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b5ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b5d8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043ac82`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043ad43`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043aeb2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043aebc`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043af6c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043af76`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b004`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b00e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b0c4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b0ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b184`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b18e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b244`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b24e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b304`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b30e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b3ba`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b3c4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b46f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b47a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b522`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b52c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b5ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043b5d8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a8f6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a94d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043aadc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a8f6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a94d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043aadc`
- `sqldk!SystemThread_TlsOffset` at `0x10043a8db`
- `sqldk!SystemThread_TlsOffset` at `0x10043a932`
- `sqldk!SystemThread_TlsOffset` at `0x10043aac1`
- `sqldk!SystemThread_TlsIndex` at `0x10043a8d2`
- `sqldk!SystemThread_TlsIndex` at `0x10043a929`
- `sqldk!SystemThread_TlsIndex` at `0x10043aab8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043ac71`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043ad32`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043ac71`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043ad32`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10043acb2`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10043ad73`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10043acb2`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10043ad73`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043ae65`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043af1f`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b077`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b137`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b1f7`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b2b7`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b377`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b42b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b4df`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b595`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043ae65`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043af1f`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b077`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b137`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b1f7`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b2b7`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b377`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b42b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b4df`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043b595`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043a914`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043a914`

## string_xrefs

- `0x10043afd4`: `Successfully installed BDC cluster root CA certificate to the store.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=42
void InitBdcRootCA(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rdx
  HCERTSTORE v5; // r15
  __int64 v6; // rbx
  __int64 v7; // rax
  struct IMemObj *v8; // r14
  int *FirstFileW; // r13
  void *v10; // rdi
  void *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rsi
  int v14; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  HANDLE FileW; // r12
  void *v18; // rsi
  void *v19; // r14
  BOOL NextFileW; // r15d
  DWORD v21; // eax
  DWORD v22; // eax
  wchar_t *v23; // rax
  wchar_t *v24; // rax
  DWORD v25; // eax
  wchar_t *v26; // rax
  DWORD v27; // eax
  wchar_t *v28; // rax
  DWORD v29; // eax
  wchar_t *v30; // rax
  DWORD v31; // eax
  wchar_t *v32; // rax
  DWORD LastError; // eax
  wchar_t *v34; // rax
  wchar_t *v35; // rax
  wchar_t *OSErrString; // rax
  DWORD v37; // eax
  wchar_t *v38; // rax
  char v39; // [rsp+40h] [rbp-C0h] BYREF
  int *v40; // [rsp+48h] [rbp-B8h]
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+58h] [rbp-A8h]
  int v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+64h] [rbp-9Ch]
  __int64 v45; // [rsp+68h] [rbp-98h]
  int v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h]
  __int64 v48; // [rsp+80h] [rbp-80h]
  __int64 v49; // [rsp+88h] [rbp-78h]
  __int64 v50; // [rsp+90h] [rbp-70h]
  bool v51; // [rsp+A0h] [rbp-60h]
  DWORD pcbBinary; // [rsp+B0h] [rbp-50h] BYREF
  void *v53; // [rsp+B8h] [rbp-48h]
  void *v54; // [rsp+C0h] [rbp-40h]
  HCERTSTORE v55; // [rsp+C8h] [rbp-38h]
  int *v56; // [rsp+D0h] [rbp-30h]
  DWORD NumberOfBytesRead; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v58; // [rsp+E0h] [rbp-20h]
  __int64 v59; // [rsp+E8h] [rbp-18h]
  _QWORD *v60; // [rsp+F0h] [rbp-10h]
  char *v61; // [rsp+F8h] [rbp-8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v63[4096]; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v64[4096]; // [rsp+1350h] [rbp+1250h] BYREF
  _BYTE v65[4096]; // [rsp+2350h] [rbp+2250h] BYREF
  _BYTE v66[4096]; // [rsp+3350h] [rbp+3250h] BYREF
  _BYTE v67[4096]; // [rsp+4350h] [rbp+4250h] BYREF
  _BYTE v68[4096]; // [rsp+5350h] [rbp+5250h] BYREF
  _BYTE v69[4096]; // [rsp+6350h] [rbp+6250h] BYREF
  _BYTE v70[4096]; // [rsp+7350h] [rbp+7250h] BYREF
  _BYTE v71[4096]; // [rsp+8350h] [rbp+8250h] BYREF
  _BYTE v72[4096]; // [rsp+9350h] [rbp+9250h] BYREF
  _QWORD v73[3]; // [rsp+A350h] [rbp+A250h] BYREF
  int v74; // [rsp+A368h] [rbp+A268h]
  _OWORD v75[7]; // [rsp+A420h] [rbp+A320h] BYREF
  __int64 v76; // [rsp+A490h] [rbp+A390h]
  WCHAR FileName[72]; // [rsp+A4A0h] [rbp+A3A0h] BYREF
  WCHAR v78[264]; // [rsp+A530h] [rbp+A430h] BYREF

  v59 = -2;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v41, 1);
  v56 = &v43;
  v46 = 4195779;
  v47 = 0;
  v49 = 0;
  v48 = 0;
  v50 = 0;
  v51 = 0;
  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v1 = *(_QWORD *)(v0 + 256);
  if ( !v1 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v1 = *(_QWORD *)(v0 + 256);
  }
  v2 = *(_QWORD *)(v1 + 600);
  if ( v2 )
    v51 = (unsigned int)SOS_Task::PushWait(v2, &v46) == 0;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v45 = v4;
  v44 = (*(_DWORD *)(v4 + 800) >> 11) & 1;
  if ( v44 || (*(_BYTE *)(v4 + 800) & 4) == 0 )
  {
    v43 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 608) + 8LL))(*(_QWORD *)(v4 + 608));
  }
  else
  {
    v43 = 0;
  }
  wcscpy(FileName, L"c:\\usr\\local\\share\\ca-certificates\\cluster-ca-certificates\\*.crt");
  v75[0] = *(_OWORD *)L"c:\\usr\\local\\share\\ca-certificates\\cluster-ca-certificates\\";
  v75[1] = *(_OWORD *)L"ocal\\share\\ca-certificates\\cluster-ca-certificates\\";
  v75[2] = *(_OWORD *)L"re\\ca-certificates\\cluster-ca-certificates\\";
  v75[3] = *(_OWORD *)L"rtificates\\cluster-ca-certificates\\";
  v75[4] = *(_OWORD *)L"es\\cluster-ca-certificates\\";
  v75[5] = *(_OWORD *)L"er-ca-certificates\\";
  v75[6] = *(_OWORD *)L"rtificates\\";
  v76 = *(_QWORD *)L"es\\";
  memset_0(v78, 0, 0x20Au);
  v54 = 0;
  v53 = 0;
  v5 = 0;
  v55 = 0;
  v39 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(struct IMemObj **)(v7 + 1000);
  v56 = (int *)v8;
  v73[1] = CertCloseStore;
  v73[2] = 0;
  v74 = 0;
  v73[0] = &FunctionCallBinderVirtual_2<void,int (*)(void *,unsigned long),void *,int>::`vftable';
  v60 = v73;
  v61 = &v39;
  FirstFileW = (int *)FindFirstFileW(FileName, &FindFileData);
  v40 = FirstFileW;
  v10 = v54;
  v11 = v53;
  while ( FirstFileW != (int *)-1LL )
  {
    if ( !FindFileData.nFileSizeLow || FindFileData.nFileSizeHigh )
    {
      OSErrString = GetOSErrString(0xDu, (struct ErrorStringHolder *)v71, 0, 0);
      scierrlogwithstate(0xC32Du, 10, 1, OSErrString);
      FindClose(FirstFileW);
      if ( v39 )
        (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
      operator delete[](v11);
      operator delete[](v10);
      v40 = &v43;
      if ( v43 )
      {
        if ( v44 )
          *(_DWORD *)(v45 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
            *(_QWORD *)(v45 + 608),
            v45,
            1);
      }
      goto LABEL_119;
    }
    v12 = -1;
    do
      ++v12;
    while ( FindFileData.cFileName[v12] );
    v13 = (unsigned int)v12;
    v14 = StringCchPrintfExW(v78, 0x105u, 0, 0, 0, L"%s%s", v75, FindFileData.cFileName);
    if ( v14 < 0 )
    {
      _mm_lfence();
      v35 = GetOSErrString((unsigned __int16)v14, (struct ErrorStringHolder *)v70, 0, 0);
      scierrlogwithstate(0xC32Du, 10, 1, v35);
      FindClose(FirstFileW);
      if ( v39 )
        (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
      operator delete[](v53);
      operator delete[](v54);
      v40 = &v43;
      if ( v43 )
      {
        if ( v44 )
          *(_DWORD *)(v45 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
            *(_QWORD *)(v45 + 608),
            v45,
            1);
      }
      goto LABEL_119;
    }
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v75 + v15) );
    v16 = v13 + (unsigned int)v15;
    if ( v16 >= 261 )
      _report_rangecheckfailure();
    v78[v16] = 0;
    v58 = -1;
    FileW = CreateFileW(v78, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    v58 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v34 = GetOSErrString(LastError, (struct ErrorStringHolder *)v69, 0, 0);
      scierrlogwithstate(0xC32Du, 10, 1, v34);
      FindClose(FirstFileW);
      if ( v39 )
        (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
      operator delete[](v11);
      operator delete[](v10);
      v40 = &v43;
      if ( v43 )
      {
        if ( v44 )
          *(_DWORD *)(v45 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
            *(_QWORD *)(v45 + 608),
            v45,
            1);
      }
      goto LABEL_119;
    }
    v18 = operator new[](FindFileData.nFileSizeLow + 1, v8, 1, "sql\\ntdbms\\ksource\\bdc.cpp", 295, 6u);
    if ( v10 != v18 )
      operator delete[](v10);
    v10 = v18;
    v54 = v18;
    if ( !v18 )
    {
      scierrlog(0x42F2u, L"InitBdcRootCA");
      SQLExit(143, 0, 2147942414LL);
    }
    if ( !ReadFile(FileW, v18, FindFileData.nFileSizeLow, &NumberOfBytesRead, 0) )
    {
      v31 = GetLastError();
      v32 = GetOSErrString(v31, (struct ErrorStringHolder *)v68, 0, 0);
      scierrlogwithstate(0xC32Du, 10, 1, v32);
      CloseHandle(FileW);
      FindClose(FirstFileW);
      if ( v39 )
        (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
      operator delete[](v11);
      operator delete[](v18);
      v40 = &v43;
      if ( v43 )
      {
        if ( v44 )
          *(_DWORD *)(v45 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
            *(_QWORD *)(v45 + 608),
            v45,
            1);
      }
      goto LABEL_119;
    }
    *((_BYTE *)v18 + FindFileData.nFileSizeLow) = 0;
    if ( !CryptStringToBinaryA((LPCSTR)v18, 0, 0, 0, &pcbBinary, 0, 0) )
    {
      v29 = GetLastError();
      v30 = GetOSErrString(v29, (struct ErrorStringHolder *)v67, 0, 0);
      scierrlogwithstate(0xC32Du, 10, 1, v30);
      CloseHandle(FileW);
      FindClose(FirstFileW);
      if ( v39 )
        (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
      operator delete[](v11);
      operator delete[](v18);
      v40 = &v43;
      if ( v43 )
      {
        if ( v44 )
          *(_DWORD *)(v45 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
            *(_QWORD *)(v45 + 608),
            v45,
            1);
      }
      goto LABEL_119;
    }
    v19 = operator new[](pcbBinary, v8, 1, "sql\\ntdbms\\ksource\\bdc.cpp", 337, 6u);
    if ( v11 != v19 )
      operator delete[](v11);
    v11 = v19;
    v53 = v19;
    if ( !v19 )
    {
      scierrlog(0x42F2u, L"InitBdcRootCA");
      SQLExit(144, 0, 2147942414LL);
    }
    if ( !CryptStringToBinaryA((LPCSTR)v18, 0, 0, (BYTE *)v19, &pcbBinary, 0, 0) )
    {
      v27 = GetLastError();
      v28 = GetOSErrString(v27, (struct ErrorStringHolder *)v66, 0, 0);
      scierrlogwithstate(0xC32Du, 10, 1, v28);
      CloseHandle(FileW);
      FindClose(FirstFileW);
      if ( v39 )
        (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
      operator delete[](v19);
      operator delete[](v18);
      v40 = &v43;
      if ( v43 )
      {
        if ( v44 )
          *(_DWORD *)(v45 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
            *(_QWORD *)(v45 + 608),
            v45,
            1);
      }
      goto LABEL_119;
    }
    if ( !v5 )
    {
      v5 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"root");
      v55 = v5;
      if ( !v5 )
      {
        v22 = GetLastError();
        v23 = GetOSErrString(v22, (struct ErrorStringHolder *)v63, 0, 0);
        scierrlogwithstate(0xC32Du, 10, 1, v23);
        CloseHandle(FileW);
        FindClose(FirstFileW);
        if ( v39 )
          (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
        operator delete[](v19);
        operator delete[](v18);
        v40 = &v43;
        if ( v43 )
        {
          if ( v44 )
            *(_DWORD *)(v45 + 800) |= 0x800u;
          else
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
              *(_QWORD *)(v45 + 608),
              v45,
              1);
        }
        goto LABEL_119;
      }
      v39 = 1;
    }
    if ( !CertAddEncodedCertificateToStore(v5, 1u, (const BYTE *)v19, pcbBinary, 3u, 0) )
    {
      v25 = GetLastError();
      v26 = GetOSErrString(v25, (struct ErrorStringHolder *)v65, 0, 0);
      scierrlogwithstate(0xC32Du, 10, 1, v26);
      CloseHandle(FileW);
      FindClose(FirstFileW);
      if ( v39 )
        (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
      operator delete[](v19);
      operator delete[](v18);
      v40 = &v43;
      if ( v43 )
      {
        if ( v44 )
          *(_DWORD *)(v45 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
            *(_QWORD *)(v45 + 608),
            v45,
            1);
      }
      goto LABEL_119;
    }
    NextFileW = FindNextFileW(FirstFileW, &FindFileData);
    if ( !NextFileW )
    {
      v21 = GetLastError();
      if ( v21 != 18 )
      {
        v24 = GetOSErrString(v21, (struct ErrorStringHolder *)v64, 0, 0);
        scierrlogwithstate(0xC32Du, 10, 1, v24);
        CloseHandle(FileW);
        FindClose(FirstFileW);
        if ( v39 )
          (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
        operator delete[](v19);
        operator delete[](v18);
        v40 = &v43;
        if ( v43 )
        {
          if ( v44 )
            *(_DWORD *)(v45 + 800) |= 0x800u;
          else
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
              *(_QWORD *)(v45 + 608),
              v45,
              1);
        }
        goto LABEL_119;
      }
    }
    CloseHandle(FileW);
    if ( !NextFileW )
    {
      SOS_OS_LogUnlocalizedRoutine(L"Successfully installed BDC cluster root CA certificate to the store.\n");
      FindClose(FirstFileW);
      if ( v39 )
        (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
      operator delete[](v19);
      operator delete[](v18);
      v40 = &v43;
      if ( v43 )
      {
        if ( v44 )
          *(_DWORD *)(v45 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
            *(_QWORD *)(v45 + 608),
            v45,
            1);
      }
      goto LABEL_119;
    }
    v5 = v55;
    v8 = (struct IMemObj *)v56;
  }
  v37 = GetLastError();
  v38 = GetOSErrString(v37, (struct ErrorStringHolder *)v72, 0, 0);
  scierrlogwithstate(0xC32Du, 10, 1, v38);
  if ( v39 )
    (*(void (__fastcall **)(_QWORD *))(v73[0] + 8LL))(v73);
  operator delete[](v11);
  operator delete[](v10);
  v40 = &v43;
  if ( v43 )
  {
    if ( v44 )
      *(_DWORD *)(v45 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v45 + 608) + 16LL))(
        *(_QWORD *)(v45 + 608),
        v45,
        1);
  }
LABEL_119:
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v46);
  *(_DWORD *)(v42 + 616) &= ~v41;
}

```

## disassembly

```asm
0x10043a840  push    rbp
0x10043a842  push    r12
0x10043a844  push    r13
0x10043a846  push    r14
0x10043a848  push    r15
0x10043a84a  lea     rbp, [rsp-0A650h]
0x10043a852  mov     eax, 0A750h
0x10043a857  call    _alloca_probe
0x10043a85c  sub     rsp, rax
0x10043a85f  mov     [rbp+0A670h+var_A688], 0FFFFFFFFFFFFFFFEh
0x10043a867  mov     [rsp+0A770h+arg_0], rbx
0x10043a86f  mov     [rsp+0A770h+arg_8], rsi
0x10043a877  mov     [rsp+0A770h+arg_10], rdi
0x10043a87f  mov     rax, cs:__security_cookie
0x10043a886  xor     rax, rsp
0x10043a889  mov     [rbp+0A670h+var_30], rax
0x10043a890  mov     edx, 1
0x10043a895  lea     rcx, [rsp+0A770h+var_A720]
0x10043a89a  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10043a89f  nop
0x10043a8a0  lea     rax, [rsp+0A770h+var_A710]
0x10043a8a5  mov     [rbp+0A670h+var_A6A0], rax
0x10043a8a9  mov     [rsp+0A770h+var_A700], 4005C3h
0x10043a8b1  xor     r12d, r12d
0x10043a8b4  mov     [rsp+0A770h+var_A6F8], r12
0x10043a8b9  mov     [rbp+0A670h+var_A6E8], r12
0x10043a8bd  mov     [rbp+0A670h+var_A6F0], r12
0x10043a8c1  mov     [rbp+0A670h+var_A6E0], r12
0x10043a8c5  mov     [rbp+0A670h+var_A6D0], r12b
0x10043a8c9  mov     rdx, gs:58h
0x10043a8d2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043a8d9  mov     ecx, [rax]
0x10043a8db  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043a8e2  mov     ebx, [rax]
0x10043a8e4  add     rbx, [rdx+rcx*8]
0x10043a8e8  mov     rax, [rbx+100h]
0x10043a8ef  test    rax, rax
0x10043a8f2  jnz     short loc_10043A903
0x10043a8f4  xor     ecx, ecx
0x10043a8f6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043a8fc  mov     rax, [rbx+100h]
0x10043a903  mov     rcx, [rax+258h]
0x10043a90a  test    rcx, rcx
0x10043a90d  jz      short loc_10043A920
0x10043a90f  lea     rdx, [rsp+0A770h+var_A700]
0x10043a914  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10043a91a  test    eax, eax
0x10043a91c  setz    [rbp+0A670h+var_A6D0]
0x10043a920  mov     rdx, gs:58h
0x10043a929  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043a930  mov     ecx, [rax]
0x10043a932  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043a939  mov     ebx, [rax]
0x10043a93b  add     rbx, [rdx+rcx*8]
0x10043a93f  mov     rdx, [rbx+100h]
0x10043a946  test    rdx, rdx
0x10043a949  jnz     short loc_10043A95A
0x10043a94b  xor     ecx, ecx
0x10043a94d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043a953  mov     rdx, [rbx+100h]
0x10043a95a  mov     [rsp+0A770h+var_A708], rdx
0x10043a95f  mov     eax, [rdx+320h]
0x10043a965  shr     eax, 0Bh
0x10043a968  and     eax, 1
0x10043a96b  mov     [rsp+0A770h+var_A70C], eax
0x10043a96f  jnz     short loc_10043A981
0x10043a971  test    byte ptr [rdx+320h], 4
0x10043a978  jz      short loc_10043A981
0x10043a97a  mov     [rsp+0A770h+var_A710], r12d
0x10043a97f  jmp     short loc_10043A997
0x10043a981  mov     [rsp+0A770h+var_A710], 1
0x10043a989  mov     rcx, [rdx+260h]
0x10043a990  mov     rax, [rcx]
0x10043a993  call    qword ptr [rax+8]
0x10043a996  nop
0x10043a997  movaps  xmm0, xmmword ptr cs:aCUsrLocalShare_0; "c:\\usr\\local\\share\\ca-certificates"...
0x10043a99e  movaps  xmmword ptr [rbp+0A670h+FileName], xmm0
0x10043a9a5  movaps  xmm1, xmmword ptr cs:aCUsrLocalShare_0+10h; "ocal\\share\\ca-certificates\\cluster-c"...
0x10043a9ac  movaps  [rbp+0A670h+var_2C0], xmm1
0x10043a9b3  movaps  xmm0, xmmword ptr cs:aCUsrLocalShare_0+20h; "re\\ca-certificates\\cluster-ca-certifi"...
0x10043a9ba  movaps  [rbp+0A670h+var_2B0], xmm0
0x10043a9c1  movaps  xmm1, xmmword ptr cs:aCUsrLocalShare_0+30h; "rtificates\\cluster-ca-certificates\\*."...
0x10043a9c8  movaps  [rbp+0A670h+var_2A0], xmm1
0x10043a9cf  movaps  xmm0, xmmword ptr cs:aCUsrLocalShare_0+40h; "es\\cluster-ca-certificates\\*.crt"
0x10043a9d6  movaps  [rbp+0A670h+var_290], xmm0
0x10043a9dd  movaps  xmm1, xmmword ptr cs:aCUsrLocalShare_0+50h; "er-ca-certificates\\*.crt"
0x10043a9e4  movaps  [rbp+0A670h+var_280], xmm1
0x10043a9eb  movaps  xmm0, xmmword ptr cs:aCUsrLocalShare_0+60h; "rtificates\\*.crt"
0x10043a9f2  movaps  [rbp+0A670h+var_270], xmm0
0x10043a9f9  movaps  xmm1, xmmword ptr cs:aCUsrLocalShare_0+70h; "es\\*.crt"
0x10043aa00  movaps  [rbp+0A670h+var_260], xmm1
0x10043aa07  movzx   eax, word ptr cs:aCUsrLocalShare_0+80h; ""
0x10043aa0e  mov     [rbp+0A670h+var_250], ax
0x10043aa15  movaps  xmm0, xmmword ptr cs:aCUsrLocalShare; "c:\\usr\\local\\share\\ca-certificates"...
0x10043aa1c  movaps  [rbp+0A670h+var_350], xmm0
0x10043aa23  movaps  xmm1, xmmword ptr cs:aCUsrLocalShare+10h; "ocal\\share\\ca-certificates\\cluster-c"...
0x10043aa2a  movaps  [rbp+0A670h+var_340], xmm1
0x10043aa31  movaps  xmm0, xmmword ptr cs:aCUsrLocalShare+20h; "re\\ca-certificates\\cluster-ca-certifi"...
0x10043aa38  movaps  [rbp+0A670h+var_330], xmm0
0x10043aa3f  movaps  xmm1, xmmword ptr cs:aCUsrLocalShare+30h; "rtificates\\cluster-ca-certificates\\"
0x10043aa46  movaps  [rbp+0A670h+var_320], xmm1
0x10043aa4d  movaps  xmm0, xmmword ptr cs:aCUsrLocalShare+40h; "es\\cluster-ca-certificates\\"
0x10043aa54  movaps  [rbp+0A670h+var_310], xmm0
0x10043aa5b  movaps  xmm1, xmmword ptr cs:aCUsrLocalShare+50h; "er-ca-certificates\\"
0x10043aa62  movaps  [rbp+0A670h+var_300], xmm1
0x10043aa69  movaps  xmm0, xmmword ptr cs:aCUsrLocalShare+60h; "rtificates\\"
0x10043aa70  movaps  [rbp+0A670h+var_2F0], xmm0
0x10043aa77  movsd   xmm1, qword ptr cs:aCUsrLocalShare+70h; "es\\"
0x10043aa7f  movsd   [rbp+0A670h+var_2E0], xmm1
0x10043aa87  xor     edx, edx; Val
0x10043aa89  mov     r8d, 20Ah; Size
0x10043aa8f  lea     rcx, [rbp+0A670h+var_240]; void *
0x10043aa96  call    memset_0
0x10043aa9b  mov     [rbp+0A670h+var_A6B0], r12
0x10043aa9f  mov     [rbp+0A670h+var_A6B8], r12
0x10043aaa3  mov     r15, r12
0x10043aaa6  mov     [rbp+0A670h+var_A6A8], r12
0x10043aaaa  mov     [rsp+0A770h+var_A730], r15b
0x10043aaaf  mov     rdx, gs:58h
0x10043aab8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043aabf  mov     ecx, [rax]
0x10043aac1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043aac8  mov     ebx, [rax]
0x10043aaca  add     rbx, [rdx+rcx*8]
0x10043aace  mov     rax, [rbx+100h]
0x10043aad5  test    rax, rax
0x10043aad8  jnz     short loc_10043AAE9
0x10043aada  xor     ecx, ecx
0x10043aadc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043aae2  mov     rax, [rbx+100h]
0x10043aae9  mov     r14, [rax+3E8h]
0x10043aaf0  mov     [rbp+0A670h+var_A6A0], r14
0x10043aaf4  mov     rax, cs:__imp_CertCloseStore
0x10043aafb  mov     [rbp+0A670h+var_418], rax
0x10043ab02  mov     [rbp+0A670h+var_410], r12
0x10043ab09  mov     [rbp+0A670h+var_408], r12d
0x10043ab10  lea     rax, ??_7?$FunctionCallBinderVirtual_2@XP6AHPEAXK@ZPEAXH@@6B@; const FunctionCallBinderVirtual_2<void,int (*)(void *,ulong),void *,int>::`vftable'
0x10043ab17  mov     [rbp+0A670h+var_420], rax
0x10043ab1e  lea     rax, [rbp+0A670h+var_420]
0x10043ab25  mov     [rbp+0A670h+var_A680], rax
0x10043ab29  lea     rax, [rsp+0A770h+var_A730]
0x10043ab2e  mov     [rbp+0A670h+var_A678], rax
0x10043ab32  lea     rdx, [rbp+0A670h+FindFileData]; lpFindFileData
0x10043ab36  lea     rcx, [rbp+0A670h+FileName]; lpFileName
0x10043ab3d  call    cs:__imp_FindFirstFileW
0x10043ab43  mov     r13, rax
0x10043ab46  mov     [rsp+0A770h+var_A728], rax
0x10043ab4b  mov     rdi, [rbp+0A670h+var_A6B0]
0x10043ab4f  mov     rbx, [rbp+0A670h+var_A6B8]
0x10043ab53  lea     rdx, aSS_1; "%s%s"
0x10043ab5a  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x10043ab5e  jz      loc_10043B580
0x10043ab64  cmp     [rbp+0A670h+FindFileData.nFileSizeLow], 0
0x10043ab68  jz      loc_10043B4CE
0x10043ab6e  cmp     [rbp+0A670h+FindFileData.nFileSizeHigh], 0
0x10043ab72  jnz     loc_10043B4CE
0x10043ab78  lea     rcx, [rbp+0A670h+FindFileData.cFileName]
0x10043ab7c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10043ab83  inc     rax
0x10043ab86  cmp     word ptr [rcx+rax*2], 0
0x10043ab8b  jnz     short loc_10043AB83
0x10043ab8d  mov     esi, eax
0x10043ab8f  lea     rax, [rbp+0A670h+FindFileData.cFileName]
0x10043ab93  mov     [rsp+0A770h+var_A738], rax
0x10043ab98  lea     rax, [rbp+0A670h+var_350]
0x10043ab9f  mov     [rsp+0A770h+hTemplateFile], rax
0x10043aba4  mov     qword ptr [rsp+0A770h+dwFlagsAndAttributes], rdx; wchar_t *
0x10043aba9  mov     qword ptr [rsp+0A770h+dwCreationDisposition], r12; unsigned int
0x10043abae  xor     r9d, r9d; unsigned __int64 *
0x10043abb1  xor     r8d, r8d; wchar_t **
0x10043abb4  mov     edx, 105h; unsigned __int64
0x10043abb9  lea     rcx, [rbp+0A670h+var_240]; wchar_t *
0x10043abc0  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x10043abc5  test    eax, eax
0x10043abc7  js      loc_10043B418
0x10043abcd  lea     rcx, [rbp+0A670h+var_350]
0x10043abd4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10043abdb  nop     dword ptr [rax+rax+00h]
0x10043abe0  inc     rax
0x10043abe3  cmp     word ptr [rcx+rax*2], 0
0x10043abe8  jnz     short loc_10043ABE0
0x10043abea  mov     ecx, eax
0x10043abec  add     rcx, rsi
0x10043abef  add     rcx, rcx
0x10043abf2  cmp     rcx, 20Ah
0x10043abf9  jnb     loc_10043B668
0x10043abff  mov     [rbp+rcx+0A670h+var_240], r12w
0x10043ac08  mov     [rbp+0A670h+var_A690], 0FFFFFFFFFFFFFFFFh
0x10043ac10  mov     [rsp+0A770h+hTemplateFile], r12; hTemplateFile
0x10043ac15  mov     [rsp+0A770h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x10043ac1d  mov     [rsp+0A770h+dwCreationDisposition], 3; dwCreationDisposition
0x10043ac25  xor     r9d, r9d; lpSecurityAttributes
0x10043ac28  mov     edx, 80000000h; dwDesiredAccess
0x10043ac2d  lea     r8d, [r9+3]; dwShareMode
0x10043ac31  lea     rcx, [rbp+0A670h+var_240]; lpFileName
0x10043ac38  call    cs:__imp_CreateFileW
0x10043ac3e  mov     r12, rax
0x10043ac41  mov     [rbp+0A670h+var_A690], rax
0x10043ac45  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10043ac49  jz      loc_10043B362
0x10043ac4f  mov     ecx, [rbp+0A670h+FindFileData.nFileSizeLow]
0x10043ac52  inc     ecx
0x10043ac54  mov     byte ptr [rsp+0A770h+dwFlagsAndAttributes], 6
0x10043ac59  mov     [rsp+0A770h+dwCreationDisposition], 127h
0x10043ac61  lea     r9, aSqlNtdbmsKsour_2; "sql\\ntdbms\\ksource\\bdc.cpp"
0x10043ac68  mov     r8d, 1
0x10043ac6e  mov     rdx, r14
0x10043ac71  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10043ac77  mov     rsi, rax
0x10043ac7a  cmp     rdi, rax
0x10043ac7d  jz      short loc_10043AC88
0x10043ac7f  mov     rcx, rdi
0x10043ac82  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10043ac88  mov     rdi, rsi
0x10043ac8b  mov     [rbp+0A670h+var_A6B0], rsi
0x10043ac8f  test    rsi, rsi
0x10043ac92  jnz     short loc_10043ACB8
0x10043ac94  lea     rdx, aInitbdcrootca; "InitBdcRootCA"
0x10043ac9b  mov     ecx, 42F2h; unsigned int
0x10043aca0  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10043aca5  xor     edx, edx
0x10043aca7  mov     ecx, 8Fh
0x10043acac  mov     r8d, 8007000Eh
0x10043acb2  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10043acb8  mov     qword ptr [rsp+0A770h+dwCreationDisposition], 0; lpOverlapped
0x10043acc1  lea     r9, [rbp+0A670h+NumberOfBytesRead]; lpNumberOfBytesRead
0x10043acc5  mov     r8d, [rbp+0A670h+FindFileData.nFileSizeLow]; nNumberOfBytesToRead
0x10043acc9  mov     rdx, rsi; lpBuffer
0x10043accc  mov     rcx, r12; hFile
0x10043accf  call    cs:__imp_ReadFile
0x10043acd5  test    eax, eax
0x10043acd7  jz      loc_10043B2A2
0x10043acdd  mov     eax, [rbp+0A670h+FindFileData.nFileSizeLow]
0x10043ace0  mov     byte ptr [rax+rsi], 0
0x10043ace4  xor     eax, eax
0x10043ace6  mov     [rsp+0A770h+hTemplateFile], rax; pdwFlags
0x10043aceb  mov     qword ptr [rsp+0A770h+dwFlagsAndAttributes], rax; pdwSkip
0x10043acf0  lea     rax, [rbp+0A670h+pcbBinary]
0x10043acf4  mov     qword ptr [rsp+0A770h+dwCreationDisposition], rax; pcbBinary
0x10043acf9  xor     r9d, r9d; pbBinary
0x10043acfc  xor     r8d, r8d; dwFlags
0x10043acff  xor     edx, edx; cchString
0x10043ad01  mov     rcx, rsi; pszString
0x10043ad04  call    cs:__imp_CryptStringToBinaryA
0x10043ad0a  test    eax, eax
0x10043ad0c  jz      loc_10043B1E2
0x10043ad12  mov     ecx, [rbp+0A670h+pcbBinary]
0x10043ad15  mov     byte ptr [rsp+0A770h+dwFlagsAndAttributes], 6
0x10043ad1a  mov     [rsp+0A770h+dwCreationDisposition], 151h
0x10043ad22  lea     r9, aSqlNtdbmsKsour_2; "sql\\ntdbms\\ksource\\bdc.cpp"
0x10043ad29  mov     r8d, 1
0x10043ad2f  mov     rdx, r14
0x10043ad32  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10043ad38  mov     r14, rax
0x10043ad3b  cmp     rbx, rax
0x10043ad3e  jz      short loc_10043AD49
0x10043ad40  mov     rcx, rbx
0x10043ad43  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10043ad49  mov     rbx, r14
0x10043ad4c  mov     [rbp+0A670h+var_A6B8], rbx
0x10043ad50  test    r14, r14
0x10043ad53  jnz     short loc_10043AD79
0x10043ad55  lea     rdx, aInitbdcrootca; "InitBdcRootCA"
0x10043ad5c  mov     ecx, 42F2h; unsigned int
0x10043ad61  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10043ad66  xor     edx, edx
0x10043ad68  mov     ecx, 90h
0x10043ad6d  mov     r8d, 8007000Eh
0x10043ad73  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10043ad79  xor     eax, eax
0x10043ad7b  mov     [rsp+0A770h+hTemplateFile], rax; pdwFlags
0x10043ad80  mov     qword ptr [rsp+0A770h+dwFlagsAndAttributes], rax; pdwSkip
0x10043ad85  lea     rax, [rbp+0A670h+pcbBinary]
0x10043ad89  mov     qword ptr [rsp+0A770h+dwCreationDisposition], rax; pcbBinary
0x10043ad8e  mov     r9, r14; pbBinary
0x10043ad91  xor     r8d, r8d; dwFlags
0x10043ad94  xor     edx, edx; cchString
0x10043ad96  mov     rcx, rsi; pszString
0x10043ad99  call    cs:__imp_CryptStringToBinaryA
0x10043ad9f  test    eax, eax
0x10043ada1  jz      loc_10043B122
0x10043ada7  test    r15, r15
0x10043adaa  jnz     short loc_10043ADDD
0x10043adac  lea     rax, aRoot; "root"
0x10043adb3  mov     qword ptr [rsp+0A770h+dwCreationDisposition], rax; pvPara
0x10043adb8  mov     r9d, 20000h; dwFlags
0x10043adbe  xor     r8d, r8d; hCryptProv
0x10043adc1  xor     edx, edx; dwEncodingType
0x10043adc3  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x10043adc6  call    cs:__imp_CertOpenStore
0x10043adcc  mov     r15, rax
0x10043adcf  mov     [rbp+0A670h+var_A6A8], rax
0x10043add3  test    rax, rax
0x10043add6  jz      short loc_10043AE50
0x10043add8  mov     [rsp+0A770h+var_A730], 1
0x10043addd  mov     qword ptr [rsp+0A770h+dwFlagsAndAttributes], 0; ppCertContext
0x10043ade6  mov     [rsp+0A770h+dwCreationDisposition], 3; dwAddDisposition
0x10043adee  mov     r9d, [rbp+0A670h+pcbBinary]; cbCertEncoded
0x10043adf2  mov     r8, r14; pbCertEncoded
0x10043adf5  mov     edx, 1; dwCertEncodingType
  ... truncated ...
```
