# WP_RECYCLER::StartTimeBased(ulong)

- ea: `0x1800094d8`
- end: `0x180009639`
- name: `?StartTimeBased@WP_RECYCLER@@QEAAJK@Z`
- size: `353`
- prototype: `__int64 __fastcall(WP_RECYCLER *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001180`

## callees

- `0x180001f14`
- `0x1800094d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000959e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000959e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000961f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000961f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094e7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180009587`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180009587`
- `iisutil!PuDbgPrint` at `0x180009536`
- `iisutil!PuDbgPrint` at `0x180009602`
- `iisutil!PuDbgPrint` at `0x180009536`
- `iisutil!PuDbgPrint` at `0x180009602`

## string_xrefs

- `0x18000952f`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x1800095fb`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

## pseudocode

```c
__int64 __fastcall WP_RECYCLER::StartTimeBased(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx

  EnterCriticalSection(this);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
      1018,
      "WP_RECYCLER::StartTimeBased",
      "WP_RECYCLER::StartTimeBased(%d min)\n",
      a2);
  if ( LODWORD(this[3].LockSemaphore) == 1 )
    WP_RECYCLER::TerminateTimeBased((WP_RECYCLER *)this);
  if ( !a2 )
    goto LABEL_12;
  if ( CreateTimerQueueTimer(
         &this[3].OwningThread,
         0,
         WP_RECYCLER::TimerCallbackForTimeBased,
         this,
         60000 * a2,
         60000 * a2,
         0x10u) )
  {
    LODWORD(this[3].LockSemaphore) = 1;
LABEL_12:
    v5 = 0;
    goto LABEL_13;
  }
  this[3].OwningThread = 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  WP_RECYCLER::TerminateTimeBased((WP_RECYCLER *)this);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
      1070,
      "WP_RECYCLER::StartTimeBased",
      "WP_RECYCLER::StartTimeBased() failed with error hr=0x%x\n",
      v5);
LABEL_13:
  LeaveCriticalSection(this);
  return v5;
}

```

## disassembly

```asm
0x1800094d8  mov     [rsp+arg_0], rbx
0x1800094dd  push    rdi
0x1800094de  sub     rsp, 40h
0x1800094e2  mov     ebx, edx
0x1800094e4  mov     rdi, rcx
0x1800094e7  call    cs:__imp_EnterCriticalSection
0x1800094ee  nop     dword ptr [rax+rax+00h]
0x1800094f3  mov     eax, cs:g_dwDebugFlags
0x1800094f9  test    al, 3
0x1800094fb  setnz   r8b
0x1800094ff  bt      eax, 14h
0x180009503  setb    al
0x180009506  test    al, r8b
0x180009509  jz      short loc_180009542
0x18000950b  mov     rcx, cs:g_pDebug
0x180009512  lea     rax, aWpRecyclerStar_6; "WP_RECYCLER::StartTimeBased(%d min)\n"
0x180009519  mov     [rsp+48h+Period], ebx
0x18000951d  lea     r9, aWpRecyclerStar_3; "WP_RECYCLER::StartTimeBased"
0x180009524  mov     r8d, 3FAh
0x18000952a  mov     qword ptr [rsp+48h+DueTime], rax
0x18000952f  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009536  call    cs:__imp_PuDbgPrint
0x18000953d  nop     dword ptr [rax+rax+00h]
0x180009542  cmp     dword ptr [rdi+90h], 1
0x180009549  jnz     short loc_180009553
0x18000954b  mov     rcx, rdi; this
0x18000954e  call    ?TerminateTimeBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateTimeBased(void)
0x180009553  test    ebx, ebx
0x180009555  jz      loc_18000961A
0x18000955b  imul    eax, ebx, 0EA60h
0x180009561  lea     r8, ?TimerCallbackForTimeBased@WP_RECYCLER@@SAXPEAXE@Z; Callback
0x180009568  mov     [rsp+48h+Flags], 10h; Flags
0x180009570  lea     rbx, [rdi+88h]
0x180009577  mov     r9, rdi; Parameter
0x18000957a  xor     edx, edx; TimerQueue
0x18000957c  mov     rcx, rbx; phNewTimer
0x18000957f  mov     [rsp+48h+Period], eax; Period
0x180009583  mov     [rsp+48h+DueTime], eax; DueTime
0x180009587  call    cs:__imp_CreateTimerQueueTimer
0x18000958e  nop     dword ptr [rax+rax+00h]
0x180009593  test    eax, eax
0x180009595  jnz     short loc_180009610
0x180009597  mov     qword ptr [rbx], 0
0x18000959e  call    cs:__imp_GetLastError
0x1800095a5  nop     dword ptr [rax+rax+00h]
0x1800095aa  mov     ebx, eax
0x1800095ac  test    eax, eax
0x1800095ae  jle     short loc_1800095B9
0x1800095b0  movzx   ebx, ax
0x1800095b3  or      ebx, 80070000h
0x1800095b9  mov     rcx, rdi; this
0x1800095bc  call    ?TerminateTimeBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateTimeBased(void)
0x1800095c1  mov     eax, cs:g_dwDebugFlags
0x1800095c7  test    al, 3
0x1800095c9  setnz   cl
0x1800095cc  bt      eax, 14h
0x1800095d0  setb    al
0x1800095d3  test    al, cl
0x1800095d5  jz      short loc_18000961C
0x1800095d7  mov     rcx, cs:g_pDebug
0x1800095de  lea     rax, aWpRecyclerStar_9; "WP_RECYCLER::StartTimeBased() failed wi"...
0x1800095e5  mov     [rsp+48h+Period], ebx
0x1800095e9  lea     r9, aWpRecyclerStar_3; "WP_RECYCLER::StartTimeBased"
0x1800095f0  mov     r8d, 42Eh
0x1800095f6  mov     qword ptr [rsp+48h+DueTime], rax
0x1800095fb  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009602  call    cs:__imp_PuDbgPrint
0x180009609  nop     dword ptr [rax+rax+00h]
0x18000960e  jmp     short loc_18000961C
0x180009610  mov     dword ptr [rdi+90h], 1
0x18000961a  xor     ebx, ebx
0x18000961c  mov     rcx, rdi; lpCriticalSection
0x18000961f  call    cs:__imp_LeaveCriticalSection
0x180009626  nop     dword ptr [rax+rax+00h]
0x18000962b  mov     eax, ebx
0x18000962d  mov     rbx, [rsp+48h+arg_0]
0x180009632  add     rsp, 40h
0x180009636  pop     rdi
0x180009637  retn
```
