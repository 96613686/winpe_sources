# __raise_securityfailure

- ea: `0x180001ad8`
- end: `0x180001b0c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b20`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001b05`
- `KERNEL32!GetCurrentProcess` at `0x180001af2`
- `KERNEL32!GetCurrentProcess` at `0x180001af2`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001ae3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001ae3`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001aec`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001aec`

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
0x180001ad8  push    rbx
0x180001ada  sub     rsp, 20h
0x180001ade  mov     rbx, rcx
0x180001ae1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001ae3  call    cs:__imp_SetUnhandledExceptionFilter
0x180001ae9  mov     rcx, rbx; ExceptionInfo
0x180001aec  call    cs:__imp_UnhandledExceptionFilter
0x180001af2  call    cs:__imp_GetCurrentProcess
0x180001af8  mov     rcx, rax
0x180001afb  mov     edx, 0C0000409h
0x180001b00  add     rsp, 20h
0x180001b04  pop     rbx
0x180001b05  jmp     cs:__imp_TerminateProcess
```
