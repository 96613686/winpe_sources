# Idolater::RegisterWithIdleService(void)

- ea: `0x180069484`
- end: `0x180069680`
- name: `?RegisterWithIdleService@Idolater@@AEAAJXZ`
- size: `508`
- prototype: `__int64 __fastcall(Idolater *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800693b4`

## callees

- `0x180024730`
- `0x180069484`
- `0x180078700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800694e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800694e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800695bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180069666`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800695bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180069666`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800694a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800694a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800694b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069532`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800694b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069532`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800695e1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180069627`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800695e1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180069627`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180069510`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180069576`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180069510`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180069576`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Idolater::RegisterWithIdleService(Idolater *this)
{
  HANDLE EventW; // rbx
  signed int LastError; // eax
  unsigned int v3; // ebx
  HANDLE v4; // rbx

  EnterCriticalSection(&stru_1800C1690);
  EventW = CreateEventW(0, 0, 0, 0);
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&hSourceHandle);
  hSourceHandle = EventW;
  if ( EventW
    && (*(&xmmword_1800C1670 + 1) = RegisterWaitForSingleObjectEx(
                                      EventW,
                                      Idolater::IdleStartCallback,
                                      &g_Idolater,
                                      0xFFFFFFFFLL,
                                      0)) != 0
    && (v4 = CreateEventW(0, 0, 0, 0),
        wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&xmmword_1800C1670),
        (xmmword_1800C1670 = v4) != 0)
    && (WaitHandle = (HANDLE)RegisterWaitForSingleObjectEx(v4, Idolater::IdleEndCallback, &g_Idolater, 0xFFFFFFFFLL, 0)) != 0 )
  {
    LastError = ItSrvSetTSchedHandle(hSourceHandle, xmmword_1800C1670);
    v3 = LastError;
    if ( !LastError )
    {
      v3 = 0;
      LeaveCriticalSection(&stru_1800C1690);
      return v3;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
  }
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  LeaveCriticalSection(&stru_1800C1690);
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( *(&xmmword_1800C1670 + 1) )
    {
      UnregisterWaitEx(*(&xmmword_1800C1670 + 1), 0);
      *(&xmmword_1800C1670 + 1) = 0;
    }
    if ( hSourceHandle )
    {
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&hSourceHandle);
      hSourceHandle = 0;
    }
    if ( WaitHandle )
    {
      UnregisterWaitEx(WaitHandle, 0);
      WaitHandle = 0;
    }
    if ( xmmword_1800C1670 )
    {
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&xmmword_1800C1670);
      xmmword_1800C1670 = 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180069484  mov     [rsp+arg_8], rbx
0x180069489  mov     [rsp+arg_0], rcx
0x18006948e  push    rsi
0x18006948f  sub     rsp, 30h
0x180069493  lea     rsi, stru_1800C1690
0x18006949a  mov     [rsp+38h+arg_0], rsi
0x18006949f  mov     rcx, rsi; lpCriticalSection
0x1800694a2  call    cs:__imp_EnterCriticalSection
0x1800694a9  nop     dword ptr [rax+rax+00h]
0x1800694ae  nop
0x1800694af  xor     r9d, r9d; lpName
0x1800694b2  xor     r8d, r8d; bInitialState
0x1800694b5  xor     edx, edx; bManualReset
0x1800694b7  xor     ecx, ecx; lpEventAttributes
0x1800694b9  call    cs:__imp_CreateEventW
0x1800694c0  nop     dword ptr [rax+rax+00h]
0x1800694c5  mov     rbx, rax
0x1800694c8  lea     rcx, hSourceHandle; this
0x1800694cf  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x1800694d4  mov     cs:hSourceHandle, rbx
0x1800694db  test    rbx, rbx
0x1800694de  jnz     short loc_1800694F3
0x1800694e0  call    cs:__imp_GetLastError
0x1800694e7  nop     dword ptr [rax+rax+00h]
0x1800694ec  mov     ebx, eax
0x1800694ee  jmp     loc_1800695AF
0x1800694f3  mov     [rsp+38h+var_18], 0
0x1800694fb  or      r9d, 0FFFFFFFFh
0x1800694ff  lea     r8, ?g_Idolater@@3VIdolater@@A; Idolater g_Idolater
0x180069506  lea     rdx, ?IdleStartCallback@Idolater@@CAXPEAXE@Z; Idolater::IdleStartCallback(void *,uchar)
0x18006950d  mov     rcx, rbx
0x180069510  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180069517  nop     dword ptr [rax+rax+00h]
0x18006951c  mov     qword ptr cs:xmmword_1800C1670+8, rax
0x180069523  test    rax, rax
0x180069526  jz      short loc_1800694E0
0x180069528  xor     r9d, r9d; lpName
0x18006952b  xor     r8d, r8d; bInitialState
0x18006952e  xor     edx, edx; bManualReset
0x180069530  xor     ecx, ecx; lpEventAttributes
0x180069532  call    cs:__imp_CreateEventW
0x180069539  nop     dword ptr [rax+rax+00h]
0x18006953e  mov     rbx, rax
0x180069541  lea     rcx, xmmword_1800C1670; this
0x180069548  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18006954d  mov     qword ptr cs:xmmword_1800C1670, rbx
0x180069554  test    rbx, rbx
0x180069557  jz      short loc_1800694E0
0x180069559  mov     [rsp+38h+var_18], 0
0x180069561  or      r9d, 0FFFFFFFFh
0x180069565  lea     r8, ?g_Idolater@@3VIdolater@@A; Idolater g_Idolater
0x18006956c  lea     rdx, ?IdleEndCallback@Idolater@@CAXPEAXE@Z; Idolater::IdleEndCallback(void *,uchar)
0x180069573  mov     rcx, rbx
0x180069576  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18006957d  nop     dword ptr [rax+rax+00h]
0x180069582  mov     qword ptr cs:WaitHandle, rax
0x180069589  test    rax, rax
0x18006958c  jz      loc_1800694E0
0x180069592  mov     rdx, qword ptr cs:xmmword_1800C1670; HANDLE
0x180069599  mov     rcx, cs:hSourceHandle; hSourceHandle
0x1800695a0  call    ItSrvSetTSchedHandle
0x1800695a5  mov     ebx, eax
0x1800695a7  test    eax, eax
0x1800695a9  jz      loc_180069661
0x1800695af  test    eax, eax
0x1800695b1  jle     short loc_1800695BC
0x1800695b3  movzx   ebx, ax
0x1800695b6  or      ebx, 80070000h
0x1800695bc  mov     rcx, rsi; lpCriticalSection
0x1800695bf  call    cs:__imp_LeaveCriticalSection
0x1800695c6  nop     dword ptr [rax+rax+00h]
0x1800695cb  test    ebx, ebx
0x1800695cd  jns     loc_180069672
0x1800695d3  mov     rcx, qword ptr cs:xmmword_1800C1670+8; WaitHandle
0x1800695da  test    rcx, rcx
0x1800695dd  jz      short loc_1800695F8
0x1800695df  xor     edx, edx; CompletionEvent
0x1800695e1  call    cs:__imp_UnregisterWaitEx
0x1800695e8  nop     dword ptr [rax+rax+00h]
0x1800695ed  mov     qword ptr cs:xmmword_1800C1670+8, 0
0x1800695f8  cmp     cs:hSourceHandle, 0
0x180069600  jz      short loc_180069619
0x180069602  lea     rcx, hSourceHandle; this
0x180069609  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18006960e  mov     cs:hSourceHandle, 0
0x180069619  mov     rcx, qword ptr cs:WaitHandle; WaitHandle
0x180069620  test    rcx, rcx
0x180069623  jz      short loc_18006963E
0x180069625  xor     edx, edx; CompletionEvent
0x180069627  call    cs:__imp_UnregisterWaitEx
0x18006962e  nop     dword ptr [rax+rax+00h]
0x180069633  mov     qword ptr cs:WaitHandle, 0
0x18006963e  cmp     qword ptr cs:xmmword_1800C1670, 0
0x180069646  jz      short loc_180069672
0x180069648  lea     rcx, xmmword_1800C1670; this
0x18006964f  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180069654  mov     qword ptr cs:xmmword_1800C1670, 0
0x18006965f  jmp     short loc_180069672
0x180069661  xor     ebx, ebx
0x180069663  mov     rcx, rsi; lpCriticalSection
0x180069666  call    cs:__imp_LeaveCriticalSection
0x18006966d  nop     dword ptr [rax+rax+00h]
0x180069672  mov     eax, ebx
0x180069674  mov     rbx, [rsp+38h+arg_8]
0x180069679  add     rsp, 30h
0x18006967d  pop     rsi
0x18006967e  retn
```
