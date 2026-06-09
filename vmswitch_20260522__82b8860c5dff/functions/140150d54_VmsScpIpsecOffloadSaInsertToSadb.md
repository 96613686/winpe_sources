# VmsScpIpsecOffloadSaInsertToSadb

- ea: `0x140150d54`
- end: `0x140150eb9`
- name: `VmsScpIpsecOffloadSaInsertToSadb`
- size: `357`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14014fac0`

## callees

- `0x140070100`
- `0x140150cc0`
- `0x140150d04`
- `0x140150d54`
- `0x1401518b8`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150dde`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150e45`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150e72`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150dde`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150e45`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140150e72`
- `NDIS!NdisReleaseReadWriteLock` at `0x140150e98`
- `NDIS!NdisReleaseReadWriteLock` at `0x140150e98`
- `NDIS!NdisAcquireReadWriteLock` at `0x140150dc2`
- `NDIS!NdisAcquireReadWriteLock` at `0x140150dc2`

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
0x140150d54  mov     rax, rsp
0x140150d57  mov     [rax+10h], rbx
0x140150d5b  push    rbp
0x140150d5c  push    rsi
0x140150d5d  push    rdi
0x140150d5e  push    r12
0x140150d60  push    r14
0x140150d62  sub     rsp, 50h
0x140150d66  mov     rdi, rcx
0x140150d69  xor     r12d, r12d
0x140150d6c  add     rcx, 60h ; '`'
0x140150d70  mov     [rax+8], r12d
0x140150d74  mov     rsi, rdx
0x140150d77  call    VmsScpIpsecOffloadSaComputeHandlePlusPortSignature
0x140150d7c  mov     edx, [rdi+0A0h]
0x140150d82  lea     rcx, [rdi+8Ch]
0x140150d89  mov     rbx, rax
0x140150d8c  call    VmsScpIpsecOffloadSaComputeIpSpiSignature
0x140150d91  lea     r8, [rsp+78h+Signature]
0x140150d99  mov     [rsp+78h+Signature], r12
0x140150da1  lea     edx, [r12+8]
0x140150da6  mov     rcx, rsi
0x140150da9  mov     rbp, rax
0x140150dac  call    VmsScpIpsecGenericUpdateHash
0x140150db1  mov     dl, 1; fWrite
0x140150db3  lea     r8, [rsp+78h+LockState]; LockState
0x140150dbb  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x140150dc2  call    cs:__imp_NdisAcquireReadWriteLock
0x140150dc9  nop     dword ptr [rax+rax+00h]
0x140150dce  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x140150dd5  xor     r9d, r9d; Context
0x140150dd8  mov     r8, rbx; Signature
0x140150ddb  mov     rdx, rdi; Entry
0x140150dde  call    cs:__imp_RtlInsertEntryHashTable
0x140150de5  nop     dword ptr [rax+rax+00h]
0x140150dea  lock inc dword ptr [rdi+68h]
0x140150dee  lock inc dword ptr [rdi+0A4h]
0x140150df5  mov     rcx, cs:WPP_GLOBAL_Control
0x140150dfc  mov     al, [rcx+29h]
0x140150dff  dec     al
0x140150e01  cmp     al, 2
0x140150e03  ja      short loc_140150E0C
0x140150e05  cmp     [rcx+48h], r12w
0x140150e0a  jz      short loc_140150E34
0x140150e0c  movzx   eax, byte ptr [rdi+6Ch]
0x140150e10  mov     rcx, [rcx+40h]
0x140150e14  mov     [rsp+78h+var_38], rsi
0x140150e19  mov     [rsp+78h+var_40], eax
0x140150e1d  mov     rax, [rdi+58h]
0x140150e21  mov     [rsp+78h+var_48], rax
0x140150e26  mov     rax, [rdi+60h]
0x140150e2a  mov     [rsp+78h+var_50], rax
0x140150e2f  call    WPP_RECORDER_SF_qqDq
0x140150e34  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; HashTable
0x140150e3b  lea     rdx, [rdi+30h]; Entry
0x140150e3f  xor     r9d, r9d; Context
0x140150e42  mov     r8, rbp; Signature
0x140150e45  call    cs:__imp_RtlInsertEntryHashTable
0x140150e4c  nop     dword ptr [rax+rax+00h]
0x140150e51  lock inc dword ptr [rdi+68h]
0x140150e55  lock inc dword ptr [rdi+0A8h]
0x140150e5c  mov     r8, [rsp+78h+Signature]; Signature
0x140150e64  lea     rdx, [rdi+18h]; Entry
0x140150e68  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x140150e6f  xor     r9d, r9d; Context
0x140150e72  call    cs:__imp_RtlInsertEntryHashTable
0x140150e79  nop     dword ptr [rax+rax+00h]
0x140150e7e  lock inc dword ptr [rdi+68h]
0x140150e82  lock inc dword ptr [rdi+0ACh]
0x140150e89  lea     rdx, [rsp+78h+LockState]; LockState
0x140150e91  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x140150e98  call    cs:__imp_NdisReleaseReadWriteLock
0x140150e9f  nop     dword ptr [rax+rax+00h]
0x140150ea4  mov     rbx, [rsp+78h+arg_8]
0x140150eac  add     rsp, 50h
0x140150eb0  pop     r14
0x140150eb2  pop     r12
0x140150eb4  pop     rdi
0x140150eb5  pop     rsi
0x140150eb6  pop     rbp
0x140150eb7  retn
```
