# lbfoUpdateNicMacWorkItem

- ea: `0x140166ba0`
- end: `0x140166e3b`
- name: `lbfoUpdateNicMacWorkItem`
- size: `667`
- prototype: `NDIS_IO_WORKITEM_FUNCTION`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x1401609e8`
- `0x140165f38`
- `0x140166ba0`
- `0x140168464`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140166dff`
- `ntoskrnl!KeSetEvent` at `0x140166dff`
- `ntoskrnl!ExAcquireFastMutex` at `0x140166ca1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140166ca1`
- `ntoskrnl!ExReleaseFastMutex` at `0x140166db6`
- `ntoskrnl!ExReleaseFastMutex` at `0x140166db6`
- `NDIS!NdisReleaseRWLock` at `0x140166d1c`
- `NDIS!NdisReleaseRWLock` at `0x140166da6`
- `NDIS!NdisReleaseRWLock` at `0x140166e16`
- `NDIS!NdisReleaseRWLock` at `0x140166d1c`
- `NDIS!NdisReleaseRWLock` at `0x140166da6`
- `NDIS!NdisReleaseRWLock` at `0x140166e16`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166cbb`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166d64`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166dd9`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166cbb`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166d64`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166dd9`

## string_xrefs

- `0x140166c6b`: `SrIov->UpdateMacWIQueued`

## pseudocode

```c
void __fastcall lbfoUpdateNicMacWorkItem(char *WorkItemContext, NDIS_HANDLE NdisIoWorkItemHandle)
{
  int v3; // r15d
  char v4; // r13
  __int16 v5; // r12
  __int64 v6; // rdi
  int v7; // edx
  __int64 NicSrIov; // r14
  unsigned __int8 v9; // cl
  char v10; // si
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  struct _NDIS_RW_LOCK_EX *v14; // rcx
  int v16; // [rsp+80h] [rbp+40h] BYREF
  __int16 v17; // [rsp+84h] [rbp+44h]
  struct _LOCK_STATE_EX LockState; // [rsp+90h] [rbp+50h] BYREF
  struct _LOCK_STATE_EX v19; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  v4 = 0;
  LockState.Flags = 0;
  v5 = 0;
  if ( !WorkItemContext )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      (_DWORD)NdisIoWorkItemHandle,
      19,
      10,
      (__int64)WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids,
      (__int64)"Nic != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceObject) & 8) == 0 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      (_DWORD)NdisIoWorkItemHandle,
      19,
      11,
      (__int64)WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids,
      (__int64)"LbfoGlobal.RunningInVM");
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceObject) & 8) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v6 = *((_QWORD *)WorkItemContext + 87);
  NicSrIov = lbfoGetNicSrIov(v6, WorkItemContext);
  if ( (*(_BYTE *)(NicSrIov + 64) & 1) == 0 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v7,
      19,
      12,
      (__int64)WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids,
      (__int64)"SrIov->UpdateMacWIQueued");
    if ( (*(_BYTE *)(NicSrIov + 64) & 1) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  ExAcquireFastMutex((PFAST_MUTEX)(NicSrIov + 8));
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState, 0);
  v9 = *(_BYTE *)(NicSrIov + 64);
  v10 = v9 >> 2;
  if ( ((v9 & 2) != 0) != ((v9 & 4) != 0) )
  {
    v4 = 1;
    if ( (v9 & 4) != 0 )
    {
      v3 = *((_DWORD *)WorkItemContext + 10);
      v5 = *((_WORD *)WorkItemContext + 22);
    }
    else
    {
      v3 = *(_DWORD *)(v6 + 126);
      v5 = *(_WORD *)(v6 + 130);
    }
  }
  *(_BYTE *)(NicSrIov + 64) = (v9 & 0xFB ^ (2 * (v9 & 2))) & 0xFE;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState);
  if ( v4 )
  {
    LOBYTE(v13) = WorkItemContext[680];
    v16 = v3;
    v17 = v5;
    if ( (unsigned int)lbfoIssueOidRequestOnNic(v6, v11, v12, v13, (__int64)&v16) )
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState, 0);
      *(_BYTE *)(NicSrIov + 64) ^= (*(_BYTE *)(NicSrIov + 64) ^ (4 * v10)) & 4;
      *((_DWORD *)WorkItemContext + 191) = 0;
      lbfoUpdateNicPHYState(v6, WorkItemContext);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState);
    }
  }
  ExReleaseFastMutex((PFAST_MUTEX)(NicSrIov + 8));
  v14 = *(struct _NDIS_RW_LOCK_EX **)(v6 + 1584);
  *(_WORD *)&v19.OldIrql = 0;
  v19.Flags = 0;
  NdisAcquireRWLockWrite(v14, &v19, 0);
  if ( (*((_WORD *)WorkItemContext + 85))-- == 1 )
    KeSetEvent((PRKEVENT)(WorkItemContext + 176), 0, 0);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &v19);
}

```

## disassembly

```asm
0x140166ba0  mov     [rsp-38h+arg_8], rbx
0x140166ba5  push    rbp
0x140166ba6  push    rsi
0x140166ba7  push    rdi
0x140166ba8  push    r12
0x140166baa  push    r13
0x140166bac  push    r14
0x140166bae  push    r15
0x140166bb0  mov     rbp, rsp
0x140166bb3  sub     rsp, 40h
0x140166bb7  xor     eax, eax
0x140166bb9  mov     rbx, rcx
0x140166bbc  xor     r15d, r15d
0x140166bbf  mov     word ptr [rbp+LockState.OldIrql], ax
0x140166bc3  xor     r13b, r13b
0x140166bc6  mov     [rbp+LockState.Flags], al
0x140166bc9  lea     rcx, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140166bd0  movzx   r12d, r15w
0x140166bd4  lea     esi, [rax+13h]
0x140166bd7  test    rbx, rbx
0x140166bda  jnz     short loc_140166C0C
0x140166bdc  lea     rax, aNicNull; "Nic != NULL"
0x140166be3  mov     r8d, esi
0x140166be6  mov     [rsp+40h+var_18], rax
0x140166beb  lea     r9d, [r15+0Ah]
0x140166bef  mov     [rsp+40h+var_20], rcx
0x140166bf4  mov     rcx, cs:VmsIfrLog
0x140166bfb  call    WPP_RECORDER_SF_s
0x140166c00  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic != ((void *)0)")
0x140166c05  lea     rcx, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140166c0c  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 8
0x140166c13  jnz     short loc_140166C49
0x140166c15  lea     rax, aLbfoglobalRunn; "LbfoGlobal.RunningInVM"
0x140166c1c  mov     r9d, 0Bh
0x140166c22  mov     [rsp+40h+var_18], rax
0x140166c27  mov     r8d, esi
0x140166c2a  mov     [rsp+40h+var_20], rcx
0x140166c2f  mov     rcx, cs:VmsIfrLog
0x140166c36  call    WPP_RECORDER_SF_s
0x140166c3b  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 8
0x140166c42  jnz     short loc_140166C49
0x140166c44  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "LbfoGlobal.RunningInVM")
0x140166c49  mov     rdi, [rbx+2B8h]
0x140166c50  mov     rdx, rbx
0x140166c53  mov     rcx, rdi
0x140166c56  call    lbfoGetNicSrIov
0x140166c5b  mov     r14, rax
0x140166c5e  test    byte ptr [rax+40h], 1
0x140166c62  jnz     short loc_140166C9D
0x140166c64  mov     rcx, cs:VmsIfrLog
0x140166c6b  lea     rax, aSriovUpdatemac_0; "SrIov->UpdateMacWIQueued"
0x140166c72  mov     [rsp+40h+var_18], rax
0x140166c77  mov     r9d, 0Ch
0x140166c7d  lea     rax, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140166c84  mov     r8d, esi
0x140166c87  mov     [rsp+40h+var_20], rax
0x140166c8c  call    WPP_RECORDER_SF_s
0x140166c91  test    byte ptr [r14+40h], 1
0x140166c96  jnz     short loc_140166C9D
0x140166c98  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "SrIov->UpdateMacWIQueued")
0x140166c9d  lea     rcx, [r14+8]; FastMutex
0x140166ca1  call    cs:__imp_ExAcquireFastMutex
0x140166ca8  nop     dword ptr [rax+rax+00h]
0x140166cad  mov     rcx, [rdi+630h]; Lock
0x140166cb4  lea     rdx, [rbp+LockState]; LockState
0x140166cb8  xor     r8d, r8d; Flags
0x140166cbb  call    cs:__imp_NdisAcquireRWLockWrite
0x140166cc2  nop     dword ptr [rax+rax+00h]
0x140166cc7  mov     cl, [r14+40h]
0x140166ccb  mov     sil, cl
0x140166cce  mov     al, cl
0x140166cd0  shr     sil, 2
0x140166cd4  shr     al, 1
0x140166cd6  mov     dl, sil
0x140166cd9  and     dl, 1
0x140166cdc  and     al, 1
0x140166cde  cmp     al, dl
0x140166ce0  jz      short loc_140166D00
0x140166ce2  mov     r13b, 1
0x140166ce5  test    dl, dl
0x140166ce7  jz      short loc_140166CF4
0x140166ce9  mov     r15d, [rbx+28h]
0x140166ced  movzx   r12d, word ptr [rbx+2Ch]
0x140166cf2  jmp     short loc_140166D00
0x140166cf4  mov     r15d, [rdi+7Eh]
0x140166cf8  movzx   r12d, word ptr [rdi+82h]
0x140166d00  mov     al, cl
0x140166d02  lea     rdx, [rbp+LockState]; LockState
0x140166d06  and     al, 2
0x140166d08  and     cl, 0FBh
0x140166d0b  add     al, al
0x140166d0d  xor     al, cl
0x140166d0f  and     al, 0FEh
0x140166d11  mov     [r14+40h], al
0x140166d15  mov     rcx, [rdi+630h]; Lock
0x140166d1c  call    cs:__imp_NdisReleaseRWLock
0x140166d23  nop     dword ptr [rax+rax+00h]
0x140166d28  test    r13b, r13b
0x140166d2b  jz      loc_140166DB2
0x140166d31  mov     r9b, [rbx+2A8h]
0x140166d38  lea     rax, [rbp+arg_0]
0x140166d3c  mov     rcx, rdi
0x140166d3f  mov     [rsp+40h+var_20], rax
0x140166d44  mov     [rbp+arg_0], r15d
0x140166d48  mov     [rbp+arg_4], r12w
0x140166d4d  call    lbfoIssueOidRequestOnNic
0x140166d52  test    eax, eax
0x140166d54  jz      short loc_140166DB2
0x140166d56  mov     rcx, [rdi+630h]; Lock
0x140166d5d  lea     rdx, [rbp+LockState]; LockState
0x140166d61  xor     r8d, r8d; Flags
0x140166d64  call    cs:__imp_NdisAcquireRWLockWrite
0x140166d6b  nop     dword ptr [rax+rax+00h]
0x140166d70  mov     al, [r14+40h]
0x140166d74  mov     rdx, rbx
0x140166d77  shl     sil, 2
0x140166d7b  mov     rcx, rdi
0x140166d7e  xor     sil, al
0x140166d81  and     sil, 4
0x140166d85  xor     sil, al
0x140166d88  mov     [r14+40h], sil
0x140166d8c  mov     dword ptr [rbx+2FCh], 0
0x140166d96  call    lbfoUpdateNicPHYState
0x140166d9b  mov     rcx, [rdi+630h]; Lock
0x140166da2  lea     rdx, [rbp+LockState]; LockState
0x140166da6  call    cs:__imp_NdisReleaseRWLock
0x140166dad  nop     dword ptr [rax+rax+00h]
0x140166db2  lea     rcx, [r14+8]; FastMutex
0x140166db6  call    cs:__imp_ExReleaseFastMutex
0x140166dbd  nop     dword ptr [rax+rax+00h]
0x140166dc2  mov     rcx, [rdi+630h]; Lock
0x140166dc9  lea     rdx, [rbp+arg_18]; LockState
0x140166dcd  xor     eax, eax
0x140166dcf  xor     r8d, r8d; Flags
0x140166dd2  mov     word ptr [rbp+arg_18.OldIrql], ax
0x140166dd6  mov     [rbp+arg_18.Flags], al
0x140166dd9  call    cs:__imp_NdisAcquireRWLockWrite
0x140166de0  nop     dword ptr [rax+rax+00h]
0x140166de5  mov     eax, 0FFFFh
0x140166dea  add     [rbx+0AAh], ax
0x140166df1  jnz     short loc_140166E0B
0x140166df3  lea     rcx, [rbx+0B0h]; Event
0x140166dfa  xor     r8d, r8d; Wait
0x140166dfd  xor     edx, edx; Increment
0x140166dff  call    cs:__imp_KeSetEvent
0x140166e06  nop     dword ptr [rax+rax+00h]
0x140166e0b  mov     rcx, [rdi+630h]; Lock
0x140166e12  lea     rdx, [rbp+arg_18]; LockState
0x140166e16  call    cs:__imp_NdisReleaseRWLock
0x140166e1d  nop     dword ptr [rax+rax+00h]
0x140166e22  mov     rbx, [rsp+40h+arg_8]
0x140166e2a  add     rsp, 40h
0x140166e2e  pop     r15
0x140166e30  pop     r14
0x140166e32  pop     r13
0x140166e34  pop     r12
0x140166e36  pop     rdi
0x140166e37  pop     rsi
0x140166e38  pop     rbp
0x140166e39  retn
```
