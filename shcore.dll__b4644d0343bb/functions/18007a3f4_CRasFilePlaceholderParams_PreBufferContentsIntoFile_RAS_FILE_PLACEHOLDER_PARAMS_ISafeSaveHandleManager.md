# CRasFilePlaceholderParams::_PreBufferContentsIntoFile(RAS_FILE_PLACEHOLDER_PARAMS &,ISafeSaveHandleManager *)

- ea: `0x18007a3f4`
- end: `0x18007a6ee`
- name: `?_PreBufferContentsIntoFile@CRasFilePlaceholderParams@@AEAAJAEAURAS_FILE_PLACEHOLDER_PARAMS@@PEAUISafeSaveHandleManager@@@Z`
- size: `762`
- prototype: `__int64 __fastcall(CRasFilePlaceholderParams *__hidden this, struct RAS_FILE_PLACEHOLDER_PARAMS *, struct ISafeSaveHandleManager *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800792d0`

## callees

- `0x1800083d0`
- `0x18000ddd4`
- `0x180011ce0`
- `0x180011cfc`
- `0x18001c82c`
- `0x180023730`
- `0x180031cb0`
- `0x18003a89c`
- `0x18003aaa8`
- `0x18003b35c`
- `0x18006519c`
- `0x180079690`
- `0x18007a3f4`
- `0x18007a8b8`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007a45a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007a45a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a66f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a66f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007a506`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007a67d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007a506`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007a67d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007a5ce`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007a5ce`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18007a602`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18007a602`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRasFilePlaceholderParams::_PreBufferContentsIntoFile(
        CRasFilePlaceholderParams *this,
        struct RAS_FILE_PLACEHOLDER_PARAMS *a2,
        struct ISafeSaveHandleManager *a3)
{
  int Error; // ebx
  void *v7; // rcx
  void *v8; // rsi
  __int64 (__fastcall *v9)(struct ISafeSaveHandleManager *, _QWORD, struct IFileHandle **); // rbx
  BOOL v10; // eax
  BOOL OverlappedResult; // eax
  struct IFileHandle *v13; // [rsp+30h] [rbp-29h] BYREF
  LPCVOID lpBuffer; // [rsp+38h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int64 v17; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v18[8]; // [rsp+58h] [rbp-1h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp+7h] BYREF
  CRasFilePlaceholderParams *v20; // [rsp+80h] [rbp+27h]
  unsigned __int64 NumberOfBytesTransferred; // [rsp+C8h] [rbp+6Fh] BYREF
  int v22; // [rsp+D8h] [rbp+7Fh] BYREF

  v16 = 0;
  Error = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)a2 + 1) + 24LL))(
            *((_QWORD *)a2 + 1),
            &v16);
  if ( Error >= 0 )
  {
    memset(&Overlapped, 0, sizeof(Overlapped));
    Overlapped.hEvent = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( Overlapped.hEvent || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      lpBuffer = 0;
      NumberOfBytesTransferred = 0;
      Error = ULongLongMult(0x100000u, 1u, &NumberOfBytesTransferred);
      if ( Error >= 0 )
      {
        Error = CTCoAllocPolicy::Alloc(v7, 1u, NumberOfBytesTransferred, (void **)&lpBuffer);
        while ( Error >= 0 )
        {
          Microsoft::WRL::Wrappers::SRWLock::LockShared(v18, (char *)this + 104);
          v17 = 0;
          Error = CRasFilePlaceholderParams::_WaitForNextPreBufferingRangeAndLock(this, a2, v16, &v17);
          if ( Error >= 0 )
          {
            v20 = this;
            _InterlockedIncrement(&CRasFilePlaceholderParams::s_dwRemoteReadRefCount);
            CRasFilePlaceholderParams::s_wpLastRemoteRead = this;
            CRasFilePlaceholderParams::s_dwTickCountLastRemoteRead = GetTickCount();
            v8 = (void *)*((_QWORD *)this + 22);
            v22 = 0;
            Error = (*(__int64 (__fastcall **)(_QWORD, void *, LPCVOID, _QWORD, int *))(**(_QWORD **)a2 + 24LL))(
                      *(_QWORD *)a2,
                      v8,
                      lpBuffer,
                      *((unsigned int *)this + 46),
                      &v22);
            if ( Error >= 0 )
            {
              v13 = 0;
              v9 = *(__int64 (__fastcall **)(struct ISafeSaveHandleManager *, _QWORD, struct IFileHandle **))(*(_QWORD *)a3 + 32LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v13);
              Error = v9(a3, 0, &v13);
              if ( Error >= 0 )
              {
                hFile = 0;
                Error = LockHandle(v13, &hFile);
                if ( Error >= 0 )
                {
                  LODWORD(NumberOfBytesTransferred) = 0;
                  Overlapped.Pointer = v8;
                  v10 = WriteFile(hFile, lpBuffer, *((_DWORD *)this + 46), 0, &Overlapped);
                  Error = ResultFromWin32Bool(v10);
                  if ( (int)(Error + 0x80000000) < 0 || Error == -2147023899 )
                  {
                    OverlappedResult = GetOverlappedResult(hFile, &Overlapped, (LPDWORD)&NumberOfBytesTransferred, 1);
                    Error = ResultFromWin32Bool(OverlappedResult);
                  }
                  (*(void (__fastcall **)(struct IFileHandle *))(*(_QWORD *)v13 + 32LL))(v13);
                  if ( Error >= 0 )
                  {
                    CRasFilePlaceholderParams::_UpdateCachePosition(
                      this,
                      v17,
                      *((_QWORD *)this + 22) + (unsigned int)NumberOfBytesTransferred - v17,
                      0);
                    Error = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a2 + 1) + 56LL))(
                              *((_QWORD *)a2 + 1),
                              *((_QWORD *)this + 22),
                              (unsigned int)NumberOfBytesTransferred);
                  }
                }
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v13);
            }
            ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
            CRasFilePlaceholderParams::s_wpLastRemoteRead = this;
            CRasFilePlaceholderParams::s_dwTickCountLastRemoteRead = GetTickCount();
            _InterlockedDecrement(&CRasFilePlaceholderParams::s_dwRemoteReadRefCount);
          }
          Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v18);
        }
      }
      SafeCloseHandle(&Overlapped.hEvent);
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&lpBuffer);
    }
  }
  if ( Error == -2147024858 )
  {
    Error = 0;
    CRasFilePlaceholderParams::SetLocallyCompleteIfAppropriate(this, a3, -1, 0);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18007a3f4  mov     [rsp-8+arg_0], rbx
0x18007a3f9  mov     [rsp-8+arg_10], rsi
0x18007a3fe  push    rbp
0x18007a3ff  push    rdi
0x18007a400  push    r12
0x18007a402  push    r14
0x18007a404  push    r15
0x18007a406  lea     rbp, [rsp-37h]
0x18007a40b  sub     rsp, 90h
0x18007a412  mov     r15, r8
0x18007a415  mov     r14, rdx
0x18007a418  mov     rdi, rcx
0x18007a41b  mov     [rbp+57h+var_68], 0
0x18007a423  mov     rcx, [rdx+8]
0x18007a427  mov     rax, [rcx]
0x18007a42a  lea     rdx, [rbp+57h+var_68]
0x18007a42e  mov     rax, [rax+18h]
0x18007a432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a437  mov     ebx, eax
0x18007a439  test    eax, eax
0x18007a43b  js      loc_18007A6B4
0x18007a441  xorps   xmm0, xmm0
0x18007a444  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18007a448  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18007a44c  xor     edx, edx; lpName
0x18007a44e  xor     ecx, ecx; lpEventAttributes
0x18007a450  mov     r9d, 1F0003h; dwDesiredAccess
0x18007a456  lea     r8d, [rdx+1]; dwFlags
0x18007a45a  call    cs:__imp_CreateEventExW
0x18007a460  mov     [rbp+57h+Overlapped.hEvent], rax
0x18007a464  test    rax, rax
0x18007a467  jnz     short loc_18007A478
0x18007a469  call    ResultFromKnownLastError
0x18007a46e  mov     ebx, eax
0x18007a470  test    eax, eax
0x18007a472  js      loc_18007A6B4
0x18007a478  mov     [rbp+57h+lpBuffer], 0
0x18007a480  mov     [rbp+57h+NumberOfBytesTransferred], 0
0x18007a488  lea     r8, [rbp+57h+NumberOfBytesTransferred]; unsigned __int64 *
0x18007a48c  mov     edx, 1; unsigned __int64
0x18007a491  mov     ecx, 100000h; unsigned __int64
0x18007a496  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007a49b  mov     ebx, eax
0x18007a49d  test    eax, eax
0x18007a49f  js      loc_18007A6A1
0x18007a4a5  lea     r9, [rbp+57h+lpBuffer]; void **
0x18007a4a9  mov     r8, [rbp+57h+NumberOfBytesTransferred]; unsigned __int64
0x18007a4ad  mov     edx, 1; unsigned int
0x18007a4b2  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18007a4b7  mov     ebx, eax
0x18007a4b9  test    eax, eax
0x18007a4bb  js      loc_18007A6A1
0x18007a4c1  lea     rdx, [rdi+68h]
0x18007a4c5  lea     rcx, [rbp+57h+var_58]
0x18007a4c9  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18007a4ce  nop
0x18007a4cf  mov     [rbp+57h+var_60], 0
0x18007a4d7  lea     r9, [rbp+57h+var_60]; unsigned __int64 *
0x18007a4db  mov     r8, [rbp+57h+var_68]; unsigned __int64
0x18007a4df  mov     rdx, r14; struct RAS_FILE_PLACEHOLDER_PARAMS *
0x18007a4e2  mov     rcx, rdi; this
0x18007a4e5  call    ?_WaitForNextPreBufferingRangeAndLock@CRasFilePlaceholderParams@@AEAAJAEBURAS_FILE_PLACEHOLDER_PARAMS@@_KPEA_K@Z; CRasFilePlaceholderParams::_WaitForNextPreBufferingRangeAndLock(RAS_FILE_PLACEHOLDER_PARAMS const &,unsigned __int64,unsigned __int64 *)
0x18007a4ea  mov     ebx, eax
0x18007a4ec  test    eax, eax
0x18007a4ee  js      loc_18007A690
0x18007a4f4  mov     [rbp+57h+var_30], rdi
0x18007a4f8  lock inc cs:?s_dwRemoteReadRefCount@CRasFilePlaceholderParams@@0JC; long volatile CRasFilePlaceholderParams::s_dwRemoteReadRefCount
0x18007a4ff  mov     cs:?s_wpLastRemoteRead@CRasFilePlaceholderParams@@0PEAV1@EA, rdi; CRasFilePlaceholderParams * CRasFilePlaceholderParams::s_wpLastRemoteRead
0x18007a506  call    cs:__imp_GetTickCount
0x18007a50c  mov     cs:?s_dwTickCountLastRemoteRead@CRasFilePlaceholderParams@@0KA, eax; ulong CRasFilePlaceholderParams::s_dwTickCountLastRemoteRead
0x18007a512  mov     rsi, [rdi+0B0h]
0x18007a519  mov     [rbp+57h+arg_18], 0
0x18007a520  mov     rcx, [r14]
0x18007a523  mov     rax, [rcx]
0x18007a526  lea     rdx, [rbp+57h+arg_18]
0x18007a52a  mov     [rsp+0B0h+lpOverlapped], rdx
0x18007a52f  mov     r9d, [rdi+0B8h]
0x18007a536  mov     r8, [rbp+57h+lpBuffer]
0x18007a53a  mov     rdx, rsi
0x18007a53d  mov     rax, [rax+18h]
0x18007a541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a546  mov     ebx, eax
0x18007a548  test    eax, eax
0x18007a54a  js      loc_18007A668
0x18007a550  mov     [rbp+57h+var_80], 0
0x18007a558  mov     rax, [r15]
0x18007a55b  mov     rbx, [rax+20h]
0x18007a55f  lea     rcx, [rbp+57h+var_80]
0x18007a563  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007a568  lea     r8, [rbp+57h+var_80]
0x18007a56c  xor     edx, edx
0x18007a56e  mov     rcx, r15
0x18007a571  mov     rax, rbx
0x18007a574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a579  mov     ebx, eax
0x18007a57b  test    eax, eax
0x18007a57d  js      loc_18007A65F
0x18007a583  mov     [rbp+57h+hFile], 0
0x18007a58b  lea     rdx, [rbp+57h+hFile]; void **
0x18007a58f  mov     rcx, [rbp+57h+var_80]; struct IFileHandle *
0x18007a593  call    ?LockHandle@@YAJPEAUIFileHandle@@PEAPEAX@Z; LockHandle(IFileHandle *,void * *)
0x18007a598  mov     ebx, eax
0x18007a59a  test    eax, eax
0x18007a59c  js      loc_18007A65F
0x18007a5a2  mov     dword ptr [rbp+57h+NumberOfBytesTransferred], 0
0x18007a5a9  mov     dword ptr [rbp+57h+Overlapped.10h], esi
0x18007a5ac  sar     rsi, 20h
0x18007a5b0  mov     dword ptr [rbp+57h+Overlapped.10h+4], esi
0x18007a5b3  lea     rax, [rbp+57h+Overlapped]
0x18007a5b7  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x18007a5bc  xor     r9d, r9d; lpNumberOfBytesWritten
0x18007a5bf  mov     r8d, [rdi+0B8h]; nNumberOfBytesToWrite
0x18007a5c6  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x18007a5ca  mov     rcx, [rbp+57h+hFile]; hFile
0x18007a5ce  call    cs:__imp_WriteFile
0x18007a5d4  mov     ecx, eax; int
0x18007a5d6  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18007a5db  mov     ebx, eax
0x18007a5dd  mov     ecx, 80000000h
0x18007a5e2  add     eax, ecx
0x18007a5e4  test    ecx, eax
0x18007a5e6  jnz     short loc_18007A5F0
0x18007a5e8  cmp     ebx, 800703E5h
0x18007a5ee  jnz     short loc_18007A611
0x18007a5f0  mov     r9d, 1; bWait
0x18007a5f6  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18007a5fa  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18007a5fe  mov     rcx, [rbp+57h+hFile]; hFile
0x18007a602  call    cs:__imp_GetOverlappedResult
0x18007a608  mov     ecx, eax; int
0x18007a60a  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18007a60f  mov     ebx, eax
0x18007a611  mov     rcx, [rbp+57h+var_80]
0x18007a615  mov     rax, [rcx]
0x18007a618  mov     rax, [rax+20h]
0x18007a61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a621  test    ebx, ebx
0x18007a623  js      short loc_18007A65F
0x18007a625  mov     r8d, dword ptr [rbp+57h+NumberOfBytesTransferred]
0x18007a629  mov     rdx, [rbp+57h+var_60]; unsigned __int64
0x18007a62d  sub     r8, rdx
0x18007a630  add     r8, [rdi+0B0h]; unsigned __int64
0x18007a637  xor     r9d, r9d; bool
0x18007a63a  mov     rcx, rdi; this
0x18007a63d  call    ?_UpdateCachePosition@CRasFilePlaceholderParams@@AEAAX_K0_N@Z; CRasFilePlaceholderParams::_UpdateCachePosition(unsigned __int64,unsigned __int64,bool)
0x18007a642  mov     rcx, [r14+8]
0x18007a646  mov     rax, [rcx]
0x18007a649  mov     r8d, dword ptr [rbp+57h+NumberOfBytesTransferred]
0x18007a64d  mov     rdx, [rdi+0B0h]
0x18007a654  mov     rax, [rax+38h]
0x18007a658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a65d  mov     ebx, eax
0x18007a65f  lea     rcx, [rbp+57h+var_80]
0x18007a663  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007a668  lea     rcx, [rdi+0C8h]; SRWLock
0x18007a66f  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a675  nop
0x18007a676  mov     cs:?s_wpLastRemoteRead@CRasFilePlaceholderParams@@0PEAV1@EA, rdi; CRasFilePlaceholderParams * CRasFilePlaceholderParams::s_wpLastRemoteRead
0x18007a67d  call    cs:__imp_GetTickCount
0x18007a683  mov     cs:?s_dwTickCountLastRemoteRead@CRasFilePlaceholderParams@@0KA, eax; ulong CRasFilePlaceholderParams::s_dwTickCountLastRemoteRead
0x18007a689  lock dec cs:?s_dwRemoteReadRefCount@CRasFilePlaceholderParams@@0JC; long volatile CRasFilePlaceholderParams::s_dwRemoteReadRefCount
0x18007a690  lea     rcx, [rbp+57h+var_58]; this
0x18007a694  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x18007a699  test    ebx, ebx
0x18007a69b  jns     loc_18007A4C1
0x18007a6a1  lea     rcx, [rbp+57h+Overlapped.hEvent]; void **
0x18007a6a5  call    ?SafeCloseHandle@@YAHPEAPEAX@Z; SafeCloseHandle(void * *)
0x18007a6aa  nop
0x18007a6ab  lea     rcx, [rbp+57h+lpBuffer]
0x18007a6af  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18007a6b4  cmp     ebx, 80070026h
0x18007a6ba  jnz     short loc_18007A6D0
0x18007a6bc  xor     ebx, ebx
0x18007a6be  xor     r9d, r9d
0x18007a6c1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007a6c5  mov     rdx, r15
0x18007a6c8  mov     rcx, rdi
0x18007a6cb  call    ?SetLocallyCompleteIfAppropriate@CRasFilePlaceholderParams@@QEAAJPEAUISafeSaveHandleManager@@_KW4TransactionType@@@Z; CRasFilePlaceholderParams::SetLocallyCompleteIfAppropriate(ISafeSaveHandleManager *,unsigned __int64,TransactionType)
0x18007a6d0  mov     eax, ebx
0x18007a6d2  lea     r11, [rsp+0B0h+var_20]
0x18007a6da  mov     rbx, [r11+30h]
0x18007a6de  mov     rsi, [r11+40h]
0x18007a6e2  mov     rsp, r11
0x18007a6e5  pop     r15
0x18007a6e7  pop     r14
0x18007a6e9  pop     r12
0x18007a6eb  pop     rdi
0x18007a6ec  pop     rbp
0x18007a6ed  retn
```
