# CSafeSaveHandleManagerBase::PrepareTransactedCopy(unsigned __int64)

- ea: `0x180008930`
- end: `0x180008cad`
- name: `?PrepareTransactedCopy@CSafeSaveHandleManagerBase@@UEAAJ_K@Z`
- size: `893`
- prototype: `__int64 __fastcall(CSafeSaveHandleManagerBase *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180008824`
- `0x180008930`
- `0x18000ddd4`
- `0x18001af64`
- `0x180023730`
- `0x1800251e0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008954`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008985`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008954`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008985`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008a75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008a75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008961`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000899f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008961`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000899f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008af9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008bf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008af9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008bf0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008aa2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008aa2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180008ba9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180008ba9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180008ad3`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180008bda`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180008ad3`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180008bda`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSafeSaveHandleManagerBase::PrepareTransactedCopy(
        CSafeSaveHandleManagerBase *this,
        unsigned __int64 a2)
{
  RTL_SRWLOCK *v4; // r15
  unsigned __int64 v5; // rsi
  signed int ReadHandleSize; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // r14
  RTL_SRWLOCK *v9; // rcx
  unsigned __int64 v12; // r14
  unsigned int v13; // eax
  __int64 (__fastcall *v14)(CSafeSaveHandleManagerBase *, __int64 *); // rbx
  HANDLE v15; // rbx
  BOOL File; // eax
  BOOL OverlappedResult; // eax
  __int64 (__fastcall *v18)(CSafeSaveHandleManagerBase *, __int64, HANDLE *); // rbx
  HANDLE v19; // rbx
  BOOL v20; // eax
  BOOL v21; // eax
  HANDLE v22; // rcx
  __int64 v23; // rcx
  HANDLE hFile; // [rsp+30h] [rbp-30h] BYREF
  __int64 v25; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v26; // [rsp+40h] [rbp-20h]
  HANDLE v27; // [rsp+48h] [rbp-18h] BYREF
  HANDLE v28; // [rsp+50h] [rbp-10h]
  unsigned __int64 v29; // [rsp+58h] [rbp-8h]
  unsigned __int64 nNumberOfBytesToRead; // [rsp+A0h] [rbp+40h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+B0h] [rbp+50h] BYREF
  DWORD v32; // [rsp+B8h] [rbp+58h] BYREF

  v4 = (RTL_SRWLOCK *)((char *)this + 16);
  AcquireSRWLockShared((PSRWLOCK)this + 2);
  v5 = *((_QWORD *)this + 4);
  ReleaseSRWLockShared(v4);
  nNumberOfBytesToRead = 0;
  ReadHandleSize = CSafeSaveHandleManagerBase::_GetReadHandleSize(
                     (CSafeSaveHandleManagerBase *)((char *)this - 8),
                     &nNumberOfBytesToRead);
  if ( ReadHandleSize >= 0 )
  {
    AcquireSRWLockShared(v4);
    v7 = nNumberOfBytesToRead;
    if ( nNumberOfBytesToRead >= *((_QWORD *)this + 5) )
      v7 = *((_QWORD *)this + 5);
    v29 = v7;
    ReleaseSRWLockShared(v4);
    v8 = v7;
    if ( a2 < v7 )
      v8 = a2;
    v9 = (RTL_SRWLOCK *)((char *)this - 8);
    if ( v8 <= v5 )
      return (unsigned int)CSafeSaveHandleManagerBase::_SetWriteHandleSize(v9, 1, v5);
    v12 = v8 - v5;
    v26 = v5;
    ReadHandleSize = CSafeSaveHandleManagerBase::_EnsureBufferAndOverlapped(v9);
    if ( ReadHandleSize >= 0 )
    {
      v26 = v5;
      while ( v12 )
      {
        v13 = *((_DWORD *)this + 20);
        if ( v13 >= (unsigned int)v12 )
          v13 = v12;
        LODWORD(nNumberOfBytesToRead) = v13;
        v25 = 0;
        v14 = *(__int64 (__fastcall **)(CSafeSaveHandleManagerBase *, __int64 *))(*(_QWORD *)this + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v25);
        ReadHandleSize = v14(this, &v25);
        if ( ReadHandleSize >= 0 )
        {
          hFile = 0;
          ReadHandleSize = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v25 + 24LL))(v25, &hFile);
          if ( ReadHandleSize >= 0 )
          {
            v15 = hFile;
            v27 = hFile;
            AcquireSRWLockExclusive(v4);
            *((_DWORD *)this + 16) = v5;
            *((_DWORD *)this + 17) = HIDWORD(v26);
            NumberOfBytesTransferred = 0;
            File = ReadFile(v15, *((LPVOID *)this + 11), nNumberOfBytesToRead, 0, (LPOVERLAPPED)((char *)this + 48));
            ReadHandleSize = ResultFromWin32Bool(File);
            if ( (int)(ReadHandleSize + 0x80000000) < 0 || ReadHandleSize == -2147023899 )
            {
              OverlappedResult = GetOverlappedResult(
                                   v27,
                                   (LPOVERLAPPED)((char *)this + 48),
                                   &NumberOfBytesTransferred,
                                   1);
              ReadHandleSize = ResultFromWin32Bool(OverlappedResult);
              if ( ReadHandleSize >= 0 )
                ReadHandleSize = (_DWORD)nNumberOfBytesToRead != NumberOfBytesTransferred ? 0x8000FFFF : 0;
            }
            ReleaseSRWLockExclusive(v4);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
            if ( ReadHandleSize >= 0 )
            {
              hFile = 0;
              v18 = *(__int64 (__fastcall **)(CSafeSaveHandleManagerBase *, __int64, HANDLE *))(*(_QWORD *)this + 32LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&hFile);
              ReadHandleSize = v18(this, 1, &hFile);
              if ( ReadHandleSize >= 0 )
              {
                v27 = 0;
                ReadHandleSize = (*(__int64 (__fastcall **)(HANDLE, HANDLE *))(*(_QWORD *)hFile + 24LL))(hFile, &v27);
                if ( ReadHandleSize >= 0 )
                {
                  v19 = v27;
                  v28 = v27;
                  AcquireSRWLockExclusive(v4);
                  *((_DWORD *)this + 16) = v5;
                  *((_DWORD *)this + 17) = HIDWORD(v26);
                  v32 = 0;
                  v20 = WriteFile(
                          v19,
                          *((LPCVOID *)this + 11),
                          nNumberOfBytesToRead,
                          0,
                          (LPOVERLAPPED)((char *)this + 48));
                  ReadHandleSize = ResultFromWin32Bool(v20);
                  if ( (int)(ReadHandleSize + 0x80000000) < 0 || ReadHandleSize == -2147023899 )
                  {
                    v21 = GetOverlappedResult(v28, (LPOVERLAPPED)((char *)this + 48), &v32, 1);
                    ReadHandleSize = ResultFromWin32Bool(v21);
                    if ( ReadHandleSize >= 0 )
                      ReadHandleSize = (_DWORD)nNumberOfBytesToRead != v32 ? 0x8000FFFF : 0;
                  }
                  ReleaseSRWLockExclusive(v4);
                  (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hFile + 32LL))(hFile);
                }
              }
              v22 = hFile;
              if ( hFile )
              {
                hFile = 0;
                (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v22 + 16LL))(v22);
              }
              if ( ReadHandleSize >= 0 )
              {
                v5 += (unsigned int)nNumberOfBytesToRead;
                v26 = v5;
                v12 -= (unsigned int)nNumberOfBytesToRead;
              }
            }
          }
        }
        v23 = v25;
        if ( v25 )
        {
          v25 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        if ( ReadHandleSize < 0 )
          return (unsigned int)ReadHandleSize;
      }
      if ( a2 <= v29 )
        return (unsigned int)(*(__int64 (__fastcall **)(CSafeSaveHandleManagerBase *, unsigned __int64))(*(_QWORD *)this + 72LL))(
                               this,
                               a2);
      ReadHandleSize = CSafeSaveHandleManagerBase::_SetWriteHandleSize((char *)this - 8, 1, a2);
      if ( ReadHandleSize >= 0 )
        return (unsigned int)(*(__int64 (__fastcall **)(CSafeSaveHandleManagerBase *, unsigned __int64))(*(_QWORD *)this + 72LL))(
                               this,
                               a2);
    }
  }
  return (unsigned int)ReadHandleSize;
}

```

## disassembly

```asm
0x180008930  mov     [rsp-38h+arg_8], rbx
0x180008935  push    rbp
0x180008936  push    rsi
0x180008937  push    rdi
0x180008938  push    r12
0x18000893a  push    r13
0x18000893c  push    r14
0x18000893e  push    r15
0x180008940  mov     rbp, rsp
0x180008943  sub     rsp, 60h
0x180008947  mov     r13, rdx
0x18000894a  mov     rdi, rcx
0x18000894d  lea     r15, [rcx+10h]
0x180008951  mov     rcx, r15; SRWLock
0x180008954  call    cs:__imp_AcquireSRWLockShared
0x18000895a  mov     rsi, [rdi+20h]
0x18000895e  mov     rcx, r15; SRWLock
0x180008961  call    cs:__imp_ReleaseSRWLockShared
0x180008967  mov     [rbp+nNumberOfBytesToRead], 0
0x18000896f  lea     rdx, [rbp+nNumberOfBytesToRead]; unsigned __int64 *
0x180008973  lea     rcx, [rdi-8]; this
0x180008977  call    ?_GetReadHandleSize@CSafeSaveHandleManagerBase@@AEAAJPEA_K@Z; CSafeSaveHandleManagerBase::_GetReadHandleSize(unsigned __int64 *)
0x18000897c  mov     ebx, eax
0x18000897e  test    eax, eax
0x180008980  js      short loc_1800089C7
0x180008982  mov     rcx, r15; SRWLock
0x180008985  call    cs:__imp_AcquireSRWLockShared
0x18000898b  mov     rbx, [rbp+nNumberOfBytesToRead]
0x18000898f  cmp     rbx, [rdi+28h]
0x180008993  cmovnb  rbx, [rdi+28h]
0x180008998  mov     [rbp+var_8], rbx
0x18000899c  mov     rcx, r15; SRWLock
0x18000899f  call    cs:__imp_ReleaseSRWLockShared
0x1800089a5  mov     r14, rbx
0x1800089a8  cmp     r13, rbx
0x1800089ab  cmovb   r14, r13
0x1800089af  lea     rcx, [rdi-8]; this
0x1800089b3  cmp     r14, rsi
0x1800089b6  ja      short loc_1800089E1
0x1800089b8  mov     r8, rsi
0x1800089bb  mov     edx, 1
0x1800089c0  call    ?_SetWriteHandleSize@CSafeSaveHandleManagerBase@@AEAAJW4TransactionType@@_K@Z; CSafeSaveHandleManagerBase::_SetWriteHandleSize(TransactionType,unsigned __int64)
0x1800089c5  mov     ebx, eax
0x1800089c7  mov     eax, ebx
0x1800089c9  mov     rbx, [rsp+60h+arg_8]
0x1800089d1  add     rsp, 60h
0x1800089d5  pop     r15
0x1800089d7  pop     r14
0x1800089d9  pop     r13
0x1800089db  pop     r12
0x1800089dd  pop     rdi
0x1800089de  pop     rsi
0x1800089df  pop     rbp
0x1800089e0  retn
0x1800089e1  sub     r14, rsi
0x1800089e4  mov     [rbp+var_20], rsi
0x1800089e8  call    ?_EnsureBufferAndOverlapped@CSafeSaveHandleManagerBase@@AEAAJXZ; CSafeSaveHandleManagerBase::_EnsureBufferAndOverlapped(void)
0x1800089ed  mov     ebx, eax
0x1800089ef  test    eax, eax
0x1800089f1  js      short loc_1800089C7
0x1800089f3  mov     [rbp+var_20], rsi
0x1800089f7  mov     r12d, 1
0x1800089fd  test    r14, r14
0x180008a00  jz      loc_180008CA5
0x180008a06  mov     eax, [rdi+50h]
0x180008a09  cmp     eax, r14d
0x180008a0c  cmovnb  eax, r14d
0x180008a10  mov     dword ptr [rbp+nNumberOfBytesToRead], eax
0x180008a13  mov     [rbp+var_28], 0
0x180008a1b  mov     rax, [rdi]
0x180008a1e  mov     rbx, [rax+18h]
0x180008a22  lea     rcx, [rbp+var_28]
0x180008a26  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180008a2b  lea     rdx, [rbp+var_28]
0x180008a2f  mov     rcx, rdi
0x180008a32  mov     rax, rbx
0x180008a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a3a  mov     ebx, eax
0x180008a3c  test    eax, eax
0x180008a3e  js      loc_180008C29
0x180008a44  mov     rcx, [rbp+var_28]
0x180008a48  mov     [rbp+hFile], 0
0x180008a50  mov     rax, [rcx]
0x180008a53  lea     rdx, [rbp+hFile]
0x180008a57  mov     rax, [rax+18h]
0x180008a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a60  mov     ebx, eax
0x180008a62  test    eax, eax
0x180008a64  js      loc_180008C29
0x180008a6a  mov     rbx, [rbp+hFile]
0x180008a6e  mov     [rbp+var_18], rbx
0x180008a72  mov     rcx, r15; SRWLock
0x180008a75  call    cs:__imp_AcquireSRWLockExclusive
0x180008a7b  mov     [rdi+40h], esi
0x180008a7e  mov     eax, dword ptr [rbp+var_20+4]
0x180008a81  mov     [rdi+44h], eax
0x180008a84  mov     [rbp+NumberOfBytesTransferred], 0
0x180008a8b  lea     rax, [rdi+30h]
0x180008a8f  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x180008a94  xor     r9d, r9d; lpNumberOfBytesRead
0x180008a97  mov     r8d, dword ptr [rbp+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180008a9b  mov     rdx, [rdi+58h]; lpBuffer
0x180008a9f  mov     rcx, rbx; hFile
0x180008aa2  call    cs:__imp_ReadFile
0x180008aa8  mov     ecx, eax; int
0x180008aaa  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180008aaf  mov     ebx, eax
0x180008ab1  mov     ecx, 80000000h
0x180008ab6  add     eax, ecx
0x180008ab8  test    ecx, eax
0x180008aba  jnz     short loc_180008AC4
0x180008abc  cmp     ebx, 800703E5h
0x180008ac2  jnz     short loc_180008AF6
0x180008ac4  mov     r9d, r12d; bWait
0x180008ac7  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180008acb  lea     rdx, [rdi+30h]; lpOverlapped
0x180008acf  mov     rcx, [rbp+var_18]; hFile
0x180008ad3  call    cs:__imp_GetOverlappedResult
0x180008ad9  mov     ecx, eax; int
0x180008adb  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180008ae0  mov     ebx, eax
0x180008ae2  test    eax, eax
0x180008ae4  js      short loc_180008AF6
0x180008ae6  mov     eax, [rbp+NumberOfBytesTransferred]
0x180008ae9  sub     eax, dword ptr [rbp+nNumberOfBytesToRead]
0x180008aec  neg     eax
0x180008aee  sbb     ebx, ebx
0x180008af0  and     ebx, 8000FFFFh
0x180008af6  mov     rcx, r15; SRWLock
0x180008af9  call    cs:__imp_ReleaseSRWLockExclusive
0x180008aff  mov     rcx, [rbp+var_28]
0x180008b03  mov     rax, [rcx]
0x180008b06  mov     rax, [rax+20h]
0x180008b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0f  test    ebx, ebx
0x180008b11  js      loc_180008C29
0x180008b17  mov     [rbp+hFile], 0
0x180008b1f  mov     rax, [rdi]
0x180008b22  mov     rbx, [rax+20h]
0x180008b26  lea     rcx, [rbp+hFile]
0x180008b2a  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180008b2f  lea     r8, [rbp+hFile]
0x180008b33  mov     edx, r12d
0x180008b36  mov     rcx, rdi
0x180008b39  mov     rax, rbx
0x180008b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b41  mov     ebx, eax
0x180008b43  test    eax, eax
0x180008b45  js      loc_180008C07
0x180008b4b  mov     rcx, [rbp+hFile]
0x180008b4f  mov     [rbp+var_18], 0
0x180008b57  mov     rax, [rcx]
0x180008b5a  lea     rdx, [rbp+var_18]
0x180008b5e  mov     rax, [rax+18h]
0x180008b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b67  mov     ebx, eax
0x180008b69  test    eax, eax
0x180008b6b  js      loc_180008C07
0x180008b71  mov     rbx, [rbp+var_18]
0x180008b75  mov     [rbp+var_10], rbx
0x180008b79  mov     rcx, r15; SRWLock
0x180008b7c  call    cs:__imp_AcquireSRWLockExclusive
0x180008b82  mov     [rdi+40h], esi
0x180008b85  mov     eax, dword ptr [rbp+var_20+4]
0x180008b88  mov     [rdi+44h], eax
0x180008b8b  mov     [rbp+arg_18], 0
0x180008b92  lea     rax, [rdi+30h]
0x180008b96  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x180008b9b  xor     r9d, r9d; lpNumberOfBytesWritten
0x180008b9e  mov     r8d, dword ptr [rbp+nNumberOfBytesToRead]; nNumberOfBytesToWrite
0x180008ba2  mov     rdx, [rdi+58h]; lpBuffer
0x180008ba6  mov     rcx, rbx; hFile
0x180008ba9  call    cs:__imp_WriteFile
0x180008baf  mov     ecx, eax; int
0x180008bb1  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180008bb6  mov     ebx, eax
0x180008bb8  mov     ecx, 80000000h
0x180008bbd  add     eax, ecx
0x180008bbf  test    ecx, eax
0x180008bc1  jnz     short loc_180008BCB
0x180008bc3  cmp     ebx, 800703E5h
0x180008bc9  jnz     short loc_180008BED
0x180008bcb  mov     r9d, r12d; bWait
0x180008bce  lea     r8, [rbp+arg_18]; lpNumberOfBytesTransferred
0x180008bd2  lea     rdx, [rdi+30h]; lpOverlapped
0x180008bd6  mov     rcx, [rbp+var_10]; hFile
0x180008bda  call    cs:__imp_GetOverlappedResult
0x180008be0  mov     ecx, eax; int
0x180008be2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180008be7  mov     ebx, eax
0x180008be9  test    eax, eax
0x180008beb  jns     short loc_180008C54
0x180008bed  mov     rcx, r15; SRWLock
0x180008bf0  call    cs:__imp_ReleaseSRWLockExclusive
0x180008bf6  mov     rcx, [rbp+hFile]
0x180008bfa  mov     rax, [rcx]
0x180008bfd  mov     rax, [rax+20h]
0x180008c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c06  nop
0x180008c07  mov     rcx, [rbp+hFile]
0x180008c0b  test    rcx, rcx
0x180008c0e  jz      short loc_180008C25
0x180008c10  mov     [rbp+hFile], 0
0x180008c18  mov     rax, [rcx]
0x180008c1b  mov     rax, [rax+10h]
0x180008c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c24  nop
0x180008c25  test    ebx, ebx
0x180008c27  jns     short loc_180008C96
0x180008c29  mov     rcx, [rbp+var_28]
0x180008c2d  test    rcx, rcx
0x180008c30  jz      short loc_180008C47
0x180008c32  mov     [rbp+var_28], 0
0x180008c3a  mov     rax, [rcx]
0x180008c3d  mov     rax, [rax+10h]
0x180008c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c46  nop
0x180008c47  test    ebx, ebx
0x180008c49  jns     loc_1800089FD
0x180008c4f  jmp     loc_1800089C7
0x180008c54  mov     eax, [rbp+arg_18]
0x180008c57  sub     eax, dword ptr [rbp+nNumberOfBytesToRead]
0x180008c5a  neg     eax
0x180008c5c  sbb     ebx, ebx
0x180008c5e  and     ebx, 8000FFFFh
0x180008c64  jmp     short loc_180008BED
0x180008c66  mov     r8, r13
0x180008c69  mov     edx, r12d
0x180008c6c  lea     rcx, [rdi-8]
0x180008c70  call    ?_SetWriteHandleSize@CSafeSaveHandleManagerBase@@AEAAJW4TransactionType@@_K@Z; CSafeSaveHandleManagerBase::_SetWriteHandleSize(TransactionType,unsigned __int64)
0x180008c75  mov     ebx, eax
0x180008c77  test    eax, eax
0x180008c79  js      loc_1800089C7
0x180008c7f  mov     rax, [rdi]
0x180008c82  mov     rdx, r13
0x180008c85  mov     rcx, rdi
0x180008c88  mov     rax, [rax+48h]
0x180008c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c91  jmp     loc_1800089C5
0x180008c96  mov     eax, dword ptr [rbp+nNumberOfBytesToRead]
0x180008c99  add     rsi, rax
0x180008c9c  mov     [rbp+var_20], rsi
0x180008ca0  sub     r14, rax
0x180008ca3  jmp     short loc_180008C29
0x180008ca5  cmp     r13, [rbp+var_8]
0x180008ca9  jbe     short loc_180008C7F
0x180008cab  jmp     short loc_180008C66
```
