# WP_IDLE_TIMER::IncrementTick(void)

- ea: `0x180009a78`
- end: `0x180009ce5`
- name: `?IncrementTick@WP_IDLE_TIMER@@QEAAXXZ`
- size: `621`
- prototype: `void __fastcall(WP_IDLE_TIMER *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009a20`

## callees

- `0x180001900`
- `0x18000620c`
- `0x180008ad4`
- `0x180009a78`
- `0x180009e18`
- `0x18000d2f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009bd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009bd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009b82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009b82`
- `api-ms-win-core-psapi-l1-1-0!K32EmptyWorkingSet` at `0x180009b91`
- `api-ms-win-core-psapi-l1-1-0!K32EmptyWorkingSet` at `0x180009b91`
- `iisutil!PuDbgPrint` at `0x180009b23`
- `iisutil!PuDbgPrint` at `0x180009c89`
- `iisutil!PuDbgPrint` at `0x180009b23`
- `iisutil!PuDbgPrint` at `0x180009c89`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180009c4b`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180009c4b`

## string_xrefs

- `0x180009b1c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`
- `0x180009c82`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`

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
0x180009a78  push    rbp
0x180009a7a  push    rbx
0x180009a7b  push    rdi
0x180009a7c  push    r14
0x180009a7e  lea     rbp, [rsp-3Fh]
0x180009a83  sub     rsp, 98h
0x180009a8a  mov     rax, cs:__security_cookie
0x180009a91  xor     rax, rsp
0x180009a94  mov     [rbp+57h+var_30], rax
0x180009a98  xor     eax, eax
0x180009a9a  mov     rbx, rcx
0x180009a9d  lea     r14d, [rax+1]
0x180009aa1  lock cmpxchg [rcx], r14d
0x180009aa6  jz      short loc_180009AB2
0x180009aa8  lock add [rcx+8], r14d
0x180009aad  jmp     loc_180009CCB
0x180009ab2  xor     edi, edi
0x180009ab4  xchg    edi, [rcx+4]
0x180009ab7  cmp     dword ptr [rcx+18h], 0
0x180009abb  jnz     short loc_180009ACB
0x180009abd  call    ?CheckIdle@W3WP_HOST@@QEAAHXZ; W3WP_HOST::CheckIdle(void)
0x180009ac2  test    eax, eax
0x180009ac4  jz      short loc_180009ACB
0x180009ac6  mov     eax, r14d
0x180009ac9  jmp     short loc_180009ACD
0x180009acb  xor     eax, eax
0x180009acd  test    edi, edi
0x180009acf  jnz     loc_180009CC0
0x180009ad5  test    eax, eax
0x180009ad7  jz      loc_180009CC0
0x180009add  lock add [rbx+8], r14d
0x180009ae2  mov     eax, [rbx+0Ch]
0x180009ae5  cmp     [rbx+8], eax
0x180009ae8  jb      loc_180009CC7
0x180009aee  cmp     [rbx+1Ch], edi
0x180009af1  jnz     short loc_180009B49
0x180009af3  test    byte ptr cs:g_dwDebugFlags, 3
0x180009afa  jz      short loc_180009B2F
0x180009afc  mov     rcx, cs:g_pDebug
0x180009b03  lea     rax, aIdleTimeReache; "Idle time reached.  Send shutdown messa"...
0x180009b0a  lea     r9, aWpIdleTimerInc; "WP_IDLE_TIMER::IncrementTick"
0x180009b11  mov     [rsp+0B0h+var_90], rax
0x180009b16  mov     r8d, 0D2h
0x180009b1c  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009b23  call    cs:__imp_PuDbgPrint
0x180009b2a  nop     dword ptr [rax+rax+00h]
0x180009b2f  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180009b36  mov     edx, 2
0x180009b3b  mov     rcx, [rcx+58h]
0x180009b3f  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x180009b44  jmp     loc_180009CC7
0x180009b49  cmp     [rbx+1Ch], r14d
0x180009b4d  jnz     loc_180009CC7
0x180009b53  cmp     dword ptr [rbx+18h], 0
0x180009b57  jnz     loc_180009CC0
0x180009b5d  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; this
0x180009b64  xor     eax, eax
0x180009b66  lock cmpxchg [rcx+63Ch], r14d
0x180009b6f  jnz     loc_180009CC7
0x180009b75  call    ?NotifySuspendProcess@W3WP_HOST@@QEAAJXZ; W3WP_HOST::NotifySuspendProcess(void)
0x180009b7a  test    eax, eax
0x180009b7c  js      loc_180009C59
0x180009b82  call    cs:__imp_GetCurrentProcess
0x180009b89  nop     dword ptr [rax+rax+00h]
0x180009b8e  mov     rcx, rax; hProcess
0x180009b91  call    cs:__imp_K32EmptyWorkingSet
0x180009b98  nop     dword ptr [rax+rax+00h]
0x180009b9d  test    eax, eax
0x180009b9f  jz      loc_180009C59
0x180009ba5  xor     eax, eax
0x180009ba7  mov     [rbx+18h], r14d
0x180009bab  xorps   xmm0, xmm0
0x180009bae  mov     dword ptr [rbx+8], 0
0x180009bb5  xorps   xmm1, xmm1
0x180009bb8  mov     [rbp+57h+var_68], rax
0x180009bbc  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x180009bc0  mov     qword ptr [rbp+57h+var_60+0Eh], rax
0x180009bc4  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180009bc8  mov     qword ptr [rbp+57h+var_48+0Eh], rax
0x180009bcc  movups  [rbp+57h+var_78], xmm0
0x180009bd0  call    cs:__imp_GetCurrentProcessId
0x180009bd7  nop     dword ptr [rax+rax+00h]
0x180009bdc  mov     edi, 0Bh
0x180009be1  lea     r8, aLu; "%lu"
0x180009be8  mov     r9d, eax
0x180009beb  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x180009bef  mov     edx, edi; unsigned __int64
0x180009bf1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009bf6  mov     r9d, [rbx+0Ch]
0x180009bfa  lea     r8, aLu; "%lu"
0x180009c01  mov     edx, edi; unsigned __int64
0x180009c03  lea     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x180009c07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009c0c  mov     rdx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180009c13  lea     rax, [rbp+57h+var_60]
0x180009c17  mov     qword ptr [rbp+57h+var_78], rax
0x180009c1b  lea     r8d, [rdi-8]
0x180009c1f  lea     r9, [rbp+57h+var_78]
0x180009c23  mov     dword ptr [rsp+0B0h+var_90], 0
0x180009c2b  mov     rax, [rdx+138h]
0x180009c32  mov     rcx, [rax+18h]
0x180009c36  lea     rax, [rbp+57h+var_48]
0x180009c3a  mov     qword ptr [rbp+57h+var_78+8], rcx
0x180009c3e  lea     rcx, [rdx+50h]
0x180009c42  mov     edx, 40000906h
0x180009c47  mov     [rbp+57h+var_68], rax
0x180009c4b  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180009c52  nop     dword ptr [rax+rax+00h]
0x180009c57  jmp     short loc_180009CAA
0x180009c59  test    byte ptr cs:g_dwDebugFlags, 3
0x180009c60  jz      short loc_180009C95
0x180009c62  mov     rcx, cs:g_pDebug
0x180009c69  lea     rax, aPageoutFailedU; "Pageout failed upon idle time reached. "...
0x180009c70  lea     r9, aWpIdleTimerInc; "WP_IDLE_TIMER::IncrementTick"
0x180009c77  mov     [rsp+0B0h+var_90], rax
0x180009c7c  mov     r8d, 10Ch
0x180009c82  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009c89  call    cs:__imp_PuDbgPrint
0x180009c90  nop     dword ptr [rax+rax+00h]
0x180009c95  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180009c9c  mov     edx, 2
0x180009ca1  mov     rcx, [rcx+58h]
0x180009ca5  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x180009caa  mov     rdx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180009cb1  xor     ecx, ecx
0x180009cb3  mov     eax, r14d
0x180009cb6  lock cmpxchg [rdx+63Ch], ecx
0x180009cbe  jmp     short loc_180009CC7
0x180009cc0  mov     dword ptr [rbx+8], 0
0x180009cc7  xor     eax, eax
0x180009cc9  xchg    eax, [rbx]
0x180009ccb  mov     rcx, [rbp+57h+var_30]
0x180009ccf  xor     rcx, rsp; StackCookie
0x180009cd2  call    __security_check_cookie
0x180009cd7  add     rsp, 98h
0x180009cde  pop     r14
0x180009ce0  pop     rdi
0x180009ce1  pop     rbx
0x180009ce2  pop     rbp
0x180009ce3  retn
```
