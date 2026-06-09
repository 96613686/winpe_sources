# WP_RECYCLER::StartMemoryBased(unsigned __int64,unsigned __int64)

- ea: `0x180008588`
- end: `0x1800086e3`
- name: `?StartMemoryBased@WP_RECYCLER@@QEAAJ_K0@Z`
- size: `347`
- prototype: `__int64 __fastcall(WP_RECYCLER *__hidden this, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007610`

## callees

- `0x180001d8c`
- `0x180008588`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008644`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000859d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000859d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800086aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800086aa`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180008632`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180008632`
- `iisutil!PuDbgPrint` at `0x1800085f0`
- `iisutil!PuDbgPrint` at `0x1800086a2`
- `iisutil!PuDbgPrint` at `0x1800085f0`
- `iisutil!PuDbgPrint` at `0x1800086a2`

## string_xrefs

- `0x1800085de`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x18000869b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

## pseudocode

```c
__int64 __fastcall WP_RECYCLER::StartMemoryBased(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx

  EnterCriticalSection(this);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
      616,
      "WP_RECYCLER::StartMemoryBased",
      "WP_RECYCLER::StartMemoryBased(VM:%I64u bytes, Private Bytes:%I64u bytes)\n");
  if ( this[1].LockCount == 1 )
    WP_RECYCLER::TerminateMemoryBased((WP_RECYCLER *)this);
  if ( !a2 )
    goto LABEL_12;
  if ( CreateTimerQueueTimer(
         (PHANDLE)&this[1].DebugInfo,
         0,
         WP_RECYCLER::TimerCallbackForMemoryBased,
         this,
         0xEA60u,
         0xEA60u,
         0x10u) )
  {
    LODWORD(this[1].SpinCount) = GetCurrentProcessId();
    this[1].OwningThread = a2;
    this[1].LockSemaphore = 0;
    this[1].LockCount = 1;
LABEL_12:
    v5 = 0;
    goto LABEL_13;
  }
  this[1].DebugInfo = 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  WP_RECYCLER::TerminateMemoryBased((WP_RECYCLER *)this);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
      679,
      "WP_RECYCLER::StartMemoryBased",
      "WP_RECYCLER::StartMemoryBased() failed with error hr=0x%x\n");
LABEL_13:
  LeaveCriticalSection(this);
  return v5;
}

```

## disassembly

```asm
0x180008588  mov     [rsp+arg_0], rbx
0x18000858d  mov     [rsp+arg_8], rsi
0x180008592  push    rdi
0x180008593  sub     rsp, 40h
0x180008597  mov     rbx, rdx
0x18000859a  mov     rdi, rcx
0x18000859d  call    cs:__imp_EnterCriticalSection
0x1800085a3  mov     eax, cs:g_dwDebugFlags
0x1800085a9  test    al, 3
0x1800085ab  setnz   r8b
0x1800085af  bt      eax, 14h
0x1800085b3  setb    al
0x1800085b6  test    al, r8b
0x1800085b9  jz      short loc_1800085F6
0x1800085bb  mov     rcx, cs:g_pDebug
0x1800085c2  lea     rax, aWpRecyclerStar_2; "WP_RECYCLER::StartMemoryBased(VM:%I64u "...
0x1800085c9  mov     qword ptr [rsp+48h+Flags], 0
0x1800085d2  lea     r9, aWpRecyclerStar_8; "WP_RECYCLER::StartMemoryBased"
0x1800085d9  mov     qword ptr [rsp+48h+Period], rbx
0x1800085de  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800085e5  mov     r8d, 268h
0x1800085eb  mov     qword ptr [rsp+48h+DueTime], rax
0x1800085f0  call    cs:__imp_PuDbgPrint
0x1800085f6  cmp     dword ptr [rdi+30h], 1
0x1800085fa  jnz     short loc_180008604
0x1800085fc  mov     rcx, rdi; this
0x1800085ff  call    ?TerminateMemoryBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateMemoryBased(void)
0x180008604  test    rbx, rbx
0x180008607  jz      loc_1800086C6
0x18000860d  mov     eax, 0EA60h
0x180008612  mov     [rsp+48h+Flags], 10h; Flags
0x18000861a  mov     [rsp+48h+Period], eax; Period
0x18000861e  lea     r8, ?TimerCallbackForMemoryBased@WP_RECYCLER@@SAXPEAXE@Z; Callback
0x180008625  mov     r9, rdi; Parameter
0x180008628  mov     [rsp+48h+DueTime], eax; DueTime
0x18000862c  xor     edx, edx; TimerQueue
0x18000862e  lea     rcx, [rdi+28h]; phNewTimer
0x180008632  call    cs:__imp_CreateTimerQueueTimer
0x180008638  test    eax, eax
0x18000863a  jnz     short loc_1800086AA
0x18000863c  mov     qword ptr [rdi+28h], 0
0x180008644  call    cs:__imp_GetLastError
0x18000864a  mov     ebx, eax
0x18000864c  test    eax, eax
0x18000864e  jle     short loc_180008659
0x180008650  movzx   ebx, ax
0x180008653  or      ebx, 80070000h
0x180008659  mov     rcx, rdi; this
0x18000865c  call    ?TerminateMemoryBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateMemoryBased(void)
0x180008661  mov     eax, cs:g_dwDebugFlags
0x180008667  test    al, 3
0x180008669  setnz   cl
0x18000866c  bt      eax, 14h
0x180008670  setb    al
0x180008673  test    al, cl
0x180008675  jz      short loc_1800086C8
0x180008677  mov     rcx, cs:g_pDebug
0x18000867e  lea     rax, aWpRecyclerStar_5; "WP_RECYCLER::StartMemoryBased() failed "...
0x180008685  mov     [rsp+48h+Period], ebx
0x180008689  lea     r9, aWpRecyclerStar_8; "WP_RECYCLER::StartMemoryBased"
0x180008690  mov     r8d, 2A7h
0x180008696  mov     qword ptr [rsp+48h+DueTime], rax
0x18000869b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800086a2  call    cs:__imp_PuDbgPrint
0x1800086a8  jmp     short loc_1800086C8
0x1800086aa  call    cs:__imp_GetCurrentProcessId
0x1800086b0  mov     [rdi+48h], eax
0x1800086b3  mov     [rdi+38h], rbx
0x1800086b7  mov     qword ptr [rdi+40h], 0
0x1800086bf  mov     dword ptr [rdi+30h], 1
0x1800086c6  xor     ebx, ebx
0x1800086c8  mov     rcx, rdi; lpCriticalSection
0x1800086cb  call    cs:__imp_LeaveCriticalSection
0x1800086d1  mov     rsi, [rsp+48h+arg_8]
0x1800086d6  mov     eax, ebx
0x1800086d8  mov     rbx, [rsp+48h+arg_0]
0x1800086dd  add     rsp, 40h
0x1800086e1  pop     rdi
0x1800086e2  retn
```
