# __raise_securityfailure

- ea: `0x180010fa8`
- end: `0x180010fdc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010ff0`
- `0x180011198`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180010fbc`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180010fbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180010fb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180010fb3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180010fd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010fc2`

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
0x180010fa8  push    rbx
0x180010faa  sub     rsp, 20h
0x180010fae  mov     rbx, rcx
0x180010fb1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180010fb3  call    cs:__imp_SetUnhandledExceptionFilter
0x180010fb9  mov     rcx, rbx; ExceptionInfo
0x180010fbc  call    cs:__imp_UnhandledExceptionFilter
0x180010fc2  call    cs:__imp_GetCurrentProcess
0x180010fc8  mov     rcx, rax
0x180010fcb  mov     edx, 0C0000409h
0x180010fd0  add     rsp, 20h
0x180010fd4  pop     rbx
0x180010fd5  jmp     cs:__imp_TerminateProcess
```
