# __raise_securityfailure

- ea: `0x180006604`
- end: `0x180006638`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006640`
- `0x1800067e8`

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000660f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000660f`
- `KERNEL32!UnhandledExceptionFilter` at `0x180006618`
- `KERNEL32!UnhandledExceptionFilter` at `0x180006618`
- `KERNEL32!TerminateProcess` at `0x180006631`
- `KERNEL32!GetCurrentProcess` at `0x18000661e`
- `KERNEL32!GetCurrentProcess` at `0x18000661e`

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
0x180006604  push    rbx
0x180006606  sub     rsp, 20h
0x18000660a  mov     rbx, rcx
0x18000660d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000660f  call    cs:__imp_SetUnhandledExceptionFilter
0x180006615  mov     rcx, rbx; ExceptionInfo
0x180006618  call    cs:__imp_UnhandledExceptionFilter
0x18000661e  call    cs:__imp_GetCurrentProcess
0x180006624  mov     rcx, rax
0x180006627  mov     edx, 0C0000409h
0x18000662c  add     rsp, 20h
0x180006630  pop     rbx
0x180006631  jmp     cs:__imp_TerminateProcess
```
