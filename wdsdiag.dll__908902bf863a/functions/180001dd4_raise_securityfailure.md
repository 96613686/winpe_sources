# __raise_securityfailure

- ea: `0x180001dd4`
- end: `0x180001e08`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001e10`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001e01`
- `KERNEL32!GetCurrentProcess` at `0x180001dee`
- `KERNEL32!GetCurrentProcess` at `0x180001dee`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001ddf`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001ddf`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001de8`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001de8`

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
0x180001dd4  push    rbx
0x180001dd6  sub     rsp, 20h
0x180001dda  mov     rbx, rcx
0x180001ddd  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001ddf  call    cs:__imp_SetUnhandledExceptionFilter
0x180001de5  mov     rcx, rbx; ExceptionInfo
0x180001de8  call    cs:__imp_UnhandledExceptionFilter
0x180001dee  call    cs:__imp_GetCurrentProcess
0x180001df4  mov     rcx, rax
0x180001df7  mov     edx, 0C0000409h
0x180001dfc  add     rsp, 20h
0x180001e00  pop     rbx
0x180001e01  jmp     cs:__imp_TerminateProcess
```
