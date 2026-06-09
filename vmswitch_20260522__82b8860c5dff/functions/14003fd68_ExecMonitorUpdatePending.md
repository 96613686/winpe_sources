# ExecMonitorUpdatePending

- ea: `0x14003fd68`
- end: `0x14003ff29`
- name: `ExecMonitorUpdatePending`
- size: `449`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14003e778`
- `0x14003fb98`
- `0x14003fc38`

## callees

- `0x14003a450`
- `0x14003f25c`
- `0x14003fd68`
- `0x14003ff30`
- `0x140046f1c`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14003fe1f`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14003fe1f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003fdf8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003fdf8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fe4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fe97`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fe4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fe97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003fd8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003fd8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe73`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003fd7b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003fd7b`

## pseudocode

```c
void __fastcall ExecMonitorUpdatePending(__int64 a1, char a2)
{
  KIRQL v4; // bp
  int v5; // edx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *PendingEntry; // rbx
  _LIST_ENTRY *v7; // rax
  unsigned __int64 v8; // rax
  __int64 i; // rsi
  __int64 v10; // rcx
  const UNICODE_STRING *v11; // rdx
  char *v12; // rdi
  int v13; // edx

  KeGetCurrentIrql();
  v4 = KeAcquireSpinLockRaiseToDpc(&g_VmsExecMonitorPendingLock);
  PendingEntry = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)ExecMonitorGetPendingEntry(
                                                           *(_QWORD *)(a1 + 72),
                                                           *(unsigned int *)(a1 + 24));
  if ( !PendingEntry )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_id(
      VmsIfrLog,
      v5,
      20,
      25,
      (__int64)WPP_39d9d437f1aa36274999bb0a13ad1489_Traceguids,
      *(_QWORD *)(a1 + 72),
      37);
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v13, 20, 26, (__int64)WPP_39d9d437f1aa36274999bb0a13ad1489_Traceguids, 37);
LABEL_15:
    KeReleaseSpinLock(&g_VmsExecMonitorPendingLock, v4);
    return;
  }
  v7 = *(_LIST_ENTRY **)(a1 + 48);
  if ( v7 )
    PendingEntry[2].Linkage.Flink = v7;
  v8 = *(_QWORD *)(a1 + 40);
  if ( v8 )
  {
    PendingEntry[1].Signature = v8;
    PendingEntry[2].Linkage.Blink = *(_LIST_ENTRY **)(a1 + 56);
  }
  for ( i = 0; i != 3; ++i )
  {
    v10 = 536 * i;
    v11 = (const UNICODE_STRING *)(536 * i + a1 + 88);
    if ( v11->Length )
    {
      *(_DWORD *)((char *)&PendingEntry[3].Linkage.Blink + v10) = *(_DWORD *)(v10 + a1 + 80);
      RtlCopyUnicodeString((PUNICODE_STRING)((char *)&PendingEntry[3].Signature + v10), v11);
    }
  }
  if ( !a2 )
    goto LABEL_15;
  RtlRemoveEntryHashTable(g_VmsExecMonitorPendingTable, PendingEntry, 0);
  if ( *(_DWORD *)(a1 + 24) == 8 )
  {
    v12 = (char *)PendingEntry[1].Linkage.Blink - PendingEntry[1].Signature;
  }
  else if ( *(_BYTE *)(a1 + 64) )
  {
    v12 = (char *)(PendingEntry[1].Signature - (unsigned __int64)PendingEntry[1].Linkage.Blink);
  }
  else
  {
    v12 = 0;
  }
  KeReleaseSpinLock(&g_VmsExecMonitorPendingLock, v4);
  ExecMonitorUpdate(PendingEntry, v12);
  _InterlockedAdd((_DWORD *)&g_VmsExecMonConfig + 1, 0xFFFFF968);
  ExFreePoolWithTag(PendingEntry, 0);
}

```

## disassembly

```asm
0x14003fd68  push    rbx
0x14003fd6a  push    rbp
0x14003fd6b  push    rsi
0x14003fd6c  push    rdi
0x14003fd6d  push    r14
0x14003fd6f  push    r15
0x14003fd71  sub     rsp, 48h
0x14003fd75  mov     r14b, dl
0x14003fd78  mov     rdi, rcx
0x14003fd7b  call    cs:__imp_KeGetCurrentIrql
0x14003fd82  nop     dword ptr [rax+rax+00h]
0x14003fd87  lea     rcx, g_VmsExecMonitorPendingLock; SpinLock
0x14003fd8e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003fd95  nop     dword ptr [rax+rax+00h]
0x14003fd9a  mov     edx, [rdi+18h]
0x14003fd9d  mov     bpl, al
0x14003fda0  mov     rcx, [rdi+48h]
0x14003fda4  call    ExecMonitorGetPendingEntry
0x14003fda9  xor     r15d, r15d
0x14003fdac  mov     rbx, rax
0x14003fdaf  test    rax, rax
0x14003fdb2  jz      loc_14003FECD
0x14003fdb8  mov     rax, [rdi+30h]
0x14003fdbc  test    rax, rax
0x14003fdbf  jz      short loc_14003FDC5
0x14003fdc1  mov     [rbx+30h], rax
0x14003fdc5  mov     rax, [rdi+28h]
0x14003fdc9  test    rax, rax
0x14003fdcc  jnz     loc_14003FEA5
0x14003fdd2  mov     rsi, r15
0x14003fdd5  imul    rcx, rsi, 218h
0x14003fddc  lea     rdx, [rdi+58h]
0x14003fde0  add     rdx, rcx; SourceString
0x14003fde3  cmp     [rdx], r15w
0x14003fde7  jz      short loc_14003FE04
0x14003fde9  mov     eax, [rcx+rdi+50h]
0x14003fded  mov     [rcx+rbx+50h], eax
0x14003fdf1  add     rcx, 58h ; 'X'
0x14003fdf5  add     rcx, rbx; DestinationString
0x14003fdf8  call    cs:__imp_RtlCopyUnicodeString
0x14003fdff  nop     dword ptr [rax+rax+00h]
0x14003fe04  inc     rsi
0x14003fe07  cmp     rsi, 3
0x14003fe0b  jnz     short loc_14003FDD5
0x14003fe0d  test    r14b, r14b
0x14003fe10  jz      short loc_14003FE8D
0x14003fe12  mov     rcx, cs:g_VmsExecMonitorPendingTable; HashTable
0x14003fe19  xor     r8d, r8d; Context
0x14003fe1c  mov     rdx, rbx; Entry
0x14003fe1f  call    cs:__imp_RtlRemoveEntryHashTable
0x14003fe26  nop     dword ptr [rax+rax+00h]
0x14003fe2b  cmp     dword ptr [rdi+18h], 8
0x14003fe2f  jz      loc_14003FEB6
0x14003fe35  cmp     [rdi+40h], r15b
0x14003fe39  jnz     loc_14003FEC0
0x14003fe3f  mov     rdi, r15
0x14003fe42  mov     dl, bpl; NewIrql
0x14003fe45  lea     rcx, g_VmsExecMonitorPendingLock; SpinLock
0x14003fe4c  call    cs:__imp_KeReleaseSpinLock
0x14003fe53  nop     dword ptr [rax+rax+00h]
0x14003fe58  mov     rdx, rdi
0x14003fe5b  mov     rcx, rbx
0x14003fe5e  call    ExecMonitorUpdate
0x14003fe63  lock add dword ptr cs:g_VmsExecMonConfig+4, 0FFFFF968h
0x14003fe6e  xor     edx, edx; Tag
0x14003fe70  mov     rcx, rbx; P
0x14003fe73  call    cs:__imp_ExFreePoolWithTag
0x14003fe7a  nop     dword ptr [rax+rax+00h]
0x14003fe7f  add     rsp, 48h
0x14003fe83  pop     r15
0x14003fe85  pop     r14
0x14003fe87  pop     rdi
0x14003fe88  pop     rsi
0x14003fe89  pop     rbp
0x14003fe8a  pop     rbx
0x14003fe8b  retn
0x14003fe8d  mov     dl, bpl; NewIrql
0x14003fe90  lea     rcx, g_VmsExecMonitorPendingLock; SpinLock
0x14003fe97  call    cs:__imp_KeReleaseSpinLock
0x14003fe9e  nop     dword ptr [rax+rax+00h]
0x14003fea3  jmp     short loc_14003FE7F
0x14003fea5  mov     [rbx+28h], rax
0x14003fea9  mov     rax, [rdi+38h]
0x14003fead  mov     [rbx+38h], rax
0x14003feb1  jmp     loc_14003FDD2
0x14003feb6  mov     rdi, [rbx+20h]
0x14003feba  sub     rdi, [rbx+28h]
0x14003febe  jmp     short loc_14003FE42
0x14003fec0  mov     rdi, [rbx+28h]
0x14003fec4  sub     rdi, [rbx+20h]
0x14003fec8  jmp     loc_14003FE42
0x14003fecd  mov     rax, [rdi+48h]
0x14003fed1  mov     r9d, 19h
0x14003fed7  mov     rcx, cs:VmsIfrLog
0x14003fede  lea     rdi, WPP_39d9d437f1aa36274999bb0a13ad1489_Traceguids
0x14003fee5  mov     esi, 0C0000225h
0x14003feea  mov     dl, 2
0x14003feec  mov     [rsp+78h+var_48], esi
0x14003fef0  lea     ebx, [r9-5]
0x14003fef4  mov     [rsp+78h+var_50], rax
0x14003fef9  mov     r8d, ebx
0x14003fefc  mov     [rsp+78h+var_58], rdi
0x14003ff01  call    WPP_RECORDER_SF_id
0x14003ff06  mov     rcx, cs:VmsIfrLog
0x14003ff0d  lea     r9d, [rbx+6]
0x14003ff11  mov     dword ptr [rsp+78h+var_50], esi
0x14003ff15  mov     r8d, ebx
0x14003ff18  mov     dl, 2
0x14003ff1a  mov     [rsp+78h+var_58], rdi
0x14003ff1f  call    WPP_RECORDER_SF_d
0x14003ff24  jmp     loc_14003FE8D
```
