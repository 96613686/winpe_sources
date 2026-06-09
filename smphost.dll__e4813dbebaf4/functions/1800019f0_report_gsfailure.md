# __report_gsfailure

- ea: `0x1800019f0`
- end: `0x180001b90`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002890`

## callees

- `0x1800019ac`
- `0x1800019f0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180001a9c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180001a9c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001a30`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001a30`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001a4f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001a4f`

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
0x1800019f0  mov     [rsp+arg_0], rcx
0x1800019f5  sub     rsp, 88h
0x1800019fc  mov     [rsp+88h+ControlPc], 0
0x180001a05  mov     [rsp+88h+var_30], 0
0x180001a0e  mov     [rsp+88h+FunctionEntry], 0
0x180001a17  mov     [rsp+88h+var_28], 0
0x180001a20  mov     [rsp+88h+ImageBase], 0
0x180001a29  lea     rcx, ContextRecord; ContextRecord
0x180001a30  call    cs:__imp_RtlCaptureContext
0x180001a36  mov     rax, cs:ContextRecord.Rip
0x180001a3d  mov     [rsp+88h+ControlPc], rax
0x180001a42  xor     r8d, r8d; HistoryTable
0x180001a45  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001a4a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180001a4f  call    cs:__imp_RtlLookupFunctionEntry
0x180001a55  mov     [rsp+88h+FunctionEntry], rax
0x180001a5a  cmp     [rsp+88h+FunctionEntry], 0
0x180001a60  jz      short loc_180001AA5
0x180001a62  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180001a6b  lea     rax, [rsp+88h+var_30]
0x180001a70  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001a75  lea     rax, [rsp+88h+var_28]
0x180001a7a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180001a7f  lea     rax, ContextRecord
0x180001a86  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180001a8b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001a90  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001a95  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001a9a  xor     ecx, ecx; HandlerType
0x180001a9c  call    cs:__imp_RtlVirtualUnwind
0x180001aa2  nop
0x180001aa3  jmp     short loc_180001AC8
0x180001aa5  mov     rax, cs:ContextRecord.Rsp
0x180001aac  mov     rax, [rax]
0x180001aaf  mov     cs:ContextRecord.Rip, rax
0x180001ab6  mov     rax, cs:ContextRecord.Rsp
0x180001abd  add     rax, 8
0x180001ac1  mov     cs:ContextRecord.Rsp, rax
0x180001ac8  mov     rax, cs:ContextRecord.Rip
0x180001acf  mov     cs:qword_180006260, rax
0x180001ad6  mov     rax, [rsp+88h+arg_0]
0x180001ade  mov     cs:ContextRecord.Rcx, rax
0x180001ae5  mov     cs:dword_180006250, 0C0000409h
0x180001aef  mov     cs:dword_180006254, 1
0x180001af9  mov     cs:dword_180006268, 3
0x180001b03  mov     eax, 8
0x180001b08  imul    rax, 0
0x180001b0c  lea     rcx, qword_180006270
0x180001b13  mov     qword ptr [rcx+rax], 2
0x180001b1b  mov     eax, 8
0x180001b20  imul    rax, 1
0x180001b24  lea     rcx, qword_180006270
0x180001b2b  mov     rdx, cs:__security_cookie
0x180001b32  mov     [rcx+rax], rdx
0x180001b36  mov     eax, 8
0x180001b3b  imul    rax, 2
0x180001b3f  lea     rcx, qword_180006270
0x180001b46  mov     rdx, cs:__security_cookie_complement
0x180001b4d  mov     [rcx+rax], rdx
0x180001b51  mov     eax, 8
0x180001b56  imul    rax, 0
0x180001b5a  mov     rcx, cs:__security_cookie
0x180001b61  mov     [rsp+rax+88h+var_20], rcx
0x180001b66  mov     eax, 8
0x180001b6b  imul    rax, 1
0x180001b6f  mov     rcx, cs:__security_cookie_complement
0x180001b76  mov     [rsp+rax+88h+var_20], rcx
0x180001b7b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001b82  call    __raise_securityfailure
0x180001b87  nop
0x180001b88  add     rsp, 88h
0x180001b8f  retn
```
