# __raise_securityfailure

- ea: `0x180002520`
- end: `0x180002554`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002560`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18000254d`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002534`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002534`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000252b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000252b`
- `KERNEL32!GetCurrentProcess` at `0x18000253a`
- `KERNEL32!GetCurrentProcess` at `0x18000253a`

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
0x180002520  push    rbx
0x180002522  sub     rsp, 20h
0x180002526  mov     rbx, rcx
0x180002529  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000252b  call    cs:__imp_SetUnhandledExceptionFilter
0x180002531  mov     rcx, rbx; ExceptionInfo
0x180002534  call    cs:__imp_UnhandledExceptionFilter
0x18000253a  call    cs:__imp_GetCurrentProcess
0x180002540  mov     rcx, rax
0x180002543  mov     edx, 0C0000409h
0x180002548  add     rsp, 20h
0x18000254c  pop     rbx
0x18000254d  jmp     cs:__imp_TerminateProcess
```
