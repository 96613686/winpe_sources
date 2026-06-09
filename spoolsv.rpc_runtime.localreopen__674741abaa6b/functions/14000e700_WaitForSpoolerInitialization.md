# WaitForSpoolerInitialization

- ea: `0x14000e700`
- end: `0x14000e7e8`
- name: `WaitForSpoolerInitialization`
- size: `232`
- prototype: `__int64(void)`
- caller_count: `34`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14000e010`
- `0x14000e250`
- `0x14000e670`
- `0x140013c60`
- `0x140061dc0`
- `0x140064710`
- `0x1400647d0`
- `0x1400649c0`
- `0x140064b10`
- `0x140064c10`
- `0x140064ca0`
- `0x140064fa0`
- `0x140065060`
- `0x140065110`
- `0x140065510`
- `0x140065610`
- `0x140068250`
- `0x140068330`
- `0x1400683c0`
- `0x1400683f0`
- `0x1400684c0`
- `0x140068610`
- `0x1400687b0`
- `0x140068830`
- `0x1400688b0`
- `0x140068970`
- `0x140068a30`
- `0x140068ac0`
- `0x140068b80`
- `0x140068da0`
- `0x14006ac30`
- `0x14006ada0`
- `0x14006aea0`
- `0x140071470`

## callees

- `0x14000e700`
- `0x14000f600`
- `0x140012c48`
- `0x140015378`
- `0x1400161d0`
- `0x14005bc28`
- `0x14005c00c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000e790`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000e790`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000e72b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000e72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e73f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e73f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e7bc`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000e780`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000e780`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e79f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e79f`

## string_xrefs

- `0x14000e74e`: `Failed to create Phase2Init event.  Error %d.`

## pseudocode

```c
void WaitForSpoolerInitialization()
{
  HANDLE v0; // rdi
  HANDLE v1; // rax
  void *v2; // rbx
  DWORD LastError; // eax
  DWORD v4; // eax
  NCoreLibrary *v5; // rcx
  unsigned int v6; // r8d
  DWORD v7; // eax

  if ( !Initialized )
  {
    v0 = RevertToPrinterSelf();
    v1 = OpenEventW(2u, 0, L"RouterPreInitEvent");
    v2 = v1;
    if ( !v1 )
    {
      LastError = GetLastError();
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "WaitForSpoolerInitialization",
        L"Failed to create Phase2Init event.  Error %d.",
        LastError);
      v4 = GetLastError();
      SplLogRouterEvent(&MSG_ROUTER_PHASE2INIT_FAILED, v4, 0);
      ExitProcess(0);
    }
    SetEvent(v1);
    CloseHandle(v2);
    if ( v0 )
    {
      if ( !ImpersonatePrinterClient(v0) )
      {
        v7 = GetLastError();
        ForceProcessShutdown(0x69u, v7);
      }
    }
    NCoreLibrary::WaitForAutoEventHandle(v5, (struct NCoreLibrary::TAutoHandle *)0xFFFFFFFFLL, v6);
  }
}

```

## disassembly

```asm
0x14000e700  mov     [rsp+arg_0], rbx
0x14000e705  push    rdi
0x14000e706  sub     rsp, 20h
0x14000e70a  cmp     cs:?Initialized@@3HA, 0; int Initialized
0x14000e711  jnz     loc_14000E7DC
0x14000e717  call    RevertToPrinterSelf
0x14000e71c  xor     edx, edx; bInheritHandle
0x14000e71e  lea     r8, Name; "RouterPreInitEvent"
0x14000e725  mov     rdi, rax
0x14000e728  lea     ecx, [rdx+2]; dwDesiredAccess
0x14000e72b  call    cs:__imp_OpenEventW
0x14000e732  nop     dword ptr [rax+rax+00h]
0x14000e737  mov     rbx, rax
0x14000e73a  test    rax, rax
0x14000e73d  jnz     short loc_14000E78D
0x14000e73f  call    cs:__imp_GetLastError
0x14000e746  nop     dword ptr [rax+rax+00h]
0x14000e74b  mov     r8d, eax
0x14000e74e  lea     rdx, aFailedToCreate_3; "Failed to create Phase2Init event.  Err"...
0x14000e755  lea     rcx, aWaitforspooler; "WaitForSpoolerInitialization"
0x14000e75c  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e761  call    cs:__imp_GetLastError
0x14000e768  nop     dword ptr [rax+rax+00h]
0x14000e76d  xor     r8d, r8d; unsigned __int16 *
0x14000e770  lea     rcx, MSG_ROUTER_PHASE2INIT_FAILED; struct _EVENT_DESCRIPTOR *
0x14000e777  mov     edx, eax; unsigned int
0x14000e779  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14000e77e  xor     ecx, ecx; uExitCode
0x14000e780  call    cs:__imp_ExitProcess
0x14000e78d  mov     rcx, rbx; hEvent
0x14000e790  call    cs:__imp_SetEvent
0x14000e797  nop     dword ptr [rax+rax+00h]
0x14000e79c  mov     rcx, rbx; hObject
0x14000e79f  call    cs:__imp_CloseHandle
0x14000e7a6  nop     dword ptr [rax+rax+00h]
0x14000e7ab  test    rdi, rdi
0x14000e7ae  jz      short loc_14000E7D4
0x14000e7b0  mov     rcx, rdi; hToken
0x14000e7b3  call    ImpersonatePrinterClient
0x14000e7b8  test    eax, eax
0x14000e7ba  jnz     short loc_14000E7D4
0x14000e7bc  call    cs:__imp_GetLastError
0x14000e7c3  nop     dword ptr [rax+rax+00h]
0x14000e7c8  mov     edx, eax; unsigned int
0x14000e7ca  mov     ecx, 69h ; 'i'; unsigned int
0x14000e7cf  call    ?ForceProcessShutdown@@YAXKK@Z; ForceProcessShutdown(ulong,ulong)
0x14000e7d4  or      edx, 0FFFFFFFFh; struct NCoreLibrary::TAutoHandle *
0x14000e7d7  call    ?WaitForAutoEventHandle@NCoreLibrary@@YAJPEAVTAutoHandle@1@K@Z; NCoreLibrary::WaitForAutoEventHandle(NCoreLibrary::TAutoHandle *,ulong)
0x14000e7dc  mov     rbx, [rsp+28h+arg_0]
0x14000e7e1  add     rsp, 20h
0x14000e7e5  pop     rdi
0x14000e7e6  retn
```
