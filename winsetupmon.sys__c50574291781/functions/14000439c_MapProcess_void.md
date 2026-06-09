# MapProcess(void *)

- ea: `0x14000439c`
- end: `0x14000455b`
- name: `?MapProcess@@YAJPEAX@Z`
- size: `447`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001e808`
- `0x14001f4e0`

## callees

- `0x140003944`
- `0x14000439c`
- `0x14000e488`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400044d7`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400044d7`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400043ce`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400043ce`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400043f5`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400043f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004433`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000444d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004510`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000452a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004433`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000444d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004510`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000452a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140004466`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140004466`
- `FLTMGR!FltReleasePushLockEx` at `0x14000453f`
- `FLTMGR!FltReleasePushLockEx` at `0x14000453f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400043b5`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400043b5`

## string_xrefs

- `0x140004409`: `Could not remove existing entry for process %p <==> %wZ`

## pseudocode

```c
__int64 __fastcall MapProcess(void *a1)
{
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v2; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v3; // rbx
  unsigned int v4; // edi
  struct _LIST_ENTRY *Flink; // rcx
  PVOID PoolWithTag; // rax
  unsigned int *v7; // r9
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v8; // rbx
  int ProcessInfo; // eax
  struct _LIST_ENTRY *v10; // rcx
  void *v12; // [rsp+20h] [rbp-48h]

  FltAcquirePushLockExclusiveEx(&qword_140019378, 0);
  v2 = RtlLookupEntryHashTable(HashTable, (ULONG_PTR)a1, 0);
  v3 = v2;
  if ( v2 )
  {
    if ( !RtlRemoveEntryHashTable(HashTable, v2, 0) )
    {
      v4 = -1073741616;
      WriteLogMessage(3, L"Could not remove existing entry for process %p <==> %wZ", a1, v3[1].Linkage.Flink);
      goto LABEL_19;
    }
    Flink = v3[1].Linkage.Flink;
    if ( Flink )
    {
      ExFreePoolWithTag(Flink, 0x6E6D7377u);
      v3[1].Linkage.Flink = 0;
    }
    ExFreePoolWithTag(v3, 0x6E6D7377u);
  }
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, 0x20u, 0x6E6D7377u);
  v8 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_10;
LABEL_13:
    v4 = -1073741670;
    goto LABEL_19;
  }
  if ( !PoolWithTag )
    goto LABEL_13;
  *(_OWORD *)PoolWithTag = 0;
  *((_OWORD *)PoolWithTag + 1) = 0;
LABEL_10:
  ProcessInfo = GetProcessInfo(a1, (struct _UNICODE_STRING **)PoolWithTag + 3, 0, v7, v12);
  v4 = ProcessInfo;
  if ( ProcessInfo >= 0 )
  {
    if ( RtlInsertEntryHashTable(HashTable, v8, (ULONG_PTR)a1, 0) )
      goto LABEL_19;
    v4 = -1073741616;
    WriteLogMessage(3, L"Failed to insert process hash table entry %p <==> %wZ", a1, v8[1].Linkage.Flink);
  }
  else
  {
    WriteLogMessage(3, L"GetProcessInfo failed for process ID %p (0x%08X)", a1, (unsigned int)ProcessInfo);
  }
  v10 = v8[1].Linkage.Flink;
  if ( v10 )
  {
    ExFreePoolWithTag(v10, 0x6E6D7377u);
    v8[1].Linkage.Flink = 0;
  }
  ExFreePoolWithTag(v8, 0x6E6D7377u);
LABEL_19:
  FltReleasePushLockEx(&qword_140019378, 0);
  return v4;
}

```

## disassembly

```asm
0x14000439c  push    rbx
0x14000439e  push    rbp
0x14000439f  push    rsi
0x1400043a0  push    rdi
0x1400043a1  push    r12
0x1400043a3  push    r14
0x1400043a5  sub     rsp, 38h
0x1400043a9  mov     rbp, rcx
0x1400043ac  xor     edx, edx
0x1400043ae  lea     rcx, qword_140019378
0x1400043b5  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400043bc  nop     dword ptr [rax+rax+00h]
0x1400043c1  mov     rcx, cs:HashTable; HashTable
0x1400043c8  xor     r8d, r8d; Context
0x1400043cb  mov     rdx, rbp; Signature
0x1400043ce  call    cs:__imp_RtlLookupEntryHashTable
0x1400043d5  nop     dword ptr [rax+rax+00h]
0x1400043da  mov     rbx, rax
0x1400043dd  mov     r12d, 6E6D7377h
0x1400043e3  test    rax, rax
0x1400043e6  jz      short loc_140004459
0x1400043e8  mov     rcx, cs:HashTable; HashTable
0x1400043ef  xor     r8d, r8d; Context
0x1400043f2  mov     rdx, rax; Entry
0x1400043f5  call    cs:__imp_RtlRemoveEntryHashTable
0x1400043fc  nop     dword ptr [rax+rax+00h]
0x140004401  test    al, al
0x140004403  jnz     short loc_140004427
0x140004405  mov     r9, [rbx+18h]
0x140004409  lea     rdx, aCouldNotRemove_0; "Could not remove existing entry for pro"...
0x140004410  mov     r8, rbp
0x140004413  mov     ecx, 3
0x140004418  mov     edi, 0C00000D0h
0x14000441d  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004422  jmp     loc_140004536
0x140004427  mov     rcx, [rbx+18h]; P
0x14000442b  test    rcx, rcx
0x14000442e  jz      short loc_140004447
0x140004430  mov     edx, r12d; Tag
0x140004433  call    cs:__imp_ExFreePoolWithTag
0x14000443a  nop     dword ptr [rax+rax+00h]
0x14000443f  mov     qword ptr [rbx+18h], 0
0x140004447  mov     edx, r12d; Tag
0x14000444a  mov     rcx, rbx; P
0x14000444d  call    cs:__imp_ExFreePoolWithTag
0x140004454  nop     dword ptr [rax+rax+00h]
0x140004459  mov     r8d, r12d; Tag
0x14000445c  mov     edx, 20h ; ' '; NumberOfBytes
0x140004461  mov     ecx, 401h; PoolType
0x140004466  call    cs:__imp_ExAllocatePoolWithTag
0x14000446d  nop     dword ptr [rax+rax+00h]
0x140004472  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140004479  mov     rbx, rax
0x14000447c  jnz     short loc_1400044BE
0x14000447e  test    rax, rax
0x140004481  jz      short loc_1400044C3
0x140004483  xorps   xmm0, xmm0
0x140004486  movups  xmmword ptr [rax], xmm0
0x140004489  movups  xmmword ptr [rax+10h], xmm0
0x14000448d  xor     r8d, r8d; void **
0x140004490  lea     rdx, [rax+18h]; struct _UNICODE_STRING **
0x140004494  mov     rcx, rbp; void *
0x140004497  mov     rsi, rbx
0x14000449a  call    ?GetProcessInfo@@YAJPEAXPEAPEAU_UNICODE_STRING@@PEAPEAXPEAKPEAE@Z; GetProcessInfo(void *,_UNICODE_STRING * *,void * *,ulong *,uchar *)
0x14000449f  mov     edi, eax
0x1400044a1  mov     r8, rbp; Signature
0x1400044a4  test    eax, eax
0x1400044a6  jns     short loc_1400044CA
0x1400044a8  mov     r9d, eax
0x1400044ab  lea     rdx, aGetprocessinfo; "GetProcessInfo failed for process ID %p"...
0x1400044b2  mov     ecx, 3
0x1400044b7  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400044bc  jmp     short loc_140004504
0x1400044be  test    rbx, rbx
0x1400044c1  jnz     short loc_14000448D
0x1400044c3  mov     edi, 0C000009Ah
0x1400044c8  jmp     short loc_140004536
0x1400044ca  mov     rcx, cs:HashTable; HashTable
0x1400044d1  xor     r9d, r9d; Context
0x1400044d4  mov     rdx, rbx; Entry
0x1400044d7  call    cs:__imp_RtlInsertEntryHashTable
0x1400044de  nop     dword ptr [rax+rax+00h]
0x1400044e3  test    al, al
0x1400044e5  jnz     short loc_140004536
0x1400044e7  mov     r9, [rbx+18h]
0x1400044eb  lea     rdx, aFailedToInsert_0; "Failed to insert process hash table ent"...
0x1400044f2  mov     r8, rbp
0x1400044f5  mov     ecx, 3
0x1400044fa  mov     edi, 0C00000D0h
0x1400044ff  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004504  mov     rcx, [rsi+18h]; P
0x140004508  test    rcx, rcx
0x14000450b  jz      short loc_140004524
0x14000450d  mov     edx, r12d; Tag
0x140004510  call    cs:__imp_ExFreePoolWithTag
0x140004517  nop     dword ptr [rax+rax+00h]
0x14000451c  mov     qword ptr [rsi+18h], 0
0x140004524  mov     edx, r12d; Tag
0x140004527  mov     rcx, rsi; P
0x14000452a  call    cs:__imp_ExFreePoolWithTag
0x140004531  nop     dword ptr [rax+rax+00h]
0x140004536  xor     edx, edx
0x140004538  lea     rcx, qword_140019378
0x14000453f  call    cs:__imp_FltReleasePushLockEx
0x140004546  nop     dword ptr [rax+rax+00h]
0x14000454b  mov     eax, edi
0x14000454d  add     rsp, 38h
0x140004551  pop     r14
0x140004553  pop     r12
0x140004555  pop     rdi
0x140004556  pop     rsi
0x140004557  pop     rbp
0x140004558  pop     rbx
0x140004559  retn
```
