# Smb2LeaseDecrementOpensInProgressAndCloseIfUnused

- ea: `0x14000ca00`
- end: `0x14000cde4`
- name: `Smb2LeaseDecrementOpensInProgressAndCloseIfUnused`
- size: `996`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1400760e0`
- `0x140079c30`
- `0x140085d40`

## callees

- `0x140004960`
- `0x140005070`
- `0x14000ca00`
- `0x14000e140`
- `0x14000e340`
- `0x140021b20`
- `0x1400222ec`
- `0x140091cc0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000cd29`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000cd29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ca17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cae7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ca17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cae7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cdba`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cdba`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cb40`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cccc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cb40`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cccc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000cd44`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000cd44`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ccb3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ccb3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cca0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cca0`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000cbe4`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000cbe4`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000cc37`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000cc37`

## string_xrefs

- `0x14000cd0a`: `Srv2PostToThreadPool`

## pseudocode

```c
void __fastcall Smb2LeaseDecrementOpensInProgressAndCloseIfUnused(__int64 a1, __int64 a2, char a3)
{
  KIRQL v5; // al
  bool v6; // zf
  KIRQL v7; // si
  int v8; // ecx
  __int64 v9; // rbp
  __int64 v10; // r14
  KIRQL v11; // al
  _QWORD *v12; // rdx
  KIRQL v13; // r9
  __int64 v14; // r8
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  __int64 v17; // rsi
  KIRQL v18; // r15
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  signed __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rdi
  __int64 v24; // rdx

  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v6 = (*(_DWORD *)(a1 + 172))-- == 1;
  v7 = v5;
  if ( !v6 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v5);
    return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, a1);
  }
  v8 = *(_DWORD *)(a1 + 12);
  if ( v8 == 221 || *(_QWORD *)(a1 + 152) != a1 + 152 || *(_DWORD *)(a1 + 172) )
  {
    Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(a1, v7);
    return;
  }
  if ( v8 == 224 )
    Smb2CancelQueuedDelayedLease(a1);
  *(_DWORD *)(a1 + 12) = 221;
  *(_BYTE *)(a1 + 128) = 1;
  if ( a3 )
    *(_DWORD *)(a1 + 140) |= 4u;
  v9 = *(_QWORD *)(a1 + 112);
  v10 = *(_QWORD *)(a1 + 200);
  *(_QWORD *)(a1 + 112) = 0;
  _InterlockedIncrement(&dword_14004B384);
  Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(a1, v7);
  v11 = KeAcquireSpinLockRaiseToDpc(&qword_14004B500);
  v12 = (_QWORD *)(a1 + 216);
  v13 = v11;
  v14 = *(_QWORD *)(a1 + 216);
  if ( v14 == a1 + 216 )
  {
    KeReleaseSpinLock(&qword_14004B500, v11);
  }
  else
  {
    if ( *(_QWORD **)(v14 + 8) != v12 )
      goto LABEL_42;
    v15 = *(_QWORD **)(a1 + 224);
    if ( (_QWORD *)*v15 != v12 )
      goto LABEL_42;
    *v15 = v14;
    *(_QWORD *)(v14 + 8) = v15;
    *(_QWORD *)(a1 + 224) = a1 + 216;
    *v12 = v12;
    --dword_14004B530;
    KeReleaseSpinLock(&qword_14004B500, v13);
    Smb2DereferenceLease((PVOID)a1);
  }
  v16 = (_QWORD *)(a1 + 184);
  _mm_lfence();
  v17 = *(_QWORD *)(v10 + 56)
      + 32LL
      * ((*(unsigned __int8 *)(a1 + 80)
        + *(unsigned __int8 *)(a1 + 81)
        + *(unsigned __int8 *)(a1 + 82)
        + *(unsigned __int8 *)(a1 + 83)
        + *(unsigned __int8 *)(a1 + 84)
        + *(unsigned __int8 *)(a1 + 86)
        + *(unsigned __int8 *)(a1 + 87)
        + *(unsigned __int8 *)(a1 + 88)
        + *(unsigned __int8 *)(a1 + 89)
        + *(unsigned __int8 *)(a1 + 90)
        + *(unsigned __int8 *)(a1 + 91)
        + *(unsigned __int8 *)(a1 + 92)
        + *(unsigned __int8 *)(a1 + 93)
        + *(unsigned __int8 *)(a1 + 94)
        + *(unsigned __int8 *)(a1 + 95)
        + (unsigned int)*(unsigned __int8 *)(a1 + 85))
       % *(_DWORD *)v10);
  if ( (*(_DWORD *)(v17 + 12) & 1) != 0 )
  {
    v18 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v17);
  }
  else
  {
    v18 = 0;
    ExAcquirePushLockExclusiveEx(v17, 0);
  }
  v19 = (_QWORD *)*v16;
  if ( (_QWORD *)*v16 == v16 )
    goto LABEL_22;
  if ( (_QWORD *)v19[1] != v16 || (v20 = *(_QWORD **)(a1 + 192), (_QWORD *)*v20 != v16) )
LABEL_42:
    __fastfail(3u);
  *v20 = v19;
  v19[1] = v20;
  *(_QWORD *)(a1 + 192) = a1 + 184;
  *v16 = v16;
  _InterlockedDecrement((volatile signed __int32 *)(v10 + 8));
  --*(_DWORD *)(v17 + 8);
LABEL_22:
  if ( (*(_DWORD *)(v17 + 12) & 1) != 0 )
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v17, v18);
  else
    ExReleasePushLockExclusiveEx(v17, 0);
  if ( v9 )
  {
    v21 = _InterlockedDecrement64((volatile signed __int64 *)v9);
    if ( v21 == -1 )
    {
      __int2c();
    }
    else if ( !v21 )
    {
      if ( KeGetCurrentIrql() )
      {
        v6 = *(_DWORD *)(v9 + 8) == 5;
        *(_QWORD *)(v9 + 48) = Smb2DereferenceHandleCallback;
        *(_DWORD *)(v9 + 72) = 0;
        if ( v6 )
        {
          LOBYTE(v24) = 1;
          SRV2_PERF_ENTER_EX(v9 + 584, v24, 391, "Srv2PostToThreadPool", 1);
        }
        v22 = *(_QWORD *)(*(_QWORD *)(v9 + 64) + 136LL);
        v23 = *(_QWORD *)(v22 + 8LL * KeGetCurrentNodeNumber() + 8);
        if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v23, (PSLIST_ENTRY)(v9 + 32)) )
        {
          if ( *(_WORD *)(v23 + 66) )
            RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v23);
        }
      }
      else
      {
        Smb2DereferenceHandleCleanup((PVOID)v9, 0);
      }
    }
  }
  Smb2DereferenceLease((PVOID)a1);
}

```

## disassembly

```asm
0x14000ca00  mov     [rsp+arg_18], rbx
0x14000ca05  push    rbp
0x14000ca06  push    rsi
0x14000ca07  push    rdi
0x14000ca08  sub     rsp, 30h
0x14000ca0c  mov     rbx, rcx
0x14000ca0f  movzx   ebp, r8b
0x14000ca13  add     rcx, 60h ; '`'; SpinLock
0x14000ca17  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ca1e  nop     dword ptr [rax+rax+00h]
0x14000ca23  add     dword ptr [rbx+0ACh], 0FFFFFFFFh
0x14000ca2a  movzx   esi, al
0x14000ca2d  jnz     loc_14000CCC4
0x14000ca33  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ca3a  lea     rax, WPP_GLOBAL_Control
0x14000ca41  cmp     rcx, rax
0x14000ca44  jz      short loc_14000CA53
0x14000ca46  test    dword ptr [rcx+2Ch], 40000000h
0x14000ca4d  jnz     loc_14000CD73
0x14000ca53  mov     ecx, [rbx+0Ch]
0x14000ca56  cmp     ecx, 0DDh
0x14000ca5c  jz      short loc_14000CA6A
0x14000ca5e  lea     rax, [rbx+98h]
0x14000ca65  cmp     [rax], rax
0x14000ca68  jz      short loc_14000CA84
0x14000ca6a  movzx   edx, sil
0x14000ca6e  mov     rcx, rbx
0x14000ca71  call    Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock
0x14000ca76  mov     rbx, [rsp+48h+arg_18]
0x14000ca7b  add     rsp, 30h
0x14000ca7f  pop     rdi
0x14000ca80  pop     rsi
0x14000ca81  pop     rbp
0x14000ca82  retn
0x14000ca84  cmp     dword ptr [rbx+0ACh], 0
0x14000ca8b  jnz     short loc_14000CA6A
0x14000ca8d  mov     [rsp+48h+arg_0], r14
0x14000ca92  cmp     ecx, 0E0h
0x14000ca98  jz      loc_14000CD9A
0x14000ca9e  mov     dword ptr [rbx+0Ch], 0DDh
0x14000caa5  mov     byte ptr [rbx+80h], 1
0x14000caac  test    bpl, bpl
0x14000caaf  jnz     loc_14000CDA7
0x14000cab5  mov     rbp, [rbx+70h]
0x14000cab9  mov     r14, [rbx+0C8h]
0x14000cac0  mov     qword ptr [rbx+70h], 0
0x14000cac8  mov     [rsp+48h+arg_10], r15
0x14000cacd  lock inc cs:dword_14004B384
0x14000cad4  movzx   edx, sil
0x14000cad8  mov     rcx, rbx
0x14000cadb  call    Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock
0x14000cae0  lea     rcx, qword_14004B500; SpinLock
0x14000cae7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000caee  nop     dword ptr [rax+rax+00h]
0x14000caf3  lea     rdx, [rbx+0D8h]
0x14000cafa  movzx   r9d, al
0x14000cafe  mov     r8, [rdx]
0x14000cb01  cmp     r8, rdx
0x14000cb04  jz      loc_14000CC82
0x14000cb0a  cmp     [r8+8], rdx
0x14000cb0e  jnz     loc_14000CDDD
0x14000cb14  mov     rax, [rdx+8]
0x14000cb18  cmp     [rax], rdx
0x14000cb1b  jnz     loc_14000CDDD
0x14000cb21  mov     [rax], r8
0x14000cb24  lea     rcx, qword_14004B500; SpinLock
0x14000cb2b  mov     [r8+8], rax
0x14000cb2f  mov     [rdx+8], rdx
0x14000cb33  mov     [rdx], rdx
0x14000cb36  movzx   edx, r9b; NewIrql
0x14000cb3a  dec     cs:dword_14004B530
0x14000cb40  call    cs:__imp_KeReleaseSpinLock
0x14000cb47  nop     dword ptr [rax+rax+00h]
0x14000cb4c  mov     rcx, rbx
0x14000cb4f  call    Smb2DereferenceLease
0x14000cb54  lea     rdi, [rbx+0B8h]
0x14000cb5b  lfence
0x14000cb5e  movzx   ecx, byte ptr [rbx+54h]
0x14000cb62  xor     edx, edx
0x14000cb64  movzx   eax, byte ptr [rbx+5Eh]
0x14000cb68  movzx   r8d, byte ptr [rbx+5Fh]
0x14000cb6d  add     r8d, eax
0x14000cb70  movzx   eax, byte ptr [rbx+5Dh]
0x14000cb74  add     r8d, eax
0x14000cb77  movzx   eax, byte ptr [rbx+5Ch]
0x14000cb7b  add     r8d, eax
0x14000cb7e  movzx   eax, byte ptr [rbx+5Bh]
0x14000cb82  add     r8d, eax
0x14000cb85  movzx   eax, byte ptr [rbx+5Ah]
0x14000cb89  add     r8d, eax
0x14000cb8c  movzx   eax, byte ptr [rbx+59h]
0x14000cb90  add     r8d, eax
0x14000cb93  movzx   eax, byte ptr [rbx+58h]
0x14000cb97  add     r8d, eax
0x14000cb9a  movzx   eax, byte ptr [rbx+57h]
0x14000cb9e  add     r8d, eax
0x14000cba1  movzx   eax, byte ptr [rbx+56h]
0x14000cba5  add     r8d, eax
0x14000cba8  movzx   eax, byte ptr [rbx+55h]
0x14000cbac  add     eax, r8d
0x14000cbaf  add     eax, ecx
0x14000cbb1  movzx   ecx, byte ptr [rbx+53h]
0x14000cbb5  add     eax, ecx
0x14000cbb7  movzx   ecx, byte ptr [rbx+52h]
0x14000cbbb  add     eax, ecx
0x14000cbbd  movzx   ecx, byte ptr [rbx+51h]
0x14000cbc1  add     eax, ecx
0x14000cbc3  movzx   ecx, byte ptr [rbx+50h]
0x14000cbc7  add     eax, ecx
0x14000cbc9  div     dword ptr [r14]
0x14000cbcc  mov     esi, edx
0x14000cbce  shl     rsi, 5
0x14000cbd2  add     rsi, [r14+38h]
0x14000cbd6  mov     rcx, rsi; SpinLock
0x14000cbd9  mov     eax, [rsi+0Ch]
0x14000cbdc  test    al, 1
0x14000cbde  jz      loc_14000CCAE
0x14000cbe4  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000cbeb  nop     dword ptr [rax+rax+00h]
0x14000cbf0  movzx   r15d, al
0x14000cbf4  mov     rax, [rdi]
0x14000cbf7  cmp     rax, rdi
0x14000cbfa  jz      short loc_14000CC29
0x14000cbfc  cmp     [rax+8], rdi
0x14000cc00  jnz     loc_14000CDDD
0x14000cc06  mov     rcx, [rdi+8]
0x14000cc0a  cmp     [rcx], rdi
0x14000cc0d  jnz     loc_14000CDDD
0x14000cc13  mov     [rcx], rax
0x14000cc16  mov     [rax+8], rcx
0x14000cc1a  mov     [rdi+8], rdi
0x14000cc1e  mov     [rdi], rdi
0x14000cc21  lock dec dword ptr [r14+8]
0x14000cc26  dec     dword ptr [rsi+8]
0x14000cc29  mov     eax, [rsi+0Ch]
0x14000cc2c  mov     rcx, rsi; SpinLock
0x14000cc2f  test    al, 1
0x14000cc31  jz      short loc_14000CC9E
0x14000cc33  movzx   edx, r15b; OldIrql
0x14000cc37  call    cs:__imp_ExReleaseSpinLockExclusive
0x14000cc3e  nop     dword ptr [rax+rax+00h]
0x14000cc43  test    rbp, rbp
0x14000cc46  jz      short loc_14000CC6B
0x14000cc48  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000cc4f  lock xadd [rbp+0], rax
0x14000cc55  dec     rax
0x14000cc58  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000cc5c  jnb     loc_14000CDB3
0x14000cc62  test    rax, rax
0x14000cc65  jz      loc_14000CDBA
0x14000cc6b  mov     rcx, rbx
0x14000cc6e  call    Smb2DereferenceLease
0x14000cc73  mov     r15, [rsp+48h+arg_10]
0x14000cc78  mov     r14, [rsp+48h+arg_0]
0x14000cc7d  jmp     loc_14000CA76
0x14000cc82  movzx   edx, r9b; NewIrql
0x14000cc86  lea     rcx, qword_14004B500; SpinLock
0x14000cc8d  call    cs:__imp_KeReleaseSpinLock
0x14000cc94  nop     dword ptr [rax+rax+00h]
0x14000cc99  jmp     loc_14000CB54
0x14000cc9e  xor     edx, edx
0x14000cca0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000cca7  nop     dword ptr [rax+rax+00h]
0x14000ccac  jmp     short loc_14000CC43
0x14000ccae  xor     r15b, r15b
0x14000ccb1  xor     edx, edx
0x14000ccb3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ccba  nop     dword ptr [rax+rax+00h]
0x14000ccbf  jmp     loc_14000CBF4
0x14000ccc4  movzx   edx, sil; NewIrql
0x14000ccc8  lea     rcx, [rbx+60h]; SpinLock
0x14000cccc  call    cs:__imp_KeReleaseSpinLock
0x14000ccd3  nop     dword ptr [rax+rax+00h]
0x14000ccd8  mov     rbx, [rsp+48h+arg_18]
0x14000ccdd  add     rsp, 30h
0x14000cce1  pop     rdi
0x14000cce2  pop     rsi
0x14000cce3  pop     rbp
0x14000cce4  retn
0x14000cce6  cmp     dword ptr [rbp+8], 5
0x14000ccea  lea     rax, Smb2DereferenceHandleCallback
0x14000ccf1  mov     [rbp+30h], rax
0x14000ccf5  mov     dword ptr [rbp+48h], 0
0x14000ccfc  jnz     short loc_14000CD1E
0x14000ccfe  lea     rcx, [rbp+248h]
0x14000cd05  mov     [rsp+48h+var_28], 1
0x14000cd0a  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14000cd11  mov     r8d, 187h
0x14000cd17  mov     dl, 1
0x14000cd19  call    SRV2_PERF_ENTER_EX
0x14000cd1e  mov     rax, [rbp+40h]
0x14000cd22  mov     rdi, [rax+88h]
0x14000cd29  call    cs:__imp_KeGetCurrentNodeNumber
0x14000cd30  nop     dword ptr [rax+rax+00h]
0x14000cd35  movzx   eax, ax
0x14000cd38  lea     rdx, [rbp+20h]; ListEntry
0x14000cd3c  mov     rdi, [rdi+rax*8+8]
0x14000cd41  mov     rcx, rdi; ListHead
0x14000cd44  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000cd4b  nop     dword ptr [rax+rax+00h]
0x14000cd50  test    rax, rax
0x14000cd53  jnz     loc_14000CC6B
0x14000cd59  movzx   edx, word ptr [rdi+42h]
0x14000cd5d  cmp     ax, dx
0x14000cd60  jz      loc_14000CC6B
0x14000cd66  mov     rcx, rdi
0x14000cd69  call    RfspThreadPoolNodeWakeIdleWorker
0x14000cd6e  jmp     loc_14000CC6B
0x14000cd73  cmp     byte ptr [rcx+29h], 2
0x14000cd77  jb      loc_14000CA53
0x14000cd7d  mov     rcx, [rcx+18h]
0x14000cd81  lea     r8, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids
0x14000cd88  mov     edx, 13h
0x14000cd8d  mov     r9, rbx
0x14000cd90  call    WPP_SF_q
0x14000cd95  jmp     loc_14000CA53
0x14000cd9a  mov     rcx, rbx
0x14000cd9d  call    Smb2CancelQueuedDelayedLease
0x14000cda2  jmp     loc_14000CA9E
0x14000cda7  or      dword ptr [rbx+8Ch], 4
0x14000cdae  jmp     loc_14000CAB5
0x14000cdb3  int     2Ch; Windows NT - assertion failure
0x14000cdb5  jmp     loc_14000CC6B
0x14000cdba  call    cs:__imp_KeGetCurrentIrql
0x14000cdc1  nop     dword ptr [rax+rax+00h]
0x14000cdc6  test    al, al
0x14000cdc8  jnz     loc_14000CCE6
0x14000cdce  xor     edx, edx
0x14000cdd0  mov     rcx, rbp; P
0x14000cdd3  call    Smb2DereferenceHandleCleanup
0x14000cdd8  jmp     loc_14000CC6B
0x14000cddd  mov     ecx, 3
0x14000cde2  int     29h; Win8: RtlFailFast(ecx)
```
