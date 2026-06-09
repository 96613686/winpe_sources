# HTTP_LOG_PIPE_CLIENT::~HTTP_LOG_PIPE_CLIENT(void)

- ea: `0x180008dac`
- end: `0x180008ee1`
- name: `??1HTTP_LOG_PIPE_CLIENT@@UEAA@XZ`
- size: `309`
- prototype: `void __fastcall(HTTP_LOG_PIPE_CLIENT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008f90`

## callees

- `0x180008dac`
- `0x180009d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008e7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008e7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008ebe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180008e2a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180008e2a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180008e1d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180008e1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180008e0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180008e0e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008e89`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008e89`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008e96`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008e96`

## pseudocode

```c
void __fastcall HTTP_LOG_PIPE_CLIENT::~HTTP_LOG_PIPE_CLIENT(HTTP_LOG_PIPE_CLIENT *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  char *v5; // rcx

  *(_QWORD *)this = &HTTP_LOG_PIPE_CLIENT::`vftable'{for `STTABLE_ITEM'};
  *((_QWORD *)this + 16) = &HTTP_LOG_PIPE_CLIENT::`vftable'{for `IPM2_MESSAGE_ACCEPTOR'};
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  if ( *((_QWORD *)this + 42) )
    HTTP_LOG_PIPE_CLIENT::Shutdown(this, 1);
  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 22);
  if ( v2 )
  {
    SetThreadpoolWait(v2, 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 22), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 22));
    *((_QWORD *)this + 22) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 24);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 24) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 21);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 21) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 80352));
  STRU::~STRU((HTTP_LOG_PIPE_CLIENT *)((char *)this + 280));
  STRA::~STRA((HTTP_LOG_PIPE_CLIENT *)((char *)this + 224));
  *(_QWORD *)this = &STTABLE_ITEM::`vftable';
  *((_QWORD *)this + 4) = &STBUFF::`vftable';
  v5 = (char *)*((_QWORD *)this + 5);
  if ( v5 != (char *)this + 60 )
  {
    LocalFree(v5);
    *((_QWORD *)this + 5) = (char *)this + 60;
    *((_DWORD *)this + 13) = 64;
  }
  *((_DWORD *)this + 12) = 0;
}

```

## disassembly

```asm
0x180008dac  mov     [rsp+arg_0], rbx
0x180008db1  push    rdi
0x180008db2  sub     rsp, 20h
0x180008db6  mov     rbx, rcx
0x180008db9  lea     rax, ??_7HTTP_LOG_PIPE_CLIENT@@6BSTTABLE_ITEM@@@; const HTTP_LOG_PIPE_CLIENT::`vftable'{for `STTABLE_ITEM'}
0x180008dc0  mov     [rcx], rax
0x180008dc3  lea     rax, ??_7HTTP_LOG_PIPE_CLIENT@@6BIPM2_MESSAGE_ACCEPTOR@@@; const HTTP_LOG_PIPE_CLIENT::`vftable'{for `IPM2_MESSAGE_ACCEPTOR'}
0x180008dca  mov     [rcx+80h], rax
0x180008dd1  mov     qword ptr [rcx+88h], 0
0x180008ddc  mov     qword ptr [rcx+90h], 0
0x180008de7  mov     edi, 1
0x180008dec  cmp     qword ptr [rcx+150h], 0
0x180008df4  jz      short loc_180008DFD
0x180008df6  mov     edx, edi; int
0x180008df8  call    ?Shutdown@HTTP_LOG_PIPE_CLIENT@@QEAAXJ@Z; HTTP_LOG_PIPE_CLIENT::Shutdown(long)
0x180008dfd  mov     rcx, [rbx+0B0h]; pwa
0x180008e04  test    rcx, rcx
0x180008e07  jz      short loc_180008E3B
0x180008e09  xor     r8d, r8d; pftTimeout
0x180008e0c  xor     edx, edx; h
0x180008e0e  call    cs:__imp_SetThreadpoolWait
0x180008e14  mov     edx, edi; fCancelPendingCallbacks
0x180008e16  mov     rcx, [rbx+0B0h]; pwa
0x180008e1d  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180008e23  mov     rcx, [rbx+0B0h]; pwa
0x180008e2a  call    cs:__imp_CloseThreadpoolWait
0x180008e30  mov     qword ptr [rbx+0B0h], 0
0x180008e3b  mov     rcx, [rbx+0C0h]; hObject
0x180008e42  test    rcx, rcx
0x180008e45  jz      short loc_180008E58
0x180008e47  call    cs:__imp_CloseHandle
0x180008e4d  mov     qword ptr [rbx+0C0h], 0
0x180008e58  mov     rcx, [rbx+0A8h]; hObject
0x180008e5f  test    rcx, rcx
0x180008e62  jz      short loc_180008E75
0x180008e64  call    cs:__imp_CloseHandle
0x180008e6a  mov     qword ptr [rbx+0A8h], 0
0x180008e75  lea     rcx, [rbx+139E0h]; lpCriticalSection
0x180008e7c  call    cs:__imp_DeleteCriticalSection
0x180008e82  lea     rcx, [rbx+118h]
0x180008e89  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008e8f  lea     rcx, [rbx+0E0h]
0x180008e96  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008e9c  lea     rax, ??_7STTABLE_ITEM@@6B@; const STTABLE_ITEM::`vftable'
0x180008ea3  mov     [rbx], rax
0x180008ea6  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180008ead  mov     [rbx+20h], rax
0x180008eb1  lea     rdi, [rbx+3Ch]
0x180008eb5  mov     rcx, [rbx+28h]; hMem
0x180008eb9  cmp     rcx, rdi
0x180008ebc  jz      short loc_180008ECF
0x180008ebe  call    cs:__imp_LocalFree
0x180008ec4  mov     [rbx+28h], rdi
0x180008ec8  mov     dword ptr [rbx+34h], 40h ; '@'
0x180008ecf  mov     dword ptr [rbx+30h], 0
0x180008ed6  mov     rbx, [rsp+28h+arg_0]
0x180008edb  add     rsp, 20h
0x180008edf  pop     rdi
0x180008ee0  retn
```
