# __raise_securityfailure

- ea: `0x1800015e0`
- end: `0x180001614`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001620`
- `0x180001718`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18000160d`
- `KERNEL32!GetCurrentProcess` at `0x1800015fa`
- `KERNEL32!GetCurrentProcess` at `0x1800015fa`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800015eb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800015eb`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800015f4`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800015f4`

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
0x1800015e0  push    rbx
0x1800015e2  sub     rsp, 20h
0x1800015e6  mov     rbx, rcx
0x1800015e9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800015eb  call    cs:__imp_SetUnhandledExceptionFilter
0x1800015f1  mov     rcx, rbx; ExceptionInfo
0x1800015f4  call    cs:__imp_UnhandledExceptionFilter
0x1800015fa  call    cs:__imp_GetCurrentProcess
0x180001600  mov     rcx, rax
0x180001603  mov     edx, 0C0000409h
0x180001608  add     rsp, 20h
0x18000160c  pop     rbx
0x18000160d  jmp     cs:__imp_TerminateProcess
```
