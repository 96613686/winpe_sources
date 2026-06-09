# lbfoLACPRemoveNic

- ea: `0x140099f40`
- end: `0x14009a1ea`
- name: `lbfoLACPRemoveNic`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14016cab0`

## callees

- `0x14003c378`
- `0x140099f40`
- `0x14009a1f0`
- `0x14009a438`
- `0x14009a814`
- `0x14009ac44`
- `0x14009afb0`
- `0x14009b204`
- `0x140164bf4`

## import_xrefs

- `ntoskrnl!KeFlushQueuedDpcs` at `0x14009a0cb`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14009a0cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009a1a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009a1a4`
- `NDIS!NdisFreeTimerObject` at `0x14009a12b`
- `NDIS!NdisFreeTimerObject` at `0x14009a144`
- `NDIS!NdisFreeTimerObject` at `0x14009a15d`
- `NDIS!NdisFreeTimerObject` at `0x14009a176`
- `NDIS!NdisFreeTimerObject` at `0x14009a18f`
- `NDIS!NdisFreeTimerObject` at `0x14009a12b`
- `NDIS!NdisFreeTimerObject` at `0x14009a144`
- `NDIS!NdisFreeTimerObject` at `0x14009a15d`
- `NDIS!NdisFreeTimerObject` at `0x14009a176`
- `NDIS!NdisFreeTimerObject` at `0x14009a18f`
- `NDIS!NdisCancelTimerObject` at `0x14009a055`
- `NDIS!NdisCancelTimerObject` at `0x14009a06a`
- `NDIS!NdisCancelTimerObject` at `0x14009a07f`
- `NDIS!NdisCancelTimerObject` at `0x14009a094`
- `NDIS!NdisCancelTimerObject` at `0x14009a0a9`
- `NDIS!NdisCancelTimerObject` at `0x14009a055`
- `NDIS!NdisCancelTimerObject` at `0x14009a06a`
- `NDIS!NdisCancelTimerObject` at `0x14009a07f`
- `NDIS!NdisCancelTimerObject` at `0x14009a094`
- `NDIS!NdisCancelTimerObject` at `0x14009a0a9`
- `NDIS!NdisMSleep` at `0x14009a0f4`
- `NDIS!NdisMSleep` at `0x14009a0f4`
- `NDIS!NdisReleaseRWLock` at `0x14009a0bf`
- `NDIS!NdisReleaseRWLock` at `0x14009a0e3`
- `NDIS!NdisReleaseRWLock` at `0x14009a0bf`
- `NDIS!NdisReleaseRWLock` at `0x14009a0e3`
- `NDIS!NdisAcquireRWLockWrite` at `0x14009a10d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14009a10d`

## pseudocode

```c
void __fastcall lbfoLACPRemoveNic(__int64 a1, __int64 a2, struct _LOCK_STATE_EX *a3)
{
  void ***v3; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  void **v9; // rcx
  void **v10; // rax
  void **v11; // rcx
  void **v12; // rcx
  void **v13; // rcx
  void **v14; // rcx
  void **v15; // rcx
  void **v16; // rcx
  void **v17; // rcx
  void **v18; // rcx
  void **v19; // rcx
  void **v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r8

  v3 = *(void ****)(a2 + 800);
  if ( v3 )
  {
    if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_I(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        23,
        19,
        (__int64)WPP_3b3ad73f635538be001feb44cefcc211_Traceguids,
        a2);
    *((_BYTE *)v3 + 156) = 1;
    lbfoLACPReceiveMachine(a1, a2);
    lbfoLACPPeriodicTransmissionMachine(v7, a2);
    lbfoLACPSelectionLogic(a1, a2);
    lbfoLACPMuxMachine(a1, a2);
    lbfoLACPTransmitMachine(v8, a2);
    lbfoLACPChurnDetectionMachine(a2, 1);
    lbfoLACPChurnDetectionMachine(a2, 0);
    v9 = *v3;
    if ( (*v3)[1] != v3 || (v10 = v3[1], *v10 != v3) )
      __fastfail(3u);
    *v10 = v9;
    v9[1] = v10;
    if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_I(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        23,
        20,
        (__int64)WPP_3b3ad73f635538be001feb44cefcc211_Traceguids,
        a2);
    v11 = v3[8];
    if ( v11 )
      NdisCancelTimerObject(v11);
    v12 = v3[10];
    if ( v12 )
      NdisCancelTimerObject(v12);
    v13 = v3[9];
    if ( v13 )
      NdisCancelTimerObject(v13);
    v14 = v3[11];
    if ( v14 )
      NdisCancelTimerObject(v14);
    v15 = v3[12];
    if ( v15 )
      NdisCancelTimerObject(v15);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 1584), a3);
    KeFlushQueuedDpcs();
    while ( 1 )
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 1584), a3, 0);
      if ( !*((_BYTE *)v3 + 176) )
        break;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 1584), a3);
      NdisMSleep(0xAu);
    }
    v16 = v3[8];
    if ( v16 )
    {
      NdisFreeTimerObject(v16);
      v3[8] = 0;
    }
    v17 = v3[10];
    if ( v17 )
    {
      NdisFreeTimerObject(v17);
      v3[10] = 0;
    }
    v18 = v3[9];
    if ( v18 )
    {
      NdisFreeTimerObject(v18);
      v3[9] = 0;
    }
    v19 = v3[11];
    if ( v19 )
    {
      NdisFreeTimerObject(v19);
      v3[11] = 0;
    }
    v20 = v3[12];
    if ( v20 )
    {
      NdisFreeTimerObject(v20);
      v3[12] = 0;
    }
    ExFreePoolWithTag(v3, 0);
    *(_QWORD *)(a2 + 800) = 0;
    if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 0x200000) != 0 )
      McTemplateK0jd_EtwWriteTransfer(v21, LacpDeinitingInfo, v22, a2 + 48, 0);
  }
}

```

## disassembly

```asm
0x140099f40  push    rbx
0x140099f42  push    rbp
0x140099f43  push    rsi
0x140099f44  push    rdi
0x140099f45  push    r12
0x140099f47  push    r14
0x140099f49  sub     rsp, 38h
0x140099f4d  mov     rbx, [rdx+320h]
0x140099f54  xor     r14d, r14d
0x140099f57  mov     rbp, r8
0x140099f5a  mov     rdi, rdx
0x140099f5d  mov     rsi, rcx
0x140099f60  test    rbx, rbx
0x140099f63  jz      loc_14009A1D5
0x140099f69  mov     rcx, cs:WPP_GLOBAL_Control
0x140099f70  lea     r12, WPP_3b3ad73f635538be001feb44cefcc211_Traceguids
0x140099f77  mov     al, [rcx+29h]
0x140099f7a  dec     al
0x140099f7c  cmp     al, 2
0x140099f7e  ja      short loc_140099F87
0x140099f80  cmp     [rcx+48h], r14w
0x140099f85  jz      short loc_140099FA6
0x140099f87  mov     rcx, [rcx+40h]
0x140099f8b  mov     r9d, 13h
0x140099f91  mov     [rsp+68h+var_40], rdi
0x140099f96  xor     edx, edx
0x140099f98  mov     [rsp+68h+var_48], r12
0x140099f9d  lea     r8d, [r9+4]
0x140099fa1  call    WPP_RECORDER_SF_I
0x140099fa6  mov     rdx, rdi
0x140099fa9  mov     byte ptr [rbx+9Ch], 1
0x140099fb0  mov     rcx, rsi
0x140099fb3  call    lbfoLACPReceiveMachine
0x140099fb8  mov     rdx, rdi
0x140099fbb  call    lbfoLACPPeriodicTransmissionMachine
0x140099fc0  mov     rdx, rdi
0x140099fc3  mov     rcx, rsi
0x140099fc6  call    lbfoLACPSelectionLogic
0x140099fcb  mov     rdx, rdi
0x140099fce  mov     rcx, rsi
0x140099fd1  call    lbfoLACPMuxMachine
0x140099fd6  mov     rdx, rdi
0x140099fd9  call    lbfoLACPTransmitMachine
0x140099fde  mov     edx, 1
0x140099fe3  mov     rcx, rdi
0x140099fe6  call    lbfoLACPChurnDetectionMachine
0x140099feb  xor     edx, edx
0x140099fed  mov     rcx, rdi
0x140099ff0  call    lbfoLACPChurnDetectionMachine
0x140099ff5  mov     rcx, [rbx]
0x140099ff8  cmp     [rcx+8], rbx
0x140099ffc  jnz     loc_14009A1E3
0x14009a002  mov     rax, [rbx+8]
0x14009a006  cmp     [rax], rbx
0x14009a009  jnz     loc_14009A1E3
0x14009a00f  mov     [rax], rcx
0x14009a012  mov     [rcx+8], rax
0x14009a016  mov     rcx, cs:WPP_GLOBAL_Control
0x14009a01d  mov     al, [rcx+29h]
0x14009a020  dec     al
0x14009a022  cmp     al, 2
0x14009a024  ja      short loc_14009A02D
0x14009a026  cmp     [rcx+48h], r14w
0x14009a02b  jz      short loc_14009A04C
0x14009a02d  mov     rcx, [rcx+40h]
0x14009a031  mov     r9d, 14h
0x14009a037  mov     [rsp+68h+var_40], rdi
0x14009a03c  xor     edx, edx
0x14009a03e  mov     [rsp+68h+var_48], r12
0x14009a043  lea     r8d, [r9+3]
0x14009a047  call    WPP_RECORDER_SF_I
0x14009a04c  mov     rcx, [rbx+40h]; TimerObject
0x14009a050  test    rcx, rcx
0x14009a053  jz      short loc_14009A061
0x14009a055  call    cs:__imp_NdisCancelTimerObject
0x14009a05c  nop     dword ptr [rax+rax+00h]
0x14009a061  mov     rcx, [rbx+50h]; TimerObject
0x14009a065  test    rcx, rcx
0x14009a068  jz      short loc_14009A076
0x14009a06a  call    cs:__imp_NdisCancelTimerObject
0x14009a071  nop     dword ptr [rax+rax+00h]
0x14009a076  mov     rcx, [rbx+48h]; TimerObject
0x14009a07a  test    rcx, rcx
0x14009a07d  jz      short loc_14009A08B
0x14009a07f  call    cs:__imp_NdisCancelTimerObject
0x14009a086  nop     dword ptr [rax+rax+00h]
0x14009a08b  mov     rcx, [rbx+58h]; TimerObject
0x14009a08f  test    rcx, rcx
0x14009a092  jz      short loc_14009A0A0
0x14009a094  call    cs:__imp_NdisCancelTimerObject
0x14009a09b  nop     dword ptr [rax+rax+00h]
0x14009a0a0  mov     rcx, [rbx+60h]; TimerObject
0x14009a0a4  test    rcx, rcx
0x14009a0a7  jz      short loc_14009A0B5
0x14009a0a9  call    cs:__imp_NdisCancelTimerObject
0x14009a0b0  nop     dword ptr [rax+rax+00h]
0x14009a0b5  mov     rcx, [rsi+630h]; Lock
0x14009a0bc  mov     rdx, rbp; LockState
0x14009a0bf  call    cs:__imp_NdisReleaseRWLock
0x14009a0c6  nop     dword ptr [rax+rax+00h]
0x14009a0cb  call    cs:__imp_KeFlushQueuedDpcs
0x14009a0d2  nop     dword ptr [rax+rax+00h]
0x14009a0d7  jmp     short loc_14009A100
0x14009a0d9  mov     rcx, [rsi+630h]; Lock
0x14009a0e0  mov     rdx, rbp; LockState
0x14009a0e3  call    cs:__imp_NdisReleaseRWLock
0x14009a0ea  nop     dword ptr [rax+rax+00h]
0x14009a0ef  mov     ecx, 0Ah; MicrosecondsToSleep
0x14009a0f4  call    cs:__imp_NdisMSleep
0x14009a0fb  nop     dword ptr [rax+rax+00h]
0x14009a100  mov     rcx, [rsi+630h]; Lock
0x14009a107  xor     r8d, r8d; Flags
0x14009a10a  mov     rdx, rbp; LockState
0x14009a10d  call    cs:__imp_NdisAcquireRWLockWrite
0x14009a114  nop     dword ptr [rax+rax+00h]
0x14009a119  cmp     [rbx+0B0h], r14b
0x14009a120  jnz     short loc_14009A0D9
0x14009a122  mov     rcx, [rbx+40h]; TimerObject
0x14009a126  test    rcx, rcx
0x14009a129  jz      short loc_14009A13B
0x14009a12b  call    cs:__imp_NdisFreeTimerObject
0x14009a132  nop     dword ptr [rax+rax+00h]
0x14009a137  mov     [rbx+40h], r14
0x14009a13b  mov     rcx, [rbx+50h]; TimerObject
0x14009a13f  test    rcx, rcx
0x14009a142  jz      short loc_14009A154
0x14009a144  call    cs:__imp_NdisFreeTimerObject
0x14009a14b  nop     dword ptr [rax+rax+00h]
0x14009a150  mov     [rbx+50h], r14
0x14009a154  mov     rcx, [rbx+48h]; TimerObject
0x14009a158  test    rcx, rcx
0x14009a15b  jz      short loc_14009A16D
0x14009a15d  call    cs:__imp_NdisFreeTimerObject
0x14009a164  nop     dword ptr [rax+rax+00h]
0x14009a169  mov     [rbx+48h], r14
0x14009a16d  mov     rcx, [rbx+58h]; TimerObject
0x14009a171  test    rcx, rcx
0x14009a174  jz      short loc_14009A186
0x14009a176  call    cs:__imp_NdisFreeTimerObject
0x14009a17d  nop     dword ptr [rax+rax+00h]
0x14009a182  mov     [rbx+58h], r14
0x14009a186  mov     rcx, [rbx+60h]; TimerObject
0x14009a18a  test    rcx, rcx
0x14009a18d  jz      short loc_14009A19F
0x14009a18f  call    cs:__imp_NdisFreeTimerObject
0x14009a196  nop     dword ptr [rax+rax+00h]
0x14009a19b  mov     [rbx+60h], r14
0x14009a19f  xor     edx, edx; Tag
0x14009a1a1  mov     rcx, rbx; P
0x14009a1a4  call    cs:__imp_ExFreePoolWithTag
0x14009a1ab  nop     dword ptr [rax+rax+00h]
0x14009a1b0  mov     [rdi+320h], r14
0x14009a1b7  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits+2, 20h
0x14009a1be  jz      short loc_14009A1D5
0x14009a1c0  lea     r9, [rdi+30h]
0x14009a1c4  mov     dword ptr [rsp+68h+var_48], r14d
0x14009a1c9  lea     rdx, LacpDeinitingInfo
0x14009a1d0  call    McTemplateK0jd_EtwWriteTransfer
0x14009a1d5  add     rsp, 38h
0x14009a1d9  pop     r14
0x14009a1db  pop     r12
0x14009a1dd  pop     rdi
0x14009a1de  pop     rsi
0x14009a1df  pop     rbp
0x14009a1e0  pop     rbx
0x14009a1e1  retn
0x14009a1e3  mov     ecx, 3
0x14009a1e8  int     29h; Win8: RtlFailFast(ecx)
```
