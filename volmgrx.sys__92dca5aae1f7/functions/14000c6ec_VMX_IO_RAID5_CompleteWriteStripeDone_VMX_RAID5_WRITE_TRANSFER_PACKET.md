# VMX_IO_RAID5::CompleteWriteStripeDone(VMX_RAID5_WRITE_TRANSFER_PACKET *)

- ea: `0x14000c6ec`
- end: `0x14000cb26`
- name: `?CompleteWriteStripeDone@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_WRITE_TRANSFER_PACKET@@@Z`
- size: `1082`
- prototype: `void __fastcall(VMX_IO_RAID5 *__hidden this, struct VMX_RAID5_WRITE_TRANSFER_PACKET *)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000c648`
- `0x140014410`
- `0x140014490`

## callees

- `0x140007828`
- `0x1400087d0`
- `0x14000c6ec`
- `0x14000d0dc`
- `0x140012560`
- `0x140018f64`
- `0x140018fcc`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c799`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c92f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ca3b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000caa6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c799`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c92f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ca3b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000caa6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c7e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c97c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ca88`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000caf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c7e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c97c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ca88`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000caf3`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000c7fa`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000c994`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000c7fa`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000c994`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c844`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c879`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c844`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c879`

## pseudocode

```c
void __fastcall VMX_IO_RAID5::CompleteWriteStripeDone(
        KSPIN_LOCK *this,
        struct VMX_RAID5_WRITE_TRANSFER_PACKET *a2,
        __int64 a3)
{
  char *v3; // rsi
  NTSTATUS v4; // r12d
  char *v5; // rbp
  NTSTATUS v6; // r15d
  void (__fastcall *v9)(struct VMX_RAID5_WRITE_TRANSFER_PACKET *); // rax
  char v10; // r12
  KIRQL v11; // al
  __int64 v12; // rdx
  KIRQL v13; // r11
  __int128 v14; // xmm0
  __int64 v15; // rcx
  PVOID v16; // rbx
  __int64 v17; // r10
  PVOID v18; // rax
  __int64 v19; // rcx
  char v20; // di
  KIRQL v21; // al
  __int64 v22; // rdx
  KIRQL v23; // r11
  KIRQL v24; // al
  __int64 v25; // rdx
  KIRQL v26; // r11
  KIRQL v27; // al
  __int64 v28; // rdx
  KIRQL v29; // r11
  void (__fastcall *v30)(struct VMX_RAID5_WRITE_TRANSFER_PACKET *); // rax

  v3 = (char *)a2 + 296;
  v4 = *((_DWORD *)a2 + 98);
  v5 = (char *)a2 + 568;
  v6 = *((_DWORD *)a2 + 166);
  if ( v4 < 0 )
  {
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_ddq(*((_QWORD *)WPP_GLOBAL_Control + 3), a2, a3, (unsigned int)v4, v6, this);
      }
      if ( *((_DWORD *)a2 + 72) != 4 && (!*((_QWORD *)v5 + 6) || VmxpIsWorseStatus(v4, v6)) )
      {
        if ( v4 != -2147483626 )
        {
          v24 = KeAcquireSpinLockRaiseToDpc(this + 3);
          v25 = *((unsigned int *)v3 + 60);
          v26 = v24;
          if ( *(_DWORD *)(this[14] + 24 * v25 + 16) != 4
            && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)this, v25, 1) )
          {
            ++*(_DWORD *)(*((_QWORD *)a2 + 32) + 168LL);
          }
          KeReleaseSpinLock(this + 3, v26);
        }
LABEL_17:
        v14 = *((_OWORD *)v3 + 6);
LABEL_58:
        v30 = (void (__fastcall *)(struct VMX_RAID5_WRITE_TRANSFER_PACKET *))*((_QWORD *)a2 + 5);
        *((_OWORD *)a2 + 6) = v14;
        v30(a2);
        return;
      }
      if ( v6 != -2147483626 )
      {
        v27 = KeAcquireSpinLockRaiseToDpc(this + 3);
        v28 = *((unsigned int *)a2 + 192);
        v29 = v27;
        if ( *(_DWORD *)(this[14] + 24 * v28 + 16) != 4
          && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)this, v28, 1) )
        {
          ++*(_DWORD *)(*((_QWORD *)a2 + 32) + 168LL);
        }
        KeReleaseSpinLock(this + 3, v29);
      }
    }
    else
    {
      if ( *((_DWORD *)a2 + 72) != 4
        && WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 31, a3, this, v4);
      }
      if ( v4 == -2147483626 )
        goto LABEL_39;
      if ( *((_DWORD *)a2 + 72) != 4 )
      {
        v20 = 1;
        v21 = KeAcquireSpinLockRaiseToDpc(this + 3);
        v22 = *((unsigned int *)v3 + 60);
        v23 = v21;
        if ( *(_DWORD *)(this[14] + 24 * v22 + 16) != 4 )
        {
          if ( VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)this, v22, 1) )
            ++*(_DWORD *)(*((_QWORD *)a2 + 32) + 168LL);
          else
            v20 = 0;
        }
        KeReleaseSpinLock(this + 3, v23);
        if ( !v20 )
        {
          if ( FsRtlIsTotalDeviceFailure(v4) )
          {
LABEL_39:
            *((_OWORD *)a2 + 6) = *((_OWORD *)v3 + 6);
            *((_QWORD *)v5 + 5) = VmxpRaid5CompleteWriteStripeDonePhase2;
            VMX_PARITY_IO_MANAGER::UpdateParity(
              (VMX_PARITY_IO_MANAGER *)(this + 20),
              (struct VMX_RAID5_PARITY_TRANSFER_PACKET *)v5);
            return;
          }
        }
      }
    }
    v14 = *((_OWORD *)v5 + 6);
    goto LABEL_58;
  }
  if ( v6 >= 0 )
  {
    v9 = (void (__fastcall *)(struct VMX_RAID5_WRITE_TRANSFER_PACKET *))*((_QWORD *)a2 + 5);
    *((_OWORD *)a2 + 6) = *(_OWORD *)((char *)a2 + 392);
    v9(a2);
    return;
  }
  if ( *((_QWORD *)a2 + 77)
    && WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 30, a3, this, v6);
  }
  if ( v6 != -2147483626 )
  {
    if ( !*((_QWORD *)v5 + 6) )
      goto LABEL_17;
    v10 = 1;
    v11 = KeAcquireSpinLockRaiseToDpc(this + 3);
    v12 = *((unsigned int *)a2 + 192);
    v13 = v11;
    if ( *(_DWORD *)(this[14] + 24 * v12 + 16) != 4 )
    {
      if ( VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)this, v12, 1) )
        ++*(_DWORD *)(*((_QWORD *)a2 + 32) + 168LL);
      else
        v10 = 0;
    }
    KeReleaseSpinLock(this + 3, v13);
    if ( v10 || !FsRtlIsTotalDeviceFailure(v6) )
      goto LABEL_17;
  }
  *((_OWORD *)a2 + 6) = *((_OWORD *)v5 + 6);
  v15 = *((_QWORD *)v3 + 3);
  if ( (*(_BYTE *)(v15 + 10) & 5) != 0 )
    v16 = *(PVOID *)(v15 + 24);
  else
    v16 = MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000010u);
  v17 = *((_QWORD *)v5 + 3);
  if ( (*(_BYTE *)(v17 + 10) & 5) != 0 )
    v18 = *(PVOID *)(v17 + 24);
  else
    v18 = MmMapLockedPagesSpecifyCache((PMDL)v17, 0, MmCached, 0, 0, 0x40000010u);
  VmxpComputeParity(v16, v18, *((_DWORD *)v3 + 2));
  v19 = *((_QWORD *)v3 + 6);
  *((_QWORD *)v3 + 5) = VmxpRaid5CompleteWriteStripeDonePhase1;
  v3[82] = 0;
  *((_DWORD *)v3 + 3) = 33685519;
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v19 + 8LL))(v19, v3);
}

```

## disassembly

```asm
0x14000c6ec  push    rbx
0x14000c6ee  push    rbp
0x14000c6ef  push    rsi
0x14000c6f0  push    rdi
0x14000c6f1  push    r12
0x14000c6f3  push    r13
0x14000c6f5  push    r14
0x14000c6f7  push    r15
0x14000c6f9  sub     rsp, 38h
0x14000c6fd  lea     rsi, [rdx+128h]
0x14000c704  xor     r13d, r13d
0x14000c707  mov     r12d, [rsi+60h]
0x14000c70b  lea     rbp, [rdx+238h]
0x14000c712  mov     r15d, [rbp+60h]
0x14000c716  mov     rbx, rdx
0x14000c719  mov     r14, rcx
0x14000c71c  test    r12d, r12d
0x14000c71f  js      loc_14000C8C2
0x14000c725  test    r15d, r15d
0x14000c728  js      short loc_14000C73C
0x14000c72a  movups  xmm0, xmmword ptr [rsi+60h]
0x14000c72e  mov     rax, [rdx+28h]
0x14000c732  movdqu  xmmword ptr [rdx+60h], xmm0
0x14000c737  jmp     loc_14000CB0C
0x14000c73c  cmp     [rbp+30h], r13
0x14000c740  jz      short loc_14000C77A
0x14000c742  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c749  lea     rax, WPP_GLOBAL_Control
0x14000c750  cmp     rcx, rax
0x14000c753  jz      short loc_14000C77A
0x14000c755  test    dword ptr [rcx+2Ch], 1000h
0x14000c75c  jz      short loc_14000C77A
0x14000c75e  cmp     byte ptr [rcx+29h], 3
0x14000c762  jb      short loc_14000C77A
0x14000c764  mov     rcx, [rcx+18h]
0x14000c768  mov     edx, 1Eh
0x14000c76d  mov     r9, r14
0x14000c770  mov     [rsp+78h+BugCheckOnFailure], r15d
0x14000c775  call    WPP_SF_qd
0x14000c77a  mov     edi, 1
0x14000c77f  cmp     r15d, 80000016h
0x14000c786  jz      loc_14000C813
0x14000c78c  cmp     [rbp+30h], r13
0x14000c790  jz      short loc_14000C80A
0x14000c792  lea     rcx, [r14+18h]; SpinLock
0x14000c796  mov     r12b, dil
0x14000c799  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c7a0  nop     dword ptr [rax+rax+00h]
0x14000c7a5  mov     edx, [rbx+300h]; unsigned int
0x14000c7ab  mov     r11b, al
0x14000c7ae  mov     rcx, [r14+70h]
0x14000c7b2  lea     r8, [rdx+rdx*2]
0x14000c7b6  cmp     dword ptr [rcx+r8*8+10h], 4
0x14000c7bc  jz      short loc_14000C7DF
0x14000c7be  mov     r8b, dil; unsigned __int8
0x14000c7c1  mov     rcx, r14; this
0x14000c7c4  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x14000c7c9  test    al, al
0x14000c7cb  jz      short loc_14000C7DC
0x14000c7cd  mov     rax, [rbx+100h]
0x14000c7d4  add     [rax+0A8h], edi
0x14000c7da  jmp     short loc_14000C7DF
0x14000c7dc  xor     r12b, r12b
0x14000c7df  mov     dl, r11b; NewIrql
0x14000c7e2  lea     rcx, [r14+18h]; SpinLock
0x14000c7e6  call    cs:__imp_KeReleaseSpinLock
0x14000c7ed  nop     dword ptr [rax+rax+00h]
0x14000c7f2  test    r12b, r12b
0x14000c7f5  jnz     short loc_14000C80A
0x14000c7f7  mov     ecx, r15d; Status
0x14000c7fa  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x14000c801  nop     dword ptr [rax+rax+00h]
0x14000c806  test    al, al
0x14000c808  jnz     short loc_14000C813
0x14000c80a  movups  xmm0, xmmword ptr [rsi+60h]
0x14000c80e  jmp     loc_14000CB03
0x14000c813  movups  xmm0, xmmword ptr [rbp+60h]
0x14000c817  mov     r14d, 40000010h
0x14000c81d  movdqu  xmmword ptr [rbx+60h], xmm0
0x14000c822  mov     rcx, [rsi+18h]; MemoryDescriptorList
0x14000c826  test    byte ptr [rcx+0Ah], 5
0x14000c82a  jz      short loc_14000C832
0x14000c82c  mov     rbx, [rcx+18h]
0x14000c830  jmp     short loc_14000C853
0x14000c832  mov     [rsp+78h+Priority], r14d; Priority
0x14000c837  xor     r9d, r9d; RequestedAddress
0x14000c83a  mov     r8d, edi; CacheType
0x14000c83d  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14000c842  xor     edx, edx; AccessMode
0x14000c844  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000c84b  nop     dword ptr [rax+rax+00h]
0x14000c850  mov     rbx, rax
0x14000c853  mov     r10, [rbp+18h]
0x14000c857  test    byte ptr [r10+0Ah], 5
0x14000c85c  jz      short loc_14000C864
0x14000c85e  mov     rax, [r10+18h]
0x14000c862  jmp     short loc_14000C885
0x14000c864  mov     [rsp+78h+Priority], r14d; Priority
0x14000c869  xor     r9d, r9d; RequestedAddress
0x14000c86c  mov     r8d, edi; CacheType
0x14000c86f  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14000c874  xor     edx, edx; AccessMode
0x14000c876  mov     rcx, r10; MemoryDescriptorList
0x14000c879  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000c880  nop     dword ptr [rax+rax+00h]
0x14000c885  mov     r8d, [rsi+8]; unsigned int
0x14000c889  mov     rdx, rax; void *
0x14000c88c  mov     rcx, rbx; void *
0x14000c88f  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x14000c894  mov     rcx, [rsi+30h]
0x14000c898  lea     rax, ?VmxpRaid5CompleteWriteStripeDonePhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5CompleteWriteStripeDonePhase1(VMX_TRANSFER_PACKET *)
0x14000c89f  mov     [rsi+28h], rax
0x14000c8a3  mov     rdx, rsi
0x14000c8a6  mov     [rsi+52h], r13b
0x14000c8aa  mov     dword ptr [rsi+0Ch], 202000Fh
0x14000c8b1  mov     rax, [rcx]
0x14000c8b4  mov     rax, [rax+8]
0x14000c8b8  call    _guard_dispatch_icall
0x14000c8bd  jmp     loc_14000CB14
0x14000c8c2  test    r15d, r15d
0x14000c8c5  js      loc_14000C9D0
0x14000c8cb  cmp     dword ptr [rdx+120h], 4
0x14000c8d2  jz      short loc_14000C90C
0x14000c8d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c8db  lea     rax, WPP_GLOBAL_Control
0x14000c8e2  cmp     rcx, rax
0x14000c8e5  jz      short loc_14000C90C
0x14000c8e7  test    dword ptr [rcx+2Ch], 1000h
0x14000c8ee  jz      short loc_14000C90C
0x14000c8f0  cmp     byte ptr [rcx+29h], 3
0x14000c8f4  jb      short loc_14000C90C
0x14000c8f6  mov     rcx, [rcx+18h]
0x14000c8fa  mov     edx, 1Fh
0x14000c8ff  mov     r9, r14
0x14000c902  mov     [rsp+78h+BugCheckOnFailure], r12d
0x14000c907  call    WPP_SF_qd
0x14000c90c  cmp     r12d, 80000016h
0x14000c913  jz      loc_14000C9A8
0x14000c919  cmp     dword ptr [rbx+120h], 4
0x14000c920  jz      loc_14000CAFF
0x14000c926  lea     rcx, [r14+18h]; SpinLock
0x14000c92a  mov     edi, 1
0x14000c92f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c936  nop     dword ptr [rax+rax+00h]
0x14000c93b  mov     edx, [rsi+0F0h]; unsigned int
0x14000c941  mov     r11b, al
0x14000c944  mov     rcx, [r14+70h]
0x14000c948  lea     r8, [rdx+rdx*2]
0x14000c94c  cmp     dword ptr [rcx+r8*8+10h], 4
0x14000c952  jz      short loc_14000C975
0x14000c954  mov     r8b, dil; unsigned __int8
0x14000c957  mov     rcx, r14; this
0x14000c95a  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x14000c95f  test    al, al
0x14000c961  jz      short loc_14000C972
0x14000c963  mov     rax, [rbx+100h]
0x14000c96a  add     [rax+0A8h], edi
0x14000c970  jmp     short loc_14000C975
0x14000c972  mov     dil, r13b
0x14000c975  mov     dl, r11b; NewIrql
0x14000c978  lea     rcx, [r14+18h]; SpinLock
0x14000c97c  call    cs:__imp_KeReleaseSpinLock
0x14000c983  nop     dword ptr [rax+rax+00h]
0x14000c988  test    dil, dil
0x14000c98b  jnz     loc_14000CAFF
0x14000c991  mov     ecx, r12d; Status
0x14000c994  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x14000c99b  nop     dword ptr [rax+rax+00h]
0x14000c9a0  test    al, al
0x14000c9a2  jz      loc_14000CAFF
0x14000c9a8  movups  xmm0, xmmword ptr [rsi+60h]
0x14000c9ac  lea     rax, ?VmxpRaid5CompleteWriteStripeDonePhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5CompleteWriteStripeDonePhase2(VMX_TRANSFER_PACKET *)
0x14000c9b3  mov     rdx, rbp; struct VMX_RAID5_PARITY_TRANSFER_PACKET *
0x14000c9b6  lea     rcx, [r14+0A0h]; this
0x14000c9bd  movdqu  xmmword ptr [rbx+60h], xmm0
0x14000c9c2  mov     [rbp+28h], rax
0x14000c9c6  call    ?UpdateParity@VMX_PARITY_IO_MANAGER@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z; VMX_PARITY_IO_MANAGER::UpdateParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)
0x14000c9cb  jmp     loc_14000CB14
0x14000c9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c9d7  lea     rax, WPP_GLOBAL_Control
0x14000c9de  cmp     rcx, rax
0x14000c9e1  jz      short loc_14000CA08
0x14000c9e3  test    dword ptr [rcx+2Ch], 1000h
0x14000c9ea  jz      short loc_14000CA08
0x14000c9ec  cmp     byte ptr [rcx+29h], 3
0x14000c9f0  jb      short loc_14000CA08
0x14000c9f2  mov     rcx, [rcx+18h]
0x14000c9f6  mov     r9d, r12d
0x14000c9f9  mov     qword ptr [rsp+78h+Priority], r14
0x14000c9fe  mov     [rsp+78h+BugCheckOnFailure], r15d
0x14000ca03  call    WPP_SF_ddq
0x14000ca08  cmp     dword ptr [rbx+120h], 4
0x14000ca0f  jz      loc_14000CA99
0x14000ca15  cmp     [rbp+30h], r13
0x14000ca19  jz      short loc_14000CA2A
0x14000ca1b  mov     edx, r15d; NTSTATUS
0x14000ca1e  mov     ecx, r12d; Status
0x14000ca21  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x14000ca26  test    al, al
0x14000ca28  jz      short loc_14000CA99
0x14000ca2a  cmp     r12d, 80000016h
0x14000ca31  jz      loc_14000C80A
0x14000ca37  lea     rcx, [r14+18h]; SpinLock
0x14000ca3b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ca42  nop     dword ptr [rax+rax+00h]
0x14000ca47  mov     edx, [rsi+0F0h]; unsigned int
0x14000ca4d  mov     r11b, al
0x14000ca50  mov     rcx, [r14+70h]
0x14000ca54  lea     r8, [rdx+rdx*2]
0x14000ca58  cmp     dword ptr [rcx+r8*8+10h], 4
0x14000ca5e  jz      short loc_14000CA81
0x14000ca60  mov     edi, 1
0x14000ca65  mov     rcx, r14; this
0x14000ca68  mov     r8b, dil; unsigned __int8
0x14000ca6b  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x14000ca70  test    al, al
0x14000ca72  jz      short loc_14000CA81
0x14000ca74  mov     rax, [rbx+100h]
0x14000ca7b  add     [rax+0A8h], edi
0x14000ca81  mov     dl, r11b; NewIrql
0x14000ca84  lea     rcx, [r14+18h]; SpinLock
0x14000ca88  call    cs:__imp_KeReleaseSpinLock
0x14000ca8f  nop     dword ptr [rax+rax+00h]
0x14000ca94  jmp     loc_14000C80A
0x14000ca99  cmp     r15d, 80000016h
0x14000caa0  jz      short loc_14000CAFF
0x14000caa2  lea     rcx, [r14+18h]; SpinLock
0x14000caa6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000caad  nop     dword ptr [rax+rax+00h]
0x14000cab2  mov     edx, [rbx+300h]; unsigned int
0x14000cab8  mov     r11b, al
0x14000cabb  mov     rcx, [r14+70h]
0x14000cabf  lea     r8, [rdx+rdx*2]
0x14000cac3  cmp     dword ptr [rcx+r8*8+10h], 4
0x14000cac9  jz      short loc_14000CAEC
0x14000cacb  mov     edi, 1
0x14000cad0  mov     rcx, r14; this
0x14000cad3  mov     r8b, dil; unsigned __int8
0x14000cad6  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x14000cadb  test    al, al
0x14000cadd  jz      short loc_14000CAEC
0x14000cadf  mov     rax, [rbx+100h]
0x14000cae6  add     [rax+0A8h], edi
0x14000caec  mov     dl, r11b; NewIrql
0x14000caef  lea     rcx, [r14+18h]; SpinLock
0x14000caf3  call    cs:__imp_KeReleaseSpinLock
0x14000cafa  nop     dword ptr [rax+rax+00h]
0x14000caff  movups  xmm0, xmmword ptr [rbp+60h]
0x14000cb03  mov     rax, [rbx+28h]
0x14000cb07  movdqu  xmmword ptr [rbx+60h], xmm0
0x14000cb0c  mov     rcx, rbx
0x14000cb0f  call    _guard_dispatch_icall
0x14000cb14  add     rsp, 38h
0x14000cb18  pop     r15
0x14000cb1a  pop     r14
0x14000cb1c  pop     r13
0x14000cb1e  pop     r12
0x14000cb20  pop     rdi
0x14000cb21  pop     rsi
0x14000cb22  pop     rbp
0x14000cb23  pop     rbx
0x14000cb24  retn
```
