# __report_rangecheckfailure

- ea: `0x1800067e8`
- end: `0x18000690e`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005adc`
- `0x180009a9c`

## callees

- `0x180006604`
- `0x1800067e8`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x18000688c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000688c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000683f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000683f`
- `KERNEL32!RtlCaptureContext` at `0x180006820`
- `KERNEL32!RtlCaptureContext` at `0x180006820`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *FunctionEntry; // [rsp+40h] [rbp-38h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-30h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-20h] BYREF
  PVOID HandlerData; // [rsp+60h] [rbp-18h] BYREF

  EstablisherFrame = 0;
  HandlerData = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = *(_QWORD *)ContextRecord.Rsp;
    ContextRecord.Rsp += 8LL;
  }
  qword_180018640 = ContextRecord.Rip;
  dword_180018630 = -1073740791;
  dword_180018634 = 1;
  dword_180018648 = 1;
  qword_180018650[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800067e8  sub     rsp, 78h
0x1800067ec  mov     [rsp+78h+ControlPc], 0
0x1800067f5  mov     [rsp+78h+var_20], 0
0x1800067fe  mov     [rsp+78h+FunctionEntry], 0
0x180006807  mov     [rsp+78h+var_18], 0
0x180006810  mov     [rsp+78h+ImageBase], 0
0x180006819  lea     rcx, ContextRecord; ContextRecord
0x180006820  call    cs:__imp_RtlCaptureContext
0x180006826  mov     rax, cs:ContextRecord.Rip
0x18000682d  mov     [rsp+78h+ControlPc], rax
0x180006832  xor     r8d, r8d; HistoryTable
0x180006835  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000683a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x18000683f  call    cs:__imp_RtlLookupFunctionEntry
0x180006845  mov     [rsp+78h+FunctionEntry], rax
0x18000684a  cmp     [rsp+78h+FunctionEntry], 0
0x180006850  jz      short loc_180006895
0x180006852  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x18000685b  lea     rax, [rsp+78h+var_20]
0x180006860  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180006865  lea     rax, [rsp+78h+var_18]
0x18000686a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000686f  lea     rax, ContextRecord
0x180006876  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000687b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180006880  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180006885  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000688a  xor     ecx, ecx; HandlerType
0x18000688c  call    cs:__imp_RtlVirtualUnwind
0x180006892  nop
0x180006893  jmp     short loc_1800068B8
0x180006895  mov     rax, cs:ContextRecord.Rsp
0x18000689c  mov     rax, [rax]
0x18000689f  mov     cs:ContextRecord.Rip, rax
0x1800068a6  mov     rax, cs:ContextRecord.Rsp
0x1800068ad  add     rax, 8
0x1800068b1  mov     cs:ContextRecord.Rsp, rax
0x1800068b8  mov     rax, cs:ContextRecord.Rip
0x1800068bf  mov     cs:qword_180018640, rax
0x1800068c6  mov     cs:dword_180018630, 0C0000409h
0x1800068d0  mov     cs:dword_180018634, 1
0x1800068da  mov     cs:dword_180018648, 1
0x1800068e4  mov     eax, 8
0x1800068e9  imul    rax, 0
0x1800068ed  lea     rcx, qword_180018650
0x1800068f4  mov     qword ptr [rcx+rax], 8
0x1800068fc  lea     rcx, ExceptionInfo; ExceptionInfo
0x180006903  call    __raise_securityfailure
0x180006908  nop
0x180006909  add     rsp, 78h
0x18000690d  retn
```
