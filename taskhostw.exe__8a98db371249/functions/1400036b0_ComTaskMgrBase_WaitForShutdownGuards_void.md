# ComTaskMgrBase::WaitForShutdownGuards(void)

- ea: `0x1400036b0`
- end: `0x140003846`
- name: `?WaitForShutdownGuards@ComTaskMgrBase@@KAJXZ`
- size: `406`
- prototype: `signed int(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140003250`
- `0x140003270`
- `0x140003b10`

## callees

- `0x1400036b0`
- `0x140009330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400037fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400037fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400037a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400037a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000376a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000376a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037b7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003737`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003737`
- `ntdll!DbgPrintEx` at `0x1400037e4`
- `ntdll!DbgPrintEx` at `0x1400037e4`

## string_xrefs

- `0x140003705`: `EnableDebuggerBreakForTaskHang`
- `0x1400037cf`: `ComTaskHost::StartTaskWorker or ComTaskHost::StopTaskWorker`
- `0x1400037d8`: `\n================================================================================================\nWARNING: A possible task hung was detected for a COM-based scheduled task!\nThe likely culprit task is stuck on the same stack with %S.\nThis break is recoverable. If you let it go we will continue to wait on the task to complete.\n================================================================================================\n\n`

## pseudocode

```c
signed int ComTaskMgrBase::WaitForShutdownGuards(void)
{
  void *v0; // rbx
  unsigned int ValueW; // eax
  BOOL v2; // eax
  DWORD v3; // edx
  DWORD v4; // eax
  signed int result; // eax
  int pvData; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF

  if ( _InterlockedCompareExchange(&dword_1400159E4, 0, 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)&ShutdownMgr::s_sync, 0xFFFFFFFF) == 1 )
  {
    SetEvent((HANDLE)_InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1));
  }
  v0 = (void *)_InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1);
  while ( 1 )
  {
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule",
               L"EnableDebuggerBreakForTaskHang",
               0x10u,
               0,
               &pvData,
               &pcbData);
    if ( ValueW )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids, ValueW);
      v2 = 0;
    }
    else
    {
      v2 = pvData != 0;
    }
    v3 = 20000;
    if ( !v2 )
      v3 = -1;
    v4 = WaitForSingleObject(v0, v3);
    if ( !v4 )
      return 0;
    if ( v4 != 258 )
      break;
    if ( IsDebuggerPresent() || MEMORY[0x7FFE02D4] )
    {
      DbgPrintEx(
        0x1Cu,
        0,
        "\n"
        "================================================================================================\n"
        "WARNING: A possible task hung was detected for a COM-based scheduled task!\n"
        "The likely culprit task is stuck on the same stack with %S.\n"
        "This break is recoverable. If you let it go we will continue to wait on the task to complete.\n"
        "================================================================================================\n"
        "\n",
        L"ComTaskHost::StartTaskWorker or ComTaskHost::StopTaskWorker");
      __debugbreak();
    }
  }
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x1400036b0  mov     [rsp+arg_10], rbx
0x1400036b5  push    rbp
0x1400036b6  push    rsi
0x1400036b7  push    rdi
0x1400036b8  sub     rsp, 40h
0x1400036bc  xor     edi, edi
0x1400036be  mov     eax, 1
0x1400036c3  mov     ecx, edi
0x1400036c5  lock cmpxchg cs:dword_1400159E4, ecx
0x1400036cd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400036d4  test    eax, eax
0x1400036d6  jnz     loc_140003783
0x1400036dc  mov     rax, rbx
0x1400036df  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rbx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x1400036e8  mov     rbx, rax
0x1400036eb  lea     rsi, WPP_GLOBAL_Control
0x1400036f2  mov     ebp, 0FFFFFFFFh
0x1400036f7  lea     rax, [rsp+58h+arg_8]
0x1400036fc  mov     [rsp+58h+arg_0], edi
0x140003700  mov     [rsp+58h+pcbData], rax; pcbData
0x140003705  lea     r8, Value; "EnableDebuggerBreakForTaskHang"
0x14000370c  lea     rax, [rsp+58h+arg_0]
0x140003711  mov     [rsp+58h+arg_8], 4
0x140003719  mov     [rsp+58h+pvData], rax; pvData
0x14000371e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140003725  mov     r9d, 10h; dwFlags
0x14000372b  mov     [rsp+58h+pdwType], rdi; pdwType
0x140003730  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140003737  call    cs:__imp_RegGetValueW
0x14000373d  test    eax, eax
0x14000373f  jz      loc_1400037F0
0x140003745  mov     rcx, cs:WPP_GLOBAL_Control
0x14000374c  cmp     rcx, rsi
0x14000374f  jz      short loc_14000375B
0x140003751  test    byte ptr [rcx+1Ch], 1
0x140003755  jnz     loc_14000381F
0x14000375b  mov     eax, edi
0x14000375d  test    eax, eax
0x14000375f  mov     edx, 4E20h
0x140003764  mov     rcx, rbx; hHandle
0x140003767  cmovz   edx, ebp; dwMilliseconds
0x14000376a  call    cs:__imp_WaitForSingleObject
0x140003770  test    eax, eax
0x140003772  jnz     short loc_1400037B0
0x140003774  mov     eax, edi
0x140003776  mov     rbx, [rsp+58h+arg_10]
0x14000377b  add     rsp, 40h
0x14000377f  pop     rdi
0x140003780  pop     rsi
0x140003781  pop     rbp
0x140003782  retn
0x140003783  mov     eax, ebx
0x140003785  lock xadd cs:?s_sync@ShutdownMgr@@0USync@1@A, eax; ShutdownMgr::Sync ShutdownMgr::s_sync
0x14000378d  cmp     eax, 1
0x140003790  jnz     loc_1400036DC
0x140003796  mov     rax, rbx
0x140003799  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rbx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x1400037a2  mov     rcx, rax; hEvent
0x1400037a5  call    cs:__imp_SetEvent
0x1400037ab  jmp     loc_1400036DC
0x1400037b0  cmp     eax, 102h
0x1400037b5  jnz     short loc_1400037FE
0x1400037b7  call    cs:__imp_IsDebuggerPresent
0x1400037bd  test    eax, eax
0x1400037bf  jnz     short loc_1400037CF
0x1400037c1  cmp     ds:7FFE02D4h, dil
0x1400037c9  jz      loc_1400036F7
0x1400037cf  lea     r9, aComtaskhostSta; "ComTaskHost::StartTaskWorker or ComTask"...
0x1400037d6  xor     edx, edx; Level
0x1400037d8  lea     r8, Format; "\n====================================="...
0x1400037df  mov     ecx, 1Ch; ComponentId
0x1400037e4  call    cs:__imp_DbgPrintEx
0x1400037ea  int     3; Trap to Debugger
0x1400037eb  jmp     loc_1400036F7
0x1400037f0  mov     eax, edi
0x1400037f2  cmp     [rsp+58h+arg_0], eax
0x1400037f6  setnz   al
0x1400037f9  jmp     loc_14000375D
0x1400037fe  call    cs:__imp_GetLastError
0x140003804  test    eax, eax
0x140003806  jg      short loc_14000383C
0x140003808  mov     rbx, [rsp+58h+arg_10]
0x14000380d  test    eax, eax
0x14000380f  mov     ecx, 80004005h
0x140003814  cmovns  eax, ecx
0x140003817  add     rsp, 40h
0x14000381b  pop     rdi
0x14000381c  pop     rsi
0x14000381d  pop     rbp
0x14000381e  retn
0x14000381f  mov     rcx, [rcx+10h]
0x140003823  lea     r8, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids
0x14000382a  mov     edx, 0Dh
0x14000382f  mov     r9d, eax
0x140003832  call    WPP_SF_d
0x140003837  jmp     loc_14000375B
0x14000383c  movzx   eax, ax
0x14000383f  or      eax, 80070000h
0x140003844  jmp     short loc_140003808
```
