# LOG_SVC_ADMIN::TerminateServiceAndReportFinalStatus(long)

- ea: `0x18000d420`
- end: `0x18000d50c`
- name: `?TerminateServiceAndReportFinalStatus@LOG_SVC_ADMIN@@AEAAXJ@Z`
- size: `236`
- prototype: `void __fastcall(LOG_SVC_ADMIN *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b324`

## callees

- `0x18000d180`
- `0x18000d420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4d3`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000d490`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000d490`
- `iisutil!PuDbgPrintError` at `0x18000d474`
- `iisutil!PuDbgPrintError` at `0x18000d474`

## string_xrefs

- `0x18000d46d`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000d450`: `Fatal service error, shutting down\n`
- `0x18000d45c`: `LOG_SVC_ADMIN::TerminateServiceAndReportFinalStatus`

## pseudocode

```c
void __fastcall LOG_SVC_ADMIN::TerminateServiceAndReportFinalStatus(LOG_SVC_ADMIN *this, int a2)
{
  signed int v2; // ebp
  signed int v3; // ebx
  int v5; // esi

  v2 = 0;
  v3 = a2;
  if ( a2 < 0 || (v3 = *((_DWORD *)this + 498), v5 = 0, v3 < 0) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        1099,
        "LOG_SVC_ADMIN::TerminateServiceAndReportFinalStatus",
        v3,
        "Fatal service error, shutting down\n");
    EVENT_LOG::LogEvent((LOG_SVC_ADMIN *)((char *)this + 1896), 0xC0001778, 0, 0, v3);
    if ( (v3 & 0x1FFF0000) == 0x70000 )
    {
      if ( v3 >= 0 )
        v5 = v3;
      else
        v5 = (unsigned __int16)v3;
    }
    else
    {
      v5 = 1066;
      v2 = v3;
    }
  }
  LOG_SVC_ADMIN::Terminate(this);
  if ( *((_DWORD *)this + 512) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2008));
    *((_DWORD *)this + 517) = 1;
    *((_DWORD *)this + 519) = v5;
    *((_DWORD *)this + 520) = v2;
    *(_QWORD *)((char *)this + 2084) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2008));
  }
}

```

## disassembly

```asm
0x18000d420  push    rbx
0x18000d422  push    rbp
0x18000d423  push    rsi
0x18000d424  push    rdi
0x18000d425  sub     rsp, 38h
0x18000d429  xor     ebp, ebp
0x18000d42b  mov     ebx, edx
0x18000d42d  mov     rdi, rcx
0x18000d430  test    edx, edx
0x18000d432  js      short loc_18000D440
0x18000d434  mov     ebx, [rcx+7C8h]
0x18000d43a  xor     esi, esi
0x18000d43c  test    ebx, ebx
0x18000d43e  jns     short loc_18000D4B8
0x18000d440  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d447  jz      short loc_18000D47A
0x18000d449  mov     rcx, cs:g_pDebug
0x18000d450  lea     rax, aFatalServiceEr; "Fatal service error, shutting down\n"
0x18000d457  mov     [rsp+58h+var_30], rax
0x18000d45c  lea     r9, aLogSvcAdminTer; "LOG_SVC_ADMIN::TerminateServiceAndRepor"...
0x18000d463  mov     r8d, 44Bh
0x18000d469  mov     [rsp+58h+var_38], ebx
0x18000d46d  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d474  call    cs:__imp_PuDbgPrintError
0x18000d47a  xor     r8d, r8d
0x18000d47d  mov     [rsp+58h+var_38], ebx
0x18000d481  lea     rcx, [rdi+768h]
0x18000d488  xor     r9d, r9d
0x18000d48b  mov     edx, 0C0001778h
0x18000d490  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000d496  mov     eax, ebx
0x18000d498  and     eax, 1FFF0000h
0x18000d49d  cmp     eax, 70000h
0x18000d4a2  jnz     short loc_18000D4B1
0x18000d4a4  test    ebx, ebx
0x18000d4a6  jns     short loc_18000D4AD
0x18000d4a8  movzx   esi, bx
0x18000d4ab  jmp     short loc_18000D4B8
0x18000d4ad  mov     esi, ebx
0x18000d4af  jmp     short loc_18000D4B8
0x18000d4b1  mov     esi, 42Ah
0x18000d4b6  mov     ebp, ebx
0x18000d4b8  mov     rcx, rdi; this
0x18000d4bb  call    ?Terminate@LOG_SVC_ADMIN@@AEAAXXZ; LOG_SVC_ADMIN::Terminate(void)
0x18000d4c0  cmp     dword ptr [rdi+800h], 0
0x18000d4c7  jz      short loc_18000D503
0x18000d4c9  lea     rbx, [rdi+7D8h]
0x18000d4d0  mov     rcx, rbx; lpCriticalSection
0x18000d4d3  call    cs:__imp_EnterCriticalSection
0x18000d4d9  mov     rcx, rbx; lpCriticalSection
0x18000d4dc  mov     dword ptr [rdi+814h], 1
0x18000d4e6  mov     [rdi+81Ch], esi
0x18000d4ec  mov     [rdi+820h], ebp
0x18000d4f2  mov     qword ptr [rdi+824h], 0
0x18000d4fd  call    cs:__imp_LeaveCriticalSection
0x18000d503  add     rsp, 38h
0x18000d507  pop     rdi
0x18000d508  pop     rsi
0x18000d509  pop     rbp
0x18000d50a  pop     rbx
0x18000d50b  retn
```
