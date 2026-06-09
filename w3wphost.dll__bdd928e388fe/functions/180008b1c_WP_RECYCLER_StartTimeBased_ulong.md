# WP_RECYCLER::StartTimeBased(ulong)

- ea: `0x180008b1c`
- end: `0x180008c58`
- name: `?StartTimeBased@WP_RECYCLER@@QEAAJK@Z`
- size: `316`
- prototype: `__int64 __fastcall(WP_RECYCLER *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001170`

## callees

- `0x180001e24`
- `0x180008b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b2b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180008bbf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180008bbf`
- `iisutil!PuDbgPrint` at `0x180008b74`
- `iisutil!PuDbgPrint` at `0x180008c2e`
- `iisutil!PuDbgPrint` at `0x180008b74`
- `iisutil!PuDbgPrint` at `0x180008c2e`

## string_xrefs

- `0x180008b6d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180008c27`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

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
      "WP_RECYCLER::StartTimeBased(%d min)\n");
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
      "WP_RECYCLER::StartTimeBased() failed with error hr=0x%x\n");
LABEL_13:
  LeaveCriticalSection(this);
  return v5;
}

```

## disassembly

```asm
0x180008b1c  mov     [rsp+arg_0], rbx
0x180008b21  push    rdi
0x180008b22  sub     rsp, 40h
0x180008b26  mov     ebx, edx
0x180008b28  mov     rdi, rcx
0x180008b2b  call    cs:__imp_EnterCriticalSection
0x180008b31  mov     eax, cs:g_dwDebugFlags
0x180008b37  test    al, 3
0x180008b39  setnz   r8b
0x180008b3d  bt      eax, 14h
0x180008b41  setb    al
0x180008b44  test    al, r8b
0x180008b47  jz      short loc_180008B7A
0x180008b49  mov     rcx, cs:g_pDebug
0x180008b50  lea     rax, aWpRecyclerStar_6; "WP_RECYCLER::StartTimeBased(%d min)\n"
0x180008b57  mov     [rsp+48h+Period], ebx
0x180008b5b  lea     r9, aWpRecyclerStar_3; "WP_RECYCLER::StartTimeBased"
0x180008b62  mov     r8d, 3FAh
0x180008b68  mov     qword ptr [rsp+48h+DueTime], rax
0x180008b6d  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008b74  call    cs:__imp_PuDbgPrint
0x180008b7a  cmp     dword ptr [rdi+90h], 1
0x180008b81  jnz     short loc_180008B8B
0x180008b83  mov     rcx, rdi; this
0x180008b86  call    ?TerminateTimeBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateTimeBased(void)
0x180008b8b  test    ebx, ebx
0x180008b8d  jz      loc_180008C40
0x180008b93  imul    eax, ebx, 0EA60h
0x180008b99  lea     r8, ?TimerCallbackForTimeBased@WP_RECYCLER@@SAXPEAXE@Z; Callback
0x180008ba0  mov     [rsp+48h+Flags], 10h; Flags
0x180008ba8  lea     rbx, [rdi+88h]
0x180008baf  mov     r9, rdi; Parameter
0x180008bb2  xor     edx, edx; TimerQueue
0x180008bb4  mov     rcx, rbx; phNewTimer
0x180008bb7  mov     [rsp+48h+Period], eax; Period
0x180008bbb  mov     [rsp+48h+DueTime], eax; DueTime
0x180008bbf  call    cs:__imp_CreateTimerQueueTimer
0x180008bc5  test    eax, eax
0x180008bc7  jnz     short loc_180008C36
0x180008bc9  mov     qword ptr [rbx], 0
0x180008bd0  call    cs:__imp_GetLastError
0x180008bd6  mov     ebx, eax
0x180008bd8  test    eax, eax
0x180008bda  jle     short loc_180008BE5
0x180008bdc  movzx   ebx, ax
0x180008bdf  or      ebx, 80070000h
0x180008be5  mov     rcx, rdi; this
0x180008be8  call    ?TerminateTimeBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateTimeBased(void)
0x180008bed  mov     eax, cs:g_dwDebugFlags
0x180008bf3  test    al, 3
0x180008bf5  setnz   cl
0x180008bf8  bt      eax, 14h
0x180008bfc  setb    al
0x180008bff  test    al, cl
0x180008c01  jz      short loc_180008C42
0x180008c03  mov     rcx, cs:g_pDebug
0x180008c0a  lea     rax, aWpRecyclerStar_9; "WP_RECYCLER::StartTimeBased() failed wi"...
0x180008c11  mov     [rsp+48h+Period], ebx
0x180008c15  lea     r9, aWpRecyclerStar_3; "WP_RECYCLER::StartTimeBased"
0x180008c1c  mov     r8d, 42Eh
0x180008c22  mov     qword ptr [rsp+48h+DueTime], rax
0x180008c27  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008c2e  call    cs:__imp_PuDbgPrint
0x180008c34  jmp     short loc_180008C42
0x180008c36  mov     dword ptr [rdi+90h], 1
0x180008c40  xor     ebx, ebx
0x180008c42  mov     rcx, rdi; lpCriticalSection
0x180008c45  call    cs:__imp_LeaveCriticalSection
0x180008c4b  mov     eax, ebx
0x180008c4d  mov     rbx, [rsp+48h+arg_0]
0x180008c52  add     rsp, 40h
0x180008c56  pop     rdi
0x180008c57  retn
```
