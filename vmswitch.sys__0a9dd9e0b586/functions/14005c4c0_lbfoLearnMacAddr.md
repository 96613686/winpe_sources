# lbfoLearnMacAddr

- ea: `0x14005c4c0`
- end: `0x14005c686`
- name: `lbfoLearnMacAddr`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14005c370`

## callees

- `0x14005c4c0`
- `0x14005c68c`
- `0x14005c6c4`
- `0x14005c748`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x14005c58d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14005c58d`
- `NDIS!NdisAcquireRWLockRead` at `0x14005c4f0`
- `NDIS!NdisAcquireRWLockRead` at `0x14005c675`
- `NDIS!NdisAcquireRWLockRead` at `0x14005c4f0`
- `NDIS!NdisAcquireRWLockRead` at `0x14005c675`
- `NDIS!NdisReleaseRWLock` at `0x14005c5c1`
- `NDIS!NdisReleaseRWLock` at `0x14005c5ed`
- `NDIS!NdisReleaseRWLock` at `0x14005c65a`
- `NDIS!NdisReleaseRWLock` at `0x14005c5c1`
- `NDIS!NdisReleaseRWLock` at `0x14005c5ed`
- `NDIS!NdisReleaseRWLock` at `0x14005c65a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005c608`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005c608`
- `NDIS!NdisGetDataBuffer` at `0x14005c515`
- `NDIS!NdisGetDataBuffer` at `0x14005c515`

## pseudocode

```c
void __fastcall lbfoLearnMacAddr(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  char *DataBuffer; // rsi
  unsigned int NblVlan; // ebp
  __int64 VmsPortFromVmsId; // rdi
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v8; // rax
  __int64 v9; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h]
  int v12; // [rsp+60h] [rbp+18h] BYREF
  __int16 v13; // [rsp+64h] [rbp+1Ch]

  v2 = *(_QWORD *)(a1 + 16);
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState, 0);
  DataBuffer = (char *)NdisGetDataBuffer(*(PNET_BUFFER *)(a2 + 8), 0xEu, 0, 1u, 0);
  if ( DataBuffer )
  {
    NblVlan = (unsigned __int16)GetNblVlan(a1, a2);
    VmsPortFromVmsId = lbfoGetVmsPortFromVmsId(v2, *(unsigned __int16 *)(a2 + 298));
    if ( VmsPortFromVmsId )
    {
      v11 = *(unsigned int *)(DataBuffer + 6);
      WORD2(v11) = *((_WORD *)DataBuffer + 5);
      v8 = RtlLookupEntryHashTable(
             (PRTL_DYNAMIC_HASH_TABLE)(v2 + 1648),
             v11 | ((unsigned __int64)NblVlan << 48) | 0x8000000000000000uLL,
             0);
      if ( v8 && (((__int64)v8[1].Linkage.Blink & 1) == 0 || v8[2].Signature == VmsPortFromVmsId) )
      {
        v8[3].Signature = MEMORY[0xFFFFF78000000320];
      }
      else
      {
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState);
        NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState, 0);
        v12 = *(_DWORD *)(DataBuffer + 6);
        v13 = *((_WORD *)DataBuffer + 5);
        v9 = lbfoLearnMacOnVmsPort(v2, VmsPortFromVmsId, &v12, (unsigned __int16)NblVlan);
        if ( v9 )
          *(_QWORD *)(v9 + 88) = MEMORY[0xFFFFF78000000320];
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState);
        NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState, 0);
      }
    }
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v2 + 1584), &LockState);
}

```

## disassembly

```asm
0x14005c4c0  mov     [rsp+arg_18], rbx
0x14005c4c5  push    rbp
0x14005c4c6  push    rsi
0x14005c4c7  push    rdi
0x14005c4c8  sub     rsp, 30h
0x14005c4cc  mov     rbx, [rcx+10h]
0x14005c4d0  xor     eax, eax
0x14005c4d2  mov     rdi, rdx
0x14005c4d5  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14005c4da  mov     rbp, rcx
0x14005c4dd  mov     [rsp+48h+LockState.Flags], al
0x14005c4e1  xor     r8d, r8d; Flags
0x14005c4e4  lea     rdx, [rsp+48h+LockState]; LockState
0x14005c4e9  mov     rcx, [rbx+630h]; Lock
0x14005c4f0  call    cs:__imp_NdisAcquireRWLockRead
0x14005c4f7  nop     dword ptr [rax+rax+00h]
0x14005c4fc  mov     rcx, [rdi+8]; NetBuffer
0x14005c500  mov     r9d, 1; AlignMultiple
0x14005c506  xor     r8d, r8d; Storage
0x14005c509  mov     [rsp+48h+AlignOffset], 0; AlignOffset
0x14005c511  lea     edx, [r9+0Dh]; BytesNeeded
0x14005c515  call    cs:__imp_NdisGetDataBuffer
0x14005c51c  nop     dword ptr [rax+rax+00h]
0x14005c521  mov     rsi, rax
0x14005c524  test    rax, rax
0x14005c527  jz      loc_14005C5B5
0x14005c52d  mov     rdx, rdi
0x14005c530  mov     rcx, rbp
0x14005c533  call    GetNblVlan
0x14005c538  movzx   edx, word ptr [rdi+12Ah]
0x14005c53f  mov     rcx, rbx
0x14005c542  movzx   ebp, ax
0x14005c545  call    lbfoGetVmsPortFromVmsId
0x14005c54a  mov     rdi, rax
0x14005c54d  test    rax, rax
0x14005c550  jz      short loc_14005C5B5
0x14005c552  mov     ecx, [rsi+6]
0x14005c555  mov     rax, 8000000000000000h
0x14005c55f  mov     [rsp+48h+arg_8], 0
0x14005c568  mov     edx, ebp
0x14005c56a  mov     dword ptr [rsp+48h+arg_8], ecx
0x14005c56e  xor     r8d, r8d; Context
0x14005c571  movzx   ecx, word ptr [rsi+0Ah]
0x14005c575  mov     word ptr [rsp+48h+arg_8+4], cx
0x14005c57a  lea     rcx, [rbx+670h]; HashTable
0x14005c581  shl     rdx, 30h
0x14005c585  or      rdx, [rsp+48h+arg_8]
0x14005c58a  or      rdx, rax; Signature
0x14005c58d  call    cs:__imp_RtlLookupEntryHashTable
0x14005c594  nop     dword ptr [rax+rax+00h]
0x14005c599  mov     rdx, rax
0x14005c59c  test    rax, rax
0x14005c59f  jz      short loc_14005C5E1
0x14005c5a1  test    byte ptr [rax+20h], 1
0x14005c5a5  jnz     short loc_14005C5DB
0x14005c5a7  mov     rax, ds:0FFFFF78000000320h
0x14005c5b1  mov     [rdx+58h], rax
0x14005c5b5  mov     rcx, [rbx+630h]; Lock
0x14005c5bc  lea     rdx, [rsp+48h+LockState]; LockState
0x14005c5c1  call    cs:__imp_NdisReleaseRWLock
0x14005c5c8  nop     dword ptr [rax+rax+00h]
0x14005c5cd  mov     rbx, [rsp+48h+arg_18]
0x14005c5d2  add     rsp, 30h
0x14005c5d6  pop     rdi
0x14005c5d7  pop     rsi
0x14005c5d8  pop     rbp
0x14005c5d9  retn
0x14005c5db  cmp     [rax+40h], rdi
0x14005c5df  jz      short loc_14005C5A7
0x14005c5e1  mov     rcx, [rbx+630h]; Lock
0x14005c5e8  lea     rdx, [rsp+48h+LockState]; LockState
0x14005c5ed  call    cs:__imp_NdisReleaseRWLock
0x14005c5f4  nop     dword ptr [rax+rax+00h]
0x14005c5f9  mov     rcx, [rbx+630h]; Lock
0x14005c600  lea     rdx, [rsp+48h+LockState]; LockState
0x14005c605  xor     r8d, r8d; Flags
0x14005c608  call    cs:__imp_NdisAcquireRWLockWrite
0x14005c60f  nop     dword ptr [rax+rax+00h]
0x14005c614  mov     eax, [rsi+6]
0x14005c617  lea     r8, [rsp+48h+arg_10]
0x14005c61c  mov     [rsp+48h+arg_10], eax
0x14005c620  movzx   r9d, bp
0x14005c624  movzx   eax, word ptr [rsi+0Ah]
0x14005c628  mov     rdx, rdi
0x14005c62b  mov     rcx, rbx
0x14005c62e  mov     [rsp+48h+arg_14], ax
0x14005c633  call    lbfoLearnMacOnVmsPort
0x14005c638  mov     rcx, rax
0x14005c63b  test    rax, rax
0x14005c63e  jz      short loc_14005C64E
0x14005c640  mov     rax, ds:0FFFFF78000000320h
0x14005c64a  mov     [rcx+58h], rax
0x14005c64e  mov     rcx, [rbx+630h]; Lock
0x14005c655  lea     rdx, [rsp+48h+LockState]; LockState
0x14005c65a  call    cs:__imp_NdisReleaseRWLock
0x14005c661  nop     dword ptr [rax+rax+00h]
0x14005c666  mov     rcx, [rbx+630h]; Lock
0x14005c66d  lea     rdx, [rsp+48h+LockState]; LockState
0x14005c672  xor     r8d, r8d; Flags
0x14005c675  call    cs:__imp_NdisAcquireRWLockRead
0x14005c67c  nop     dword ptr [rax+rax+00h]
0x14005c681  jmp     loc_14005C5B5
```
