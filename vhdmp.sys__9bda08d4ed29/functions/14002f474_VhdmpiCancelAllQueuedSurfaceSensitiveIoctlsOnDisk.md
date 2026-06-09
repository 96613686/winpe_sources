# VhdmpiCancelAllQueuedSurfaceSensitiveIoctlsOnDisk

- ea: `0x14002f474`
- end: `0x14002f609`
- name: `VhdmpiCancelAllQueuedSurfaceSensitiveIoctlsOnDisk`
- size: `405`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400bbfb8`
- `0x1400bc0c0`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x140022750`
- `0x140023980`
- `0x14002f474`
- `0x140036284`
- `0x14009f2e4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002f513`
- `ntoskrnl!IofCompleteRequest` at `0x14002f599`
- `ntoskrnl!IofCompleteRequest` at `0x14002f513`
- `ntoskrnl!IofCompleteRequest` at `0x14002f599`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f502`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f588`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f502`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f588`

## pseudocode

```c
void __fastcall VhdmpiCancelAllQueuedSurfaceSensitiveIoctlsOnDisk(_DWORD *a1)
{
  struct _IRP *v2; // rax
  IRP *v3; // rdi
  IRP *i; // rdi

  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents(
      "VhdmpiCancelAllQueuedSurfaceSensitiveIoctlsOnDisk",
      0x38Du,
      5u,
      0x10u,
      "VhdmpiCancelAllQueuedIoctlsOnDisk: enter... VirtualDisk=0x%p",
      a1);
  while ( 1 )
  {
    v2 = (struct _IRP *)VhdmpiDequeueControlDeviceIoctl(a1, 2955592);
    v3 = v2;
    if ( !v2 )
      break;
    v2->IoStatus.Information = 0;
    v2->IoStatus.Status = -1073741536;
    VhdmpiCancelDequeuedAsyncOp(v2);
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)v3->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2 + 33);
    IofCompleteRequest(v3, 0);
  }
  for ( i = (IRP *)VhdmpiDequeueControlDeviceIoctl(a1, 2955548); i; i = (IRP *)VhdmpiDequeueControlDeviceIoctl(
                                                                                 a1,
                                                                                 2955548) )
  {
    i->IoStatus.Information = 0;
    i->IoStatus.Status = -1073741536;
    VhdmpiAcquirePassiveLock(a1 + 46);
    --a1[52];
    VhdmpiReleasePassiveLock(a1 + 46);
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)i->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2 + 33);
    IofCompleteRequest(i, 0);
  }
  if ( (unsigned int)dword_1400876D0 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents(
        "VhdmpiCancelAllQueuedSurfaceSensitiveIoctlsOnDisk",
        0x3BAu,
        5u,
        0x10u,
        "VhdmpiCancelAllQueuedIoctlsOnDisk: leaving...");
  }
}

```

## disassembly

```asm
0x14002f474  push    rbx
0x14002f476  push    rsi
0x14002f477  push    rdi
0x14002f478  push    r14
0x14002f47a  sub     rsp, 38h
0x14002f47e  mov     eax, cs:dword_1400876D0
0x14002f484  mov     rbx, rcx
0x14002f487  mov     r14d, 10h
0x14002f48d  cmp     eax, 5
0x14002f490  jbe     short loc_14002F4CE
0x14002f492  mov     edx, r14d
0x14002f495  lea     rcx, dword_1400876D0
0x14002f49c  call    _tlgKeywordOn
0x14002f4a1  test    al, al
0x14002f4a3  jz      short loc_14002F4CE
0x14002f4a5  lea     rax, aVhdmpicancelal_6; "VhdmpiCancelAllQueuedIoctlsOnDisk: ente"...
0x14002f4ac  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14002f4b1  mov     edx, 38Dh; int
0x14002f4b6  mov     [rsp+58h+var_38], rax; char *
0x14002f4bb  mov     r9d, r14d; int
0x14002f4be  lea     r8d, [r14-0Bh]; int
0x14002f4c2  lea     rcx, aVhdmpicancelal; "VhdmpiCancelAllQueuedSurfaceSensitiveIo"...
0x14002f4c9  call    TraceEvents
0x14002f4ce  mov     esi, 2D1948h
0x14002f4d3  jmp     short loc_14002F51F
0x14002f4d5  mov     rcx, rdi; struct _IRP *
0x14002f4d8  mov     qword ptr [rdi+38h], 0
0x14002f4e0  mov     dword ptr [rdi+30h], 0C0000120h
0x14002f4e7  call    ?VhdmpiCancelDequeuedAsyncOp@@YAXPEAU_IRP@@@Z; VhdmpiCancelDequeuedAsyncOp(_IRP *)
0x14002f4ec  mov     rcx, [rdi+0B8h]
0x14002f4f3  mov     rdx, [rcx+30h]
0x14002f4f7  mov     rcx, [rdx+20h]
0x14002f4fb  add     rcx, 108h; RunRef
0x14002f502  call    cs:__imp_ExReleaseRundownProtection
0x14002f509  nop     dword ptr [rax+rax+00h]
0x14002f50e  xor     edx, edx; PriorityBoost
0x14002f510  mov     rcx, rdi; Irp
0x14002f513  call    cs:__imp_IofCompleteRequest
0x14002f51a  nop     dword ptr [rax+rax+00h]
0x14002f51f  mov     edx, esi
0x14002f521  mov     rcx, rbx
0x14002f524  call    VhdmpiDequeueControlDeviceIoctl
0x14002f529  mov     rdi, rax
0x14002f52c  test    rax, rax
0x14002f52f  jnz     short loc_14002F4D5
0x14002f531  mov     edx, 2D191Ch
0x14002f536  mov     rcx, rbx
0x14002f539  call    VhdmpiDequeueControlDeviceIoctl
0x14002f53e  mov     rdi, rax
0x14002f541  test    rax, rax
0x14002f544  jz      short loc_14002F5BA
0x14002f546  lea     rsi, [rbx+0B8h]
0x14002f54d  mov     rcx, rsi
0x14002f550  mov     qword ptr [rdi+38h], 0
0x14002f558  mov     dword ptr [rdi+30h], 0C0000120h
0x14002f55f  call    VhdmpiAcquirePassiveLock
0x14002f564  dec     dword ptr [rbx+0D0h]
0x14002f56a  mov     rcx, rsi
0x14002f56d  call    VhdmpiReleasePassiveLock
0x14002f572  mov     rax, [rdi+0B8h]
0x14002f579  mov     rcx, [rax+30h]
0x14002f57d  mov     rcx, [rcx+20h]
0x14002f581  add     rcx, 108h; RunRef
0x14002f588  call    cs:__imp_ExReleaseRundownProtection
0x14002f58f  nop     dword ptr [rax+rax+00h]
0x14002f594  xor     edx, edx; PriorityBoost
0x14002f596  mov     rcx, rdi; Irp
0x14002f599  call    cs:__imp_IofCompleteRequest
0x14002f5a0  nop     dword ptr [rax+rax+00h]
0x14002f5a5  mov     edx, 2D191Ch
0x14002f5aa  mov     rcx, rbx
0x14002f5ad  call    VhdmpiDequeueControlDeviceIoctl
0x14002f5b2  mov     rdi, rax
0x14002f5b5  test    rax, rax
0x14002f5b8  jnz     short loc_14002F54D
0x14002f5ba  mov     eax, cs:dword_1400876D0
0x14002f5c0  cmp     eax, 5
0x14002f5c3  jbe     short loc_14002F5FE
0x14002f5c5  mov     rdx, r14
0x14002f5c8  lea     rcx, dword_1400876D0
0x14002f5cf  call    _tlgKeywordOn
0x14002f5d4  test    al, al
0x14002f5d6  jz      short loc_14002F5FE
0x14002f5d8  lea     rax, aVhdmpicancelal_5; "VhdmpiCancelAllQueuedIoctlsOnDisk: leav"...
0x14002f5df  mov     edx, 3BAh; int
0x14002f5e4  mov     r9d, r14d; int
0x14002f5e7  mov     [rsp+58h+var_38], rax; char *
0x14002f5ec  mov     r8d, 5; int
0x14002f5f2  lea     rcx, aVhdmpicancelal; "VhdmpiCancelAllQueuedSurfaceSensitiveIo"...
0x14002f5f9  call    TraceEvents
0x14002f5fe  add     rsp, 38h
0x14002f602  pop     r14
0x14002f604  pop     rdi
0x14002f605  pop     rsi
0x14002f606  pop     rbx
0x14002f607  retn
```
