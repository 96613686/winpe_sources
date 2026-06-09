# SdbpCreateDatabaseInMemory

- ea: `0x1400152d8`
- end: `0x14001539e`
- name: `SdbpCreateDatabaseInMemory`
- size: `198`
- prototype: `void *()`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140015104`
- `0x14001d808`

## callees

- `0x14001008c`
- `0x1400152d8`
- `0x14001561c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140015307`
- `ntdll!RtlAllocateHeap` at `0x140015307`
- `ntdll!RtlFreeHeap` at `0x14001538d`
- `ntdll!RtlFreeHeap` at `0x14001538d`

## string_xrefs

- `0x140015322`: `SdbpCreateDatabaseInMemory`
- `0x14001536c`: `SdbpCreateDatabaseInMemory`
- `0x14001535f`: `Failed to write the header to disk`

## pseudocode

```c
void *SdbpCreateDatabaseInMemory()
{
  PVOID Heap; // rax
  void *v1; // rbx
  __int64 v3; // [rsp+30h] [rbp-18h] BYREF
  int v4; // [rsp+38h] [rbp-10h]

  v4 = 1717724275;
  v3 = 3;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v1 = Heap;
  if ( Heap )
  {
    *((_DWORD *)Heap + 6) |= 9u;
    *((_DWORD *)Heap + 4) = 1;
    if ( !(unsigned int)SdbpWriteBufferedData(Heap, 0, &v3, 12, 0) )
    {
      AslLogCallPrintf(1, "SdbpCreateDatabaseInMemory", 334, "Failed to write the header to disk");
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
      return 0;
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpCreateDatabaseInMemory", 317, "Failed to allocate PDB");
  }
  return v1;
}

```

## disassembly

```asm
0x1400152d8  push    rbx
0x1400152da  sub     rsp, 40h
0x1400152de  mov     rcx, gs:60h
0x1400152e7  mov     edx, 8; Flags
0x1400152ec  mov     r8d, 0A80h; Size
0x1400152f2  mov     [rsp+48h+var_10], 66626473h
0x1400152fa  mov     [rsp+48h+var_18], 3
0x140015303  mov     rcx, [rcx+30h]; HeapHandle
0x140015307  call    cs:__imp_RtlAllocateHeap
0x14001530d  mov     rbx, rax
0x140015310  test    rax, rax
0x140015313  jnz     short loc_140015333
0x140015315  lea     r9, aFailedToAlloca_1; "Failed to allocate PDB"
0x14001531c  mov     r8d, 13Dh
0x140015322  lea     rdx, aSdbpcreatedata; "SdbpCreateDatabaseInMemory"
0x140015329  lea     ecx, [rax+1]
0x14001532c  call    AslLogCallPrintf
0x140015331  jmp     short loc_140015395
0x140015333  or      dword ptr [rax+18h], 9
0x140015337  lea     r8, [rsp+48h+var_18]
0x14001533c  mov     r9d, 0Ch
0x140015342  mov     dword ptr [rax+10h], 1
0x140015349  xor     edx, edx
0x14001534b  mov     [rsp+48h+var_28], 0
0x140015353  mov     rcx, rbx
0x140015356  call    SdbpWriteBufferedData
0x14001535b  test    eax, eax
0x14001535d  jnz     short loc_140015395
0x14001535f  lea     r9, aFailedToWriteT_7; "Failed to write the header to disk"
0x140015366  mov     r8d, 14Eh
0x14001536c  lea     rdx, aSdbpcreatedata; "SdbpCreateDatabaseInMemory"
0x140015373  lea     ecx, [rax+1]
0x140015376  call    AslLogCallPrintf
0x14001537b  mov     rcx, gs:60h
0x140015384  mov     r8, rbx; P
0x140015387  xor     edx, edx; Flags
0x140015389  mov     rcx, [rcx+30h]; HeapHandle
0x14001538d  call    cs:__imp_RtlFreeHeap
0x140015393  xor     ebx, ebx
0x140015395  mov     rax, rbx
0x140015398  add     rsp, 40h
0x14001539c  pop     rbx
0x14001539d  retn
```
