# lbfoLACPSendLacpduWorkItem

- ea: `0x14016db60`
- end: `0x14016dc70`
- name: `lbfoLACPSendLacpduWorkItem`
- size: `272`
- prototype: `NDIS_IO_WORKITEM_FUNCTION`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14009b204`
- `0x14016db60`

## import_xrefs

- `NDIS!NdisMSleep` at `0x14016dbf6`
- `NDIS!NdisMSleep` at `0x14016dbf6`
- `NDIS!NdisReleaseRWLock` at `0x14016dbe5`
- `NDIS!NdisReleaseRWLock` at `0x14016dc56`
- `NDIS!NdisReleaseRWLock` at `0x14016dbe5`
- `NDIS!NdisReleaseRWLock` at `0x14016dc56`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016db95`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016dc11`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016db95`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016dc11`
- `NDIS!NdisFreeIoWorkItem` at `0x14016dc22`
- `NDIS!NdisFreeIoWorkItem` at `0x14016dc22`

## pseudocode

```c
void __fastcall lbfoLACPSendLacpduWorkItem(_QWORD *WorkItemContext, NDIS_HANDLE NdisIoWorkItemHandle)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  __int64 v6; // rbx
  __int64 v7; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF

  v2 = WorkItemContext[3];
  v3 = WorkItemContext[2];
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState, 0);
  v6 = WorkItemContext[*((unsigned __int8 *)WorkItemContext + 208) + 23];
  while ( 1 )
  {
    v7 = 0;
    if ( MEMORY[0xFFFFF78000000320] - v6 >= 0 )
      v7 = MEMORY[0xFFFFF78000000320] - v6;
    if ( (unsigned __int64)LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) * v7 >= 0x989680 )
      break;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState);
    NdisMSleep(0xC350u);
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState, 0);
  }
  NdisFreeIoWorkItem(NdisIoWorkItemHandle);
  *((_BYTE *)WorkItemContext + 176) = 0;
  if ( *(_QWORD *)(v3 + 800) )
    lbfoLACPTransmitMachine(v2, v3);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState);
}

```

## disassembly

```asm
0x14016db60  push    rbx
0x14016db62  push    rbp
0x14016db63  push    rsi
0x14016db64  push    rdi
0x14016db65  push    r14
0x14016db67  push    r15
0x14016db69  sub     rsp, 28h
0x14016db6d  mov     rdi, [rcx+18h]
0x14016db71  xor     eax, eax
0x14016db73  mov     rsi, [rcx+10h]
0x14016db77  mov     r14, rdx
0x14016db7a  mov     rbp, rcx
0x14016db7d  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14016db82  mov     [rsp+58h+LockState.Flags], al
0x14016db86  lea     rdx, [rsp+58h+LockState]; LockState
0x14016db8b  mov     rcx, [rdi+630h]; Lock
0x14016db92  xor     r8d, r8d; Flags
0x14016db95  call    cs:__imp_NdisAcquireRWLockWrite
0x14016db9c  nop     dword ptr [rax+rax+00h]
0x14016dba1  movzx   ebx, byte ptr [rbp+0D0h]
0x14016dba8  mov     r15, 0FFFFF78000000320h
0x14016dbb2  mov     rbx, [rbp+rbx*8+0B8h]
0x14016dbba  mov     rax, [r15]
0x14016dbbd  xor     ecx, ecx
0x14016dbbf  sub     rax, rbx
0x14016dbc2  cmovns  rcx, rax
0x14016dbc6  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x14016dbcc  imul    rcx, rax
0x14016dbd0  cmp     rcx, 989680h
0x14016dbd7  jnb     short loc_14016DC1F
0x14016dbd9  mov     rcx, [rdi+630h]; Lock
0x14016dbe0  lea     rdx, [rsp+58h+LockState]; LockState
0x14016dbe5  call    cs:__imp_NdisReleaseRWLock
0x14016dbec  nop     dword ptr [rax+rax+00h]
0x14016dbf1  mov     ecx, 0C350h; MicrosecondsToSleep
0x14016dbf6  call    cs:__imp_NdisMSleep
0x14016dbfd  nop     dword ptr [rax+rax+00h]
0x14016dc02  mov     rcx, [rdi+630h]; Lock
0x14016dc09  lea     rdx, [rsp+58h+LockState]; LockState
0x14016dc0e  xor     r8d, r8d; Flags
0x14016dc11  call    cs:__imp_NdisAcquireRWLockWrite
0x14016dc18  nop     dword ptr [rax+rax+00h]
0x14016dc1d  jmp     short loc_14016DBBA
0x14016dc1f  mov     rcx, r14; NdisIoWorkItemHandle
0x14016dc22  call    cs:__imp_NdisFreeIoWorkItem
0x14016dc29  nop     dword ptr [rax+rax+00h]
0x14016dc2e  mov     byte ptr [rbp+0B0h], 0
0x14016dc35  cmp     qword ptr [rsi+320h], 0
0x14016dc3d  jz      short loc_14016DC4A
0x14016dc3f  mov     rdx, rsi
0x14016dc42  mov     rcx, rdi
0x14016dc45  call    lbfoLACPTransmitMachine
0x14016dc4a  mov     rcx, [rdi+630h]; Lock
0x14016dc51  lea     rdx, [rsp+58h+LockState]; LockState
0x14016dc56  call    cs:__imp_NdisReleaseRWLock
0x14016dc5d  nop     dword ptr [rax+rax+00h]
0x14016dc62  add     rsp, 28h
0x14016dc66  pop     r15
0x14016dc68  pop     r14
0x14016dc6a  pop     rdi
0x14016dc6b  pop     rsi
0x14016dc6c  pop     rbp
0x14016dc6d  pop     rbx
0x14016dc6e  retn
```
