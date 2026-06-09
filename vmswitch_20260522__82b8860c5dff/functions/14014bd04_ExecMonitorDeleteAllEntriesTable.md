# ExecMonitorDeleteAllEntriesTable

- ea: `0x14014bd04`
- end: `0x14014be46`
- name: `ExecMonitorDeleteAllEntriesTable`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008e6d4`
- `0x14014c9d0`

## callees

- `0x14003a450`
- `0x14003f194`
- `0x140046f1c`
- `0x14014bd04`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014bdd3`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014bdd3`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14014be10`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14014be10`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14014bdf7`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14014bdf7`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14014bd59`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14014bd59`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014be22`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014be22`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bd42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bd42`
- `ntoskrnl!KeGetCurrentIrql` at `0x14014bd33`
- `ntoskrnl!KeGetCurrentIrql` at `0x14014bd33`

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
0x14014bd04  mov     [rsp+arg_0], rbx
0x14014bd09  mov     [rsp+arg_8], rbp
0x14014bd0e  push    rsi
0x14014bd0f  push    rdi
0x14014bd10  push    r14
0x14014bd12  sub     rsp, 70h
0x14014bd16  xorps   xmm0, xmm0
0x14014bd19  xor     eax, eax
0x14014bd1b  movups  xmmword ptr [rsp+88h+Enumerator.___u0], xmm0
0x14014bd20  mov     qword ptr [rsp+88h+Enumerator.BucketIndex], rax
0x14014bd25  mov     r14, r8
0x14014bd28  movups  xmmword ptr [rsp+88h+Enumerator.___u0+10h], xmm0
0x14014bd2d  mov     rsi, rdx
0x14014bd30  mov     rbx, rcx
0x14014bd33  call    cs:__imp_KeGetCurrentIrql
0x14014bd3a  nop     dword ptr [rax+rax+00h]
0x14014bd3f  mov     rcx, rsi; SpinLock
0x14014bd42  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14014bd49  nop     dword ptr [rax+rax+00h]
0x14014bd4e  mov     rcx, [rbx]; HashTable
0x14014bd51  lea     rdx, [rsp+88h+Enumerator]; Enumerator
0x14014bd56  mov     bpl, al
0x14014bd59  call    cs:__imp_RtlInitEnumerationHashTable
0x14014bd60  nop     dword ptr [rax+rax+00h]
0x14014bd65  mov     rcx, [rbx]
0x14014bd68  test    al, al
0x14014bd6a  jnz     short loc_14014BDC1
0x14014bd6c  mov     edi, 0C0000001h
0x14014bd71  mov     r9d, 0Ah
0x14014bd77  mov     [rsp+88h+var_58], edi
0x14014bd7b  mov     [rsp+88h+var_60], rcx
0x14014bd80  lea     r14, WPP_39d9d437f1aa36274999bb0a13ad1489_Traceguids
0x14014bd87  mov     rcx, cs:VmsIfrLog
0x14014bd8e  mov     dl, 2
0x14014bd90  mov     [rsp+88h+var_68], r14
0x14014bd95  lea     ebx, [r9+0Ah]
0x14014bd99  mov     r8d, ebx
0x14014bd9c  call    WPP_RECORDER_SF_id
0x14014bda1  mov     rcx, cs:VmsIfrLog
0x14014bda8  lea     r9d, [rbx-9]
0x14014bdac  mov     dword ptr [rsp+88h+var_60], edi
0x14014bdb0  mov     r8d, ebx
0x14014bdb3  mov     dl, 2
0x14014bdb5  mov     [rsp+88h+var_68], r14
0x14014bdba  call    WPP_RECORDER_SF_d
0x14014bdbf  jmp     short loc_14014BE1C
0x14014bdc1  xor     edi, edi
0x14014bdc3  jmp     short loc_14014BDF2
0x14014bdc5  xor     r8d, r8d; Context
0x14014bdc8  mov     [rsp+88h+arg_18], rax
0x14014bdd0  mov     rdx, rax; Entry
0x14014bdd3  call    cs:__imp_RtlRemoveEntryHashTable
0x14014bdda  nop     dword ptr [rax+rax+00h]
0x14014bddf  mov     rdx, r14
0x14014bde2  lea     rcx, [rsp+88h+arg_18]
0x14014bdea  call    ExecMonitorFree
0x14014bdef  mov     rcx, [rbx]; HashTable
0x14014bdf2  lea     rdx, [rsp+88h+Enumerator]; Enumerator
0x14014bdf7  call    cs:__imp_RtlEnumerateEntryHashTable
0x14014bdfe  nop     dword ptr [rax+rax+00h]
0x14014be03  mov     rcx, [rbx]; HashTable
0x14014be06  test    rax, rax
0x14014be09  jnz     short loc_14014BDC5
0x14014be0b  lea     rdx, [rsp+88h+Enumerator]; Enumerator
0x14014be10  call    cs:__imp_RtlEndEnumerationHashTable
0x14014be17  nop     dword ptr [rax+rax+00h]
0x14014be1c  mov     dl, bpl; NewIrql
0x14014be1f  mov     rcx, rsi; SpinLock
0x14014be22  call    cs:__imp_KeReleaseSpinLock
0x14014be29  nop     dword ptr [rax+rax+00h]
0x14014be2e  lea     r11, [rsp+88h+var_18]
0x14014be33  mov     eax, edi
0x14014be35  mov     rbx, [r11+20h]
0x14014be39  mov     rbp, [r11+28h]
0x14014be3d  mov     rsp, r11
0x14014be40  pop     r14
0x14014be42  pop     rdi
0x14014be43  pop     rsi
0x14014be44  retn
```
