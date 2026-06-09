# VmsOmFindPortInitialized

- ea: `0x140046a88`
- end: `0x140046d12`
- name: `VmsOmFindPortInitialized`
- size: `650`
- prototype: ``
- caller_count: `16`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140035480`
- `0x1400359fc`
- `0x1400b9c4c`
- `0x1400cbbf0`
- `0x1400cd390`
- `0x1400cd868`
- `0x1400cde64`
- `0x1400ce254`
- `0x1400cea00`
- `0x1400cef18`
- `0x1400cfbfc`
- `0x1400d0168`
- `0x1400d0564`
- `0x1400d0d6c`
- `0x1400d1338`
- `0x14013c56c`

## callees

- `0x140014988`
- `0x140027a64`
- `0x140046a88`
- `0x140046d18`
- `0x140046e5c`
- `0x14008497c`
- `0x1400a832c`
- `0x1401bbb64`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140046af3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046b5a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046be5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046cad`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046af3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046b5a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046be5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046cad`
- `NDIS!NdisAcquireRWLockRead` at `0x140046ae7`
- `NDIS!NdisAcquireRWLockRead` at `0x140046b29`
- `NDIS!NdisAcquireRWLockRead` at `0x140046ae7`
- `NDIS!NdisAcquireRWLockRead` at `0x140046b29`
- `NDIS!NdisReleaseRWLock` at `0x140046c2c`
- `NDIS!NdisReleaseRWLock` at `0x140046c44`
- `NDIS!NdisReleaseRWLock` at `0x140046c71`
- `NDIS!NdisReleaseRWLock` at `0x1401bc88c`
- `NDIS!NdisReleaseRWLock` at `0x140046c2c`
- `NDIS!NdisReleaseRWLock` at `0x140046c44`
- `NDIS!NdisReleaseRWLock` at `0x140046c71`
- `NDIS!NdisReleaseRWLock` at `0x1401bc88c`
- `NDIS!NdisAcquireRWLockWrite` at `0x140046b76`
- `NDIS!NdisAcquireRWLockWrite` at `0x140046b76`

## pseudocode

```c
__int64 __fastcall VmsOmFindPortInitialized(__int64 a1, __int64 a2, char a3, _QWORD *a4)
{
  int v8; // edx
  int v9; // edx
  __int64 v10; // rbx
  int v11; // edx
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 v15; // [rsp+0h] [rbp-98h] BYREF
  struct _LOCK_STATE_EX v16; // [rsp+40h] [rbp-58h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+44h] [rbp-54h] BYREF
  struct _LOCK_STATE_EX v18; // [rsp+48h] [rbp-50h] BYREF
  int PortInListUnsafe; // [rsp+4Ch] [rbp-4Ch]
  __int64 v20; // [rsp+50h] [rbp-48h] BYREF
  PNDIS_RW_LOCK_EX *v21; // [rsp+58h] [rbp-40h]
  __int64 *v22; // [rsp+60h] [rbp-38h]

  v22 = &v15;
  v20 = 0;
  *(_WORD *)&v18.OldIrql = 0;
  v18.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_WORD *)&v16.OldIrql = 0;
  v16.Flags = 0;
  NdisAcquireRWLockRead(VmsOmObjectListLock, &v18, 0);
  if ( KeGetCurrentIrql() != 2 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v8,
      19,
      24,
      (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
      (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
    if ( KeGetCurrentIrql() != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v21 = (PNDIS_RW_LOCK_EX *)(a1 + 56);
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState, 1u);
  PortInListUnsafe = VmsOmpFindPortInListUnsafe(a1 + 1416, a2, &v20);
  if ( !PortInListUnsafe )
  {
    v10 = v20;
    if ( KeGetCurrentIrql() != 2 )
      goto LABEL_6;
    while ( 1 )
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v10 + 56), &v16, 1u);
      if ( *(_DWORD *)(v10 + 68) != 2 )
        break;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 9096), v12, 20, 46, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids);
      PortInListUnsafe = -1073741738;
      local_unwind_0(v22, &loc_140046C13);
LABEL_6:
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v11,
        19,
        23,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    LOBYTE(v12) = a3;
    VmsOmpObjectReference(v10, v12);
    *a4 = v10;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v10 + 56), &v16);
  }
  v13 = PortInListUnsafe;
  if ( PortInListUnsafe < 0 )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_qZd(
      *(_QWORD *)(a1 + 9096),
      v9,
      20,
      47,
      (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids,
      a1,
      a2,
      PortInListUnsafe);
  }
  NdisReleaseRWLock(*v21, &LockState);
  NdisReleaseRWLock(VmsOmObjectListLock, &v18);
  return v13;
}

```

## disassembly

```asm
0x140046a88  mov     r11, rsp
0x140046a8b  mov     [r11+18h], rbx
0x140046a8f  mov     [r11+10h], rdx
0x140046a93  mov     [r11+8], rcx
0x140046a97  push    rsi
0x140046a98  push    rdi
0x140046a99  push    r12
0x140046a9b  push    r14
0x140046a9d  push    r15
0x140046a9f  sub     rsp, 70h
0x140046aa3  mov     [rsp+98h+var_38], rsp
0x140046aa8  mov     r15, r9
0x140046aab  mov     r12d, r8d
0x140046aae  mov     rbx, rdx
0x140046ab1  mov     r14, rcx
0x140046ab4  mov     qword ptr [r11-48h], 0
0x140046abc  xor     eax, eax
0x140046abe  mov     word ptr [rsp+98h+var_50.OldIrql], ax
0x140046ac3  mov     [rsp+98h+var_50.Flags], al
0x140046ac7  mov     word ptr [rsp+98h+LockState.OldIrql], ax
0x140046acc  mov     [rsp+98h+LockState.Flags], al
0x140046ad0  mov     word ptr [rsp+98h+var_58.OldIrql], ax
0x140046ad5  mov     [rsp+98h+var_58.Flags], al
0x140046ad9  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140046ae0  xor     r8d, r8d; Flags
0x140046ae3  lea     rdx, [r11-50h]; LockState
0x140046ae7  call    cs:__imp_NdisAcquireRWLockRead
0x140046aee  nop     dword ptr [rax+rax+00h]
0x140046af3  call    cs:__imp_KeGetCurrentIrql
0x140046afa  nop     dword ptr [rax+rax+00h]
0x140046aff  cmp     al, 2
0x140046b01  jnz     loc_140046C7F
0x140046b07  lea     rdi, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x140046b0e  lea     rsi, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140046b15  lea     rcx, [r14+38h]
0x140046b19  mov     [rsp+98h+var_40], rcx
0x140046b1e  mov     r8b, 1; Flags
0x140046b21  lea     rdx, [rsp+98h+LockState]; LockState
0x140046b26  mov     rcx, [rcx]; Lock
0x140046b29  call    cs:__imp_NdisAcquireRWLockRead
0x140046b30  nop     dword ptr [rax+rax+00h]
0x140046b35  lea     rcx, [r14+588h]
0x140046b3c  lea     r8, [rsp+98h+var_48]
0x140046b41  mov     rdx, rbx
0x140046b44  call    VmsOmpFindPortInListUnsafe
0x140046b49  mov     [rsp+98h+var_4C], eax
0x140046b4d  test    eax, eax
0x140046b4f  jnz     loc_140046C13
0x140046b55  mov     rbx, [rsp+98h+var_48]
0x140046b5a  call    cs:__imp_KeGetCurrentIrql
0x140046b61  nop     dword ptr [rax+rax+00h]
0x140046b66  cmp     al, 2
0x140046b68  jnz     short loc_140046BC5
0x140046b6a  mov     r8b, 1; Flags
0x140046b6d  lea     rdx, [rsp+98h+var_58]; LockState
0x140046b72  mov     rcx, [rbx+38h]; Lock
0x140046b76  call    cs:__imp_NdisAcquireRWLockWrite
0x140046b7d  nop     dword ptr [rax+rax+00h]
0x140046b82  cmp     dword ptr [rbx+44h], 2
0x140046b86  jnz     short loc_140046C03
0x140046b88  mov     r9d, 2Eh ; '.'
0x140046b8e  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x140046b95  mov     [rsp+98h+var_78], rax
0x140046b9a  lea     r8d, [r9-1Ah]
0x140046b9e  mov     dl, 2
0x140046ba0  mov     rcx, [r14+2388h]
0x140046ba7  call    WPP_RECORDER_SF_
0x140046bac  mov     [rsp+98h+var_4C], 0C0000056h
0x140046bb4  lea     rdx, loc_140046C13
0x140046bbb  mov     rcx, [rsp+98h+var_38]
0x140046bc0  call    _local_unwind_0
0x140046bc5  mov     r9d, 17h
0x140046bcb  mov     [rsp+98h+var_70], rdi
0x140046bd0  mov     [rsp+98h+var_78], rsi
0x140046bd5  lea     r8d, [r9-4]
0x140046bd9  mov     rcx, cs:VmsIfrLog
0x140046be0  call    WPP_RECORDER_SF_s
0x140046be5  call    cs:__imp_KeGetCurrentIrql
0x140046bec  nop     dword ptr [rax+rax+00h]
0x140046bf1  cmp     al, 2
0x140046bf3  jz      loc_140046B6A
0x140046bf9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x140046bfe  jmp     loc_140046B6A
0x140046c03  mov     dl, r12b
0x140046c06  mov     rcx, rbx
0x140046c09  call    VmsOmpObjectReference
0x140046c0e  mov     [r15], rbx
0x140046c11  jmp     short loc_140046C68
0x140046c13  mov     ebx, [rsp+98h+var_4C]
0x140046c17  test    ebx, ebx
0x140046c19  js      loc_140046CCB
0x140046c1f  lea     rdx, [rsp+98h+LockState]; LockState
0x140046c24  mov     rcx, [rsp+98h+var_40]
0x140046c29  mov     rcx, [rcx]; Lock
0x140046c2c  call    cs:__imp_NdisReleaseRWLock
0x140046c33  nop     dword ptr [rax+rax+00h]
0x140046c38  lea     rdx, [rsp+98h+var_50]; LockState
0x140046c3d  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140046c44  call    cs:__imp_NdisReleaseRWLock
0x140046c4b  nop     dword ptr [rax+rax+00h]
0x140046c50  mov     eax, ebx
0x140046c52  mov     rbx, [rsp+98h+arg_10]
0x140046c5a  add     rsp, 70h
0x140046c5e  pop     r15
0x140046c60  pop     r14
0x140046c62  pop     r12
0x140046c64  pop     rdi
0x140046c65  pop     rsi
0x140046c66  retn
0x140046c68  lea     rdx, [rsp+98h+var_58]; LockState
0x140046c6d  mov     rcx, [rbx+38h]; Lock
0x140046c71  call    cs:__imp_NdisReleaseRWLock
0x140046c78  nop     dword ptr [rax+rax+00h]
0x140046c7d  jmp     short loc_140046C13
0x140046c7f  mov     r9d, 18h
0x140046c85  lea     rdi, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x140046c8c  mov     [rsp+98h+var_70], rdi
0x140046c91  lea     rsi, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140046c98  mov     [rsp+98h+var_78], rsi
0x140046c9d  lea     r8d, [r9-5]
0x140046ca1  mov     rcx, cs:VmsIfrLog
0x140046ca8  call    WPP_RECORDER_SF_s
0x140046cad  call    cs:__imp_KeGetCurrentIrql
0x140046cb4  nop     dword ptr [rax+rax+00h]
0x140046cb9  cmp     al, 2
0x140046cbb  jz      loc_140046B15
0x140046cc1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x140046cc6  jmp     loc_140046B15
0x140046ccb  mov     r9d, 2Fh ; '/'
0x140046cd1  mov     [rsp+98h+var_60], ebx
0x140046cd5  mov     rax, [rsp+98h+arg_8]
0x140046cdd  mov     [rsp+98h+var_68], rax
0x140046ce2  mov     rcx, [rsp+98h+arg_0]
0x140046cea  mov     [rsp+98h+var_70], rcx
0x140046cef  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x140046cf6  mov     [rsp+98h+var_78], rax
0x140046cfb  lea     r8d, [r9-1Bh]
0x140046cff  mov     dl, 2
0x140046d01  mov     rcx, [rcx+2388h]
0x140046d08  call    WPP_RECORDER_SF_qZd
0x140046d0d  jmp     loc_140046C1F
0x1401bc877  push    rbp
0x1401bc879  sub     rsp, 40h
0x1401bc87d  mov     rbp, rdx
0x1401bc880  mov     rcx, [rbp+50h]
0x1401bc884  lea     rdx, [rbp+40h]; LockState
0x1401bc888  mov     rcx, [rcx+38h]; Lock
0x1401bc88c  call    cs:__imp_NdisReleaseRWLock
0x1401bc893  nop     dword ptr [rax+rax+00h]
0x1401bc898  nop
0x1401bc899  add     rsp, 40h
0x1401bc89d  pop     rbp
0x1401bc89e  retn
```
