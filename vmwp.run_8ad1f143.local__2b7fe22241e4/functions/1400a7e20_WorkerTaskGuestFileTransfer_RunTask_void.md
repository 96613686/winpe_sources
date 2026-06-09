# WorkerTaskGuestFileTransfer::RunTask(void)

- ea: `0x1400a7e20`
- end: `0x1400a8a96`
- name: `?RunTask@WorkerTaskGuestFileTransfer@@UEAAXXZ`
- size: `3190`
- prototype: `void __fastcall(WorkerTaskGuestFileTransfer *__hidden this)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x14001e648`
- `0x14002ecf0`
- `0x140032f60`
- `0x140053564`
- `0x14005dbf0`
- `0x14006af58`
- `0x14009d7cc`
- `0x1400a7e20`
- `0x1400a8a9c`
- `0x1400a8bc8`
- `0x1400a8c14`
- `0x1400a8e54`
- `0x1400a9ad8`
- `0x1400b0d60`
- `0x1400cf8c0`
- `0x1400dbe6c`
- `0x1400df15c`
- `0x1400eb548`
- `0x140122778`
- `0x140132960`
- `0x140132990`
- `0x14013361c`
- `0x140133a1c`
- `0x14015b72c`
- `0x14018d1f0`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a805d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a8517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a805d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a8517`
- `vmprox!GetVmErrInfo` at `0x1400a8a26`
- `vmprox!GetVmErrInfo` at `0x1400a8a26`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400a804d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400a804d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400a8507`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400a8507`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1400a8116`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1400a8116`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400a8104`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400a8104`

## string_xrefs

- `0x1400a7ecb`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a7f0d`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a7f6b`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8080`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8134`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8284`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8440`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8749`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a87ff`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8542`: `onecore\vm\common/vml/VmFiles.h`

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
0x1400a7e20  mov     r11, rsp
0x1400a7e23  mov     [r11+10h], rbx
0x1400a7e27  mov     [r11+18h], rsi
0x1400a7e2b  push    rdi
0x1400a7e2c  push    r12
0x1400a7e2e  push    r13
0x1400a7e30  push    r14
0x1400a7e32  push    r15
0x1400a7e34  sub     rsp, 1A0h
0x1400a7e3b  mov     rax, cs:__security_cookie
0x1400a7e42  xor     rax, rsp
0x1400a7e45  mov     [rsp+1C8h+var_38], rax
0x1400a7e4d  mov     qword ptr [rsp+1C8h+var_174+4], rcx
0x1400a7e52  mov     [rsp+1C8h+var_128], rcx
0x1400a7e5a  mov     [rsp+1C8h+var_130], rcx
0x1400a7e62  xor     edi, edi
0x1400a7e64  mov     r12d, edi
0x1400a7e67  mov     [r11-0B8h], rdi
0x1400a7e6e  mov     [rsp+1C8h+var_178], edi
0x1400a7e72  mov     [r11-0B0h], rdi
0x1400a7e79  mov     qword ptr [r11-100h], 0FFFFFFFFFFFFFFFFh
0x1400a7e84  lea     rsi, [rcx+10h]
0x1400a7e88  mov     [rsp+1C8h+var_140], rsi
0x1400a7e90  mov     [rsp+1C8h+var_F8], rsi
0x1400a7e98  mov     rcx, [rsi]
0x1400a7e9b  lea     r9, [r11-0B0h]; struct IUnknown **
0x1400a7ea2  lea     r8, IID_IUnknown; struct _GUID *
0x1400a7ea9  lea     rdx, g_ICVDevClassIdGuestInterface; struct _GUID *
0x1400a7eb0  mov     rcx, [rcx+3D8h]; this
0x1400a7eb7  call    ?FindVirtualDevice@VirtualMotherboard@@QEAAJAEBU_GUID@@0PEAPEAUIUnknown@@@Z; VirtualMotherboard::FindVirtualDevice(_GUID const &,_GUID const &,IUnknown * *)
0x1400a7ebc  mov     rcx, [rsp+1C8h]; this
0x1400a7ec4  test    eax, eax
0x1400a7ec6  jns     short loc_1400A7EDC
0x1400a7ec8  mov     r9d, eax; char *
0x1400a7ecb  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a7ed2  mov     edx, 86h; void *
0x1400a7ed7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a7edc  mov     rcx, [rsp+1C8h+var_B0]
0x1400a7ee4  mov     rax, [rcx]
0x1400a7ee7  lea     r8, [rsp+1C8h+var_B8]
0x1400a7eef  lea     rdx, IID_IICGuestInterface
0x1400a7ef6  mov     rax, [rax]
0x1400a7ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a7efe  mov     rcx, [rsp+1C8h]; this
0x1400a7f06  test    eax, eax
0x1400a7f08  jns     short loc_1400A7F1E
0x1400a7f0a  mov     r9d, eax; char *
0x1400a7f0d  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a7f14  mov     edx, 8Ah; void *
0x1400a7f19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a7f1e  mov     [rsp+1C8h+var_118], rdi
0x1400a7f26  xor     r8d, r8d; int
0x1400a7f29  xor     edx, edx; int
0x1400a7f2b  lea     rcx, [rsp+1C8h+var_118]; this
0x1400a7f33  call    ??0VmEvent@Vml@@QEAA@HHPEAU_SECURITY_ATTRIBUTES@@PEBG1@Z; Vml::VmEvent::VmEvent(int,int,_SECURITY_ATTRIBUTES *,ushort const *,ushort const *)
0x1400a7f38  nop
0x1400a7f39  mov     [rsp+1C8h+var_C0], edi
0x1400a7f40  mov     rcx, [rsp+1C8h+var_B8]
0x1400a7f48  mov     rax, [rcx]
0x1400a7f4b  lea     rdx, [rsp+1C8h+var_C0]
0x1400a7f53  mov     rax, [rax+20h]
0x1400a7f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a7f5c  mov     rcx, [rsp+1C8h]; this
0x1400a7f64  test    eax, eax
0x1400a7f66  jns     short loc_1400A7F7C
0x1400a7f68  mov     r9d, eax; char *
0x1400a7f6b  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a7f72  mov     edx, 98h; void *
0x1400a7f77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a7f7c  lea     rax, ??1?$pair@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@_K@std@@QEAA@XZ; std::pair<std::vector<gsl::byte>,unsigned __int64>::~pair<std::vector<gsl::byte>,unsigned __int64>(void)
0x1400a7f83  mov     [rsp+1C8h+var_1A8], rax; unsigned int
0x1400a7f88  lea     r9, ??0?$vector@U?$atomic@_N@std@@V?$allocator@U?$atomic@_N@std@@@2@@std@@QEAA@XZ; void (*)(void *)
0x1400a7f8f  mov     edx, 18h; unsigned __int64
0x1400a7f94  lea     r8d, [rdx-16h]; unsigned __int64
0x1400a7f98  lea     rcx, [rsp+1C8h+var_A8]; void *
0x1400a7fa0  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400a7fa5  nop
0x1400a7fa6  mov     r14d, edi
0x1400a7fa9  cmp     r14d, 2
0x1400a7fad  jnb     short loc_1400A8019
0x1400a7faf  mov     eax, r14d
0x1400a7fb2  lea     rcx, [rax+rax*2]
0x1400a7fb6  lea     rsi, [rsp+1C8h+var_A8]
0x1400a7fbe  lea     rsi, [rsi+rcx*8]
0x1400a7fc2  mov     ebx, [rsp+1C8h+var_C0]
0x1400a7fc9  mov     rdx, [rsi]
0x1400a7fcc  mov     r15, [rsi+8]
0x1400a7fd0  mov     rcx, r15
0x1400a7fd3  sub     rcx, rdx
0x1400a7fd6  cmp     rbx, rcx
0x1400a7fd9  jnb     short loc_1400A7FE1
0x1400a7fdb  lea     rax, [rdx+rbx]
0x1400a7fdf  jmp     short loc_1400A8010
0x1400a7fe1  jbe     short loc_1400A8014
0x1400a7fe3  mov     rax, [rsi+10h]
0x1400a7fe7  sub     rax, rdx
0x1400a7fea  cmp     rbx, rax
0x1400a7fed  jbe     short loc_1400A7FFC
0x1400a7fef  mov     rdx, rbx
0x1400a7ff2  mov     rcx, rsi
0x1400a7ff5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1400a7ffa  jmp     short loc_1400A8014
0x1400a7ffc  sub     rbx, rcx
0x1400a7fff  mov     r8, rbx; Size
0x1400a8002  xor     edx, edx; Val
0x1400a8004  mov     rcx, r15; void *
0x1400a8007  call    memset_0
0x1400a800c  lea     rax, [rbx+r15]
0x1400a8010  mov     [rsi+8], rax
0x1400a8014  inc     r14d
0x1400a8017  jmp     short loc_1400A7FA9
0x1400a8019  mov     r14, rdi
0x1400a801c  mov     [rsp+1C8h+var_160], rdi
0x1400a8021  mov     r13, qword ptr [rsp+1C8h+var_174+4]
0x1400a8026  add     r13, 190h
0x1400a802d  mov     rbx, [r13+0]
0x1400a8031  mov     rsi, [r13+8]
0x1400a8035  cmp     rbx, rsi
0x1400a8038  jz      short loc_1400A80AB
0x1400a803a  mov     qword ptr [rsp+1C8h+FileSize], rdi
0x1400a8042  lea     rdx, [rsp+1C8h+FileSize]; lpFileSize
0x1400a804a  mov     rcx, [rbx]; hFile
0x1400a804d  call    cs:__imp_GetFileSizeEx
0x1400a8054  nop     dword ptr [rax+rax+00h]
0x1400a8059  test    eax, eax
0x1400a805b  jnz     short loc_1400A8091
0x1400a805d  call    cs:__imp_GetLastError
0x1400a8064  nop     dword ptr [rax+rax+00h]
0x1400a8069  test    eax, eax
0x1400a806b  jle     short loc_1400A8075
0x1400a806d  movzx   eax, ax
0x1400a8070  or      eax, 80070000h
0x1400a8075  mov     rcx, [rsp+1C8h]; this
0x1400a807d  mov     r9d, eax; char *
0x1400a8080  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a8087  mov     edx, 0ABh; void *
0x1400a808c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a8091  mov     rax, qword ptr [rsp+1C8h+FileSize]
0x1400a8099  mov     [rbx+50h], rax
0x1400a809d  add     r14, rax
0x1400a80a0  mov     [rsp+1C8h+var_160], r14
0x1400a80a5  add     rbx, 58h ; 'X'
0x1400a80a9  jmp     short loc_1400A8035
0x1400a80ab  mov     [rsp+1C8h+var_168], rdi
0x1400a80b0  mov     [rsp+1C8h+var_138], edi
0x1400a80b7  mov     r15, [r13+0]
0x1400a80bb  mov     rax, [r13+8]
0x1400a80bf  mov     [rsp+1C8h+var_108], rax
0x1400a80c7  mov     rsi, [rsp+1C8h+var_140]
0x1400a80cf  lea     rbx, GUID_NULL
0x1400a80d6  cmp     r15, rax
0x1400a80d9  jz      loc_1400A882E
0x1400a80df  mov     rbx, [r15]
0x1400a80e2  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1400a80e9  mov     [rsp+1C8h+var_120], rbx
0x1400a80f1  lea     r14, [r15+8]
0x1400a80f5  cmp     qword ptr [r15+20h], 7
0x1400a80fa  jbe     short loc_1400A8101
0x1400a80fc  mov     rcx, [r14]
0x1400a80ff  jmp     short loc_1400A8104
0x1400a8101  mov     rcx, r14; pszPath
0x1400a8104  call    cs:__imp_PathFindFileNameW
0x1400a810b  nop     dword ptr [rax+rax+00h]
0x1400a8110  mov     r12, rax
0x1400a8113  mov     rcx, rax; pszPath
0x1400a8116  call    cs:__imp_PathIsFileSpecW
0x1400a811d  nop     dword ptr [rax+rax+00h]
0x1400a8122  test    eax, eax
0x1400a8124  jnz     short loc_1400A8144
0x1400a8126  mov     rcx, [rsp+1C8h]; this
0x1400a812e  mov     r9d, 0A1h; char *
0x1400a8134  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a813b  lea     edx, [r9+20h]; void *
0x1400a813f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a8144  mov     rcx, [rsp+1C8h+var_B8]
0x1400a814c  mov     rax, [rcx]
0x1400a814f  mov     r11, [rax+18h]
0x1400a8153  mov     rdx, [r15+50h]
0x1400a8157  movzx   r9d, byte ptr [r15+49h]
0x1400a815c  movzx   r10d, byte ptr [r15+48h]
0x1400a8161  lea     rsi, [r15+28h]
0x1400a8165  cmp     qword ptr [r15+40h], 7
0x1400a816a  jbe     short loc_1400A8171
0x1400a816c  mov     r8, [rsi]
0x1400a816f  jmp     short loc_1400A8174
0x1400a8171  mov     r8, rsi
0x1400a8174  lea     rax, GUID_NULL
0x1400a817b  mov     [rsp+1C8h+var_198], rax
0x1400a8180  mov     [rsp+1C8h+var_1A0], rdx
0x1400a8185  mov     dword ptr [rsp+1C8h+var_1A8], r9d; unsigned int
0x1400a818a  mov     r9d, r10d
0x1400a818d  mov     rdx, r12
0x1400a8190  mov     rax, r11
0x1400a8193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a8198  mov     r12d, eax
0x1400a819b  test    eax, eax
0x1400a819d  jns     loc_1400A8295
0x1400a81a3  mov     ebx, eax
0x1400a81a5  btr     ebx, 1Ch
0x1400a81a9  mov     r9d, ebx
0x1400a81ac  lea     r8, aU_0; "%%%%%u"
0x1400a81b3  mov     r15d, 10h
0x1400a81b9  mov     edx, r15d
0x1400a81bc  lea     rcx, [rsp+1C8h+var_58]
0x1400a81c4  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400a81c9  mov     r9d, ebx
0x1400a81cc  lea     r8, a0x08x; "0x%08X"
0x1400a81d3  mov     edx, r15d
0x1400a81d6  lea     rcx, [rsp+1C8h+var_78]
0x1400a81de  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400a81e3  cmp     qword ptr [rsi+18h], 7
0x1400a81e8  jbe     short loc_1400A81ED
0x1400a81ea  mov     rsi, [rsi]
0x1400a81ed  mov     [rsp+1C8h+var_160], rsi
0x1400a81f2  cmp     qword ptr [r14+18h], 7
0x1400a81f7  jbe     short loc_1400A81FC
0x1400a81f9  mov     r14, [r14]
0x1400a81fc  mov     [rsp+1C8h+var_168], r14
0x1400a8201  mov     rcx, [rsp+1C8h+var_140]
0x1400a8209  mov     rcx, [rcx]
0x1400a820c  lea     rax, [rcx+480h]
0x1400a8213  mov     qword ptr [rsp+1C8h+var_174+4], rax
0x1400a8218  add     rcx, r15; this
0x1400a821b  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400a8220  mov     qword ptr [rsp+1C8h+FileSize], rax
0x1400a8228  lea     rax, [rsp+1C8h+var_160]
0x1400a822d  mov     [rsp+1C8h+var_180], rax; __int64
0x1400a8232  lea     rax, [rsp+1C8h+var_168]
0x1400a8237  mov     [rsp+1C8h+var_188], rax; __int64
0x1400a823c  lea     rax, [rsp+1C8h+var_78]
0x1400a8244  mov     [rsp+1C8h+var_190], rax; unsigned __int16 *
0x1400a8249  lea     rax, [rsp+1C8h+var_58]
0x1400a8251  mov     [rsp+1C8h+var_198], rax; unsigned __int16 *
0x1400a8256  lea     rax, [rsp+1C8h+var_174+4]
0x1400a825b  mov     [rsp+1C8h+var_1A0], rax; __int64
0x1400a8260  lea     rax, [rsp+1C8h+FileSize]
0x1400a8268  mov     [rsp+1C8h+var_1A8], rax; int
0x1400a826d  lea     rcx, MSVML_FAILED_TO_START_GUEST_COPY; struct _EVENT_DESCRIPTOR *
0x1400a8274  call    ??$VmEventWriteAndReport@PEBGPEBGAEAY0BA@GAEAY0BA@GPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG3AEAY0BA@G433@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort (&)[16],ushort (&)[16],ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort (&)[16],ushort (&)[16],ushort const * &&,ushort const * &&)
0x1400a8279  mov     rcx, [rsp+1C8h]; this
0x1400a8281  mov     r9d, r12d; char *
0x1400a8284  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a828b  mov     edx, 0DEh; void *
0x1400a8290  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a8295  mov     [rsp+1C8h+Overlapped.Internal], rdi
0x1400a829d  mov     [rsp+1C8h+Overlapped.InternalHigh], rdi
0x1400a82a5  mov     qword ptr [rsp+1C8h+Overlapped.10h], rdi
0x1400a82ad  mov     rax, [rsp+1C8h+var_118]
0x1400a82b5  mov     [rsp+1C8h+Overlapped.hEvent], rax
0x1400a82bd  mov     eax, [rsp+1C8h+var_C0]
0x1400a82c4  mov     [rsp+1C8h+NumberOfBytesTransferred], eax
0x1400a82cb  mov     [rsp+1C8h+var_178], 1
0x1400a82d3  lea     r9, [rsp+1C8h+Overlapped]; struct _OVERLAPPED *
0x1400a82db  lea     r8, [rsp+1C8h+NumberOfBytesTransferred]; unsigned int *
0x1400a82e3  mov     rdx, [rsp+1C8h+var_A8]; void *
0x1400a82eb  lea     rcx, [rsp+1C8h+var_120]; this
0x1400a82f3  call    ?Read@VmFile@Vml@@QEAAHPEAXAEAKPEAU_OVERLAPPED@@@Z; Vml::VmFile::Read(void *,ulong &,_OVERLAPPED *)
0x1400a82f8  mov     ecx, eax
0x1400a82fa  mov     qword ptr [rsp+1C8h+FileSize], rdi
0x1400a8302  mov     r9, rdi
0x1400a8305  mov     [rsp+1C8h+var_150], rdi
0x1400a830a  mov     r8d, edi
0x1400a830d  mov     dword ptr [rsp+1C8h+var_174], edi
0x1400a8311  mov     [rsp+1C8h+var_178], edi
0x1400a8315  mov     eax, edi
0x1400a8317  test    ecx, ecx
0x1400a8319  setz    al
0x1400a831c  mov     r12, qword ptr [rsp+1C8h+var_174+4]
0x1400a8321  test    eax, eax
0x1400a8323  jnz     loc_1400A84EE
0x1400a8329  cmp     [rsp+1C8h+NumberOfBytesTransferred], edi
0x1400a8330  ja      loc_1400A8571
0x1400a8336  mov     rcx, [rsp+1C8h+var_B8]
0x1400a833e  mov     rax, [rcx]
0x1400a8341  lea     rbx, GUID_NULL
0x1400a8348  mov     rdx, rbx
0x1400a834b  mov     rax, [rax+30h]
0x1400a834f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a8354  mov     r12d, eax
0x1400a8357  test    eax, eax
0x1400a8359  jns     loc_1400A8451
0x1400a835f  mov     ebx, eax
0x1400a8361  btr     ebx, 1Ch
0x1400a8365  mov     r9d, ebx
0x1400a8368  lea     r8, aU_0; "%%%%%u"
0x1400a836f  mov     r15d, 10h
0x1400a8375  mov     edx, r15d
0x1400a8378  lea     rcx, [rsp+1C8h+var_78]
0x1400a8380  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400a8385  mov     r9d, ebx
0x1400a8388  lea     r8, a0x08x; "0x%08X"
0x1400a838f  mov     edx, r15d
0x1400a8392  lea     rcx, [rsp+1C8h+var_58]
0x1400a839a  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400a839f  cmp     qword ptr [rsi+18h], 7
0x1400a83a4  jbe     short loc_1400A83A9
0x1400a83a6  mov     rsi, [rsi]
0x1400a83a9  mov     [rsp+1C8h+var_160], rsi
0x1400a83ae  cmp     qword ptr [r14+18h], 7
0x1400a83b3  jbe     short loc_1400A83B8
  ... truncated ...
```
