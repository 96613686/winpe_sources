# PipeTransport::Close(void)

- ea: `0x1400f3730`
- end: `0x1400f3838`
- name: `?Close@PipeTransport@@UEAAXXZ`
- size: `264`
- prototype: `void __fastcall(PipeTransport *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400f34f0`

## callees

- `0x1400f33f8`
- `0x1400f3730`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400f376c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400f376c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3797`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3797`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f3746`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f3746`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400f37e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400f3821`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400f37e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400f3821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f37d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f380e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f37d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f380e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1400f37ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1400f37ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400f3819`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400f3819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f37de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f37de`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1400f37bf`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1400f37bf`

## pseudocode

```c
void __fastcall PipeTransport::Close(PipeTransport *this)
{
  RTL_SRWLOCK *v1; // rbx
  char v3; // si
  void *v4; // rcx
  char *v5; // rsi
  DWORD LastError; // ebx
  struct _TP_IO *v7; // rcx
  struct _TP_IO *v8; // rsi
  DWORD v9; // ebx
  PipeTransport *v10; // [rsp+20h] [rbp-38h] BYREF

  v1 = (RTL_SRWLOCK *)((char *)this + 32);
  v3 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  if ( *((_DWORD *)this + 11) != 7 )
  {
    v3 = 1;
    *((_DWORD *)this + 11) = 7;
    while ( *((_DWORD *)this + 14) )
      SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 6, v1, 0xFFFFFFFF, 0);
    v10 = this;
    ComputeService::Diagnostics::TraceProvider::Transport_IoSummary<PipeTransport *,unsigned __int64 &,unsigned __int64 &>(
      &v10,
      (char *)this + 104,
      (char *)this + 96);
  }
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  if ( v3 )
  {
    v4 = (void *)*((_QWORD *)this + 1);
    if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      if ( *((_QWORD *)this + 2) )
        CancelIoEx(v4, 0);
      v5 = (char *)*((_QWORD *)this + 1);
      if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v5);
        SetLastError(LastError);
      }
      *((_QWORD *)this + 1) = -1;
    }
    v7 = (struct _TP_IO *)*((_QWORD *)this + 2);
    if ( v7 )
    {
      WaitForThreadpoolIoCallbacks(v7, 0);
      v8 = (struct _TP_IO *)*((_QWORD *)this + 2);
      if ( v8 )
      {
        v9 = GetLastError();
        CloseThreadpoolIo(v8);
        SetLastError(v9);
      }
      *((_QWORD *)this + 2) = 0;
    }
  }
}

```

## disassembly

```asm
0x1400f3730  push    rbx
0x1400f3732  push    rbp
0x1400f3733  push    rsi
0x1400f3734  push    rdi
0x1400f3735  sub     rsp, 38h
0x1400f3739  lea     rbx, [rcx+20h]
0x1400f373d  mov     rdi, rcx
0x1400f3740  mov     rcx, rbx; SRWLock
0x1400f3743  xor     sil, sil
0x1400f3746  call    cs:__imp_AcquireSRWLockExclusive
0x1400f374c  cmp     dword ptr [rdi+2Ch], 7
0x1400f3750  jz      short loc_1400F378F
0x1400f3752  mov     sil, 1
0x1400f3755  mov     dword ptr [rdi+2Ch], 7
0x1400f375c  jmp     short loc_1400F3772
0x1400f375e  xor     r9d, r9d; Flags
0x1400f3761  lea     rcx, [rdi+30h]; ConditionVariable
0x1400f3765  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1400f3769  mov     rdx, rbx; SRWLock
0x1400f376c  call    cs:__imp_SleepConditionVariableSRW
0x1400f3772  cmp     dword ptr [rdi+38h], 0
0x1400f3776  ja      short loc_1400F375E
0x1400f3778  lea     r8, [rdi+60h]
0x1400f377c  mov     [rsp+58h+var_38], rdi
0x1400f3781  lea     rdx, [rdi+68h]
0x1400f3785  lea     rcx, [rsp+58h+var_38]
0x1400f378a  call    ??$Transport_IoSummary@PEAVPipeTransport@@AEA_KAEA_K@TraceProvider@Diagnostics@ComputeService@@SAX$$QEAPEAVPipeTransport@@AEA_K1@Z; ComputeService::Diagnostics::TraceProvider::Transport_IoSummary<PipeTransport *,unsigned __int64 &,unsigned __int64 &>(PipeTransport * &&,unsigned __int64 &,unsigned __int64 &)
0x1400f378f  test    rbx, rbx
0x1400f3792  jz      short loc_1400F379D
0x1400f3794  mov     rcx, rbx; SRWLock
0x1400f3797  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f379d  test    sil, sil
0x1400f37a0  jz      loc_1400F382F
0x1400f37a6  mov     rcx, [rdi+8]; hFile
0x1400f37aa  lea     rax, [rcx+1]
0x1400f37ae  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400f37b4  jz      short loc_1400F37F4
0x1400f37b6  cmp     qword ptr [rdi+10h], 0
0x1400f37bb  jz      short loc_1400F37C5
0x1400f37bd  xor     edx, edx; lpOverlapped
0x1400f37bf  call    cs:__imp_CancelIoEx
0x1400f37c5  mov     rsi, [rdi+8]
0x1400f37c9  lea     rax, [rsi-1]
0x1400f37cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400f37d1  ja      short loc_1400F37EC
0x1400f37d3  call    cs:__imp_GetLastError
0x1400f37d9  mov     rcx, rsi; hObject
0x1400f37dc  mov     ebx, eax
0x1400f37de  call    cs:__imp_CloseHandle
0x1400f37e4  mov     ecx, ebx; dwErrCode
0x1400f37e6  call    cs:__imp_SetLastError
0x1400f37ec  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1400f37f4  mov     rcx, [rdi+10h]; pio
0x1400f37f8  test    rcx, rcx
0x1400f37fb  jz      short loc_1400F382F
0x1400f37fd  xor     edx, edx; fCancelPendingCallbacks
0x1400f37ff  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1400f3805  mov     rsi, [rdi+10h]
0x1400f3809  test    rsi, rsi
0x1400f380c  jz      short loc_1400F3827
0x1400f380e  call    cs:__imp_GetLastError
0x1400f3814  mov     rcx, rsi; pio
0x1400f3817  mov     ebx, eax
0x1400f3819  call    cs:__imp_CloseThreadpoolIo
0x1400f381f  mov     ecx, ebx; dwErrCode
0x1400f3821  call    cs:__imp_SetLastError
0x1400f3827  mov     qword ptr [rdi+10h], 0
0x1400f382f  add     rsp, 38h
0x1400f3833  pop     rdi
0x1400f3834  pop     rsi
0x1400f3835  pop     rbp
0x1400f3836  pop     rbx
0x1400f3837  retn
```
