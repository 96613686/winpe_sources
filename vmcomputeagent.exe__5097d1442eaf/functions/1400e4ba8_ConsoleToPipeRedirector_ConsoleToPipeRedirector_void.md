# ConsoleToPipeRedirector::~ConsoleToPipeRedirector(void)

- ea: `0x1400e4ba8`
- end: `0x1400e4c77`
- name: `??1ConsoleToPipeRedirector@@QEAA@XZ`
- size: `207`
- prototype: `void __fastcall(ConsoleToPipeRedirector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400dfe6c`
- `0x1400dff68`

## callees

- `0x1400e4ba8`
- `0x1400e8290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e4bf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e4bf0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400e4bdb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400e4bdb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400e4c0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400e4c0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400e4c21`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400e4c21`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1400e4bce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1400e4bce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400e4c30`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400e4c30`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400e4c18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400e4c18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e4c44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e4c58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e4c44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e4c58`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1400e4bc2`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1400e4bc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConsoleToPipeRedirector::~ConsoleToPipeRedirector(ConsoleToPipeRedirector *this)
{
  struct _TP_TIMER *v2; // rdi
  struct _TP_IO *v3; // rcx
  char *v4; // rcx
  char *v5; // rcx

  if ( *((_QWORD *)this + 8) )
  {
    CancelIoEx(*((HANDLE *)this + 6), 0);
    WaitForThreadpoolIoCallbacks(*((PTP_IO *)this + 8), 0);
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 5);
  *((_DWORD *)this + 3) = 0;
  if ( this != (ConsoleToPipeRedirector *)-40LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 9), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
  }
  v3 = (struct _TP_IO *)*((_QWORD *)this + 8);
  if ( v3 )
    CloseThreadpoolIo(v3);
  v4 = (char *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = (char *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( *(_QWORD *)this )
    CsCloseConsole(*(PVOID *)this);
}

```

## disassembly

```asm
0x1400e4ba8  mov     [rsp+arg_8], rbx
0x1400e4bad  push    rdi
0x1400e4bae  sub     rsp, 20h
0x1400e4bb2  mov     rbx, rcx
0x1400e4bb5  cmp     qword ptr [rcx+40h], 0
0x1400e4bba  jz      short loc_1400E4BD4
0x1400e4bbc  xor     edx, edx; lpOverlapped
0x1400e4bbe  mov     rcx, [rcx+30h]; hFile
0x1400e4bc2  call    cs:__imp_CancelIoEx
0x1400e4bc8  xor     edx, edx; fCancelPendingCallbacks
0x1400e4bca  mov     rcx, [rbx+40h]; pio
0x1400e4bce  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1400e4bd4  lea     rdi, [rbx+28h]
0x1400e4bd8  mov     rcx, rdi; SRWLock
0x1400e4bdb  call    cs:__imp_AcquireSRWLockExclusive
0x1400e4be1  mov     dword ptr [rbx+0Ch], 0
0x1400e4be8  test    rdi, rdi
0x1400e4beb  jz      short loc_1400E4BF6
0x1400e4bed  mov     rcx, rdi; SRWLock
0x1400e4bf0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400e4bf6  mov     rdi, [rbx+48h]
0x1400e4bfa  test    rdi, rdi
0x1400e4bfd  jz      short loc_1400E4C27
0x1400e4bff  xor     r9d, r9d; msWindowLength
0x1400e4c02  xor     r8d, r8d; msPeriod
0x1400e4c05  xor     edx, edx; pftDueTime
0x1400e4c07  mov     rcx, rdi; pti
0x1400e4c0a  call    cs:__imp_SetThreadpoolTimer
0x1400e4c10  mov     edx, 1; fCancelPendingCallbacks
0x1400e4c15  mov     rcx, rdi; pti
0x1400e4c18  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400e4c1e  mov     rcx, rdi; pti
0x1400e4c21  call    cs:__imp_CloseThreadpoolTimer
0x1400e4c27  mov     rcx, [rbx+40h]; pio
0x1400e4c2b  test    rcx, rcx
0x1400e4c2e  jz      short loc_1400E4C36
0x1400e4c30  call    cs:__imp_CloseThreadpoolIo
0x1400e4c36  mov     rcx, [rbx+38h]; hObject
0x1400e4c3a  lea     rax, [rcx-1]
0x1400e4c3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e4c42  ja      short loc_1400E4C4A
0x1400e4c44  call    cs:__imp_CloseHandle
0x1400e4c4a  mov     rcx, [rbx+30h]; hObject
0x1400e4c4e  lea     rax, [rcx-1]
0x1400e4c52  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e4c56  ja      short loc_1400E4C5E
0x1400e4c58  call    cs:__imp_CloseHandle
0x1400e4c5e  mov     rcx, [rbx]; P
0x1400e4c61  test    rcx, rcx
0x1400e4c64  jz      short loc_1400E4C6C
0x1400e4c66  call    CsCloseConsole
0x1400e4c6b  nop
0x1400e4c6c  mov     rbx, [rsp+28h+arg_8]
0x1400e4c71  add     rsp, 20h
0x1400e4c75  pop     rdi
0x1400e4c76  retn
```
