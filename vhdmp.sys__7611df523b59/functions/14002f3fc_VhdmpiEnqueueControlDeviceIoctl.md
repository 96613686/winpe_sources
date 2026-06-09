# VhdmpiEnqueueControlDeviceIoctl

- ea: `0x14002f3fc`
- end: `0x14002f55e`
- name: `VhdmpiEnqueueControlDeviceIoctl`
- size: `354`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140035508`
- `0x14009f454`
- `0x1400d2640`

## callees

- `0x140023560`
- `0x14002f3fc`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!IoCsqInsertIrpEx` at `0x14002f478`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x14002f478`
- `ntoskrnl!IofCompleteRequest` at `0x14002f4e2`
- `ntoskrnl!IofCompleteRequest` at `0x14002f4e2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f4f5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f4f5`

## pseudocode

```c
unsigned __int8 __fastcall VhdmpiEnqueueControlDeviceIoctl(PIRP Irp)
{
  struct _EX_RUNDOWN_REF *FsContext2; // rsi
  struct _IO_CSQ *v3; // rcx
  int inserted; // edi
  unsigned __int8 v5; // bl

  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
    TraceEvents("VhdmpiEnqueueControlDeviceIoctl", 0x28Cu, 5u, 2u, "VhdmpiEnqueueControlDeviceIoctl: enter...");
  FsContext2 = (struct _EX_RUNDOWN_REF *)Irp->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2;
  v3 = (struct _IO_CSQ *)(VhdmpControlExtension + 8);
  Irp->IoStatus.Status = 259;
  inserted = IoCsqInsertIrpEx(v3, Irp, 0, 0);
  if ( inserted < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
      TraceEvents(
        "VhdmpiEnqueueControlDeviceIoctl",
        0x2A8u,
        2u,
        2u,
        "VhdmpiEnqueueControlDeviceIoctl: failed to insert(0x%x)",
        inserted);
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = inserted;
    IofCompleteRequest(Irp, 0);
    ExReleaseRundownProtection(FsContext2 + 33);
    v5 = 0;
  }
  else
  {
    v5 = 1;
  }
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
    TraceEvents(
      "VhdmpiEnqueueControlDeviceIoctl",
      0x2B4u,
      5u,
      2u,
      "VhdmpiEnqueueControlDeviceIoctl: leaving... (0x%08x)",
      v5);
  return v5;
}

```

## disassembly

```asm
0x14002f3fc  push    rbx
0x14002f3fe  push    rbp
0x14002f3ff  push    rsi
0x14002f400  push    rdi
0x14002f401  sub     rsp, 38h
0x14002f405  mov     eax, cs:dword_140087708
0x14002f40b  mov     rbx, rcx
0x14002f40e  mov     ebp, 2
0x14002f413  cmp     eax, 5
0x14002f416  jbe     short loc_14002F44E
0x14002f418  mov     edx, ebp
0x14002f41a  lea     rcx, dword_140087708
0x14002f421  call    _tlgKeywordOn
0x14002f426  test    al, al
0x14002f428  jz      short loc_14002F44E
0x14002f42a  lea     rax, aVhdmpienqueuec_2; "VhdmpiEnqueueControlDeviceIoctl: enter."...
0x14002f431  mov     edx, 28Ch; int
0x14002f436  mov     r9d, ebp; int
0x14002f439  mov     [rsp+58h+var_38], rax; char *
0x14002f43e  lea     r8d, [rbp+3]; int
0x14002f442  lea     rcx, aVhdmpienqueuec_1; "VhdmpiEnqueueControlDeviceIoctl"
0x14002f449  call    TraceEvents
0x14002f44e  mov     rax, [rbx+0B8h]
0x14002f455  xor     r9d, r9d; InsertContext
0x14002f458  xor     r8d, r8d; Context
0x14002f45b  mov     rdx, rbx; Irp
0x14002f45e  mov     rcx, [rax+30h]
0x14002f462  mov     rsi, [rcx+20h]
0x14002f466  mov     rcx, cs:VhdmpControlExtension
0x14002f46d  add     rcx, 8; Csq
0x14002f471  mov     dword ptr [rbx+30h], 103h
0x14002f478  call    cs:__imp_IoCsqInsertIrpEx
0x14002f47f  nop     dword ptr [rax+rax+00h]
0x14002f484  mov     edi, eax
0x14002f486  test    eax, eax
0x14002f488  js      short loc_14002F48E
0x14002f48a  mov     bl, 1
0x14002f48c  jmp     short loc_14002F503
0x14002f48e  mov     eax, cs:dword_140087708
0x14002f494  cmp     eax, ebp
0x14002f496  jbe     short loc_14002F4D2
0x14002f498  mov     rdx, rbp
0x14002f49b  lea     rcx, dword_140087708
0x14002f4a2  call    _tlgKeywordOn
0x14002f4a7  test    al, al
0x14002f4a9  jz      short loc_14002F4D2
0x14002f4ab  lea     rax, aVhdmpienqueuec_0; "VhdmpiEnqueueControlDeviceIoctl: failed"...
0x14002f4b2  mov     dword ptr [rsp+58h+var_30], edi; char
0x14002f4b6  mov     edx, 2A8h; int
0x14002f4bb  mov     [rsp+58h+var_38], rax; char *
0x14002f4c0  mov     r9d, ebp; int
0x14002f4c3  lea     rcx, aVhdmpienqueuec_1; "VhdmpiEnqueueControlDeviceIoctl"
0x14002f4ca  mov     r8d, ebp; int
0x14002f4cd  call    TraceEvents
0x14002f4d2  xor     edx, edx; PriorityBoost
0x14002f4d4  mov     qword ptr [rbx+38h], 0
0x14002f4dc  mov     rcx, rbx; Irp
0x14002f4df  mov     [rbx+30h], edi
0x14002f4e2  call    cs:__imp_IofCompleteRequest
0x14002f4e9  nop     dword ptr [rax+rax+00h]
0x14002f4ee  lea     rcx, [rsi+108h]; RunRef
0x14002f4f5  call    cs:__imp_ExReleaseRundownProtection
0x14002f4fc  nop     dword ptr [rax+rax+00h]
0x14002f501  xor     bl, bl
0x14002f503  mov     eax, cs:dword_140087708
0x14002f509  cmp     eax, 5
0x14002f50c  jbe     short loc_14002F552
0x14002f50e  mov     rdx, rbp
0x14002f511  lea     rcx, dword_140087708
0x14002f518  call    _tlgKeywordOn
0x14002f51d  test    al, al
0x14002f51f  jz      short loc_14002F552
0x14002f521  movzx   edx, bl
0x14002f524  lea     rax, aVhdmpienqueuec; "VhdmpiEnqueueControlDeviceIoctl: leavin"...
0x14002f52b  mov     dword ptr [rsp+58h+var_30], edx; char
0x14002f52f  lea     rcx, aVhdmpienqueuec_1; "VhdmpiEnqueueControlDeviceIoctl"
0x14002f536  mov     r10d, 2B4h
0x14002f53c  mov     [rsp+58h+var_38], rax; char *
0x14002f541  mov     edx, r10d; int
0x14002f544  mov     r9d, ebp; int
0x14002f547  mov     r8d, 5; int
0x14002f54d  call    TraceEvents
0x14002f552  mov     al, bl
0x14002f554  add     rsp, 38h
0x14002f558  pop     rdi
0x14002f559  pop     rsi
0x14002f55a  pop     rbp
0x14002f55b  pop     rbx
0x14002f55c  retn
```
