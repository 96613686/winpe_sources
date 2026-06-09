# SVSThreadPool::Worker(void)

- ea: `0x1800239c0`
- end: `0x180023b5c`
- name: `?Worker@SVSThreadPool@@IEAAXXZ`
- size: `412`
- prototype: `void __fastcall(SVSThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004f3c0`

## callees

- `0x1800239c0`
- `0x180023b64`
- `0x180023c40`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023ab9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023ab9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023ad9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023ad9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023a0d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023a0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023ac3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023b08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023b54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023ac3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023b08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023b54`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023b30`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023b30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023b3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023b3e`

## pseudocode

```c
void __fastcall SVSThreadPool::Worker(SVSThreadPool *this)
{
  void *v2; // rsi
  int v3; // r14d
  DWORD DelayUntilNextEvent; // ebp
  struct SVSThreadBlock *NextJobFromQueue; // rsi
  struct SVSThreadBlock **v6; // r14
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  HANDLE Thread; // rax

  if ( *((_DWORD *)this + 22) )
  {
    while ( 1 )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 27, 1, 0) )
      {
        v2 = (void *)*((_QWORD *)this + 9);
        v3 = 0;
        DelayUntilNextEvent = 300000;
      }
      else
      {
        v2 = (void *)*((_QWORD *)this + 10);
        v3 = 1;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        DelayUntilNextEvent = SVSThreadPool::GetDelayUntilNextEvent(this);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      }
      if ( WaitForSingleObject(v2, DelayUntilNextEvent) == 258 )
        break;
      if ( v3 )
        goto LABEL_10;
LABEL_6:
      if ( !*((_DWORD *)this + 22) )
        goto LABEL_7;
    }
    if ( !v3 )
      goto LABEL_7;
LABEL_10:
    *((_DWORD *)this + 27) = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    NextJobFromQueue = SVSThreadPool::GetNextJobFromQueue(this);
    if ( NextJobFromQueue )
    {
      ++*((_DWORD *)this + 24);
      if ( --*((_DWORD *)this + 25) )
      {
        SetEvent(*((HANDLE *)this + 9));
      }
      else if ( *((_DWORD *)this + 24) < *((_DWORD *)this + 23) )
      {
        Thread = CreateThread(0, 0, SVSThreadPool::SVSThreadPoolWorkerThread, this, 0, 0);
        if ( Thread )
        {
          CloseHandle(Thread);
          ++*((_DWORD *)this + 25);
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      (*(void (__fastcall **)(_QWORD))NextJobFromQueue)(*((_QWORD *)NextJobFromQueue + 1));
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      v6 = (struct SVSThreadBlock **)*((_QWORD *)this + 8);
      v7 = (struct _RTL_CRITICAL_SECTION *)v6[2];
      if ( v7 )
        EnterCriticalSection(v7);
      *(_QWORD *)NextJobFromQueue = *v6;
      v8 = (struct _RTL_CRITICAL_SECTION *)v6[2];
      *v6 = NextJobFromQueue;
      if ( v8 )
        LeaveCriticalSection(v8);
      ++*((_DWORD *)this + 25);
      --*((_DWORD *)this + 24);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    goto LABEL_6;
  }
LABEL_7:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  --*((_DWORD *)this + 25);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x1800239c0  push    rbx
0x1800239c2  push    rdi
0x1800239c3  sub     rsp, 38h
0x1800239c7  cmp     dword ptr [rcx+58h], 0
0x1800239cb  mov     rbx, rcx
0x1800239ce  jz      short loc_180023A3E
0x1800239d0  mov     [rsp+48h+arg_0], rbp
0x1800239d5  mov     [rsp+48h+arg_8], rsi
0x1800239da  mov     [rsp+48h+arg_10], r12
0x1800239df  xor     r12d, r12d
0x1800239e2  mov     [rsp+48h+var_18], r15
0x1800239e7  mov     r15d, 1
0x1800239ed  mov     [rsp+48h+arg_18], r14
0x1800239f2  xor     eax, eax
0x1800239f4  lock cmpxchg [rbx+6Ch], r15d
0x1800239fa  jz      short loc_180023A5C
0x1800239fc  mov     rsi, [rbx+48h]
0x180023a00  mov     r14d, r12d
0x180023a03  mov     ebp, 493E0h
0x180023a08  mov     edx, ebp; dwMilliseconds
0x180023a0a  mov     rcx, rsi; hHandle
0x180023a0d  call    cs:__imp_WaitForSingleObject
0x180023a13  cmp     eax, 102h
0x180023a18  jz      short loc_180023A83
0x180023a1a  test    r14d, r14d
0x180023a1d  jnz     short loc_180023A88
0x180023a1f  cmp     [rbx+58h], r12d
0x180023a23  jnz     short loc_1800239F2
0x180023a25  mov     r14, [rsp+48h+arg_18]
0x180023a2a  mov     r12, [rsp+48h+arg_10]
0x180023a2f  mov     rsi, [rsp+48h+arg_8]
0x180023a34  mov     rbp, [rsp+48h+arg_0]
0x180023a39  mov     r15, [rsp+48h+var_18]
0x180023a3e  lea     rcx, [rbx+18h]; lpCriticalSection
0x180023a42  call    cs:__imp_EnterCriticalSection
0x180023a48  dec     dword ptr [rbx+64h]
0x180023a4b  lea     rcx, [rbx+18h]
0x180023a4f  add     rsp, 38h
0x180023a53  pop     rdi
0x180023a54  pop     rbx
0x180023a55  jmp     cs:__imp_LeaveCriticalSection
0x180023a5c  mov     rsi, [rbx+50h]
0x180023a60  lea     rcx, [rbx+18h]; lpCriticalSection
0x180023a64  mov     r14d, r15d
0x180023a67  call    cs:__imp_EnterCriticalSection
0x180023a6d  mov     rcx, rbx; this
0x180023a70  call    ?GetDelayUntilNextEvent@SVSThreadPool@@IEAAKXZ; SVSThreadPool::GetDelayUntilNextEvent(void)
0x180023a75  lea     rcx, [rbx+18h]; lpCriticalSection
0x180023a79  mov     ebp, eax
0x180023a7b  call    cs:__imp_LeaveCriticalSection
0x180023a81  jmp     short loc_180023A08
0x180023a83  test    r14d, r14d
0x180023a86  jz      short loc_180023A25
0x180023a88  lea     rcx, [rbx+18h]; lpCriticalSection
0x180023a8c  mov     [rbx+6Ch], r12d
0x180023a90  call    cs:__imp_EnterCriticalSection
0x180023a96  mov     rcx, rbx; this
0x180023a99  call    ?GetNextJobFromQueue@SVSThreadPool@@IEAAPEAVSVSThreadBlock@@XZ; SVSThreadPool::GetNextJobFromQueue(void)
0x180023a9e  mov     rsi, rax
0x180023aa1  test    rax, rax
0x180023aa4  jz      short loc_180023B04
0x180023aa6  inc     dword ptr [rbx+60h]
0x180023aa9  dec     dword ptr [rbx+64h]
0x180023aac  mov     eax, [rbx+60h]
0x180023aaf  cmp     [rbx+64h], r12d
0x180023ab3  jz      short loc_180023B13
0x180023ab5  mov     rcx, [rbx+48h]; hEvent
0x180023ab9  call    cs:__imp_SetEvent
0x180023abf  lea     rcx, [rbx+18h]; lpCriticalSection
0x180023ac3  call    cs:__imp_LeaveCriticalSection
0x180023ac9  mov     rcx, [rsi+8]
0x180023acd  mov     rax, [rsi]
0x180023ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ad5  lea     rcx, [rbx+18h]; lpCriticalSection
0x180023ad9  call    cs:__imp_EnterCriticalSection
0x180023adf  mov     r14, [rbx+40h]
0x180023ae3  mov     rcx, [r14+10h]; lpCriticalSection
0x180023ae7  test    rcx, rcx
0x180023aea  jnz     short loc_180023B4C
0x180023aec  mov     rax, [r14]
0x180023aef  mov     [rsi], rax
0x180023af2  mov     rcx, [r14+10h]; lpCriticalSection
0x180023af6  mov     [r14], rsi
0x180023af9  test    rcx, rcx
0x180023afc  jnz     short loc_180023B54
0x180023afe  inc     dword ptr [rbx+64h]
0x180023b01  dec     dword ptr [rbx+60h]
0x180023b04  lea     rcx, [rbx+18h]; lpCriticalSection
0x180023b08  call    cs:__imp_LeaveCriticalSection
0x180023b0e  jmp     loc_180023A1F
0x180023b13  cmp     eax, [rbx+5Ch]
0x180023b16  jnb     short loc_180023ABF
0x180023b18  mov     [rsp+48h+lpThreadId], r12; lpThreadId
0x180023b1d  lea     r8, ?SVSThreadPoolWorkerThread@SVSThreadPool@@KAKPEAX@Z; lpStartAddress
0x180023b24  mov     r9, rbx; lpParameter
0x180023b27  mov     [rsp+48h+dwCreationFlags], r12d; dwCreationFlags
0x180023b2c  xor     edx, edx; dwStackSize
0x180023b2e  xor     ecx, ecx; lpThreadAttributes
0x180023b30  call    cs:__imp_CreateThread
0x180023b36  test    rax, rax
0x180023b39  jz      short loc_180023ABF
0x180023b3b  mov     rcx, rax; hObject
0x180023b3e  call    cs:__imp_CloseHandle
0x180023b44  inc     dword ptr [rbx+64h]
0x180023b47  jmp     loc_180023ABF
0x180023b4c  call    cs:__imp_EnterCriticalSection
0x180023b52  jmp     short loc_180023AEC
0x180023b54  call    cs:__imp_LeaveCriticalSection
0x180023b5a  jmp     short loc_180023AFE
```
