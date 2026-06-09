# UnmapProcess(void *)

- ea: `0x140004564`
- end: `0x140004668`
- name: `?UnmapProcess@@YAJPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(ULONG_PTR Signature)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001f4e0`

## callees

- `0x140003944`
- `0x140004564`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x140004596`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140004596`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400045ba`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400045ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000461b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004634`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000461b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004634`
- `FLTMGR!FltReleasePushLockEx` at `0x1400045f5`
- `FLTMGR!FltReleasePushLockEx` at `0x14000464e`
- `FLTMGR!FltReleasePushLockEx` at `0x1400045f5`
- `FLTMGR!FltReleasePushLockEx` at `0x14000464e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000457d`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000457d`

## string_xrefs

- `0x1400045ce`: `Could not remove entry for process %p <==> %wZ`

## pseudocode

```c
__int64 __fastcall UnmapProcess(ULONG_PTR Signature)
{
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v2; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v3; // rax
  char v4; // bp
  unsigned int v5; // esi
  struct _LIST_ENTRY *Flink; // rcx

  v2 = 0;
  FltAcquirePushLockExclusiveEx(&qword_140019378, 0);
  v3 = RtlLookupEntryHashTable(HashTable, Signature, 0);
  if ( !v3 || (v2 = v3, RtlRemoveEntryHashTable(HashTable, v3, 0)) )
  {
    FltReleasePushLockEx(&qword_140019378, 0);
    v5 = 0;
    if ( !v2 )
      return v5;
    v4 = 0;
  }
  else
  {
    v4 = 1;
    v5 = -1073741616;
    WriteLogMessage(3, L"Could not remove entry for process %p <==> %wZ", Signature, v2[1].Linkage.Flink);
  }
  Flink = v2[1].Linkage.Flink;
  if ( Flink )
  {
    ExFreePoolWithTag(Flink, 0x6E6D7377u);
    v2[1].Linkage.Flink = 0;
  }
  ExFreePoolWithTag(v2, 0x6E6D7377u);
  if ( v4 )
    FltReleasePushLockEx(&qword_140019378, 0);
  return v5;
}

```

## disassembly

```asm
0x140004564  push    rbx
0x140004566  push    rbp
0x140004567  push    rsi
0x140004568  push    rdi
0x140004569  push    r14
0x14000456b  sub     rsp, 20h
0x14000456f  mov     r14, rcx
0x140004572  xor     edx, edx
0x140004574  lea     rcx, qword_140019378
0x14000457b  xor     ebx, ebx
0x14000457d  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140004584  nop     dword ptr [rax+rax+00h]
0x140004589  mov     rcx, cs:HashTable; HashTable
0x140004590  xor     r8d, r8d; Context
0x140004593  mov     rdx, r14; Signature
0x140004596  call    cs:__imp_RtlLookupEntryHashTable
0x14000459d  nop     dword ptr [rax+rax+00h]
0x1400045a2  mov     rdi, rax
0x1400045a5  test    rax, rax
0x1400045a8  jz      short loc_1400045EC
0x1400045aa  mov     rcx, cs:HashTable; HashTable
0x1400045b1  xor     r8d, r8d; Context
0x1400045b4  mov     rdx, rax; Entry
0x1400045b7  mov     rbx, rax
0x1400045ba  call    cs:__imp_RtlRemoveEntryHashTable
0x1400045c1  nop     dword ptr [rax+rax+00h]
0x1400045c6  test    al, al
0x1400045c8  jnz     short loc_1400045EC
0x1400045ca  mov     r9, [rbx+18h]
0x1400045ce  lea     rdx, aCouldNotRemove_1; "Could not remove entry for process %p <"...
0x1400045d5  mov     r8, r14
0x1400045d8  mov     ecx, 3
0x1400045dd  mov     bpl, 1
0x1400045e0  mov     esi, 0C00000D0h
0x1400045e5  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400045ea  jmp     short loc_14000460B
0x1400045ec  xor     edx, edx
0x1400045ee  lea     rcx, qword_140019378
0x1400045f5  call    cs:__imp_FltReleasePushLockEx
0x1400045fc  nop     dword ptr [rax+rax+00h]
0x140004601  xor     esi, esi
0x140004603  test    rbx, rbx
0x140004606  jz      short loc_14000465A
0x140004608  xor     bpl, bpl
0x14000460b  mov     rcx, [rbx+18h]; P
0x14000460f  mov     edi, 6E6D7377h
0x140004614  test    rcx, rcx
0x140004617  jz      short loc_14000462F
0x140004619  mov     edx, edi; Tag
0x14000461b  call    cs:__imp_ExFreePoolWithTag
0x140004622  nop     dword ptr [rax+rax+00h]
0x140004627  mov     qword ptr [rbx+18h], 0
0x14000462f  mov     edx, edi; Tag
0x140004631  mov     rcx, rbx; P
0x140004634  call    cs:__imp_ExFreePoolWithTag
0x14000463b  nop     dword ptr [rax+rax+00h]
0x140004640  test    bpl, bpl
0x140004643  jz      short loc_14000465A
0x140004645  xor     edx, edx
0x140004647  lea     rcx, qword_140019378
0x14000464e  call    cs:__imp_FltReleasePushLockEx
0x140004655  nop     dword ptr [rax+rax+00h]
0x14000465a  mov     eax, esi
0x14000465c  add     rsp, 20h
0x140004660  pop     r14
0x140004662  pop     rdi
0x140004663  pop     rsi
0x140004664  pop     rbp
0x140004665  pop     rbx
0x140004666  retn
```
