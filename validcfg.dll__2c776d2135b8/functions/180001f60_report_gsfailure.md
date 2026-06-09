# __report_gsfailure

- ea: `0x180001f60`
- end: `0x180002100`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003160`

## callees

- `0x180001f1c`
- `0x180001f60`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001fbf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001fbf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000200c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000200c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001fa0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001fa0`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF

  EstablisherFrame = 0;
  HandlerData[0] = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = *(_QWORD *)ContextRecord.Rsp;
    ContextRecord.Rsp += 8LL;
  }
  qword_1800070C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800070B0 = -1073740791;
  dword_1800070B4 = 1;
  dword_1800070C8 = 3;
  qword_1800070D0[0] = 2;
  qword_1800070D0[1] = _security_cookie;
  qword_1800070D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001f60  mov     [rsp+arg_0], rcx
0x180001f65  sub     rsp, 88h
0x180001f6c  mov     [rsp+88h+ControlPc], 0
0x180001f75  mov     [rsp+88h+var_30], 0
0x180001f7e  mov     [rsp+88h+FunctionEntry], 0
0x180001f87  mov     [rsp+88h+var_28], 0
0x180001f90  mov     [rsp+88h+ImageBase], 0
0x180001f99  lea     rcx, ContextRecord; ContextRecord
0x180001fa0  call    cs:__imp_RtlCaptureContext
0x180001fa6  mov     rax, cs:ContextRecord.Rip
0x180001fad  mov     [rsp+88h+ControlPc], rax
0x180001fb2  xor     r8d, r8d; HistoryTable
0x180001fb5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001fba  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180001fbf  call    cs:__imp_RtlLookupFunctionEntry
0x180001fc5  mov     [rsp+88h+FunctionEntry], rax
0x180001fca  cmp     [rsp+88h+FunctionEntry], 0
0x180001fd0  jz      short loc_180002015
0x180001fd2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180001fdb  lea     rax, [rsp+88h+var_30]
0x180001fe0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001fe5  lea     rax, [rsp+88h+var_28]
0x180001fea  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180001fef  lea     rax, ContextRecord
0x180001ff6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180001ffb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180002000  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180002005  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000200a  xor     ecx, ecx; HandlerType
0x18000200c  call    cs:__imp_RtlVirtualUnwind
0x180002012  nop
0x180002013  jmp     short loc_180002038
0x180002015  mov     rax, cs:ContextRecord.Rsp
0x18000201c  mov     rax, [rax]
0x18000201f  mov     cs:ContextRecord.Rip, rax
0x180002026  mov     rax, cs:ContextRecord.Rsp
0x18000202d  add     rax, 8
0x180002031  mov     cs:ContextRecord.Rsp, rax
0x180002038  mov     rax, cs:ContextRecord.Rip
0x18000203f  mov     cs:qword_1800070C0, rax
0x180002046  mov     rax, [rsp+88h+arg_0]
0x18000204e  mov     cs:ContextRecord.Rcx, rax
0x180002055  mov     cs:dword_1800070B0, 0C0000409h
0x18000205f  mov     cs:dword_1800070B4, 1
0x180002069  mov     cs:dword_1800070C8, 3
0x180002073  mov     eax, 8
0x180002078  imul    rax, 0
0x18000207c  lea     rcx, qword_1800070D0
0x180002083  mov     qword ptr [rcx+rax], 2
0x18000208b  mov     eax, 8
0x180002090  imul    rax, 1
0x180002094  lea     rcx, qword_1800070D0
0x18000209b  mov     rdx, cs:__security_cookie
0x1800020a2  mov     [rcx+rax], rdx
0x1800020a6  mov     eax, 8
0x1800020ab  imul    rax, 2
0x1800020af  lea     rcx, qword_1800070D0
0x1800020b6  mov     rdx, cs:__security_cookie_complement
0x1800020bd  mov     [rcx+rax], rdx
0x1800020c1  mov     eax, 8
0x1800020c6  imul    rax, 0
0x1800020ca  mov     rcx, cs:__security_cookie
0x1800020d1  mov     [rsp+rax+88h+var_20], rcx
0x1800020d6  mov     eax, 8
0x1800020db  imul    rax, 1
0x1800020df  mov     rcx, cs:__security_cookie_complement
0x1800020e6  mov     [rsp+rax+88h+var_20], rcx
0x1800020eb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800020f2  call    __raise_securityfailure
0x1800020f7  nop
0x1800020f8  add     rsp, 88h
0x1800020ff  retn
```
