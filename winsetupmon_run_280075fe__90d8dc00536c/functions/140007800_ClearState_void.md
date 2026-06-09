# ClearState(void)

- ea: `0x140007800`
- end: `0x140007a4f`
- name: `?ClearState@@YAXXZ`
- size: `591`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001ffd0`
- `0x140022078`

## callees

- `0x140003780`
- `0x140003944`
- `0x1400056bc`
- `0x140006a18`
- `0x140006b70`
- `0x140007800`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x140007833`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400078ac`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140007833`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400078ac`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14000784c`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14000784c`
- `ntoskrnl!RtlDeleteHashTable` at `0x140007997`
- `ntoskrnl!RtlDeleteHashTable` at `0x140007997`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140007984`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140007984`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400078fe`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400078fe`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000795e`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000795e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400078d1`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400078d1`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000781b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000781b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007863`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007882`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000789b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000792c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007944`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400079f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007863`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007882`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000789b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000792c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007944`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400079f5`
- `FLTMGR!FltDeletePushLock` at `0x1400079bf`
- `FLTMGR!FltDeletePushLock` at `0x140007a2d`
- `FLTMGR!FltDeletePushLock` at `0x1400079bf`
- `FLTMGR!FltDeletePushLock` at `0x140007a2d`
- `FLTMGR!FltReleasePushLockEx` at `0x1400079ac`
- `FLTMGR!FltReleasePushLockEx` at `0x140007a1e`
- `FLTMGR!FltReleasePushLockEx` at `0x1400079ac`
- `FLTMGR!FltReleasePushLockEx` at `0x140007a1e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400078e6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400079d7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400078e6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400079d7`

## string_xrefs

- `0x140007911`: `Could not remove entry for process %wZ`

## pseudocode

```c
void ClearState(void)
{
  struct _UNICODE_PREFIX_TABLE_ENTRY *i; // rax
  struct _RTL_SPLAY_LINKS *Parent; // rcx
  struct _UNICODE_PREFIX_TABLE_ENTRY *NextPrefixTree; // rcx
  struct _UNICODE_PREFIX_TABLE_ENTRY *v3; // rbx
  PVOID *p_Flink; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v5; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v6; // rdi
  struct _KMUTANT *v7; // rbx
  struct _LIST_ENTRY *Flink; // rcx

  UninitializePrivacyFilter();
  ExAcquireFastMutex(&stru_140019468);
  for ( i = RtlNextUnicodePrefix(&PrefixTable, 1u); ; i = RtlNextUnicodePrefix(&PrefixTable, 0) )
  {
    v3 = i;
    if ( !i )
      break;
    RtlRemoveUnicodePrefix(&PrefixTable, i);
    Parent = v3[1].Links.Parent;
    if ( Parent )
    {
      ExFreePoolWithTag(Parent, 0x6E6D7377u);
      v3[1].Links.Parent = 0;
    }
    NextPrefixTree = v3[1].NextPrefixTree;
    if ( NextPrefixTree )
    {
      ExFreePoolWithTag(NextPrefixTree, 0x6E6D7377u);
      v3[1].NextPrefixTree = 0;
    }
    ExFreePoolWithTag(v3, 0x6E6D7377u);
  }
  ReleaseTrackedVolumesList();
  ReleaseTrackedPathsTable();
  ExReleaseFastMutex(&stru_140019468);
  FltAcquirePushLockExclusiveEx(&qword_140019378, 0);
  while ( 1 )
  {
    v5 = RtlEnumerateEntryHashTable(HashTable, &Enumerator);
    v6 = v5;
    if ( !v5 )
      break;
    p_Flink = (PVOID *)&v5[1].Linkage.Flink;
    if ( !RtlRemoveEntryHashTable(HashTable, v5, 0) )
      WriteLogMessage(3, L"Could not remove entry for process %wZ", *p_Flink);
    if ( *p_Flink )
    {
      ExFreePoolWithTag(*p_Flink, 0x6E6D7377u);
      *p_Flink = 0;
    }
    ExFreePoolWithTag(v6, 0x6E6D7377u);
  }
  RtlEndEnumerationHashTable(HashTable, &Enumerator);
  RtlDeleteHashTable(HashTable);
  FltReleasePushLockEx(&qword_140019378, 0);
  FltDeletePushLock(&qword_140019378);
  FltAcquirePushLockExclusiveEx(&qword_140019650, 0);
  v7 = (struct _KMUTANT *)qword_140019658;
  do
  {
    Flink = v7->Header.WaitListHead.Flink;
    if ( Flink )
    {
      ExFreePoolWithTag(Flink, 0x6E6D7377u);
      v7->Header.WaitListHead.Flink = 0;
    }
    v7 = (struct _KMUTANT *)((char *)v7 + 16);
  }
  while ( v7 != &stru_1400197F8 );
  FltReleasePushLockEx(&qword_140019650, 0);
  FltDeletePushLock(&qword_140019650);
  UninitializeLogger();
}

```

## disassembly

```asm
0x140007800  mov     [rsp+arg_0], rbx
0x140007805  mov     [rsp+arg_8], rbp
0x14000780a  push    rdi
0x14000780b  sub     rsp, 20h
0x14000780f  call    ?UninitializePrivacyFilter@@YAXXZ; UninitializePrivacyFilter(void)
0x140007814  lea     rcx, stru_140019468; FastMutex
0x14000781b  call    cs:__imp_ExAcquireFastMutex
0x140007822  nop     dword ptr [rax+rax+00h]
0x140007827  lea     rdi, PrefixTable
0x14000782e  mov     dl, 1; Restart
0x140007830  mov     rcx, rdi; PrefixTable
0x140007833  call    cs:__imp_RtlNextUnicodePrefix
0x14000783a  nop     dword ptr [rax+rax+00h]
0x14000783f  mov     ebp, 6E6D7377h
0x140007844  jmp     short loc_1400078B8
0x140007846  mov     rdx, rbx; PrefixTableEntry
0x140007849  mov     rcx, rdi; PrefixTable
0x14000784c  call    cs:__imp_RtlRemoveUnicodePrefix
0x140007853  nop     dword ptr [rax+rax+00h]
0x140007858  mov     rcx, [rbx+50h]; P
0x14000785c  test    rcx, rcx
0x14000785f  jz      short loc_140007877
0x140007861  mov     edx, ebp; Tag
0x140007863  call    cs:__imp_ExFreePoolWithTag
0x14000786a  nop     dword ptr [rax+rax+00h]
0x14000786f  mov     qword ptr [rbx+50h], 0
0x140007877  mov     rcx, [rbx+40h]; P
0x14000787b  test    rcx, rcx
0x14000787e  jz      short loc_140007896
0x140007880  mov     edx, ebp; Tag
0x140007882  call    cs:__imp_ExFreePoolWithTag
0x140007889  nop     dword ptr [rax+rax+00h]
0x14000788e  mov     qword ptr [rbx+40h], 0
0x140007896  mov     edx, ebp; Tag
0x140007898  mov     rcx, rbx; P
0x14000789b  call    cs:__imp_ExFreePoolWithTag
0x1400078a2  nop     dword ptr [rax+rax+00h]
0x1400078a7  xor     edx, edx; Restart
0x1400078a9  mov     rcx, rdi; PrefixTable
0x1400078ac  call    cs:__imp_RtlNextUnicodePrefix
0x1400078b3  nop     dword ptr [rax+rax+00h]
0x1400078b8  mov     rbx, rax
0x1400078bb  test    rax, rax
0x1400078be  jnz     short loc_140007846
0x1400078c0  call    ReleaseTrackedVolumesList
0x1400078c5  call    ReleaseTrackedPathsTable
0x1400078ca  lea     rcx, stru_140019468; FastMutex
0x1400078d1  call    cs:__imp_ExReleaseFastMutex
0x1400078d8  nop     dword ptr [rax+rax+00h]
0x1400078dd  xor     edx, edx
0x1400078df  lea     rcx, qword_140019378
0x1400078e6  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400078ed  nop     dword ptr [rax+rax+00h]
0x1400078f2  jmp     short loc_140007950
0x1400078f4  xor     r8d, r8d; Context
0x1400078f7  lea     rbx, [rdi+18h]
0x1400078fb  mov     rdx, rdi; Entry
0x1400078fe  call    cs:__imp_RtlRemoveEntryHashTable
0x140007905  nop     dword ptr [rax+rax+00h]
0x14000790a  test    al, al
0x14000790c  jnz     short loc_140007922
0x14000790e  mov     r8, [rbx]
0x140007911  lea     rdx, aCouldNotRemove; "Could not remove entry for process %wZ"
0x140007918  mov     ecx, 3
0x14000791d  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140007922  mov     rcx, [rbx]; P
0x140007925  test    rcx, rcx
0x140007928  jz      short loc_14000793F
0x14000792a  mov     edx, ebp; Tag
0x14000792c  call    cs:__imp_ExFreePoolWithTag
0x140007933  nop     dword ptr [rax+rax+00h]
0x140007938  mov     qword ptr [rbx], 0
0x14000793f  mov     edx, ebp; Tag
0x140007941  mov     rcx, rdi; P
0x140007944  call    cs:__imp_ExFreePoolWithTag
0x14000794b  nop     dword ptr [rax+rax+00h]
0x140007950  mov     rcx, cs:HashTable; HashTable
0x140007957  lea     rdx, Enumerator; Enumerator
0x14000795e  call    cs:__imp_RtlEnumerateEntryHashTable
0x140007965  nop     dword ptr [rax+rax+00h]
0x14000796a  mov     rcx, cs:HashTable; HashTable
0x140007971  mov     rdi, rax
0x140007974  test    rax, rax
0x140007977  jnz     loc_1400078F4
0x14000797d  lea     rdx, Enumerator; Enumerator
0x140007984  call    cs:__imp_RtlEndEnumerationHashTable
0x14000798b  nop     dword ptr [rax+rax+00h]
0x140007990  mov     rcx, cs:HashTable; HashTable
0x140007997  call    cs:__imp_RtlDeleteHashTable
0x14000799e  nop     dword ptr [rax+rax+00h]
0x1400079a3  xor     edx, edx
0x1400079a5  lea     rcx, qword_140019378
0x1400079ac  call    cs:__imp_FltReleasePushLockEx
0x1400079b3  nop     dword ptr [rax+rax+00h]
0x1400079b8  lea     rcx, qword_140019378; PushLock
0x1400079bf  call    cs:__imp_FltDeletePushLock
0x1400079c6  nop     dword ptr [rax+rax+00h]
0x1400079cb  lea     rdi, qword_140019650
0x1400079d2  xor     edx, edx
0x1400079d4  mov     rcx, rdi
0x1400079d7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400079de  nop     dword ptr [rax+rax+00h]
0x1400079e3  lea     rbx, qword_140019658
0x1400079ea  mov     rcx, [rbx+8]; P
0x1400079ee  test    rcx, rcx
0x1400079f1  jz      short loc_140007A09
0x1400079f3  mov     edx, ebp; Tag
0x1400079f5  call    cs:__imp_ExFreePoolWithTag
0x1400079fc  nop     dword ptr [rax+rax+00h]
0x140007a01  mov     qword ptr [rbx+8], 0
0x140007a09  add     rbx, 10h
0x140007a0d  lea     rax, stru_1400197F8
0x140007a14  cmp     rbx, rax
0x140007a17  jnz     short loc_1400079EA
0x140007a19  xor     edx, edx
0x140007a1b  mov     rcx, rdi
0x140007a1e  call    cs:__imp_FltReleasePushLockEx
0x140007a25  nop     dword ptr [rax+rax+00h]
0x140007a2a  mov     rcx, rdi; PushLock
0x140007a2d  call    cs:__imp_FltDeletePushLock
0x140007a34  nop     dword ptr [rax+rax+00h]
0x140007a39  call    ?UninitializeLogger@@YAXXZ; UninitializeLogger(void)
0x140007a3e  mov     rbx, [rsp+28h+arg_0]
0x140007a43  mov     rbp, [rsp+28h+arg_8]
0x140007a48  add     rsp, 20h
0x140007a4c  pop     rdi
0x140007a4d  retn
```
