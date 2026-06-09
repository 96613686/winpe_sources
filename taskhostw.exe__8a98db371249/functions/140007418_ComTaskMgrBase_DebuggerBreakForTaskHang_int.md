# ComTaskMgrBase::DebuggerBreakForTaskHang(int)

- ea: `0x140007418`
- end: `0x140007460`
- name: `?DebuggerBreakForTaskHang@ComTaskMgrBase@@KAXH@Z`
- size: `72`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140003270`
- `0x140003880`

## callees

- `0x140007418`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007420`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007420`
- `ntdll!DbgPrintEx` at `0x140007453`
- `ntdll!DbgPrintEx` at `0x140007453`

## string_xrefs

- `0x14000743c`: `ComTaskHost::StartTaskWorker or ComTaskHost::StopTaskWorker`
- `0x140007433`: `ComTaskMgrWnd::ShutdownTasksThreadProc`
- `0x140007447`: `\n================================================================================================\nWARNING: A possible task hung was detected for a COM-based scheduled task!\nThe likely culprit task is stuck on the same stack with %S.\nThis break is recoverable. If you let it go we will continue to wait on the task to complete.\n================================================================================================\n\n`

## pseudocode

```c
void __fastcall ComTaskMgrBase::DebuggerBreakForTaskHang(int a1)
{
  const wchar_t *v2; // r9

  if ( IsDebuggerPresent() || MEMORY[0x7FFE02D4] )
  {
    v2 = L"ComTaskHost::StartTaskWorker or ComTaskHost::StopTaskWorker";
    if ( !a1 )
      v2 = L"ComTaskMgrWnd::ShutdownTasksThreadProc";
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
      v2);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x140007418  push    rbx
0x14000741a  sub     rsp, 20h
0x14000741e  mov     ebx, ecx
0x140007420  call    cs:__imp_IsDebuggerPresent
0x140007426  test    eax, eax
0x140007428  jnz     short loc_140007433
0x14000742a  cmp     ds:7FFE02D4h, al
0x140007431  jz      short loc_14000745A
0x140007433  lea     rax, aComtaskmgrwndS; "ComTaskMgrWnd::ShutdownTasksThreadProc"
0x14000743a  test    ebx, ebx
0x14000743c  lea     r9, aComtaskhostSta; "ComTaskHost::StartTaskWorker or ComTask"...
0x140007443  cmovz   r9, rax
0x140007447  lea     r8, Format; "\n====================================="...
0x14000744e  xor     edx, edx; Level
0x140007450  lea     ecx, [rdx+1Ch]; ComponentId
0x140007453  call    cs:__imp_DbgPrintEx
0x140007459  int     3; Trap to Debugger
0x14000745a  add     rsp, 20h
0x14000745e  pop     rbx
0x14000745f  retn
```
