# SAL2::CSALFileIoMgr::WorkerCompleteIo(void)

- ea: `0x180089af0`
- end: `0x180089caa`
- name: `?WorkerCompleteIo@CSALFileIoMgr@SAL2@@AEAAXXZ`
- size: `442`
- prototype: `void __fastcall(SAL2::CSALFileIoMgr *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180089cb0`

## callees

- `0x180062710`
- `0x180088b08`
- `0x180088dd4`
- `0x1800896d0`
- `0x180089af0`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180089b34`
- `KERNEL32!GetCurrentThread` at `0x180089bba`
- `KERNEL32!GetCurrentThread` at `0x180089b34`
- `KERNEL32!GetCurrentThread` at `0x180089bba`
- `KERNEL32!GetLastError` at `0x180089b83`
- `KERNEL32!GetLastError` at `0x180089b83`
- `KERNEL32!SetThreadPriority` at `0x180089b41`
- `KERNEL32!SetThreadPriority` at `0x180089bc6`
- `KERNEL32!SetThreadPriority` at `0x180089b41`
- `KERNEL32!SetThreadPriority` at `0x180089bc6`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180089bf6`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180089bf6`
- `KERNEL32!GetModuleHandleExW` at `0x180089b17`
- `KERNEL32!GetModuleHandleExW` at `0x180089b2e`
- `KERNEL32!GetModuleHandleExW` at `0x180089b17`
- `KERNEL32!GetModuleHandleExW` at `0x180089b2e`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180089b79`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180089b79`

## string_xrefs

- `0x180089b25`: `ehtrace.dll`

## pseudocode

```c
void __fastcall SAL2::CSALFileIoMgr::WorkerCompleteIo(SAL2::CSALFileIoMgr *this)
{
  int v1; // r14d
  HANDLE CurrentThread; // rax
  void *v4; // rcx
  signed int LastError; // eax
  signed int v6; // ebx
  HANDLE v7; // rax
  LPOVERLAPPED v8; // rsi
  volatile signed __int64 *v9; // r8
  char *v10; // r10
  unsigned __int64 v11; // rax
  signed __int64 v12; // rdx
  unsigned __int64 v13; // r9
  unsigned __int64 CompletionKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp+30h] BYREF
  HMODULE v16; // [rsp+78h] [rbp+38h] BYREF
  HMODULE phModule; // [rsp+80h] [rbp+40h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+88h] [rbp+48h] BYREF

  v1 = 0;
  phModule = 0;
  GetModuleHandleExW(4u, (LPCWSTR)SAL2::CSALFileIoMgr::WorkerCompleteIoThunk, &phModule);
  v16 = 0;
  GetModuleHandleExW(0, L"ehtrace.dll", &v16);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 2);
  while ( 1 )
  {
    v4 = (void *)*((_QWORD *)this + 39);
    NumberOfBytesTransferred = 0;
    CompletionKey = 0;
    Overlapped = 0;
    if ( !GetQueuedCompletionStatus(v4, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
      break;
    v6 = 0;
    v1 = 0;
LABEL_10:
    v8 = Overlapped;
    if ( Overlapped )
    {
      if ( Overlapped == (LPOVERLAPPED)this )
        goto LABEL_7;
      if ( (SAL2::CSALFileIoMgr *)Overlapped[-2].Internal != this )
        SBEBasicTracers::EtwTraceAssert(
          (SAL2::CSALFileIoMgr *)((char *)this + 96),
          "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
          0x39Cu);
      if ( v6 >= 0 && LODWORD(v8[-2].InternalHigh) == 2 )
      {
        v9 = (volatile signed __int64 *)*((_QWORD *)this + 47);
        if ( v9 )
        {
          v10 = (char *)v8[-2].Pointer + LODWORD(v8[-2].hEvent);
          v11 = *v9;
          do
          {
            v12 = v11;
            v13 = v11;
            if ( v11 <= (unsigned __int64)v10 )
              v12 = (signed __int64)v10;
            v11 = _InterlockedCompareExchange64(v9, v12, v11);
          }
          while ( v11 != v13 );
        }
      }
      SAL2::CSALFileIoMgr::AsyncIo::CompleteIo((SAL2::CSALFileIoMgr::AsyncIo *)&v8[-3].16, NumberOfBytesTransferred, v6);
      (*((void (__fastcall **)(PVOID *))v8[-3].Pointer + 2))(&v8[-3].Pointer);
    }
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (unsigned int)++v1 < 0x1388 )
    goto LABEL_10;
  SBEBasicTracers::EtwTraceAssert(
    (SAL2::CSALFileIoMgr *)((char *)this + 96),
    "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
    0x38Bu);
LABEL_7:
  v7 = GetCurrentThread();
  SetThreadPriority(v7, -1);
  *((_DWORD *)this + 80) = 0;
  SAL2::CSALFileIoMgr::ReleaseWorker(this);
  SAL2::CSALLibraryThreadLock::Free((SAL2::CSALLibraryThreadLock *)&v16);
  if ( phModule )
    FreeLibraryAndExitThread(phModule, 0);
  SAL2::CSALLibraryThreadLock::Free((SAL2::CSALLibraryThreadLock *)&v16);
  SAL2::CSALLibraryThreadLock::Free((SAL2::CSALLibraryThreadLock *)&phModule);
}

```

## disassembly

```asm
0x180089af0  push    rbp
0x180089af2  push    rbx
0x180089af3  push    rsi
0x180089af4  push    rdi
0x180089af5  push    r14
0x180089af7  mov     rbp, rsp
0x180089afa  sub     rsp, 40h
0x180089afe  xor     r14d, r14d
0x180089b01  lea     r8, [rbp+phModule]; phModule
0x180089b05  mov     rdi, rcx
0x180089b08  mov     [rbp+phModule], r14
0x180089b0c  lea     rdx, ?WorkerCompleteIoThunk@CSALFileIoMgr@SAL2@@CAKPEAX@Z; lpModuleName
0x180089b13  lea     ecx, [r14+4]; dwFlags
0x180089b17  call    cs:__imp_GetModuleHandleExW
0x180089b1d  lea     r8, [rbp+arg_8]; phModule
0x180089b21  mov     [rbp+arg_8], r14
0x180089b25  lea     rdx, aEhtraceDll; "ehtrace.dll"
0x180089b2c  xor     ecx, ecx; dwFlags
0x180089b2e  call    cs:__imp_GetModuleHandleExW
0x180089b34  call    cs:__imp_GetCurrentThread
0x180089b3a  mov     rcx, rax; hThread
0x180089b3d  lea     edx, [r14+2]; nPriority
0x180089b41  call    cs:__imp_SetThreadPriority
0x180089b47  mov     rcx, [rdi+138h]; CompletionPort
0x180089b4e  lea     r9, [rbp+Overlapped]; lpOverlapped
0x180089b52  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x180089b56  mov     [rbp+NumberOfBytesTransferred], 0
0x180089b5d  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180089b61  mov     [rbp+CompletionKey], 0
0x180089b69  mov     [rbp+Overlapped], 0
0x180089b71  mov     [rsp+40h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180089b79  call    cs:__imp_GetQueuedCompletionStatus
0x180089b7f  test    eax, eax
0x180089b81  jnz     short loc_180089BFD
0x180089b83  call    cs:__imp_GetLastError
0x180089b89  mov     ebx, eax
0x180089b8b  test    eax, eax
0x180089b8d  jle     short loc_180089B98
0x180089b8f  movzx   ebx, ax
0x180089b92  or      ebx, 80070000h
0x180089b98  inc     r14d
0x180089b9b  cmp     r14d, 1388h
0x180089ba2  jb      short loc_180089C02
0x180089ba4  lea     rcx, [rdi+60h]; struct CEhEventTracer *
0x180089ba8  mov     r8d, 38Bh; unsigned int
0x180089bae  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180089bb5  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x180089bba  call    cs:__imp_GetCurrentThread
0x180089bc0  mov     rcx, rax; hThread
0x180089bc3  or      edx, 0FFFFFFFFh; nPriority
0x180089bc6  call    cs:__imp_SetThreadPriority
0x180089bcc  mov     rcx, rdi; this
0x180089bcf  mov     dword ptr [rdi+140h], 0
0x180089bd9  call    ?ReleaseWorker@CSALFileIoMgr@SAL2@@AEAAXXZ; SAL2::CSALFileIoMgr::ReleaseWorker(void)
0x180089bde  lea     rcx, [rbp+arg_8]; this
0x180089be2  call    ?Free@CSALLibraryThreadLock@SAL2@@QEAAXXZ; SAL2::CSALLibraryThreadLock::Free(void)
0x180089be7  mov     rcx, [rbp+phModule]; hLibModule
0x180089beb  test    rcx, rcx
0x180089bee  jz      loc_180089C8D
0x180089bf4  xor     edx, edx; dwExitCode
0x180089bf6  call    cs:__imp_FreeLibraryAndExitThread
0x180089bfd  xor     ebx, ebx
0x180089bff  xor     r14d, r14d
0x180089c02  mov     rsi, [rbp+Overlapped]
0x180089c06  test    rsi, rsi
0x180089c09  jz      loc_180089B47
0x180089c0f  cmp     rsi, rdi
0x180089c12  jz      short loc_180089BBA
0x180089c14  cmp     [rsi-40h], rdi
0x180089c18  jz      short loc_180089C30
0x180089c1a  lea     rcx, [rdi+60h]; struct CEhEventTracer *
0x180089c1e  mov     r8d, 39Ch; unsigned int
0x180089c24  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180089c2b  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x180089c30  test    ebx, ebx
0x180089c32  js      short loc_180089C68
0x180089c34  cmp     dword ptr [rsi-38h], 2
0x180089c38  jnz     short loc_180089C68
0x180089c3a  mov     r8, [rdi+178h]
0x180089c41  test    r8, r8
0x180089c44  jz      short loc_180089C68
0x180089c46  mov     r10d, [rsi-28h]
0x180089c4a  add     r10, [rsi-30h]
0x180089c4e  mov     rax, [r8]
0x180089c51  cmp     rax, r10
0x180089c54  mov     rdx, rax
0x180089c57  mov     r9, rax
0x180089c5a  cmovbe  rdx, r10
0x180089c5e  lock cmpxchg [r8], rdx
0x180089c63  cmp     rax, r9
0x180089c66  jnz     short loc_180089C51
0x180089c68  mov     edx, [rbp+NumberOfBytesTransferred]; unsigned int
0x180089c6b  lea     rcx, [rsi-50h]; this
0x180089c6f  mov     r8d, ebx; int
0x180089c72  call    ?CompleteIo@AsyncIo@CSALFileIoMgr@SAL2@@QEAAXKJ@Z; SAL2::CSALFileIoMgr::AsyncIo::CompleteIo(ulong,long)
0x180089c77  mov     rax, [rsi-50h]
0x180089c7b  lea     rcx, [rsi-50h]
0x180089c7f  mov     rax, [rax+10h]
0x180089c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c88  jmp     loc_180089B47
0x180089c8d  lea     rcx, [rbp+arg_8]; this
0x180089c91  call    ?Free@CSALLibraryThreadLock@SAL2@@QEAAXXZ; SAL2::CSALLibraryThreadLock::Free(void)
0x180089c96  lea     rcx, [rbp+phModule]; this
0x180089c9a  call    ?Free@CSALLibraryThreadLock@SAL2@@QEAAXXZ; SAL2::CSALLibraryThreadLock::Free(void)
0x180089c9f  add     rsp, 40h
0x180089ca3  pop     r14
0x180089ca5  pop     rdi
0x180089ca6  pop     rsi
0x180089ca7  pop     rbx
0x180089ca8  pop     rbp
0x180089ca9  retn
```
