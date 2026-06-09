# __raise_securityfailure

- ea: `0x18000187c`
- end: `0x1800018b0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800018c0`
- `0x180001a68`

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001887`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001887`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001890`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001890`
- `KERNEL32!TerminateProcess` at `0x1800018a9`
- `KERNEL32!GetCurrentProcess` at `0x180001896`
- `KERNEL32!GetCurrentProcess` at `0x180001896`

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
0x18000187c  push    rbx
0x18000187e  sub     rsp, 20h
0x180001882  mov     rbx, rcx
0x180001885  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001887  call    cs:__imp_SetUnhandledExceptionFilter
0x18000188d  mov     rcx, rbx; ExceptionInfo
0x180001890  call    cs:__imp_UnhandledExceptionFilter
0x180001896  call    cs:__imp_GetCurrentProcess
0x18000189c  mov     rcx, rax
0x18000189f  mov     edx, 0C0000409h
0x1800018a4  add     rsp, 20h
0x1800018a8  pop     rbx
0x1800018a9  jmp     cs:__imp_TerminateProcess
```
