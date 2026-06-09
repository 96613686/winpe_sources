# VhdmpiCancelAllQueuedSurfaceSensitiveIoctlsOnDisk

- ea: `0x14002efb4`
- end: `0x14002f149`
- name: `VhdmpiCancelAllQueuedSurfaceSensitiveIoctlsOnDisk`
- size: `405`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400bbfc8`
- `0x1400bc0d0`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x140022330`
- `0x140023560`
- `0x14002efb4`
- `0x140035e94`
- `0x14009f2e4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002f053`
- `ntoskrnl!IofCompleteRequest` at `0x14002f0d9`
- `ntoskrnl!IofCompleteRequest` at `0x14002f053`
- `ntoskrnl!IofCompleteRequest` at `0x14002f0d9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f042`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f0c8`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f042`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f0c8`

## pseudocode

```c
void __fastcall VhdmpiCancelAllQueuedSurfaceSensitiveIoctlsOnDisk(_DWORD *a1)
{
  struct _IRP *v2; // rax
  IRP *v3; // rdi
  __int64 v4; // rdx
  IRP *i; // rdi
  __int64 v6; // r8

  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
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
    VhdmpiAcquirePassiveLock(a1 + 46, v4, v6);
    --a1[52];
    VhdmpiReleasePassiveLock(a1 + 46);
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)i->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2 + 33);
    IofCompleteRequest(i, 0);
  }
  if ( (unsigned int)dword_140087708 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
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
0x14002efb4  push    rbx
0x14002efb6  push    rsi
0x14002efb7  push    rdi
0x14002efb8  push    r14
0x14002efba  sub     rsp, 38h
0x14002efbe  mov     eax, cs:dword_140087708
0x14002efc4  mov     rbx, rcx
0x14002efc7  mov     r14d, 10h
0x14002efcd  cmp     eax, 5
0x14002efd0  jbe     short loc_14002F00E
0x14002efd2  mov     edx, r14d
0x14002efd5  lea     rcx, dword_140087708
0x14002efdc  call    _tlgKeywordOn
0x14002efe1  test    al, al
0x14002efe3  jz      short loc_14002F00E
0x14002efe5  lea     rax, aVhdmpicancelal_6; "VhdmpiCancelAllQueuedIoctlsOnDisk: ente"...
0x14002efec  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14002eff1  mov     edx, 38Dh; int
0x14002eff6  mov     [rsp+58h+var_38], rax; char *
0x14002effb  mov     r9d, r14d; int
0x14002effe  lea     r8d, [r14-0Bh]; int
0x14002f002  lea     rcx, aVhdmpicancelal; "VhdmpiCancelAllQueuedSurfaceSensitiveIo"...
0x14002f009  call    TraceEvents
0x14002f00e  mov     esi, 2D1948h
0x14002f013  jmp     short loc_14002F05F
0x14002f015  mov     rcx, rdi; struct _IRP *
0x14002f018  mov     qword ptr [rdi+38h], 0
0x14002f020  mov     dword ptr [rdi+30h], 0C0000120h
0x14002f027  call    ?VhdmpiCancelDequeuedAsyncOp@@YAXPEAU_IRP@@@Z; VhdmpiCancelDequeuedAsyncOp(_IRP *)
0x14002f02c  mov     rcx, [rdi+0B8h]
0x14002f033  mov     rdx, [rcx+30h]
0x14002f037  mov     rcx, [rdx+20h]
0x14002f03b  add     rcx, 108h; RunRef
0x14002f042  call    cs:__imp_ExReleaseRundownProtection
0x14002f049  nop     dword ptr [rax+rax+00h]
0x14002f04e  xor     edx, edx; PriorityBoost
0x14002f050  mov     rcx, rdi; Irp
0x14002f053  call    cs:__imp_IofCompleteRequest
0x14002f05a  nop     dword ptr [rax+rax+00h]
0x14002f05f  mov     edx, esi
0x14002f061  mov     rcx, rbx
0x14002f064  call    VhdmpiDequeueControlDeviceIoctl
0x14002f069  mov     rdi, rax
0x14002f06c  test    rax, rax
0x14002f06f  jnz     short loc_14002F015
0x14002f071  mov     edx, 2D191Ch
0x14002f076  mov     rcx, rbx
0x14002f079  call    VhdmpiDequeueControlDeviceIoctl
0x14002f07e  mov     rdi, rax
0x14002f081  test    rax, rax
0x14002f084  jz      short loc_14002F0FA
0x14002f086  lea     rsi, [rbx+0B8h]
0x14002f08d  mov     rcx, rsi
0x14002f090  mov     qword ptr [rdi+38h], 0
0x14002f098  mov     dword ptr [rdi+30h], 0C0000120h
0x14002f09f  call    VhdmpiAcquirePassiveLock
0x14002f0a4  dec     dword ptr [rbx+0D0h]
0x14002f0aa  mov     rcx, rsi
0x14002f0ad  call    VhdmpiReleasePassiveLock
0x14002f0b2  mov     rax, [rdi+0B8h]
0x14002f0b9  mov     rcx, [rax+30h]
0x14002f0bd  mov     rcx, [rcx+20h]
0x14002f0c1  add     rcx, 108h; RunRef
0x14002f0c8  call    cs:__imp_ExReleaseRundownProtection
0x14002f0cf  nop     dword ptr [rax+rax+00h]
0x14002f0d4  xor     edx, edx; PriorityBoost
0x14002f0d6  mov     rcx, rdi; Irp
0x14002f0d9  call    cs:__imp_IofCompleteRequest
0x14002f0e0  nop     dword ptr [rax+rax+00h]
0x14002f0e5  mov     edx, 2D191Ch
0x14002f0ea  mov     rcx, rbx
0x14002f0ed  call    VhdmpiDequeueControlDeviceIoctl
0x14002f0f2  mov     rdi, rax
0x14002f0f5  test    rax, rax
0x14002f0f8  jnz     short loc_14002F08D
0x14002f0fa  mov     eax, cs:dword_140087708
0x14002f100  cmp     eax, 5
0x14002f103  jbe     short loc_14002F13E
0x14002f105  mov     rdx, r14
0x14002f108  lea     rcx, dword_140087708
0x14002f10f  call    _tlgKeywordOn
0x14002f114  test    al, al
0x14002f116  jz      short loc_14002F13E
0x14002f118  lea     rax, aVhdmpicancelal_5; "VhdmpiCancelAllQueuedIoctlsOnDisk: leav"...
0x14002f11f  mov     edx, 3BAh; int
0x14002f124  mov     r9d, r14d; int
0x14002f127  mov     [rsp+58h+var_38], rax; char *
0x14002f12c  mov     r8d, 5; int
0x14002f132  lea     rcx, aVhdmpicancelal; "VhdmpiCancelAllQueuedSurfaceSensitiveIo"...
0x14002f139  call    TraceEvents
0x14002f13e  add     rsp, 38h
0x14002f142  pop     r14
0x14002f144  pop     rdi
0x14002f145  pop     rsi
0x14002f146  pop     rbx
0x14002f147  retn
```
