# WaitForSpoolerInitialization

- ea: `0x14000d520`
- end: `0x14000d5dd`
- name: `WaitForSpoolerInitialization`
- size: `189`
- prototype: `__int64(void)`
- caller_count: `34`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14000ce80`
- `0x14000d0a0`
- `0x14000d4a0`
- `0x140012a20`
- `0x14005c280`
- `0x14005ea30`
- `0x14005ead0`
- `0x14005ec90`
- `0x14005edc0`
- `0x14005eeb0`
- `0x14005ef30`
- `0x14005f1d0`
- `0x14005f290`
- `0x14005f330`
- `0x14005f720`
- `0x14005f810`
- `0x140062290`
- `0x140062360`
- `0x1400623e0`
- `0x140062410`
- `0x1400624d0`
- `0x140062610`
- `0x140062790`
- `0x140062800`
- `0x140062880`
- `0x140062930`
- `0x1400629e0`
- `0x140062a60`
- `0x140062b10`
- `0x140062d10`
- `0x140064940`
- `0x140064aa0`
- `0x140064b80`
- `0x14006a910`

## callees

- `0x14000d520`
- `0x14000e590`
- `0x140011ebc`
- `0x1400140cc`
- `0x140014eb0`
- `0x140056768`
- `0x140056b18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000d598`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000d598`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000d54b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000d54b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d5b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d5b8`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000d58e`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000d58e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d5a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d5a1`

## string_xrefs

- `0x14000d562`: `Failed to create Phase2Init event.  Error %d.`

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
0x14000d520  mov     [rsp+arg_0], rbx
0x14000d525  push    rdi
0x14000d526  sub     rsp, 20h
0x14000d52a  cmp     cs:?Initialized@@3HA, 0; int Initialized
0x14000d531  jnz     loc_14000D5D2
0x14000d537  call    RevertToPrinterSelf
0x14000d53c  xor     edx, edx; bInheritHandle
0x14000d53e  lea     r8, Name; "RouterPreInitEvent"
0x14000d545  mov     rdi, rax
0x14000d548  lea     ecx, [rdx+2]; dwDesiredAccess
0x14000d54b  call    cs:__imp_OpenEventW
0x14000d551  mov     rbx, rax
0x14000d554  test    rax, rax
0x14000d557  jnz     short loc_14000D595
0x14000d559  call    cs:__imp_GetLastError
0x14000d55f  mov     r8d, eax
0x14000d562  lea     rdx, aFailedToCreate_3; "Failed to create Phase2Init event.  Err"...
0x14000d569  lea     rcx, aWaitforspooler; "WaitForSpoolerInitialization"
0x14000d570  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000d575  call    cs:__imp_GetLastError
0x14000d57b  xor     r8d, r8d; unsigned __int16 *
0x14000d57e  lea     rcx, MSG_ROUTER_PHASE2INIT_FAILED; struct _EVENT_DESCRIPTOR *
0x14000d585  mov     edx, eax; unsigned int
0x14000d587  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14000d58c  xor     ecx, ecx; uExitCode
0x14000d58e  call    cs:__imp_ExitProcess
0x14000d595  mov     rcx, rbx; hEvent
0x14000d598  call    cs:__imp_SetEvent
0x14000d59e  mov     rcx, rbx; hObject
0x14000d5a1  call    cs:__imp_CloseHandle
0x14000d5a7  test    rdi, rdi
0x14000d5aa  jz      short loc_14000D5CA
0x14000d5ac  mov     rcx, rdi; hToken
0x14000d5af  call    ImpersonatePrinterClient
0x14000d5b4  test    eax, eax
0x14000d5b6  jnz     short loc_14000D5CA
0x14000d5b8  call    cs:__imp_GetLastError
0x14000d5be  mov     edx, eax; unsigned int
0x14000d5c0  mov     ecx, 69h ; 'i'; unsigned int
0x14000d5c5  call    ?ForceProcessShutdown@@YAXKK@Z; ForceProcessShutdown(ulong,ulong)
0x14000d5ca  or      edx, 0FFFFFFFFh; struct NCoreLibrary::TAutoHandle *
0x14000d5cd  call    ?WaitForAutoEventHandle@NCoreLibrary@@YAJPEAVTAutoHandle@1@K@Z; NCoreLibrary::WaitForAutoEventHandle(NCoreLibrary::TAutoHandle *,ulong)
0x14000d5d2  mov     rbx, [rsp+28h+arg_0]
0x14000d5d7  add     rsp, 20h
0x14000d5db  pop     rdi
0x14000d5dc  retn
```
