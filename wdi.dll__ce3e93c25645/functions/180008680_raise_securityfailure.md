# __raise_securityfailure

- ea: `0x180008680`
- end: `0x1800086b4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800086c0`
- `0x180008868`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000868b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000868b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180008694`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180008694`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800086ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000869a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000869a`

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
0x180008680  push    rbx
0x180008682  sub     rsp, 20h
0x180008686  mov     rbx, rcx
0x180008689  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000868b  call    cs:__imp_SetUnhandledExceptionFilter
0x180008691  mov     rcx, rbx; ExceptionInfo
0x180008694  call    cs:__imp_UnhandledExceptionFilter
0x18000869a  call    cs:__imp_GetCurrentProcess
0x1800086a0  mov     rcx, rax
0x1800086a3  mov     edx, 0C0000409h
0x1800086a8  add     rsp, 20h
0x1800086ac  pop     rbx
0x1800086ad  jmp     cs:__imp_TerminateProcess
```
