# THREAD_MANAGER::RequestThread(ulong (*)(void *),void *)

- ea: `0x180001160`
- end: `0x18000131e`
- name: `?RequestThread@THREAD_MANAGER@@QEAAXP6AKPEAX@Z0@Z`
- size: `446`
- prototype: `void __fastcall(PVOID Parameter, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001090`

## callees

- `0x180001160`
- `0x180001590`
- `0x180001f4c`
- `0x180001f8c`
- `0x180002d54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000130e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000130e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001190`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001190`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011f1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800012d4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800012d4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800012a2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800012a2`
- `iisutil!PuDbgPrint` at `0x1800011eb`
- `iisutil!PuDbgPrint` at `0x1800011eb`

## string_xrefs

- `0x1800011cb`: `W3TP: Thread Request received\n`
- `0x1800011d2`: `THREAD_MANAGER::RequestThread`
- `0x1800011e4`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`

## pseudocode

```c
void __fastcall THREAD_MANAGER::RequestThread(char *Parameter, unsigned int (*a2)(void *), void *a3)
{
  bool v5; // zf
  DWORD TickCount; // ebp
  _QWORD *v7; // rax
  void *v8; // rdx
  _DWORD *v9; // rcx

  if ( !*((_QWORD *)Parameter + 6) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
    if ( !*((_QWORD *)Parameter + 6) )
    {
      v5 = (g_dwDebugFlags & 3) == 0;
      *((_DWORD *)Parameter + 13) = 1;
      if ( !v5 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
          955,
          "THREAD_MANAGER::RequestThread",
          "W3TP: Thread Request received\n");
      TickCount = GetTickCount();
      if ( (unsigned int)GetContextSwitchCount((unsigned int *)Parameter + 18)
        && (*(_DWORD *)(*((_QWORD *)Parameter + 14) + 68LL) == -1
         || (int)GetProcessorInformation(
                   (union _LARGE_INTEGER *)Parameter + 16,
                   (union _LARGE_INTEGER *)Parameter + 15,
                   g_dwNumProcs) >= 0) )
      {
        v7 = operator new(0x30u);
        if ( v7 )
        {
          *(_DWORD *)v7 = 1380012116;
          v7[2] = 0;
          v7[3] = 0;
          v7[4] = 0;
          *((_DWORD *)v7 + 10) = 0;
          *((_QWORD *)Parameter + 8) = v7;
          v7[1] = THREAD_POOL_DATA::ThreadPoolThread;
          *(_QWORD *)(*((_QWORD *)Parameter + 8) + 16LL) = a3;
          *(_QWORD *)(*((_QWORD *)Parameter + 8) + 24LL) = Parameter;
          *(_DWORD *)(*((_QWORD *)Parameter + 8) + 32LL) = TickCount;
          *(_DWORD *)(*((_QWORD *)Parameter + 8) + 36LL) = 1;
          v8 = (void *)*((_QWORD *)Parameter + 7);
          if ( v8 )
          {
            DeleteTimerQueueTimer(0, v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
            *((_QWORD *)Parameter + 7) = 0;
          }
          if ( CreateTimerQueueTimer(
                 (PHANDLE)Parameter + 7,
                 0,
                 THREAD_MANAGER::ControlTimerCallback,
                 Parameter,
                 *(_DWORD *)(*((_QWORD *)Parameter + 14) + 80LL),
                 0,
                 8u) )
          {
            goto LABEL_17;
          }
        }
        else
        {
          *((_QWORD *)Parameter + 8) = 0;
        }
      }
      v9 = (_DWORD *)*((_QWORD *)Parameter + 8);
      if ( v9 )
      {
        *v9 = 2017546324;
        operator delete(v9);
      }
      *((_QWORD *)Parameter + 8) = 0;
      *((_DWORD *)Parameter + 13) = 0;
    }
LABEL_17:
    LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
  }
}

```

## disassembly

```asm
0x180001160  mov     [rsp+arg_18], rbx
0x180001165  push    rdi
0x180001166  sub     rsp, 40h
0x18000116a  cmp     dword ptr [rcx+30h], 0
0x18000116e  mov     rdi, r8
0x180001171  mov     rbx, rcx
0x180001174  jnz     short loc_18000117C
0x180001176  cmp     dword ptr [rcx+34h], 0
0x18000117a  jz      short loc_180001187
0x18000117c  mov     rbx, [rsp+48h+arg_18]
0x180001181  add     rsp, 40h
0x180001185  pop     rdi
0x180001186  retn
0x180001187  add     rcx, 8; lpCriticalSection
0x18000118b  mov     [rsp+48h+arg_8], rsi
0x180001190  call    cs:__imp_EnterCriticalSection
0x180001196  cmp     dword ptr [rbx+30h], 0
0x18000119a  jnz     loc_18000130A
0x1800011a0  cmp     dword ptr [rbx+34h], 0
0x1800011a4  jnz     loc_18000130A
0x1800011aa  test    cs:g_dwDebugFlags, 3
0x1800011b1  mov     [rsp+48h+arg_0], rbp
0x1800011b6  mov     [rsp+48h+arg_10], r14
0x1800011bb  mov     dword ptr [rbx+34h], 1
0x1800011c2  jz      short loc_1800011F1
0x1800011c4  mov     rcx, cs:g_pDebug
0x1800011cb  lea     rax, aW3tpThreadRequ; "W3TP: Thread Request received\n"
0x1800011d2  lea     r9, aThreadManagerR_0; "THREAD_MANAGER::RequestThread"
0x1800011d9  mov     qword ptr [rsp+48h+DueTime], rax
0x1800011de  mov     r8d, 3BBh
0x1800011e4  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800011eb  call    cs:__imp_PuDbgPrint
0x1800011f1  call    cs:__imp_GetTickCount
0x1800011f7  lea     rcx, [rbx+48h]; unsigned int *
0x1800011fb  mov     ebp, eax
0x1800011fd  call    ?GetContextSwitchCount@@YAHPEAK@Z; GetContextSwitchCount(ulong *)
0x180001202  xor     r14d, r14d
0x180001205  test    eax, eax
0x180001207  jz      loc_1800012E4
0x18000120d  mov     rcx, [rbx+70h]
0x180001211  cmp     dword ptr [rcx+44h], 0FFFFFFFFh
0x180001215  jz      short loc_180001236
0x180001217  mov     r8d, cs:?g_dwNumProcs@@3KA; unsigned int
0x18000121e  lea     rdx, [rbx+78h]; union _LARGE_INTEGER *
0x180001222  lea     rcx, [rbx+80h]; union _LARGE_INTEGER *
0x180001229  call    ?GetProcessorInformation@@YAJPEAT_LARGE_INTEGER@@0K@Z; GetProcessorInformation(_LARGE_INTEGER *,_LARGE_INTEGER *,ulong)
0x18000122e  test    eax, eax
0x180001230  js      loc_1800012E4
0x180001236  mov     ecx, 30h ; '0'; Size
0x18000123b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001240  test    rax, rax
0x180001243  jz      loc_1800012E0
0x180001249  mov     dword ptr [rax], 52415054h
0x18000124f  lea     rcx, ?ThreadPoolThread@THREAD_POOL_DATA@@SAKPEAX@Z; THREAD_POOL_DATA::ThreadPoolThread(void *)
0x180001256  mov     [rax+10h], r14
0x18000125a  mov     [rax+18h], r14
0x18000125e  mov     [rax+20h], r14
0x180001262  mov     [rax+28h], r14d
0x180001266  mov     [rbx+40h], rax
0x18000126a  mov     [rax+8], rcx
0x18000126e  mov     rax, [rbx+40h]
0x180001272  mov     [rax+10h], rdi
0x180001276  mov     rax, [rbx+40h]
0x18000127a  mov     [rax+18h], rbx
0x18000127e  mov     rax, [rbx+40h]
0x180001282  mov     [rax+20h], ebp
0x180001285  mov     rax, [rbx+40h]
0x180001289  mov     dword ptr [rax+24h], 1
0x180001290  mov     rdx, [rbx+38h]; Timer
0x180001294  test    rdx, rdx
0x180001297  jz      short loc_1800012AC
0x180001299  xor     ecx, ecx; TimerQueue
0x18000129b  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800012a2  call    cs:__imp_DeleteTimerQueueTimer
0x1800012a8  mov     [rbx+38h], r14
0x1800012ac  mov     rax, [rbx+70h]
0x1800012b0  lea     r8, ?ControlTimerCallback@THREAD_MANAGER@@CAXPEAXE@Z; Callback
0x1800012b7  mov     [rsp+48h+Flags], 8; Flags
0x1800012bf  lea     rcx, [rbx+38h]; phNewTimer
0x1800012c3  mov     [rsp+48h+Period], r14d; Period
0x1800012c8  mov     r9, rbx; Parameter
0x1800012cb  xor     edx, edx; TimerQueue
0x1800012cd  mov     eax, [rax+50h]
0x1800012d0  mov     [rsp+48h+DueTime], eax; DueTime
0x1800012d4  call    cs:__imp_CreateTimerQueueTimer
0x1800012da  test    eax, eax
0x1800012dc  jz      short loc_1800012E4
0x1800012de  jmp     short loc_180001300
0x1800012e0  mov     [rbx+40h], r14
0x1800012e4  mov     rcx, [rbx+40h]; Block
0x1800012e8  test    rcx, rcx
0x1800012eb  jz      short loc_1800012F8
0x1800012ed  mov     dword ptr [rcx], 78415054h
0x1800012f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800012f8  mov     [rbx+40h], r14
0x1800012fc  mov     [rbx+34h], r14d
0x180001300  mov     rbp, [rsp+48h+arg_0]
0x180001305  mov     r14, [rsp+48h+arg_10]
0x18000130a  lea     rcx, [rbx+8]; lpCriticalSection
0x18000130e  call    cs:__imp_LeaveCriticalSection
0x180001314  mov     rsi, [rsp+48h+arg_8]
0x180001319  jmp     loc_18000117C
```
