# __raise_securityfailure

- ea: `0x14000114c`
- end: `0x140001180`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001190`
- `0x140001338`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x140001160`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001160`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001157`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001157`
- `KERNEL32!GetCurrentProcess` at `0x140001166`
- `KERNEL32!GetCurrentProcess` at `0x140001166`
- `KERNEL32!TerminateProcess` at `0x140001179`

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
0x14000114c  push    rbx
0x14000114e  sub     rsp, 20h
0x140001152  mov     rbx, rcx
0x140001155  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001157  call    cs:__imp_SetUnhandledExceptionFilter
0x14000115d  mov     rcx, rbx; ExceptionInfo
0x140001160  call    cs:__imp_UnhandledExceptionFilter
0x140001166  call    cs:__imp_GetCurrentProcess
0x14000116c  mov     rcx, rax
0x14000116f  mov     edx, 0C0000409h
0x140001174  add     rsp, 20h
0x140001178  pop     rbx
0x140001179  jmp     cs:__imp_TerminateProcess
```
