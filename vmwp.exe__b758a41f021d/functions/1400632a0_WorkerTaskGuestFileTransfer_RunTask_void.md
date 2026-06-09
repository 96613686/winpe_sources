# WorkerTaskGuestFileTransfer::RunTask(void)

- ea: `0x1400632a0`
- end: `0x140063f16`
- name: `?RunTask@WorkerTaskGuestFileTransfer@@UEAAXXZ`
- size: `3190`
- prototype: `void __fastcall(WorkerTaskGuestFileTransfer *__hidden this)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x14001ec28`
- `0x140031480`
- `0x14003b720`
- `0x140052ea4`
- `0x14005c320`
- `0x1400632a0`
- `0x140063f1c`
- `0x140064048`
- `0x140064094`
- `0x140064408`
- `0x140067a88`
- `0x140078628`
- `0x14009d7bc`
- `0x1400a61c8`
- `0x1400a6470`
- `0x1400ba144`
- `0x1400bc420`
- `0x1400cf1dc`
- `0x1400dc8cc`
- `0x14011ea40`
- `0x14011ea70`
- `0x14011f6fc`
- `0x14011fafc`
- `0x140147f2c`
- `0x14017a580`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400634dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400634dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063997`
- `vmprox!GetVmErrInfo` at `0x140063ea6`
- `vmprox!GetVmErrInfo` at `0x140063ea6`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400634cd`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400634cd`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140063987`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140063987`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x140063596`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x140063596`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140063584`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140063584`

## string_xrefs

- `0x14006334b`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x14006338d`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400633eb`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x140063500`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400635b4`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x140063704`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400638c0`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x140063bc9`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x140063c7f`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400639c2`: `onecore\vm\common/vml/VmFiles.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall WorkerTaskGuestFileTransfer::RunTask(WorkerTaskGuestFileTransfer *this)
{
  int v1; // r12d
  int VirtualDevice; // eax
  int v3; // eax
  struct _SECURITY_ATTRIBUTES *v4; // r9
  int v5; // eax
  unsigned int i; // r14d
  void **v7; // rsi
  _BYTE *v8; // rdx
  _BYTE *v9; // r15
  unsigned __int64 v10; // rcx
  char *v11; // rax
  size_t v12; // rbx
  __int64 v13; // r14
  __int64 v14; // r13
  __int64 v15; // rbx
  __int64 v16; // rsi
  signed int LastError; // eax
  union _LARGE_INTEGER v18; // rax
  GuestFileCopy *v19; // r15
  GuestFileCopy *v20; // rax
  __int64 *v21; // rsi
  void *v22; // rbx
  const WCHAR *v23; // r14
  const WCHAR *v24; // rcx
  const WCHAR *FileNameW; // r12
  _QWORD *v26; // rsi
  _QWORD *v27; // r8
  int v28; // eax
  unsigned int v29; // r12d
  unsigned int v30; // ebx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // r9
  __int64 v34; // r8
  int v35; // eax
  int v36; // eax
  unsigned int v37; // ebx
  __int64 v38; // rcx
  __int64 v39; // rcx
  void *v40; // rdx
  DWORD v41; // eax
  __int64 v42; // rcx
  unsigned __int64 v43; // rax
  void *v44; // rdx
  const char *v45; // r9
  WorkerAsyncTaskBase *v46; // r14
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 VmErrInfo; // rax
  void (*v51)(void *); // [rsp+20h] [rbp-1A8h]
  int v52; // [rsp+20h] [rbp-1A8h]
  unsigned int v53; // [rsp+20h] [rbp-1A8h]
  DWORD LowPart; // [rsp+20h] [rbp-1A8h]
  int v55; // [rsp+20h] [rbp-1A8h]
  int v56; // [rsp+20h] [rbp-1A8h]
  int v57; // [rsp+20h] [rbp-1A8h]
  const unsigned __int16 *v58; // [rsp+28h] [rbp-1A0h]
  _DWORD v59[3]; // [rsp+54h] [rbp-174h] BYREF
  __int64 v60; // [rsp+60h] [rbp-168h] BYREF
  __int64 v61; // [rsp+68h] [rbp-160h] BYREF
  int v62[2]; // [rsp+70h] [rbp-158h] BYREF
  __int64 v63; // [rsp+78h] [rbp-150h] BYREF
  __int64 v64; // [rsp+80h] [rbp-148h] BYREF
  __int64 *v65; // [rsp+88h] [rbp-140h]
  int v66; // [rsp+90h] [rbp-138h]
  __int64 VmName; // [rsp+98h] [rbp-130h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-128h] BYREF
  void *v69; // [rsp+A8h] [rbp-120h] BYREF
  void *v70; // [rsp+B0h] [rbp-118h] BYREF
  unsigned __int64 v71; // [rsp+B8h] [rbp-110h]
  GuestFileCopy *v72; // [rsp+C0h] [rbp-108h]
  __int64 v73; // [rsp+C8h] [rbp-100h] BYREF
  _QWORD *v74; // [rsp+D0h] [rbp-F8h]
  struct _OVERLAPPED Overlapped; // [rsp+D8h] [rbp-F0h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+F8h] [rbp-D0h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+100h] [rbp-C8h] BYREF
  DWORD v78; // [rsp+108h] [rbp-C0h] BYREF
  __int64 v79; // [rsp+110h] [rbp-B8h] BYREF
  struct IUnknown *v80; // [rsp+118h] [rbp-B0h] BYREF
  void *v81[6]; // [rsp+120h] [rbp-A8h] BYREF
  unsigned __int16 v82[16]; // [rsp+150h] [rbp-78h] BYREF
  unsigned __int16 v83[16]; // [rsp+170h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  try
  {
    *(_QWORD *)&v59[1] = this;
    v68 = (__int64)this;
    VmName = (__int64)this;
    v1 = 0;
    v79 = 0;
    v80 = 0;
    v73 = -1;
    v65 = (__int64 *)((char *)this + 16);
    v74 = (_QWORD *)((char *)this + 16);
    VirtualDevice = VirtualMotherboard::FindVirtualDevice(
                      *(VirtualMotherboard **)(*((_QWORD *)this + 2) + 984LL),
                      &g_ICVDevClassIdGuestInterface,
                      &IID_IUnknown,
                      &v80);
    if ( VirtualDevice < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)(unsigned int)VirtualDevice,
        (int)v51);
    v3 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v80->lpVtbl->QueryInterface)(
           v80,
           &IID_IICGuestInterface,
           &v79);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)(unsigned int)v3,
        (int)v51);
    v70 = 0;
    Vml::VmEvent::VmEvent((Vml::VmEvent *)&v70, 0, 0, v4, (const unsigned __int16 *)v51, v58);
    v78 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v79 + 32LL))(v79, &v78);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)(unsigned int)v5,
        v52);
    `eh vector constructor iterator'(
      v81,
      0x18u,
      2u,
      std::vector<std::atomic<bool>>::vector<std::atomic<bool>>,
      std::pair<std::vector<enum gsl::byte>,unsigned __int64>::~pair<std::vector<enum gsl::byte>,unsigned __int64>);
    for ( i = 0; i < 2; ++i )
    {
      v7 = &v81[3 * i];
      v8 = *v7;
      v9 = v7[1];
      v10 = v9 - (_BYTE *)*v7;
      if ( v78 >= v10 )
      {
        if ( v78 <= v10 )
          continue;
        if ( v78 > (unsigned __int64)((_BYTE *)v7[2] - v8) )
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v81[3 * i], v78);
          continue;
        }
        v12 = v78 - v10;
        memset_0(v7[1], 0, v12);
        v11 = &v9[v12];
      }
      else
      {
        v11 = &v8[v78];
      }
      v7[1] = v11;
    }
    v13 = 0;
    v61 = 0;
    v14 = *(_QWORD *)&v59[1] + 400LL;
    v15 = *(_QWORD *)(*(_QWORD *)&v59[1] + 400LL);
    v16 = *(_QWORD *)(*(_QWORD *)&v59[1] + 408LL);
    while ( v15 != v16 )
    {
      FileSize.QuadPart = 0;
      if ( !GetFileSizeEx(*(HANDLE *)v15, &FileSize) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
          (const char *)(unsigned int)LastError,
          v53);
      }
      v18 = FileSize;
      *(union _LARGE_INTEGER *)(v15 + 80) = FileSize;
      v13 += v18.QuadPart;
      v61 = v13;
      v15 += 88;
    }
    v60 = 0;
    v66 = 0;
    v19 = *(GuestFileCopy **)v14;
    v20 = *(GuestFileCopy **)(v14 + 8);
    v72 = v20;
    v21 = v65;
LABEL_26:
    if ( v19 == v20 )
    {
      `eh vector destructor iterator'(
        v81,
        0x18u,
        2u,
        std::pair<std::vector<enum gsl::byte>,unsigned __int64>::~pair<std::vector<enum gsl::byte>,unsigned __int64>);
      Vml::VmWaitable::~VmWaitable((Vml::VmWaitable *)&v70);
      Vml::VmFile::Reset((Vml::VmFile *)&v73, v44);
      Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(&v80);
      v46 = *(WorkerAsyncTaskBase **)&v59[1];
      goto LABEL_89;
    }
    v22 = *(void **)v19;
    *(_QWORD *)v19 = -1;
    v69 = v22;
    v23 = (const WCHAR *)((char *)v19 + 8);
    if ( *((_QWORD *)v19 + 4) <= 7u )
      v24 = (const WCHAR *)((char *)v19 + 8);
    else
      v24 = *(const WCHAR **)v23;
    FileNameW = PathFindFileNameW(v24);
    if ( !PathIsFileSpecW(FileNameW) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)0xA1,
        v53);
    v26 = (_QWORD *)((char *)v19 + 40);
    if ( *((_QWORD *)v19 + 8) <= 7u )
      v27 = (_QWORD *)((char *)v19 + 40);
    else
      v27 = (_QWORD *)*v26;
    LowPart = *((unsigned __int8 *)v19 + 73);
    v28 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, _QWORD *, _QWORD))(*(_QWORD *)v79 + 24LL))(
            v79,
            FileNameW,
            v27,
            *((unsigned __int8 *)v19 + 72));
    v29 = v28;
    if ( v28 < 0 )
    {
      v30 = v28 & 0xEFFFFFFF;
      _snwprintf_s<16>(v83, 16, L"%%%%%u", v28 & 0xEFFFFFFF);
      _snwprintf_s<16>(v82, 16, L"0x%08X", v30);
      if ( *((_QWORD *)v19 + 8) > 7u )
        v26 = (_QWORD *)*v26;
      v61 = (__int64)v26;
      if ( *((_QWORD *)v19 + 4) > 7u )
        v23 = *(const WCHAR **)v23;
      v60 = (__int64)v23;
      v31 = *v65;
      *(_QWORD *)&v59[1] = *v65 + 1152;
      FileSize.QuadPart = (LONGLONG)VirtualMachine::GetVmName((VirtualMachine *)(v31 + 16));
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16],unsigned short const *,unsigned short const *>(
        (struct _EVENT_DESCRIPTOR *)&MSVML_FAILED_TO_START_GUEST_COPY,
        (__int64)&FileSize,
        (__int64)&v59[1],
        v83,
        v82,
        (__int64)&v60,
        (__int64)&v61);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)v29,
        v55);
    }
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = v70;
    NumberOfBytesTransferred = v78;
    v32 = Vml::VmFile::Read((Vml::VmFile *)&v69, v81[0], &NumberOfBytesTransferred, &Overlapped);
    FileSize.QuadPart = 0;
    v33 = 0;
    v63 = 0;
    v34 = 0;
    v59[0] = 0;
    v35 = v32 == 0;
    while ( 1 )
    {
      if ( v35 )
      {
        if ( !GetOverlappedResult(v22, &Overlapped, &NumberOfBytesTransferred, 1) )
        {
          v41 = GetLastError();
          if ( v41 != 996 )
          {
            if ( v41 != 38 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x4D6,
                (unsigned int)"onecore\\vm\\common/vml/VmFiles.h",
                (const char *)v41,
                LowPart);
            NumberOfBytesTransferred = 0;
          }
        }
        if ( !NumberOfBytesTransferred )
        {
          v35 = 0;
          goto LABEL_75;
        }
        LOBYTE(v34) = v59[0];
        v33 = v63;
      }
      else if ( !NumberOfBytesTransferred )
      {
        v36 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int64))(*(_QWORD *)v79 + 48LL))(
                v79,
                &GUID_NULL,
                v34,
                v33);
        v1 = v36;
        if ( v36 < 0 )
        {
          v37 = v36 & 0xEFFFFFFF;
          _snwprintf_s<16>(v82, 16, L"%%%%%u", v36 & 0xEFFFFFFF);
          _snwprintf_s<16>(v83, 16, L"0x%08X", v37);
          if ( *((_QWORD *)v19 + 8) > 7u )
            v26 = (_QWORD *)*v26;
          v61 = (__int64)v26;
          if ( *((_QWORD *)v19 + 4) > 7u )
            v23 = *(const WCHAR **)v23;
          v60 = (__int64)v23;
          v38 = *v65;
          *(_QWORD *)&v59[1] = *v65 + 1152;
          FileSize.QuadPart = (LONGLONG)VirtualMachine::GetVmName((VirtualMachine *)(v38 + 16));
          VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16],unsigned short const *,unsigned short const *>(
            (struct _EVENT_DESCRIPTOR *)&MSVML_FAILED_TO_COMPLETE_GUEST_COPY,
            (__int64)&FileSize,
            (__int64)&v59[1],
            v82,
            v83,
            (__int64)&v60,
            (__int64)&v61);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x183,
            (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
            (const char *)(unsigned int)v1,
            v56);
        }
        if ( *((_QWORD *)v19 + 8) > 7u )
          v26 = (_QWORD *)*v26;
        FileSize.QuadPart = (LONGLONG)v26;
        if ( *((_QWORD *)v19 + 4) > 7u )
          v23 = *(const WCHAR **)v23;
        v63 = (__int64)v23;
        v21 = v65;
        v39 = *v65;
        v64 = *v65 + 1152;
        *(_QWORD *)v62 = VirtualMachine::GetVmName((VirtualMachine *)(v39 + 16));
        VmEventWrite<unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
          &MSVML_WP_SUCCEEDED_COPY_FILES_TO_GUEST,
          (__int64)&v64,
          (__int64)&v63,
          (__int64)&FileSize);
        Vml::VmFile::Reset((Vml::VmFile *)&v69, v40);
        v19 = (GuestFileCopy *)((char *)v19 + 88);
        v20 = v72;
        goto LABEL_26;
      }
      v62[0] = NumberOfBytesTransferred;
      v71 = ((_BYTE)v34 - 1) & 1;
      v63 = NumberOfBytesTransferred + v33;
      Overlapped.Pointer = (PVOID)v63;
      NumberOfBytesTransferred = v78;
      LODWORD(v64) = Vml::VmFile::Read((Vml::VmFile *)&v69, v81[3 * v71], &NumberOfBytesTransferred, &Overlapped) == 0;
      LowPart = FileSize.LowPart;
      v59[0] = (*(__int64 (__fastcall **)(__int64, GUID *, void *, _QWORD))(*(_QWORD *)v79 + 40LL))(
                 v79,
                 &GUID_NULL,
                 v81[3 * v59[0]],
                 (unsigned int)v62[0]);
      if ( v59[0] < 0 )
      {
        (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v79 + 56LL))(v79, &GUID_NULL);
        _snwprintf_s<16>(v82, 16, L"%%%%%u", v59[0] & 0xEFFFFFFF);
        _snwprintf_s<16>(v83, 16, L"0x%08X", v59[0] & 0xEFFFFFFF);
        if ( *((_QWORD *)v19 + 8) > 7u )
          v26 = (_QWORD *)*v26;
        v61 = (__int64)v26;
        if ( *((_QWORD *)v19 + 4) > 7u )
          v23 = *(const WCHAR **)v23;
        v60 = (__int64)v23;
        v42 = *v65;
        *(_QWORD *)&v59[1] = *v65 + 1152;
        FileSize.QuadPart = (LONGLONG)VirtualMachine::GetVmName((VirtualMachine *)(v42 + 16));
        VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16],unsigned short const *,unsigned short const *>(
          (struct _EVENT_DESCRIPTOR *)&MSVML_FAILED_TO_PERFORM_GUEST_COPY,
          (__int64)&FileSize,
          (__int64)&v59[1],
          v82,
          v83,
          (__int64)&v60,
          (__int64)&v61);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
          (const char *)v59[0],
          v57);
      }
      v34 = (unsigned int)v71;
      v59[0] = v71;
      FileSize.QuadPart += (unsigned int)v62[0];
      v60 += (unsigned int)v62[0];
      v43 = 100 * v60 / (unsigned __int64)v61;
      v71 = v43;
      if ( (_DWORD)v43 == v66 )
      {
        v35 = v64;
        goto LABEL_76;
      }
      v62[0] = 0;
      WorkerAsyncTaskBase::UpdateStatusProgress(*(WorkerAsyncTaskBase **)&v59[1], v43, v62);
      if ( v62[0] || *(_DWORD *)(*(_QWORD *)&v59[1] + 424LL) )
      {
        (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v79 + 56LL))(v79, &GUID_NULL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x168,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
          (const char *)0x80042001LL,
          LowPart);
      }
      v66 = v71;
      v35 = v64;
LABEL_75:
      v34 = v59[0];
LABEL_76:
      v33 = v63;
    }
  }
  catch ( ... )
  {
    LODWORD(v64) = wil::details::in1diag3::Log_CaughtException(
                     retaddr,
                     (void *)0x193,
                     (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
                     v45);
    v14 = VmName + 400;
    v1 = v64;
    v46 = (WorkerAsyncTaskBase *)v68;
    v21 = v65;
  }
LABEL_89:
  if ( *(_QWORD *)v14 != *(_QWORD *)(v14 + 8) )
  {
    std::_Destroy_range<std::allocator<GuestFileCopy>>(*(GuestFileCopy **)v14);
    *(_QWORD *)(v14 + 8) = *(_QWORD *)v14;
  }
  if ( v1 >= 0 )
  {
    v49 = 40;
  }
  else
  {
    if ( v1 == -2147213311 )
    {
      v47 = *v21;
      v68 = *v21 + 1152;
      VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v47 + 16));
      VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
        (struct _EVENT_DESCRIPTOR *)&MSVML_WP_CANCELLED_COPY_FILES_TO_GUEST,
        5u,
        (__int64)&VmName,
        (__int64)&v68);
    }
    else
    {
      _snwprintf_s<16>(v82, 16, L"%%%%%u", v1 & 0xEFFFFFFF);
      _snwprintf_s<16>(v83, 16, L"0x%08X", v1 & 0xEFFFFFFF);
      v48 = *v21;
      v68 = *v21 + 1152;
      VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v48 + 16));
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
        (struct _EVENT_DESCRIPTOR *)&MSVML_WP_FAILED_COPY_FILES_TO_GUEST,
        5u,
        (__int64)&VmName,
        (__int64)&v68,
        (__int64)v82,
        (__int64)v83);
    }
    v49 = 41;
  }
  VirtualMachine::SetState(*v74, 2, v49);
  *(_QWORD *)&v59[1] = 0;
  VmErrInfo = GetVmErrInfo();
  Vml::VmComPtr<IVmSimpleTask>::Attach<IVmSimpleTask>(&v59[1], VmErrInfo);
  WorkerAsyncTaskBase::SetStatusComplete(v46, v1, *(struct IUnknown **)&v59[1]);
  Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(&v59[1]);
  Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(&v79);
}

```

## disassembly

```asm
0x1400632a0  mov     r11, rsp
0x1400632a3  mov     [r11+10h], rbx
0x1400632a7  mov     [r11+18h], rsi
0x1400632ab  push    rdi
0x1400632ac  push    r12
0x1400632ae  push    r13
0x1400632b0  push    r14
0x1400632b2  push    r15
0x1400632b4  sub     rsp, 1A0h
0x1400632bb  mov     rax, cs:__security_cookie
0x1400632c2  xor     rax, rsp
0x1400632c5  mov     [rsp+1C8h+var_38], rax
0x1400632cd  mov     qword ptr [rsp+1C8h+var_174+4], rcx
0x1400632d2  mov     [rsp+1C8h+var_128], rcx
0x1400632da  mov     [rsp+1C8h+var_130], rcx
0x1400632e2  xor     edi, edi
0x1400632e4  mov     r12d, edi
0x1400632e7  mov     [r11-0B8h], rdi
0x1400632ee  mov     [rsp+1C8h+var_178], edi
0x1400632f2  mov     [r11-0B0h], rdi
0x1400632f9  mov     qword ptr [r11-100h], 0FFFFFFFFFFFFFFFFh
0x140063304  lea     rsi, [rcx+10h]
0x140063308  mov     [rsp+1C8h+var_140], rsi
0x140063310  mov     [rsp+1C8h+var_F8], rsi
0x140063318  mov     rcx, [rsi]
0x14006331b  lea     r9, [r11-0B0h]; struct IUnknown **
0x140063322  lea     r8, IID_IUnknown; struct _GUID *
0x140063329  lea     rdx, g_ICVDevClassIdGuestInterface; struct _GUID *
0x140063330  mov     rcx, [rcx+3D8h]; this
0x140063337  call    ?FindVirtualDevice@VirtualMotherboard@@QEAAJAEBU_GUID@@0PEAPEAUIUnknown@@@Z; VirtualMotherboard::FindVirtualDevice(_GUID const &,_GUID const &,IUnknown * *)
0x14006333c  mov     rcx, [rsp+1C8h]; this
0x140063344  test    eax, eax
0x140063346  jns     short loc_14006335C
0x140063348  mov     r9d, eax; char *
0x14006334b  lea     r8, aOnecoreVmWorke_118; "onecore\\vm\\worker\\wpcore\\workertask"...
0x140063352  mov     edx, 86h; void *
0x140063357  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006335c  mov     rcx, [rsp+1C8h+var_B0]
0x140063364  mov     rax, [rcx]
0x140063367  lea     r8, [rsp+1C8h+var_B8]
0x14006336f  lea     rdx, IID_IICGuestInterface
0x140063376  mov     rax, [rax]
0x140063379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006337e  mov     rcx, [rsp+1C8h]; this
0x140063386  test    eax, eax
0x140063388  jns     short loc_14006339E
0x14006338a  mov     r9d, eax; char *
0x14006338d  lea     r8, aOnecoreVmWorke_118; "onecore\\vm\\worker\\wpcore\\workertask"...
0x140063394  mov     edx, 8Ah; void *
0x140063399  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006339e  mov     [rsp+1C8h+var_118], rdi
0x1400633a6  xor     r8d, r8d; int
0x1400633a9  xor     edx, edx; int
0x1400633ab  lea     rcx, [rsp+1C8h+var_118]; this
0x1400633b3  call    ??0VmEvent@Vml@@QEAA@HHPEAU_SECURITY_ATTRIBUTES@@PEBG1@Z; Vml::VmEvent::VmEvent(int,int,_SECURITY_ATTRIBUTES *,ushort const *,ushort const *)
0x1400633b8  nop
0x1400633b9  mov     [rsp+1C8h+var_C0], edi
0x1400633c0  mov     rcx, [rsp+1C8h+var_B8]
0x1400633c8  mov     rax, [rcx]
0x1400633cb  lea     rdx, [rsp+1C8h+var_C0]
0x1400633d3  mov     rax, [rax+20h]
0x1400633d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400633dc  mov     rcx, [rsp+1C8h]; this
0x1400633e4  test    eax, eax
0x1400633e6  jns     short loc_1400633FC
0x1400633e8  mov     r9d, eax; char *
0x1400633eb  lea     r8, aOnecoreVmWorke_118; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400633f2  mov     edx, 98h; void *
0x1400633f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400633fc  lea     rax, ??1?$pair@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@_K@std@@QEAA@XZ; std::pair<std::vector<gsl::byte>,unsigned __int64>::~pair<std::vector<gsl::byte>,unsigned __int64>(void)
0x140063403  mov     [rsp+1C8h+var_1A8], rax; unsigned int
0x140063408  lea     r9, ??0?$vector@U?$atomic@_N@std@@V?$allocator@U?$atomic@_N@std@@@2@@std@@QEAA@XZ; void (*)(void *)
0x14006340f  mov     edx, 18h; unsigned __int64
0x140063414  lea     r8d, [rdx-16h]; unsigned __int64
0x140063418  lea     rcx, [rsp+1C8h+var_A8]; void *
0x140063420  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140063425  nop
0x140063426  mov     r14d, edi
0x140063429  cmp     r14d, 2
0x14006342d  jnb     short loc_140063499
0x14006342f  mov     eax, r14d
0x140063432  lea     rcx, [rax+rax*2]
0x140063436  lea     rsi, [rsp+1C8h+var_A8]
0x14006343e  lea     rsi, [rsi+rcx*8]
0x140063442  mov     ebx, [rsp+1C8h+var_C0]
0x140063449  mov     rdx, [rsi]
0x14006344c  mov     r15, [rsi+8]
0x140063450  mov     rcx, r15
0x140063453  sub     rcx, rdx
0x140063456  cmp     rbx, rcx
0x140063459  jnb     short loc_140063461
0x14006345b  lea     rax, [rdx+rbx]
0x14006345f  jmp     short loc_140063490
0x140063461  jbe     short loc_140063494
0x140063463  mov     rax, [rsi+10h]
0x140063467  sub     rax, rdx
0x14006346a  cmp     rbx, rax
0x14006346d  jbe     short loc_14006347C
0x14006346f  mov     rdx, rbx
0x140063472  mov     rcx, rsi
0x140063475  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x14006347a  jmp     short loc_140063494
0x14006347c  sub     rbx, rcx
0x14006347f  mov     r8, rbx; Size
0x140063482  xor     edx, edx; Val
0x140063484  mov     rcx, r15; void *
0x140063487  call    memset_0
0x14006348c  lea     rax, [rbx+r15]
0x140063490  mov     [rsi+8], rax
0x140063494  inc     r14d
0x140063497  jmp     short loc_140063429
0x140063499  mov     r14, rdi
0x14006349c  mov     [rsp+1C8h+var_160], rdi
0x1400634a1  mov     r13, qword ptr [rsp+1C8h+var_174+4]
0x1400634a6  add     r13, 190h
0x1400634ad  mov     rbx, [r13+0]
0x1400634b1  mov     rsi, [r13+8]
0x1400634b5  cmp     rbx, rsi
0x1400634b8  jz      short loc_14006352B
0x1400634ba  mov     qword ptr [rsp+1C8h+FileSize], rdi
0x1400634c2  lea     rdx, [rsp+1C8h+FileSize]; lpFileSize
0x1400634ca  mov     rcx, [rbx]; hFile
0x1400634cd  call    cs:__imp_GetFileSizeEx
0x1400634d4  nop     dword ptr [rax+rax+00h]
0x1400634d9  test    eax, eax
0x1400634db  jnz     short loc_140063511
0x1400634dd  call    cs:__imp_GetLastError
0x1400634e4  nop     dword ptr [rax+rax+00h]
0x1400634e9  test    eax, eax
0x1400634eb  jle     short loc_1400634F5
0x1400634ed  movzx   eax, ax
0x1400634f0  or      eax, 80070000h
0x1400634f5  mov     rcx, [rsp+1C8h]; this
0x1400634fd  mov     r9d, eax; char *
0x140063500  lea     r8, aOnecoreVmWorke_118; "onecore\\vm\\worker\\wpcore\\workertask"...
0x140063507  mov     edx, 0ABh; void *
0x14006350c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140063511  mov     rax, qword ptr [rsp+1C8h+FileSize]
0x140063519  mov     [rbx+50h], rax
0x14006351d  add     r14, rax
0x140063520  mov     [rsp+1C8h+var_160], r14
0x140063525  add     rbx, 58h ; 'X'
0x140063529  jmp     short loc_1400634B5
0x14006352b  mov     [rsp+1C8h+var_168], rdi
0x140063530  mov     [rsp+1C8h+var_138], edi
0x140063537  mov     r15, [r13+0]
0x14006353b  mov     rax, [r13+8]
0x14006353f  mov     [rsp+1C8h+var_108], rax
0x140063547  mov     rsi, [rsp+1C8h+var_140]
0x14006354f  lea     rbx, GUID_NULL
0x140063556  cmp     r15, rax
0x140063559  jz      loc_140063CAE
0x14006355f  mov     rbx, [r15]
0x140063562  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x140063569  mov     [rsp+1C8h+var_120], rbx
0x140063571  lea     r14, [r15+8]
0x140063575  cmp     qword ptr [r15+20h], 7
0x14006357a  jbe     short loc_140063581
0x14006357c  mov     rcx, [r14]
0x14006357f  jmp     short loc_140063584
0x140063581  mov     rcx, r14; pszPath
0x140063584  call    cs:__imp_PathFindFileNameW
0x14006358b  nop     dword ptr [rax+rax+00h]
0x140063590  mov     r12, rax
0x140063593  mov     rcx, rax; pszPath
0x140063596  call    cs:__imp_PathIsFileSpecW
0x14006359d  nop     dword ptr [rax+rax+00h]
0x1400635a2  test    eax, eax
0x1400635a4  jnz     short loc_1400635C4
0x1400635a6  mov     rcx, [rsp+1C8h]; this
0x1400635ae  mov     r9d, 0A1h; char *
0x1400635b4  lea     r8, aOnecoreVmWorke_118; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400635bb  lea     edx, [r9+20h]; void *
0x1400635bf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400635c4  mov     rcx, [rsp+1C8h+var_B8]
0x1400635cc  mov     rax, [rcx]
0x1400635cf  mov     r11, [rax+18h]
0x1400635d3  mov     rdx, [r15+50h]
0x1400635d7  movzx   r9d, byte ptr [r15+49h]
0x1400635dc  movzx   r10d, byte ptr [r15+48h]
0x1400635e1  lea     rsi, [r15+28h]
0x1400635e5  cmp     qword ptr [r15+40h], 7
0x1400635ea  jbe     short loc_1400635F1
0x1400635ec  mov     r8, [rsi]
0x1400635ef  jmp     short loc_1400635F4
0x1400635f1  mov     r8, rsi
0x1400635f4  lea     rax, GUID_NULL
0x1400635fb  mov     [rsp+1C8h+var_198], rax
0x140063600  mov     [rsp+1C8h+var_1A0], rdx
0x140063605  mov     dword ptr [rsp+1C8h+var_1A8], r9d; unsigned int
0x14006360a  mov     r9d, r10d
0x14006360d  mov     rdx, r12
0x140063610  mov     rax, r11
0x140063613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063618  mov     r12d, eax
0x14006361b  test    eax, eax
0x14006361d  jns     loc_140063715
0x140063623  mov     ebx, eax
0x140063625  btr     ebx, 1Ch
0x140063629  mov     r9d, ebx
0x14006362c  lea     r8, aU_0; "%%%%%u"
0x140063633  mov     r15d, 10h
0x140063639  mov     edx, r15d
0x14006363c  lea     rcx, [rsp+1C8h+var_58]
0x140063644  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x140063649  mov     r9d, ebx
0x14006364c  lea     r8, a0x08x; "0x%08X"
0x140063653  mov     edx, r15d
0x140063656  lea     rcx, [rsp+1C8h+var_78]
0x14006365e  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x140063663  cmp     qword ptr [rsi+18h], 7
0x140063668  jbe     short loc_14006366D
0x14006366a  mov     rsi, [rsi]
0x14006366d  mov     [rsp+1C8h+var_160], rsi
0x140063672  cmp     qword ptr [r14+18h], 7
0x140063677  jbe     short loc_14006367C
0x140063679  mov     r14, [r14]
0x14006367c  mov     [rsp+1C8h+var_168], r14
0x140063681  mov     rcx, [rsp+1C8h+var_140]
0x140063689  mov     rcx, [rcx]
0x14006368c  lea     rax, [rcx+480h]
0x140063693  mov     qword ptr [rsp+1C8h+var_174+4], rax
0x140063698  add     rcx, r15; this
0x14006369b  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400636a0  mov     qword ptr [rsp+1C8h+FileSize], rax
0x1400636a8  lea     rax, [rsp+1C8h+var_160]
0x1400636ad  mov     [rsp+1C8h+var_180], rax; __int64
0x1400636b2  lea     rax, [rsp+1C8h+var_168]
0x1400636b7  mov     [rsp+1C8h+var_188], rax; __int64
0x1400636bc  lea     rax, [rsp+1C8h+var_78]
0x1400636c4  mov     [rsp+1C8h+var_190], rax; unsigned __int16 *
0x1400636c9  lea     rax, [rsp+1C8h+var_58]
0x1400636d1  mov     [rsp+1C8h+var_198], rax; unsigned __int16 *
0x1400636d6  lea     rax, [rsp+1C8h+var_174+4]
0x1400636db  mov     [rsp+1C8h+var_1A0], rax; __int64
0x1400636e0  lea     rax, [rsp+1C8h+FileSize]
0x1400636e8  mov     [rsp+1C8h+var_1A8], rax; int
0x1400636ed  lea     rcx, MSVML_FAILED_TO_START_GUEST_COPY; struct _EVENT_DESCRIPTOR *
0x1400636f4  call    ??$VmEventWriteAndReport@PEBGPEBGAEAY0BA@GAEAY0BA@GPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG3AEAY0BA@G433@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort (&)[16],ushort (&)[16],ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort (&)[16],ushort (&)[16],ushort const * &&,ushort const * &&)
0x1400636f9  mov     rcx, [rsp+1C8h]; this
0x140063701  mov     r9d, r12d; char *
0x140063704  lea     r8, aOnecoreVmWorke_118; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14006370b  mov     edx, 0DEh; void *
0x140063710  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140063715  mov     [rsp+1C8h+Overlapped.Internal], rdi
0x14006371d  mov     [rsp+1C8h+Overlapped.InternalHigh], rdi
0x140063725  mov     qword ptr [rsp+1C8h+Overlapped.10h], rdi
0x14006372d  mov     rax, [rsp+1C8h+var_118]
0x140063735  mov     [rsp+1C8h+Overlapped.hEvent], rax
0x14006373d  mov     eax, [rsp+1C8h+var_C0]
0x140063744  mov     [rsp+1C8h+NumberOfBytesTransferred], eax
0x14006374b  mov     [rsp+1C8h+var_178], 1
0x140063753  lea     r9, [rsp+1C8h+Overlapped]; struct _OVERLAPPED *
0x14006375b  lea     r8, [rsp+1C8h+NumberOfBytesTransferred]; unsigned int *
0x140063763  mov     rdx, [rsp+1C8h+var_A8]; void *
0x14006376b  lea     rcx, [rsp+1C8h+var_120]; this
0x140063773  call    ?Read@VmFile@Vml@@QEAAHPEAXAEAKPEAU_OVERLAPPED@@@Z; Vml::VmFile::Read(void *,ulong &,_OVERLAPPED *)
0x140063778  mov     ecx, eax
0x14006377a  mov     qword ptr [rsp+1C8h+FileSize], rdi
0x140063782  mov     r9, rdi
0x140063785  mov     [rsp+1C8h+var_150], rdi
0x14006378a  mov     r8d, edi
0x14006378d  mov     dword ptr [rsp+1C8h+var_174], edi
0x140063791  mov     [rsp+1C8h+var_178], edi
0x140063795  mov     eax, edi
0x140063797  test    ecx, ecx
0x140063799  setz    al
0x14006379c  mov     r12, qword ptr [rsp+1C8h+var_174+4]
0x1400637a1  test    eax, eax
0x1400637a3  jnz     loc_14006396E
0x1400637a9  cmp     [rsp+1C8h+NumberOfBytesTransferred], edi
0x1400637b0  ja      loc_1400639F1
0x1400637b6  mov     rcx, [rsp+1C8h+var_B8]
0x1400637be  mov     rax, [rcx]
0x1400637c1  lea     rbx, GUID_NULL
0x1400637c8  mov     rdx, rbx
0x1400637cb  mov     rax, [rax+30h]
0x1400637cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400637d4  mov     r12d, eax
0x1400637d7  test    eax, eax
0x1400637d9  jns     loc_1400638D1
0x1400637df  mov     ebx, eax
0x1400637e1  btr     ebx, 1Ch
0x1400637e5  mov     r9d, ebx
0x1400637e8  lea     r8, aU_0; "%%%%%u"
0x1400637ef  mov     r15d, 10h
0x1400637f5  mov     edx, r15d
0x1400637f8  lea     rcx, [rsp+1C8h+var_78]
0x140063800  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x140063805  mov     r9d, ebx
0x140063808  lea     r8, a0x08x; "0x%08X"
0x14006380f  mov     edx, r15d
0x140063812  lea     rcx, [rsp+1C8h+var_58]
0x14006381a  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14006381f  cmp     qword ptr [rsi+18h], 7
0x140063824  jbe     short loc_140063829
0x140063826  mov     rsi, [rsi]
0x140063829  mov     [rsp+1C8h+var_160], rsi
0x14006382e  cmp     qword ptr [r14+18h], 7
0x140063833  jbe     short loc_140063838
  ... truncated ...
```
