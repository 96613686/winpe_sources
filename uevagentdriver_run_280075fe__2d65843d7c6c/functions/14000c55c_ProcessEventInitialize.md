# ProcessEventInitialize

- ea: `0x14000c55c`
- end: `0x14000c60c`
- name: `ProcessEventInitialize`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c614`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x14000a900`
- `0x14000aad0`
- `0x14000b03c`
- `0x14000c078`
- `0x14000c55c`

## import_xrefs

- `ntoskrnl!KeInitializeGuardedMutex` at `0x14000c58a`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14000c58a`

## string_xrefs

- `0x14000c5be`: `UevFilter.ProcessEventInitialize: Failed to allocate completion port. Status = 0x%0X.\n`

## pseudocode

```c
__int64 ProcessEventInitialize()
{
  int FilterHashTable; // ebx

  DbgTrace(2, "UevFilter.ProcessEventInitialize: Entry\n");
  if ( (unsigned __int8)IsSupportedVersion() )
  {
    byte_140007138 = 1;
    KeInitializeGuardedMutex(&Mutex);
    FilterHashTable = AllocateFilterHashTable();
    if ( FilterHashTable >= 0 )
    {
      FilterHashTable = CreateProcessEventCompletionPort();
      if ( FilterHashTable < 0 )
      {
        DbgTraceFrmtErr("UevFilter.ProcessEventInitialize: Failed to allocate completion port. Status = 0x%0X.\n");
        FreeFilterHashTable();
        P = 0;
      }
    }
    else
    {
      DbgTraceFrmtErr("UevFilter.ProcessEventInitialize: Failed to allocate a hash table. Status = 0x%0X.\n");
    }
  }
  else
  {
    DbgTraceFrmt(2, "UevFilter.ProcessEventInitialize: OS version is not supported.");
    FilterHashTable = 0;
  }
  DbgTraceFrmt(2, "UevFilter.ProcessEventInitialize: Exit, status = 0x%0X.\n", FilterHashTable);
  return (unsigned int)FilterHashTable;
}

```

## disassembly

```asm
0x14000c55c  push    rbx
0x14000c55e  sub     rsp, 20h
0x14000c562  lea     rdx, aUevfilterProce_4; "UevFilter.ProcessEventInitialize: Entry"...
0x14000c569  mov     ecx, 2
0x14000c56e  call    DbgTrace
0x14000c573  call    IsSupportedVersion
0x14000c578  test    al, al
0x14000c57a  jz      short loc_14000C5DC
0x14000c57c  lea     rcx, Mutex; Mutex
0x14000c583  mov     cs:byte_140007138, 1
0x14000c58a  call    cs:__imp_KeInitializeGuardedMutex
0x14000c591  nop     dword ptr [rax+rax+00h]
0x14000c596  call    AllocateFilterHashTable
0x14000c59b  mov     ebx, eax
0x14000c59d  test    eax, eax
0x14000c59f  jns     short loc_14000C5B1
0x14000c5a1  mov     edx, eax
0x14000c5a3  lea     rcx, aUevfilterProce_9; "UevFilter.ProcessEventInitialize: Faile"...
0x14000c5aa  call    DbgTraceFrmtErr
0x14000c5af  jmp     short loc_14000C5EF
0x14000c5b1  call    CreateProcessEventCompletionPort
0x14000c5b6  mov     ebx, eax
0x14000c5b8  test    eax, eax
0x14000c5ba  jns     short loc_14000C5EF
0x14000c5bc  mov     edx, eax
0x14000c5be  lea     rcx, aUevfilterProce_8; "UevFilter.ProcessEventInitialize: Faile"...
0x14000c5c5  call    DbgTraceFrmtErr
0x14000c5ca  call    FreeFilterHashTable
0x14000c5cf  mov     cs:P, 0
0x14000c5da  jmp     short loc_14000C5EF
0x14000c5dc  lea     rdx, aUevfilterProce_0; "UevFilter.ProcessEventInitialize: OS ve"...
0x14000c5e3  mov     ecx, 2
0x14000c5e8  call    DbgTraceFrmt
0x14000c5ed  xor     ebx, ebx
0x14000c5ef  mov     r8d, ebx
0x14000c5f2  lea     rdx, aUevfilterProce_3; "UevFilter.ProcessEventInitialize: Exit,"...
0x14000c5f9  mov     ecx, 2
0x14000c5fe  call    DbgTraceFrmt
0x14000c603  mov     eax, ebx
0x14000c605  add     rsp, 20h
0x14000c609  pop     rbx
0x14000c60a  retn
```
