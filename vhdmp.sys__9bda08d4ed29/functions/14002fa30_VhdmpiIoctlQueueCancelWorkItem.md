# VhdmpiIoctlQueueCancelWorkItem

- ea: `0x14002fa30`
- end: `0x14002fd35`
- name: `VhdmpiIoctlQueueCancelWorkItem`
- size: `773`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x140023980`
- `0x140026dec`
- `0x14002f148`
- `0x14002fa30`
- `0x14003447c`
- `0x140036284`
- `0x14009f2e4`
- `0x1400bbfb8`
- `0x1400d2380`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002fcad`
- `ntoskrnl!IofCompleteRequest` at `0x14002fcad`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002fc9c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002fc9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fa93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fcbc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fa93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fcbc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fabe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fabe`

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
  __int64 *v15; // rbx
  __int64 v16; // rcx

  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
    TraceEvents("VhdmpiIoctlQueueCancelWorkItem", 0x18Fu, 5u, 2u, "VhdmpiIoctlQueueCancelWorkItem: enter...");
  v2 = (KSPIN_LOCK *)(a1 - 24);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 - 24));
  v4 = (__int64 **)(a1 - 16);
  while ( 1 )
  {
    v15 = *v4;
    v16 = **v4;
    if ( (__int64 **)(*v4)[1] != v4 || *(__int64 **)(v16 + 8) != v15 )
      __fastfail(3u);
    *v4 = (__int64 *)v16;
    *(_QWORD *)(v16 + 8) = v4;
    KeReleaseSpinLock(v2, v3);
    if ( v15 == (__int64 *)v4 )
      break;
    v5 = v15[2];
    v6 = *(_DWORD *)(v5 + 24);
    v7 = *(struct _EX_RUNDOWN_REF **)(*(_QWORD *)(v5 + 48) + 32LL);
    v8 = (unsigned int)(v6 - 2955556);
    if ( (unsigned int)v8 <= 0x34 && (v9 = 0x11111000000001LL, _bittest64(&v9, v8))
      || (unsigned int)(v6 - 2955860) <= 0xC && (v10 = 4353, _bittest(&v10, v6 - 2955860)) )
    {
      if ( (unsigned int)dword_1400876D0 > 4 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
          TraceEvents(
            "VhdmpiIoctlQueueCancelWorkItem",
            0x1C1u,
            4u,
            2u,
            "VhdmpiIoctlQueueCancelWorkItem: canceling async op, Irp=0x%p",
            v15 - 21);
      }
      VhdmpiCancelDequeuedAsyncOp((struct _IRP *)(v15 - 21));
    }
    else if ( v6 == 2955548 )
    {
      Count = v7[7].Count;
      if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
        TraceEvents(
          "VhdmpiIoctlQueueCancelWorkItem",
          0x1CFu,
          4u,
          2u,
          "VhdmpiIoctlQueueCancelWorkItem: canceling surface, Irp=0x%p",
          v15 - 21);
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
        VhdmpiAcquirePassiveLock(Count + 184);
        --*(_DWORD *)(Count + 208);
        VhdmpiReleasePassiveLock(Count + 184);
        VhdmpiReleaseSurface(v13);
      }
    }
    else if ( v6 == 2955904 )
    {
      if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
        TraceEvents(
          "VhdmpiIoctlQueueCancelWorkItem",
          0x1F2u,
          4u,
          2u,
          "VhdmpiIoctlQueueCancelWorkItem: canceling recovery, Irp=0x%p",
          v15 - 21);
      VhdmpiCancelVirtualDiskRecoveryV2(v7, v15 - 21);
    }
    ExReleaseRundownProtection(v7 + 33);
    IofCompleteRequest((PIRP)(v15 - 21), 0);
    v3 = KeAcquireSpinLockRaiseToDpc(v2);
  }
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
    TraceEvents("VhdmpiIoctlQueueCancelWorkItem", 0x203u, 5u, 2u, "VhdmpiIoctlQueueCancelWorkItem: leaving...");
}

```

## disassembly

```asm
0x14002fa30  push    rbx
0x14002fa32  push    rbp
0x14002fa33  push    rsi
0x14002fa34  push    rdi
0x14002fa35  push    r12
0x14002fa37  push    r13
0x14002fa39  push    r14
0x14002fa3b  push    r15
0x14002fa3d  sub     rsp, 38h
0x14002fa41  mov     eax, cs:dword_1400876D0
0x14002fa47  mov     rbx, rcx
0x14002fa4a  mov     r13d, 2
0x14002fa50  cmp     eax, 5
0x14002fa53  jbe     short loc_14002FA8C
0x14002fa55  mov     edx, r13d
0x14002fa58  lea     rcx, dword_1400876D0
0x14002fa5f  call    _tlgKeywordOn
0x14002fa64  test    al, al
0x14002fa66  jz      short loc_14002FA8C
0x14002fa68  lea     rax, aVhdmpiioctlque_3; "VhdmpiIoctlQueueCancelWorkItem: enter.."...
0x14002fa6f  mov     edx, 18Fh; int
0x14002fa74  mov     r9d, r13d; int
0x14002fa77  mov     [rsp+78h+var_58], rax; char *
0x14002fa7c  lea     r8d, [r13+3]; int
0x14002fa80  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002fa87  call    TraceEvents
0x14002fa8c  lea     r12, [rbx-18h]
0x14002fa90  mov     rcx, r12; SpinLock
0x14002fa93  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002fa9a  nop     dword ptr [rax+rax+00h]
0x14002fa9f  lea     r14, [rbx-10h]
0x14002faa3  jmp     loc_14002FCC8
0x14002faa8  cmp     [rcx+8], rbx
0x14002faac  jnz     loc_14002FCD8
0x14002fab2  mov     [r14], rcx
0x14002fab5  mov     dl, al; NewIrql
0x14002fab7  mov     [rcx+8], r14
0x14002fabb  mov     rcx, r12; SpinLock
0x14002fabe  call    cs:__imp_KeReleaseSpinLock
0x14002fac5  nop     dword ptr [rax+rax+00h]
0x14002faca  cmp     rbx, r14
0x14002facd  jz      loc_14002FCDF
0x14002fad3  lea     rdi, [rbx-0A8h]
0x14002fada  mov     rcx, [rdi+0B8h]
0x14002fae1  mov     rax, [rcx+30h]
0x14002fae5  mov     edx, [rcx+18h]
0x14002fae8  mov     r15, [rax+20h]
0x14002faec  lea     eax, [rdx-2D1924h]
0x14002faf2  cmp     eax, 34h ; '4'
0x14002faf5  ja      short loc_14002FB07
0x14002faf7  mov     rcx, 11111000000001h
0x14002fb01  bt      rcx, rax
0x14002fb05  jb      short loc_14002FB1C
0x14002fb07  lea     eax, [rdx-2D1A54h]
0x14002fb0d  cmp     eax, 0Ch
0x14002fb10  ja      short loc_14002FB72
0x14002fb12  mov     ecx, 1101h
0x14002fb17  bt      ecx, eax
0x14002fb1a  jnb     short loc_14002FB72
0x14002fb1c  mov     eax, cs:dword_1400876D0
0x14002fb22  cmp     eax, 4
0x14002fb25  jbe     short loc_14002FB65
0x14002fb27  mov     rdx, r13
0x14002fb2a  lea     rcx, dword_1400876D0
0x14002fb31  call    _tlgKeywordOn
0x14002fb36  test    al, al
0x14002fb38  jz      short loc_14002FB65
0x14002fb3a  lea     rax, aVhdmpiioctlque_4; "VhdmpiIoctlQueueCancelWorkItem: canceli"...
0x14002fb41  mov     qword ptr [rsp+78h+var_50], rdi; char
0x14002fb46  mov     edx, 1C1h; int
0x14002fb4b  mov     [rsp+78h+var_58], rax; char *
0x14002fb50  mov     r9d, r13d; int
0x14002fb53  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002fb5a  mov     r8d, 4; int
0x14002fb60  call    TraceEvents
0x14002fb65  mov     rcx, rdi; struct _IRP *
0x14002fb68  call    ?VhdmpiCancelDequeuedAsyncOp@@YAXPEAU_IRP@@@Z; VhdmpiCancelDequeuedAsyncOp(_IRP *)
0x14002fb6d  jmp     loc_14002FC95
0x14002fb72  cmp     edx, 2D191Ch
0x14002fb78  jnz     loc_14002FC39
0x14002fb7e  mov     eax, cs:dword_1400876D0
0x14002fb84  mov     rsi, [r15+38h]
0x14002fb88  cmp     eax, 4
0x14002fb8b  jbe     short loc_14002FBCB
0x14002fb8d  mov     rdx, r13
0x14002fb90  lea     rcx, dword_1400876D0
0x14002fb97  call    _tlgKeywordOn
0x14002fb9c  test    al, al
0x14002fb9e  jz      short loc_14002FBCB
0x14002fba0  lea     rax, aVhdmpiioctlque_1; "VhdmpiIoctlQueueCancelWorkItem: canceli"...
0x14002fba7  mov     qword ptr [rsp+78h+var_50], rdi; char
0x14002fbac  mov     edx, 1CFh; int
0x14002fbb1  mov     [rsp+78h+var_58], rax; char *
0x14002fbb6  mov     r9d, r13d; int
0x14002fbb9  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002fbc0  mov     r8d, 4; int
0x14002fbc6  call    TraceEvents
0x14002fbcb  mov     rcx, rsi
0x14002fbce  call    VhdmpiAddRefSurfaceByVirtualDisk
0x14002fbd3  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, r13b
0x14002fbda  mov     rbp, rax
0x14002fbdd  jz      short loc_14002FBFF
0x14002fbdf  mov     r9, [rsi+90h]
0x14002fbe6  lea     rdx, VhdSurfaceCancellation
0x14002fbed  mov     [rsp+78h+var_58], 0
0x14002fbf6  mov     r9, [r9+78h]
0x14002fbfa  call    McTemplateK0zp_EtwWriteTransfer
0x14002fbff  test    rbp, rbp
0x14002fc02  jz      loc_14002FC95
0x14002fc08  xor     edx, edx
0x14002fc0a  mov     rcx, rbp; struct _VHD_SURFACE *
0x14002fc0d  call    VhdmpiHaltSurfaceOrWait
0x14002fc12  lea     rbx, [rsi+0B8h]
0x14002fc19  mov     rcx, rbx
0x14002fc1c  call    VhdmpiAcquirePassiveLock
0x14002fc21  dec     dword ptr [rsi+0D0h]
0x14002fc27  mov     rcx, rbx
0x14002fc2a  call    VhdmpiReleasePassiveLock
0x14002fc2f  mov     rcx, rbp
0x14002fc32  call    VhdmpiReleaseSurface
0x14002fc37  jmp     short loc_14002FC95
0x14002fc39  cmp     edx, 2D1A80h
0x14002fc3f  jnz     short loc_14002FC95
0x14002fc41  mov     eax, cs:dword_1400876D0
0x14002fc47  cmp     eax, 4
0x14002fc4a  jbe     short loc_14002FC8A
0x14002fc4c  mov     rdx, r13
0x14002fc4f  lea     rcx, dword_1400876D0
0x14002fc56  call    _tlgKeywordOn
0x14002fc5b  test    al, al
0x14002fc5d  jz      short loc_14002FC8A
0x14002fc5f  lea     rax, aVhdmpiioctlque_0; "VhdmpiIoctlQueueCancelWorkItem: canceli"...
0x14002fc66  mov     qword ptr [rsp+78h+var_50], rdi; char
0x14002fc6b  mov     edx, 1F2h; int
0x14002fc70  mov     [rsp+78h+var_58], rax; char *
0x14002fc75  mov     r9d, r13d; int
0x14002fc78  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002fc7f  mov     r8d, 4; int
0x14002fc85  call    TraceEvents
0x14002fc8a  mov     rdx, rdi
0x14002fc8d  mov     rcx, r15
0x14002fc90  call    VhdmpiCancelVirtualDiskRecoveryV2
0x14002fc95  lea     rcx, [r15+108h]; RunRef
0x14002fc9c  call    cs:__imp_ExReleaseRundownProtection
0x14002fca3  nop     dword ptr [rax+rax+00h]
0x14002fca8  xor     edx, edx; PriorityBoost
0x14002fcaa  mov     rcx, rdi; Irp
0x14002fcad  call    cs:__imp_IofCompleteRequest
0x14002fcb4  nop     dword ptr [rax+rax+00h]
0x14002fcb9  mov     rcx, r12; SpinLock
0x14002fcbc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002fcc3  nop     dword ptr [rax+rax+00h]
0x14002fcc8  mov     rbx, [r14]
0x14002fccb  mov     rcx, [rbx]
0x14002fcce  cmp     [rbx+8], r14
0x14002fcd2  jz      loc_14002FAA8
0x14002fcd8  mov     ecx, 3
0x14002fcdd  int     29h; Win8: RtlFailFast(ecx)
0x14002fcdf  mov     eax, cs:dword_1400876D0
0x14002fce5  cmp     eax, 5
0x14002fce8  jbe     short loc_14002FD23
0x14002fcea  mov     rdx, r13
0x14002fced  lea     rcx, dword_1400876D0
0x14002fcf4  call    _tlgKeywordOn
0x14002fcf9  test    al, al
0x14002fcfb  jz      short loc_14002FD23
0x14002fcfd  lea     rax, aVhdmpiioctlque; "VhdmpiIoctlQueueCancelWorkItem: leaving"...
0x14002fd04  mov     edx, 203h; int
0x14002fd09  mov     r9d, r13d; int
0x14002fd0c  mov     [rsp+78h+var_58], rax; char *
0x14002fd11  mov     r8d, 5; int
0x14002fd17  lea     rcx, aVhdmpiioctlque_2; "VhdmpiIoctlQueueCancelWorkItem"
0x14002fd1e  call    TraceEvents
0x14002fd23  add     rsp, 38h
0x14002fd27  pop     r15
0x14002fd29  pop     r14
0x14002fd2b  pop     r13
0x14002fd2d  pop     r12
0x14002fd2f  pop     rdi
0x14002fd30  pop     rsi
0x14002fd31  pop     rbp
0x14002fd32  pop     rbx
0x14002fd33  retn
```
