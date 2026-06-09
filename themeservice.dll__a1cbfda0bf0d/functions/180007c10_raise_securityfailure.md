# __raise_securityfailure

- ea: `0x180007c10`
- end: `0x180007c44`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180007c1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180007c1b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180007c24`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180007c24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007c2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007c2a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180007c3d`

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
0x180007c10  push    rbx
0x180007c12  sub     rsp, 20h
0x180007c16  mov     rbx, rcx
0x180007c19  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180007c1b  call    cs:__imp_SetUnhandledExceptionFilter
0x180007c21  mov     rcx, rbx; ExceptionInfo
0x180007c24  call    cs:__imp_UnhandledExceptionFilter
0x180007c2a  call    cs:__imp_GetCurrentProcess
0x180007c30  mov     rcx, rax
0x180007c33  mov     edx, 0C0000409h
0x180007c38  add     rsp, 20h
0x180007c3c  pop     rbx
0x180007c3d  jmp     cs:__imp_TerminateProcess
```
