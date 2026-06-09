# __raise_securityfailure

- ea: `0x1800104f4`
- end: `0x180010528`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010530`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800104ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800104ff`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180010508`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180010508`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001050e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001050e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180010521`

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
0x1800104f4  push    rbx
0x1800104f6  sub     rsp, 20h
0x1800104fa  mov     rbx, rcx
0x1800104fd  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800104ff  call    cs:__imp_SetUnhandledExceptionFilter
0x180010505  mov     rcx, rbx; ExceptionInfo
0x180010508  call    cs:__imp_UnhandledExceptionFilter
0x18001050e  call    cs:__imp_GetCurrentProcess
0x180010514  mov     rcx, rax
0x180010517  mov     edx, 0C0000409h
0x18001051c  add     rsp, 20h
0x180010520  pop     rbx
0x180010521  jmp     cs:__imp_TerminateProcess
```
