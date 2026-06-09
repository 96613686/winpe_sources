# UpdateCallHubHashing

- ea: `0x18001ea6c`
- end: `0x18001eaf6`
- name: `UpdateCallHubHashing`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000fe60`

## callees

- `0x1800011a0`
- `0x1800063b0`
- `0x18001b04c`
- `0x18001bf78`
- `0x18001ea6c`
- `0x18001f620`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001eae3`
- `KERNEL32!LeaveCriticalSection` at `0x18001eae3`

## pseudocode

```c
__int64 __fastcall UpdateCallHubHashing(unsigned __int64 a1)
{
  _DWORD *DynamicHashTableEntry; // rax
  _DWORD *v3; // rdi

  if ( (unsigned int)WaitForExclusivetCallAccess(a1, 1280065859) )
  {
    DynamicHashTableEntry = (_DWORD *)AcquireHashTableEntryLock(*(_QWORD *)(a1 + 24), *(unsigned int *)(a1 + 160));
    v3 = DynamicHashTableEntry;
    if ( *DynamicHashTableEntry != *(_DWORD *)(a1 + 160) )
      DynamicHashTableEntry = (_DWORD *)FindDynamicHashTableEntry(DynamicHashTableEntry);
    if ( DynamicHashTableEntry )
      SendNewCallHubEvent(a1, DynamicHashTableEntry);
    ReleaseHashTableEntryLock(*(_QWORD *)(a1 + 24), v3);
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
  }
  return 0;
}

```

## disassembly

```asm
0x18001ea6c  mov     [rsp+arg_0], rbx
0x18001ea71  push    rdi
0x18001ea72  sub     rsp, 20h
0x18001ea76  mov     edx, 4C4C4143h
0x18001ea7b  mov     rbx, rcx
0x18001ea7e  call    WaitForExclusivetCallAccess
0x18001ea83  test    eax, eax
0x18001ea85  jz      short loc_18001EAE9
0x18001ea87  mov     edx, [rbx+0A0h]
0x18001ea8d  mov     rcx, [rbx+18h]
0x18001ea91  call    AcquireHashTableEntryLock
0x18001ea96  mov     edx, [rbx+0A0h]
0x18001ea9c  mov     rdi, rax
0x18001ea9f  cmp     [rax], edx
0x18001eaa1  jz      short loc_18001EAAB
0x18001eaa3  mov     rcx, rax
0x18001eaa6  call    FindDynamicHashTableEntry
0x18001eaab  test    rax, rax
0x18001eaae  jz      short loc_18001EABB
0x18001eab0  mov     rdx, rax
0x18001eab3  mov     rcx, rbx
0x18001eab6  call    SendNewCallHubEvent
0x18001eabb  mov     rcx, [rbx+18h]
0x18001eabf  mov     rdx, rdi
0x18001eac2  call    ReleaseHashTableEntryLock
0x18001eac7  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001eacd  shr     rbx, 4
0x18001ead1  and     rbx, rax
0x18001ead4  mov     rax, cs:gLockTable
0x18001eadb  lea     rcx, [rbx+rbx*4]
0x18001eadf  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001eae3  call    cs:__imp_LeaveCriticalSection
0x18001eae9  mov     rbx, [rsp+28h+arg_0]
0x18001eaee  xor     eax, eax
0x18001eaf0  add     rsp, 20h
0x18001eaf4  pop     rdi
0x18001eaf5  retn
```
