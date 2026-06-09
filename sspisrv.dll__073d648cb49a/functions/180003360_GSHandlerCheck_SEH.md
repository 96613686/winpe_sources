# __GSHandlerCheck_SEH

- ea: `0x180003360`
- end: `0x1800033c8`
- name: `__GSHandlerCheck_SEH`
- size: `104`
- prototype: `__int64 __fastcall(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800032f4`
- `0x180003360`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!__C_specific_handler` at `0x1800033b7`
- `api-ms-win-core-crt-l1-1-0!__C_specific_handler` at `0x1800033b7`

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
  _GSHandlerCheckCommon((__int64)EstablisherFrame, (__int64)DispatcherContext);
  result = ExceptionContinueSearch;
  if ( ((((ExceptionRecord->ExceptionFlags & 0x66) != 0) + 1) & *((_DWORD *)v8 + 1)) != 0 )
    return __C_specific_handler(ExceptionRecord, EstablisherFrame, ContextRecord, DispatcherContext);
  return result;
}

```

## disassembly

```asm
0x180003360  push    rbx
0x180003362  push    rbp
0x180003363  push    rsi
0x180003364  push    rdi
0x180003365  push    r14
0x180003367  sub     rsp, 20h
0x18000336b  mov     r10, [r9+38h]
0x18000336f  mov     rsi, rdx
0x180003372  mov     r14, r8
0x180003375  mov     rbp, rcx
0x180003378  mov     rdx, r9
0x18000337b  mov     rcx, rsi
0x18000337e  mov     rdi, r9
0x180003381  mov     ebx, [r10]
0x180003384  shl     rbx, 4
0x180003388  add     rbx, r10
0x18000338b  lea     r8, [rbx+4]
0x18000338f  call    __GSHandlerCheckCommon
0x180003394  mov     eax, [rbp+4]
0x180003397  and     al, 66h
0x180003399  neg     al
0x18000339b  mov     eax, 1
0x1800033a0  sbb     edx, edx
0x1800033a2  neg     edx
0x1800033a4  add     edx, eax
0x1800033a6  test    [rbx+4], edx
0x1800033a9  jz      short loc_1800033BD
0x1800033ab  mov     r9, rdi; DispatcherContext
0x1800033ae  mov     r8, r14; ContextRecord
0x1800033b1  mov     rdx, rsi; EstablisherFrame
0x1800033b4  mov     rcx, rbp; ExceptionRecord
0x1800033b7  call    cs:__imp___C_specific_handler
0x1800033bd  add     rsp, 20h
0x1800033c1  pop     r14
0x1800033c3  pop     rdi
0x1800033c4  pop     rsi
0x1800033c5  pop     rbp
0x1800033c6  pop     rbx
0x1800033c7  retn
```
