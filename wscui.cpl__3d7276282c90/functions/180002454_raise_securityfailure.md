# __raise_securityfailure

- ea: `0x180002454`
- end: `0x180002488`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000245f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000245f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002468`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002468`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002481`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000246e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000246e`

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
0x180002454  push    rbx
0x180002456  sub     rsp, 20h
0x18000245a  mov     rbx, rcx
0x18000245d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000245f  call    cs:__imp_SetUnhandledExceptionFilter
0x180002465  mov     rcx, rbx; ExceptionInfo
0x180002468  call    cs:__imp_UnhandledExceptionFilter
0x18000246e  call    cs:__imp_GetCurrentProcess
0x180002474  mov     rcx, rax
0x180002477  mov     edx, 0C0000409h
0x18000247c  add     rsp, 20h
0x180002480  pop     rbx
0x180002481  jmp     cs:__imp_TerminateProcess
```
