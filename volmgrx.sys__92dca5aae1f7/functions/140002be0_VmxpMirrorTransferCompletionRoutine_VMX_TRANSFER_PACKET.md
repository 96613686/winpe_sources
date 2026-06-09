# VmxpMirrorTransferCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x140002be0`
- end: `0x1400032c8`
- name: `?VmxpMirrorTransferCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `1768`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140002be0`
- `0x1400032d0`
- `0x140003774`
- `0x140003bd8`
- `0x140003f3c`
- `0x14000716c`
- `0x1400072ec`
- `0x140007828`
- `0x14000d078`
- `0x140010bb0`
- `0x140018fcc`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002c10`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002c89`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002dcc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002e3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002c10`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002c89`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002dcc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002e3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002cc9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e25`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ff8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000306b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003120`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000324b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002cc9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e25`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ff8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000306b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003120`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000324b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d38`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140002d7c`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140002fae`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140002d7c`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140002fae`

## pseudocode

```c
void __fastcall VmxpMirrorTransferCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v2; // rsi
  NTSTATUS v3; // r14d
  __int64 v4; // rbp
  KIRQL v5; // al
  KIRQL v6; // r12
  int v7; // edi
  char v8; // r14
  unsigned int v9; // edi
  _QWORD *v10; // r14
  __int64 v11; // rbx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  __int64 v13; // r8
  KIRQL v14; // al
  __int64 v15; // r9
  KIRQL v16; // r13
  __int64 v17; // r15
  KIRQL v18; // r15
  unsigned int v19; // edi
  __int64 v20; // r13
  __int64 v21; // rcx
  bool v22; // zf
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  unsigned int Member; // eax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  KIRQL v30; // al
  NTSTATUS v31; // edx
  NTSTATUS v32; // edx
  KIRQL v33; // al
  __int64 v34; // rdx
  __int64 v35; // rdi
  int v36; // edi
  NTSTATUS v37; // edx
  KIRQL v38; // [rsp+80h] [rbp+8h]

  v2 = *((_QWORD *)a1 + 28);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *((_QWORD *)a1 + 29);
  if ( !*((_BYTE *)a1 + 82) )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 88));
    if ( v3 >= 0 )
    {
      if ( *(int *)(v2 + 96) >= 0 )
        *(_QWORD *)(v2 + 104) = *((_QWORD *)a1 + 13);
      goto LABEL_10;
    }
    if ( v3 == -2147483626 )
    {
      v31 = *(_DWORD *)(v2 + 96);
      *(_QWORD *)(v2 + 104) = 0;
      if ( VmxpIsWorseStatus(-2147483626, v31) )
        *(_DWORD *)(v2 + 96) = -2147483626;
    }
    else
    {
      if ( !FsRtlIsTotalDeviceFailure(v3) && !*((_BYTE *)a1 + 272) )
      {
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
        {
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, v25, v4, v3);
        }
        if ( *((_QWORD *)a1 + 3) )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 88), v6);
          *((_BYTE *)a1 + 272) = 1;
          VMX_IO_MIRROR::RecoverWrite((VMX_IO_MIRROR *)v4, a1);
          return;
        }
        v32 = *(_DWORD *)(v2 + 96);
        *(_QWORD *)(v2 + 104) = 0;
        if ( !VmxpIsWorseStatus(v3, v32) )
          goto LABEL_10;
        goto LABEL_81;
      }
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 14, v25, v4, v3);
      }
      v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
      v34 = *((unsigned int *)a1 + 60);
      v38 = v33;
      v35 = *(_QWORD *)(v4 + 96) + 40 * v34;
      if ( *(_DWORD *)(v35 + 16) != 4 && VMX_IO_MIRROR::DetachFaultTolerantMember((VMX_IO_MIRROR *)v4, v34, 1u) )
        ++*(_DWORD *)(v2 + 168);
      v36 = *(_DWORD *)(v35 + 16);
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v38);
      if ( v36 != 4 )
      {
        v37 = *(_DWORD *)(v2 + 96);
        *(_QWORD *)(v2 + 104) = 0;
        if ( VmxpIsWorseStatus(v3, v37) )
LABEL_81:
          *(_DWORD *)(v2 + 96) = v3;
      }
    }
LABEL_10:
    v7 = --*(_DWORD *)(v2 + 128);
    v8 = *(_BYTE *)(v2 + 81);
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 88), v6);
    if ( v7 )
    {
      if ( (v8 & 8) != 0 )
      {
        v23 = *(_QWORD *)(*((_QWORD *)a1 + 31) + 8LL * (unsigned int)(*((_DWORD *)a1 + 65) + 1));
        v24 = *(_QWORD *)(v23 + 48);
        *(_QWORD *)(v23 + 40) = VmxpMirrorTransferCompletionRoutine;
        *(_DWORD *)(v23 + 12) = 16908289;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    else
    {
      if ( *((_DWORD *)a1 + 64) )
        goto LABEL_90;
      v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
      v19 = *((_DWORD *)a1 + 60) + 1;
      v20 = *(_QWORD *)(v4 + 96) + 40LL * v19;
      while ( v19 < *(_DWORD *)(v4 + 56) )
      {
        if ( (*(_DWORD *)(v20 + 16) & 0xFFFFFFFD) == 0 )
        {
          if ( !*(_BYTE *)(v20 + 20) )
          {
            *((_DWORD *)a1 + 60) = v19;
            ++*(_DWORD *)(v2 + 128);
            break;
          }
          if ( VMX_IO_MIRROR::DetachFaultTolerantMember((VMX_IO_MIRROR *)v4, v19, 1u) )
            ++*(_DWORD *)(v2 + 168);
        }
        ++v19;
        v20 += 40;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v18);
      if ( *(int *)(v2 + 128) <= 0 )
      {
LABEL_90:
        if ( *((_BYTE *)a1 + 274) )
          *(_OWORD *)(v2 + 96) = *(_OWORD *)((char *)a1 + 280);
        v9 = *((_DWORD *)a1 + 64);
        if ( v9 )
        {
          v10 = (_QWORD *)*((_QWORD *)a1 + 31);
          v11 = 0;
          do
          {
            v12 = (void (__fastcall ***)(_QWORD, __int64))v10[v11];
            if ( v12 )
              (**v12)(v12, 1);
            v11 = (unsigned int)(v11 + 1);
          }
          while ( (unsigned int)v11 < v9 );
          ExFreePoolWithTag(v10, 0);
        }
        else
        {
          VMX_IO_MIRROR::RecyclePacket((VMX_IO_MIRROR *)v4, a1);
        }
        if ( *(_DWORD *)(v2 + 168) )
        {
          *(_QWORD *)(v2 + 152) = VmxpMirrorLogDetachOperation;
          *(_QWORD *)(v2 + 160) = VmxpMirrorLogDetachCompletion;
          VMX_LOG::QueueLogPacket(*(VMX_LOG **)(v4 + 128), (struct VMX_LOG_TRANSFER_PACKET *)v2);
        }
        else
        {
          (*(void (__fastcall **)(__int64))(v2 + 40))(v2);
        }
      }
      else
      {
        v21 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8LL * *((unsigned int *)a1 + 60));
        *((_QWORD *)a1 + 5) = VmxpMirrorTransferCompletionRoutine;
        *((_QWORD *)a1 + 6) = v21;
        *((_DWORD *)a1 + 3) = 16908289;
        (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v21 + 8LL))(v21, a1);
      }
    }
    return;
  }
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
  --*(_DWORD *)(*(_QWORD *)(v4 + 96) + 40LL * *((unsigned int *)a1 + 60) + 28);
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v5);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147483626 && !*(_BYTE *)(v2 + 83) )
  {
    if ( FsRtlIsTotalDeviceFailure(v3) )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 12, v13, v4, v3);
      }
      v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
      v15 = *((unsigned int *)a1 + 60);
      v16 = v14;
      v17 = *(_QWORD *)(v4 + 96) + 40 * v15;
      if ( *(_DWORD *)(v17 + 16) == 4 )
        goto LABEL_91;
      if ( VMX_IO_MIRROR::DetachFaultTolerantMember((VMX_IO_MIRROR *)v4, v15, 1u) )
        ++*(_DWORD *)(v2 + 168);
      if ( *(_DWORD *)(v17 + 16) == 4 )
      {
LABEL_91:
        if ( !*((_BYTE *)a1 + 272) )
        {
          if ( *((_BYTE *)a1 + 274) )
            Member = VMX_IO_MIRROR::PickFirstMember((VMX_IO_MIRROR *)v4);
          else
            Member = VMX_IO_MIRROR::PickMemberUsingLoadBalancing((VMX_IO_MIRROR *)v4, *((_QWORD *)a1 + 2));
          *((_DWORD *)a1 + 60) = Member;
          v27 = 5LL * Member;
          v28 = *(_QWORD *)(v4 + 96);
          ++*(_DWORD *)(v28 + 8 * v27 + 28);
          *(_QWORD *)(v28 + 8 * v27 + 32) = *((_QWORD *)a1 + 2) + *((unsigned int *)a1 + 2);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v16);
        if ( !*((_BYTE *)a1 + 272) )
        {
          v29 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8LL * *((unsigned int *)a1 + 60));
          *((_QWORD *)a1 + 6) = v29;
          *((_DWORD *)a1 + 3) = 16842754;
          (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v29 + 8LL))(v29, a1);
          return;
        }
      }
      else
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v16);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 13, v13, v4, v3);
      }
      if ( !*((_BYTE *)a1 + 272) )
      {
        v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
        ++*(_DWORD *)(*(_QWORD *)(v4 + 96) + 40LL * *((unsigned int *)a1 + 60) + 28);
        KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v30);
        *((_BYTE *)a1 + 272) = 1;
        VMX_IO_MIRROR::RecoverRead((VMX_IO_MIRROR *)v4, a1);
        return;
      }
    }
  }
  if ( *((_BYTE *)a1 + 274) && v3 >= 0 )
  {
    VMX_IO_MIRROR::WriteBack((VMX_IO_MIRROR *)v4, a1);
  }
  else
  {
    v22 = *(_DWORD *)(v2 + 168) == 0;
    *(_OWORD *)(v2 + 96) = *((_OWORD *)a1 + 6);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(v2 + 40))(v2);
    }
    else
    {
      *(_QWORD *)(v2 + 152) = VmxpMirrorLogDetachOperation;
      *(_QWORD *)(v2 + 160) = VmxpMirrorLogDetachCompletion;
      VMX_LOG::QueueLogPacket(*(VMX_LOG **)(v4 + 128), (struct VMX_LOG_TRANSFER_PACKET *)v2);
    }
    VMX_IO_MIRROR::RecyclePacket((VMX_IO_MIRROR *)v4, a1);
  }
}

```

## disassembly

```asm
0x140002be0  push    rbx
0x140002be2  push    rbp
0x140002be3  push    rsi
0x140002be4  push    rdi
0x140002be5  push    r12
0x140002be7  push    r13
0x140002be9  push    r14
0x140002beb  push    r15
0x140002bed  sub     rsp, 38h
0x140002bf1  cmp     byte ptr [rcx+52h], 0
0x140002bf5  mov     rbx, rcx
0x140002bf8  mov     rsi, [rcx+0E0h]
0x140002bff  mov     r14d, [rcx+60h]
0x140002c03  mov     rbp, [rcx+0E8h]
0x140002c0a  jz      short loc_140002C85
0x140002c0c  lea     rcx, [rbp+18h]; SpinLock
0x140002c10  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002c17  nop     dword ptr [rax+rax+00h]
0x140002c1c  mov     ecx, [rbx+0F0h]
0x140002c22  lea     rdx, [rcx+rcx*4]
0x140002c26  mov     rcx, [rbp+60h]
0x140002c2a  dec     dword ptr [rcx+rdx*8+1Ch]
0x140002c2e  movzx   edx, al; NewIrql
0x140002c31  lea     rcx, [rbp+18h]; SpinLock
0x140002c35  call    cs:__imp_KeReleaseSpinLock
0x140002c3c  nop     dword ptr [rax+rax+00h]
0x140002c41  mov     ecx, 80000000h
0x140002c46  lea     eax, [r14+rcx]
0x140002c4a  test    ecx, eax
0x140002c4c  jz      loc_140002D62
0x140002c52  cmp     byte ptr [rbx+112h], 0
0x140002c59  jz      loc_140002EC0
0x140002c5f  test    r14d, r14d
0x140002c62  js      loc_140002EC0
0x140002c68  mov     rdx, rbx; struct VMX_MIRROR_TRANSFER_PACKET *
0x140002c6b  mov     rcx, rbp; this
0x140002c6e  call    ?WriteBack@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::WriteBack(VMX_MIRROR_TRANSFER_PACKET *)
0x140002c73  add     rsp, 38h
0x140002c77  pop     r15
0x140002c79  pop     r14
0x140002c7b  pop     r13
0x140002c7d  pop     r12
0x140002c7f  pop     rdi
0x140002c80  pop     rsi
0x140002c81  pop     rbp
0x140002c82  pop     rbx
0x140002c83  retn
0x140002c85  lea     rcx, [rsi+58h]; SpinLock
0x140002c89  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002c90  nop     dword ptr [rax+rax+00h]
0x140002c95  movzx   r12d, al
0x140002c99  test    r14d, r14d
0x140002c9c  js      loc_140002F9E
0x140002ca2  cmp     dword ptr [rsi+60h], 0
0x140002ca6  jl      short loc_140002CB0
0x140002ca8  mov     rcx, [rbx+68h]
0x140002cac  mov     [rsi+68h], rcx
0x140002cb0  dec     dword ptr [rsi+80h]
0x140002cb6  lea     rcx, [rsi+58h]; SpinLock
0x140002cba  mov     edi, [rsi+80h]
0x140002cc0  movzx   edx, r12b; NewIrql
0x140002cc4  movzx   r14d, byte ptr [rsi+51h]
0x140002cc9  call    cs:__imp_KeReleaseSpinLock
0x140002cd0  nop     dword ptr [rax+rax+00h]
0x140002cd5  test    edi, edi
0x140002cd7  jnz     loc_140002F4A
0x140002cdd  cmp     [rbx+100h], edi
0x140002ce3  jz      loc_140002E36
0x140002ce9  cmp     byte ptr [rbx+112h], 0
0x140002cf0  jz      short loc_140002CFD
0x140002cf2  movups  xmm0, xmmword ptr [rbx+118h]
0x140002cf9  movups  xmmword ptr [rsi+60h], xmm0
0x140002cfd  mov     edi, [rbx+100h]
0x140002d03  test    edi, edi
0x140002d05  jz      loc_140002F8E
0x140002d0b  mov     r14, [rbx+0F8h]
0x140002d12  xor     ebx, ebx
0x140002d14  mov     rcx, [r14+rbx*8]
0x140002d18  test    rcx, rcx
0x140002d1b  jz      short loc_140002D2D
0x140002d1d  mov     rax, [rcx]
0x140002d20  mov     edx, 1
0x140002d25  mov     rax, [rax]
0x140002d28  call    _guard_dispatch_icall
0x140002d2d  inc     ebx
0x140002d2f  cmp     ebx, edi
0x140002d31  jb      short loc_140002D14
0x140002d33  xor     edx, edx; Tag
0x140002d35  mov     rcx, r14; P
0x140002d38  call    cs:__imp_ExFreePoolWithTag
0x140002d3f  nop     dword ptr [rax+rax+00h]
0x140002d44  cmp     dword ptr [rsi+0A8h], 0
0x140002d4b  ja      loc_140002F1A
0x140002d51  mov     rax, [rsi+28h]
0x140002d55  mov     rcx, rsi
0x140002d58  call    _guard_dispatch_icall
0x140002d5d  jmp     loc_140002C73
0x140002d62  cmp     r14d, 80000016h
0x140002d69  jz      loc_140002C52
0x140002d6f  cmp     byte ptr [rsi+53h], 0
0x140002d73  jnz     loc_140002C52
0x140002d79  mov     ecx, r14d; Status
0x140002d7c  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140002d83  nop     dword ptr [rax+rax+00h]
0x140002d88  test    al, al
0x140002d8a  jz      loc_1400030B1
0x140002d90  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d97  lea     rax, WPP_GLOBAL_Control
0x140002d9e  cmp     rcx, rax
0x140002da1  jz      short loc_140002DC8
0x140002da3  test    dword ptr [rcx+2Ch], 1000h
0x140002daa  jz      short loc_140002DC8
0x140002dac  cmp     byte ptr [rcx+29h], 3
0x140002db0  jb      short loc_140002DC8
0x140002db2  mov     rcx, [rcx+18h]
0x140002db6  mov     edx, 0Ch
0x140002dbb  mov     r9, rbp
0x140002dbe  mov     [rsp+78h+var_58], r14d
0x140002dc3  call    WPP_SF_qd
0x140002dc8  lea     rcx, [rbp+18h]; SpinLock
0x140002dcc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002dd3  nop     dword ptr [rax+rax+00h]
0x140002dd8  mov     r9d, [rbx+0F0h]
0x140002ddf  movzx   r13d, al
0x140002de3  mov     rcx, [rbp+60h]
0x140002de7  lea     rdx, [r9+r9*4]
0x140002deb  cmp     dword ptr [rcx+rdx*8+10h], 4
0x140002df0  lea     r15, [rcx+rdx*8]
0x140002df4  jz      loc_14000301B
0x140002dfa  mov     r8b, 1; unsigned __int8
0x140002dfd  mov     edx, r9d; unsigned int
0x140002e00  mov     rcx, rbp; this
0x140002e03  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x140002e08  test    al, al
0x140002e0a  jz      short loc_140002E12
0x140002e0c  inc     dword ptr [rsi+0A8h]
0x140002e12  cmp     dword ptr [r15+10h], 4
0x140002e17  jz      loc_14000301B
0x140002e1d  movzx   edx, r13b; NewIrql
0x140002e21  lea     rcx, [rbp+18h]; SpinLock
0x140002e25  call    cs:__imp_KeReleaseSpinLock
0x140002e2c  nop     dword ptr [rax+rax+00h]
0x140002e31  jmp     loc_140002C52
0x140002e36  lea     rcx, [rbp+18h]; SpinLock
0x140002e3a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002e41  nop     dword ptr [rax+rax+00h]
0x140002e46  mov     edi, [rbx+0F0h]
0x140002e4c  movzx   r15d, al
0x140002e50  mov     rcx, [rbp+60h]
0x140002e54  inc     edi
0x140002e56  lea     rdx, [rdi+rdi*4]
0x140002e5a  lea     r13, [rcx+rdx*8]
0x140002e5e  cmp     edi, [rbp+38h]
0x140002e61  jb      loc_140003284
0x140002e67  movzx   edx, r15b; NewIrql
0x140002e6b  lea     rcx, [rbp+18h]; SpinLock
0x140002e6f  call    cs:__imp_KeReleaseSpinLock
0x140002e76  nop     dword ptr [rax+rax+00h]
0x140002e7b  cmp     dword ptr [rsi+80h], 0
0x140002e82  jle     loc_140002CE9
0x140002e88  mov     rax, [rbp+30h]
0x140002e8c  mov     rdx, rbx
0x140002e8f  mov     ecx, [rbx+0F0h]
0x140002e95  mov     rcx, [rax+rcx*8]
0x140002e99  lea     rax, ?VmxpMirrorTransferCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorTransferCompletionRoutine(VMX_TRANSFER_PACKET *)
0x140002ea0  mov     [rbx+28h], rax
0x140002ea4  mov     [rbx+30h], rcx
0x140002ea8  mov     dword ptr [rbx+0Ch], 1020001h
0x140002eaf  mov     rax, [rcx]
0x140002eb2  mov     rax, [rax+8]
0x140002eb6  call    _guard_dispatch_icall
0x140002ebb  jmp     loc_140002C73
0x140002ec0  cmp     dword ptr [rsi+0A8h], 0
0x140002ec7  movups  xmm0, xmmword ptr [rbx+60h]
0x140002ecb  movups  xmmword ptr [rsi+60h], xmm0
0x140002ecf  jbe     short loc_140002F0C
0x140002ed1  lea     rax, ?VmxpMirrorLogDetachOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpMirrorLogDetachOperation(VMX_LOG_TRANSFER_PACKET *)
0x140002ed8  mov     rdx, rsi; struct VMX_LOG_TRANSFER_PACKET *
0x140002edb  mov     [rsi+98h], rax
0x140002ee2  lea     rax, ?VmxpMirrorLogDetachCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpMirrorLogDetachCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x140002ee9  mov     [rsi+0A0h], rax
0x140002ef0  mov     rcx, [rbp+80h]; this
0x140002ef7  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x140002efc  mov     rdx, rbx; struct VMX_MIRROR_TRANSFER_PACKET *
0x140002eff  mov     rcx, rbp; this
0x140002f02  call    ?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)
0x140002f07  jmp     loc_140002C73
0x140002f0c  mov     rax, [rsi+28h]
0x140002f10  mov     rcx, rsi
0x140002f13  call    _guard_dispatch_icall
0x140002f18  jmp     short loc_140002EFC
0x140002f1a  lea     rax, ?VmxpMirrorLogDetachOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpMirrorLogDetachOperation(VMX_LOG_TRANSFER_PACKET *)
0x140002f21  mov     rdx, rsi; struct VMX_LOG_TRANSFER_PACKET *
0x140002f24  mov     [rsi+98h], rax
0x140002f2b  lea     rax, ?VmxpMirrorLogDetachCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpMirrorLogDetachCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x140002f32  mov     [rsi+0A0h], rax
0x140002f39  mov     rcx, [rbp+80h]; this
0x140002f40  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x140002f45  jmp     loc_140002C73
0x140002f4a  test    r14b, 8
0x140002f4e  jz      loc_140002C73
0x140002f54  mov     ecx, [rbx+104h]
0x140002f5a  mov     rax, [rbx+0F8h]
0x140002f61  inc     ecx
0x140002f63  mov     rdx, [rax+rcx*8]
0x140002f67  lea     rax, ?VmxpMirrorTransferCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorTransferCompletionRoutine(VMX_TRANSFER_PACKET *)
0x140002f6e  mov     rcx, [rdx+30h]
0x140002f72  mov     [rdx+28h], rax
0x140002f76  mov     dword ptr [rdx+0Ch], 1020001h
0x140002f7d  mov     rax, [rcx]
0x140002f80  mov     rax, [rax+8]
0x140002f84  call    _guard_dispatch_icall
0x140002f89  jmp     loc_140002C73
0x140002f8e  mov     rdx, rbx; struct VMX_MIRROR_TRANSFER_PACKET *
0x140002f91  mov     rcx, rbp; this
0x140002f94  call    ?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)
0x140002f99  jmp     loc_140002D44
0x140002f9e  cmp     r14d, 80000016h
0x140002fa5  jz      loc_140003143
0x140002fab  mov     ecx, r14d; Status
0x140002fae  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140002fb5  nop     dword ptr [rax+rax+00h]
0x140002fba  test    al, al
0x140002fbc  jnz     loc_1400031BE
0x140002fc2  cmp     [rbx+110h], al
0x140002fc8  jnz     loc_1400031BE
0x140002fce  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fd5  lea     rax, WPP_GLOBAL_Control
0x140002fdc  cmp     rcx, rax
0x140002fdf  jnz     loc_14000316C
0x140002fe5  cmp     qword ptr [rbx+18h], 0
0x140002fea  jz      loc_14000319E
0x140002ff0  movzx   edx, r12b; NewIrql
0x140002ff4  lea     rcx, [rsi+58h]; SpinLock
0x140002ff8  call    cs:__imp_KeReleaseSpinLock
0x140002fff  nop     dword ptr [rax+rax+00h]
0x140003004  mov     rdx, rbx; struct VMX_MIRROR_TRANSFER_PACKET *
0x140003007  mov     byte ptr [rbx+110h], 1
0x14000300e  mov     rcx, rbp; this
0x140003011  call    ?RecoverWrite@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecoverWrite(VMX_MIRROR_TRANSFER_PACKET *)
0x140003016  jmp     loc_140002C73
0x14000301b  cmp     byte ptr [rbx+110h], 0
0x140003022  jnz     short loc_140003063
0x140003024  cmp     byte ptr [rbx+112h], 0
0x14000302b  mov     rcx, rbp; this
0x14000302e  jz      short loc_140003037
0x140003030  call    ?PickFirstMember@VMX_IO_MIRROR@@QEAAKXZ; VMX_IO_MIRROR::PickFirstMember(void)
0x140003035  jmp     short loc_140003040
0x140003037  mov     rdx, [rbx+10h]; unsigned __int64
0x14000303b  call    ?PickMemberUsingLoadBalancing@VMX_IO_MIRROR@@QEAAK_K@Z; VMX_IO_MIRROR::PickMemberUsingLoadBalancing(unsigned __int64)
0x140003040  mov     [rbx+0F0h], eax
0x140003046  mov     eax, eax
0x140003048  lea     rdx, [rax+rax*4]
0x14000304c  mov     rax, [rbp+60h]
0x140003050  inc     dword ptr [rax+rdx*8+1Ch]
0x140003054  lea     r8, [rax+rdx*8]
0x140003058  mov     eax, [rbx+8]
0x14000305b  add     rax, [rbx+10h]
0x14000305f  mov     [r8+20h], rax
0x140003063  movzx   edx, r13b; NewIrql
0x140003067  lea     rcx, [rbp+18h]; SpinLock
0x14000306b  call    cs:__imp_KeReleaseSpinLock
0x140003072  nop     dword ptr [rax+rax+00h]
0x140003077  cmp     byte ptr [rbx+110h], 0
0x14000307e  jnz     loc_140002C52
0x140003084  mov     rax, [rbp+30h]
0x140003088  mov     rdx, rbx
0x14000308b  mov     ecx, [rbx+0F0h]
0x140003091  mov     rcx, [rax+rcx*8]
0x140003095  mov     [rbx+30h], rcx
0x140003099  mov     dword ptr [rbx+0Ch], 1010002h
0x1400030a0  mov     rax, [rcx]
0x1400030a3  mov     rax, [rax+8]
0x1400030a7  call    _guard_dispatch_icall
0x1400030ac  jmp     loc_140002C73
0x1400030b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030b8  lea     rax, WPP_GLOBAL_Control
0x1400030bf  cmp     rcx, rax
0x1400030c2  jz      short loc_1400030E9
0x1400030c4  test    dword ptr [rcx+2Ch], 1000h
0x1400030cb  jz      short loc_1400030E9
0x1400030cd  cmp     byte ptr [rcx+29h], 3
0x1400030d1  jb      short loc_1400030E9
0x1400030d3  mov     rcx, [rcx+18h]
0x1400030d7  mov     edx, 0Dh
0x1400030dc  mov     r9, rbp
0x1400030df  mov     [rsp+78h+var_58], r14d
0x1400030e4  call    WPP_SF_qd
0x1400030e9  cmp     byte ptr [rbx+110h], 0
0x1400030f0  jnz     loc_140002C52
0x1400030f6  lea     rcx, [rbp+18h]; SpinLock
0x1400030fa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003101  nop     dword ptr [rax+rax+00h]
0x140003106  mov     edx, [rbx+0F0h]
0x14000310c  lea     rcx, [rbp+18h]; SpinLock
0x140003110  lea     r8, [rdx+rdx*4]
0x140003114  mov     rdx, [rbp+60h]
0x140003118  inc     dword ptr [rdx+r8*8+1Ch]
0x14000311d  movzx   edx, al; NewIrql
0x140003120  call    cs:__imp_KeReleaseSpinLock
  ... truncated ...
```
