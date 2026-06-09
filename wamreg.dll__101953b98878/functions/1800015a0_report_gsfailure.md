# __report_gsfailure

- ea: `0x1800015a0`
- end: `0x180001740`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006850`

## callees

- `0x180001558`
- `0x1800015a0`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x18000164c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000164c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800015ff`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800015ff`
- `KERNEL32!RtlCaptureContext` at `0x1800015e0`
- `KERNEL32!RtlCaptureContext` at `0x1800015e0`

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
  qword_18000B0C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000B0B0 = -1073740791;
  dword_18000B0B4 = 1;
  dword_18000B0C8 = 3;
  qword_18000B0D0[0] = 2;
  qword_18000B0D0[1] = _security_cookie;
  qword_18000B0D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800015a0  mov     [rsp+arg_0], rcx
0x1800015a5  sub     rsp, 88h
0x1800015ac  mov     [rsp+88h+ControlPc], 0
0x1800015b5  mov     [rsp+88h+var_30], 0
0x1800015be  mov     [rsp+88h+FunctionEntry], 0
0x1800015c7  mov     [rsp+88h+var_28], 0
0x1800015d0  mov     [rsp+88h+ImageBase], 0
0x1800015d9  lea     rcx, ContextRecord; ContextRecord
0x1800015e0  call    cs:__imp_RtlCaptureContext
0x1800015e6  mov     rax, cs:ContextRecord.Rip
0x1800015ed  mov     [rsp+88h+ControlPc], rax
0x1800015f2  xor     r8d, r8d; HistoryTable
0x1800015f5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800015fa  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800015ff  call    cs:__imp_RtlLookupFunctionEntry
0x180001605  mov     [rsp+88h+FunctionEntry], rax
0x18000160a  cmp     [rsp+88h+FunctionEntry], 0
0x180001610  jz      short loc_180001655
0x180001612  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000161b  lea     rax, [rsp+88h+var_30]
0x180001620  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001625  lea     rax, [rsp+88h+var_28]
0x18000162a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000162f  lea     rax, ContextRecord
0x180001636  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000163b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001640  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001645  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000164a  xor     ecx, ecx; HandlerType
0x18000164c  call    cs:__imp_RtlVirtualUnwind
0x180001652  nop
0x180001653  jmp     short loc_180001678
0x180001655  mov     rax, cs:ContextRecord.Rsp
0x18000165c  mov     rax, [rax]
0x18000165f  mov     cs:ContextRecord.Rip, rax
0x180001666  mov     rax, cs:ContextRecord.Rsp
0x18000166d  add     rax, 8
0x180001671  mov     cs:ContextRecord.Rsp, rax
0x180001678  mov     rax, cs:ContextRecord.Rip
0x18000167f  mov     cs:qword_18000B0C0, rax
0x180001686  mov     rax, [rsp+88h+arg_0]
0x18000168e  mov     cs:ContextRecord.Rcx, rax
0x180001695  mov     cs:dword_18000B0B0, 0C0000409h
0x18000169f  mov     cs:dword_18000B0B4, 1
0x1800016a9  mov     cs:dword_18000B0C8, 3
0x1800016b3  mov     eax, 8
0x1800016b8  imul    rax, 0
0x1800016bc  lea     rcx, qword_18000B0D0
0x1800016c3  mov     qword ptr [rcx+rax], 2
0x1800016cb  mov     eax, 8
0x1800016d0  imul    rax, 1
0x1800016d4  lea     rcx, qword_18000B0D0
0x1800016db  mov     rdx, cs:__security_cookie
0x1800016e2  mov     [rcx+rax], rdx
0x1800016e6  mov     eax, 8
0x1800016eb  imul    rax, 2
0x1800016ef  lea     rcx, qword_18000B0D0
0x1800016f6  mov     rdx, cs:__security_cookie_complement
0x1800016fd  mov     [rcx+rax], rdx
0x180001701  mov     eax, 8
0x180001706  imul    rax, 0
0x18000170a  mov     rcx, cs:__security_cookie
0x180001711  mov     [rsp+rax+88h+var_20], rcx
0x180001716  mov     eax, 8
0x18000171b  imul    rax, 1
0x18000171f  mov     rcx, cs:__security_cookie_complement
0x180001726  mov     [rsp+rax+88h+var_20], rcx
0x18000172b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001732  call    __raise_securityfailure
0x180001737  nop
0x180001738  add     rsp, 88h
0x18000173f  retn
```
