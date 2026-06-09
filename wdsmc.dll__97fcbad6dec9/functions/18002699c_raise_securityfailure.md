# __raise_securityfailure

- ea: `0x18002699c`
- end: `0x1800269d0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800269e0`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x1800269b0`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800269b0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800269a7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800269a7`
- `KERNEL32!GetCurrentProcess` at `0x1800269b6`
- `KERNEL32!GetCurrentProcess` at `0x1800269b6`
- `KERNEL32!TerminateProcess` at `0x1800269c9`

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
0x18002699c  push    rbx
0x18002699e  sub     rsp, 20h
0x1800269a2  mov     rbx, rcx
0x1800269a5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800269a7  call    cs:__imp_SetUnhandledExceptionFilter
0x1800269ad  mov     rcx, rbx; ExceptionInfo
0x1800269b0  call    cs:__imp_UnhandledExceptionFilter
0x1800269b6  call    cs:__imp_GetCurrentProcess
0x1800269bc  mov     rcx, rax
0x1800269bf  mov     edx, 0C0000409h
0x1800269c4  add     rsp, 20h
0x1800269c8  pop     rbx
0x1800269c9  jmp     cs:__imp_TerminateProcess
```
