# NVMeStorageHealthMonitor::HandleEvent(void *)

- ea: `0x18006fbb8`
- end: `0x18006fd73`
- name: `?HandleEvent@NVMeStorageHealthMonitor@@CAKPEAX@Z`
- size: `443`
- prototype: `unsigned int __fastcall(EVT_HANDLE Fragment)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800700f0`

## callees

- `0x180057218`
- `0x18006fbb8`
- `0x18006fd7c`
- `0x180070050`
- `0x1800701c0`
- `0x180070238`
- `0x1800702f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006fd5d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006fd5d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18006fc6d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18006fc6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fd24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fd24`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18006fc53`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18006fc9e`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18006fc53`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18006fc9e`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18006fd4f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18006fd4f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x18006fbf9`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x18006fbf9`

## string_xrefs

- `0x18006fc0d`: `Failed to create Render Context`

## pseudocode

```c
__int64 __fastcall NVMeStorageHealthMonitor::HandleEvent(EVT_HANDLE Fragment)
{
  EVT_HANDLE RenderContext; // rsi
  DWORD LastError; // ebx
  __int64 v4; // rax
  struct _EVT_VARIANT *Buffer; // rdi
  DWORD v6; // ebx
  const char *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  DWORD v10; // r14d
  __int64 v11; // rax
  _BYTE v13[32]; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v14[2]; // [rsp+60h] [rbp+7h] BYREF
  __int128 v15; // [rsp+80h] [rbp+27h]
  DWORD BufferSize; // [rsp+C8h] [rbp+6Fh] BYREF
  DWORD PropertyCount; // [rsp+D0h] [rbp+77h] BYREF

  BufferSize = 0;
  PropertyCount = 0;
  memset(v14, 0, sizeof(v14));
  v15 = 0;
  RenderContext = EvtCreateRenderContext(6u, &ValuePaths, 0);
  if ( !RenderContext )
  {
    LastError = GetLastError();
    v4 = std::string::string(v13, "Failed to create Render Context");
    StorageHealthMonitorTelemetry::TraceLoggingWriteEventWithOneParam(v4, LastError);
    return LastError;
  }
  Buffer = 0;
  if ( EvtRender(RenderContext, Fragment, 0, 0, 0, &BufferSize, &PropertyCount) )
    goto LABEL_11;
  if ( GetLastError() == 122 )
  {
    v6 = BufferSize;
    Buffer = (struct _EVT_VARIANT *)malloc(BufferSize);
    if ( !Buffer )
    {
      LastError = 14;
      v7 = "EvtRender malloc failed";
      goto LABEL_10;
    }
    EvtRender(RenderContext, Fragment, 0, v6, Buffer, &BufferSize, &PropertyCount);
  }
  LastError = GetLastError();
  if ( !LastError )
  {
LABEL_11:
    LastError = NVMeStorageHealthMonitor::ParseRenderedEvent(Buffer, (struct NVMeDiskInfo *)v14);
    v9 = std::string::string(v13, "RenderEventStatus");
    StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(v9, LastError);
    if ( BYTE2(v15) || (_WORD)v15 )
    {
      v10 = 0;
      if ( (unsigned int)NVMeStorageHealthMonitor::NotifyAllUsers((struct NVMeDiskInfo *)v14) )
        v10 = GetLastError();
      v11 = std::string::string(v13, "NotifyAllUsersStatus");
      StorageHealthMonitorTelemetry::TraceLoggingWriteNotifyAllUsers(v11, v10, *(_QWORD *)&v14[0]);
    }
    goto LABEL_16;
  }
  v7 = "EvtRender failed";
LABEL_10:
  v8 = std::string::string(v13, v7);
  StorageHealthMonitorTelemetry::TraceLoggingWriteEventWithOneParam(v8, LastError);
LABEL_16:
  EvtClose(RenderContext);
  if ( Buffer )
    free(Buffer);
  return LastError;
}

```

## disassembly

```asm
0x18006fbb8  push    rbp
0x18006fbba  push    rbx
0x18006fbbb  push    rsi
0x18006fbbc  push    rdi
0x18006fbbd  push    r14
0x18006fbbf  lea     rbp, [rsp-37h]
0x18006fbc4  sub     rsp, 90h
0x18006fbcb  xorps   xmm0, xmm0
0x18006fbce  mov     [rbp+57h+BufferSize], 0
0x18006fbd5  xor     r8d, r8d; Flags
0x18006fbd8  mov     [rbp+57h+arg_10], 0
0x18006fbdf  mov     r14, rcx
0x18006fbe2  lea     rdx, ValuePaths; ValuePaths
0x18006fbe9  movups  [rbp+57h+var_50], xmm0
0x18006fbed  lea     ecx, [r8+6]; ValuePathsCount
0x18006fbf1  movups  [rbp+57h+var_40], xmm0
0x18006fbf5  movups  [rbp+57h+var_30], xmm0
0x18006fbf9  call    cs:__imp_EvtCreateRenderContext
0x18006fbff  mov     rsi, rax
0x18006fc02  test    rax, rax
0x18006fc05  jnz     short loc_18006FC2E
0x18006fc07  call    cs:__imp_GetLastError
0x18006fc0d  lea     rdx, aFailedToCreate; "Failed to create Render Context"
0x18006fc14  mov     ebx, eax
0x18006fc16  lea     rcx, [rbp+57h+var_70]
0x18006fc1a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18006fc1f  mov     edx, ebx
0x18006fc21  mov     rcx, rax
0x18006fc24  call    ?TraceLoggingWriteEventWithOneParam@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteEventWithOneParam(std::string,ulong)
0x18006fc29  jmp     loc_18006FD63
0x18006fc2e  lea     rax, [rbp+57h+arg_10]
0x18006fc32  xor     edi, edi
0x18006fc34  mov     [rsp+0B0h+PropertyCount], rax; PropertyCount
0x18006fc39  xor     r9d, r9d; BufferSize
0x18006fc3c  lea     rax, [rbp+57h+BufferSize]
0x18006fc40  xor     r8d, r8d; Flags
0x18006fc43  mov     [rsp+0B0h+BufferUsed], rax; BufferUsed
0x18006fc48  mov     rdx, r14; Fragment
0x18006fc4b  mov     rcx, rsi; Context
0x18006fc4e  mov     [rsp+0B0h+Buffer], rdi; Buffer
0x18006fc53  call    cs:__imp_EvtRender
0x18006fc59  test    eax, eax
0x18006fc5b  jnz     short loc_18006FCDA
0x18006fc5d  call    cs:__imp_GetLastError
0x18006fc63  cmp     eax, 7Ah ; 'z'
0x18006fc66  jnz     short loc_18006FCA4
0x18006fc68  mov     ebx, [rbp+57h+BufferSize]
0x18006fc6b  mov     ecx, ebx; Size
0x18006fc6d  call    cs:__imp_malloc
0x18006fc73  mov     rdi, rax
0x18006fc76  test    rax, rax
0x18006fc79  jz      short loc_18006FCB9
0x18006fc7b  lea     rax, [rbp+57h+arg_10]
0x18006fc7f  mov     r9d, ebx; BufferSize
0x18006fc82  mov     [rsp+0B0h+PropertyCount], rax; PropertyCount
0x18006fc87  xor     r8d, r8d; Flags
0x18006fc8a  lea     rax, [rbp+57h+BufferSize]
0x18006fc8e  mov     rdx, r14; Fragment
0x18006fc91  mov     [rsp+0B0h+BufferUsed], rax; BufferUsed
0x18006fc96  mov     rcx, rsi; Context
0x18006fc99  mov     [rsp+0B0h+Buffer], rdi; Buffer
0x18006fc9e  call    cs:__imp_EvtRender
0x18006fca4  call    cs:__imp_GetLastError
0x18006fcaa  mov     ebx, eax
0x18006fcac  test    eax, eax
0x18006fcae  jz      short loc_18006FCDA
0x18006fcb0  lea     rdx, aEvtrenderFaile; "EvtRender failed"
0x18006fcb7  jmp     short loc_18006FCC5
0x18006fcb9  mov     ebx, 0Eh
0x18006fcbe  lea     rdx, aEvtrenderMallo; "EvtRender malloc failed"
0x18006fcc5  lea     rcx, [rbp+57h+var_70]
0x18006fcc9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18006fcce  mov     edx, ebx
0x18006fcd0  mov     rcx, rax
0x18006fcd3  call    ?TraceLoggingWriteEventWithOneParam@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteEventWithOneParam(std::string,ulong)
0x18006fcd8  jmp     short loc_18006FD4C
0x18006fcda  lea     rdx, [rbp+57h+var_50]; struct NVMeDiskInfo *
0x18006fcde  mov     rcx, rdi; struct _EVT_VARIANT *
0x18006fce1  call    ?ParseRenderedEvent@NVMeStorageHealthMonitor@@CAKPEAU_EVT_VARIANT@@AEAUNVMeDiskInfo@@@Z; NVMeStorageHealthMonitor::ParseRenderedEvent(_EVT_VARIANT *,NVMeDiskInfo &)
0x18006fce6  lea     rdx, aRendereventsta; "RenderEventStatus"
0x18006fced  mov     ebx, eax
0x18006fcef  lea     rcx, [rbp+57h+var_70]
0x18006fcf3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18006fcf8  mov     edx, ebx
0x18006fcfa  mov     rcx, rax
0x18006fcfd  call    ?TraceLoggingWriteStatusErrorCode@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(std::string,ulong)
0x18006fd02  cmp     byte ptr [rbp+57h+var_30+2], 0
0x18006fd06  jnz     short loc_18006FD14
0x18006fd08  cmp     byte ptr [rbp+57h+var_30], 0
0x18006fd0c  jnz     short loc_18006FD14
0x18006fd0e  cmp     byte ptr [rbp+57h+var_30+1], 0
0x18006fd12  jz      short loc_18006FD4C
0x18006fd14  lea     rcx, [rbp+57h+var_50]; struct NVMeDiskInfo *
0x18006fd18  xor     r14d, r14d
0x18006fd1b  call    ?NotifyAllUsers@NVMeStorageHealthMonitor@@CAJAEAUNVMeDiskInfo@@@Z; NVMeStorageHealthMonitor::NotifyAllUsers(NVMeDiskInfo &)
0x18006fd20  test    eax, eax
0x18006fd22  jz      short loc_18006FD2D
0x18006fd24  call    cs:__imp_GetLastError
0x18006fd2a  mov     r14d, eax
0x18006fd2d  lea     rdx, aNotifyallusers; "NotifyAllUsersStatus"
0x18006fd34  lea     rcx, [rbp+57h+var_70]
0x18006fd38  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18006fd3d  mov     r8, qword ptr [rbp+57h+var_50]
0x18006fd41  mov     edx, r14d
0x18006fd44  mov     rcx, rax
0x18006fd47  call    ?TraceLoggingWriteNotifyAllUsers@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@KPEAU_GUID@@@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteNotifyAllUsers(std::string,ulong,_GUID *)
0x18006fd4c  mov     rcx, rsi; Object
0x18006fd4f  call    cs:__imp_EvtClose
0x18006fd55  test    rdi, rdi
0x18006fd58  jz      short loc_18006FD63
0x18006fd5a  mov     rcx, rdi; Block
0x18006fd5d  call    cs:__imp_free
0x18006fd63  mov     eax, ebx
0x18006fd65  add     rsp, 90h
0x18006fd6c  pop     r14
0x18006fd6e  pop     rdi
0x18006fd6f  pop     rsi
0x18006fd70  pop     rbx
0x18006fd71  pop     rbp
0x18006fd72  retn
```
