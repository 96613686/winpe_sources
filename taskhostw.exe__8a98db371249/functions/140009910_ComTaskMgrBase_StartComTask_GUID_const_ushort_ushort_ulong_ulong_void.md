# ComTaskMgrBase::StartComTask(_GUID * const,ushort *,ushort *,ulong,ulong,void * *)

- ea: `0x140009910`
- end: `0x140009a30`
- name: `?StartComTask@ComTaskMgrBase@@UEAAJQEAU_GUID@@PEAG1KKPEAPEAX@Z`
- size: `288`
- prototype: `__int64 __fastcall(ComTaskMgrBase *this, struct _GUID *const, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400050c0`
- `0x140006210`
- `0x140006550`
- `0x1400067a0`
- `0x140006f60`
- `0x140007f24`
- `0x140009910`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400099b4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400099b4`
- `ntdll!DbgPrintEx` at `0x1400099d3`
- `ntdll!DbgPrintEx` at `0x1400099d3`

## string_xrefs

- `0x140009a0f`: `StartComTask`
- `0x1400099c7`: `\n\n======================================================================\nWARNING: This is not an error but a forced debug break enabled by setting the registry key\nHKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\EnableDebuggerBreakForTaskStart\nThis break is recoverable. If you let it go we will continue starting the task.\n======================================================================\n\n`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::StartComTask(
        ComTaskMgrBase *this,
        struct _GUID *const a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        void **a7)
{
  ComTaskHost *v10; // rax
  ComTaskHost *v11; // rbx
  int v12; // edi
  __int32 v14; // [rsp+30h] [rbp-18h] BYREF
  ComTaskHost *v15; // [rsp+38h] [rbp-10h]

  v14 = 0;
  _InterlockedExchange(&v14, 0);
  _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
  _InterlockedExchange(&v14, _InterlockedCompareExchange(&dword_1400159E4, 0, 0) != 0);
  if ( _InterlockedCompareExchange(&v14, 0, 0) )
  {
    v10 = (ComTaskHost *)operator new(0x88u);
    v15 = v10;
    if ( v10 )
      v11 = ComTaskHost::ComTaskHost(v10, a2, a3, a4, a5, a6);
    else
      v11 = 0;
    if ( v11 )
    {
      if ( (unsigned int)ComTaskMgrBase::IsDebuggerBreakForTaskStartEnabled(a3) )
      {
        if ( IsDebuggerPresent() || MEMORY[0x7FFE02D4] )
          DbgPrintEx(
            0x1Cu,
            0,
            "\n"
            "\n"
            "======================================================================\n"
            "WARNING: This is not an error but a forced debug break enabled by setting the registry key\n"
            "HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\EnableDebuggerBreakForTaskStart\n"
            "This break is recoverable. If you let it go we will continue starting the task.\n"
            "======================================================================\n"
            "\n");
        __debugbreak();
      }
      v12 = ComTaskHost::Start(v11);
      if ( v12 >= 0 )
        *a7 = v11;
    }
    else
    {
      v12 = -2147024882;
    }
  }
  else
  {
    v11 = 0;
    v12 = -2147024255;
  }
  ShutdownGuard::~ShutdownGuard((ShutdownGuard *)&v14);
  if ( v12 < 0 && v11 )
    ComTaskHost::ReleaseLifetimeRef(v11, L"StartComTask");
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140009910  mov     [rsp+arg_0], rbx
0x140009915  mov     [rsp+arg_8], rsi
0x14000991a  push    rdi
0x14000991b  sub     rsp, 40h
0x14000991f  mov     rbx, r9
0x140009922  mov     rdi, r8
0x140009925  mov     rsi, rdx
0x140009928  mov     [rsp+48h+var_18], 0
0x140009930  xor     eax, eax
0x140009932  xchg    eax, [rsp+48h+var_18]
0x140009936  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x14000993d  xor     ecx, ecx
0x14000993f  xor     eax, eax
0x140009941  lock cmpxchg cs:dword_1400159E4, ecx
0x140009949  setnz   cl
0x14000994c  xchg    ecx, [rsp+48h+var_18]
0x140009950  xor     ecx, ecx
0x140009952  xor     eax, eax
0x140009954  lock cmpxchg [rsp+48h+var_18], ecx
0x14000995a  jz      loc_1400099F5
0x140009960  mov     ecx, 88h; Size
0x140009965  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000996a  mov     [rsp+48h+var_10], rax
0x14000996f  test    rax, rax
0x140009972  jz      short loc_14000999A
0x140009974  mov     ecx, [rsp+48h+arg_28]
0x140009978  mov     [rsp+48h+var_20], ecx; unsigned int
0x14000997c  mov     ecx, [rsp+48h+arg_20]
0x140009980  mov     [rsp+48h+var_28], ecx; unsigned int
0x140009984  mov     r9, rbx; unsigned __int16 *
0x140009987  mov     r8, rdi; unsigned __int16 *
0x14000998a  mov     rdx, rsi; struct _GUID *
0x14000998d  mov     rcx, rax; this
0x140009990  call    ??0ComTaskHost@@QEAA@QEAU_GUID@@PEAG1KK@Z; ComTaskHost::ComTaskHost(_GUID * const,ushort *,ushort *,ulong,ulong)
0x140009995  mov     rbx, rax
0x140009998  jmp     short loc_14000999C
0x14000999a  xor     ebx, ebx
0x14000999c  test    rbx, rbx
0x14000999f  jnz     short loc_1400099A8
0x1400099a1  mov     edi, 8007000Eh
0x1400099a6  jmp     short loc_1400099FC
0x1400099a8  mov     rcx, rdi; SubStr
0x1400099ab  call    ?IsDebuggerBreakForTaskStartEnabled@ComTaskMgrBase@@KAHPEBG@Z; ComTaskMgrBase::IsDebuggerBreakForTaskStartEnabled(ushort const *)
0x1400099b0  test    eax, eax
0x1400099b2  jz      short loc_1400099DA
0x1400099b4  call    cs:__imp_IsDebuggerPresent
0x1400099ba  test    eax, eax
0x1400099bc  jnz     short loc_1400099C7
0x1400099be  cmp     ds:7FFE02D4h, al
0x1400099c5  jz      short loc_1400099D9
0x1400099c7  lea     r8, asc_140010E60; "\n\n==================================="...
0x1400099ce  xor     edx, edx; Level
0x1400099d0  lea     ecx, [rdx+1Ch]; ComponentId
0x1400099d3  call    cs:__imp_DbgPrintEx
0x1400099d9  int     3; Trap to Debugger
0x1400099da  mov     rcx, rbx; this
0x1400099dd  call    ?Start@ComTaskHost@@QEAAJXZ; ComTaskHost::Start(void)
0x1400099e2  mov     edi, eax
0x1400099e4  test    eax, eax
0x1400099e6  js      short loc_1400099FC
0x1400099e8  mov     rax, [rsp+48h+arg_30]
0x1400099f0  mov     [rax], rbx
0x1400099f3  jmp     short loc_1400099FC
0x1400099f5  xor     ebx, ebx
0x1400099f7  mov     edi, 80070281h
0x1400099fc  lea     rcx, [rsp+48h+var_18]; this
0x140009a01  call    ??1ShutdownGuard@@QEAA@XZ; ShutdownGuard::~ShutdownGuard(void)
0x140009a06  test    edi, edi
0x140009a08  jns     short loc_140009A1E
0x140009a0a  test    rbx, rbx
0x140009a0d  jz      short loc_140009A1E
0x140009a0f  lea     rdx, aStartcomtask; "StartComTask"
0x140009a16  mov     rcx, rbx; this
0x140009a19  call    ?ReleaseLifetimeRef@ComTaskHost@@QEAAKPEBG@Z; ComTaskHost::ReleaseLifetimeRef(ushort const *)
0x140009a1e  mov     eax, edi
0x140009a20  mov     rbx, [rsp+48h+arg_0]
0x140009a25  mov     rsi, [rsp+48h+arg_8]
0x140009a2a  add     rsp, 40h
0x140009a2e  pop     rdi
0x140009a2f  retn
```
