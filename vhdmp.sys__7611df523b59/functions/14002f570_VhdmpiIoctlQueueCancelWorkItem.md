# VhdmpiIoctlQueueCancelWorkItem

- ea: `0x14002f570`
- end: `0x14002f875`
- name: `VhdmpiIoctlQueueCancelWorkItem`
- size: `773`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x140023560`
- `0x1400269cc`
- `0x14002ec88`
- `0x14002f570`
- `0x140033fbc`
- `0x140035e94`
- `0x14009f2e4`
- `0x1400bbfc8`
- `0x1400d23f0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002f7ed`
- `ntoskrnl!IofCompleteRequest` at `0x14002f7ed`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f7dc`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f7dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f5d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f7fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f5d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f7fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f5fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f5fe`

## pseudocode

```c
void __fastcall VhdmpiIoctlQueueCancelWorkItem(__int64 a1)
{
  KSPIN_LOCK *v2; // r12
  KIRQL v3; // al
  __int64 **v4; // r14
  __int64 v5; // rcx
  int v6; // edx
  struct _EX_RUNDOWN_REF *v7; // r15
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // ecx
  ULONG_PTR Count; // rsi
  int v12; // ecx
  struct _VHD_SURFACE *v13; // rbp
  int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rbx
  __int64 v18; // rcx

  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
    TraceEvents("VhdmpiIoctlQueueCancelWorkItem", 0x18Fu, 5u, 2u, "VhdmpiIoctlQueueCancelWorkItem: enter...");
  v2 = (KSPIN_LOCK *)(a1 - 24);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 - 24));
  v4 = (__int64 **)(a1 - 16);
  while ( 1 )
  {
    v17 = *v4;
    v18 = **v4;
    if ( (__int64 **)(*v4)[1] != v4 || *(__int64 **)(v18 + 8) != v17 )
      __fastfail(3u);
    *v4 = (__int64 *)v18;
    *(_QWORD *)(v18 + 8) = v4;
    KeReleaseSpinLock(v2, v3);
    if ( v17 == (__int64 *)v4 )
      break;
    v5 = v17[2];
    v6 = *(_DWORD *)(v5 + 24);
    v7 = *(struct _EX_RUNDOWN_REF **)(*(_QWORD *)(v5 + 48) + 32LL);
    v8 = (unsigned int)(v6 - 2955556);
    if ( (unsigned int)v8 <= 0x34 && (v9 = 0x11111000000001LL, _bittest64(&v9, v8))
      || (unsigned int)(v6 - 2955860) <= 0xC && (v10 = 4353, _bittest(&v10, v6 - 2955860)) )
    {
      if ( (unsigned int)dword_140087708 > 4 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
          TraceEvents(
            "VhdmpiIoctlQueueCancelWorkItem",
            0x1C1u,
            4u,
            2u,
            "VhdmpiIoctlQueueCancelWorkItem: canceling async op, Irp=0x%p",
            v17 - 21);
      }
      VhdmpiCancelDequeuedAsyncOp((struct _IRP *)(v17 - 21));
    }
    else if ( v6 == 2955548 )
    {
      Count = v7[7].Count;
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
        TraceEvents(
          "VhdmpiIoctlQueueCancelWorkItem",
          0x1CFu,
          4u,
          2u,
          "VhdmpiIoctlQueueCancelWorkItem: canceling surface, Irp=0x%p",
          v17 - 21);
      v13 = (struct _VHD_SURFACE *)VhdmpiAddRefSurfaceByVirtualDisk(Count);
      if ( (Microsoft_Windows_VHDMPEnableBits & 2) != 0 )
        McTemplateK0zp_EtwWriteTransfer(
          v12,
          (unsigned int)VhdSurfaceCancellation,
          v14,
          *(_QWORD *)(*(_QWORD *)(Count + 144) + 120LL),
          0);
      if ( v13 )
      {
        VhdmpiHaltSurfaceOrWait(v13);
        VhdmpiAcquirePassiveLock(Count + 184, v15, v16);
        --*(_DWORD *)(Count + 208);
        VhdmpiReleasePassiveLock(Count + 184);
        VhdmpiReleaseSurface(v13);
      }
    }
    else if ( v6 == 2955904 )
    {
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
        TraceEvents(
          "VhdmpiIoctlQueueCancelWorkItem",
          0x1F2u,
          4u,
          2u,
          "VhdmpiIoctlQueueCancelWorkItem: canceling recovery, Irp=0x%p",
          v17 - 21);
      VhdmpiCancelVirtualDiskRecoveryV2(v7, v17 - 21);
    }
    ExReleaseRundownProtection(v7 + 33);
    IofCompleteRequest((PIRP)(v17 - 21), 0);
    v3 = KeAcquireSpinLockRaiseToDpc(v2);
  }
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
    TraceEvents("VhdmpiIoctlQueueCancelWorkItem", 0x203u, 5u, 2u, "VhdmpiIoctlQueueCancelWorkItem: leaving...");
}

```

## disassembly

```asm
0x14002f570  push    rbx
0x14002f572  push    rbp
0x14002f573  push    rsi
0x14002f574  push    rdi
0x14002f575  push    r12
0x14002f577  push    r13
0x14002f579  push    r14
0x14002f57b  push    r15
0x14002f57d  sub     rsp, 38h
0x14002f581  mov     eax, cs:dword_140087708
0x14002f587  mov     rbx, rcx
0x14002f58a  mov     r13d, 2
0x14002f590  cmp     eax, 5
0x14002f593  jbe     short loc_14002F5CC
0x14002f595  mov     edx, r13d
0x14002f598  lea     rcx, dword_140087708
0x14002f59f  call    _tlgKeywordOn
0x14002f5a4  test    al, al
0x14002f5a6  jz      short loc_14002F5CC
0x14002f5a8  lea     rax, aVhdmpiioctlque_3; "VhdmpiIoctlQueueCancelWorkItem: enter.."...
0x14002f5af  mov     edx, 18Fh; int
0x14002f5b4  mov     r9d, r13d; int
0x14002f5b7  mov     [rsp+78h+var_58], rax; char *
0x14002f5bc  lea     r8d, [r13+3]; int
0x14002f5c0  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002f5c7  call    TraceEvents
0x14002f5cc  lea     r12, [rbx-18h]
0x14002f5d0  mov     rcx, r12; SpinLock
0x14002f5d3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f5da  nop     dword ptr [rax+rax+00h]
0x14002f5df  lea     r14, [rbx-10h]
0x14002f5e3  jmp     loc_14002F808
0x14002f5e8  cmp     [rcx+8], rbx
0x14002f5ec  jnz     loc_14002F818
0x14002f5f2  mov     [r14], rcx
0x14002f5f5  mov     dl, al; NewIrql
0x14002f5f7  mov     [rcx+8], r14
0x14002f5fb  mov     rcx, r12; SpinLock
0x14002f5fe  call    cs:__imp_KeReleaseSpinLock
0x14002f605  nop     dword ptr [rax+rax+00h]
0x14002f60a  cmp     rbx, r14
0x14002f60d  jz      loc_14002F81F
0x14002f613  lea     rdi, [rbx-0A8h]
0x14002f61a  mov     rcx, [rdi+0B8h]
0x14002f621  mov     rax, [rcx+30h]
0x14002f625  mov     edx, [rcx+18h]
0x14002f628  mov     r15, [rax+20h]
0x14002f62c  lea     eax, [rdx-2D1924h]
0x14002f632  cmp     eax, 34h ; '4'
0x14002f635  ja      short loc_14002F647
0x14002f637  mov     rcx, 11111000000001h
0x14002f641  bt      rcx, rax
0x14002f645  jb      short loc_14002F65C
0x14002f647  lea     eax, [rdx-2D1A54h]
0x14002f64d  cmp     eax, 0Ch
0x14002f650  ja      short loc_14002F6B2
0x14002f652  mov     ecx, 1101h
0x14002f657  bt      ecx, eax
0x14002f65a  jnb     short loc_14002F6B2
0x14002f65c  mov     eax, cs:dword_140087708
0x14002f662  cmp     eax, 4
0x14002f665  jbe     short loc_14002F6A5
0x14002f667  mov     rdx, r13
0x14002f66a  lea     rcx, dword_140087708
0x14002f671  call    _tlgKeywordOn
0x14002f676  test    al, al
0x14002f678  jz      short loc_14002F6A5
0x14002f67a  lea     rax, aVhdmpiioctlque_4; "VhdmpiIoctlQueueCancelWorkItem: canceli"...
0x14002f681  mov     qword ptr [rsp+78h+var_50], rdi; char
0x14002f686  mov     edx, 1C1h; int
0x14002f68b  mov     [rsp+78h+var_58], rax; char *
0x14002f690  mov     r9d, r13d; int
0x14002f693  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002f69a  mov     r8d, 4; int
0x14002f6a0  call    TraceEvents
0x14002f6a5  mov     rcx, rdi; struct _IRP *
0x14002f6a8  call    ?VhdmpiCancelDequeuedAsyncOp@@YAXPEAU_IRP@@@Z; VhdmpiCancelDequeuedAsyncOp(_IRP *)
0x14002f6ad  jmp     loc_14002F7D5
0x14002f6b2  cmp     edx, 2D191Ch
0x14002f6b8  jnz     loc_14002F779
0x14002f6be  mov     eax, cs:dword_140087708
0x14002f6c4  mov     rsi, [r15+38h]
0x14002f6c8  cmp     eax, 4
0x14002f6cb  jbe     short loc_14002F70B
0x14002f6cd  mov     rdx, r13
0x14002f6d0  lea     rcx, dword_140087708
0x14002f6d7  call    _tlgKeywordOn
0x14002f6dc  test    al, al
0x14002f6de  jz      short loc_14002F70B
0x14002f6e0  lea     rax, aVhdmpiioctlque_1; "VhdmpiIoctlQueueCancelWorkItem: canceli"...
0x14002f6e7  mov     qword ptr [rsp+78h+var_50], rdi; char
0x14002f6ec  mov     edx, 1CFh; int
0x14002f6f1  mov     [rsp+78h+var_58], rax; char *
0x14002f6f6  mov     r9d, r13d; int
0x14002f6f9  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002f700  mov     r8d, 4; int
0x14002f706  call    TraceEvents
0x14002f70b  mov     rcx, rsi
0x14002f70e  call    VhdmpiAddRefSurfaceByVirtualDisk
0x14002f713  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, r13b
0x14002f71a  mov     rbp, rax
0x14002f71d  jz      short loc_14002F73F
0x14002f71f  mov     r9, [rsi+90h]
0x14002f726  lea     rdx, VhdSurfaceCancellation
0x14002f72d  mov     [rsp+78h+var_58], 0
0x14002f736  mov     r9, [r9+78h]
0x14002f73a  call    McTemplateK0zp_EtwWriteTransfer
0x14002f73f  test    rbp, rbp
0x14002f742  jz      loc_14002F7D5
0x14002f748  xor     edx, edx
0x14002f74a  mov     rcx, rbp; struct _VHD_SURFACE *
0x14002f74d  call    VhdmpiHaltSurfaceOrWait
0x14002f752  lea     rbx, [rsi+0B8h]
0x14002f759  mov     rcx, rbx
0x14002f75c  call    VhdmpiAcquirePassiveLock
0x14002f761  dec     dword ptr [rsi+0D0h]
0x14002f767  mov     rcx, rbx
0x14002f76a  call    VhdmpiReleasePassiveLock
0x14002f76f  mov     rcx, rbp
0x14002f772  call    VhdmpiReleaseSurface
0x14002f777  jmp     short loc_14002F7D5
0x14002f779  cmp     edx, 2D1A80h
0x14002f77f  jnz     short loc_14002F7D5
0x14002f781  mov     eax, cs:dword_140087708
0x14002f787  cmp     eax, 4
0x14002f78a  jbe     short loc_14002F7CA
0x14002f78c  mov     rdx, r13
0x14002f78f  lea     rcx, dword_140087708
0x14002f796  call    _tlgKeywordOn
0x14002f79b  test    al, al
0x14002f79d  jz      short loc_14002F7CA
0x14002f79f  lea     rax, aVhdmpiioctlque_0; "VhdmpiIoctlQueueCancelWorkItem: canceli"...
0x14002f7a6  mov     qword ptr [rsp+78h+var_50], rdi; char
0x14002f7ab  mov     edx, 1F2h; int
0x14002f7b0  mov     [rsp+78h+var_58], rax; char *
0x14002f7b5  mov     r9d, r13d; int
0x14002f7b8  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002f7bf  mov     r8d, 4; int
0x14002f7c5  call    TraceEvents
0x14002f7ca  mov     rdx, rdi
0x14002f7cd  mov     rcx, r15
0x14002f7d0  call    VhdmpiCancelVirtualDiskRecoveryV2
0x14002f7d5  lea     rcx, [r15+108h]; RunRef
0x14002f7dc  call    cs:__imp_ExReleaseRundownProtection
0x14002f7e3  nop     dword ptr [rax+rax+00h]
0x14002f7e8  xor     edx, edx; PriorityBoost
0x14002f7ea  mov     rcx, rdi; Irp
0x14002f7ed  call    cs:__imp_IofCompleteRequest
0x14002f7f4  nop     dword ptr [rax+rax+00h]
0x14002f7f9  mov     rcx, r12; SpinLock
0x14002f7fc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f803  nop     dword ptr [rax+rax+00h]
0x14002f808  mov     rbx, [r14]
0x14002f80b  mov     rcx, [rbx]
0x14002f80e  cmp     [rbx+8], r14
0x14002f812  jz      loc_14002F5E8
0x14002f818  mov     ecx, 3
0x14002f81d  int     29h; Win8: RtlFailFast(ecx)
0x14002f81f  mov     eax, cs:dword_140087708
0x14002f825  cmp     eax, 5
0x14002f828  jbe     short loc_14002F863
0x14002f82a  mov     rdx, r13
0x14002f82d  lea     rcx, dword_140087708
0x14002f834  call    _tlgKeywordOn
0x14002f839  test    al, al
0x14002f83b  jz      short loc_14002F863
0x14002f83d  lea     rax, aVhdmpiioctlque; "VhdmpiIoctlQueueCancelWorkItem: leaving"...
0x14002f844  mov     edx, 203h; int
0x14002f849  mov     r9d, r13d; int
0x14002f84c  mov     [rsp+78h+var_58], rax; char *
0x14002f851  mov     r8d, 5; int
0x14002f857  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002f85e  call    TraceEvents
0x14002f863  add     rsp, 38h
0x14002f867  pop     r15
0x14002f869  pop     r14
0x14002f86b  pop     r13
0x14002f86d  pop     r12
0x14002f86f  pop     rdi
0x14002f870  pop     rsi
0x14002f871  pop     rbp
0x14002f872  pop     rbx
0x14002f873  retn
```
