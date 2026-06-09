# SocketTransport::Close(void)

- ea: `0x14005fb20`
- end: `0x14005fdb2`
- name: `?Close@SocketTransport@@UEAAXXZ`
- size: `658`
- prototype: `void __fastcall(SocketTransport *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005f5c8`

## callees

- `0x140005360`
- `0x140006098`
- `0x14005da80`
- `0x14005ec0c`
- `0x14005efac`
- `0x14005f2e4`
- `0x14005fb20`
- `0x140060248`
- `0x140062518`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14005fbda`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14005fbda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005fc19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005fd6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005fc19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005fd6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005fb9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005fd35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005fb9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005fd35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fc60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fca1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fcf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fd24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fc60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fca1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fcf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005fd24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fc8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fd11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fc8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fd11`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x14005fc7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x14005fcd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x14005fc7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x14005fcd1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14005fc99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14005fcee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14005fc99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14005fcee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fba2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fbe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fd3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fba2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fbe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fd3b`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x14005fc3d`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x14005fcc2`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x14005fc3d`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x14005fcc2`
- `WS2_32!__imp_closesocket` at `0x14005fc58`
- `WS2_32!__imp_closesocket` at `0x14005fd1c`
- `WS2_32!__imp_closesocket` at `0x14005fc58`
- `WS2_32!__imp_closesocket` at `0x14005fd1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SocketTransport::Close(SocketTransport *this)
{
  char v2; // bl
  void *v3; // rcx
  SOCKET v4; // r14
  DWORD LastError; // ebx
  struct _TP_IO *v6; // rcx
  struct _TP_IO *v7; // r14
  DWORD v8; // ebx
  struct _TP_IO *v9; // r14
  DWORD v10; // ebx
  SOCKET v11; // r14
  DWORD v12; // ebx
  _QWORD v13[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v14[42]; // [rsp+30h] [rbp-D0h] BYREF

  memset_0(v14, 0, sizeof(v14));
  v13[0] = this;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v14,
    "SocketTransport_Close");
  v14[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::StartActivity<SocketTransport *>(v14, v13);
  v2 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 25);
  *((_DWORD *)this + 52) = GetCurrentThreadId();
  if ( *((_DWORD *)this + 57) != 9 )
  {
    v2 = 1;
    *((_DWORD *)this + 57) = 9;
    while ( *((_DWORD *)this + 56) )
    {
      *((_DWORD *)this + 52) = 0;
      SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 27, (PSRWLOCK)this + 25, 0xFFFFFFFF, 0);
      *((_DWORD *)this + 52) = GetCurrentThreadId();
    }
    v13[0] = this;
    ComputeService::Diagnostics::TraceProvider::Transport_IoSummary<SocketTransport *,unsigned __int64 &,unsigned __int64 &>(
      v13,
      (char *)this + 376,
      (char *)this + 368);
  }
  *((_DWORD *)this + 52) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
  if ( v2 )
  {
    v3 = (void *)*((_QWORD *)this + 15);
    if ( v3 != (void *)-1LL )
    {
      if ( *((_QWORD *)this + 17) )
        CancelIoEx(v3, 0);
      v4 = *((_QWORD *)this + 15);
      if ( v4 != -1 )
      {
        LastError = GetLastError();
        closesocket(v4);
        SetLastError(LastError);
      }
      *((_QWORD *)this + 15) = -1;
    }
    v6 = (struct _TP_IO *)*((_QWORD *)this + 17);
    if ( v6 )
    {
      WaitForThreadpoolIoCallbacks(v6, 0);
      v7 = (struct _TP_IO *)*((_QWORD *)this + 17);
      if ( v7 )
      {
        v8 = GetLastError();
        CloseThreadpoolIo(v7);
        SetLastError(v8);
      }
      *((_QWORD *)this + 17) = 0;
    }
    if ( *((_QWORD *)this + 16) )
    {
      CancelIoEx(*((HANDLE *)this + 14), 0);
      WaitForThreadpoolIoCallbacks(*((PTP_IO *)this + 16), 0);
      v9 = (struct _TP_IO *)*((_QWORD *)this + 16);
      if ( v9 )
      {
        v10 = GetLastError();
        CloseThreadpoolIo(v9);
        SetLastError(v10);
      }
      *((_QWORD *)this + 16) = 0;
    }
    v11 = *((_QWORD *)this + 14);
    if ( v11 != -1 )
    {
      v12 = GetLastError();
      closesocket(v11);
      SetLastError(v12);
    }
    *((_QWORD *)this + 14) = -1;
    AcquireSRWLockExclusive((PSRWLOCK)this + 25);
    *((_DWORD *)this + 52) = GetCurrentThreadId();
    if ( *((_BYTE *)this + 232) )
    {
      *((_DWORD *)this + 57) = 3;
      *((_BYTE *)this + 110) = 0;
      *((_BYTE *)this + 109) = 0;
    }
    *((_DWORD *)this + 52) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v14);
  v14[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v14);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(v14);
}

```

## disassembly

```asm
0x14005fb20  push    rbp
0x14005fb22  push    rbx
0x14005fb23  push    rsi
0x14005fb24  push    rdi
0x14005fb25  push    r13
0x14005fb27  push    r14
0x14005fb29  lea     rbp, [rsp-98h]
0x14005fb31  sub     rsp, 198h
0x14005fb38  mov     rax, cs:__security_cookie
0x14005fb3f  xor     rax, rsp
0x14005fb42  mov     [rbp+0C0h+var_40], rax
0x14005fb49  mov     rdi, rcx
0x14005fb4c  xor     edx, edx; Val
0x14005fb4e  mov     r8d, 150h; Size
0x14005fb54  lea     rcx, [rsp+1C0h+var_190]; void *
0x14005fb59  call    memset_0
0x14005fb5e  mov     [rsp+1C0h+var_1A0], rdi
0x14005fb63  lea     rdx, aSockettranspor_2; "SocketTransport_Close"
0x14005fb6a  lea     rcx, [rsp+1C0h+var_190]
0x14005fb6f  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14005fb74  lea     r13, ??_7SocketTransport_Close@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::`vftable'
0x14005fb7b  mov     [rsp+1C0h+var_190], r13
0x14005fb80  lea     rdx, [rsp+1C0h+var_1A0]
0x14005fb85  lea     rcx, [rsp+1C0h+var_190]
0x14005fb8a  call    ??$StartActivity@PEAVSocketTransport@@@SocketTransport_Close@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::StartActivity<SocketTransport *>(SocketTransport * &&)
0x14005fb8f  nop
0x14005fb90  xor     bl, bl
0x14005fb92  lea     rsi, [rdi+0C8h]
0x14005fb99  mov     rcx, rsi; SRWLock
0x14005fb9c  call    cs:__imp_AcquireSRWLockExclusive
0x14005fba2  call    cs:__imp_GetCurrentThreadId
0x14005fba8  mov     [rsi+8], eax
0x14005fbab  cmp     dword ptr [rdi+0E4h], 9
0x14005fbb2  jz      short loc_14005FC0F
0x14005fbb4  mov     bl, 1
0x14005fbb6  mov     dword ptr [rdi+0E4h], 9
0x14005fbc0  jmp     short loc_14005FBE9
0x14005fbc2  mov     dword ptr [rsi+8], 0
0x14005fbc9  xor     r9d, r9d; Flags
0x14005fbcc  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x14005fbd0  mov     rdx, rsi; SRWLock
0x14005fbd3  lea     rcx, [rdi+0D8h]; ConditionVariable
0x14005fbda  call    cs:__imp_SleepConditionVariableSRW
0x14005fbe0  call    cs:__imp_GetCurrentThreadId
0x14005fbe6  mov     [rsi+8], eax
0x14005fbe9  cmp     dword ptr [rdi+0E0h], 0
0x14005fbf0  ja      short loc_14005FBC2
0x14005fbf2  mov     [rsp+1C0h+var_1A0], rdi
0x14005fbf7  lea     r8, [rdi+170h]
0x14005fbfe  lea     rdx, [rdi+178h]
0x14005fc05  lea     rcx, [rsp+1C0h+var_1A0]
0x14005fc0a  call    ??$Transport_IoSummary@PEAVSocketTransport@@AEA_KAEA_K@TraceProvider@Diagnostics@ComputeService@@SAX$$QEAPEAVSocketTransport@@AEA_K1@Z; ComputeService::Diagnostics::TraceProvider::Transport_IoSummary<SocketTransport *,unsigned __int64 &,unsigned __int64 &>(SocketTransport * &&,unsigned __int64 &,unsigned __int64 &)
0x14005fc0f  mov     dword ptr [rsi+8], 0
0x14005fc16  mov     rcx, rsi; SRWLock
0x14005fc19  call    cs:__imp_ReleaseSRWLockExclusive
0x14005fc1f  test    bl, bl
0x14005fc21  jz      loc_14005FD70
0x14005fc27  mov     rcx, [rdi+78h]; hFile
0x14005fc2b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14005fc2f  jz      short loc_14005FC6E
0x14005fc31  cmp     qword ptr [rdi+88h], 0
0x14005fc39  jz      short loc_14005FC43
0x14005fc3b  xor     edx, edx; lpOverlapped
0x14005fc3d  call    cs:__imp_CancelIoEx
0x14005fc43  mov     r14, [rdi+78h]
0x14005fc47  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14005fc4b  jz      short loc_14005FC66
0x14005fc4d  call    cs:__imp_GetLastError
0x14005fc53  mov     ebx, eax
0x14005fc55  mov     rcx, r14; s
0x14005fc58  call    cs:__imp_closesocket
0x14005fc5e  mov     ecx, ebx; dwErrCode
0x14005fc60  call    cs:__imp_SetLastError
0x14005fc66  mov     qword ptr [rdi+78h], 0FFFFFFFFFFFFFFFFh
0x14005fc6e  mov     rcx, [rdi+88h]; pio
0x14005fc75  test    rcx, rcx
0x14005fc78  jz      short loc_14005FCB2
0x14005fc7a  xor     edx, edx; fCancelPendingCallbacks
0x14005fc7c  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x14005fc82  mov     r14, [rdi+88h]
0x14005fc89  test    r14, r14
0x14005fc8c  jz      short loc_14005FCA7
0x14005fc8e  call    cs:__imp_GetLastError
0x14005fc94  mov     ebx, eax
0x14005fc96  mov     rcx, r14; pio
0x14005fc99  call    cs:__imp_CloseThreadpoolIo
0x14005fc9f  mov     ecx, ebx; dwErrCode
0x14005fca1  call    cs:__imp_SetLastError
0x14005fca7  mov     qword ptr [rdi+88h], 0
0x14005fcb2  cmp     qword ptr [rdi+80h], 0
0x14005fcba  jz      short loc_14005FD07
0x14005fcbc  xor     edx, edx; lpOverlapped
0x14005fcbe  mov     rcx, [rdi+70h]; hFile
0x14005fcc2  call    cs:__imp_CancelIoEx
0x14005fcc8  xor     edx, edx; fCancelPendingCallbacks
0x14005fcca  mov     rcx, [rdi+80h]; pio
0x14005fcd1  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x14005fcd7  mov     r14, [rdi+80h]
0x14005fcde  test    r14, r14
0x14005fce1  jz      short loc_14005FCFC
0x14005fce3  call    cs:__imp_GetLastError
0x14005fce9  mov     ebx, eax
0x14005fceb  mov     rcx, r14; pio
0x14005fcee  call    cs:__imp_CloseThreadpoolIo
0x14005fcf4  mov     ecx, ebx; dwErrCode
0x14005fcf6  call    cs:__imp_SetLastError
0x14005fcfc  mov     qword ptr [rdi+80h], 0
0x14005fd07  mov     r14, [rdi+70h]
0x14005fd0b  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14005fd0f  jz      short loc_14005FD2A
0x14005fd11  call    cs:__imp_GetLastError
0x14005fd17  mov     ebx, eax
0x14005fd19  mov     rcx, r14; s
0x14005fd1c  call    cs:__imp_closesocket
0x14005fd22  mov     ecx, ebx; dwErrCode
0x14005fd24  call    cs:__imp_SetLastError
0x14005fd2a  mov     qword ptr [rdi+70h], 0FFFFFFFFFFFFFFFFh
0x14005fd32  mov     rcx, rsi; SRWLock
0x14005fd35  call    cs:__imp_AcquireSRWLockExclusive
0x14005fd3b  call    cs:__imp_GetCurrentThreadId
0x14005fd41  mov     [rsi+8], eax
0x14005fd44  cmp     byte ptr [rdi+0E8h], 0
0x14005fd4b  jz      short loc_14005FD60
0x14005fd4d  mov     dword ptr [rdi+0E4h], 3
0x14005fd57  xor     eax, eax
0x14005fd59  xchg    al, [rdi+6Eh]
0x14005fd5c  mov     byte ptr [rdi+6Dh], 0
0x14005fd60  mov     dword ptr [rsi+8], 0
0x14005fd67  mov     rcx, rsi; SRWLock
0x14005fd6a  call    cs:__imp_ReleaseSRWLockExclusive
0x14005fd70  lea     rcx, [rsp+1C0h+var_190]
0x14005fd75  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14005fd7a  mov     [rsp+1C0h+var_190], r13
0x14005fd7f  lea     rcx, [rsp+1C0h+var_190]
0x14005fd84  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14005fd89  lea     rcx, [rsp+1C0h+var_190]
0x14005fd8e  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x14005fd93  mov     rcx, [rbp+0C0h+var_40]
0x14005fd9a  xor     rcx, rsp; StackCookie
0x14005fd9d  call    __security_check_cookie
0x14005fda2  add     rsp, 198h
0x14005fda9  pop     r14
0x14005fdab  pop     r13
0x14005fdad  pop     rdi
0x14005fdae  pop     rsi
0x14005fdaf  pop     rbx
0x14005fdb0  pop     rbp
0x14005fdb1  retn
```
