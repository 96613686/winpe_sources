# LOG_SVC_ADMIN::BeginStateTransition(ulong)

- ea: `0x18000b154`
- end: `0x18000b28a`
- name: `?BeginStateTransition@LOG_SVC_ADMIN@@AEAAJK@Z`
- size: `310`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c3a4`
- `0x18000cf98`

## callees

- `0x18000b154`
- `0x18000cba8`

## import_xrefs

- `ntdll!RtlCreateTimer` at `0x18000b22c`
- `ntdll!RtlCreateTimer` at `0x18000b22c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b279`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b279`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b17c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b17c`
- `iisutil!PuDbgPrintError` at `0x18000b270`
- `iisutil!PuDbgPrintError` at `0x18000b270`

## string_xrefs

- `0x18000b265`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000b1e0`: `couldn't set service status\n`
- `0x18000b245`: `Could not create timer\n`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::BeginStateTransition(LOG_SVC_ADMIN *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  int v7; // ebx
  void *v8; // rcx
  NTSTATUS Timer; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2008);
  v4 = 180000;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2008);
  if ( a2 != 2 )
    v4 = 20000;
  EnterCriticalSection(v5);
  if ( (unsigned int)(*((_DWORD *)this + 517) - 2) > 1 )
  {
    *((_QWORD *)this + 259) = 0;
    *((_DWORD *)this + 517) = a2;
    *((_DWORD *)this + 520) = 0;
    *((_DWORD *)this + 521) = 1;
    *((_DWORD *)this + 522) = v4;
    v7 = LOG_SVC_ADMIN::ReportServiceStatus(this);
    if ( v7 >= 0 )
    {
      if ( !*((_QWORD *)this + 263) && a2 != 2 )
      {
        v8 = (void *)*((_QWORD *)this + 264);
        if ( v8 )
        {
          Timer = RtlCreateTimer(
                    v8,
                    (PHANDLE)this + 263,
                    UpdatePendingServiceStatusCallback,
                    this,
                    0x2710u,
                    0x2710u,
                    4u);
          if ( Timer < 0 )
          {
            v7 = Timer | 0x10000000;
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
                1286,
                "LOG_SVC_ADMIN::BeginStateTransition",
                v7,
                "Could not create timer\n");
          }
        }
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        1227,
        "LOG_SVC_ADMIN::BeginStateTransition",
        v7,
        "couldn't set service status\n");
    }
  }
  else
  {
    v7 = -2147023835;
  }
  LeaveCriticalSection(v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b154  push    rbx
0x18000b156  push    rbp
0x18000b157  push    rsi
0x18000b158  push    rdi
0x18000b159  sub     rsp, 48h
0x18000b15d  cmp     edx, 2
0x18000b160  lea     rbp, [rcx+7D8h]
0x18000b167  mov     rdi, rcx
0x18000b16a  mov     eax, 4E20h
0x18000b16f  mov     ebx, 2BF20h
0x18000b174  mov     rcx, rbp; lpCriticalSection
0x18000b177  cmovnz  ebx, eax
0x18000b17a  mov     esi, edx
0x18000b17c  call    cs:__imp_EnterCriticalSection
0x18000b182  mov     eax, [rdi+814h]
0x18000b188  sub     eax, 2
0x18000b18b  cmp     eax, 1
0x18000b18e  ja      short loc_18000B19A
0x18000b190  mov     ebx, 80070425h
0x18000b195  jmp     loc_18000B276
0x18000b19a  mov     rcx, rdi; this
0x18000b19d  mov     qword ptr [rdi+818h], 0
0x18000b1a8  mov     [rdi+814h], esi
0x18000b1ae  mov     dword ptr [rdi+820h], 0
0x18000b1b8  mov     dword ptr [rdi+824h], 1
0x18000b1c2  mov     [rdi+828h], ebx
0x18000b1c8  call    ?ReportServiceStatus@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::ReportServiceStatus(void)
0x18000b1cd  mov     ebx, eax
0x18000b1cf  test    eax, eax
0x18000b1d1  jns     short loc_18000B1EF
0x18000b1d3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b1da  jz      loc_18000B276
0x18000b1e0  lea     rax, aCouldnTSetServ; "couldn't set service status\n"
0x18000b1e7  mov     r8d, 4CBh
0x18000b1ed  jmp     short loc_18000B252
0x18000b1ef  lea     rdx, [rdi+838h]; phNewTimer
0x18000b1f6  cmp     qword ptr [rdx], 0
0x18000b1fa  jnz     short loc_18000B276
0x18000b1fc  cmp     esi, 2
0x18000b1ff  jz      short loc_18000B276
0x18000b201  mov     rcx, [rdi+840h]; TimerQueue
0x18000b208  test    rcx, rcx
0x18000b20b  jz      short loc_18000B276
0x18000b20d  mov     eax, 2710h
0x18000b212  mov     [rsp+68h+Flags], 4; Flags
0x18000b21a  mov     [rsp+68h+Period], eax; Period
0x18000b21e  lea     r8, ?UpdatePendingServiceStatusCallback@@YAXPEAXE@Z; Callback
0x18000b225  mov     r9, rdi; Parameter
0x18000b228  mov     [rsp+68h+DueTime], eax; DueTime
0x18000b22c  call    cs:__imp_RtlCreateTimer
0x18000b232  test    eax, eax
0x18000b234  jns     short loc_18000B276
0x18000b236  mov     ebx, eax
0x18000b238  bts     ebx, 1Ch
0x18000b23c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b243  jz      short loc_18000B276
0x18000b245  lea     rax, aCouldNotCreate_0; "Could not create timer\n"
0x18000b24c  mov     r8d, 506h
0x18000b252  mov     rcx, cs:g_pDebug
0x18000b259  lea     r9, aLogSvcAdminBeg; "LOG_SVC_ADMIN::BeginStateTransition"
0x18000b260  mov     qword ptr [rsp+68h+Period], rax
0x18000b265  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000b26c  mov     [rsp+68h+DueTime], ebx
0x18000b270  call    cs:__imp_PuDbgPrintError
0x18000b276  mov     rcx, rbp; lpCriticalSection
0x18000b279  call    cs:__imp_LeaveCriticalSection
0x18000b27f  mov     eax, ebx
0x18000b281  add     rsp, 48h
0x18000b285  pop     rdi
0x18000b286  pop     rsi
0x18000b287  pop     rbp
0x18000b288  pop     rbx
0x18000b289  retn
```
