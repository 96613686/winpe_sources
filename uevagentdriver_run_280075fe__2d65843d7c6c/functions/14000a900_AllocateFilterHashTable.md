# AllocateFilterHashTable

- ea: `0x14000a900`
- end: `0x14000a98d`
- name: `AllocateFilterHashTable`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c55c`

## callees

- `0x140001118`
- `0x1400015c0`
- `0x140001b40`
- `0x14000a900`

## pseudocode

```c
__int64 __fastcall AllocateFilterHashTable(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rcx
  int GenericBuffer; // ebx
  __int64 v5; // r8

  DbgTrace(2, "UevFilter.AllocateFilterHashTable: Entry\n", a3);
  GenericBuffer = AllocateGenericBuffer(v3, 24224, (__int64 *)&P);
  if ( GenericBuffer >= 0 )
  {
    memset(P, 0, 0x5EA0u);
    *((_DWORD *)P + 4) = 1009;
    *(_QWORD *)P = GenerateSessionTableHash;
    *((_QWORD *)P + 1) = &FreeHashTableEntry;
  }
  DbgTrace(2, "UevFilter.AllocateFilterHashTable: Exit\n", v5);
  return (unsigned int)GenericBuffer;
}

```

## disassembly

```asm
0x14000a900  push    rbx
0x14000a902  sub     rsp, 20h
0x14000a906  lea     rdx, aUevfilterAlloc_1; "UevFilter.AllocateFilterHashTable: Entr"...
0x14000a90d  mov     ecx, 2
0x14000a912  call    DbgTrace
0x14000a917  lea     r8, P
0x14000a91e  mov     edx, 5EA0h
0x14000a923  call    AllocateGenericBuffer
0x14000a928  mov     ebx, eax
0x14000a92a  test    eax, eax
0x14000a92c  js      short loc_14000A973
0x14000a92e  mov     rcx, cs:P; void *
0x14000a935  xor     edx, edx; Val
0x14000a937  mov     r8d, 5EA0h; Size
0x14000a93d  call    memset
0x14000a942  mov     rdx, cs:P
0x14000a949  lea     rax, GenerateSessionTableHash
0x14000a950  mov     dword ptr [rdx+10h], 3F1h
0x14000a957  mov     rdx, cs:P
0x14000a95e  mov     [rdx], rax
0x14000a961  lea     rax, FreeHashTableEntry
0x14000a968  mov     rdx, cs:P
0x14000a96f  mov     [rdx+8], rax
0x14000a973  lea     rdx, aUevfilterAlloc_2; "UevFilter.AllocateFilterHashTable: Exit"...
0x14000a97a  mov     ecx, 2
0x14000a97f  call    DbgTrace
0x14000a984  mov     eax, ebx
0x14000a986  add     rsp, 20h
0x14000a98a  pop     rbx
0x14000a98b  retn
```
