# __raise_securityfailure

- ea: `0x180001ee0`
- end: `0x180001f14`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f20`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180001efa`
- `KERNEL32!GetCurrentProcess` at `0x180001efa`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001ef4`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001ef4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001eeb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001eeb`
- `KERNEL32!TerminateProcess` at `0x180001f0d`

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
0x180001ee0  push    rbx
0x180001ee2  sub     rsp, 20h
0x180001ee6  mov     rbx, rcx
0x180001ee9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001eeb  call    cs:__imp_SetUnhandledExceptionFilter
0x180001ef1  mov     rcx, rbx; ExceptionInfo
0x180001ef4  call    cs:__imp_UnhandledExceptionFilter
0x180001efa  call    cs:__imp_GetCurrentProcess
0x180001f00  mov     rcx, rax
0x180001f03  mov     edx, 0C0000409h
0x180001f08  add     rsp, 20h
0x180001f0c  pop     rbx
0x180001f0d  jmp     cs:__imp_TerminateProcess
```
