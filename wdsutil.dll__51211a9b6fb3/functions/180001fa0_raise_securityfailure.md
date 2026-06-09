# __raise_securityfailure

- ea: `0x180001fa0`
- end: `0x180001fd4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001fe0`
- `0x180002188`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001fb4`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001fb4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001fab`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001fab`
- `KERNEL32!GetCurrentProcess` at `0x180001fba`
- `KERNEL32!GetCurrentProcess` at `0x180001fba`
- `KERNEL32!TerminateProcess` at `0x180001fcd`

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
0x180001fa0  push    rbx
0x180001fa2  sub     rsp, 20h
0x180001fa6  mov     rbx, rcx
0x180001fa9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001fab  call    cs:__imp_SetUnhandledExceptionFilter
0x180001fb1  mov     rcx, rbx; ExceptionInfo
0x180001fb4  call    cs:__imp_UnhandledExceptionFilter
0x180001fba  call    cs:__imp_GetCurrentProcess
0x180001fc0  mov     rcx, rax
0x180001fc3  mov     edx, 0C0000409h
0x180001fc8  add     rsp, 20h
0x180001fcc  pop     rbx
0x180001fcd  jmp     cs:__imp_TerminateProcess
```
