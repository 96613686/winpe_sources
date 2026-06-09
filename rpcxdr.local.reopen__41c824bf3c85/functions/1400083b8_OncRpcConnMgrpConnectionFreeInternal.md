# OncRpcConnMgrpConnectionFreeInternal

- ea: `0x1400083b8`
- end: `0x1400085ab`
- name: `OncRpcConnMgrpConnectionFreeInternal`
- size: `499`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x140007b48`
- `0x140007cc0`
- `0x1400082a8`

## callees

- `0x140002170`
- `0x14000639c`
- `0x140006798`
- `0x1400083b8`
- `0x14000880c`
- `0x14000fabc`
- `0x140012a60`
- `0x140015680`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000856b`
- `ntoskrnl!IoFreeIrp` at `0x14000856b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008439`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400084e1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008439`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400084e1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400084b1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008513`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400084b1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008513`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400084a0`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400084a0`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpConnectionFreeInternal(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 (__fastcall *v3)(__int64); // rbp
  __int64 v4; // r14
  __int64 v5; // rsi
  __int64 *v7; // rdi
  __int64 *v8; // rcx
  __int64 **v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rax
  __int64 *v14; // rcx
  __int64 **v15; // rax
  __int64 v16; // r9
  IRP *v17; // rcx
  __int64 result; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-58h] BYREF

  v3 = *(__int64 (__fastcall **)(__int64))(a1 + 96);
  v4 = *(_QWORD *)(a1 + 88);
  v5 = *(_QWORD *)(a1 + 64);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_qdL(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      a3,
      a1,
      *(_DWORD *)(a1 + 4),
      *(_DWORD *)(a1 + 80),
      LockHandle.LockQueue.Next,
      LockHandle.LockQueue.Lock,
      *(_QWORD *)&LockHandle.OldIrql);
  v7 = (__int64 *)(a1 + 24);
  if ( !v5 )
  {
    KeAcquireInStackQueuedSpinLock(&OncRpcConnMgrGlobals, &LockHandle);
    v14 = (__int64 *)*v7;
    if ( *(__int64 **)(*v7 + 8) == v7 )
    {
      v15 = *(__int64 ***)(a1 + 32);
      if ( *v15 == v7 )
      {
        *v15 = v14;
        v14[1] = (__int64)v15;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        goto LABEL_16;
      }
    }
LABEL_26:
    __fastfail(3u);
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 40), &LockHandle);
  v8 = (__int64 *)*v7;
  if ( *(__int64 **)(*v7 + 8) != v7 )
    goto LABEL_26;
  v9 = *(__int64 ***)(a1 + 32);
  if ( *v9 != v7 )
    goto LABEL_26;
  *v9 = v8;
  v8[1] = (__int64)v9;
  v10 = *(_QWORD *)(a1 + 40);
  if ( *(_QWORD *)(v10 + 8) != a1 + 40 )
    goto LABEL_26;
  v11 = *(_QWORD **)(a1 + 48);
  if ( *v11 != a1 + 40 )
    goto LABEL_26;
  *v11 = v10;
  *(_QWORD *)(v10 + 8) = v11;
  v12 = *(_QWORD *)(a1 + 56);
  if ( (*(_DWORD *)(v12 + 28))-- == 1 )
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v5 + 288), *(PVOID *)(a1 + 56));
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  _InterlockedDecrement((volatile signed __int32 *)(v5 + 280));
  if ( !(unsigned int)NfsStandardHeaderDereferenceNoType(v5) )
    OncRpcConnMgrpEndpointFree((PVOID)v5);
LABEL_16:
  v16 = *(_QWORD *)(a1 + 160);
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids, v16);
    OncRpcWiMgrSrvWorkItemFree(*(_QWORD *)(a1 + 160));
  }
  v17 = *(IRP **)(a1 + 224);
  if ( v17 )
    IoFreeIrp(v17);
  result = NfsMemMgrStructureFreeByHandle(qword_14001A3A8, a1);
  if ( v3 )
    return v3(v4);
  return result;
}

```

## disassembly

```asm
0x1400083b8  push    rbx
0x1400083ba  push    rbp
0x1400083bb  push    rsi
0x1400083bc  push    rdi
0x1400083bd  push    r14
0x1400083bf  push    r15
0x1400083c1  sub     rsp, 58h
0x1400083c5  mov     rbp, [rcx+60h]
0x1400083c9  xorps   xmm0, xmm0
0x1400083cc  mov     r14, [rcx+58h]
0x1400083d0  xor     eax, eax
0x1400083d2  mov     rsi, [rcx+40h]
0x1400083d6  mov     rbx, rcx
0x1400083d9  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x1400083de  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x1400083e3  mov     rax, cs:WPP_GLOBAL_Control
0x1400083ea  lea     r15, WPP_GLOBAL_Control
0x1400083f1  cmp     rax, r15
0x1400083f4  jz      short loc_140008423
0x1400083f6  mov     eax, [rax+2Ch]
0x1400083f9  test    al, 8
0x1400083fb  jz      short loc_140008423
0x1400083fd  mov     ecx, [rcx+4]
0x140008400  mov     edx, 0Bh
0x140008405  mov     eax, [rbx+50h]
0x140008408  mov     r9, rbx
0x14000840b  mov     [rsp+88h+var_60], eax
0x14000840f  mov     [rsp+88h+var_68], ecx
0x140008413  mov     rcx, cs:WPP_GLOBAL_Control
0x14000841a  mov     rcx, [rcx+18h]
0x14000841e  call    WPP_SF_qdL
0x140008423  lea     rdi, [rbx+18h]
0x140008427  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14000842c  test    rsi, rsi
0x14000842f  jz      loc_1400084DA
0x140008435  lea     rcx, [rsi+28h]; SpinLock
0x140008439  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140008440  nop     dword ptr [rax+rax+00h]
0x140008445  mov     rcx, [rdi]
0x140008448  cmp     [rcx+8], rdi
0x14000844c  jnz     loc_1400085A4
0x140008452  mov     rax, [rdi+8]
0x140008456  cmp     [rax], rdi
0x140008459  jnz     loc_1400085A4
0x14000845f  mov     [rax], rcx
0x140008462  mov     [rcx+8], rax
0x140008466  lea     rax, [rbx+28h]
0x14000846a  mov     rdx, [rax]
0x14000846d  cmp     [rdx+8], rax
0x140008471  jnz     loc_1400085A4
0x140008477  mov     rcx, [rax+8]
0x14000847b  cmp     [rcx], rax
0x14000847e  jnz     loc_1400085A4
0x140008484  mov     [rcx], rdx
0x140008487  mov     [rdx+8], rcx
0x14000848b  mov     rax, [rbx+38h]
0x14000848f  add     dword ptr [rax+1Ch], 0FFFFFFFFh
0x140008493  jnz     short loc_1400084AC
0x140008495  mov     rdx, [rbx+38h]; Buffer
0x140008499  lea     rcx, [rsi+120h]; Table
0x1400084a0  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400084a7  nop     dword ptr [rax+rax+00h]
0x1400084ac  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x1400084b1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400084b8  nop     dword ptr [rax+rax+00h]
0x1400084bd  lock dec dword ptr [rsi+118h]
0x1400084c4  mov     rcx, rsi
0x1400084c7  call    NfsStandardHeaderDereferenceNoType
0x1400084cc  test    eax, eax
0x1400084ce  jnz     short loc_14000851F
0x1400084d0  mov     rcx, rsi; P
0x1400084d3  call    OncRpcConnMgrpEndpointFree
0x1400084d8  jmp     short loc_14000851F
0x1400084da  lea     rcx, OncRpcConnMgrGlobals; SpinLock
0x1400084e1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400084e8  nop     dword ptr [rax+rax+00h]
0x1400084ed  mov     rcx, [rdi]
0x1400084f0  cmp     [rcx+8], rdi
0x1400084f4  jnz     loc_1400085A4
0x1400084fa  mov     rax, [rdi+8]
0x1400084fe  cmp     [rax], rdi
0x140008501  jnz     loc_1400085A4
0x140008507  mov     [rax], rcx
0x14000850a  mov     [rcx+8], rax
0x14000850e  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x140008513  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000851a  nop     dword ptr [rax+rax+00h]
0x14000851f  mov     r9, [rbx+0A0h]
0x140008526  test    r9, r9
0x140008529  jz      short loc_14000855F
0x14000852b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008532  cmp     rcx, r15
0x140008535  jz      short loc_140008553
0x140008537  mov     eax, [rcx+2Ch]
0x14000853a  test    al, 8
0x14000853c  jz      short loc_140008553
0x14000853e  mov     rcx, [rcx+18h]
0x140008542  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x140008549  mov     edx, 0Ch
0x14000854e  call    WPP_SF_q
0x140008553  mov     rcx, [rbx+0A0h]
0x14000855a  call    OncRpcWiMgrSrvWorkItemFree
0x14000855f  mov     rcx, [rbx+0E0h]; Irp
0x140008566  test    rcx, rcx
0x140008569  jz      short loc_140008577
0x14000856b  call    cs:__imp_IoFreeIrp
0x140008572  nop     dword ptr [rax+rax+00h]
0x140008577  mov     rcx, cs:qword_14001A3A8
0x14000857e  mov     rdx, rbx
0x140008581  call    NfsMemMgrStructureFreeByHandle
0x140008586  test    rbp, rbp
0x140008589  jz      short loc_140008596
0x14000858b  mov     rcx, r14
0x14000858e  mov     rax, rbp
0x140008591  call    _guard_dispatch_icall
0x140008596  add     rsp, 58h
0x14000859a  pop     r15
0x14000859c  pop     r14
0x14000859e  pop     rdi
0x14000859f  pop     rsi
0x1400085a0  pop     rbp
0x1400085a1  pop     rbx
0x1400085a2  retn
0x1400085a4  mov     ecx, 3
0x1400085a9  int     29h; Win8: RtlFailFast(ecx)
```
