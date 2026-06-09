# WP_RECYCLER::StartMemoryBased(unsigned __int64,unsigned __int64)

- ea: `0x180008e9c`
- end: `0x180009022`
- name: `?StartMemoryBased@WP_RECYCLER@@QEAAJ_K0@Z`
- size: `390`
- prototype: `__int64 __fastcall(WP_RECYCLER *__hidden this, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007dbc`

## callees

- `0x180001e5c`
- `0x180008e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009003`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009003`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008eb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008fdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008fdc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180008f52`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180008f52`
- `iisutil!PuDbgPrint` at `0x180008f0a`
- `iisutil!PuDbgPrint` at `0x180008fce`
- `iisutil!PuDbgPrint` at `0x180008f0a`
- `iisutil!PuDbgPrint` at `0x180008fce`

## string_xrefs

- `0x180008ef8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180008fc7`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

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
      "WP_RECYCLER::StartMemoryBased(VM:%I64u bytes, Private Bytes:%I64u bytes)\n",
      a2,
      0);
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
      "WP_RECYCLER::StartMemoryBased() failed with error hr=0x%x\n",
      v5);
LABEL_13:
  LeaveCriticalSection(this);
  return v5;
}

```

## disassembly

```asm
0x180008e9c  mov     [rsp+arg_0], rbx
0x180008ea1  mov     [rsp+arg_8], rsi
0x180008ea6  push    rdi
0x180008ea7  sub     rsp, 40h
0x180008eab  mov     rbx, rdx
0x180008eae  mov     rdi, rcx
0x180008eb1  call    cs:__imp_EnterCriticalSection
0x180008eb8  nop     dword ptr [rax+rax+00h]
0x180008ebd  mov     eax, cs:g_dwDebugFlags
0x180008ec3  test    al, 3
0x180008ec5  setnz   r8b
0x180008ec9  bt      eax, 14h
0x180008ecd  setb    al
0x180008ed0  test    al, r8b
0x180008ed3  jz      short loc_180008F16
0x180008ed5  mov     rcx, cs:g_pDebug
0x180008edc  lea     rax, aWpRecyclerStar_2; "WP_RECYCLER::StartMemoryBased(VM:%I64u "...
0x180008ee3  mov     qword ptr [rsp+48h+Flags], 0
0x180008eec  lea     r9, aWpRecyclerStar_8; "WP_RECYCLER::StartMemoryBased"
0x180008ef3  mov     qword ptr [rsp+48h+Period], rbx
0x180008ef8  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008eff  mov     r8d, 268h
0x180008f05  mov     qword ptr [rsp+48h+DueTime], rax
0x180008f0a  call    cs:__imp_PuDbgPrint
0x180008f11  nop     dword ptr [rax+rax+00h]
0x180008f16  cmp     dword ptr [rdi+30h], 1
0x180008f1a  jnz     short loc_180008F24
0x180008f1c  mov     rcx, rdi; this
0x180008f1f  call    ?TerminateMemoryBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateMemoryBased(void)
0x180008f24  test    rbx, rbx
0x180008f27  jz      loc_180008FFE
0x180008f2d  mov     eax, 0EA60h
0x180008f32  mov     [rsp+48h+Flags], 10h; Flags
0x180008f3a  mov     [rsp+48h+Period], eax; Period
0x180008f3e  lea     r8, ?TimerCallbackForMemoryBased@WP_RECYCLER@@SAXPEAXE@Z; Callback
0x180008f45  mov     r9, rdi; Parameter
0x180008f48  mov     [rsp+48h+DueTime], eax; DueTime
0x180008f4c  xor     edx, edx; TimerQueue
0x180008f4e  lea     rcx, [rdi+28h]; phNewTimer
0x180008f52  call    cs:__imp_CreateTimerQueueTimer
0x180008f59  nop     dword ptr [rax+rax+00h]
0x180008f5e  test    eax, eax
0x180008f60  jnz     short loc_180008FDC
0x180008f62  mov     qword ptr [rdi+28h], 0
0x180008f6a  call    cs:__imp_GetLastError
0x180008f71  nop     dword ptr [rax+rax+00h]
0x180008f76  mov     ebx, eax
0x180008f78  test    eax, eax
0x180008f7a  jle     short loc_180008F85
0x180008f7c  movzx   ebx, ax
0x180008f7f  or      ebx, 80070000h
0x180008f85  mov     rcx, rdi; this
0x180008f88  call    ?TerminateMemoryBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateMemoryBased(void)
0x180008f8d  mov     eax, cs:g_dwDebugFlags
0x180008f93  test    al, 3
0x180008f95  setnz   cl
0x180008f98  bt      eax, 14h
0x180008f9c  setb    al
0x180008f9f  test    al, cl
0x180008fa1  jz      short loc_180009000
0x180008fa3  mov     rcx, cs:g_pDebug
0x180008faa  lea     rax, aWpRecyclerStar_5; "WP_RECYCLER::StartMemoryBased() failed "...
0x180008fb1  mov     [rsp+48h+Period], ebx
0x180008fb5  lea     r9, aWpRecyclerStar_8; "WP_RECYCLER::StartMemoryBased"
0x180008fbc  mov     r8d, 2A7h
0x180008fc2  mov     qword ptr [rsp+48h+DueTime], rax
0x180008fc7  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008fce  call    cs:__imp_PuDbgPrint
0x180008fd5  nop     dword ptr [rax+rax+00h]
0x180008fda  jmp     short loc_180009000
0x180008fdc  call    cs:__imp_GetCurrentProcessId
0x180008fe3  nop     dword ptr [rax+rax+00h]
0x180008fe8  mov     [rdi+48h], eax
0x180008feb  mov     [rdi+38h], rbx
0x180008fef  mov     qword ptr [rdi+40h], 0
0x180008ff7  mov     dword ptr [rdi+30h], 1
0x180008ffe  xor     ebx, ebx
0x180009000  mov     rcx, rdi; lpCriticalSection
0x180009003  call    cs:__imp_LeaveCriticalSection
0x18000900a  nop     dword ptr [rax+rax+00h]
0x18000900f  mov     rsi, [rsp+48h+arg_8]
0x180009014  mov     eax, ebx
0x180009016  mov     rbx, [rsp+48h+arg_0]
0x18000901b  add     rsp, 40h
0x18000901f  pop     rdi
0x180009020  retn
```
