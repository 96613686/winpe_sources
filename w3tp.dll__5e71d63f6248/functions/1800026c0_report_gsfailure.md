# __report_gsfailure

- ea: `0x1800026c0`
- end: `0x180002860`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800041d0`

## callees

- `0x180002680`
- `0x1800026c0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180002700`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180002700`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000271f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000271f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000276c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000276c`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
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
  qword_1800090E0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800090D0 = -1073740791;
  dword_1800090D4 = 1;
  dword_1800090E8 = 3;
  qword_1800090F0[0] = 2;
  qword_1800090F0[1] = _security_cookie;
  qword_1800090F0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800026c0  mov     [rsp+arg_0], rcx
0x1800026c5  sub     rsp, 88h
0x1800026cc  mov     [rsp+88h+ControlPc], 0
0x1800026d5  mov     [rsp+88h+var_30], 0
0x1800026de  mov     [rsp+88h+FunctionEntry], 0
0x1800026e7  mov     [rsp+88h+var_28], 0
0x1800026f0  mov     [rsp+88h+ImageBase], 0
0x1800026f9  lea     rcx, ContextRecord; ContextRecord
0x180002700  call    cs:__imp_RtlCaptureContext
0x180002706  mov     rax, cs:ContextRecord.Rip
0x18000270d  mov     [rsp+88h+ControlPc], rax
0x180002712  xor     r8d, r8d; HistoryTable
0x180002715  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000271a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000271f  call    cs:__imp_RtlLookupFunctionEntry
0x180002725  mov     [rsp+88h+FunctionEntry], rax
0x18000272a  cmp     [rsp+88h+FunctionEntry], 0
0x180002730  jz      short loc_180002775
0x180002732  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000273b  lea     rax, [rsp+88h+var_30]
0x180002740  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180002745  lea     rax, [rsp+88h+var_28]
0x18000274a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000274f  lea     rax, ContextRecord
0x180002756  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000275b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180002760  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180002765  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000276a  xor     ecx, ecx; HandlerType
0x18000276c  call    cs:__imp_RtlVirtualUnwind
0x180002772  nop
0x180002773  jmp     short loc_180002798
0x180002775  mov     rax, cs:ContextRecord.Rsp
0x18000277c  mov     rax, [rax]
0x18000277f  mov     cs:ContextRecord.Rip, rax
0x180002786  mov     rax, cs:ContextRecord.Rsp
0x18000278d  add     rax, 8
0x180002791  mov     cs:ContextRecord.Rsp, rax
0x180002798  mov     rax, cs:ContextRecord.Rip
0x18000279f  mov     cs:qword_1800090E0, rax
0x1800027a6  mov     rax, [rsp+88h+arg_0]
0x1800027ae  mov     cs:ContextRecord.Rcx, rax
0x1800027b5  mov     cs:dword_1800090D0, 0C0000409h
0x1800027bf  mov     cs:dword_1800090D4, 1
0x1800027c9  mov     cs:dword_1800090E8, 3
0x1800027d3  mov     eax, 8
0x1800027d8  imul    rax, 0
0x1800027dc  lea     rcx, qword_1800090F0
0x1800027e3  mov     qword ptr [rcx+rax], 2
0x1800027eb  mov     eax, 8
0x1800027f0  imul    rax, 1
0x1800027f4  lea     rcx, qword_1800090F0
0x1800027fb  mov     rdx, cs:__security_cookie
0x180002802  mov     [rcx+rax], rdx
0x180002806  mov     eax, 8
0x18000280b  imul    rax, 2
0x18000280f  lea     rcx, qword_1800090F0
0x180002816  mov     rdx, cs:__security_cookie_complement
0x18000281d  mov     [rcx+rax], rdx
0x180002821  mov     eax, 8
0x180002826  imul    rax, 0
0x18000282a  mov     rcx, cs:__security_cookie
0x180002831  mov     [rsp+rax+88h+var_20], rcx
0x180002836  mov     eax, 8
0x18000283b  imul    rax, 1
0x18000283f  mov     rcx, cs:__security_cookie_complement
0x180002846  mov     [rsp+rax+88h+var_20], rcx
0x18000284b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002852  call    __raise_securityfailure
0x180002857  nop
0x180002858  add     rsp, 88h
0x18000285f  retn
```
