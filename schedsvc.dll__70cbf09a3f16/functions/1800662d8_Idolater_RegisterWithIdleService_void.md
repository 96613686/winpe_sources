# Idolater::RegisterWithIdleService(void)

- ea: `0x1800662d8`
- end: `0x180066497`
- name: `?RegisterWithIdleService@Idolater@@AEAAJXZ`
- size: `447`
- prototype: `__int64 __fastcall(Idolater *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180066228`

## callees

- `0x180039d00`
- `0x1800662d8`
- `0x18007484c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066328`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800663ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066484`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800663ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066484`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800662f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800662f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066307`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006636e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066307`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006636e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18006640b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18006644b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18006640b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18006644b`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180066352`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800663ac`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180066352`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800663ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Idolater::RegisterWithIdleService(Idolater *this)
{
  HANDLE EventW; // rbx
  signed int LastError; // eax
  unsigned int v3; // ebx
  HANDLE v4; // rbx

  EnterCriticalSection(&stru_1800BD590);
  EventW = CreateEventW(0, 0, 0, 0);
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&hSourceHandle);
  hSourceHandle = EventW;
  if ( EventW
    && (*(&xmmword_1800BD570 + 1) = RegisterWaitForSingleObjectEx(
                                      EventW,
                                      Idolater::IdleStartCallback,
                                      &g_Idolater,
                                      0xFFFFFFFFLL,
                                      0)) != 0
    && (v4 = CreateEventW(0, 0, 0, 0),
        wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&xmmword_1800BD570),
        (xmmword_1800BD570 = v4) != 0)
    && (WaitHandle = (HANDLE)RegisterWaitForSingleObjectEx(v4, Idolater::IdleEndCallback, &g_Idolater, 0xFFFFFFFFLL, 0)) != 0 )
  {
    LastError = ItSrvSetTSchedHandle(hSourceHandle, xmmword_1800BD570);
    v3 = LastError;
    if ( !LastError )
    {
      v3 = 0;
      LeaveCriticalSection(&stru_1800BD590);
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
  LeaveCriticalSection(&stru_1800BD590);
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( *(&xmmword_1800BD570 + 1) )
    {
      UnregisterWaitEx(*(&xmmword_1800BD570 + 1), 0);
      *(&xmmword_1800BD570 + 1) = 0;
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
    if ( xmmword_1800BD570 )
    {
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&xmmword_1800BD570);
      xmmword_1800BD570 = 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800662d8  mov     [rsp+arg_8], rbx
0x1800662dd  mov     [rsp+arg_0], rcx
0x1800662e2  push    rsi
0x1800662e3  sub     rsp, 30h
0x1800662e7  lea     rsi, stru_1800BD590
0x1800662ee  mov     [rsp+38h+arg_0], rsi
0x1800662f3  mov     rcx, rsi; lpCriticalSection
0x1800662f6  call    cs:__imp_EnterCriticalSection
0x1800662fc  nop
0x1800662fd  xor     r9d, r9d; lpName
0x180066300  xor     r8d, r8d; bInitialState
0x180066303  xor     edx, edx; bManualReset
0x180066305  xor     ecx, ecx; lpEventAttributes
0x180066307  call    cs:__imp_CreateEventW
0x18006630d  mov     rbx, rax
0x180066310  lea     rcx, hSourceHandle; this
0x180066317  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18006631c  mov     cs:hSourceHandle, rbx
0x180066323  test    rbx, rbx
0x180066326  jnz     short loc_180066335
0x180066328  call    cs:__imp_GetLastError
0x18006632e  mov     ebx, eax
0x180066330  jmp     loc_1800663DF
0x180066335  mov     [rsp+38h+var_18], 0
0x18006633d  or      r9d, 0FFFFFFFFh
0x180066341  lea     r8, ?g_Idolater@@3VIdolater@@A; Idolater g_Idolater
0x180066348  lea     rdx, ?IdleStartCallback@Idolater@@CAXPEAXE@Z; Idolater::IdleStartCallback(void *,uchar)
0x18006634f  mov     rcx, rbx
0x180066352  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180066358  mov     qword ptr cs:xmmword_1800BD570+8, rax
0x18006635f  test    rax, rax
0x180066362  jz      short loc_180066328
0x180066364  xor     r9d, r9d; lpName
0x180066367  xor     r8d, r8d; bInitialState
0x18006636a  xor     edx, edx; bManualReset
0x18006636c  xor     ecx, ecx; lpEventAttributes
0x18006636e  call    cs:__imp_CreateEventW
0x180066374  mov     rbx, rax
0x180066377  lea     rcx, xmmword_1800BD570; this
0x18006637e  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180066383  mov     qword ptr cs:xmmword_1800BD570, rbx
0x18006638a  test    rbx, rbx
0x18006638d  jz      short loc_180066328
0x18006638f  mov     [rsp+38h+var_18], 0
0x180066397  or      r9d, 0FFFFFFFFh
0x18006639b  lea     r8, ?g_Idolater@@3VIdolater@@A; Idolater g_Idolater
0x1800663a2  lea     rdx, ?IdleEndCallback@Idolater@@CAXPEAXE@Z; Idolater::IdleEndCallback(void *,uchar)
0x1800663a9  mov     rcx, rbx
0x1800663ac  call    cs:__imp_RegisterWaitForSingleObjectEx
0x1800663b2  mov     qword ptr cs:WaitHandle, rax
0x1800663b9  test    rax, rax
0x1800663bc  jz      loc_180066328
0x1800663c2  mov     rdx, qword ptr cs:xmmword_1800BD570; HANDLE
0x1800663c9  mov     rcx, cs:hSourceHandle; hSourceHandle
0x1800663d0  call    ItSrvSetTSchedHandle
0x1800663d5  mov     ebx, eax
0x1800663d7  test    eax, eax
0x1800663d9  jz      loc_18006647F
0x1800663df  test    eax, eax
0x1800663e1  jle     short loc_1800663EC
0x1800663e3  movzx   ebx, ax
0x1800663e6  or      ebx, 80070000h
0x1800663ec  mov     rcx, rsi; lpCriticalSection
0x1800663ef  call    cs:__imp_LeaveCriticalSection
0x1800663f5  test    ebx, ebx
0x1800663f7  jns     loc_18006648A
0x1800663fd  mov     rcx, qword ptr cs:xmmword_1800BD570+8; WaitHandle
0x180066404  test    rcx, rcx
0x180066407  jz      short loc_18006641C
0x180066409  xor     edx, edx; CompletionEvent
0x18006640b  call    cs:__imp_UnregisterWaitEx
0x180066411  mov     qword ptr cs:xmmword_1800BD570+8, 0
0x18006641c  cmp     cs:hSourceHandle, 0
0x180066424  jz      short loc_18006643D
0x180066426  lea     rcx, hSourceHandle; this
0x18006642d  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180066432  mov     cs:hSourceHandle, 0
0x18006643d  mov     rcx, qword ptr cs:WaitHandle; WaitHandle
0x180066444  test    rcx, rcx
0x180066447  jz      short loc_18006645C
0x180066449  xor     edx, edx; CompletionEvent
0x18006644b  call    cs:__imp_UnregisterWaitEx
0x180066451  mov     qword ptr cs:WaitHandle, 0
0x18006645c  cmp     qword ptr cs:xmmword_1800BD570, 0
0x180066464  jz      short loc_18006648A
0x180066466  lea     rcx, xmmword_1800BD570; this
0x18006646d  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180066472  mov     qword ptr cs:xmmword_1800BD570, 0
0x18006647d  jmp     short loc_18006648A
0x18006647f  xor     ebx, ebx
0x180066481  mov     rcx, rsi; lpCriticalSection
0x180066484  call    cs:__imp_LeaveCriticalSection
0x18006648a  mov     eax, ebx
0x18006648c  mov     rbx, [rsp+38h+arg_8]
0x180066491  add     rsp, 30h
0x180066495  pop     rsi
0x180066496  retn
```
