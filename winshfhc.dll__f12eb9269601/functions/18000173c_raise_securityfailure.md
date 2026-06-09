# __raise_securityfailure

- ea: `0x18000173c`
- end: `0x180001770`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001780`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001769`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001756`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001750`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001750`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001747`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001747`

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
0x18000173c  push    rbx
0x18000173e  sub     rsp, 20h
0x180001742  mov     rbx, rcx
0x180001745  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001747  call    cs:__imp_SetUnhandledExceptionFilter
0x18000174d  mov     rcx, rbx; ExceptionInfo
0x180001750  call    cs:__imp_UnhandledExceptionFilter
0x180001756  call    cs:__imp_GetCurrentProcess
0x18000175c  mov     rcx, rax
0x18000175f  mov     edx, 0C0000409h
0x180001764  add     rsp, 20h
0x180001768  pop     rbx
0x180001769  jmp     cs:__imp_TerminateProcess
```
