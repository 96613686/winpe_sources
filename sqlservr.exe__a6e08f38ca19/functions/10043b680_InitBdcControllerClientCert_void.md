# InitBdcControllerClientCert(void)

- ea: `0x10043b680`
- end: `0x10043bd95`
- name: `?InitBdcControllerClientCert@@YAXXZ`
- size: `1813`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x100412470`

## callees

- `0x1004012e0`
- `0x100401580`
- `0x1004019a0`
- `0x100402ec0`
- `0x10043b680`
- `0x100440340`
- `0x1004403d0`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x10043b936`
- `CRYPT32!PFXIsPFXBlob` at `0x10043ba91`
- `CRYPT32!PFXIsPFXBlob` at `0x10043ba91`
- `CRYPT32!PFXImportCertStore` at `0x10043bab3`
- `CRYPT32!PFXImportCertStore` at `0x10043bab3`
- `CRYPT32!CertEnumCertificatesInStore` at `0x10043bb0e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x10043bb0e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x10043bbe2`
- `CRYPT32!CertAddCertificateContextToStore` at `0x10043bbe2`
- `CRYPT32!CertCloseStore` at `0x10043b8c3`
- `CRYPT32!CertCloseStore` at `0x10043b900`
- `CRYPT32!CertOpenStore` at `0x10043bb7f`
- `CRYPT32!CertOpenStore` at `0x10043bb7f`
- `KERNEL32!CreateFileW` at `0x10043b995`
- `KERNEL32!CreateFileW` at `0x10043b995`
- `KERNEL32!ReadFile` at `0x10043ba68`
- `KERNEL32!ReadFile` at `0x10043ba68`
- `KERNEL32!GetEnvironmentVariableW` at `0x10043b7db`
- `KERNEL32!GetEnvironmentVariableW` at `0x10043b7db`
- `KERNEL32!GetFileSizeEx` at `0x10043b9be`
- `KERNEL32!GetFileSizeEx` at `0x10043b9be`
- `KERNEL32!CloseHandle` at `0x10043bcd1`
- `KERNEL32!CloseHandle` at `0x10043bcd1`
- `KERNEL32!GetLastError` at `0x10043b9a9`
- `KERNEL32!GetLastError` at `0x10043b9c8`
- `KERNEL32!GetLastError` at `0x10043ba72`
- `KERNEL32!GetLastError` at `0x10043ba9b`
- `KERNEL32!GetLastError` at `0x10043babe`
- `KERNEL32!GetLastError` at `0x10043bb1c`
- `KERNEL32!GetLastError` at `0x10043bb8a`
- `KERNEL32!GetLastError` at `0x10043bbec`
- `KERNEL32!GetLastError` at `0x10043bcec`
- `KERNEL32!GetLastError` at `0x10043b9a9`
- `KERNEL32!GetLastError` at `0x10043b9c8`
- `KERNEL32!GetLastError` at `0x10043ba72`
- `KERNEL32!GetLastError` at `0x10043ba9b`
- `KERNEL32!GetLastError` at `0x10043babe`
- `KERNEL32!GetLastError` at `0x10043bb1c`
- `KERNEL32!GetLastError` at `0x10043bb8a`
- `KERNEL32!GetLastError` at `0x10043bbec`
- `KERNEL32!GetLastError` at `0x10043bcec`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10043baec`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10043bb48`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10043bbb8`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10043bc1a`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10043bc2f`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10043bcd9`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043ba1d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043bcc1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043ba1d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043bcc1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043b72a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043b780`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043b8af`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043b72a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043b780`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043b8af`
- `sqldk!SystemThread_TlsOffset` at `0x10043b70f`
- `sqldk!SystemThread_TlsOffset` at `0x10043b765`
- `sqldk!SystemThread_TlsOffset` at `0x10043b894`
- `sqldk!SystemThread_TlsIndex` at `0x10043b706`
- `sqldk!SystemThread_TlsIndex` at `0x10043b75c`
- `sqldk!SystemThread_TlsIndex` at `0x10043b88b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043ba0d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043ba0d`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10043ba4d`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10043ba4d`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bad0`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bb2e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bb9c`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bbfe`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bc53`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bcfe`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bad0`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bb2e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bb9c`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bbfe`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bc53`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043bcfe`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043b747`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043b747`

## string_xrefs

- `0x10043bbc2`: `Unable to open store.\n`
- `0x10043bc39`: `Successfully installed BDC Controller Client certificate to the store.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void InitBdcControllerClientCert(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  WCHAR *v6; // rax
  __int64 v7; // rbx
  WCHAR *v8; // rcx
  __int64 v9; // rax
  char *v10; // r8
  WCHAR v11; // dx
  WCHAR *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  struct IMemObj *v15; // rbx
  HANDLE FileW; // rax
  void *v17; // rdi
  void *v18; // rbx
  DWORD v19; // ecx
  HCERTSTORE v20; // rax
  DWORD v21; // eax
  wchar_t *v22; // rax
  const CERT_CONTEXT *v23; // rbx
  DWORD v24; // eax
  wchar_t *v25; // rax
  HCERTSTORE v26; // rax
  DWORD v27; // eax
  wchar_t *v28; // rax
  DWORD v29; // eax
  wchar_t *v30; // rax
  wchar_t *v31; // rax
  DWORD LastError; // eax
  wchar_t *OSErrString; // rax
  char v34; // [rsp+40h] [rbp-C0h] BYREF
  char v35; // [rsp+41h] [rbp-BFh] BYREF
  char v36; // [rsp+42h] [rbp-BEh] BYREF
  LARGE_INTEGER FileSize; // [rsp+48h] [rbp-B8h] BYREF
  void *v38; // [rsp+50h] [rbp-B0h]
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h]
  int *v41; // [rsp+68h] [rbp-98h]
  CRYPT_DATA_BLOB pPFX; // [rsp+70h] [rbp-90h] BYREF
  int v43; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+88h] [rbp-78h]
  int v45; // [rsp+90h] [rbp-70h] BYREF
  int v46; // [rsp+94h] [rbp-6Ch]
  __int64 v47; // [rsp+98h] [rbp-68h]
  int v48; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-58h]
  __int64 v50; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  __int64 v52; // [rsp+C0h] [rbp-40h]
  bool v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+E0h] [rbp-20h]
  _QWORD *v55; // [rsp+E8h] [rbp-18h]
  char *v56; // [rsp+F0h] [rbp-10h]
  _QWORD *v57; // [rsp+F8h] [rbp-8h]
  char *v58; // [rsp+100h] [rbp+0h]
  _QWORD *v59; // [rsp+108h] [rbp+8h]
  char *v60; // [rsp+110h] [rbp+10h]
  _BYTE v61[4096]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v62[3]; // [rsp+1120h] [rbp+1020h] BYREF
  int v63; // [rsp+1138h] [rbp+1038h]
  _QWORD v64[3]; // [rsp+11F0h] [rbp+10F0h] BYREF
  int v65; // [rsp+1208h] [rbp+1108h]
  _QWORD v66[26]; // [rsp+12C0h] [rbp+11C0h] BYREF
  WCHAR Buffer[264]; // [rsp+1390h] [rbp+1290h] BYREF

  v54 = -2;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v43, 1);
  v41 = &v45;
  v48 = 4195779;
  v49 = 0;
  v51 = 0;
  v50 = 0;
  v52 = 0;
  v53 = 0;
  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v1 = *(_QWORD *)(v0 + 256);
  if ( !v1 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v1 = *(_QWORD *)(v0 + 256);
  }
  v2 = *(_QWORD *)(v1 + 600);
  if ( v2 )
    v53 = (unsigned int)SOS_Task::PushWait(v2, &v48) == 0;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v47 = v4;
  v46 = (*(_DWORD *)(v4 + 800) >> 11) & 1;
  if ( v46 || (*(_BYTE *)(v4 + 800) & 4) == 0 )
  {
    v45 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 608) + 8LL))(*(_QWORD *)(v4 + 608));
  }
  else
  {
    v45 = 0;
  }
  GetEnvironmentVariableW(L"MSSQL_CERTIFICATES_LOCATION", Buffer, 0x104u);
  v5 = 260;
  v6 = Buffer;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  if ( !v5 )
    goto LABEL_54;
  v7 = v5;
  v8 = &Buffer[260 - v5];
  v9 = 2147483646;
  v10 = (char *)((char *)L"/mssql-controller-client/mssql-controller-client-certificate.p12" - (char *)v8);
  do
  {
    if ( !v9 )
      break;
    v11 = *(WCHAR *)((char *)v8 + (_QWORD)v10);
    if ( !v11 )
      break;
    *v8++ = v11;
    --v9;
    --v7;
  }
  while ( v7 );
  v12 = v8 - 1;
  if ( v7 )
    v12 = v8;
  *v12 = 0;
  if ( !v7 )
  {
LABEL_54:
    SOS_OS_LogUnlocalizedRoutine(L"Error in determining BDC controller client certificate location.\n");
    LastError = GetLastError();
    OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v61, 0, 0);
    scierrlogwithstate(0xC337u, 10, 1, OSErrString);
    goto LABEL_55;
  }
  v40 = -1;
  v38 = 0;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v14 = *(_QWORD *)(v13 + 256);
  if ( !v14 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v14 = *(_QWORD *)(v13 + 256);
  }
  v15 = *(struct IMemObj **)(v14 + 1000);
  v64[1] = CertCloseStore;
  v64[2] = 0;
  v65 = 0;
  v64[0] = &FunctionCallBinderVirtual_2<void,int (*)(void *,unsigned long),void *,int>::`vftable';
  v55 = v64;
  v56 = &v36;
  v62[1] = CertCloseStore;
  v62[2] = 0;
  v63 = 0;
  v62[0] = &FunctionCallBinderVirtual_2<void,int (*)(void *,unsigned long),void *,int>::`vftable';
  v57 = v62;
  v58 = &v35;
  v66[1] = CertFreeCertificateContext;
  v66[2] = 0;
  v66[0] = &FunctionCallBinderVirtual_1<void,int (*)(_CERT_CONTEXT const *),_CERT_CONTEXT const *>::`vftable';
  v59 = v66;
  v60 = &v34;
  FileW = CreateFileW(Buffer, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v17 = FileW;
  v40 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL && GetFileSizeEx(FileW, &FileSize) )
  {
    if ( !FileSize.LowPart || FileSize.HighPart )
    {
      v19 = 13;
      goto LABEL_45;
    }
    v18 = operator new[](FileSize.LowPart + 1, v15, 1, "sql\\ntdbms\\ksource\\bdc.cpp", 501, 6u);
    if ( v18 )
    {
      operator delete[](0);
      v38 = v18;
    }
    else
    {
      v38 = 0;
      scierrlog(0x42F2u, L"InitBdcControllerClientCert");
      SQLExit(145, 0, 2147942414LL);
    }
    if ( ReadFile(v17, v18, FileSize.LowPart, &NumberOfBytesRead, 0) )
    {
      pPFX.cbData = FileSize.LowPart;
      pPFX.pbData = (BYTE *)v18;
      if ( PFXIsPFXBlob(&pPFX) )
      {
        v20 = PFXImportCertStore(&pPFX, 0, 0x21u);
        if ( v20 )
        {
          v36 = 1;
          v23 = CertEnumCertificatesInStore(v20, 0);
          if ( v23 )
          {
            v34 = 1;
            v26 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"MY");
            if ( v26 )
            {
              v35 = 1;
              if ( CertAddCertificateContextToStore(v26, v23, 3u, 0) )
              {
                SOS_OS_LogUnlocalizedRoutine(L"Successfully installed BDC Controller Client certificate to the store.\n");
              }
              else
              {
                v29 = GetLastError();
                v30 = GetOSErrString(v29, (struct ErrorStringHolder *)v61, 0, 0);
                scierrlogwithstate(0xC337u, 10, 1, v30);
                SOS_OS_LogUnlocalizedRoutine(L"Failed to add cert to store.\n");
              }
            }
            else
            {
              v27 = GetLastError();
              v28 = GetOSErrString(v27, (struct ErrorStringHolder *)v61, 0, 0);
              scierrlogwithstate(0xC337u, 10, 1, v28);
              SOS_OS_LogUnlocalizedRoutine(L"Unable to open store.\n");
            }
          }
          else
          {
            v24 = GetLastError();
            v25 = GetOSErrString(v24, (struct ErrorStringHolder *)v61, 0, 0);
            scierrlogwithstate(0xC337u, 10, 1, v25);
            SOS_OS_LogUnlocalizedRoutine(L"Unable to enumerate certificates in certificate store.\n");
          }
        }
        else
        {
          v21 = GetLastError();
          v22 = GetOSErrString(v21, (struct ErrorStringHolder *)v61, 0, 0);
          scierrlogwithstate(0xC337u, 10, 1, v22);
          SOS_OS_LogUnlocalizedRoutine(L"Unable to import certificate.\n");
        }
        goto LABEL_46;
      }
    }
  }
  v19 = GetLastError();
LABEL_45:
  v31 = GetOSErrString(v19, (struct ErrorStringHolder *)v61, 0, 0);
  scierrlogwithstate(0xC337u, 10, 1, v31);
LABEL_46:
  if ( v34 )
    (*(void (__fastcall **)(_QWORD *))(v66[0] + 8LL))(v66);
  if ( v35 )
    (*(void (__fastcall **)(_QWORD *))(v62[0] + 8LL))(v62);
  if ( v36 )
    (*(void (__fastcall **)(_QWORD *))(v64[0] + 8LL))(v64);
  operator delete[](v38);
  if ( v17 != (void *)-1LL )
    CloseHandle(v17);
LABEL_55:
  v41 = &v45;
  if ( v45 )
  {
    if ( v46 )
      *(_DWORD *)(v47 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v47 + 608) + 16LL))(
        *(_QWORD *)(v47 + 608),
        v47,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v48);
  *(_DWORD *)(v44 + 616) &= ~v43;
}

```

## disassembly

```asm
0x10043b680  push    rbp
0x10043b682  lea     rbp, [rsp-14B0h]
0x10043b68a  mov     eax, 15B0h
0x10043b68f  call    _alloca_probe
0x10043b694  sub     rsp, rax
0x10043b697  mov     [rbp+14B0h+var_14D0], 0FFFFFFFFFFFFFFFEh
0x10043b69f  mov     [rsp+15B0h+arg_0], rbx
0x10043b6a7  mov     [rsp+15B0h+arg_8], rsi
0x10043b6af  mov     [rsp+15B0h+arg_10], rdi
0x10043b6b7  mov     rax, cs:__security_cookie
0x10043b6be  xor     rax, rsp
0x10043b6c1  mov     [rbp+14B0h+var_10], rax
0x10043b6c8  mov     edx, 1
0x10043b6cd  lea     rcx, [rbp+14B0h+var_1530]
0x10043b6d1  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10043b6d6  nop
0x10043b6d7  lea     rax, [rbp+14B0h+var_1520]
0x10043b6db  mov     [rsp+15B0h+var_1548], rax
0x10043b6e0  mov     [rbp+14B0h+var_1510], 4005C3h
0x10043b6e7  xor     esi, esi
0x10043b6e9  mov     [rbp+14B0h+var_1508], rsi
0x10043b6ed  mov     [rbp+14B0h+var_14F8], rsi
0x10043b6f1  mov     [rbp+14B0h+var_1500], rsi
0x10043b6f5  mov     [rbp+14B0h+var_14F0], rsi
0x10043b6f9  mov     [rbp+14B0h+var_14E0], sil
0x10043b6fd  mov     rdx, gs:58h
0x10043b706  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043b70d  mov     ecx, [rax]
0x10043b70f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043b716  mov     ebx, [rax]
0x10043b718  add     rbx, [rdx+rcx*8]
0x10043b71c  mov     rax, [rbx+100h]
0x10043b723  test    rax, rax
0x10043b726  jnz     short loc_10043B737
0x10043b728  xor     ecx, ecx
0x10043b72a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043b730  mov     rax, [rbx+100h]
0x10043b737  mov     rcx, [rax+258h]
0x10043b73e  test    rcx, rcx
0x10043b741  jz      short loc_10043B753
0x10043b743  lea     rdx, [rbp+14B0h+var_1510]
0x10043b747  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10043b74d  test    eax, eax
0x10043b74f  setz    [rbp+14B0h+var_14E0]
0x10043b753  mov     rdx, gs:58h
0x10043b75c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043b763  mov     ecx, [rax]
0x10043b765  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043b76c  mov     ebx, [rax]
0x10043b76e  add     rbx, [rdx+rcx*8]
0x10043b772  mov     rdx, [rbx+100h]
0x10043b779  test    rdx, rdx
0x10043b77c  jnz     short loc_10043B78D
0x10043b77e  xor     ecx, ecx
0x10043b780  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043b786  mov     rdx, [rbx+100h]
0x10043b78d  mov     [rbp+14B0h+var_1518], rdx
0x10043b791  mov     eax, [rdx+320h]
0x10043b797  shr     eax, 0Bh
0x10043b79a  and     eax, 1
0x10043b79d  mov     [rbp+14B0h+var_151C], eax
0x10043b7a0  jnz     short loc_10043B7B0
0x10043b7a2  test    byte ptr [rdx+320h], 4
0x10043b7a9  jz      short loc_10043B7B0
0x10043b7ab  mov     [rbp+14B0h+var_1520], esi
0x10043b7ae  jmp     short loc_10043B7C5
0x10043b7b0  mov     [rbp+14B0h+var_1520], 1
0x10043b7b7  mov     rcx, [rdx+260h]
0x10043b7be  mov     rax, [rcx]
0x10043b7c1  call    qword ptr [rax+8]
0x10043b7c4  nop
0x10043b7c5  mov     ebx, 104h
0x10043b7ca  mov     r8d, ebx; nSize
0x10043b7cd  lea     rdx, [rbp+14B0h+Buffer]; lpBuffer
0x10043b7d4  lea     rcx, aMssqlCertifica; "MSSQL_CERTIFICATES_LOCATION"
0x10043b7db  call    cs:__imp_GetEnvironmentVariableW
0x10043b7e1  mov     ecx, ebx
0x10043b7e3  lea     rax, [rbp+14B0h+Buffer]
0x10043b7ea  nop     word ptr [rax+rax+00h]
0x10043b7f0  cmp     word ptr [rax], 0
0x10043b7f4  jz      short loc_10043B800
0x10043b7f6  add     rax, 2
0x10043b7fa  sub     rcx, 1
0x10043b7fe  jnz     short loc_10043B7F0
0x10043b800  mov     rax, rbx
0x10043b803  sub     rax, rcx
0x10043b806  test    rcx, rcx
0x10043b809  cmovz   rax, rsi
0x10043b80d  jz      loc_10043BCD9
0x10043b813  sub     rbx, rax
0x10043b816  lea     rcx, [rbp+14B0h+Buffer]
0x10043b81d  lea     rcx, [rcx+rax*2]
0x10043b821  jz      short loc_10043B851
0x10043b823  mov     eax, 7FFFFFFEh
0x10043b828  lea     r8, aMssqlControlle; "/mssql-controller-client/mssql-controll"...
0x10043b82f  sub     r8, rcx
0x10043b832  test    rax, rax
0x10043b835  jz      short loc_10043B851
0x10043b837  movzx   edx, word ptr [r8+rcx]
0x10043b83c  test    dx, dx
0x10043b83f  jz      short loc_10043B851
0x10043b841  mov     [rcx], dx
0x10043b844  add     rcx, 2
0x10043b848  dec     rax
0x10043b84b  sub     rbx, 1
0x10043b84f  jnz     short loc_10043B832
0x10043b851  lea     rax, [rcx-2]
0x10043b855  test    rbx, rbx
0x10043b858  cmovnz  rax, rcx
0x10043b85c  mov     [rax], si
0x10043b85f  jz      loc_10043BCD9
0x10043b865  mov     [rsp+15B0h+var_1550], 0FFFFFFFFFFFFFFFFh
0x10043b86e  mov     [rsp+15B0h+var_1560], rsi
0x10043b873  mov     [rsp+15B0h+var_156E], 0
0x10043b878  mov     [rsp+15B0h+var_156F], 0
0x10043b87d  mov     [rsp+15B0h+var_1570], 0
0x10043b882  mov     rdx, gs:58h
0x10043b88b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043b892  mov     ecx, [rax]
0x10043b894  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043b89b  mov     ebx, [rax]
0x10043b89d  add     rbx, [rdx+rcx*8]
0x10043b8a1  mov     rax, [rbx+100h]
0x10043b8a8  test    rax, rax
0x10043b8ab  jnz     short loc_10043B8BC
0x10043b8ad  xor     ecx, ecx
0x10043b8af  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043b8b5  mov     rax, [rbx+100h]
0x10043b8bc  mov     rbx, [rax+3E8h]
0x10043b8c3  mov     rax, cs:__imp_CertCloseStore
0x10043b8ca  mov     [rbp+14B0h+var_3B8], rax
0x10043b8d1  mov     [rbp+14B0h+var_3B0], rsi
0x10043b8d8  mov     [rbp+14B0h+var_3A8], esi
0x10043b8de  lea     rcx, ??_7?$FunctionCallBinderVirtual_2@XP6AHPEAXK@ZPEAXH@@6B@; const FunctionCallBinderVirtual_2<void,int (*)(void *,ulong),void *,int>::`vftable'
0x10043b8e5  mov     [rbp+14B0h+var_3C0], rcx
0x10043b8ec  lea     rax, [rbp+14B0h+var_3C0]
0x10043b8f3  mov     [rbp+14B0h+var_14C8], rax
0x10043b8f7  lea     rax, [rsp+15B0h+var_156E]
0x10043b8fc  mov     [rbp+14B0h+var_14C0], rax
0x10043b900  mov     rax, cs:__imp_CertCloseStore
0x10043b907  mov     [rbp+14B0h+var_488], rax
0x10043b90e  mov     [rbp+14B0h+var_480], rsi
0x10043b915  mov     [rbp+14B0h+var_478], esi
0x10043b91b  mov     [rbp+14B0h+var_490], rcx
0x10043b922  lea     rax, [rbp+14B0h+var_490]
0x10043b929  mov     [rbp+14B0h+var_14B8], rax
0x10043b92d  lea     rax, [rsp+15B0h+var_156F]
0x10043b932  mov     [rbp+14B0h+var_14B0], rax
0x10043b936  mov     rax, cs:__imp_CertFreeCertificateContext
0x10043b93d  mov     [rbp+14B0h+var_2E8], rax
0x10043b944  mov     [rbp+14B0h+var_2E0], rsi
0x10043b94b  lea     rax, ??_7?$FunctionCallBinderVirtual_1@XP6AHPEBU_CERT_CONTEXT@@@ZPEBU1@@@6B@; const FunctionCallBinderVirtual_1<void,int (*)(_CERT_CONTEXT const *),_CERT_CONTEXT const *>::`vftable'
0x10043b952  mov     [rbp+14B0h+var_2F0], rax
0x10043b959  lea     rax, [rbp+14B0h+var_2F0]
0x10043b960  mov     [rbp+14B0h+var_14A8], rax
0x10043b964  lea     rax, [rsp+15B0h+var_1570]
0x10043b969  mov     [rbp+14B0h+var_14A0], rax
0x10043b96d  mov     [rsp+15B0h+hTemplateFile], rsi; hTemplateFile
0x10043b972  mov     [rsp+15B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x10043b97a  mov     [rsp+15B0h+dwCreationDisposition], 3; dwCreationDisposition
0x10043b982  xor     r9d, r9d; lpSecurityAttributes
0x10043b985  mov     edx, 80000000h; dwDesiredAccess
0x10043b98a  lea     r8d, [r9+3]; dwShareMode
0x10043b98e  lea     rcx, [rbp+14B0h+Buffer]; lpFileName
0x10043b995  call    cs:__imp_CreateFileW
0x10043b99b  mov     rdi, rax
0x10043b99e  mov     [rsp+15B0h+var_1550], rax
0x10043b9a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10043b9a7  jnz     short loc_10043B9B6
0x10043b9a9  call    cs:__imp_GetLastError
0x10043b9af  mov     ecx, eax
0x10043b9b1  jmp     loc_10043BC49
0x10043b9b6  lea     rdx, [rsp+15B0h+FileSize]; lpFileSize
0x10043b9bb  mov     rcx, rdi; hFile
0x10043b9be  call    cs:__imp_GetFileSizeEx
0x10043b9c4  test    eax, eax
0x10043b9c6  jnz     short loc_10043B9D5
0x10043b9c8  call    cs:__imp_GetLastError
0x10043b9ce  mov     ecx, eax
0x10043b9d0  jmp     loc_10043BC49
0x10043b9d5  mov     rax, qword ptr [rsp+15B0h+FileSize]
0x10043b9da  test    eax, eax
0x10043b9dc  jz      loc_10043BC44
0x10043b9e2  cmp     dword ptr [rsp+15B0h+FileSize+4], 0
0x10043b9e7  jnz     loc_10043BC44
0x10043b9ed  lea     ecx, [rax+1]
0x10043b9f0  mov     byte ptr [rsp+15B0h+dwFlagsAndAttributes], 6
0x10043b9f5  mov     [rsp+15B0h+dwCreationDisposition], 1F5h
0x10043b9fd  lea     r9, aSqlNtdbmsKsour_2; "sql\\ntdbms\\ksource\\bdc.cpp"
0x10043ba04  mov     r8d, 1
0x10043ba0a  mov     rdx, rbx
0x10043ba0d  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10043ba13  mov     rbx, rax
0x10043ba16  test    rax, rax
0x10043ba19  jz      short loc_10043BA2A
0x10043ba1b  xor     ecx, ecx
0x10043ba1d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10043ba23  mov     [rsp+15B0h+var_1560], rbx
0x10043ba28  jmp     short loc_10043BA53
0x10043ba2a  mov     [rsp+15B0h+var_1560], rbx
0x10043ba2f  lea     rdx, aInitbdccontrol; "InitBdcControllerClientCert"
0x10043ba36  mov     ecx, 42F2h; unsigned int
0x10043ba3b  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10043ba40  xor     edx, edx
0x10043ba42  mov     ecx, 91h
0x10043ba47  mov     r8d, 8007000Eh
0x10043ba4d  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10043ba53  mov     qword ptr [rsp+15B0h+dwCreationDisposition], rsi; lpOverlapped
0x10043ba58  lea     r9, [rsp+15B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x10043ba5d  mov     r8d, dword ptr [rsp+15B0h+FileSize]; nNumberOfBytesToRead
0x10043ba62  mov     rdx, rbx; lpBuffer
0x10043ba65  mov     rcx, rdi; hFile
0x10043ba68  call    cs:__imp_ReadFile
0x10043ba6e  test    eax, eax
0x10043ba70  jnz     short loc_10043BA7F
0x10043ba72  call    cs:__imp_GetLastError
0x10043ba78  mov     ecx, eax
0x10043ba7a  jmp     loc_10043BC49
0x10043ba7f  mov     eax, dword ptr [rsp+15B0h+FileSize]
0x10043ba83  mov     [rsp+15B0h+pPFX.cbData], eax
0x10043ba87  mov     [rsp+15B0h+pPFX.pbData], rbx
0x10043ba8c  lea     rcx, [rsp+15B0h+pPFX]; pPFX
0x10043ba91  call    cs:__imp_PFXIsPFXBlob
0x10043ba97  test    eax, eax
0x10043ba99  jnz     short loc_10043BAA8
0x10043ba9b  call    cs:__imp_GetLastError
0x10043baa1  mov     ecx, eax
0x10043baa3  jmp     loc_10043BC49
0x10043baa8  xor     edx, edx; szPassword
0x10043baaa  lea     r8d, [rdx+21h]; dwFlags
0x10043baae  lea     rcx, [rsp+15B0h+pPFX]; pPFX
0x10043bab3  call    cs:__imp_PFXImportCertStore
0x10043bab9  test    rax, rax
0x10043babc  jnz     short loc_10043BB04
0x10043babe  call    cs:__imp_GetLastError
0x10043bac4  xor     r9d, r9d
0x10043bac7  xor     r8d, r8d
0x10043baca  lea     rdx, [rbp+14B0h+var_1490]
0x10043bace  mov     ecx, eax
0x10043bad0  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10043bad6  mov     r9, rax
0x10043bad9  mov     edx, 0Ah; int
0x10043bade  mov     ecx, 0C337h; unsigned int
0x10043bae3  lea     r8d, [rdx-9]; int
0x10043bae7  call    ?scierrlogwithstate@@YAXKHHZZ; scierrlogwithstate(ulong,int,int,...)
0x10043baec  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10043baf3  mov     rdx, [rax]
0x10043baf6  lea     rcx, aUnableToImport; "Unable to import certificate.\n"
0x10043bafd  call    rdx
0x10043baff  jmp     loc_10043BC71
0x10043bb04  mov     [rsp+15B0h+var_156E], 1
0x10043bb09  xor     edx, edx; pPrevCertContext
0x10043bb0b  mov     rcx, rax; hCertStore
0x10043bb0e  call    cs:__imp_CertEnumCertificatesInStore
0x10043bb14  mov     rbx, rax
0x10043bb17  test    rax, rax
0x10043bb1a  jnz     short loc_10043BB60
0x10043bb1c  call    cs:__imp_GetLastError
0x10043bb22  xor     r9d, r9d
0x10043bb25  xor     r8d, r8d
0x10043bb28  lea     rdx, [rbp+14B0h+var_1490]
0x10043bb2c  mov     ecx, eax
0x10043bb2e  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10043bb34  mov     r9, rax
0x10043bb37  lea     edx, [rbx+0Ah]; int
0x10043bb3a  mov     ecx, 0C337h; unsigned int
0x10043bb3f  lea     r8d, [rbx+1]; int
0x10043bb43  call    ?scierrlogwithstate@@YAXKHHZZ; scierrlogwithstate(ulong,int,int,...)
0x10043bb48  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10043bb4f  mov     rdx, [rax]
0x10043bb52  lea     rcx, aUnableToEnumer; "Unable to enumerate certificates in cer"...
0x10043bb59  call    rdx
0x10043bb5b  jmp     loc_10043BC71
0x10043bb60  mov     [rsp+15B0h+var_1570], 1
0x10043bb65  lea     rax, aMy; "MY"
0x10043bb6c  mov     qword ptr [rsp+15B0h+dwCreationDisposition], rax; pvPara
0x10043bb71  mov     r9d, 20000h; dwFlags
0x10043bb77  xor     r8d, r8d; hCryptProv
0x10043bb7a  xor     edx, edx; dwEncodingType
0x10043bb7c  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x10043bb7f  call    cs:__imp_CertOpenStore
0x10043bb85  test    rax, rax
0x10043bb88  jnz     short loc_10043BBD0
0x10043bb8a  call    cs:__imp_GetLastError
0x10043bb90  xor     r9d, r9d
0x10043bb93  xor     r8d, r8d
0x10043bb96  lea     rdx, [rbp+14B0h+var_1490]
0x10043bb9a  mov     ecx, eax
0x10043bb9c  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10043bba2  mov     r9, rax
0x10043bba5  mov     edx, 0Ah; int
0x10043bbaa  mov     ecx, 0C337h; unsigned int
0x10043bbaf  lea     r8d, [rdx-9]; int
0x10043bbb3  call    ?scierrlogwithstate@@YAXKHHZZ; scierrlogwithstate(ulong,int,int,...)
0x10043bbb8  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10043bbbf  mov     rdx, [rax]
0x10043bbc2  lea     rcx, aUnableToOpenSt; "Unable to open store.\n"
0x10043bbc9  call    rdx
0x10043bbcb  jmp     loc_10043BC71
0x10043bbd0  mov     [rsp+15B0h+var_156F], 1
  ... truncated ...
```
