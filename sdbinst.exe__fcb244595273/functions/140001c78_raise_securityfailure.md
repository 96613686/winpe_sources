# __raise_securityfailure

- ea: `0x140001c78`
- end: `0x140001cac`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001cc0`
- `0x140001e68`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x140001ca5`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001c83`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001c83`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001c8c`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001c8c`
- `KERNEL32!GetCurrentProcess` at `0x140001c92`
- `KERNEL32!GetCurrentProcess` at `0x140001c92`

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
0x140001c78  push    rbx
0x140001c7a  sub     rsp, 20h
0x140001c7e  mov     rbx, rcx
0x140001c81  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001c83  call    cs:__imp_SetUnhandledExceptionFilter
0x140001c89  mov     rcx, rbx; ExceptionInfo
0x140001c8c  call    cs:__imp_UnhandledExceptionFilter
0x140001c92  call    cs:__imp_GetCurrentProcess
0x140001c98  mov     rcx, rax
0x140001c9b  mov     edx, 0C0000409h
0x140001ca0  add     rsp, 20h
0x140001ca4  pop     rbx
0x140001ca5  jmp     cs:__imp_TerminateProcess
```
