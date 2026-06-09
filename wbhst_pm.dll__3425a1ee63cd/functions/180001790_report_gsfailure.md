# __report_gsfailure

- ea: `0x180001790`
- end: `0x180001930`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004880`

## callees

- `0x18000174c`
- `0x180001790`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800017d0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800017d0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800017ef`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800017ef`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000183c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000183c`

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
0x180001790  mov     [rsp+arg_0], rcx
0x180001795  sub     rsp, 88h
0x18000179c  mov     [rsp+88h+ControlPc], 0
0x1800017a5  mov     [rsp+88h+var_30], 0
0x1800017ae  mov     [rsp+88h+FunctionEntry], 0
0x1800017b7  mov     [rsp+88h+var_28], 0
0x1800017c0  mov     [rsp+88h+ImageBase], 0
0x1800017c9  lea     rcx, ContextRecord; ContextRecord
0x1800017d0  call    cs:__imp_RtlCaptureContext
0x1800017d6  mov     rax, cs:ContextRecord.Rip
0x1800017dd  mov     [rsp+88h+ControlPc], rax
0x1800017e2  xor     r8d, r8d; HistoryTable
0x1800017e5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800017ea  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800017ef  call    cs:__imp_RtlLookupFunctionEntry
0x1800017f5  mov     [rsp+88h+FunctionEntry], rax
0x1800017fa  cmp     [rsp+88h+FunctionEntry], 0
0x180001800  jz      short loc_180001845
0x180001802  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000180b  lea     rax, [rsp+88h+var_30]
0x180001810  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001815  lea     rax, [rsp+88h+var_28]
0x18000181a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000181f  lea     rax, ContextRecord
0x180001826  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000182b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001830  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001835  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000183a  xor     ecx, ecx; HandlerType
0x18000183c  call    cs:__imp_RtlVirtualUnwind
0x180001842  nop
0x180001843  jmp     short loc_180001868
0x180001845  mov     rax, cs:ContextRecord.Rsp
0x18000184c  mov     rax, [rax]
0x18000184f  mov     cs:ContextRecord.Rip, rax
0x180001856  mov     rax, cs:ContextRecord.Rsp
0x18000185d  add     rax, 8
0x180001861  mov     cs:ContextRecord.Rsp, rax
0x180001868  mov     rax, cs:ContextRecord.Rip
0x18000186f  mov     cs:qword_1800090E0, rax
0x180001876  mov     rax, [rsp+88h+arg_0]
0x18000187e  mov     cs:ContextRecord.Rcx, rax
0x180001885  mov     cs:dword_1800090D0, 0C0000409h
0x18000188f  mov     cs:dword_1800090D4, 1
0x180001899  mov     cs:dword_1800090E8, 3
0x1800018a3  mov     eax, 8
0x1800018a8  imul    rax, 0
0x1800018ac  lea     rcx, qword_1800090F0
0x1800018b3  mov     qword ptr [rcx+rax], 2
0x1800018bb  mov     eax, 8
0x1800018c0  imul    rax, 1
0x1800018c4  lea     rcx, qword_1800090F0
0x1800018cb  mov     rdx, cs:__security_cookie
0x1800018d2  mov     [rcx+rax], rdx
0x1800018d6  mov     eax, 8
0x1800018db  imul    rax, 2
0x1800018df  lea     rcx, qword_1800090F0
0x1800018e6  mov     rdx, cs:__security_cookie_complement
0x1800018ed  mov     [rcx+rax], rdx
0x1800018f1  mov     eax, 8
0x1800018f6  imul    rax, 0
0x1800018fa  mov     rcx, cs:__security_cookie
0x180001901  mov     [rsp+rax+88h+var_20], rcx
0x180001906  mov     eax, 8
0x18000190b  imul    rax, 1
0x18000190f  mov     rcx, cs:__security_cookie_complement
0x180001916  mov     [rsp+rax+88h+var_20], rcx
0x18000191b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001922  call    __raise_securityfailure
0x180001927  nop
0x180001928  add     rsp, 88h
0x18000192f  retn
```
