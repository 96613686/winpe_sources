# __raise_securityfailure

- ea: `0x1800018a8`
- end: `0x1800018dc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800018f0`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x1800018bc`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800018bc`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800018b3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800018b3`
- `KERNEL32!GetCurrentProcess` at `0x1800018c2`
- `KERNEL32!GetCurrentProcess` at `0x1800018c2`
- `KERNEL32!TerminateProcess` at `0x1800018d5`

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
0x1800018a8  push    rbx
0x1800018aa  sub     rsp, 20h
0x1800018ae  mov     rbx, rcx
0x1800018b1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800018b3  call    cs:__imp_SetUnhandledExceptionFilter
0x1800018b9  mov     rcx, rbx; ExceptionInfo
0x1800018bc  call    cs:__imp_UnhandledExceptionFilter
0x1800018c2  call    cs:__imp_GetCurrentProcess
0x1800018c8  mov     rcx, rax
0x1800018cb  mov     edx, 0C0000409h
0x1800018d0  add     rsp, 20h
0x1800018d4  pop     rbx
0x1800018d5  jmp     cs:__imp_TerminateProcess
```
