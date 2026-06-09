# __GSHandlerCheck_SEH

- ea: `0x18000468c`
- end: `0x1800046f4`
- name: `__GSHandlerCheck_SEH`
- size: `104`
- prototype: `EXCEPTION_DISPOSITION __fastcall(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004620`
- `0x18000468c`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!__C_specific_handler` at `0x1800046e3`
- `api-ms-win-core-crt-l1-1-0!__C_specific_handler` at `0x1800046e3`

## pseudocode

```c
EXCEPTION_DISPOSITION __fastcall _GSHandlerCheck_SEH(
        struct _EXCEPTION_RECORD *ExceptionRecord,
        void *EstablisherFrame,
        struct _CONTEXT *ContextRecord,
        struct _DISPATCHER_CONTEXT *DispatcherContext)
{
  char *v8; // rbx
  EXCEPTION_DISPOSITION result; // eax

  v8 = (char *)DispatcherContext->HandlerData + 16 * *(unsigned int *)DispatcherContext->HandlerData;
  _GSHandlerCheckCommon(EstablisherFrame, DispatcherContext, v8 + 4);
  result = ExceptionContinueSearch;
  if ( ((((ExceptionRecord->ExceptionFlags & 0x66) != 0) + 1) & *((_DWORD *)v8 + 1)) != 0 )
    return __C_specific_handler(ExceptionRecord, EstablisherFrame, ContextRecord, DispatcherContext);
  return result;
}

```

## disassembly

```asm
0x18000468c  push    rbx
0x18000468e  push    rbp
0x18000468f  push    rsi
0x180004690  push    rdi
0x180004691  push    r14
0x180004693  sub     rsp, 20h
0x180004697  mov     r10, [r9+38h]
0x18000469b  mov     rsi, rdx
0x18000469e  mov     r14, r8
0x1800046a1  mov     rbp, rcx
0x1800046a4  mov     rdx, r9
0x1800046a7  mov     rcx, rsi
0x1800046aa  mov     rdi, r9
0x1800046ad  mov     ebx, [r10]
0x1800046b0  shl     rbx, 4
0x1800046b4  add     rbx, r10
0x1800046b7  lea     r8, [rbx+4]
0x1800046bb  call    __GSHandlerCheckCommon
0x1800046c0  mov     eax, [rbp+4]
0x1800046c3  and     al, 66h
0x1800046c5  neg     al
0x1800046c7  mov     eax, 1
0x1800046cc  sbb     edx, edx
0x1800046ce  neg     edx
0x1800046d0  add     edx, eax
0x1800046d2  test    [rbx+4], edx
0x1800046d5  jz      short loc_1800046E9
0x1800046d7  mov     r9, rdi; DispatcherContext
0x1800046da  mov     r8, r14; ContextRecord
0x1800046dd  mov     rdx, rsi; EstablisherFrame
0x1800046e0  mov     rcx, rbp; ExceptionRecord
0x1800046e3  call    cs:__imp___C_specific_handler
0x1800046e9  add     rsp, 20h
0x1800046ed  pop     r14
0x1800046ef  pop     rdi
0x1800046f0  pop     rsi
0x1800046f1  pop     rbp
0x1800046f2  pop     rbx
0x1800046f3  retn
```
