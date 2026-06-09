# CRasFilePlaceholderParams::ReadUsingRemoteStream(ISafeSaveHandleManager *,uchar *,uint,uint,unsigned __int64,unsigned __int64 *,ulong *,_OVERLAPPED *,bool const volatile &)

- ea: `0x1800647a4`
- end: `0x180064f01`
- name: `?ReadUsingRemoteStream@CRasFilePlaceholderParams@@QEAAJPEAUISafeSaveHandleManager@@PEAEII_KPEA_KPEAKPEAU_OVERLAPPED@@AED_N@Z`
- size: `1885`
- prototype: `__int64 __usercall@<rax>(CRasFilePlaceholderParams *__hidden this@<rcx>, struct ISafeSaveHandleManager *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, DWORD nNumberOfBytesToRead, unsigned __int64, unsigned __int64 *, unsigned int *, struct _OVERLAPPED *, const volatile bool *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021fd4`

## callees

- `0x1800083d0`
- `0x18000ddd4`
- `0x180022c90`
- `0x18002314c`
- `0x1800233b4`
- `0x180023730`
- `0x1800246dc`
- `0x18002ffd0`
- `0x180031cb0`
- `0x18003a89c`
- `0x18003aaa8`
- `0x18003b35c`
- `0x1800647a4`
- `0x180064f08`
- `0x18006507c`
- `0x18006519c`
- `0x18006d8cc`
- `0x180077128`
- `0x180079690`
- `0x18007ac54`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006493e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006493e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064947`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064947`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800649e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180064cfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800649e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180064cfa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180064b59`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180064b59`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180064b9e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180064b9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064eb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064eb4`

## string_xrefs

- `0x18006483c`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x180064901`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x1800647d3`: `ReadUsingRemoteStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CRasFilePlaceholderParams::ReadUsingRemoteStream(
        CRasFilePlaceholderParams *this,
        struct ISafeSaveHandleManager *a2,
        unsigned __int8 *a3,
        int a4,
        DWORD nNumberOfBytesToRead,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        unsigned int *a8,
        struct _OVERLAPPED *a9,
        bool *a10)
{
  struct ISafeSaveHandleManager *v10; // r12
  unsigned __int64 *v12; // rbx
  __int64 v13; // r13
  signed int ShouldContinue; // edi
  wil::details::in1diag3 *v15; // rcx
  __int64 v16; // rdx
  unsigned __int64 v17; // r15
  unsigned int v18; // r8d
  void *v19; // rcx
  unsigned int v20; // r10d
  char *v21; // rax
  unsigned __int64 v22; // rcx
  int v23; // eax
  unsigned __int64 v24; // rbx
  unsigned int v25; // r12d
  unsigned __int64 v26; // r13
  DWORD v27; // edx
  __int64 (__fastcall *v28)(struct ISafeSaveHandleManager *, _QWORD, struct IFileHandle **); // rdi
  wil::details::in1diag3 *v29; // rcx
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  int v32; // eax
  struct _OVERLAPPED *v33; // rcx
  const unsigned __int8 *v34; // r13
  BOOL v35; // eax
  BOOL OverlappedResult; // eax
  int v37; // eax
  wil::details::in1diag3 *v38; // rcx
  __int64 v39; // rdx
  rsize_t v40; // rdx
  rsize_t v41; // rdx
  DWORD v42; // r12d
  __int64 (__fastcall *v43)(struct ISafeSaveHandleManager *, struct IFileHandle **); // rbx
  int v44; // eax
  wil::details::in1diag3 *v45; // rcx
  __int64 v46; // rdx
  unsigned __int8 *v47; // rbx
  int v48; // eax
  int lpOverlapped; // [rsp+28h] [rbp-E0h]
  int lpOverlappeda; // [rsp+28h] [rbp-E0h]
  int lpOverlappedb; // [rsp+28h] [rbp-E0h]
  DWORD nNumberOfBytesToWrite[2]; // [rsp+48h] [rbp-C0h] BYREF
  DWORD NumberOfBytesTransferred[2]; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-B0h] BYREF
  struct IFileHandle *v56; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int64 v57; // [rsp+68h] [rbp-A0h]
  unsigned __int64 v58; // [rsp+70h] [rbp-98h] BYREF
  struct IFileHandle *v59; // [rsp+78h] [rbp-90h] BYREF
  void *v60; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v61[8]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v62; // [rsp+90h] [rbp-78h] BYREF
  __int64 v63; // [rsp+98h] [rbp-70h]
  int v64; // [rsp+B0h] [rbp-58h]
  _BYTE v65[8]; // [rsp+B8h] [rbp-50h] BYREF
  CRasFilePlaceholderParams *v66; // [rsp+C0h] [rbp-48h]
  _BYTE v67[128]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]
  unsigned __int8 *v70; // [rsp+168h] [rbp+60h] BYREF
  rsize_t SourceSize; // [rsp+170h] [rbp+68h] BYREF

  LODWORD(SourceSize) = a4;
  v70 = a3;
  v10 = a2;
  StreamLibTelemetry::WatchCurrentThread(v67, "ReadUsingRemoteStream");
  v12 = a7;
  *a7 = 0;
  v13 = nNumberOfBytesToRead;
  LODWORD(SourceSize) = nNumberOfBytesToRead;
  a7 = 0;
  hFile = 0;
  CRasFilePlaceholderParams::_GetParamsUnderLock(this, &v62, &a7, &hFile);
  ShouldContinue = v62 == 0 ? 0x8007000D : 0;
  v15 = retaddr;
  if ( !v62 )
  {
    v16 = 241;
LABEL_3:
    wil::details::in1diag3::_Log_Hr(
      v15,
      (void *)v16,
      (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
      (const char *)(unsigned int)ShouldContinue,
      lpOverlapped);
    goto LABEL_77;
  }
  v17 = a6;
  if ( !v64 )
  {
    v18 = (unsigned int)a7;
    if ( a6 >= (unsigned __int64)a7
      && (unsigned __int64 *)(a6 + v13) <= (unsigned __int64 *)((char *)a7 + (_QWORD)hFile) )
    {
      *v12 = (unsigned __int64)hFile + (_QWORD)a7 - a6;
      ShouldContinue = -2147024883;
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0xFB, v18, (const char *)0x8007000DLL, lpOverlapped);
      goto LABEL_77;
    }
  }
  v58 = 0;
  v57 = 0;
  v60 = 0;
  a7 = 0;
  ShouldContinue = ULongLongMult(0x100000u, 1u, (unsigned __int64 *)&a7);
  if ( ShouldContinue >= 0 )
    ShouldContinue = CTCoAllocPolicy::Alloc(v19, v20, (unsigned __int64)a7, &v60);
  v15 = retaddr;
  if ( ShouldContinue < 0 )
  {
    v16 = 261;
    goto LABEL_3;
  }
  LOBYTE(a7) = 0;
  v21 = (char *)this + 168;
  do
  {
    Microsoft::WRL::Wrappers::SRWLock::LockShared(v61, v21);
    v22 = *((_QWORD *)this + 22);
    if ( (unsigned int)v13 + v17 >= v22 && v17 < *((_QWORD *)this + 23) + v22 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)this + 25);
      ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
    }
    CRasFilePlaceholderParams::_StartPreBufferingIfNeeded(this, (struct RAS_FILE_PLACEHOLDER_PARAMS *)&v62, v10);
    Microsoft::WRL::Wrappers::SRWLock::LockShared(v65, (char *)this + 104);
    v23 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, bool))(*(_QWORD *)v63 + 48LL))(
            v63,
            v17,
            (unsigned int)v13,
            v64 != 1);
    ShouldContinue = v23;
    if ( v23 >= 0 )
    {
      if ( v57 && v58 <= v17 )
      {
        v66 = this;
        _InterlockedIncrement(&CRasFilePlaceholderParams::s_dwRemoteReadRefCount);
        CRasFilePlaceholderParams::s_wpLastRemoteRead = this;
        CRasFilePlaceholderParams::s_dwTickCountLastRemoteRead = GetTickCount();
        v24 = v58;
        v25 = v17 - v58;
        v26 = v57;
        if ( v64 && v25 + (unsigned int)SourceSize < v57 )
          v26 = v25 + (unsigned int)SourceSize;
        *(_QWORD *)NumberOfBytesTransferred = v58;
        nNumberOfBytesToWrite[0] = 0;
        ShouldContinue = (*(__int64 (__fastcall **)(__int64, unsigned __int64, void *, _QWORD))(*(_QWORD *)v62 + 24LL))(
                           v62,
                           v58,
                           v60,
                           (unsigned int)v26);
        v27 = nNumberOfBytesToWrite[0];
        LOBYTE(a7) = nNumberOfBytesToWrite[0] < v26;
        if ( ShouldContinue >= 0 )
        {
          ShouldContinue = CRasFilePlaceholderParams::s_ShouldContinue(*a10, this);
          v27 = nNumberOfBytesToWrite[0];
        }
        if ( ShouldContinue < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x149,
            (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
            (const char *)(unsigned int)ShouldContinue,
            (int)nNumberOfBytesToWrite);
LABEL_55:
          CRasFilePlaceholderParams::s_wpLastRemoteRead = this;
          CRasFilePlaceholderParams::s_dwTickCountLastRemoteRead = GetTickCount();
          _InterlockedDecrement(&CRasFilePlaceholderParams::s_dwRemoteReadRefCount);
          LODWORD(v13) = nNumberOfBytesToRead;
LABEL_71:
          v10 = a2;
          goto LABEL_72;
        }
        if ( v64 )
        {
          if ( v27 >= v25 )
          {
            v41 = v27 - v25;
            if ( (unsigned int)SourceSize < (unsigned int)v41 )
              v41 = (unsigned int)SourceSize;
            CRasFilePlaceholderParams::s_CopyAndAdvancePointers(
              (const unsigned __int8 *)v60 + v25,
              v41,
              &v70,
              &a6,
              (unsigned int *)&SourceSize,
              &nNumberOfBytesToRead,
              a8);
            v17 = a6;
          }
          goto LABEL_55;
        }
        v56 = 0;
        v28 = *(__int64 (__fastcall **)(struct ISafeSaveHandleManager *, _QWORD, struct IFileHandle **))(*(_QWORD *)a2 + 32LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v56);
        ShouldContinue = v28(a2, 0, &v56);
        if ( ShouldContinue >= 0 )
          ShouldContinue = CRasFilePlaceholderParams::s_ShouldContinue(*a10, this);
        v29 = retaddr;
        if ( ShouldContinue < 0 )
        {
          v30 = (unsigned int)ShouldContinue;
          v31 = 339;
LABEL_34:
          wil::details::in1diag3::_Log_Hr(
            v29,
            (void *)v31,
            (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
            (const char *)v30,
            (int)nNumberOfBytesToWrite);
LABEL_50:
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v56);
          goto LABEL_55;
        }
        hFile = 0;
        v32 = LockHandle(v56, &hFile);
        ShouldContinue = v32;
        v29 = retaddr;
        if ( v32 < 0 )
        {
          v30 = (unsigned int)v32;
          v31 = 343;
          goto LABEL_34;
        }
        v33 = a9;
        a9->Offset = v24;
        v33->OffsetHigh = NumberOfBytesTransferred[1];
        v34 = (const unsigned __int8 *)v60;
        v35 = WriteFile(hFile, v60, nNumberOfBytesToWrite[0], 0, v33);
        ShouldContinue = ResultFromWin32Bool(v35);
        if ( (int)(ShouldContinue + 0x80000000) < 0 || ShouldContinue == -2147023899 )
        {
          NumberOfBytesTransferred[0] = 0;
          OverlappedResult = GetOverlappedResult(hFile, a9, NumberOfBytesTransferred, 1);
          v37 = ResultFromWin32Bool(OverlappedResult);
          ShouldContinue = v37;
          v38 = retaddr;
          if ( v37 >= 0 )
          {
            _InterlockedCompareExchange64(
              (volatile signed __int64 *)this + 24,
              v24 + NumberOfBytesTransferred[0],
              *((_QWORD *)this + 24));
            v37 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v63 + 56LL))(
                    v63,
                    v58,
                    NumberOfBytesTransferred[0]);
            ShouldContinue = v37;
            v38 = retaddr;
            if ( v37 >= 0 )
            {
              if ( nNumberOfBytesToWrite[0] >= v25 )
              {
                v40 = nNumberOfBytesToWrite[0] - v25;
                if ( (unsigned int)SourceSize < (unsigned int)v40 )
                  v40 = (unsigned int)SourceSize;
                CRasFilePlaceholderParams::s_CopyAndAdvancePointers(
                  &v34[v25],
                  v40,
                  &v70,
                  &a6,
                  (unsigned int *)&SourceSize,
                  &nNumberOfBytesToRead,
                  a8);
                v17 = a6;
              }
              CRasFilePlaceholderParams::_UpdateCachePosition(this, v24, NumberOfBytesTransferred[0], 1);
              ShouldContinue = CRasFilePlaceholderParams::s_ShouldContinue(*a10, this);
              goto LABEL_47;
            }
            v39 = 359;
          }
          else
          {
            v39 = 352;
          }
          wil::details::in1diag3::_Log_Hr(
            v38,
            (void *)v39,
            (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
            (const char *)(unsigned int)v37,
            lpOverlappeda);
        }
LABEL_47:
        if ( ShouldContinue < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x173,
            (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
            (const char *)(unsigned int)ShouldContinue,
            lpOverlappeda);
        (*(void (__fastcall **)(struct IFileHandle *))(*(_QWORD *)v56 + 32LL))(v56);
        goto LABEL_50;
      }
      Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v61);
      if ( v57 )
        v42 = v58 - v17;
      else
        v42 = v13;
      v59 = 0;
      v43 = *(__int64 (__fastcall **)(struct ISafeSaveHandleManager *, struct IFileHandle **))(*(_QWORD *)a2 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v59);
      v44 = v43(a2, &v59);
      ShouldContinue = v44;
      v45 = retaddr;
      if ( v44 >= 0 )
      {
        hFile = 0;
        v44 = LockHandle(v59, &hFile);
        ShouldContinue = v44;
        v45 = retaddr;
        if ( v44 >= 0 )
        {
          NumberOfBytesTransferred[0] = 0;
          v47 = v70;
          v48 = ReadFromFile(hFile, a9, v42, NumberOfBytesTransferred);
          ShouldContinue = v48;
          if ( v48 >= 0 )
          {
            LOBYTE(a7) = NumberOfBytesTransferred[0] < v42;
            CRasFilePlaceholderParams::_UpdateCachePosition(this, v17, NumberOfBytesTransferred[0], 1);
            v17 += NumberOfBytesTransferred[0];
            a6 = v17;
            v70 = &v47[NumberOfBytesTransferred[0]];
            LODWORD(SourceSize) = SourceSize - NumberOfBytesTransferred[0];
            LODWORD(v13) = v13 - NumberOfBytesTransferred[0];
            nNumberOfBytesToRead = v13;
            *a8 += NumberOfBytesTransferred[0];
            ShouldContinue = CRasFilePlaceholderParams::s_ShouldContinue(*a10, this);
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x12D,
              (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
              (const char *)(unsigned int)v48,
              lpOverlappedb);
          }
          if ( ShouldContinue < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x136,
              (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
              (const char *)(unsigned int)ShouldContinue,
              lpOverlappedb);
          (*(void (__fastcall **)(struct IFileHandle *))(*(_QWORD *)v59 + 32LL))(v59);
          goto LABEL_70;
        }
        v46 = 296;
      }
      else
      {
        v46 = 292;
      }
      wil::details::in1diag3::_Log_Hr(
        v45,
        (void *)v46,
        (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
        (const char *)(unsigned int)v44,
        (int)&v58);
LABEL_70:
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v59);
      goto LABEL_71;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
      (const char *)(unsigned int)v23,
      (int)&v58);
LABEL_72:
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v65);
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v61);
    if ( ShouldContinue < 0 )
      break;
    if ( (_BYTE)a7 )
      break;
    v21 = (char *)this + 168;
  }
  while ( (_DWORD)v13 );
  CoTaskMemFree(v60);
  if ( ShouldContinue >= 0 )
    CRasFilePlaceholderParams::SetLocallyCompleteIfAppropriate(this, v10, -1, 0);
LABEL_77:
  RAS_FILE_PLACEHOLDER_PARAMS::~RAS_FILE_PLACEHOLDER_PARAMS((RAS_FILE_PLACEHOLDER_PARAMS *)&v62);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v67);
  return (unsigned int)ShouldContinue;
}

```

## disassembly

```asm
0x1800647a4  mov     rax, rsp
0x1800647a7  mov     [rax+8], rbx
0x1800647ab  mov     [rax+20h], r9d
0x1800647af  mov     [rax+18h], r8
0x1800647b3  mov     [rax+10h], rdx
0x1800647b7  push    rbp
0x1800647b8  push    rsi
0x1800647b9  push    rdi
0x1800647ba  push    r12
0x1800647bc  push    r13
0x1800647be  push    r14
0x1800647c0  push    r15
0x1800647c2  lea     rbp, [rax-48h]
0x1800647c6  sub     rsp, 110h
0x1800647cd  mov     r12, rdx
0x1800647d0  mov     r14, rcx
0x1800647d3  lea     rdx, aReadusingremot; "ReadUsingRemoteStream"
0x1800647da  lea     rcx, [rbp+40h+var_80]
0x1800647de  call    ?WatchCurrentThread@StreamLibTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; StreamLibTelemetry::WatchCurrentThread(char const *)
0x1800647e3  nop
0x1800647e4  xor     esi, esi
0x1800647e6  mov     rbx, [rbp+40h+arg_30]
0x1800647ed  mov     [rbx], rsi
0x1800647f0  mov     r13d, [rbp+40h+nNumberOfBytesToRead]
0x1800647f4  mov     dword ptr [rbp+40h+SourceSize], r13d
0x1800647f8  mov     [rbp+40h+arg_30], rsi
0x1800647ff  mov     [rsp+140h+hFile], rsi
0x180064804  lea     r9, [rsp+140h+hFile]
0x180064809  lea     r8, [rbp+40h+arg_30]
0x180064810  lea     rdx, [rbp+40h+var_B8]
0x180064814  mov     rcx, r14
0x180064817  call    ?_GetParamsUnderLock@CRasFilePlaceholderParams@@AEAA?AURAS_FILE_PLACEHOLDER_PARAMS@@PEA_K0@Z; CRasFilePlaceholderParams::_GetParamsUnderLock(unsigned __int64 *,unsigned __int64 *)
0x18006481c  nop
0x18006481d  mov     rax, [rbp+40h+var_B8]
0x180064821  neg     rax
0x180064824  sbb     edi, edi
0x180064826  not     edi
0x180064828  mov     r9d, 8007000Dh; char *
0x18006482e  and     edi, r9d
0x180064831  mov     rcx, [rbp+48h]; this
0x180064835  jge     short loc_180064850
0x180064837  mov     edx, 0F1h; void *
0x18006483c  lea     r8, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x180064843  mov     r9d, edi; char *
0x180064846  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006484b  jmp     loc_180064ED1
0x180064850  mov     r15, [rbp+40h+arg_28]
0x180064854  cmp     [rbp+40h+var_98], esi
0x180064857  jnz     short loc_180064896
0x180064859  mov     r8, [rbp+40h+arg_30]; unsigned int
0x180064860  cmp     r15, r8
0x180064863  jb      short loc_180064896
0x180064865  lea     rcx, [r15+r13]
0x180064869  mov     rdx, [rsp+140h+hFile]
0x18006486e  lea     rax, [rdx+r8]
0x180064872  cmp     rcx, rax
0x180064875  ja      short loc_180064896
0x180064877  sub     rdx, r15
0x18006487a  add     rdx, r8
0x18006487d  mov     [rbx], rdx
0x180064880  mov     edi, r9d
0x180064883  mov     rcx, [rbp+48h]; this
0x180064887  mov     edx, 0FBh; void *
0x18006488c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180064891  jmp     loc_180064ED1
0x180064896  xor     ebx, ebx
0x180064898  mov     [rsp+140h+var_D8], rbx
0x18006489d  mov     [rsp+140h+var_E0], rbx
0x1800648a2  mov     [rsp+140h+var_C8], rbx
0x1800648a7  mov     [rbp+40h+arg_30], rbx
0x1800648ae  lea     r8, [rbp+40h+arg_30]; unsigned __int64 *
0x1800648b5  lea     r10d, [rbx+1]
0x1800648b9  mov     edx, r10d; unsigned __int64
0x1800648bc  mov     ecx, 100000h; unsigned __int64
0x1800648c1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800648c6  mov     edi, eax
0x1800648c8  test    eax, eax
0x1800648ca  js      short loc_1800648E2
0x1800648cc  lea     r9, [rsp+140h+var_C8]; void **
0x1800648d1  mov     r8, [rbp+40h+arg_30]; unsigned __int64
0x1800648d8  mov     edx, r10d; unsigned int
0x1800648db  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800648e0  mov     edi, eax
0x1800648e2  mov     rcx, [rbp+48h]
0x1800648e6  test    edi, edi
0x1800648e8  jns     short loc_1800648F4
0x1800648ea  mov     edx, 105h
0x1800648ef  jmp     loc_18006483C
0x1800648f4  mov     byte ptr [rbp+40h+arg_30], bl
0x1800648fa  lea     rax, [r14+0A8h]
0x180064901  lea     rsi, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x180064908  mov     rdx, rax
0x18006490b  lea     rcx, [rbp+40h+var_C0]
0x18006490f  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180064914  nop
0x180064915  mov     edi, r13d
0x180064918  mov     rcx, [r14+0B0h]
0x18006491f  lea     rax, [rdi+r15]
0x180064923  cmp     rax, rcx
0x180064926  jb      short loc_18006494F
0x180064928  add     rcx, [r14+0B8h]
0x18006492f  cmp     r15, rcx
0x180064932  jnb     short loc_18006494F
0x180064934  lea     rbx, [r14+0C8h]
0x18006493b  mov     rcx, rbx; SRWLock
0x18006493e  call    cs:__imp_AcquireSRWLockExclusive
0x180064944  mov     rcx, rbx; SRWLock
0x180064947  call    cs:__imp_ReleaseSRWLockExclusive
0x18006494d  xor     ebx, ebx
0x18006494f  mov     r8, r12; struct ISafeSaveHandleManager *
0x180064952  lea     rdx, [rbp+40h+var_B8]; struct RAS_FILE_PLACEHOLDER_PARAMS *
0x180064956  mov     rcx, r14; this
0x180064959  call    ?_StartPreBufferingIfNeeded@CRasFilePlaceholderParams@@AEAAXAEAURAS_FILE_PLACEHOLDER_PARAMS@@PEAUISafeSaveHandleManager@@@Z; CRasFilePlaceholderParams::_StartPreBufferingIfNeeded(RAS_FILE_PLACEHOLDER_PARAMS &,ISafeSaveHandleManager *)
0x18006495e  lea     rdx, [r14+68h]
0x180064962  lea     rcx, [rbp+40h+var_90]
0x180064966  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18006496b  nop
0x18006496c  mov     rcx, [rbp+40h+var_B0]
0x180064970  mov     rax, [rcx]
0x180064973  mov     r9d, ebx
0x180064976  cmp     [rbp+40h+var_98], 1
0x18006497a  setnz   r9b
0x18006497e  lea     rdx, [rsp+140h+var_E0]
0x180064983  mov     [rsp+140h+lpNumberOfBytesTransferred], rdx
0x180064988  lea     rdx, [rsp+140h+var_D8]
0x18006498d  mov     [rsp+140h+lpOverlapped], rdx; int
0x180064992  mov     r8, rdi
0x180064995  mov     rdx, r15
0x180064998  mov     rax, [rax+30h]
0x18006499c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800649a1  mov     edi, eax
0x1800649a3  mov     rcx, [rbp+48h]; this
0x1800649a7  test    eax, eax
0x1800649a9  jns     short loc_1800649C0
0x1800649ab  mov     r9d, eax; char *
0x1800649ae  mov     r8, rsi; unsigned int
0x1800649b1  mov     edx, 115h; void *
0x1800649b6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800649bb  jmp     loc_180064E80
0x1800649c0  cmp     [rsp+140h+var_E0], rbx
0x1800649c5  jz      loc_180064D18
0x1800649cb  cmp     [rsp+140h+var_D8], r15
0x1800649d0  ja      loc_180064D18
0x1800649d6  mov     [rbp+40h+var_88], r14
0x1800649da  lock inc cs:?s_dwRemoteReadRefCount@CRasFilePlaceholderParams@@0JC; long volatile CRasFilePlaceholderParams::s_dwRemoteReadRefCount
0x1800649e1  mov     cs:?s_wpLastRemoteRead@CRasFilePlaceholderParams@@0PEAV1@EA, r14; CRasFilePlaceholderParams * CRasFilePlaceholderParams::s_wpLastRemoteRead
0x1800649e8  call    cs:__imp_GetTickCount
0x1800649ee  mov     cs:?s_dwTickCountLastRemoteRead@CRasFilePlaceholderParams@@0KA, eax; ulong CRasFilePlaceholderParams::s_dwTickCountLastRemoteRead
0x1800649f4  mov     r12d, r15d
0x1800649f7  mov     rbx, [rsp+140h+var_D8]
0x1800649fc  sub     r12d, ebx
0x1800649ff  mov     r13, [rsp+140h+var_E0]
0x180064a04  cmp     [rbp+40h+var_98], 0
0x180064a08  jz      short loc_180064A17
0x180064a0a  mov     ecx, dword ptr [rbp+40h+SourceSize]
0x180064a0d  add     ecx, r12d
0x180064a10  cmp     rcx, r13
0x180064a13  cmovb   r13, rcx
0x180064a17  mov     qword ptr [rsp+140h+NumberOfBytesTransferred], rbx
0x180064a1c  mov     [rsp+140h+nNumberOfBytesToWrite], 0
0x180064a24  mov     rcx, [rbp+40h+var_B8]
0x180064a28  mov     rax, [rcx]
0x180064a2b  mov     r9d, r13d
0x180064a2e  lea     rdx, [rsp+140h+nNumberOfBytesToWrite]
0x180064a33  mov     [rsp+140h+lpOverlapped], rdx; int
0x180064a38  mov     r8, [rsp+140h+var_C8]
0x180064a3d  mov     rdx, rbx
0x180064a40  mov     rax, [rax+18h]
0x180064a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a49  mov     edi, eax
0x180064a4b  mov     edx, [rsp+140h+nNumberOfBytesToWrite]
0x180064a4f  cmp     rdx, r13
0x180064a52  setb    byte ptr [rbp+40h+arg_30]
0x180064a59  test    eax, eax
0x180064a5b  js      short loc_180064A74
0x180064a5d  mov     rdx, r14; struct CRasFilePlaceholderParams *
0x180064a60  mov     rax, [rbp+40h+arg_48]
0x180064a67  mov     cl, [rax]; bool
0x180064a69  call    ?s_ShouldContinue@CRasFilePlaceholderParams@@SAJ_NPEAV1@@Z; CRasFilePlaceholderParams::s_ShouldContinue(bool,CRasFilePlaceholderParams *)
0x180064a6e  mov     edi, eax
0x180064a70  mov     edx, [rsp+140h+nNumberOfBytesToWrite]
0x180064a74  mov     rcx, [rbp+48h]; this
0x180064a78  test    edi, edi
0x180064a7a  jns     short loc_180064A91
0x180064a7c  mov     r9d, edi; char *
0x180064a7f  mov     r8, rsi; unsigned int
0x180064a82  mov     edx, 149h; void *
0x180064a87  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180064a8c  jmp     loc_180064CF3
0x180064a91  cmp     [rbp+40h+var_98], 0
0x180064a95  jnz     loc_180064CAD
0x180064a9b  mov     [rsp+140h+var_E8], 0
0x180064aa4  mov     r13, [rbp+40h+arg_8]
0x180064aa8  mov     rax, [r13+0]
0x180064aac  mov     rdi, [rax+20h]
0x180064ab0  lea     rcx, [rsp+140h+var_E8]
0x180064ab5  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180064aba  lea     r8, [rsp+140h+var_E8]
0x180064abf  xor     edx, edx
0x180064ac1  mov     rcx, r13
0x180064ac4  mov     rax, rdi
0x180064ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064acc  mov     edi, eax
0x180064ace  test    eax, eax
0x180064ad0  js      short loc_180064AE5
0x180064ad2  mov     rdx, r14; struct CRasFilePlaceholderParams *
0x180064ad5  mov     rax, [rbp+40h+arg_48]
0x180064adc  mov     cl, [rax]; bool
0x180064ade  call    ?s_ShouldContinue@CRasFilePlaceholderParams@@SAJ_NPEAV1@@Z; CRasFilePlaceholderParams::s_ShouldContinue(bool,CRasFilePlaceholderParams *)
0x180064ae3  mov     edi, eax
0x180064ae5  mov     rcx, [rbp+48h]
0x180064ae9  test    edi, edi
0x180064aeb  jns     short loc_180064AF7
0x180064aed  mov     r9d, edi
0x180064af0  mov     edx, 153h
0x180064af5  jmp     short loc_180064B21
0x180064af7  mov     [rsp+140h+hFile], 0
0x180064b00  lea     rdx, [rsp+140h+hFile]; void **
0x180064b05  mov     rcx, [rsp+140h+var_E8]; struct IFileHandle *
0x180064b0a  call    ?LockHandle@@YAJPEAUIFileHandle@@PEAPEAX@Z; LockHandle(IFileHandle *,void * *)
0x180064b0f  mov     edi, eax
0x180064b11  mov     rcx, [rbp+48h]; this
0x180064b15  test    eax, eax
0x180064b17  jns     short loc_180064B2E
0x180064b19  mov     r9d, eax; char *
0x180064b1c  mov     edx, 157h; void *
0x180064b21  mov     r8, rsi; unsigned int
0x180064b24  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180064b29  jmp     loc_180064CA1
0x180064b2e  mov     rcx, [rbp+40h+arg_40]
0x180064b35  mov     [rcx+10h], ebx
0x180064b38  mov     eax, [rsp+140h+NumberOfBytesTransferred+4]
0x180064b3c  mov     [rcx+14h], eax
0x180064b3f  mov     [rsp+140h+lpOverlapped], rcx; int
0x180064b44  xor     r9d, r9d; lpNumberOfBytesWritten
0x180064b47  mov     r8d, [rsp+140h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180064b4c  mov     r13, [rsp+140h+var_C8]
0x180064b51  mov     rdx, r13; lpBuffer
0x180064b54  mov     rcx, [rsp+140h+hFile]; hFile
0x180064b59  call    cs:__imp_WriteFile
0x180064b5f  mov     ecx, eax; int
0x180064b61  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180064b66  mov     edi, eax
0x180064b68  mov     ecx, 80000000h
0x180064b6d  add     eax, ecx
0x180064b6f  test    ecx, eax
0x180064b71  jnz     short loc_180064B7F
0x180064b73  cmp     edi, 800703E5h
0x180064b79  jnz     loc_180064C77
0x180064b7f  mov     [rsp+140h+NumberOfBytesTransferred], 0
0x180064b87  mov     r9d, 1; bWait
0x180064b8d  lea     r8, [rsp+140h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180064b92  mov     rdx, [rbp+40h+arg_40]; lpOverlapped
0x180064b99  mov     rcx, [rsp+140h+hFile]; hFile
0x180064b9e  call    cs:__imp_GetOverlappedResult
0x180064ba4  mov     ecx, eax; int
0x180064ba6  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180064bab  mov     edi, eax
0x180064bad  mov     rcx, [rbp+48h]
0x180064bb1  test    eax, eax
0x180064bb3  jns     short loc_180064BBC
0x180064bb5  mov     edx, 160h
0x180064bba  jmp     short loc_180064BFC
0x180064bbc  mov     ecx, [rsp+140h+NumberOfBytesTransferred]
0x180064bc0  add     rcx, rbx
0x180064bc3  mov     rax, [r14+0C0h]
0x180064bca  lock cmpxchg [r14+0C0h], rcx
0x180064bd3  mov     rcx, [rbp+40h+var_B0]
0x180064bd7  mov     rax, [rcx]
0x180064bda  mov     r8d, [rsp+140h+NumberOfBytesTransferred]
0x180064bdf  mov     rdx, [rsp+140h+var_D8]
0x180064be4  mov     rax, [rax+38h]
0x180064be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064bed  mov     edi, eax
0x180064bef  mov     rcx, [rbp+48h]; this
0x180064bf3  test    eax, eax
0x180064bf5  jns     short loc_180064C09
0x180064bf7  mov     edx, 167h; void *
0x180064bfc  mov     r8, rsi; unsigned int
0x180064bff  mov     r9d, eax; char *
0x180064c02  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180064c07  jmp     short loc_180064C77
0x180064c09  mov     edx, [rsp+140h+nNumberOfBytesToWrite]
0x180064c0d  cmp     edx, r12d
0x180064c10  jb      short loc_180064C51
0x180064c12  sub     edx, r12d
0x180064c15  cmp     dword ptr [rbp+40h+SourceSize], edx
0x180064c18  cmovb   edx, dword ptr [rbp+40h+SourceSize]; SourceSize
0x180064c1c  mov     ecx, r12d
0x180064c1f  add     rcx, r13; Source
0x180064c22  mov     rax, [rbp+40h+arg_38]
0x180064c29  mov     [rsp+30h], rax; unsigned int *
0x180064c2e  lea     rax, [rbp+40h+nNumberOfBytesToRead]
0x180064c32  mov     [rsp+140h+lpNumberOfBytesTransferred], rax; unsigned int *
0x180064c37  lea     rax, [rbp+40h+SourceSize]
0x180064c3b  mov     [rsp+140h+lpOverlapped], rax; int
0x180064c40  lea     r9, [rbp+40h+arg_28]; unsigned __int64 *
0x180064c44  lea     r8, [rbp+40h+arg_10]; unsigned __int8 **
0x180064c48  call    ?s_CopyAndAdvancePointers@CRasFilePlaceholderParams@@CAXPEBEKPEAPEAEPEA_KPEAI3PEAK@Z; CRasFilePlaceholderParams::s_CopyAndAdvancePointers(uchar const *,ulong,uchar * *,unsigned __int64 *,uint *,uint *,ulong *)
0x180064c4d  mov     r15, [rbp+40h+arg_28]
  ... truncated ...
```
