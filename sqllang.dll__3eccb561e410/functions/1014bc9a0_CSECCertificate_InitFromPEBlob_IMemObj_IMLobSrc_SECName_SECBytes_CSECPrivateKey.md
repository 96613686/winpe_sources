# CSECCertificate::InitFromPEBlob(IMemObj *,IMLobSrc *,SECName &,SECBytes &,CSECPrivateKey &)

- ea: `0x1014bc9a0`
- end: `0x1014bd917`
- name: `?InitFromPEBlob@CSECCertificate@@QEAA?AVCSECCryptoError@@PEAVIMemObj@@PEAVIMLobSrc@@AEAUSECName@@AEAUSECBytes@@AEAVCSECPrivateKey@@@Z`
- size: `3959`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1014f5320`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004076a0`
- `0x100430d60`
- `0x100754350`
- `0x100755b10`
- `0x1014b2db0`
- `0x1014bb4f0`
- `0x1014bc9a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1014bca51`
- `KERNEL32!GetLastError` at `0x1014bcc88`
- `KERNEL32!GetLastError` at `0x1014bcd55`
- `KERNEL32!GetLastError` at `0x1014bd008`
- `KERNEL32!GetLastError` at `0x1014bd106`
- `KERNEL32!GetLastError` at `0x1014bd208`
- `KERNEL32!GetLastError` at `0x1014bd373`
- `KERNEL32!GetLastError` at `0x1014bd4ae`
- `KERNEL32!GetLastError` at `0x1014bd6ec`
- `KERNEL32!GetLastError` at `0x1014bd7fc`
- `KERNEL32!GetLastError` at `0x1014bd8b4`
- `KERNEL32!GetLastError` at `0x1014bca51`
- `KERNEL32!GetLastError` at `0x1014bcc88`
- `KERNEL32!GetLastError` at `0x1014bcd55`
- `KERNEL32!GetLastError` at `0x1014bd008`
- `KERNEL32!GetLastError` at `0x1014bd106`
- `KERNEL32!GetLastError` at `0x1014bd208`
- `KERNEL32!GetLastError` at `0x1014bd373`
- `KERNEL32!GetLastError` at `0x1014bd4ae`
- `KERNEL32!GetLastError` at `0x1014bd6ec`
- `KERNEL32!GetLastError` at `0x1014bd7fc`
- `KERNEL32!GetLastError` at `0x1014bd8b4`
- `KERNEL32!CloseHandle` at `0x1014bcf69`
- `KERNEL32!CloseHandle` at `0x1014bd145`
- `KERNEL32!CloseHandle` at `0x1014bd841`
- `KERNEL32!CloseHandle` at `0x1014bcf69`
- `KERNEL32!CloseHandle` at `0x1014bd145`
- `KERNEL32!CloseHandle` at `0x1014bd841`
- `KERNEL32!CreateFileW` at `0x1014bce0d`
- `KERNEL32!CreateFileW` at `0x1014bce0d`
- `KERNEL32!WriteFile` at `0x1014bcf37`
- `KERNEL32!WriteFile` at `0x1014bcf37`
- `KERNEL32!DeleteFileW` at `0x1014bd0a7`
- `KERNEL32!DeleteFileW` at `0x1014bd153`
- `KERNEL32!DeleteFileW` at `0x1014bd2a7`
- `KERNEL32!DeleteFileW` at `0x1014bd413`
- `KERNEL32!DeleteFileW` at `0x1014bd54e`
- `KERNEL32!DeleteFileW` at `0x1014bd678`
- `KERNEL32!DeleteFileW` at `0x1014bd78c`
- `KERNEL32!DeleteFileW` at `0x1014bd0a7`
- `KERNEL32!DeleteFileW` at `0x1014bd153`
- `KERNEL32!DeleteFileW` at `0x1014bd2a7`
- `KERNEL32!DeleteFileW` at `0x1014bd413`
- `KERNEL32!DeleteFileW` at `0x1014bd54e`
- `KERNEL32!DeleteFileW` at `0x1014bd678`
- `KERNEL32!DeleteFileW` at `0x1014bd78c`
- `KERNEL32!GetFileType` at `0x1014bce2c`
- `KERNEL32!GetFileType` at `0x1014bce2c`
- `KERNEL32!GetTempPathW` at `0x1014bcc56`
- `KERNEL32!GetTempPathW` at `0x1014bcc56`
- `KERNEL32!GetTempFileNameW` at `0x1014bcd23`
- `KERNEL32!GetTempFileNameW` at `0x1014bcd23`
- `secforwarder!CryptMsgClose` at `0x1014bd099`
- `secforwarder!CryptMsgClose` at `0x1014bd299`
- `secforwarder!CryptMsgClose` at `0x1014bd405`
- `secforwarder!CryptMsgClose` at `0x1014bd540`
- `secforwarder!CryptMsgClose` at `0x1014bd66a`
- `secforwarder!CryptMsgClose` at `0x1014bd77e`
- `secforwarder!CryptMsgClose` at `0x1014bd099`
- `secforwarder!CryptMsgClose` at `0x1014bd299`
- `secforwarder!CryptMsgClose` at `0x1014bd405`
- `secforwarder!CryptMsgClose` at `0x1014bd540`
- `secforwarder!CryptMsgClose` at `0x1014bd66a`
- `secforwarder!CryptMsgClose` at `0x1014bd77e`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd056`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd256`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd3c2`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd4fd`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd627`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd73b`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd056`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd256`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd3c2`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd4fd`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd627`
- `secforwarder!CertFreeCertificateChain` at `0x1014bd73b`
- `secforwarder!CryptQueryObject` at `0x1014bcfd5`
- `secforwarder!CryptQueryObject` at `0x1014bcfd5`
- `secforwarder!CryptMsgGetParam` at `0x1014bd1d5`
- `secforwarder!CryptMsgGetParam` at `0x1014bd340`
- `secforwarder!CryptMsgGetParam` at `0x1014bd1d5`
- `secforwarder!CryptMsgGetParam` at `0x1014bd340`
- `secforwarder!CertGetSubjectCertificateFromStore` at `0x1014bd5a8`
- `secforwarder!CertGetSubjectCertificateFromStore` at `0x1014bd5a8`
- `secforwarder!CertOpenStore` at `0x1014bd47a`
- `secforwarder!CertOpenStore` at `0x1014bd47a`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd065`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd265`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd3d1`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd50c`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd636`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd74a`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd065`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd265`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd3d1`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd50c`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd636`
- `secforwarder!CertFreeCertificateContext` at `0x1014bd74a`
- `secforwarder!CertCloseStore` at `0x1014bd079`
- `secforwarder!CertCloseStore` at `0x1014bd08a`
- `secforwarder!CertCloseStore` at `0x1014bd279`
- `secforwarder!CertCloseStore` at `0x1014bd28a`
- `secforwarder!CertCloseStore` at `0x1014bd3e5`
- `secforwarder!CertCloseStore` at `0x1014bd3f6`
- `secforwarder!CertCloseStore` at `0x1014bd520`
- `secforwarder!CertCloseStore` at `0x1014bd531`
- `secforwarder!CertCloseStore` at `0x1014bd64a`
- `secforwarder!CertCloseStore` at `0x1014bd65b`
- `secforwarder!CertCloseStore` at `0x1014bd75e`
- `secforwarder!CertCloseStore` at `0x1014bd76f`
- `secforwarder!CertCloseStore` at `0x1014bd079`
- `secforwarder!CertCloseStore` at `0x1014bd08a`
- `secforwarder!CertCloseStore` at `0x1014bd279`
- `secforwarder!CertCloseStore` at `0x1014bd28a`
- `secforwarder!CertCloseStore` at `0x1014bd3e5`
- `secforwarder!CertCloseStore` at `0x1014bd3f6`
- `secforwarder!CertCloseStore` at `0x1014bd520`
- `secforwarder!CertCloseStore` at `0x1014bd531`
- `secforwarder!CertCloseStore` at `0x1014bd64a`
- `secforwarder!CertCloseStore` at `0x1014bd65b`
- `secforwarder!CertCloseStore` at `0x1014bd75e`
- `secforwarder!CertCloseStore` at `0x1014bd76f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014bd30f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014bd30f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1014bcb08`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1014bcb08`
- `sqldk!SystemThread_TlsIndex` at `0x1014bcac7`
- `sqldk!SystemThread_TlsIndex` at `0x1014bcb1d`
- `sqldk!SystemThread_TlsIndex` at `0x1014bce69`
- `sqldk!SystemThread_TlsOffset` at `0x1014bcad0`
- `sqldk!SystemThread_TlsOffset` at `0x1014bcb26`
- `sqldk!SystemThread_TlsOffset` at `0x1014bce72`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bcaeb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bcb41`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bce8d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bcaeb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bcb41`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bce8d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bcbd9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bcc44`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd046`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd246`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd31f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd3b2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd4ed`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd60d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd617`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd72b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bcbd9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bcc44`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd046`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd246`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd31f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd3b2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd4ed`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd60d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd617`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bd72b`
- `sqlmin!?GetFileSecurityAttributes@StartUp@@SAPEAU_SECURITY_ATTRIBUTES@@XZ` at `0x1014bcddf`
- `sqlmin!?GetFileSecurityAttributes@StartUp@@SAPEAU_SECURITY_ATTRIBUTES@@XZ` at `0x1014bcddf`

## string_xrefs

- `0x1014bd304`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=45
int *__fastcall CSECCertificate::InitFromPEBlob(
        __int64 a1,
        int *a2,
        struct IMemObj *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v11; // rax
  DWORD v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rdx
  DWORD v18; // eax
  DWORD v19; // eax
  int v20; // r15d
  struct _SECURITY_ATTRIBUTES *FileSecurityAttributes; // rax
  HANDLE FileW; // rax
  HANDLE v23; // rdi
  unsigned int v24; // r13d
  __int64 v25; // rsi
  __int64 v26; // rdi
  unsigned int v27; // r14d
  __int64 v28; // rcx
  DWORD v29; // esi
  __int64 *v30; // rcx
  __int64 v31; // rax
  DWORD v32; // eax
  DWORD v33; // eax
  DWORD v34; // eax
  struct _CERT_INFO *v35; // rdi
  DWORD v36; // eax
  HCERTSTORE v37; // rax
  DWORD v38; // eax
  PCCERT_CONTEXT SubjectCertificateFromStore; // rax
  DWORD cbCertEncoded; // edx
  DWORD v41; // eax
  DWORD v42; // eax
  DWORD LastError; // eax
  int v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h]
  int v47; // [rsp+80h] [rbp-80h] BYREF
  int v48; // [rsp+84h] [rbp-7Ch]
  __int64 v49; // [rsp+88h] [rbp-78h]
  int v50; // [rsp+90h] [rbp-70h] BYREF
  __int64 v51; // [rsp+98h] [rbp-68h]
  __int64 v52; // [rsp+A0h] [rbp-60h]
  __int64 v53; // [rsp+A8h] [rbp-58h]
  __int64 v54; // [rsp+B0h] [rbp-50h]
  bool v55; // [rsp+C0h] [rbp-40h]
  PCCERT_CHAIN_CONTEXT pChainContext[2]; // [rsp+D0h] [rbp-30h]
  HCERTSTORE hCertStore[2]; // [rsp+E0h] [rbp-20h] BYREF
  HCRYPTMSG hCryptMsg; // [rsp+F0h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+F8h] [rbp-8h] BYREF
  int *v60; // [rsp+100h] [rbp+0h]
  DWORD NumberOfBytesWritten; // [rsp+108h] [rbp+8h] BYREF
  HANDLE hFile; // [rsp+110h] [rbp+10h]
  DWORD pdwFormatType; // [rsp+118h] [rbp+18h] BYREF
  DWORD pdwContentType; // [rsp+11Ch] [rbp+1Ch] BYREF
  DWORD pdwMsgAndCertEncodingType; // [rsp+120h] [rbp+20h] BYREF
  WCHAR *v66; // [rsp+128h] [rbp+28h]
  struct IMemObj *v67; // [rsp+130h] [rbp+30h]
  struct _CERT_INFO *v68; // [rsp+138h] [rbp+38h]
  int v69; // [rsp+140h] [rbp+40h]
  int v70; // [rsp+144h] [rbp+44h]
  __int64 v71; // [rsp+148h] [rbp+48h]
  BYTE *pbCertEncoded; // [rsp+150h] [rbp+50h] BYREF
  DWORD v73; // [rsp+158h] [rbp+58h]
  __int64 v74; // [rsp+160h] [rbp+60h]
  int *v75; // [rsp+168h] [rbp+68h]
  _DWORD v76[6]; // [rsp+170h] [rbp+70h] BYREF
  void *v77; // [rsp+188h] [rbp+88h]
  _BYTE v78[24]; // [rsp+198h] [rbp+98h] BYREF
  void *v79; // [rsp+1B0h] [rbp+B0h]
  WCHAR TempFileName[264]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR Buffer[264]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v82[32768]; // [rsp+5E0h] [rbp+4E0h] BYREF

  v74 = -2;
  v67 = a3;
  v60 = (int *)a1;
  v75 = a2;
  v11 = 0;
  if ( !a4 || (v11 = (**(__int64 (__fastcall ***)(__int64))a4)(a4)) == 0 )
  {
    *a2 = 5;
    *(_QWORD *)(a2 + 1) = 50;
    *(_QWORD *)(a2 + 3) = 0;
    a2[5] = 10;
    *((_QWORD *)a2 + 3) = v11;
    a2[9] = v11;
    LastError = GetLastError();
    a2[2] = LastError;
    CSECErrorRingBufferManager::StoreRecord(
      L"Not Available",
      L"Not Available",
      LastError,
      (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
      a2[1]);
    return a2;
  }
  if ( !*(_QWORD *)(a1 + 32) )
  {
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v45, 1);
    hFile = &v47;
    v50 = 536871473;
    v51 = 0;
    v53 = 0;
    v52 = 0;
    v54 = 0;
    v55 = 0;
    v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v14 = *(_QWORD *)(v13 + 256);
    if ( !v14 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v14 = *(_QWORD *)(v13 + 256);
    }
    v15 = *(_QWORD *)(v14 + 600);
    if ( v15 )
      v55 = (unsigned int)SOS_Task::PushWait(v15, &v50) == 0;
    v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v17 = *(_QWORD *)(v16 + 256);
    if ( !v17 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v17 = *(_QWORD *)(v16 + 256);
    }
    v49 = v17;
    v48 = (*(_DWORD *)(v17 + 800) >> 11) & 1;
    if ( v48 || (*(_BYTE *)(v17 + 800) & 4) == 0 )
    {
      v47 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v17 + 608) + 8LL))(*(_QWORD *)(v17 + 608));
    }
    else
    {
      v47 = 0;
    }
    if ( *(_DWORD *)(a5 + 8) )
    {
      CSECPrivateKey::InitFromFile(a7, v76, a3, a5, a6);
      if ( v76[0] )
      {
        *((_QWORD *)a2 + 3) = 0;
        CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)a2, (const struct CSECCryptoError *)v76);
        if ( v77 )
          operator delete[](v77);
        v60 = &v47;
        if ( v47 )
        {
          if ( v48 )
            *(_DWORD *)(v49 + 800) |= 0x800u;
          else
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
              *(_QWORD *)(v49 + 608),
              v49,
              1);
        }
LABEL_23:
        SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v50);
        *(_DWORD *)(v46 + 616) &= ~v45;
        return a2;
      }
      if ( v77 )
        operator delete[](v77);
    }
    if ( GetTempPathW(0x104u, Buffer) )
    {
      if ( GetTempFileNameW(Buffer, L"Tmp", 0, TempFileName) )
      {
        v20 = 0;
        v66 = 0;
        FileSecurityAttributes = (struct _SECURITY_ATTRIBUTES *)StartUp::GetFileSecurityAttributes();
        FileW = CreateFileW(TempFileName, 0x40000000u, 1u, FileSecurityAttributes, 4u, 0x8100080u, 0);
        v23 = FileW;
        hFile = FileW;
        if ( FileW == (HANDLE)-1LL || GetFileType(FileW) != 1 )
        {
          *a2 = 7;
          *(_QWORD *)(a2 + 1) = 29;
          *(_QWORD *)(a2 + 3) = 0;
          a2[5] = 10;
          *((_QWORD *)a2 + 3) = 0;
          a2[9] = 0;
          v42 = GetLastError();
          a2[2] = v42;
          CSECErrorRingBufferManager::StoreRecord(
            L"Not Available",
            L"Not Available",
            v42,
            (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
            a2[1]);
          if ( v23 != (HANDLE)-1LL )
            CloseHandle(v23);
          if ( v47 )
          {
            if ( v48 )
              *(_DWORD *)(v49 + 800) |= 0x800u;
            else
              (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
                *(_QWORD *)(v49 + 608),
                v49,
                1);
          }
        }
        else
        {
          v66 = TempFileName;
          v24 = 0;
          if ( (**(__int64 (__fastcall ***)(__int64))a4)(a4) )
          {
            _mm_lfence();
            while ( 1 )
            {
              v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v26 = *(_QWORD *)(v25 + 256);
              if ( !v26 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v26 = *(_QWORD *)(v25 + 256);
              }
              v71 = v26;
              v27 = *(_DWORD *)(v26 + 800);
              v70 = (v27 >> 11) & 1;
              if ( (v27 & 4) != 0 && (v28 = *(_QWORD *)(v26 + 608)) != 0 )
              {
                v20 = 1;
                v69 = 1;
                (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v28 + 16LL))(v28, v26, 1);
              }
              else
              {
                v69 = 0;
              }
              v29 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a4 + 16LL))(a4, v82, 0x8000);
              if ( v20 )
              {
                v30 = *(__int64 **)(v26 + 608);
                v31 = *v30;
                if ( (v27 & 0x800) != 0 )
                  (*(void (__fastcall **)(__int64 *, __int64))(v31 + 24))(v30, v26);
                else
                  (*(void (__fastcall **)(__int64 *, __int64))(v31 + 8))(v30, v26);
              }
              v20 = 0;
              v23 = hFile;
              if ( !WriteFile(hFile, v82, v29, &NumberOfBytesWritten, 0) || v29 != NumberOfBytesWritten )
                break;
              v24 += v29;
              if ( v24 >= (unsigned __int64)(**(__int64 (__fastcall ***)(__int64))a4)(a4) )
                goto LABEL_55;
            }
            *a2 = 7;
            *(_QWORD *)(a2 + 1) = 30;
            *(_QWORD *)(a2 + 3) = 0;
            a2[5] = 10;
            *((_QWORD *)a2 + 3) = 0;
            a2[9] = 0;
            v33 = GetLastError();
            a2[2] = v33;
            CSECErrorRingBufferManager::StoreRecord(
              L"Not Available",
              L"Not Available",
              v33,
              (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
              a2[1]);
            CloseHandle(v23);
            DeleteFileW(TempFileName);
            if ( v47 )
            {
              if ( v48 )
                *(_DWORD *)(v49 + 800) |= 0x800u;
              else
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
                  *(_QWORD *)(v49 + 608),
                  v49,
                  1);
            }
          }
          else
          {
LABEL_55:
            CloseHandle(v23);
            *(_OWORD *)pChainContext = 0;
            *(_OWORD *)hCertStore = 0;
            hCryptMsg = 0;
            v68 = 0;
            if ( CryptQueryObject(
                   1u,
                   TempFileName,
                   0x400u,
                   2u,
                   0,
                   &pdwMsgAndCertEncodingType,
                   &pdwContentType,
                   &pdwFormatType,
                   &hCertStore[1],
                   &hCryptMsg,
                   0) )
            {
              if ( CryptMsgGetParam(hCryptMsg, 7u, 0, 0, &pcbData) )
              {
                v35 = (struct _CERT_INFO *)operator new[](
                                             pcbData,
                                             v67,
                                             "sql\\ntdbms\\msql\\security\\src\\seccryptmd.cpp",
                                             1009,
                                             3u);
                if ( v35 )
                  operator delete[](0);
                v68 = v35;
                if ( CryptMsgGetParam(hCryptMsg, 7u, 0, v35, &pcbData) )
                {
                  v37 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, hCryptMsg);
                  hCertStore[0] = v37;
                  if ( v37 )
                  {
                    SubjectCertificateFromStore = CertGetSubjectCertificateFromStore(v37, 0x10001u, v35);
                    pChainContext[1] = (PCCERT_CHAIN_CONTEXT)SubjectCertificateFromStore;
                    if ( SubjectCertificateFromStore
                      && (cbCertEncoded = SubjectCertificateFromStore->cbCertEncoded) != 0 )
                    {
                      pbCertEncoded = SubjectCertificateFromStore->pbCertEncoded;
                      v73 = cbCertEncoded;
                      CSECCertificate::InitFromBytes(v60, v78, &pbCertEncoded);
                      *((_QWORD *)a2 + 3) = 0;
                      CSECCryptoError::DeepCopyCSECCryptoError(
                        (CSECCryptoError *)a2,
                        (const struct CSECCryptoError *)v78);
                      if ( v79 )
                        operator delete[](v79);
                      operator delete[](v35);
                      if ( pChainContext[0] )
                        CertFreeCertificateChain(pChainContext[0]);
                      if ( pChainContext[1] )
                        CertFreeCertificateContext((PCCERT_CONTEXT)pChainContext[1]);
                      if ( hCertStore[0] )
                        CertCloseStore(hCertStore[0], 1u);
                      if ( hCertStore[1] )
                        CertCloseStore(hCertStore[1], 0);
                      if ( hCryptMsg )
                        CryptMsgClose(hCryptMsg);
                      DeleteFileW(TempFileName);
                      if ( v47 )
                      {
                        if ( v48 )
                          *(_DWORD *)(v49 + 800) |= 0x800u;
                        else
                          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
                            *(_QWORD *)(v49 + 608),
                            v49,
                            1);
                      }
                    }
                    else
                    {
                      *a2 = 7;
                      *(_QWORD *)(a2 + 1) = 35;
                      *(_QWORD *)(a2 + 3) = 0;
                      a2[5] = 10;
                      *((_QWORD *)a2 + 3) = 0;
                      a2[9] = 0;
                      v41 = GetLastError();
                      a2[2] = v41;
                      CSECErrorRingBufferManager::StoreRecord(
                        L"Not Available",
                        L"Not Available",
                        v41,
                        (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
                        a2[1]);
                      operator delete[](v35);
                      if ( pChainContext[0] )
                        CertFreeCertificateChain(pChainContext[0]);
                      if ( pChainContext[1] )
                        CertFreeCertificateContext((PCCERT_CONTEXT)pChainContext[1]);
                      if ( hCertStore[0] )
                        CertCloseStore(hCertStore[0], 1u);
                      if ( hCertStore[1] )
                        CertCloseStore(hCertStore[1], 0);
                      if ( hCryptMsg )
                        CryptMsgClose(hCryptMsg);
                      DeleteFileW(TempFileName);
                      if ( v47 )
                      {
                        if ( v48 )
                          *(_DWORD *)(v49 + 800) |= 0x800u;
                        else
                          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
                            *(_QWORD *)(v49 + 608),
                            v49,
                            1);
                      }
                    }
                  }
                  else
                  {
                    *a2 = 7;
                    *(_QWORD *)(a2 + 1) = 34;
                    *(_QWORD *)(a2 + 3) = 0;
                    a2[5] = 10;
                    *((_QWORD *)a2 + 3) = 0;
                    a2[9] = 0;
                    v38 = GetLastError();
                    a2[2] = v38;
                    CSECErrorRingBufferManager::StoreRecord(
                      L"Not Available",
                      L"Not Available",
                      v38,
                      (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
                      a2[1]);
                    operator delete[](v35);
                    if ( pChainContext[0] )
                      CertFreeCertificateChain(pChainContext[0]);
                    if ( pChainContext[1] )
                      CertFreeCertificateContext((PCCERT_CONTEXT)pChainContext[1]);
                    if ( hCertStore[0] )
                      CertCloseStore(hCertStore[0], 1u);
                    if ( hCertStore[1] )
                      CertCloseStore(hCertStore[1], 0);
                    if ( hCryptMsg )
                      CryptMsgClose(hCryptMsg);
                    DeleteFileW(TempFileName);
                    if ( v47 )
                    {
                      if ( v48 )
                        *(_DWORD *)(v49 + 800) |= 0x800u;
                      else
                        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
                          *(_QWORD *)(v49 + 608),
                          v49,
                          1);
                    }
                  }
                }
                else
                {
                  *a2 = 7;
                  *(_QWORD *)(a2 + 1) = 33;
                  *(_QWORD *)(a2 + 3) = 0;
                  a2[5] = 10;
                  *((_QWORD *)a2 + 3) = 0;
                  a2[9] = 0;
                  v36 = GetLastError();
                  a2[2] = v36;
                  CSECErrorRingBufferManager::StoreRecord(
                    L"Not Available",
                    L"Not Available",
                    v36,
                    (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
                    a2[1]);
                  operator delete[](v35);
                  if ( pChainContext[0] )
                    CertFreeCertificateChain(pChainContext[0]);
                  if ( pChainContext[1] )
                    CertFreeCertificateContext((PCCERT_CONTEXT)pChainContext[1]);
                  if ( hCertStore[0] )
                    CertCloseStore(hCertStore[0], 1u);
                  if ( hCertStore[1] )
                    CertCloseStore(hCertStore[1], 0);
                  if ( hCryptMsg )
                    CryptMsgClose(hCryptMsg);
                  DeleteFileW(TempFileName);
                  if ( v47 )
                  {
                    if ( v48 )
                      *(_DWORD *)(v49 + 800) |= 0x800u;
                    else
                      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
                        *(_QWORD *)(v49 + 608),
                        v49,
                        1);
                  }
                }
              }
              else
              {
                *a2 = 7;
                *(_QWORD *)(a2 + 1) = 32;
                *(_QWORD *)(a2 + 3) = 0;
                a2[5] = 10;
                *((_QWORD *)a2 + 3) = 0;
                a2[9] = 0;
                v34 = GetLastError();
                a2[2] = v34;
                CSECErrorRingBufferManager::StoreRecord(
                  L"Not Available",
                  L"Not Available",
                  v34,
                  (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
                  a2[1]);
                operator delete[](0);
                if ( pChainContext[0] )
                  CertFreeCertificateChain(pChainContext[0]);
                if ( pChainContext[1] )
                  CertFreeCertificateContext((PCCERT_CONTEXT)pChainContext[1]);
                if ( hCertStore[0] )
                  CertCloseStore(hCertStore[0], 1u);
                if ( hCertStore[1] )
                  CertCloseStore(hCertStore[1], 0);
                if ( hCryptMsg )
                  CryptMsgClose(hCryptMsg);
                DeleteFileW(TempFileName);
                if ( v47 )
                {
                  if ( v48 )
                    *(_DWORD *)(v49 + 800) |= 0x800u;
                  else
                    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
                      *(_QWORD *)(v49 + 608),
                      v49,
                      1);
                }
              }
            }
            else
            {
              *a2 = 7;
              *(_QWORD *)(a2 + 1) = 31;
              *(_QWORD *)(a2 + 3) = 0;
              a2[5] = 10;
              *((_QWORD *)a2 + 3) = 0;
              a2[9] = 0;
              v32 = GetLastError();
              a2[2] = v32;
              CSECErrorRingBufferManager::StoreRecord(
                L"Not Available",
                L"Not Available",
                v32,
                (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
                a2[1]);
              operator delete[](0);
              if ( pChainContext[0] )
                CertFreeCertificateChain(pChainContext[0]);
              if ( pChainContext[1] )
                CertFreeCertificateContext((PCCERT_CONTEXT)pChainContext[1]);
              if ( hCertStore[0] )
                CertCloseStore(hCertStore[0], 1u);
              if ( hCertStore[1] )
                CertCloseStore(hCertStore[1], 0);
              if ( hCryptMsg )
                CryptMsgClose(hCryptMsg);
              DeleteFileW(TempFileName);
              if ( v47 )
              {
                if ( v48 )
                  *(_DWORD *)(v49 + 800) |= 0x800u;
                else
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
                    *(_QWORD *)(v49 + 608),
                    v49,
                    1);
              }
            }
          }
        }
      }
      else
      {
        *a2 = 5;
        *(_QWORD *)(a2 + 1) = 52;
        *(_QWORD *)(a2 + 3) = 0;
        a2[5] = 10;
        *((_QWORD *)a2 + 3) = 0;
        a2[9] = 0;
        v19 = GetLastError();
        a2[2] = v19;
        CSECErrorRingBufferManager::StoreRecord(
          L"Not Available",
          L"Not Available",
          v19,
          (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
          a2[1]);
        v60 = &v47;
        if ( v47 )
        {
          if ( v48 )
            *(_DWORD *)(v49 + 800) |= 0x800u;
          else
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
              *(_QWORD *)(v49 + 608),
              v49,
              1);
        }
      }
    }
    else
    {
      *a2 = 5;
      *(_QWORD *)(a2 + 1) = 51;
      *(_QWORD *)(a2 + 3) = 0;
      a2[5] = 10;
      *((_QWORD *)a2 + 3) = 0;
      a2[9] = 0;
      v18 = GetLastError();
      a2[2] = v18;
      CSECErrorRingBufferManager::StoreRecord(
        L"Not Available",
        L"Not Available",
        v18,
        (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
        a2[1]);
      v60 = &v47;
      if ( v47 )
      {
        if ( v48 )
          *(_DWORD *)(v49 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v49 + 608) + 16LL))(
            *(_QWORD *)(v49 + 608),
            v49,
            1);
      }
    }
    goto LABEL_23;
  }
  *a2 = 3;
  *(_QWORD *)(a2 + 1) = 45;
  *(_QWORD *)(a2 + 3) = 0;
  a2[5] = 10;
  *((_QWORD *)a2 + 3) = 0;
  a2[9] = 0;
  v12 = GetLastError();
  a2[2] = v12;
  CSECErrorRingBufferManager::StoreRecord(
    L"Not Available",
    L"Not Available",
    v12,
    (&CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames)[*a2],
    a2[1]);
  return a2;
}

```

## disassembly

```asm
0x1014bc9a0  push    rbp
0x1014bc9a2  push    rbx
0x1014bc9a3  push    rsi
0x1014bc9a4  push    rdi
0x1014bc9a5  push    r12
0x1014bc9a7  push    r13
0x1014bc9a9  push    r14
0x1014bc9ab  push    r15
0x1014bc9ad  lea     rbp, [rsp-84F8h]
0x1014bc9b5  mov     eax, 85F8h
0x1014bc9ba  call    _alloca_probe
0x1014bc9bf  sub     rsp, rax
0x1014bc9c2  mov     [rbp+8530h+var_84D0], 0FFFFFFFFFFFFFFFEh
0x1014bc9ca  mov     rax, cs:__security_cookie
0x1014bc9d1  xor     rax, rsp
0x1014bc9d4  mov     [rbp+8530h+var_50], rax
0x1014bc9db  mov     r12, r9
0x1014bc9de  mov     r13, r8
0x1014bc9e1  mov     [rbp+8530h+var_8500], r8
0x1014bc9e5  mov     rbx, rdx
0x1014bc9e8  mov     rdi, rcx
0x1014bc9eb  mov     [rbp+8530h+var_8530], rcx
0x1014bc9ef  mov     [rbp+8530h+var_84C8], rdx
0x1014bc9f3  mov     rsi, [rbp+8530h+arg_20]
0x1014bc9fa  mov     r14, [rbp+8530h+arg_28]
0x1014bca01  mov     r15, [rbp+8530h+arg_30]
0x1014bca08  xor     eax, eax
0x1014bca0a  mov     [rsp+8630h+var_85D0], eax
0x1014bca0e  test    r9, r9
0x1014bca11  jz      loc_1014BD890
0x1014bca17  mov     rax, [r9]
0x1014bca1a  mov     rcx, r9
0x1014bca1d  call    qword ptr [rax]
0x1014bca1f  test    rax, rax
0x1014bca22  jz      loc_1014BD890
0x1014bca28  cmp     qword ptr [rdi+20h], 0
0x1014bca2d  jz      short loc_1014BCA8A
0x1014bca2f  mov     dword ptr [rbx], 3
0x1014bca35  mov     qword ptr [rbx+4], 2Dh ; '-'
0x1014bca3d  xor     eax, eax
0x1014bca3f  mov     [rbx+0Ch], rax
0x1014bca43  mov     dword ptr [rbx+14h], 0Ah
0x1014bca4a  mov     [rbx+18h], rax
0x1014bca4e  mov     [rbx+24h], eax
0x1014bca51  call    cs:__imp_GetLastError
0x1014bca57  mov     [rbx+8], eax
0x1014bca5a  movsxd  r9, dword ptr [rbx]
0x1014bca5d  lea     rdx, ?sm_CSECCryptoErrorToWideNames@CSECErrorRingBufferManager@@2PAPEA_WA; wchar_t * near * CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames
0x1014bca64  mov     ecx, [rbx+4]
0x1014bca67  mov     [rsp+8630h+dwCreationDisposition], ecx; int
0x1014bca6b  mov     r9, [rdx+r9*8]; wchar_t *
0x1014bca6f  mov     r8d, eax; unsigned int
0x1014bca72  lea     rdx, ?wszNotAvailable@CSECErrorAPI@@2QB_WB; "Not Available"
0x1014bca79  lea     rcx, ?wszNotAvailable@CSECErrorAPI@@2QB_WB; "Not Available"
0x1014bca80  call    ?StoreRecord@CSECErrorRingBufferManager@@SAXPEB_W0KPEA_WH@Z; CSECErrorRingBufferManager::StoreRecord(wchar_t const *,wchar_t const *,ulong,wchar_t *,int)
0x1014bca85  jmp     loc_1014BD8E9
0x1014bca8a  mov     edx, 1
0x1014bca8f  lea     rcx, [rsp+8630h+var_85C0]
0x1014bca94  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x1014bca99  nop
0x1014bca9a  lea     rax, [rbp+8530h+var_85B0]
0x1014bca9e  mov     [rbp+8530h+hFile], rax
0x1014bcaa2  mov     [rbp+8530h+var_85A0], 20000231h
0x1014bcaa9  xor     eax, eax
0x1014bcaab  mov     [rbp+8530h+var_8598], rax
0x1014bcaaf  mov     [rbp+8530h+var_8588], rax
0x1014bcab3  mov     [rbp+8530h+var_8590], rax
0x1014bcab7  mov     [rbp+8530h+var_8580], rax
0x1014bcabb  mov     [rbp+8530h+var_8570], al
0x1014bcabe  mov     rdx, gs:58h
0x1014bcac7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1014bcace  mov     ecx, [rax]
0x1014bcad0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1014bcad7  mov     edi, [rax]
0x1014bcad9  add     rdi, [rdx+rcx*8]
0x1014bcadd  mov     rax, [rdi+100h]
0x1014bcae4  test    rax, rax
0x1014bcae7  jnz     short loc_1014BCAF8
0x1014bcae9  xor     ecx, ecx
0x1014bcaeb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1014bcaf1  mov     rax, [rdi+100h]
0x1014bcaf8  mov     rcx, [rax+258h]
0x1014bcaff  test    rcx, rcx
0x1014bcb02  jz      short loc_1014BCB14
0x1014bcb04  lea     rdx, [rbp+8530h+var_85A0]
0x1014bcb08  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x1014bcb0e  test    eax, eax
0x1014bcb10  setz    [rbp+8530h+var_8570]
0x1014bcb14  mov     rdx, gs:58h
0x1014bcb1d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1014bcb24  mov     ecx, [rax]
0x1014bcb26  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1014bcb2d  mov     edi, [rax]
0x1014bcb2f  add     rdi, [rdx+rcx*8]
0x1014bcb33  mov     rdx, [rdi+100h]
0x1014bcb3a  test    rdx, rdx
0x1014bcb3d  jnz     short loc_1014BCB4E
0x1014bcb3f  xor     ecx, ecx
0x1014bcb41  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1014bcb47  mov     rdx, [rdi+100h]
0x1014bcb4e  mov     [rbp+8530h+var_85A8], rdx
0x1014bcb52  mov     eax, [rdx+320h]
0x1014bcb58  shr     eax, 0Bh
0x1014bcb5b  and     eax, 1
0x1014bcb5e  mov     [rbp+8530h+var_85AC], eax
0x1014bcb61  jnz     short loc_1014BCB73
0x1014bcb63  test    byte ptr [rdx+320h], 4
0x1014bcb6a  jz      short loc_1014BCB73
0x1014bcb6c  xor     edi, edi
0x1014bcb6e  mov     [rbp+8530h+var_85B0], edi
0x1014bcb71  jmp     short loc_1014BCB89
0x1014bcb73  mov     [rbp+8530h+var_85B0], 1
0x1014bcb7a  mov     rcx, [rdx+260h]
0x1014bcb81  mov     rax, [rcx]
0x1014bcb84  call    qword ptr [rax+8]
0x1014bcb87  xor     edi, edi
0x1014bcb89  cmp     dword ptr [rsi+8], 0
0x1014bcb8d  jz      loc_1014BCC4A
0x1014bcb93  mov     qword ptr [rsp+8630h+dwCreationDisposition], r14
0x1014bcb98  mov     r9, rsi
0x1014bcb9b  mov     r8, r13
0x1014bcb9e  lea     rdx, [rbp+8530h+var_84C0]
0x1014bcba2  mov     rcx, r15
0x1014bcba5  call    ?InitFromFile@CSECPrivateKey@@QEAA?AVCSECCryptoError@@PEAVIMemObj@@AEAUSECName@@AEAUSECBytes@@@Z; CSECPrivateKey::InitFromFile(IMemObj *,SECName &,SECBytes &)
0x1014bcbaa  nop
0x1014bcbab  cmp     [rbp+8530h+var_84C0], 0
0x1014bcbaf  jz      loc_1014BCC38
0x1014bcbb5  mov     [rbx+18h], rdi
0x1014bcbb9  lea     rdx, [rbp+8530h+var_84C0]; struct CSECCryptoError *
0x1014bcbbd  mov     rcx, rbx; this
0x1014bcbc0  call    ?DeepCopyCSECCryptoError@CSECCryptoError@@AEAAXAEBV1@@Z; CSECCryptoError::DeepCopyCSECCryptoError(CSECCryptoError const &)
0x1014bcbc5  mov     [rsp+8630h+var_85D0], 1
0x1014bcbcd  mov     rcx, [rbp+8530h+var_84A8]
0x1014bcbd4  test    rcx, rcx
0x1014bcbd7  jz      short loc_1014BCBE0
0x1014bcbd9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1014bcbdf  nop
0x1014bcbe0  lea     rax, [rbp+8530h+var_85B0]
0x1014bcbe4  mov     [rbp+8530h+var_8530], rax
0x1014bcbe8  cmp     [rbp+8530h+var_85B0], 0
0x1014bcbec  jz      short loc_1014BCC18
0x1014bcbee  mov     rdx, [rbp+8530h+var_85A8]
0x1014bcbf2  mov     rcx, [rdx+260h]
0x1014bcbf9  cmp     [rbp+8530h+var_85AC], 0
0x1014bcbfd  jz      short loc_1014BCC0B
0x1014bcbff  or      dword ptr [rdx+320h], 800h
0x1014bcc09  jmp     short loc_1014BCC18
0x1014bcc0b  mov     rax, [rcx]
0x1014bcc0e  mov     r8d, 1
0x1014bcc14  call    qword ptr [rax+10h]
0x1014bcc17  nop
0x1014bcc18  lea     rcx, [rbp+8530h+var_85A0]; this
0x1014bcc1c  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x1014bcc21  nop
0x1014bcc22  mov     rcx, [rsp+8630h+var_85B8]
0x1014bcc27  mov     eax, [rsp+8630h+var_85C0]
0x1014bcc2b  not     eax
0x1014bcc2d  and     [rcx+268h], eax
0x1014bcc33  jmp     loc_1014BD8F1
0x1014bcc38  mov     rcx, [rbp+8530h+var_84A8]
0x1014bcc3f  test    rcx, rcx
0x1014bcc42  jz      short loc_1014BCC4A
0x1014bcc44  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1014bcc4a  lea     rdx, [rbp+8530h+Buffer]; lpBuffer
0x1014bcc51  mov     ecx, 104h; nBufferLength
0x1014bcc56  call    cs:__imp_GetTempPathW
0x1014bcc5c  test    eax, eax
0x1014bcc5e  jnz     loc_1014BCD0B
0x1014bcc64  mov     dword ptr [rbx], 5
0x1014bcc6a  mov     qword ptr [rbx+4], 33h ; '3'
0x1014bcc72  mov     qword ptr [rbx+0Ch], 0
0x1014bcc7a  mov     dword ptr [rbx+14h], 0Ah
0x1014bcc81  mov     [rbx+18h], rdi
0x1014bcc85  mov     [rbx+24h], edi
0x1014bcc88  call    cs:__imp_GetLastError
0x1014bcc8e  mov     [rbx+8], eax
0x1014bcc91  movsxd  r9, dword ptr [rbx]
0x1014bcc94  lea     rdx, ?sm_CSECCryptoErrorToWideNames@CSECErrorRingBufferManager@@2PAPEA_WA; wchar_t * near * CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames
0x1014bcc9b  mov     ecx, [rbx+4]
0x1014bcc9e  mov     [rsp+8630h+dwCreationDisposition], ecx; int
0x1014bcca2  mov     r9, [rdx+r9*8]; wchar_t *
0x1014bcca6  mov     r8d, eax; unsigned int
0x1014bcca9  lea     rdx, ?wszNotAvailable@CSECErrorAPI@@2QB_WB; "Not Available"
0x1014bccb0  lea     rcx, ?wszNotAvailable@CSECErrorAPI@@2QB_WB; "Not Available"
0x1014bccb7  call    ?StoreRecord@CSECErrorRingBufferManager@@SAXPEB_W0KPEA_WH@Z; CSECErrorRingBufferManager::StoreRecord(wchar_t const *,wchar_t const *,ulong,wchar_t *,int)
0x1014bccbc  mov     [rsp+8630h+var_85D0], 1
0x1014bccc4  lea     rax, [rbp+8530h+var_85B0]
0x1014bccc8  mov     [rbp+8530h+var_8530], rax
0x1014bcccc  cmp     [rbp+8530h+var_85B0], 0
0x1014bccd0  jz      short loc_1014BCCFC
0x1014bccd2  mov     rdx, [rbp+8530h+var_85A8]
0x1014bccd6  mov     rcx, [rdx+260h]
0x1014bccdd  cmp     [rbp+8530h+var_85AC], 0
0x1014bcce1  jz      short loc_1014BCCEF
0x1014bcce3  or      dword ptr [rdx+320h], 800h
0x1014bcced  jmp     short loc_1014BCCFC
0x1014bccef  mov     rax, [rcx]
0x1014bccf2  mov     r8d, 1
0x1014bccf8  call    qword ptr [rax+10h]
0x1014bccfb  nop
0x1014bccfc  lea     rcx, [rbp+8530h+var_85A0]; this
0x1014bcd00  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x1014bcd05  nop
0x1014bcd06  jmp     loc_1014BCC22
0x1014bcd0b  lea     r9, [rbp+8530h+TempFileName]; lpTempFileName
0x1014bcd12  xor     r8d, r8d; uUnique
0x1014bcd15  lea     rdx, PrefixString; "Tmp"
0x1014bcd1c  lea     rcx, [rbp+8530h+Buffer]; lpPathName
0x1014bcd23  call    cs:__imp_GetTempFileNameW
0x1014bcd29  test    eax, eax
0x1014bcd2b  jnz     loc_1014BCDD8
0x1014bcd31  mov     dword ptr [rbx], 5
0x1014bcd37  mov     qword ptr [rbx+4], 34h ; '4'
0x1014bcd3f  mov     qword ptr [rbx+0Ch], 0
0x1014bcd47  mov     dword ptr [rbx+14h], 0Ah
0x1014bcd4e  mov     [rbx+18h], rdi
0x1014bcd52  mov     [rbx+24h], edi
0x1014bcd55  call    cs:__imp_GetLastError
0x1014bcd5b  mov     [rbx+8], eax
0x1014bcd5e  movsxd  r9, dword ptr [rbx]
0x1014bcd61  lea     rdx, ?sm_CSECCryptoErrorToWideNames@CSECErrorRingBufferManager@@2PAPEA_WA; wchar_t * near * CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames
0x1014bcd68  mov     ecx, [rbx+4]
0x1014bcd6b  mov     [rsp+8630h+dwCreationDisposition], ecx; int
0x1014bcd6f  mov     r9, [rdx+r9*8]; wchar_t *
0x1014bcd73  mov     r8d, eax; unsigned int
0x1014bcd76  lea     rdx, ?wszNotAvailable@CSECErrorAPI@@2QB_WB; "Not Available"
0x1014bcd7d  lea     rcx, ?wszNotAvailable@CSECErrorAPI@@2QB_WB; "Not Available"
0x1014bcd84  call    ?StoreRecord@CSECErrorRingBufferManager@@SAXPEB_W0KPEA_WH@Z; CSECErrorRingBufferManager::StoreRecord(wchar_t const *,wchar_t const *,ulong,wchar_t *,int)
0x1014bcd89  mov     [rsp+8630h+var_85D0], 1
0x1014bcd91  lea     rax, [rbp+8530h+var_85B0]
0x1014bcd95  mov     [rbp+8530h+var_8530], rax
0x1014bcd99  cmp     [rbp+8530h+var_85B0], 0
0x1014bcd9d  jz      short loc_1014BCDC9
0x1014bcd9f  mov     rdx, [rbp+8530h+var_85A8]
0x1014bcda3  mov     rcx, [rdx+260h]
0x1014bcdaa  cmp     [rbp+8530h+var_85AC], 0
0x1014bcdae  jz      short loc_1014BCDBC
0x1014bcdb0  or      dword ptr [rdx+320h], 800h
0x1014bcdba  jmp     short loc_1014BCDC9
0x1014bcdbc  mov     rax, [rcx]
0x1014bcdbf  mov     r8d, 1
0x1014bcdc5  call    qword ptr [rax+10h]
0x1014bcdc8  nop
0x1014bcdc9  lea     rcx, [rbp+8530h+var_85A0]; this
0x1014bcdcd  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x1014bcdd2  nop
0x1014bcdd3  jmp     loc_1014BCC22
0x1014bcdd8  xor     r15d, r15d
0x1014bcddb  mov     [rbp+8530h+var_8508], r15
0x1014bcddf  call    cs:__imp_?GetFileSecurityAttributes@StartUp@@SAPEAU_SECURITY_ATTRIBUTES@@XZ; StartUp::GetFileSecurityAttributes(void)
0x1014bcde5  mov     r9, rax; lpSecurityAttributes
0x1014bcde8  mov     [rsp+8630h+hTemplateFile], r15; hTemplateFile
0x1014bcded  mov     [rsp+8630h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x1014bcdf5  mov     [rsp+8630h+dwCreationDisposition], 4; dwCreationDisposition
0x1014bcdfd  mov     edx, 40000000h; dwDesiredAccess
0x1014bce02  lea     r8d, [r15+1]; dwShareMode
0x1014bce06  lea     rcx, [rbp+8530h+TempFileName]; lpFileName
0x1014bce0d  call    cs:__imp_CreateFileW
0x1014bce13  mov     rdi, rax
0x1014bce16  mov     [rbp+8530h+hFile], rax
0x1014bce1a  mov     [rsp+8630h+var_85C8], rax
0x1014bce1f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1014bce23  jz      loc_1014BD7DB
0x1014bce29  mov     rcx, rax; hFile
0x1014bce2c  call    cs:__imp_GetFileType
0x1014bce32  cmp     eax, 1
0x1014bce35  jnz     loc_1014BD7DB
0x1014bce3b  lea     rax, [rbp+8530h+TempFileName]
0x1014bce42  mov     [rbp+8530h+var_8508], rax
0x1014bce46  mov     r13d, r15d
0x1014bce49  mov     rax, [r12]
0x1014bce4d  mov     rcx, r12
0x1014bce50  call    qword ptr [rax]
0x1014bce52  test    rax, rax
0x1014bce55  jz      loc_1014BCF66
0x1014bce5b  lfence
0x1014bce5e  xchg    ax, ax
0x1014bce60  mov     rdx, gs:58h
0x1014bce69  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1014bce70  mov     ecx, [rax]
0x1014bce72  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1014bce79  mov     esi, [rax]
0x1014bce7b  add     rsi, [rdx+rcx*8]
0x1014bce7f  mov     rdi, [rsi+100h]
0x1014bce86  test    rdi, rdi
0x1014bce89  jnz     short loc_1014BCE9A
0x1014bce8b  xor     ecx, ecx
0x1014bce8d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1014bce93  mov     rdi, [rsi+100h]
0x1014bce9a  mov     [rbp+8530h+var_84E8], rdi
0x1014bce9e  mov     r14d, [rdi+320h]
0x1014bcea5  mov     eax, r14d
0x1014bcea8  shr     eax, 0Bh
0x1014bceab  and     eax, 1
0x1014bceae  mov     [rbp+8530h+var_84EC], eax
0x1014bceb1  test    r14b, 4
0x1014bceb5  jz      short loc_1014BCEDB
0x1014bceb7  mov     rcx, [rdi+260h]
0x1014bcebe  test    rcx, rcx
0x1014bcec1  jz      short loc_1014BCEDB
  ... truncated ...
```
