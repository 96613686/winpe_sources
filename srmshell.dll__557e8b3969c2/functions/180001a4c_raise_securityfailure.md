# __raise_securityfailure

- ea: `0x180001a4c`
- end: `0x180001a80`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001a90`
- `0x180001c38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001a57`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001a57`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001a60`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001a60`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a66`

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
0x180001a4c  push    rbx
0x180001a4e  sub     rsp, 20h
0x180001a52  mov     rbx, rcx
0x180001a55  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001a57  call    cs:__imp_SetUnhandledExceptionFilter
0x180001a5d  mov     rcx, rbx; ExceptionInfo
0x180001a60  call    cs:__imp_UnhandledExceptionFilter
0x180001a66  call    cs:__imp_GetCurrentProcess
0x180001a6c  mov     rcx, rax
0x180001a6f  mov     edx, 0C0000409h
0x180001a74  add     rsp, 20h
0x180001a78  pop     rbx
0x180001a79  jmp     cs:__imp_TerminateProcess
```
