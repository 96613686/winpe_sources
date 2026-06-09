# lbfoLACPSendLacpduWorkItem

- ea: `0x14016dbd0`
- end: `0x14016dce0`
- name: `lbfoLACPSendLacpduWorkItem`
- size: `272`
- prototype: `NDIS_IO_WORKITEM_FUNCTION`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14009b204`
- `0x14016dbd0`

## import_xrefs

- `NDIS!NdisMSleep` at `0x14016dc66`
- `NDIS!NdisMSleep` at `0x14016dc66`
- `NDIS!NdisReleaseRWLock` at `0x14016dc55`
- `NDIS!NdisReleaseRWLock` at `0x14016dcc6`
- `NDIS!NdisReleaseRWLock` at `0x14016dc55`
- `NDIS!NdisReleaseRWLock` at `0x14016dcc6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016dc05`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016dc81`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016dc05`
- `NDIS!NdisAcquireRWLockWrite` at `0x14016dc81`
- `NDIS!NdisFreeIoWorkItem` at `0x14016dc92`
- `NDIS!NdisFreeIoWorkItem` at `0x14016dc92`

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
0x14016dbd0  push    rbx
0x14016dbd2  push    rbp
0x14016dbd3  push    rsi
0x14016dbd4  push    rdi
0x14016dbd5  push    r14
0x14016dbd7  push    r15
0x14016dbd9  sub     rsp, 28h
0x14016dbdd  mov     rdi, [rcx+18h]
0x14016dbe1  xor     eax, eax
0x14016dbe3  mov     rsi, [rcx+10h]
0x14016dbe7  mov     r14, rdx
0x14016dbea  mov     rbp, rcx
0x14016dbed  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14016dbf2  mov     [rsp+58h+LockState.Flags], al
0x14016dbf6  lea     rdx, [rsp+58h+LockState]; LockState
0x14016dbfb  mov     rcx, [rdi+630h]; Lock
0x14016dc02  xor     r8d, r8d; Flags
0x14016dc05  call    cs:__imp_NdisAcquireRWLockWrite
0x14016dc0c  nop     dword ptr [rax+rax+00h]
0x14016dc11  movzx   ebx, byte ptr [rbp+0D0h]
0x14016dc18  mov     r15, 0FFFFF78000000320h
0x14016dc22  mov     rbx, [rbp+rbx*8+0B8h]
0x14016dc2a  mov     rax, [r15]
0x14016dc2d  xor     ecx, ecx
0x14016dc2f  sub     rax, rbx
0x14016dc32  cmovns  rcx, rax
0x14016dc36  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x14016dc3c  imul    rcx, rax
0x14016dc40  cmp     rcx, 989680h
0x14016dc47  jnb     short loc_14016DC8F
0x14016dc49  mov     rcx, [rdi+630h]; Lock
0x14016dc50  lea     rdx, [rsp+58h+LockState]; LockState
0x14016dc55  call    cs:__imp_NdisReleaseRWLock
0x14016dc5c  nop     dword ptr [rax+rax+00h]
0x14016dc61  mov     ecx, 0C350h; MicrosecondsToSleep
0x14016dc66  call    cs:__imp_NdisMSleep
0x14016dc6d  nop     dword ptr [rax+rax+00h]
0x14016dc72  mov     rcx, [rdi+630h]; Lock
0x14016dc79  lea     rdx, [rsp+58h+LockState]; LockState
0x14016dc7e  xor     r8d, r8d; Flags
0x14016dc81  call    cs:__imp_NdisAcquireRWLockWrite
0x14016dc88  nop     dword ptr [rax+rax+00h]
0x14016dc8d  jmp     short loc_14016DC2A
0x14016dc8f  mov     rcx, r14; NdisIoWorkItemHandle
0x14016dc92  call    cs:__imp_NdisFreeIoWorkItem
0x14016dc99  nop     dword ptr [rax+rax+00h]
0x14016dc9e  mov     byte ptr [rbp+0B0h], 0
0x14016dca5  cmp     qword ptr [rsi+320h], 0
0x14016dcad  jz      short loc_14016DCBA
0x14016dcaf  mov     rdx, rsi
0x14016dcb2  mov     rcx, rdi
0x14016dcb5  call    lbfoLACPTransmitMachine
0x14016dcba  mov     rcx, [rdi+630h]; Lock
0x14016dcc1  lea     rdx, [rsp+58h+LockState]; LockState
0x14016dcc6  call    cs:__imp_NdisReleaseRWLock
0x14016dccd  nop     dword ptr [rax+rax+00h]
0x14016dcd2  add     rsp, 28h
0x14016dcd6  pop     r15
0x14016dcd8  pop     r14
0x14016dcda  pop     rdi
0x14016dcdb  pop     rsi
0x14016dcdc  pop     rbp
0x14016dcdd  pop     rbx
0x14016dcde  retn
```
