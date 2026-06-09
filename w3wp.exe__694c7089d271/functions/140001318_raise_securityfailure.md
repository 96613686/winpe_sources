# __raise_securityfailure

- ea: `0x140001318`
- end: `0x14000134c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000132c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000132c`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001323`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001323`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140001345`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001332`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001332`

## pseudocode

```c
BOOL __fastcall _raise_securityfailure(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  HANDLE CurrentProcess; // rax

  SetUnhandledExceptionFilter(0);
  UnhandledExceptionFilter(ExceptionInfo);
  CurrentProcess = GetCurrentProcess();
  return TerminateProcess(CurrentProcess, 0xC0000409);
}

```

## disassembly

```asm
0x140001318  push    rbx
0x14000131a  sub     rsp, 20h
0x14000131e  mov     rbx, rcx
0x140001321  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001323  call    cs:__imp_SetUnhandledExceptionFilter
0x140001329  mov     rcx, rbx; ExceptionInfo
0x14000132c  call    cs:__imp_UnhandledExceptionFilter
0x140001332  call    cs:__imp_GetCurrentProcess
0x140001338  mov     rcx, rax
0x14000133b  mov     edx, 0C0000409h
0x140001340  add     rsp, 20h
0x140001344  pop     rbx
0x140001345  jmp     cs:__imp_TerminateProcess
```
