# VmsScpIpsecOffloadSaInsertToSadb

- ea: `0x140150dc4`
- end: `0x140150f29`
- name: `VmsScpIpsecOffloadSaInsertToSadb`
- size: `357`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14014fb30`

## callees

- `0x140070100`
- `0x140150d30`
- `0x140150d74`
- `0x140150dc4`
- `0x140151928`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150e4e`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150eb5`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150ee2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150e4e`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150eb5`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150ee2`
- `NDIS!NdisReleaseReadWriteLock` at `0x140150f08`
- `NDIS!NdisReleaseReadWriteLock` at `0x140150f08`
- `NDIS!NdisAcquireReadWriteLock` at `0x140150e32`
- `NDIS!NdisAcquireReadWriteLock` at `0x140150e32`

## pseudocode

```c
void __fastcall VmsScpIpsecOffloadSaInsertToSadb(PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry, __int64 a2)
{
  ULONG_PTR v4; // rbx
  __int64 v5; // rax
  ULONG_PTR v6; // rbp
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  struct _LOCK_STATE LockState; // [rsp+80h] [rbp+8h] BYREF
  ULONG_PTR Signature; // [rsp+90h] [rbp+18h] BYREF

  LockState = 0;
  v4 = VmsScpIpsecOffloadSaComputeHandlePlusPortSignature(&Entry[4]);
  v5 = VmsScpIpsecOffloadSaComputeIpSpiSignature((char *)&Entry[5].Signature + 4, LODWORD(Entry[6].Signature));
  Signature = 0;
  v6 = v5;
  VmsScpIpsecGenericUpdateHash(a2, 8, &Signature);
  NdisAcquireReadWriteLock((PNDIS_RW_LOCK)&WPP_MAIN_CB.Dpc.DpcData, 1u, &LockState);
  RtlInsertEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.DeferredRoutine, Entry, v4, 0);
  _InterlockedIncrement((volatile signed __int32 *)&Entry[4].Linkage.Blink);
  _InterlockedIncrement((volatile signed __int32 *)&Entry[6].Signature + 1);
  if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_qqDq(WPP_GLOBAL_Control->DeviceExtension, v7, v8, v9);
  RtlInsertEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.DeferredContext, Entry + 2, v6, 0);
  _InterlockedIncrement((volatile signed __int32 *)&Entry[4].Linkage.Blink);
  _InterlockedIncrement((volatile signed __int32 *)&Entry[7]);
  RtlInsertEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.SystemArgument1, Entry + 1, Signature, 0);
  _InterlockedIncrement((volatile signed __int32 *)&Entry[4].Linkage.Blink);
  _InterlockedIncrement((volatile signed __int32 *)&Entry[7].Linkage.Flink + 1);
  NdisReleaseReadWriteLock((PNDIS_RW_LOCK)&WPP_MAIN_CB.Dpc.DpcData, &LockState);
}

```

## disassembly

```asm
0x140150dc4  mov     rax, rsp
0x140150dc7  mov     [rax+10h], rbx
0x140150dcb  push    rbp
0x140150dcc  push    rsi
0x140150dcd  push    rdi
0x140150dce  push    r12
0x140150dd0  push    r14
0x140150dd2  sub     rsp, 50h
0x140150dd6  mov     rdi, rcx
0x140150dd9  xor     r12d, r12d
0x140150ddc  add     rcx, 60h ; '`'
0x140150de0  mov     [rax+8], r12d
0x140150de4  mov     rsi, rdx
0x140150de7  call    VmsScpIpsecOffloadSaComputeHandlePlusPortSignature
0x140150dec  mov     edx, [rdi+0A0h]
0x140150df2  lea     rcx, [rdi+8Ch]
0x140150df9  mov     rbx, rax
0x140150dfc  call    VmsScpIpsecOffloadSaComputeIpSpiSignature
0x140150e01  lea     r8, [rsp+78h+Signature]
0x140150e09  mov     [rsp+78h+Signature], r12
0x140150e11  lea     edx, [r12+8]
0x140150e16  mov     rcx, rsi
0x140150e19  mov     rbp, rax
0x140150e1c  call    VmsScpIpsecGenericUpdateHash
0x140150e21  mov     dl, 1; fWrite
0x140150e23  lea     r8, [rsp+78h+LockState]; LockState
0x140150e2b  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x140150e32  call    cs:__imp_NdisAcquireReadWriteLock
0x140150e39  nop     dword ptr [rax+rax+00h]
0x140150e3e  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x140150e45  xor     r9d, r9d; Context
0x140150e48  mov     r8, rbx; Signature
0x140150e4b  mov     rdx, rdi; Entry
0x140150e4e  call    cs:__imp_RtlInsertEntryHashTable
0x140150e55  nop     dword ptr [rax+rax+00h]
0x140150e5a  lock inc dword ptr [rdi+68h]
0x140150e5e  lock inc dword ptr [rdi+0A4h]
0x140150e65  mov     rcx, cs:WPP_GLOBAL_Control
0x140150e6c  mov     al, [rcx+29h]
0x140150e6f  dec     al
0x140150e71  cmp     al, 2
0x140150e73  ja      short loc_140150E7C
0x140150e75  cmp     [rcx+48h], r12w
0x140150e7a  jz      short loc_140150EA4
0x140150e7c  movzx   eax, byte ptr [rdi+6Ch]
0x140150e80  mov     rcx, [rcx+40h]
0x140150e84  mov     [rsp+78h+var_38], rsi
0x140150e89  mov     [rsp+78h+var_40], eax
0x140150e8d  mov     rax, [rdi+58h]
0x140150e91  mov     [rsp+78h+var_48], rax
0x140150e96  mov     rax, [rdi+60h]
0x140150e9a  mov     [rsp+78h+var_50], rax
0x140150e9f  call    WPP_RECORDER_SF_qqDq
0x140150ea4  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; HashTable
0x140150eab  lea     rdx, [rdi+30h]; Entry
0x140150eaf  xor     r9d, r9d; Context
0x140150eb2  mov     r8, rbp; Signature
0x140150eb5  call    cs:__imp_RtlInsertEntryHashTable
0x140150ebc  nop     dword ptr [rax+rax+00h]
0x140150ec1  lock inc dword ptr [rdi+68h]
0x140150ec5  lock inc dword ptr [rdi+0A8h]
0x140150ecc  mov     r8, [rsp+78h+Signature]; Signature
0x140150ed4  lea     rdx, [rdi+18h]; Entry
0x140150ed8  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x140150edf  xor     r9d, r9d; Context
0x140150ee2  call    cs:__imp_RtlInsertEntryHashTable
0x140150ee9  nop     dword ptr [rax+rax+00h]
0x140150eee  lock inc dword ptr [rdi+68h]
0x140150ef2  lock inc dword ptr [rdi+0ACh]
0x140150ef9  lea     rdx, [rsp+78h+LockState]; LockState
0x140150f01  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x140150f08  call    cs:__imp_NdisReleaseReadWriteLock
0x140150f0f  nop     dword ptr [rax+rax+00h]
0x140150f14  mov     rbx, [rsp+78h+arg_8]
0x140150f1c  add     rsp, 50h
0x140150f20  pop     r14
0x140150f22  pop     r12
0x140150f24  pop     rdi
0x140150f25  pop     rsi
0x140150f26  pop     rbp
0x140150f27  retn
```
