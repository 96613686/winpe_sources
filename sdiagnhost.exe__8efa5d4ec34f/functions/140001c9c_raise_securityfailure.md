# __raise_securityfailure

- ea: `0x140001c9c`
- end: `0x140001cd0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001ce0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x140001cc9`
- `KERNEL32!GetCurrentProcess` at `0x140001cb6`
- `KERNEL32!GetCurrentProcess` at `0x140001cb6`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001cb0`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001cb0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001ca7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001ca7`

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
0x140001c9c  push    rbx
0x140001c9e  sub     rsp, 20h
0x140001ca2  mov     rbx, rcx
0x140001ca5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001ca7  call    cs:__imp_SetUnhandledExceptionFilter
0x140001cad  mov     rcx, rbx; ExceptionInfo
0x140001cb0  call    cs:__imp_UnhandledExceptionFilter
0x140001cb6  call    cs:__imp_GetCurrentProcess
0x140001cbc  mov     rcx, rax
0x140001cbf  mov     edx, 0C0000409h
0x140001cc4  add     rsp, 20h
0x140001cc8  pop     rbx
0x140001cc9  jmp     cs:__imp_TerminateProcess
```
