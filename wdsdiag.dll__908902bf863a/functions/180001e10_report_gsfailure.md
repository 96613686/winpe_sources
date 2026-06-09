# __report_gsfailure

- ea: `0x180001e10`
- end: `0x180001f81`
- name: `__report_gsfailure`
- size: `369`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001b30`

## callees

- `0x180001dd4`
- `0x180001e10`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x180001e23`
- `KERNEL32!RtlCaptureContext` at `0x180001e23`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001e42`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001e42`
- `KERNEL32!RtlVirtualUnwind` at `0x180001e8f`
- `KERNEL32!RtlVirtualUnwind` at `0x180001e8f`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF

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
  qword_1800050A0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_180005090 = -1073740791;
  dword_180005094 = 1;
  dword_1800050A8 = 3;
  qword_1800050B0[0] = 2;
  qword_1800050B0[1] = _security_cookie;
  qword_1800050B0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001e10  mov     [rsp+arg_0], rcx
0x180001e15  sub     rsp, 88h
0x180001e1c  lea     rcx, ContextRecord; ContextRecord
0x180001e23  call    cs:__imp_RtlCaptureContext
0x180001e29  mov     rax, cs:ContextRecord.Rip
0x180001e30  mov     [rsp+88h+ControlPc], rax
0x180001e35  xor     r8d, r8d; HistoryTable
0x180001e38  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001e3d  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180001e42  call    cs:__imp_RtlLookupFunctionEntry
0x180001e48  mov     [rsp+88h+FunctionEntry], rax
0x180001e4d  cmp     [rsp+88h+FunctionEntry], 0
0x180001e53  jz      short loc_180001E97
0x180001e55  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180001e5e  lea     rax, [rsp+88h+var_30]
0x180001e63  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001e68  lea     rax, [rsp+88h+var_28]
0x180001e6d  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180001e72  lea     rax, ContextRecord
0x180001e79  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180001e7e  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001e83  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001e88  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001e8d  xor     ecx, ecx; HandlerType
0x180001e8f  call    cs:__imp_RtlVirtualUnwind
0x180001e95  jmp     short loc_180001EBA
0x180001e97  mov     rax, cs:ContextRecord.Rsp
0x180001e9e  mov     rax, [rax]
0x180001ea1  mov     cs:ContextRecord.Rip, rax
0x180001ea8  mov     rax, cs:ContextRecord.Rsp
0x180001eaf  add     rax, 8
0x180001eb3  mov     cs:ContextRecord.Rsp, rax
0x180001eba  mov     rax, cs:ContextRecord.Rip
0x180001ec1  mov     cs:qword_1800050A0, rax
0x180001ec8  mov     rax, [rsp+88h+arg_0]
0x180001ed0  mov     cs:ContextRecord.Rcx, rax
0x180001ed7  mov     cs:dword_180005090, 0C0000409h
0x180001ee1  mov     cs:dword_180005094, 1
0x180001eeb  mov     cs:dword_1800050A8, 3
0x180001ef5  mov     eax, 8
0x180001efa  imul    rax, 0
0x180001efe  lea     rcx, qword_1800050B0
0x180001f05  mov     qword ptr [rcx+rax], 2
0x180001f0d  mov     eax, 8
0x180001f12  imul    rax, 1
0x180001f16  lea     rcx, qword_1800050B0
0x180001f1d  mov     rdx, cs:__security_cookie
0x180001f24  mov     [rcx+rax], rdx
0x180001f28  mov     eax, 8
0x180001f2d  imul    rax, 2
0x180001f31  lea     rcx, qword_1800050B0
0x180001f38  mov     rdx, cs:__security_cookie_complement
0x180001f3f  mov     [rcx+rax], rdx
0x180001f43  mov     eax, 8
0x180001f48  imul    rax, 0
0x180001f4c  mov     rcx, cs:__security_cookie
0x180001f53  mov     [rsp+rax+88h+var_20], rcx
0x180001f58  mov     eax, 8
0x180001f5d  imul    rax, 1
0x180001f61  mov     rcx, cs:__security_cookie_complement
0x180001f68  mov     [rsp+rax+88h+var_20], rcx
0x180001f6d  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001f74  call    __raise_securityfailure
0x180001f79  add     rsp, 88h
0x180001f80  retn
```
