# __report_gsfailure

- ea: `0x180002160`
- end: `0x180002300`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800033f0`

## callees

- `0x180002124`
- `0x180002160`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800021a0`
- `ntdll!RtlCaptureContext` at `0x1800021a0`
- `ntdll!RtlLookupFunctionEntry` at `0x1800021bf`
- `ntdll!RtlLookupFunctionEntry` at `0x1800021bf`
- `ntdll!RtlVirtualUnwind` at `0x18000220c`
- `ntdll!RtlVirtualUnwind` at `0x18000220c`

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
  qword_18000A0F0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000A0E0 = -1073740791;
  dword_18000A0E4 = 1;
  dword_18000A0F8 = 3;
  qword_18000A100[0] = 2;
  qword_18000A100[1] = _security_cookie;
  qword_18000A100[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180002160  mov     [rsp+arg_0], rcx
0x180002165  sub     rsp, 88h
0x18000216c  mov     [rsp+88h+ControlPc], 0
0x180002175  mov     [rsp+88h+var_30], 0
0x18000217e  mov     [rsp+88h+FunctionEntry], 0
0x180002187  mov     [rsp+88h+var_28], 0
0x180002190  mov     [rsp+88h+ImageBase], 0
0x180002199  lea     rcx, ContextRecord; ContextRecord
0x1800021a0  call    cs:__imp_RtlCaptureContext
0x1800021a6  mov     rax, cs:ContextRecord.Rip
0x1800021ad  mov     [rsp+88h+ControlPc], rax
0x1800021b2  xor     r8d, r8d; HistoryTable
0x1800021b5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800021ba  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800021bf  call    cs:__imp_RtlLookupFunctionEntry
0x1800021c5  mov     [rsp+88h+FunctionEntry], rax
0x1800021ca  cmp     [rsp+88h+FunctionEntry], 0
0x1800021d0  jz      short loc_180002215
0x1800021d2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800021db  lea     rax, [rsp+88h+var_30]
0x1800021e0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800021e5  lea     rax, [rsp+88h+var_28]
0x1800021ea  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800021ef  lea     rax, ContextRecord
0x1800021f6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800021fb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180002200  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180002205  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000220a  xor     ecx, ecx; HandlerType
0x18000220c  call    cs:__imp_RtlVirtualUnwind
0x180002212  nop
0x180002213  jmp     short loc_180002238
0x180002215  mov     rax, cs:ContextRecord.Rsp
0x18000221c  mov     rax, [rax]
0x18000221f  mov     cs:ContextRecord.Rip, rax
0x180002226  mov     rax, cs:ContextRecord.Rsp
0x18000222d  add     rax, 8
0x180002231  mov     cs:ContextRecord.Rsp, rax
0x180002238  mov     rax, cs:ContextRecord.Rip
0x18000223f  mov     cs:qword_18000A0F0, rax
0x180002246  mov     rax, [rsp+88h+arg_0]
0x18000224e  mov     cs:ContextRecord.Rcx, rax
0x180002255  mov     cs:dword_18000A0E0, 0C0000409h
0x18000225f  mov     cs:dword_18000A0E4, 1
0x180002269  mov     cs:dword_18000A0F8, 3
0x180002273  mov     eax, 8
0x180002278  imul    rax, 0
0x18000227c  lea     rcx, qword_18000A100
0x180002283  mov     qword ptr [rcx+rax], 2
0x18000228b  mov     eax, 8
0x180002290  imul    rax, 1
0x180002294  lea     rcx, qword_18000A100
0x18000229b  mov     rdx, cs:__security_cookie
0x1800022a2  mov     [rcx+rax], rdx
0x1800022a6  mov     eax, 8
0x1800022ab  imul    rax, 2
0x1800022af  lea     rcx, qword_18000A100
0x1800022b6  mov     rdx, cs:__security_cookie_complement
0x1800022bd  mov     [rcx+rax], rdx
0x1800022c1  mov     eax, 8
0x1800022c6  imul    rax, 0
0x1800022ca  mov     rcx, cs:__security_cookie
0x1800022d1  mov     [rsp+rax+88h+var_20], rcx
0x1800022d6  mov     eax, 8
0x1800022db  imul    rax, 1
0x1800022df  mov     rcx, cs:__security_cookie_complement
0x1800022e6  mov     [rsp+rax+88h+var_20], rcx
0x1800022eb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800022f2  call    __raise_securityfailure
0x1800022f7  nop
0x1800022f8  add     rsp, 88h
0x1800022ff  retn
```
