# __scrt_fastfail

- ea: `0x180001e58`
- end: `0x180001fc4`
- name: `__scrt_fastfail`
- size: `364`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001278`
- `0x180001390`
- `0x180001b38`

## callees

- `0x180001e44`
- `0x180001e58`
- `0x180002658`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180001f74`
- `KERNEL32!IsDebuggerPresent` at `0x180001f74`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180001e74`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180001e74`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001f91`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001f91`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001f9c`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001f9c`
- `KERNEL32!RtlVirtualUnwind` at `0x180001f20`
- `KERNEL32!RtlVirtualUnwind` at `0x180001f20`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001ec6`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001ec6`
- `KERNEL32!RtlCaptureContext` at `0x180001ea1`
- `KERNEL32!RtlCaptureContext` at `0x180001ea1`

## pseudocode

```c
LONG __fastcall _scrt_fastfail(unsigned int a1)
{
  ULONG64 Rip; // rbx
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v3; // rax
  BOOL v4; // ebx
  LONG result; // eax
  _EXCEPTION_POINTERS ExceptionInfo; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v7[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD64 v8; // [rsp+60h] [rbp-A0h]
  struct _CONTEXT ContextRecord; // [rsp+F0h] [rbp-10h] BYREF
  DWORD64 retaddr; // [rsp+5C8h] [rbp+4C8h]
  __int64 v11; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int64 ImageBase; // [rsp+5D8h] [rbp+4D8h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+5E0h] [rbp+4E0h] BYREF
  PVOID HandlerData; // [rsp+5E8h] [rbp+4E8h] BYREF

  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(a1);
  _crt_debugger_hook(3);
  memset_0(&ContextRecord, 0, sizeof(ContextRecord));
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
  ContextRecord.Rsp = (DWORD64)&v11;
  memset_0(v7, 0, 0x98u);
  v8 = retaddr;
  v7[0] = 1073741845;
  v7[1] = 1;
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
0x180001e58  mov     [rsp-8+arg_0], rbx
0x180001e5d  push    rbp
0x180001e5e  lea     rbp, [rsp-4C0h]
0x180001e66  sub     rsp, 5C0h
0x180001e6d  mov     ebx, ecx
0x180001e6f  mov     ecx, 17h; ProcessorFeature
0x180001e74  call    cs:__imp_IsProcessorFeaturePresent
0x180001e7a  test    eax, eax
0x180001e7c  jz      short loc_180001E82
0x180001e7e  mov     ecx, ebx
0x180001e80  int     29h; Win8: RtlFailFast(ecx)
0x180001e82  mov     ecx, 3
0x180001e87  call    __crt_debugger_hook
0x180001e8c  xor     edx, edx; Val
0x180001e8e  lea     rcx, [rbp+4C0h+ContextRecord]; void *
0x180001e92  mov     r8d, 4D0h; Size
0x180001e98  call    memset_0
0x180001e9d  lea     rcx, [rbp+4C0h+ContextRecord]; ContextRecord
0x180001ea1  call    cs:__imp_RtlCaptureContext
0x180001ea7  mov     rbx, [rbp+4C0h+ContextRecord.Rip]
0x180001eae  lea     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x180001eb5  mov     rcx, rbx; ControlPc
0x180001eb8  mov     [rbp+4C0h+ImageBase], 0
0x180001ec3  xor     r8d, r8d; HistoryTable
0x180001ec6  call    cs:__imp_RtlLookupFunctionEntry
0x180001ecc  test    rax, rax
0x180001ecf  jz      short loc_180001F26
0x180001ed1  mov     rdx, [rbp+4C0h+ImageBase]; ImageBase
0x180001ed8  lea     rcx, [rbp+4C0h+arg_10]
0x180001edf  mov     [rsp+5C0h+ContextPointers], 0; ContextPointers
0x180001ee8  mov     r9, rax; FunctionEntry
0x180001eeb  mov     [rsp+5C0h+EstablisherFrame], rcx; EstablisherFrame
0x180001ef0  mov     r8, rbx; ControlPc
0x180001ef3  lea     rcx, [rbp+4C0h+arg_18]
0x180001efa  mov     [rbp+4C0h+arg_10], 0
0x180001f05  mov     [rsp+5C0h+HandlerData], rcx; HandlerData
0x180001f0a  lea     rcx, [rbp+4C0h+ContextRecord]
0x180001f0e  mov     [rsp+5C0h+var_5A0], rcx; ContextRecord
0x180001f13  xor     ecx, ecx; HandlerType
0x180001f15  mov     [rbp+4C0h+arg_18], 0
0x180001f20  call    cs:__imp_RtlVirtualUnwind
0x180001f26  mov     rax, [rbp+4C8h]
0x180001f2d  lea     rcx, [rsp+5C0h+var_570]; void *
0x180001f32  mov     [rbp+4C0h+ContextRecord.Rip], rax
0x180001f39  xor     edx, edx; Val
0x180001f3b  lea     rax, [rbp+4C8h]
0x180001f42  mov     r8d, 98h; Size
0x180001f48  add     rax, 8
0x180001f4c  mov     [rbp+4C0h+ContextRecord.Rsp], rax
0x180001f53  call    memset_0
0x180001f58  mov     rax, [rbp+4C8h]
0x180001f5f  mov     [rsp+5C0h+var_560], rax
0x180001f64  mov     [rsp+5C0h+var_570], 40000015h
0x180001f6c  mov     [rsp+5C0h+var_56C], 1
0x180001f74  call    cs:__imp_IsDebuggerPresent
0x180001f7a  mov     ebx, eax
0x180001f7c  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001f7e  lea     rax, [rsp+5C0h+var_570]
0x180001f83  mov     [rsp+5C0h+ExceptionInfo.ExceptionRecord], rax
0x180001f88  lea     rax, [rbp+4C0h+ContextRecord]
0x180001f8c  mov     [rsp+5C0h+ExceptionInfo.ContextRecord], rax
0x180001f91  call    cs:__imp_SetUnhandledExceptionFilter
0x180001f97  lea     rcx, [rsp+5C0h+ExceptionInfo]; ExceptionInfo
0x180001f9c  call    cs:__imp_UnhandledExceptionFilter
0x180001fa2  test    eax, eax
0x180001fa4  jnz     short loc_180001FB3
0x180001fa6  cmp     ebx, 1
0x180001fa9  jz      short loc_180001FB3
0x180001fab  lea     ecx, [rax+3]
0x180001fae  call    __crt_debugger_hook
0x180001fb3  mov     rbx, [rsp+5C0h+arg_0]
0x180001fbb  add     rsp, 5C0h
0x180001fc2  pop     rbp
0x180001fc3  retn
```
