# ExecMonitorDeleteAllEntriesTable

- ea: `0x14014bd74`
- end: `0x14014beb6`
- name: `ExecMonitorDeleteAllEntriesTable`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008e6d4`
- `0x14014ca40`

## callees

- `0x14003a450`
- `0x14003f194`
- `0x140046f1c`
- `0x14014bd74`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014be43`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014be43`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14014be80`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14014be80`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14014be67`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14014be67`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14014bdc9`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14014bdc9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014be92`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014be92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bdb2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bdb2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14014bda3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14014bda3`

## pseudocode

```c
__int64 __fastcall ExecMonitorDeleteAllEntriesTable(PRTL_DYNAMIC_HASH_TABLE *a1, KSPIN_LOCK *a2, __int64 a3)
{
  KIRQL v6; // bp
  BOOLEAN inited; // al
  int v8; // edx
  struct _RTL_DYNAMIC_HASH_TABLE *v9; // rcx
  unsigned int v10; // edi
  int v11; // edx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v12; // rax
  struct _RTL_DYNAMIC_HASH_TABLE *v13; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+40h] [rbp-48h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v16; // [rsp+A8h] [rbp+20h] BYREF

  memset(&Enumerator, 0, sizeof(Enumerator));
  KeGetCurrentIrql();
  v6 = KeAcquireSpinLockRaiseToDpc(a2);
  inited = RtlInitEnumerationHashTable(*a1, &Enumerator);
  v9 = *a1;
  if ( inited )
  {
    v10 = 0;
    while ( 1 )
    {
      v12 = RtlEnumerateEntryHashTable(v9, &Enumerator);
      v13 = *a1;
      if ( !v12 )
        break;
      v16 = v12;
      RtlRemoveEntryHashTable(v13, v12, 0);
      ExecMonitorFree(&v16, a3);
      v9 = *a1;
    }
    RtlEndEnumerationHashTable(v13, &Enumerator);
  }
  else
  {
    v10 = -1073741823;
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_id(VmsIfrLog, v8, 20, 10, (__int64)WPP_39d9d437f1aa36274999bb0a13ad1489_Traceguids, (char)v9, 1);
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v11, 20, 11, (__int64)WPP_39d9d437f1aa36274999bb0a13ad1489_Traceguids, 1);
  }
  KeReleaseSpinLock(a2, v6);
  return v10;
}

```

## disassembly

```asm
0x14014bd74  mov     [rsp+arg_0], rbx
0x14014bd79  mov     [rsp+arg_8], rbp
0x14014bd7e  push    rsi
0x14014bd7f  push    rdi
0x14014bd80  push    r14
0x14014bd82  sub     rsp, 70h
0x14014bd86  xorps   xmm0, xmm0
0x14014bd89  xor     eax, eax
0x14014bd8b  movups  xmmword ptr [rsp+88h+Enumerator.___u0], xmm0
0x14014bd90  mov     qword ptr [rsp+88h+Enumerator.BucketIndex], rax
0x14014bd95  mov     r14, r8
0x14014bd98  movups  xmmword ptr [rsp+88h+Enumerator.___u0+10h], xmm0
0x14014bd9d  mov     rsi, rdx
0x14014bda0  mov     rbx, rcx
0x14014bda3  call    cs:__imp_KeGetCurrentIrql
0x14014bdaa  nop     dword ptr [rax+rax+00h]
0x14014bdaf  mov     rcx, rsi; SpinLock
0x14014bdb2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14014bdb9  nop     dword ptr [rax+rax+00h]
0x14014bdbe  mov     rcx, [rbx]; HashTable
0x14014bdc1  lea     rdx, [rsp+88h+Enumerator]; Enumerator
0x14014bdc6  mov     bpl, al
0x14014bdc9  call    cs:__imp_RtlInitEnumerationHashTable
0x14014bdd0  nop     dword ptr [rax+rax+00h]
0x14014bdd5  mov     rcx, [rbx]
0x14014bdd8  test    al, al
0x14014bdda  jnz     short loc_14014BE31
0x14014bddc  mov     edi, 0C0000001h
0x14014bde1  mov     r9d, 0Ah
0x14014bde7  mov     [rsp+88h+var_58], edi
0x14014bdeb  mov     [rsp+88h+var_60], rcx
0x14014bdf0  lea     r14, WPP_39d9d437f1aa36274999bb0a13ad1489_Traceguids
0x14014bdf7  mov     rcx, cs:VmsIfrLog
0x14014bdfe  mov     dl, 2
0x14014be00  mov     [rsp+88h+var_68], r14
0x14014be05  lea     ebx, [r9+0Ah]
0x14014be09  mov     r8d, ebx
0x14014be0c  call    WPP_RECORDER_SF_id
0x14014be11  mov     rcx, cs:VmsIfrLog
0x14014be18  lea     r9d, [rbx-9]
0x14014be1c  mov     dword ptr [rsp+88h+var_60], edi
0x14014be20  mov     r8d, ebx
0x14014be23  mov     dl, 2
0x14014be25  mov     [rsp+88h+var_68], r14
0x14014be2a  call    WPP_RECORDER_SF_d
0x14014be2f  jmp     short loc_14014BE8C
0x14014be31  xor     edi, edi
0x14014be33  jmp     short loc_14014BE62
0x14014be35  xor     r8d, r8d; Context
0x14014be38  mov     [rsp+88h+arg_18], rax
0x14014be40  mov     rdx, rax; Entry
0x14014be43  call    cs:__imp_RtlRemoveEntryHashTable
0x14014be4a  nop     dword ptr [rax+rax+00h]
0x14014be4f  mov     rdx, r14
0x14014be52  lea     rcx, [rsp+88h+arg_18]
0x14014be5a  call    ExecMonitorFree
0x14014be5f  mov     rcx, [rbx]; HashTable
0x14014be62  lea     rdx, [rsp+88h+Enumerator]; Enumerator
0x14014be67  call    cs:__imp_RtlEnumerateEntryHashTable
0x14014be6e  nop     dword ptr [rax+rax+00h]
0x14014be73  mov     rcx, [rbx]; HashTable
0x14014be76  test    rax, rax
0x14014be79  jnz     short loc_14014BE35
0x14014be7b  lea     rdx, [rsp+88h+Enumerator]; Enumerator
0x14014be80  call    cs:__imp_RtlEndEnumerationHashTable
0x14014be87  nop     dword ptr [rax+rax+00h]
0x14014be8c  mov     dl, bpl; NewIrql
0x14014be8f  mov     rcx, rsi; SpinLock
0x14014be92  call    cs:__imp_KeReleaseSpinLock
0x14014be99  nop     dword ptr [rax+rax+00h]
0x14014be9e  lea     r11, [rsp+88h+var_18]
0x14014bea3  mov     eax, edi
0x14014bea5  mov     rbx, [r11+20h]
0x14014bea9  mov     rbp, [r11+28h]
0x14014bead  mov     rsp, r11
0x14014beb0  pop     r14
0x14014beb2  pop     rdi
0x14014beb3  pop     rsi
0x14014beb4  retn
```
