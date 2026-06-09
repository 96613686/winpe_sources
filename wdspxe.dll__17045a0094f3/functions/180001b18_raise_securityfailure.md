# __raise_securityfailure

- ea: `0x180001b18`
- end: `0x180001b4c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b60`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001b45`
- `KERNEL32!GetCurrentProcess` at `0x180001b32`
- `KERNEL32!GetCurrentProcess` at `0x180001b32`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b23`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b23`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b2c`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b2c`

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
0x180001b18  push    rbx
0x180001b1a  sub     rsp, 20h
0x180001b1e  mov     rbx, rcx
0x180001b21  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001b23  call    cs:__imp_SetUnhandledExceptionFilter
0x180001b29  mov     rcx, rbx; ExceptionInfo
0x180001b2c  call    cs:__imp_UnhandledExceptionFilter
0x180001b32  call    cs:__imp_GetCurrentProcess
0x180001b38  mov     rcx, rax
0x180001b3b  mov     edx, 0C0000409h
0x180001b40  add     rsp, 20h
0x180001b44  pop     rbx
0x180001b45  jmp     cs:__imp_TerminateProcess
```
