# __report_gsfailure

- ea: `0x180001800`
- end: `0x1800019a0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800031b0`

## callees

- `0x1800017c0`
- `0x180001800`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001840`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001840`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000185f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000185f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800018ac`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800018ac`

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
0x180001800  mov     [rsp+arg_0], rcx
0x180001805  sub     rsp, 88h
0x18000180c  mov     [rsp+88h+ControlPc], 0
0x180001815  mov     [rsp+88h+var_30], 0
0x18000181e  mov     [rsp+88h+FunctionEntry], 0
0x180001827  mov     [rsp+88h+var_28], 0
0x180001830  mov     [rsp+88h+ImageBase], 0
0x180001839  lea     rcx, ContextRecord; ContextRecord
0x180001840  call    cs:__imp_RtlCaptureContext
0x180001846  mov     rax, cs:ContextRecord.Rip
0x18000184d  mov     [rsp+88h+ControlPc], rax
0x180001852  xor     r8d, r8d; HistoryTable
0x180001855  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000185a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000185f  call    cs:__imp_RtlLookupFunctionEntry
0x180001865  mov     [rsp+88h+FunctionEntry], rax
0x18000186a  cmp     [rsp+88h+FunctionEntry], 0
0x180001870  jz      short loc_1800018B5
0x180001872  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000187b  lea     rax, [rsp+88h+var_30]
0x180001880  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001885  lea     rax, [rsp+88h+var_28]
0x18000188a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000188f  lea     rax, ContextRecord
0x180001896  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000189b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800018a0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800018a5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800018aa  xor     ecx, ecx; HandlerType
0x1800018ac  call    cs:__imp_RtlVirtualUnwind
0x1800018b2  nop
0x1800018b3  jmp     short loc_1800018D8
0x1800018b5  mov     rax, cs:ContextRecord.Rsp
0x1800018bc  mov     rax, [rax]
0x1800018bf  mov     cs:ContextRecord.Rip, rax
0x1800018c6  mov     rax, cs:ContextRecord.Rsp
0x1800018cd  add     rax, 8
0x1800018d1  mov     cs:ContextRecord.Rsp, rax
0x1800018d8  mov     rax, cs:ContextRecord.Rip
0x1800018df  mov     cs:qword_1800070C0, rax
0x1800018e6  mov     rax, [rsp+88h+arg_0]
0x1800018ee  mov     cs:ContextRecord.Rcx, rax
0x1800018f5  mov     cs:dword_1800070B0, 0C0000409h
0x1800018ff  mov     cs:dword_1800070B4, 1
0x180001909  mov     cs:dword_1800070C8, 3
0x180001913  mov     eax, 8
0x180001918  imul    rax, 0
0x18000191c  lea     rcx, qword_1800070D0
0x180001923  mov     qword ptr [rcx+rax], 2
0x18000192b  mov     eax, 8
0x180001930  imul    rax, 1
0x180001934  lea     rcx, qword_1800070D0
0x18000193b  mov     rdx, cs:__security_cookie
0x180001942  mov     [rcx+rax], rdx
0x180001946  mov     eax, 8
0x18000194b  imul    rax, 2
0x18000194f  lea     rcx, qword_1800070D0
0x180001956  mov     rdx, cs:__security_cookie_complement
0x18000195d  mov     [rcx+rax], rdx
0x180001961  mov     eax, 8
0x180001966  imul    rax, 0
0x18000196a  mov     rcx, cs:__security_cookie
0x180001971  mov     [rsp+rax+88h+var_20], rcx
0x180001976  mov     eax, 8
0x18000197b  imul    rax, 1
0x18000197f  mov     rcx, cs:__security_cookie_complement
0x180001986  mov     [rsp+rax+88h+var_20], rcx
0x18000198b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001992  call    __raise_securityfailure
0x180001997  nop
0x180001998  add     rsp, 88h
0x18000199f  retn
```
