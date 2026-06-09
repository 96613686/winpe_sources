# ExtensibilityCertCreator::LoadPfxFile(wchar_t const *,wchar_t const *,IMemObj *,ExtensibilityCertCreator::IssuerKeyInformation *,ulong)

- ea: `0x100480290`
- end: `0x1004809cd`
- name: `?LoadPfxFile@ExtensibilityCertCreator@@YAPEBU_CERT_CONTEXT@@PEB_W0PEAVIMemObj@@PEAUIssuerKeyInformation@1@K@Z`
- size: `1853`
- prototype: `const struct _CERT_CONTEXT *__fastcall(ExtensibilityCertCreator *__hidden this, const wchar_t *, const wchar_t *, struct IMemObj *, struct ExtensibilityCertCreator::IssuerKeyInformation *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10040a0b0`

## callees

- `0x100455f90`
- `0x100478330`
- `0x10047fd80`
- `0x100480290`
- `0x100486af0`
- `0x1004880d0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x100480540`
- `KERNEL32!SetFilePointer` at `0x100480540`
- `KERNEL32!GetCurrentThreadId` at `0x100480356`
- `KERNEL32!GetCurrentThreadId` at `0x100480447`
- `KERNEL32!GetCurrentThreadId` at `0x100480572`
- `KERNEL32!GetCurrentThreadId` at `0x100480647`
- `KERNEL32!GetCurrentThreadId` at `0x100480716`
- `KERNEL32!GetCurrentThreadId` at `0x1004807fa`
- `KERNEL32!GetCurrentThreadId` at `0x1004808f2`
- `KERNEL32!GetCurrentThreadId` at `0x100480356`
- `KERNEL32!GetCurrentThreadId` at `0x100480447`
- `KERNEL32!GetCurrentThreadId` at `0x100480572`
- `KERNEL32!GetCurrentThreadId` at `0x100480647`
- `KERNEL32!GetCurrentThreadId` at `0x100480716`
- `KERNEL32!GetCurrentThreadId` at `0x1004807fa`
- `KERNEL32!GetCurrentThreadId` at `0x1004808f2`
- `KERNEL32!ReadFile` at `0x10048041a`
- `KERNEL32!ReadFile` at `0x100480616`
- `KERNEL32!ReadFile` at `0x10048041a`
- `KERNEL32!ReadFile` at `0x100480616`
- `KERNEL32!CloseHandle` at `0x100480997`
- `KERNEL32!CloseHandle` at `0x100480997`
- `KERNEL32!GetLastError` at `0x100480333`
- `KERNEL32!GetLastError` at `0x100480428`
- `KERNEL32!GetLastError` at `0x10048054f`
- `KERNEL32!GetLastError` at `0x100480624`
- `KERNEL32!GetLastError` at `0x1004806f3`
- `KERNEL32!GetLastError` at `0x1004807d7`
- `KERNEL32!GetLastError` at `0x100480333`
- `KERNEL32!GetLastError` at `0x100480428`
- `KERNEL32!GetLastError` at `0x10048054f`
- `KERNEL32!GetLastError` at `0x100480624`
- `KERNEL32!GetLastError` at `0x1004806f3`
- `KERNEL32!GetLastError` at `0x1004807d7`
- `KERNEL32!CreateFileW` at `0x100480320`
- `KERNEL32!CreateFileW` at `0x100480320`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004803d6`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004804bd`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004805ef`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004806c4`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100480795`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10048087c`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100480989`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004803d6`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004804bd`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004805ef`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004806c4`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100480795`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10048087c`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100480989`
- `sqldk!??_V@YAXPEAX@Z` at `0x100480525`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004809a1`
- `sqldk!??_V@YAXPEAX@Z` at `0x100480525`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004809a1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100480511`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100480511`
- `CRYPT32!CertFreeCertificateContext` at `0x1004808cc`
- `CRYPT32!CertFreeCertificateContext` at `0x1004808cc`
- `CRYPT32!PFXImportCertStore` at `0x1004806e1`
- `CRYPT32!PFXImportCertStore` at `0x1004806e1`
- `CRYPT32!CertFindCertificateInStore` at `0x1004807c5`
- `CRYPT32!CertFindCertificateInStore` at `0x1004807c5`
- `CRYPT32!CertCloseStore` at `0x1004808af`
- `CRYPT32!CertCloseStore` at `0x1004808af`

## string_xrefs

- `0x1004804ff`: `Sql\Ntdbms\extensibility\common\src\ExtensibilityCertCreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const struct _CERT_CONTEXT *__fastcall ExtensibilityCertCreator::LoadPfxFile(
        const WCHAR *this,
        const wchar_t *a2,
        wchar_t *a3,
        struct IMemObj *a4,
        struct ExtensibilityCertCreator::IssuerKeyInformation *a5)
{
  const CERT_CONTEXT *CertificateInStore; // r15
  signed int KeyInfo; // edi
  void *v8; // rbx
  HANDLE FileW; // r12
  signed int LastError; // eax
  __int64 v11; // rsi
  signed int v12; // eax
  DWORD v13; // eax
  __int64 v14; // rsi
  unsigned __int64 v15; // rcx
  signed int v16; // eax
  DWORD v17; // eax
  __int64 v18; // rsi
  signed int v19; // eax
  DWORD v20; // eax
  __int64 v21; // rsi
  HCERTSTORE v22; // rsi
  signed int v23; // eax
  DWORD v24; // eax
  __int64 v25; // r14
  struct ExtensibilityCertCreator::IssuerKeyInformation *v26; // r9
  signed int v27; // eax
  DWORD v28; // eax
  __int64 v29; // r14
  DWORD v30; // eax
  __int64 v31; // rdi
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  void *v34; // [rsp+48h] [rbp-B8h]
  LPVOID lpBuffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _CERT_CONTEXT *v36; // [rsp+60h] [rbp-A0h]
  struct IMemObj *v37; // [rsp+68h] [rbp-98h]
  __int128 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h]
  signed int v40; // [rsp+88h] [rbp-78h]
  DWORD CurrentThreadId; // [rsp+8Ch] [rbp-74h]
  const char *v42; // [rsp+90h] [rbp-70h]
  int v43; // [rsp+98h] [rbp-68h]
  __int128 v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-50h]
  signed int v46; // [rsp+B8h] [rbp-48h]
  DWORD v47; // [rsp+BCh] [rbp-44h]
  const char *v48; // [rsp+C0h] [rbp-40h]
  int v49; // [rsp+C8h] [rbp-38h]
  __int128 v50; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v51; // [rsp+E0h] [rbp-20h]
  signed int v52; // [rsp+E8h] [rbp-18h]
  DWORD v53; // [rsp+ECh] [rbp-14h]
  const char *v54; // [rsp+F0h] [rbp-10h]
  int v55; // [rsp+F8h] [rbp-8h]
  __int128 v56; // [rsp+100h] [rbp+0h] BYREF
  __int64 v57; // [rsp+110h] [rbp+10h]
  signed int v58; // [rsp+118h] [rbp+18h]
  DWORD v59; // [rsp+11Ch] [rbp+1Ch]
  const char *v60; // [rsp+120h] [rbp+20h]
  int v61; // [rsp+128h] [rbp+28h]
  __int128 v62; // [rsp+130h] [rbp+30h] BYREF
  __int64 v63; // [rsp+140h] [rbp+40h]
  signed int v64; // [rsp+148h] [rbp+48h]
  DWORD v65; // [rsp+14Ch] [rbp+4Ch]
  const char *v66; // [rsp+150h] [rbp+50h]
  int v67; // [rsp+158h] [rbp+58h]
  __int128 v68; // [rsp+160h] [rbp+60h] BYREF
  __int64 v69; // [rsp+170h] [rbp+70h]
  signed int v70; // [rsp+178h] [rbp+78h]
  DWORD v71; // [rsp+17Ch] [rbp+7Ch]
  const char *v72; // [rsp+180h] [rbp+80h]
  int v73; // [rsp+188h] [rbp+88h]
  __int128 v74; // [rsp+190h] [rbp+90h] BYREF
  __int64 v75; // [rsp+1A0h] [rbp+A0h]
  int v76; // [rsp+1A8h] [rbp+A8h]
  DWORD v77; // [rsp+1ACh] [rbp+ACh]
  const char *v78; // [rsp+1B0h] [rbp+B0h]
  int v79; // [rsp+1B8h] [rbp+B8h]
  __int64 v80; // [rsp+1C0h] [rbp+C0h]
  _BYTE v81[216]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v82; // [rsp+2A8h] [rbp+1A8h]
  __int64 v83; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v84[216]; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v85; // [rsp+398h] [rbp+298h]
  __int64 v86; // [rsp+3A0h] [rbp+2A0h]
  _BYTE v87[216]; // [rsp+3B0h] [rbp+2B0h] BYREF
  int v88; // [rsp+488h] [rbp+388h]
  __int64 v89; // [rsp+490h] [rbp+390h]
  _BYTE v90[216]; // [rsp+4A0h] [rbp+3A0h] BYREF
  int v91; // [rsp+578h] [rbp+478h]
  __int64 v92; // [rsp+580h] [rbp+480h]
  _BYTE v93[216]; // [rsp+590h] [rbp+490h] BYREF
  int v94; // [rsp+668h] [rbp+568h]
  __int64 v95; // [rsp+670h] [rbp+570h]
  _BYTE v96[216]; // [rsp+680h] [rbp+580h] BYREF
  int v97; // [rsp+758h] [rbp+658h]
  __int64 v98; // [rsp+760h] [rbp+660h]
  _BYTE v99[216]; // [rsp+770h] [rbp+670h] BYREF
  int v100; // [rsp+848h] [rbp+748h]
  __int64 v101; // [rsp+850h] [rbp+750h]
  _BYTE Buffer[4096]; // [rsp+860h] [rbp+760h] BYREF

  v80 = -2;
  v37 = a4;
  v36 = (struct _CERT_CONTEXT *)a3;
  CertificateInStore = 0;
  KeyInfo = 0;
  v8 = 0;
  v34 = 0;
  *(_OWORD *)lpBuffer = 0;
  NumberOfBytesRead = 4096;
  FileW = CreateFileW(this, 0x80000000, 0, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    KeyInfo = LastError;
    if ( LastError > 0 )
      KeyInfo = (unsigned __int16)LastError | 0x80070000;
    if ( g_extensibilityErrorRingBuffer )
    {
      v38 = 0;
      v39 = 0;
      v40 = KeyInfo;
      CurrentThreadId = GetCurrentThreadId();
      v42 = "ExtensibilityCertCreator::LoadPfxFile";
      v43 = 841;
      v11 = g_extensibilityErrorRingBuffer;
      v82 = 0;
      v83 = 0;
      if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
        StackFrames<24>::CaptureCurrent(v81, 1);
      if ( (dword_1005113AC & 0x10) != 0 )
        ExtensibilityErrorRecord::FireMatchingEvent(&v38, v81);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v11, &v38, v81);
    }
    if ( KeyInfo < 0 )
      goto LABEL_77;
  }
  do
  {
    if ( !ReadFile(FileW, Buffer, 0x1000u, &NumberOfBytesRead, 0) )
    {
      v12 = GetLastError();
      KeyInfo = v12;
      if ( v12 > 0 )
        KeyInfo = (unsigned __int16)v12 | 0x80070000;
      if ( g_extensibilityErrorRingBuffer )
      {
        v13 = GetCurrentThreadId();
        v44 = 0;
        v45 = 0;
        v46 = KeyInfo;
        v47 = v13;
        v48 = "ExtensibilityCertCreator::LoadPfxFile";
        v49 = 859;
        v14 = g_extensibilityErrorRingBuffer;
        v85 = 0;
        v86 = 0;
        if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
          StackFrames<24>::CaptureCurrent(v84, 1);
        if ( (dword_1005113AC & 0x10) != 0 )
          ExtensibilityErrorRecord::FireMatchingEvent(&v44, v84);
        SOS_RingBuffer::StoreRecordInternalWithoutEvent(v14, &v44, v84);
      }
    }
    v15 = NumberOfBytesRead + LODWORD(lpBuffer[0]);
    LODWORD(lpBuffer[0]) += NumberOfBytesRead;
  }
  while ( NumberOfBytesRead == 4096 );
  CertificateInStore = 0;
  if ( KeyInfo >= 0 )
  {
    v8 = operator new[](
           v15,
           (struct IMemObj *)v36,
           1,
           "Sql\\Ntdbms\\extensibility\\common\\src\\ExtensibilityCertCreator.cpp",
           867,
           6u);
    if ( v8 )
    {
      operator delete[](0);
      v34 = v8;
      lpBuffer[1] = v8;
      if ( SetFilePointer(FileW, 0, 0, 0) != -1 )
        goto LABEL_42;
      v16 = GetLastError();
      KeyInfo = v16;
      if ( v16 > 0 )
        KeyInfo = (unsigned __int16)v16 | 0x80070000;
      if ( g_extensibilityErrorRingBuffer )
      {
        v17 = GetCurrentThreadId();
        v50 = 0;
        v51 = 0;
        v52 = KeyInfo;
        v53 = v17;
        v54 = "ExtensibilityCertCreator::LoadPfxFile";
        v55 = 889;
        v18 = g_extensibilityErrorRingBuffer;
        v88 = 0;
        v89 = 0;
        if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
          StackFrames<24>::CaptureCurrent(v87, 1);
        if ( (dword_1005113AC & 0x10) != 0 )
          ExtensibilityErrorRecord::FireMatchingEvent(&v50, v87);
        SOS_RingBuffer::StoreRecordInternalWithoutEvent(v18, &v50, v87);
      }
      if ( KeyInfo >= 0 )
      {
LABEL_42:
        if ( ReadFile(FileW, lpBuffer[1], (DWORD)lpBuffer[0], &NumberOfBytesRead, 0) )
          goto LABEL_43;
        v19 = GetLastError();
        KeyInfo = v19;
        if ( v19 > 0 )
          KeyInfo = (unsigned __int16)v19 | 0x80070000;
        if ( g_extensibilityErrorRingBuffer )
        {
          v20 = GetCurrentThreadId();
          v56 = 0;
          v57 = 0;
          v58 = KeyInfo;
          v59 = v20;
          v60 = "ExtensibilityCertCreator::LoadPfxFile";
          v61 = 905;
          v21 = g_extensibilityErrorRingBuffer;
          v91 = 0;
          v92 = 0;
          if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
            StackFrames<24>::CaptureCurrent(v90, 1);
          if ( (dword_1005113AC & 0x10) != 0 )
            ExtensibilityErrorRecord::FireMatchingEvent(&v56, v90);
          SOS_RingBuffer::StoreRecordInternalWithoutEvent(v21, &v56, v90);
        }
        if ( KeyInfo >= 0 )
        {
LABEL_43:
          v22 = PFXImportCertStore((CRYPT_DATA_BLOB *)lpBuffer, a2, (unsigned int)a5 | 0x11);
          if ( !v22 )
          {
            v23 = GetLastError();
            KeyInfo = v23;
            if ( v23 > 0 )
              KeyInfo = (unsigned __int16)v23 | 0x80070000;
            if ( g_extensibilityErrorRingBuffer )
            {
              v24 = GetCurrentThreadId();
              v62 = 0;
              v63 = 0;
              v64 = KeyInfo;
              v65 = v24;
              v66 = "ExtensibilityCertCreator::LoadPfxFile";
              v67 = 920;
              v25 = g_extensibilityErrorRingBuffer;
              v94 = 0;
              v95 = 0;
              if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
                StackFrames<24>::CaptureCurrent(v93, 1);
              if ( (dword_1005113AC & 0x10) != 0 )
                ExtensibilityErrorRecord::FireMatchingEvent(&v62, v93);
              SOS_RingBuffer::StoreRecordInternalWithoutEvent(v25, &v62, v93);
            }
            if ( KeyInfo < 0 )
              goto LABEL_68;
          }
          CertificateInStore = CertFindCertificateInStore(v22, 0x10001u, 0, 0, 0, 0);
          if ( CertificateInStore )
            goto LABEL_63;
          v27 = GetLastError();
          KeyInfo = v27;
          if ( v27 > 0 )
            KeyInfo = (unsigned __int16)v27 | 0x80070000;
          if ( g_extensibilityErrorRingBuffer )
          {
            v28 = GetCurrentThreadId();
            v68 = 0;
            v69 = 0;
            v70 = KeyInfo;
            v71 = v28;
            v72 = "ExtensibilityCertCreator::LoadPfxFile";
            v73 = 939;
            v29 = g_extensibilityErrorRingBuffer;
            v97 = 0;
            v98 = 0;
            if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
              StackFrames<24>::CaptureCurrent(v96, 1);
            if ( (dword_1005113AC & 0x10) != 0 )
              ExtensibilityErrorRecord::FireMatchingEvent(&v68, v96);
            SOS_RingBuffer::StoreRecordInternalWithoutEvent(v29, &v68, v96);
          }
          CertificateInStore = 0;
          if ( KeyInfo >= 0 )
          {
LABEL_63:
            if ( v37 )
              KeyInfo = ExtensibilityCertCreator::GetKeyInfo(CertificateInStore, v36, v37, v26);
          }
          if ( v22 )
            CertCloseStore(v22, 0);
          if ( KeyInfo < 0 )
          {
LABEL_68:
            if ( CertificateInStore )
            {
              _mm_lfence();
              CertFreeCertificateContext(CertificateInStore);
              CertificateInStore = 0;
              v8 = v34;
            }
          }
        }
      }
    }
    else
    {
      v34 = 0;
      if ( g_extensibilityErrorRingBuffer )
      {
        v30 = GetCurrentThreadId();
        v74 = 0;
        v75 = 0;
        v76 = -2147024882;
        v77 = v30;
        v78 = "ExtensibilityCertCreator::LoadPfxFile";
        v79 = 871;
        v31 = g_extensibilityErrorRingBuffer;
        v100 = 0;
        v101 = 0;
        if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
          StackFrames<24>::CaptureCurrent(v99, 1);
        if ( (dword_1005113AC & 0x10) != 0 )
          ExtensibilityErrorRecord::FireMatchingEvent(&v74, v99);
        SOS_RingBuffer::StoreRecordInternalWithoutEvent(v31, &v74, v99);
      }
    }
  }
  if ( FileW )
LABEL_77:
    CloseHandle(FileW);
  operator delete[](v8);
  return CertificateInStore;
}

```

## disassembly

```asm
0x100480290  push    rbp
0x100480292  push    rbx
0x100480293  push    rsi
0x100480294  push    rdi
0x100480295  push    r12
0x100480297  push    r13
0x100480299  push    r14
0x10048029b  push    r15
0x10048029d  lea     rbp, [rsp-1778h]
0x1004802a5  mov     eax, 1878h
0x1004802aa  call    _alloca_probe
0x1004802af  sub     rsp, rax
0x1004802b2  mov     [rbp+17B0h+var_16F0], 0FFFFFFFFFFFFFFFEh
0x1004802bd  mov     rax, cs:__security_cookie
0x1004802c4  xor     rax, rsp
0x1004802c7  mov     [rbp+17B0h+var_50], rax
0x1004802ce  mov     [rsp+18B0h+var_1848], r9
0x1004802d3  mov     [rsp+18B0h+var_1850], r8
0x1004802d8  mov     r13, rdx
0x1004802db  mov     r14d, dword ptr [rbp+17B0h+arg_20]
0x1004802e2  xor     esi, esi
0x1004802e4  mov     r15d, esi
0x1004802e7  mov     edi, esi
0x1004802e9  mov     ebx, esi
0x1004802eb  mov     [rsp+18B0h+var_1868], rbx
0x1004802f0  xorps   xmm0, xmm0
0x1004802f3  movups  xmmword ptr [rsp+18B0h+lpBuffer], xmm0
0x1004802f8  mov     [rsp+18B0h+NumberOfBytesRead], 1000h
0x100480300  mov     [rsp+18B0h+hTemplateFile], rsi; hTemplateFile
0x100480305  mov     [rsp+18B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x10048030d  mov     [rsp+18B0h+dwCreationDisposition], 3; dwCreationDisposition
0x100480315  xor     r9d, r9d; lpSecurityAttributes
0x100480318  xor     r8d, r8d; dwShareMode
0x10048031b  mov     edx, 80000000h; dwDesiredAccess
0x100480320  call    cs:__imp_CreateFileW
0x100480326  mov     r12, rax
0x100480329  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10048032d  jnz     loc_1004803E6
0x100480333  call    cs:__imp_GetLastError
0x100480339  mov     edi, eax
0x10048033b  test    eax, eax
0x10048033d  jle     short loc_100480348
0x10048033f  movzx   edi, ax
0x100480342  or      edi, 80070000h
0x100480348  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480350  jz      loc_1004803DE
0x100480356  call    cs:__imp_GetCurrentThreadId
0x10048035c  xorps   xmm0, xmm0
0x10048035f  xor     ecx, ecx
0x100480361  movups  [rsp+18B0h+var_1840], xmm0
0x100480366  mov     [rbp+17B0h+var_1830], rcx
0x10048036a  mov     [rbp+17B0h+var_1828], edi
0x10048036d  mov     [rbp+17B0h+var_1824], eax
0x100480370  lea     rax, aExtensibilityc_2; "ExtensibilityCertCreator::LoadPfxFile"
0x100480377  mov     [rbp+17B0h+var_1820], rax
0x10048037b  mov     [rbp+17B0h+var_1818], 349h
0x100480382  mov     rsi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480389  xor     eax, eax
0x10048038b  mov     [rbp+17B0h+var_1608], eax
0x100480391  mov     [rbp+17B0h+var_1600], rax
0x100480398  cmp     [rsi+40h], rax
0x10048039c  jz      short loc_1004803AD
0x10048039e  lea     edx, [rcx+1]
0x1004803a1  lea     rcx, [rbp+17B0h+var_16E0]
0x1004803a8  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004803ad  test    byte ptr cs:dword_1005113AC, 10h
0x1004803b4  jz      short loc_1004803C7
0x1004803b6  lea     rdx, [rbp+17B0h+var_16E0]
0x1004803bd  lea     rcx, [rsp+18B0h+var_1840]
0x1004803c2  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x1004803c7  lea     r8, [rbp+17B0h+var_16E0]
0x1004803ce  lea     rdx, [rsp+18B0h+var_1840]
0x1004803d3  mov     rcx, rsi
0x1004803d6  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004803dc  xor     esi, esi
0x1004803de  test    edi, edi
0x1004803e0  js      loc_100480994
0x1004803e6  cmp     [rsp+18B0h+NumberOfBytesRead], 1000h
0x1004803ee  jnz     loc_1004804EE
0x1004803f4  lea     r15, aExtensibilityc_2; "ExtensibilityCertCreator::LoadPfxFile"
0x1004803fb  nop     dword ptr [rax+rax+00h]
0x100480400  mov     qword ptr [rsp+18B0h+dwCreationDisposition], rsi; lpOverlapped
0x100480405  lea     r9, [rsp+18B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x10048040a  mov     r8d, 1000h; nNumberOfBytesToRead
0x100480410  lea     rdx, [rbp+17B0h+Buffer]; lpBuffer
0x100480417  mov     rcx, r12; hFile
0x10048041a  call    cs:__imp_ReadFile
0x100480420  test    eax, eax
0x100480422  jnz     loc_1004804C5
0x100480428  call    cs:__imp_GetLastError
0x10048042e  mov     edi, eax
0x100480430  test    eax, eax
0x100480432  jle     short loc_10048043D
0x100480434  movzx   edi, ax
0x100480437  or      edi, 80070000h
0x10048043d  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480445  jz      short loc_1004804C5
0x100480447  call    cs:__imp_GetCurrentThreadId
0x10048044d  xorps   xmm0, xmm0
0x100480450  xor     ecx, ecx
0x100480452  movups  [rbp+17B0h+var_1810], xmm0
0x100480456  mov     [rbp+17B0h+var_1800], rcx
0x10048045a  mov     [rbp+17B0h+var_17F8], edi
0x10048045d  mov     [rbp+17B0h+var_17F4], eax
0x100480460  mov     [rbp+17B0h+var_17F0], r15
0x100480464  mov     [rbp+17B0h+var_17E8], 35Bh
0x10048046b  mov     rsi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480472  xor     eax, eax
0x100480474  mov     [rbp+17B0h+var_1518], eax
0x10048047a  mov     [rbp+17B0h+var_1510], rax
0x100480481  cmp     [rsi+40h], rax
0x100480485  jz      short loc_100480496
0x100480487  lea     edx, [rcx+1]
0x10048048a  lea     rcx, [rbp+17B0h+var_15F0]
0x100480491  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x100480496  test    byte ptr cs:dword_1005113AC, 10h
0x10048049d  jz      short loc_1004804AF
0x10048049f  lea     rdx, [rbp+17B0h+var_15F0]
0x1004804a6  lea     rcx, [rbp+17B0h+var_1810]
0x1004804aa  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x1004804af  lea     r8, [rbp+17B0h+var_15F0]
0x1004804b6  lea     rdx, [rbp+17B0h+var_1810]
0x1004804ba  mov     rcx, rsi
0x1004804bd  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004804c3  xor     esi, esi
0x1004804c5  mov     edx, edi
0x1004804c7  mov     ecx, dword ptr [rsp+18B0h+lpBuffer]
0x1004804cb  add     ecx, [rsp+18B0h+NumberOfBytesRead]
0x1004804cf  mov     dword ptr [rsp+18B0h+lpBuffer], ecx
0x1004804d3  cmp     [rsp+18B0h+NumberOfBytesRead], 1000h
0x1004804db  jz      loc_100480400
0x1004804e1  test    edx, edx
0x1004804e3  mov     r15, rsi
0x1004804e6  js      loc_10048098F
0x1004804ec  jmp     short loc_1004804F2
0x1004804ee  mov     ecx, dword ptr [rsp+18B0h+lpBuffer]
0x1004804f2  mov     byte ptr [rsp+18B0h+dwFlagsAndAttributes], 6
0x1004804f7  mov     [rsp+18B0h+dwCreationDisposition], 363h
0x1004804ff  lea     r9, aSqlNtdbmsExten_6; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x100480506  mov     r8d, 1
0x10048050c  mov     rdx, [rsp+18B0h+var_1850]
0x100480511  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100480517  mov     rbx, rax
0x10048051a  test    rax, rax
0x10048051d  jz      loc_1004808DF
0x100480523  xor     ecx, ecx
0x100480525  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10048052b  mov     [rsp+18B0h+var_1868], rbx
0x100480530  mov     [rsp+18B0h+lpBuffer+8], rbx
0x100480535  xor     r9d, r9d; dwMoveMethod
0x100480538  xor     r8d, r8d; lpDistanceToMoveHigh
0x10048053b  xor     edx, edx; lDistanceToMove
0x10048053d  mov     rcx, r12; hFile
0x100480540  call    cs:__imp_SetFilePointer
0x100480546  cmp     eax, 0FFFFFFFFh
0x100480549  jnz     loc_1004805FD
0x10048054f  call    cs:__imp_GetLastError
0x100480555  mov     edi, eax
0x100480557  test    eax, eax
0x100480559  jle     short loc_100480564
0x10048055b  movzx   edi, ax
0x10048055e  or      edi, 80070000h
0x100480564  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10048056c  jz      loc_1004805F5
0x100480572  call    cs:__imp_GetCurrentThreadId
0x100480578  xorps   xmm0, xmm0
0x10048057b  xor     ecx, ecx
0x10048057d  movups  [rbp+17B0h+var_17E0], xmm0
0x100480581  mov     [rbp+17B0h+var_17D0], rcx
0x100480585  mov     [rbp+17B0h+var_17C8], edi
0x100480588  mov     [rbp+17B0h+var_17C4], eax
0x10048058b  lea     rax, aExtensibilityc_2; "ExtensibilityCertCreator::LoadPfxFile"
0x100480592  mov     [rbp+17B0h+var_17C0], rax
0x100480596  mov     [rbp+17B0h+var_17B8], 379h
0x10048059d  mov     rsi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x1004805a4  xor     eax, eax
0x1004805a6  mov     [rbp+17B0h+var_1428], eax
0x1004805ac  mov     [rbp+17B0h+var_1420], rax
0x1004805b3  cmp     [rsi+40h], rax
0x1004805b7  jz      short loc_1004805C8
0x1004805b9  lea     edx, [rcx+1]
0x1004805bc  lea     rcx, [rbp+17B0h+var_1500]
0x1004805c3  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004805c8  test    byte ptr cs:dword_1005113AC, 10h
0x1004805cf  jz      short loc_1004805E1
0x1004805d1  lea     rdx, [rbp+17B0h+var_1500]
0x1004805d8  lea     rcx, [rbp+17B0h+var_17E0]
0x1004805dc  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x1004805e1  lea     r8, [rbp+17B0h+var_1500]
0x1004805e8  lea     rdx, [rbp+17B0h+var_17E0]
0x1004805ec  mov     rcx, rsi
0x1004805ef  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004805f5  test    edi, edi
0x1004805f7  js      loc_10048098F
0x1004805fd  xor     eax, eax
0x1004805ff  mov     qword ptr [rsp+18B0h+dwCreationDisposition], rax; lpOverlapped
0x100480604  lea     r9, [rsp+18B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x100480609  mov     r8d, dword ptr [rsp+18B0h+lpBuffer]; nNumberOfBytesToRead
0x10048060e  mov     rdx, [rsp+18B0h+lpBuffer+8]; lpBuffer
0x100480613  mov     rcx, r12; hFile
0x100480616  call    cs:__imp_ReadFile
0x10048061c  test    eax, eax
0x10048061e  jnz     loc_1004806D2
0x100480624  call    cs:__imp_GetLastError
0x10048062a  mov     edi, eax
0x10048062c  test    eax, eax
0x10048062e  jle     short loc_100480639
0x100480630  movzx   edi, ax
0x100480633  or      edi, 80070000h
0x100480639  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480641  jz      loc_1004806CA
0x100480647  call    cs:__imp_GetCurrentThreadId
0x10048064d  xorps   xmm0, xmm0
0x100480650  xor     ecx, ecx
0x100480652  movups  [rbp+17B0h+var_17B0], xmm0
0x100480656  mov     [rbp+17B0h+var_17A0], rcx
0x10048065a  mov     [rbp+17B0h+var_1798], edi
0x10048065d  mov     [rbp+17B0h+var_1794], eax
0x100480660  lea     rax, aExtensibilityc_2; "ExtensibilityCertCreator::LoadPfxFile"
0x100480667  mov     [rbp+17B0h+var_1790], rax
0x10048066b  mov     [rbp+17B0h+var_1788], 389h
0x100480672  mov     rsi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480679  xor     eax, eax
0x10048067b  mov     [rbp+17B0h+var_1338], eax
0x100480681  mov     [rbp+17B0h+var_1330], rax
0x100480688  cmp     [rsi+40h], rax
0x10048068c  jz      short loc_10048069D
0x10048068e  lea     edx, [rcx+1]
0x100480691  lea     rcx, [rbp+17B0h+var_1410]
0x100480698  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x10048069d  test    byte ptr cs:dword_1005113AC, 10h
0x1004806a4  jz      short loc_1004806B6
0x1004806a6  lea     rdx, [rbp+17B0h+var_1410]
0x1004806ad  lea     rcx, [rbp+17B0h+var_17B0]
0x1004806b1  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x1004806b6  lea     r8, [rbp+17B0h+var_1410]
0x1004806bd  lea     rdx, [rbp+17B0h+var_17B0]
0x1004806c1  mov     rcx, rsi
0x1004806c4  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004806ca  test    edi, edi
0x1004806cc  js      loc_10048098F
0x1004806d2  or      r14d, 11h
0x1004806d6  mov     r8d, r14d; dwFlags
0x1004806d9  mov     rdx, r13; szPassword
0x1004806dc  lea     rcx, [rsp+18B0h+lpBuffer]; pPFX
0x1004806e1  call    cs:__imp_PFXImportCertStore
0x1004806e7  mov     rsi, rax
0x1004806ea  test    rax, rax
0x1004806ed  jnz     loc_1004807AA
0x1004806f3  call    cs:__imp_GetLastError
0x1004806f9  mov     edi, eax
0x1004806fb  test    eax, eax
0x1004806fd  jle     short loc_100480708
0x1004806ff  movzx   edi, ax
0x100480702  or      edi, 80070000h
0x100480708  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480710  jz      loc_10048079D
0x100480716  call    cs:__imp_GetCurrentThreadId
0x10048071c  xorps   xmm0, xmm0
0x10048071f  xor     ecx, ecx
0x100480721  movups  [rbp+17B0h+var_1780], xmm0
0x100480725  mov     [rbp+17B0h+var_1770], rcx
0x100480729  mov     [rbp+17B0h+var_1768], edi
0x10048072c  mov     [rbp+17B0h+var_1764], eax
0x10048072f  lea     rax, aExtensibilityc_2; "ExtensibilityCertCreator::LoadPfxFile"
0x100480736  mov     [rbp+17B0h+var_1760], rax
0x10048073a  mov     [rbp+17B0h+var_1758], 398h
0x100480741  mov     r14, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100480748  xor     r13d, r13d
0x10048074b  mov     [rbp+17B0h+var_1248], r13d
0x100480752  mov     [rbp+17B0h+var_1240], r13
0x100480759  cmp     [r14+40h], rcx
0x10048075d  jz      short loc_10048076E
0x10048075f  lea     edx, [rcx+1]
0x100480762  lea     rcx, [rbp+17B0h+var_1320]
0x100480769  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x10048076e  test    byte ptr cs:dword_1005113AC, 10h
0x100480775  jz      short loc_100480787
0x100480777  lea     rdx, [rbp+17B0h+var_1320]
0x10048077e  lea     rcx, [rbp+17B0h+var_1780]
0x100480782  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x100480787  lea     r8, [rbp+17B0h+var_1320]
0x10048078e  lea     rdx, [rbp+17B0h+var_1780]
0x100480792  mov     rcx, r14
0x100480795  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x10048079b  jmp     short loc_1004807A0
0x10048079d  xor     r13d, r13d
0x1004807a0  test    edi, edi
0x1004807a2  js      loc_1004808BD
0x1004807a8  jmp     short loc_1004807AD
0x1004807aa  xor     r13d, r13d
0x1004807ad  mov     qword ptr [rsp+18B0h+dwFlagsAndAttributes], r13; pPrevCertContext
0x1004807b2  mov     qword ptr [rsp+18B0h+dwCreationDisposition], r13; pvFindPara
0x1004807b7  xor     r9d, r9d; dwFindType
0x1004807ba  xor     r8d, r8d; dwFindFlags
0x1004807bd  mov     edx, 10001h; dwCertEncodingType
0x1004807c2  mov     rcx, rsi; hCertStore
0x1004807c5  call    cs:__imp_CertFindCertificateInStore
0x1004807cb  mov     r15, rax
0x1004807ce  test    rax, rax
  ... truncated ...
```
