# lbfoUpdateNicMacWorkItem

- ea: `0x140166c10`
- end: `0x140166eab`
- name: `lbfoUpdateNicMacWorkItem`
- size: `667`
- prototype: `NDIS_IO_WORKITEM_FUNCTION`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x140160a58`
- `0x140165fa8`
- `0x140166c10`
- `0x1401684d4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140166e6f`
- `ntoskrnl!KeSetEvent` at `0x140166e6f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140166d11`
- `ntoskrnl!ExAcquireFastMutex` at `0x140166d11`
- `ntoskrnl!ExReleaseFastMutex` at `0x140166e26`
- `ntoskrnl!ExReleaseFastMutex` at `0x140166e26`
- `NDIS!NdisReleaseRWLock` at `0x140166d8c`
- `NDIS!NdisReleaseRWLock` at `0x140166e16`
- `NDIS!NdisReleaseRWLock` at `0x140166e86`
- `NDIS!NdisReleaseRWLock` at `0x140166d8c`
- `NDIS!NdisReleaseRWLock` at `0x140166e16`
- `NDIS!NdisReleaseRWLock` at `0x140166e86`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166d2b`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166dd4`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166e49`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166d2b`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166dd4`
- `NDIS!NdisAcquireRWLockWrite` at `0x140166e49`

## string_xrefs

- `0x140166cdb`: `SrIov->UpdateMacWIQueued`

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
0x140166c10  mov     [rsp-38h+arg_8], rbx
0x140166c15  push    rbp
0x140166c16  push    rsi
0x140166c17  push    rdi
0x140166c18  push    r12
0x140166c1a  push    r13
0x140166c1c  push    r14
0x140166c1e  push    r15
0x140166c20  mov     rbp, rsp
0x140166c23  sub     rsp, 40h
0x140166c27  xor     eax, eax
0x140166c29  mov     rbx, rcx
0x140166c2c  xor     r15d, r15d
0x140166c2f  mov     word ptr [rbp+LockState.OldIrql], ax
0x140166c33  xor     r13b, r13b
0x140166c36  mov     [rbp+LockState.Flags], al
0x140166c39  lea     rcx, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140166c40  movzx   r12d, r15w
0x140166c44  lea     esi, [rax+13h]
0x140166c47  test    rbx, rbx
0x140166c4a  jnz     short loc_140166C7C
0x140166c4c  lea     rax, aNicNull; "Nic != NULL"
0x140166c53  mov     r8d, esi
0x140166c56  mov     [rsp+40h+var_18], rax
0x140166c5b  lea     r9d, [r15+0Ah]
0x140166c5f  mov     [rsp+40h+var_20], rcx
0x140166c64  mov     rcx, cs:VmsIfrLog
0x140166c6b  call    WPP_RECORDER_SF_s
0x140166c70  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic != ((void *)0)")
0x140166c75  lea     rcx, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140166c7c  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 8
0x140166c83  jnz     short loc_140166CB9
0x140166c85  lea     rax, aLbfoglobalRunn; "LbfoGlobal.RunningInVM"
0x140166c8c  mov     r9d, 0Bh
0x140166c92  mov     [rsp+40h+var_18], rax
0x140166c97  mov     r8d, esi
0x140166c9a  mov     [rsp+40h+var_20], rcx
0x140166c9f  mov     rcx, cs:VmsIfrLog
0x140166ca6  call    WPP_RECORDER_SF_s
0x140166cab  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 8
0x140166cb2  jnz     short loc_140166CB9
0x140166cb4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "LbfoGlobal.RunningInVM")
0x140166cb9  mov     rdi, [rbx+2B8h]
0x140166cc0  mov     rdx, rbx
0x140166cc3  mov     rcx, rdi
0x140166cc6  call    lbfoGetNicSrIov
0x140166ccb  mov     r14, rax
0x140166cce  test    byte ptr [rax+40h], 1
0x140166cd2  jnz     short loc_140166D0D
0x140166cd4  mov     rcx, cs:VmsIfrLog
0x140166cdb  lea     rax, aSriovUpdatemac_0; "SrIov->UpdateMacWIQueued"
0x140166ce2  mov     [rsp+40h+var_18], rax
0x140166ce7  mov     r9d, 0Ch
0x140166ced  lea     rax, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140166cf4  mov     r8d, esi
0x140166cf7  mov     [rsp+40h+var_20], rax
0x140166cfc  call    WPP_RECORDER_SF_s
0x140166d01  test    byte ptr [r14+40h], 1
0x140166d06  jnz     short loc_140166D0D
0x140166d08  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "SrIov->UpdateMacWIQueued")
0x140166d0d  lea     rcx, [r14+8]; FastMutex
0x140166d11  call    cs:__imp_ExAcquireFastMutex
0x140166d18  nop     dword ptr [rax+rax+00h]
0x140166d1d  mov     rcx, [rdi+630h]; Lock
0x140166d24  lea     rdx, [rbp+LockState]; LockState
0x140166d28  xor     r8d, r8d; Flags
0x140166d2b  call    cs:__imp_NdisAcquireRWLockWrite
0x140166d32  nop     dword ptr [rax+rax+00h]
0x140166d37  mov     cl, [r14+40h]
0x140166d3b  mov     sil, cl
0x140166d3e  mov     al, cl
0x140166d40  shr     sil, 2
0x140166d44  shr     al, 1
0x140166d46  mov     dl, sil
0x140166d49  and     dl, 1
0x140166d4c  and     al, 1
0x140166d4e  cmp     al, dl
0x140166d50  jz      short loc_140166D70
0x140166d52  mov     r13b, 1
0x140166d55  test    dl, dl
0x140166d57  jz      short loc_140166D64
0x140166d59  mov     r15d, [rbx+28h]
0x140166d5d  movzx   r12d, word ptr [rbx+2Ch]
0x140166d62  jmp     short loc_140166D70
0x140166d64  mov     r15d, [rdi+7Eh]
0x140166d68  movzx   r12d, word ptr [rdi+82h]
0x140166d70  mov     al, cl
0x140166d72  lea     rdx, [rbp+LockState]; LockState
0x140166d76  and     al, 2
0x140166d78  and     cl, 0FBh
0x140166d7b  add     al, al
0x140166d7d  xor     al, cl
0x140166d7f  and     al, 0FEh
0x140166d81  mov     [r14+40h], al
0x140166d85  mov     rcx, [rdi+630h]; Lock
0x140166d8c  call    cs:__imp_NdisReleaseRWLock
0x140166d93  nop     dword ptr [rax+rax+00h]
0x140166d98  test    r13b, r13b
0x140166d9b  jz      loc_140166E22
0x140166da1  mov     r9b, [rbx+2A8h]
0x140166da8  lea     rax, [rbp+arg_0]
0x140166dac  mov     rcx, rdi
0x140166daf  mov     [rsp+40h+var_20], rax
0x140166db4  mov     [rbp+arg_0], r15d
0x140166db8  mov     [rbp+arg_4], r12w
0x140166dbd  call    lbfoIssueOidRequestOnNic
0x140166dc2  test    eax, eax
0x140166dc4  jz      short loc_140166E22
0x140166dc6  mov     rcx, [rdi+630h]; Lock
0x140166dcd  lea     rdx, [rbp+LockState]; LockState
0x140166dd1  xor     r8d, r8d; Flags
0x140166dd4  call    cs:__imp_NdisAcquireRWLockWrite
0x140166ddb  nop     dword ptr [rax+rax+00h]
0x140166de0  mov     al, [r14+40h]
0x140166de4  mov     rdx, rbx
0x140166de7  shl     sil, 2
0x140166deb  mov     rcx, rdi
0x140166dee  xor     sil, al
0x140166df1  and     sil, 4
0x140166df5  xor     sil, al
0x140166df8  mov     [r14+40h], sil
0x140166dfc  mov     dword ptr [rbx+2FCh], 0
0x140166e06  call    lbfoUpdateNicPHYState
0x140166e0b  mov     rcx, [rdi+630h]; Lock
0x140166e12  lea     rdx, [rbp+LockState]; LockState
0x140166e16  call    cs:__imp_NdisReleaseRWLock
0x140166e1d  nop     dword ptr [rax+rax+00h]
0x140166e22  lea     rcx, [r14+8]; FastMutex
0x140166e26  call    cs:__imp_ExReleaseFastMutex
0x140166e2d  nop     dword ptr [rax+rax+00h]
0x140166e32  mov     rcx, [rdi+630h]; Lock
0x140166e39  lea     rdx, [rbp+arg_18]; LockState
0x140166e3d  xor     eax, eax
0x140166e3f  xor     r8d, r8d; Flags
0x140166e42  mov     word ptr [rbp+arg_18.OldIrql], ax
0x140166e46  mov     [rbp+arg_18.Flags], al
0x140166e49  call    cs:__imp_NdisAcquireRWLockWrite
0x140166e50  nop     dword ptr [rax+rax+00h]
0x140166e55  mov     eax, 0FFFFh
0x140166e5a  add     [rbx+0AAh], ax
0x140166e61  jnz     short loc_140166E7B
0x140166e63  lea     rcx, [rbx+0B0h]; Event
0x140166e6a  xor     r8d, r8d; Wait
0x140166e6d  xor     edx, edx; Increment
0x140166e6f  call    cs:__imp_KeSetEvent
0x140166e76  nop     dword ptr [rax+rax+00h]
0x140166e7b  mov     rcx, [rdi+630h]; Lock
0x140166e82  lea     rdx, [rbp+arg_18]; LockState
0x140166e86  call    cs:__imp_NdisReleaseRWLock
0x140166e8d  nop     dword ptr [rax+rax+00h]
0x140166e92  mov     rbx, [rsp+40h+arg_8]
0x140166e9a  add     rsp, 40h
0x140166e9e  pop     r15
0x140166ea0  pop     r14
0x140166ea2  pop     r13
0x140166ea4  pop     r12
0x140166ea6  pop     rdi
0x140166ea7  pop     rsi
0x140166ea8  pop     rbp
0x140166ea9  retn
```
