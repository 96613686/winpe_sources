# VmsDIoNicPvtContextCleanup

- ea: `0x140094a70`
- end: `0x140094b7c`
- name: `VmsDIoNicPvtContextCleanup`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x140094a70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140094ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094b64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094b64`
- `NDIS!NdisFreeNetBufferListPool` at `0x140094b4b`
- `NDIS!NdisFreeNetBufferListPool` at `0x140094b4b`
- `NDIS!NdisReleaseRWLock` at `0x140094b23`
- `NDIS!NdisReleaseRWLock` at `0x140094b23`
- `NDIS!NdisAcquireRWLockWrite` at `0x140094a94`
- `NDIS!NdisAcquireRWLockWrite` at `0x140094a94`
- `NDIS!NdisFreeRWLock` at `0x140094b33`
- `NDIS!NdisFreeRWLock` at `0x140094b33`

## string_xrefs

- `0x140094ae9`: `IsListEmpty(&dioNicExt->ReadRequestQueue)`

## pseudocode

```c
void __fastcall VmsDIoNicPvtContextCleanup(__int64 a1, __int64 a2)
{
  int v3; // edx
  _QWORD **v4; // rdi
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  void *v8; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+48h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a2 + 48), &LockState, 0);
  v4 = (_QWORD **)(a2 + 24);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v5[1] != v4 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
      __fastfail(3u);
    *v4 = v6;
    v6[1] = v4;
    ExFreePoolWithTag(v5, 0);
  }
  v7 = (_QWORD *)(a2 + 8);
  if ( (_QWORD *)*v7 != v7 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v3,
      19,
      17,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      "IsListEmpty(&dioNicExt->ReadRequestQueue)");
    if ( (_QWORD *)*v7 != v7 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a2 + 48), &LockState);
  NdisFreeRWLock(*(PNDIS_RW_LOCK_EX *)(a2 + 48));
  v8 = *(void **)(a2 + 56);
  *(_QWORD *)(a2 + 48) = 0;
  NdisFreeNetBufferListPool(v8);
  *(_QWORD *)(a2 + 56) = 0;
  ExFreePoolWithTag((PVOID)a2, 0);
}

```

## disassembly

```asm
0x140094a70  mov     [rsp+arg_0], rbx
0x140094a75  push    rdi
0x140094a76  sub     rsp, 30h
0x140094a7a  mov     rbx, rdx
0x140094a7d  xor     eax, eax
0x140094a7f  xor     r8d, r8d; Flags
0x140094a82  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x140094a87  lea     rdx, [rsp+38h+LockState]; LockState
0x140094a8c  mov     [rsp+38h+LockState.Flags], al
0x140094a90  mov     rcx, [rbx+30h]; Lock
0x140094a94  call    cs:__imp_NdisAcquireRWLockWrite
0x140094a9b  nop     dword ptr [rax+rax+00h]
0x140094aa0  lea     rdi, [rbx+18h]
0x140094aa4  mov     rcx, [rdi]; P
0x140094aa7  cmp     rcx, rdi
0x140094aaa  jz      short loc_140094AD9
0x140094aac  cmp     [rcx+8], rdi
0x140094ab0  jnz     short loc_140094AD2
0x140094ab2  mov     rax, [rcx]
0x140094ab5  cmp     [rax+8], rcx
0x140094ab9  jnz     short loc_140094AD2
0x140094abb  mov     [rdi], rax
0x140094abe  xor     edx, edx; Tag
0x140094ac0  mov     [rax+8], rdi
0x140094ac4  call    cs:__imp_ExFreePoolWithTag
0x140094acb  nop     dword ptr [rax+rax+00h]
0x140094ad0  jmp     short loc_140094AA4
0x140094ad2  mov     ecx, 3
0x140094ad7  int     29h; Win8: RtlFailFast(ecx)
0x140094ad9  lea     rdi, [rbx+8]
0x140094add  cmp     [rdi], rdi
0x140094ae0  jz      short loc_140094B1A
0x140094ae2  mov     rcx, cs:VmsIfrLog
0x140094ae9  lea     rax, aIslistemptyDio_0; "IsListEmpty(&dioNicExt->ReadRequestQueu"...
0x140094af0  mov     [rsp+38h+var_10], rax
0x140094af5  mov     r9d, 11h
0x140094afb  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x140094b02  mov     [rsp+38h+var_18], rax
0x140094b07  lea     r8d, [r9+2]
0x140094b0b  call    WPP_RECORDER_SF_s
0x140094b10  cmp     [rdi], rdi
0x140094b13  jz      short loc_140094B1A
0x140094b15  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "IsListEmpty(&dioNicExt->ReadRequestQueue)")
0x140094b1a  mov     rcx, [rbx+30h]; Lock
0x140094b1e  lea     rdx, [rsp+38h+LockState]; LockState
0x140094b23  call    cs:__imp_NdisReleaseRWLock
0x140094b2a  nop     dword ptr [rax+rax+00h]
0x140094b2f  mov     rcx, [rbx+30h]; Lock
0x140094b33  call    cs:__imp_NdisFreeRWLock
0x140094b3a  nop     dword ptr [rax+rax+00h]
0x140094b3f  mov     rcx, [rbx+38h]; PoolHandle
0x140094b43  mov     qword ptr [rbx+30h], 0
0x140094b4b  call    cs:__imp_NdisFreeNetBufferListPool
0x140094b52  nop     dword ptr [rax+rax+00h]
0x140094b57  xor     edx, edx; Tag
0x140094b59  mov     qword ptr [rbx+38h], 0
0x140094b61  mov     rcx, rbx; P
0x140094b64  call    cs:__imp_ExFreePoolWithTag
0x140094b6b  nop     dword ptr [rax+rax+00h]
0x140094b70  mov     rbx, [rsp+38h+arg_0]
0x140094b75  add     rsp, 30h
0x140094b79  pop     rdi
0x140094b7a  retn
```
