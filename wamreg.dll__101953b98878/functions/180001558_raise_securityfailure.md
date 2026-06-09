# __raise_securityfailure

- ea: `0x180001558`
- end: `0x18000158c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800015a0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001585`
- `KERNEL32!GetCurrentProcess` at `0x180001572`
- `KERNEL32!GetCurrentProcess` at `0x180001572`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000156c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000156c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001563`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001563`

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
0x180001558  push    rbx
0x18000155a  sub     rsp, 20h
0x18000155e  mov     rbx, rcx
0x180001561  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001563  call    cs:__imp_SetUnhandledExceptionFilter
0x180001569  mov     rcx, rbx; ExceptionInfo
0x18000156c  call    cs:__imp_UnhandledExceptionFilter
0x180001572  call    cs:__imp_GetCurrentProcess
0x180001578  mov     rcx, rax
0x18000157b  mov     edx, 0C0000409h
0x180001580  add     rsp, 20h
0x180001584  pop     rbx
0x180001585  jmp     cs:__imp_TerminateProcess
```
