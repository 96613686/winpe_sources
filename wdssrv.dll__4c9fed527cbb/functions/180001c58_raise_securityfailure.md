# __raise_securityfailure

- ea: `0x180001c58`
- end: `0x180001c8c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001ca0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001c85`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001c63`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001c63`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001c6c`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001c6c`
- `KERNEL32!GetCurrentProcess` at `0x180001c72`
- `KERNEL32!GetCurrentProcess` at `0x180001c72`

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
0x180001c58  push    rbx
0x180001c5a  sub     rsp, 20h
0x180001c5e  mov     rbx, rcx
0x180001c61  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001c63  call    cs:__imp_SetUnhandledExceptionFilter
0x180001c69  mov     rcx, rbx; ExceptionInfo
0x180001c6c  call    cs:__imp_UnhandledExceptionFilter
0x180001c72  call    cs:__imp_GetCurrentProcess
0x180001c78  mov     rcx, rax
0x180001c7b  mov     edx, 0C0000409h
0x180001c80  add     rsp, 20h
0x180001c84  pop     rbx
0x180001c85  jmp     cs:__imp_TerminateProcess
```
