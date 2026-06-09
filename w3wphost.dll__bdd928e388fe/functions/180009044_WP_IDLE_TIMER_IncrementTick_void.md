# WP_IDLE_TIMER::IncrementTick(void)

- ea: `0x180009044`
- end: `0x18000928c`
- name: `?IncrementTick@WP_IDLE_TIMER@@QEAAXXZ`
- size: `584`
- prototype: `void __fastcall(WP_IDLE_TIMER *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008ff0`

## callees

- `0x180001890`
- `0x180005c9c`
- `0x1800081fc`
- `0x180009044`
- `0x18000939c`
- `0x18000c3d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000918a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000918a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009148`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009148`
- `api-ms-win-core-psapi-l1-1-0!K32EmptyWorkingSet` at `0x180009151`
- `api-ms-win-core-psapi-l1-1-0!K32EmptyWorkingSet` at `0x180009151`
- `iisutil!PuDbgPrint` at `0x1800090ef`
- `iisutil!PuDbgPrint` at `0x180009237`
- `iisutil!PuDbgPrint` at `0x1800090ef`
- `iisutil!PuDbgPrint` at `0x180009237`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800091ff`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800091ff`

## string_xrefs

- `0x1800090e8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`
- `0x180009230`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`

## pseudocode

```c
void __fastcall WP_IDLE_TIMER::IncrementTick(WP_IDLE_TIMER *this)
{
  __int32 v2; // edi
  BOOL v3; // eax
  W3WP_HOST *v4; // rcx
  HANDLE CurrentProcess; // rax
  DWORD CurrentProcessId; // eax
  __int128 v7; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int16 *v8; // [rsp+48h] [rbp-11h]
  unsigned __int16 v9[12]; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int16 v10[12]; // [rsp+68h] [rbp+Fh] BYREF

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this, 1, 0) )
  {
    _InterlockedAdd((volatile signed __int32 *)this + 2, 1u);
    return;
  }
  v2 = _InterlockedExchange((volatile __int32 *)this + 1, 0);
  v3 = !*((_DWORD *)this + 6) && (unsigned int)W3WP_HOST::CheckIdle(this);
  if ( v2 || !v3 )
  {
LABEL_24:
    *((_DWORD *)this + 2) = 0;
    goto LABEL_25;
  }
  _InterlockedAdd((volatile signed __int32 *)this + 2, 1u);
  if ( *((_DWORD *)this + 2) >= *((_DWORD *)this + 3) )
  {
    if ( !*((_DWORD *)this + 7) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpidletimer.cxx",
          210,
          "WP_IDLE_TIMER::IncrementTick",
          "Idle time reached.  Send shutdown message to WAS.\n");
      WP_IPM::SendShutdownRequestMessage(*((_QWORD *)g_pW3WPHost + 11), 2);
      goto LABEL_25;
    }
    if ( *((_DWORD *)this + 7) == 1 )
    {
      if ( !*((_DWORD *)this + 6) )
      {
        v4 = g_pW3WPHost;
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)g_pW3WPHost + 399, 1, 0) )
        {
          if ( (int)W3WP_HOST::NotifySuspendProcess(v4) >= 0
            && (CurrentProcess = GetCurrentProcess(), K32EmptyWorkingSet(CurrentProcess)) )
          {
            *((_DWORD *)this + 6) = 1;
            *((_DWORD *)this + 2) = 0;
            v8 = 0;
            memset(v9, 0, 22);
            memset(v10, 0, 22);
            v7 = 0;
            CurrentProcessId = GetCurrentProcessId();
            StringCchPrintfW(v9, 0xBu, L"%lu", CurrentProcessId);
            StringCchPrintfW(v10, 0xBu, L"%lu", *((unsigned int *)this + 3));
            *(_QWORD *)&v7 = v9;
            *((_QWORD *)&v7 + 1) = *(_QWORD *)(*((_QWORD *)g_pW3WPHost + 39) + 24LL);
            v8 = v10;
            EVENT_LOG::LogEvent(
              (W3WP_HOST *)((char *)g_pW3WPHost + 80),
              0x40000906u,
              3u,
              (const unsigned __int16 **const)&v7,
              0);
          }
          else
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpidletimer.cxx",
                268,
                "WP_IDLE_TIMER::IncrementTick",
                "Pageout failed upon idle time reached.  Send shutdown message to WAS.\n");
            WP_IPM::SendShutdownRequestMessage(*((_QWORD *)g_pW3WPHost + 11), 2);
          }
          _InterlockedCompareExchange((volatile signed __int32 *)g_pW3WPHost + 399, 0, 1);
        }
        goto LABEL_25;
      }
      goto LABEL_24;
    }
  }
LABEL_25:
  _InterlockedExchange((volatile __int32 *)this, 0);
}

```

## disassembly

```asm
0x180009044  push    rbp
0x180009046  push    rbx
0x180009047  push    rdi
0x180009048  push    r14
0x18000904a  lea     rbp, [rsp-3Fh]
0x18000904f  sub     rsp, 98h
0x180009056  mov     rax, cs:__security_cookie
0x18000905d  xor     rax, rsp
0x180009060  mov     [rbp+57h+var_30], rax
0x180009064  xor     eax, eax
0x180009066  mov     rbx, rcx
0x180009069  lea     r14d, [rax+1]
0x18000906d  lock cmpxchg [rcx], r14d
0x180009072  jz      short loc_18000907E
0x180009074  lock add [rcx+8], r14d
0x180009079  jmp     loc_180009273
0x18000907e  xor     edi, edi
0x180009080  xchg    edi, [rcx+4]
0x180009083  cmp     dword ptr [rcx+18h], 0
0x180009087  jnz     short loc_180009097
0x180009089  call    ?CheckIdle@W3WP_HOST@@QEAAHXZ; W3WP_HOST::CheckIdle(void)
0x18000908e  test    eax, eax
0x180009090  jz      short loc_180009097
0x180009092  mov     eax, r14d
0x180009095  jmp     short loc_180009099
0x180009097  xor     eax, eax
0x180009099  test    edi, edi
0x18000909b  jnz     loc_180009268
0x1800090a1  test    eax, eax
0x1800090a3  jz      loc_180009268
0x1800090a9  lock add [rbx+8], r14d
0x1800090ae  mov     eax, [rbx+0Ch]
0x1800090b1  cmp     [rbx+8], eax
0x1800090b4  jb      loc_18000926F
0x1800090ba  cmp     [rbx+1Ch], edi
0x1800090bd  jnz     short loc_18000910F
0x1800090bf  test    byte ptr cs:g_dwDebugFlags, 3
0x1800090c6  jz      short loc_1800090F5
0x1800090c8  mov     rcx, cs:g_pDebug
0x1800090cf  lea     rax, aIdleTimeReache; "Idle time reached.  Send shutdown messa"...
0x1800090d6  lea     r9, aWpIdleTimerInc; "WP_IDLE_TIMER::IncrementTick"
0x1800090dd  mov     [rsp+0B0h+var_90], rax
0x1800090e2  mov     r8d, 0D2h
0x1800090e8  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800090ef  call    cs:__imp_PuDbgPrint
0x1800090f5  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800090fc  mov     edx, 2
0x180009101  mov     rcx, [rcx+58h]
0x180009105  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x18000910a  jmp     loc_18000926F
0x18000910f  cmp     [rbx+1Ch], r14d
0x180009113  jnz     loc_18000926F
0x180009119  cmp     dword ptr [rbx+18h], 0
0x18000911d  jnz     loc_180009268
0x180009123  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; this
0x18000912a  xor     eax, eax
0x18000912c  lock cmpxchg [rcx+63Ch], r14d
0x180009135  jnz     loc_18000926F
0x18000913b  call    ?NotifySuspendProcess@W3WP_HOST@@QEAAJXZ; W3WP_HOST::NotifySuspendProcess(void)
0x180009140  test    eax, eax
0x180009142  js      loc_180009207
0x180009148  call    cs:__imp_GetCurrentProcess
0x18000914e  mov     rcx, rax; hProcess
0x180009151  call    cs:__imp_K32EmptyWorkingSet
0x180009157  test    eax, eax
0x180009159  jz      loc_180009207
0x18000915f  xor     eax, eax
0x180009161  mov     [rbx+18h], r14d
0x180009165  xorps   xmm0, xmm0
0x180009168  mov     dword ptr [rbx+8], 0
0x18000916f  xorps   xmm1, xmm1
0x180009172  mov     [rbp+57h+var_68], rax
0x180009176  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x18000917a  mov     qword ptr [rbp+57h+var_60+0Eh], rax
0x18000917e  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180009182  mov     qword ptr [rbp+57h+var_48+0Eh], rax
0x180009186  movups  [rbp+57h+var_78], xmm0
0x18000918a  call    cs:__imp_GetCurrentProcessId
0x180009190  mov     edi, 0Bh
0x180009195  lea     r8, aLu; "%lu"
0x18000919c  mov     r9d, eax
0x18000919f  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800091a3  mov     edx, edi; unsigned __int64
0x1800091a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800091aa  mov     r9d, [rbx+0Ch]
0x1800091ae  lea     r8, aLu; "%lu"
0x1800091b5  mov     edx, edi; unsigned __int64
0x1800091b7  lea     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x1800091bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800091c0  mov     rdx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800091c7  lea     rax, [rbp+57h+var_60]
0x1800091cb  mov     qword ptr [rbp+57h+var_78], rax
0x1800091cf  lea     r8d, [rdi-8]
0x1800091d3  lea     r9, [rbp+57h+var_78]
0x1800091d7  mov     dword ptr [rsp+0B0h+var_90], 0
0x1800091df  mov     rax, [rdx+138h]
0x1800091e6  mov     rcx, [rax+18h]
0x1800091ea  lea     rax, [rbp+57h+var_48]
0x1800091ee  mov     qword ptr [rbp+57h+var_78+8], rcx
0x1800091f2  lea     rcx, [rdx+50h]
0x1800091f6  mov     edx, 40000906h
0x1800091fb  mov     [rbp+57h+var_68], rax
0x1800091ff  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180009205  jmp     short loc_180009252
0x180009207  test    byte ptr cs:g_dwDebugFlags, 3
0x18000920e  jz      short loc_18000923D
0x180009210  mov     rcx, cs:g_pDebug
0x180009217  lea     rax, aPageoutFailedU; "Pageout failed upon idle time reached. "...
0x18000921e  lea     r9, aWpIdleTimerInc; "WP_IDLE_TIMER::IncrementTick"
0x180009225  mov     [rsp+0B0h+var_90], rax
0x18000922a  mov     r8d, 10Ch
0x180009230  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009237  call    cs:__imp_PuDbgPrint
0x18000923d  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180009244  mov     edx, 2
0x180009249  mov     rcx, [rcx+58h]
0x18000924d  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x180009252  mov     rdx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180009259  xor     ecx, ecx
0x18000925b  mov     eax, r14d
0x18000925e  lock cmpxchg [rdx+63Ch], ecx
0x180009266  jmp     short loc_18000926F
0x180009268  mov     dword ptr [rbx+8], 0
0x18000926f  xor     eax, eax
0x180009271  xchg    eax, [rbx]
0x180009273  mov     rcx, [rbp+57h+var_30]
0x180009277  xor     rcx, rsp; StackCookie
0x18000927a  call    __security_check_cookie
0x18000927f  add     rsp, 98h
0x180009286  pop     r14
0x180009288  pop     rdi
0x180009289  pop     rbx
0x18000928a  pop     rbp
0x18000928b  retn
```
