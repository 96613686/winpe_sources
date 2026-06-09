# __scrt_fastfail

- ea: `0x140001d74`
- end: `0x140001ee0`
- name: `__scrt_fastfail`
- size: `364`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001530`
- `0x140001620`
- `0x1400019f4`

## callees

- `0x140001d60`
- `0x140001d74`
- `0x140005a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001eb8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001eb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001ead`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001ead`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140001dbd`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x140001dbd`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x140001e3c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x140001e3c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x140001de2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x140001de2`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x140001d90`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x140001d90`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140001e90`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140001e90`

## pseudocode

```c
LONG __fastcall _scrt_fastfail(unsigned int a1)
{
  ULONG64 Rip; // rbx
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v3; // rax
  BOOL v4; // ebx
  LONG result; // eax
  _EXCEPTION_POINTERS ExceptionInfo; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v7[20]; // [rsp+50h] [rbp-B0h] BYREF
  struct _CONTEXT ContextRecord; // [rsp+F0h] [rbp-10h] BYREF
  DWORD64 retaddr; // [rsp+5C8h] [rbp+4C8h]
  __int64 v10; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int64 ImageBase; // [rsp+5D8h] [rbp+4D8h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+5E0h] [rbp+4E0h] BYREF
  PVOID HandlerData; // [rsp+5E8h] [rbp+4E8h] BYREF

  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(a1);
  _crt_debugger_hook(3);
  memset(&ContextRecord, 0, sizeof(ContextRecord));
  RtlCaptureContext(&ContextRecord);
  Rip = ContextRecord.Rip;
  ImageBase = 0;
  v3 = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( v3 )
  {
    EstablisherFrame = 0;
    HandlerData = 0;
    RtlVirtualUnwind(0, ImageBase, Rip, v3, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v10;
  memset(v7, 0, 0x98u);
  v7[2] = retaddr;
  v7[0] = 0x140000015LL;
  v4 = IsDebuggerPresent();
  ExceptionInfo.ExceptionRecord = (PEXCEPTION_RECORD)v7;
  ExceptionInfo.ContextRecord = &ContextRecord;
  SetUnhandledExceptionFilter(0);
  result = UnhandledExceptionFilter(&ExceptionInfo);
  if ( !result && !v4 )
    return _crt_debugger_hook(3);
  return result;
}

```

## disassembly

```asm
0x140001d74  mov     [rsp-8+arg_0], rbx
0x140001d79  push    rbp
0x140001d7a  lea     rbp, [rsp-4C0h]
0x140001d82  sub     rsp, 5C0h
0x140001d89  mov     ebx, ecx
0x140001d8b  mov     ecx, 17h; ProcessorFeature
0x140001d90  call    cs:__imp_IsProcessorFeaturePresent
0x140001d96  test    eax, eax
0x140001d98  jz      short loc_140001D9E
0x140001d9a  mov     ecx, ebx
0x140001d9c  int     29h; Win8: RtlFailFast(ecx)
0x140001d9e  mov     ecx, 3
0x140001da3  call    __crt_debugger_hook
0x140001da8  xor     edx, edx; Val
0x140001daa  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x140001dae  mov     r8d, 4D0h; Size
0x140001db4  call    memset
0x140001db9  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x140001dbd  call    cs:__imp_RtlCaptureContext
0x140001dc3  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x140001dca  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x140001dd1  mov     rcx, rbx; ControlPc
0x140001dd4  mov     [rbp+4C0h+ImageBase], 0
0x140001ddf  xor     r8d, r8d; HistoryTable
0x140001de2  call    cs:__imp_RtlLookupFunctionEntry
0x140001de8  test    rax, rax
0x140001deb  jz      short loc_140001E42
0x140001ded  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x140001df4  lea     rcx, [rbp+4C0h+arg_10]
0x140001dfb  mov     [rsp+5C0h+ContextPointers], 0; ContextPointers
0x140001e04  mov     r9, rax; FunctionEntry
0x140001e07  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x140001e0c  mov     r8, rbx; ControlPc
0x140001e0f  lea     rcx, [rbp+4C0h+arg_18]
0x140001e16  mov     [rbp+4C0h+arg_10], 0
0x140001e21  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x140001e26  lea     rcx, [rbp+4C0h+ContextRecord]
0x140001e2a  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x140001e2f  xor     ecx, ecx; HandlerType
0x140001e31  mov     [rbp+4C0h+arg_18], 0
0x140001e3c  call    cs:__imp_RtlVirtualUnwind
0x140001e42  mov     rax, [rbp+4C8h]
0x140001e49  lea     rcx, [rsp+5C0h+var_570]; void *
0x140001e4e  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x140001e55  xor     edx, edx; Val
0x140001e57  lea     rax, [rbp+4C8h]
0x140001e5e  mov     r8d, 98h; Size
0x140001e64  add     rax, 8
0x140001e68  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x140001e6f  call    memset
0x140001e74  mov     rax, [rbp+4C8h]
0x140001e7b  mov     [rsp+5C0h+var_560], rax
0x140001e80  mov     [rsp+5C0h+var_570], 40000015h
0x140001e88  mov     [rsp+5C0h+var_56C], 1
0x140001e90  call    cs:__imp_IsDebuggerPresent
0x140001e96  mov     ebx, eax
0x140001e98  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001e9a  lea     rax, [rsp+5C0h+var_570]
0x140001e9f  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x140001ea4  lea     rax, [rbp+4C0h+ContextRecord]
0x140001ea8  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x140001ead  call    cs:__imp_SetUnhandledExceptionFilter
0x140001eb3  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x140001eb8  call    cs:__imp_UnhandledExceptionFilter
0x140001ebe  test    eax, eax
0x140001ec0  jnz     short loc_140001ECF
0x140001ec2  cmp     ebx, 1
0x140001ec5  jz      short loc_140001ECF
0x140001ec7  lea     ecx, [rax+3]
0x140001eca  call    __crt_debugger_hook
0x140001ecf  mov     rbx, [rsp+5C0h+arg_0]
0x140001ed7  add     rsp, 5C0h
0x140001ede  pop     rbp
0x140001edf  retn
```
