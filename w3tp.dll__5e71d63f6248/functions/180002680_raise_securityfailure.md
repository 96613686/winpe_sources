# __raise_securityfailure

- ea: `0x180002680`
- end: `0x1800026b4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800026c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000269a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000269a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800026ad`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002694`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002694`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000268b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000268b`

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
0x180002680  push    rbx
0x180002682  sub     rsp, 20h
0x180002686  mov     rbx, rcx
0x180002689  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000268b  call    cs:__imp_SetUnhandledExceptionFilter
0x180002691  mov     rcx, rbx; ExceptionInfo
0x180002694  call    cs:__imp_UnhandledExceptionFilter
0x18000269a  call    cs:__imp_GetCurrentProcess
0x1800026a0  mov     rcx, rax
0x1800026a3  mov     edx, 0C0000409h
0x1800026a8  add     rsp, 20h
0x1800026ac  pop     rbx
0x1800026ad  jmp     cs:__imp_TerminateProcess
```
