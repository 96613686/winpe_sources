# __report_gsfailure

- ea: `0x180001a00`
- end: `0x180001ba0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002950`

## callees

- `0x1800019bc`
- `0x180001a00`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180001aac`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180001aac`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001a40`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001a40`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001a5f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001a5f`

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
  qword_180006260 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_180006250 = -1073740791;
  dword_180006254 = 1;
  dword_180006268 = 3;
  qword_180006270[0] = 2;
  qword_180006270[1] = _security_cookie;
  qword_180006270[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001a00  mov     [rsp+arg_0], rcx
0x180001a05  sub     rsp, 88h
0x180001a0c  mov     [rsp+88h+ControlPc], 0
0x180001a15  mov     [rsp+88h+var_30], 0
0x180001a1e  mov     [rsp+88h+FunctionEntry], 0
0x180001a27  mov     [rsp+88h+var_28], 0
0x180001a30  mov     [rsp+88h+ImageBase], 0
0x180001a39  lea     rcx, ContextRecord; ContextRecord
0x180001a40  call    cs:__imp_RtlCaptureContext
0x180001a46  mov     rax, cs:ContextRecord.Rip
0x180001a4d  mov     [rsp+88h+ControlPc], rax
0x180001a52  xor     r8d, r8d; HistoryTable
0x180001a55  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001a5a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180001a5f  call    cs:__imp_RtlLookupFunctionEntry
0x180001a65  mov     [rsp+88h+FunctionEntry], rax
0x180001a6a  cmp     [rsp+88h+FunctionEntry], 0
0x180001a70  jz      short loc_180001AB5
0x180001a72  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180001a7b  lea     rax, [rsp+88h+var_30]
0x180001a80  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001a85  lea     rax, [rsp+88h+var_28]
0x180001a8a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180001a8f  lea     rax, ContextRecord
0x180001a96  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180001a9b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001aa0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001aa5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001aaa  xor     ecx, ecx; HandlerType
0x180001aac  call    cs:__imp_RtlVirtualUnwind
0x180001ab2  nop
0x180001ab3  jmp     short loc_180001AD8
0x180001ab5  mov     rax, cs:ContextRecord.Rsp
0x180001abc  mov     rax, [rax]
0x180001abf  mov     cs:ContextRecord.Rip, rax
0x180001ac6  mov     rax, cs:ContextRecord.Rsp
0x180001acd  add     rax, 8
0x180001ad1  mov     cs:ContextRecord.Rsp, rax
0x180001ad8  mov     rax, cs:ContextRecord.Rip
0x180001adf  mov     cs:qword_180006260, rax
0x180001ae6  mov     rax, [rsp+88h+arg_0]
0x180001aee  mov     cs:ContextRecord.Rcx, rax
0x180001af5  mov     cs:dword_180006250, 0C0000409h
0x180001aff  mov     cs:dword_180006254, 1
0x180001b09  mov     cs:dword_180006268, 3
0x180001b13  mov     eax, 8
0x180001b18  imul    rax, 0
0x180001b1c  lea     rcx, qword_180006270
0x180001b23  mov     qword ptr [rcx+rax], 2
0x180001b2b  mov     eax, 8
0x180001b30  imul    rax, 1
0x180001b34  lea     rcx, qword_180006270
0x180001b3b  mov     rdx, cs:__security_cookie
0x180001b42  mov     [rcx+rax], rdx
0x180001b46  mov     eax, 8
0x180001b4b  imul    rax, 2
0x180001b4f  lea     rcx, qword_180006270
0x180001b56  mov     rdx, cs:__security_cookie_complement
0x180001b5d  mov     [rcx+rax], rdx
0x180001b61  mov     eax, 8
0x180001b66  imul    rax, 0
0x180001b6a  mov     rcx, cs:__security_cookie
0x180001b71  mov     [rsp+rax+88h+var_20], rcx
0x180001b76  mov     eax, 8
0x180001b7b  imul    rax, 1
0x180001b7f  mov     rcx, cs:__security_cookie_complement
0x180001b86  mov     [rsp+rax+88h+var_20], rcx
0x180001b8b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001b92  call    __raise_securityfailure
0x180001b97  nop
0x180001b98  add     rsp, 88h
0x180001b9f  retn
```
