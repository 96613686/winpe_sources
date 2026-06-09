# SdbpCompressExistingDatabase

- ea: `0x140018e34`
- end: `0x14001900f`
- name: `SdbpCompressExistingDatabase`
- size: `475`
- prototype: `__int64 __fastcall(const wchar_t *, const WCHAR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001a678`

## callees

- `0x140002206`
- `0x14000f644`
- `0x14000f980`
- `0x14001008c`
- `0x14001576c`
- `0x140015934`
- `0x140016198`
- `0x140017730`
- `0x140018e34`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140018f38`
- `KERNEL32!CreateFileW` at `0x140018f38`
- `ntdll!RtlAllocateHeap` at `0x140018e91`
- `ntdll!RtlAllocateHeap` at `0x140018e91`
- `ntdll!NtClose` at `0x140018fc6`
- `ntdll!NtClose` at `0x140018fc6`
- `ntdll!RtlFreeHeap` at `0x140018fed`
- `ntdll!RtlFreeHeap` at `0x140018fed`

## string_xrefs

- `0x140018f47`: `Failed to create file`
- `0x140018f77`: `Failed to create file mapping [%x]`
- `0x140018eec`: `Failed to open copy of SDB in memory`
- `0x140018e67`: `SdbpCompressExistingDatabase`
- `0x140018eb3`: `SdbpCompressExistingDatabase`
- `0x140018ef9`: `SdbpCompressExistingDatabase`
- `0x140018f54`: `SdbpCompressExistingDatabase`
- `0x140018f88`: `SdbpCompressExistingDatabase`
- `0x140018e5a`: `Failed to open original DB`

## pseudocode

```c
__int64 __fastcall SdbpCompressExistingDatabase(const wchar_t *a1, const WCHAR *a2)
{
  unsigned int v2; // ebp
  _BYTE **v4; // rax
  _BYTE **v5; // rbx
  PVOID Heap; // rsi
  _BYTE **v7; // rdi
  HANDLE FileW; // rax
  void *v9; // rbx
  int v10; // eax

  v2 = 0;
  v4 = SdbOpenDatabaseEx(a1, (__int64)a2, 1u);
  v5 = v4;
  if ( !v4 )
  {
    AslLogCallPrintf(1, "SdbpCompressExistingDatabase", 629, "Failed to open original DB");
    return v2;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, *((unsigned int *)v4 + 5));
  if ( !Heap )
  {
    AslLogCallPrintf(
      1,
      "SdbpCompressExistingDatabase",
      635,
      "Failed to allocate %d bytes: Out of memory",
      *((_DWORD *)v5 + 5));
    goto LABEL_19;
  }
  memcpy_0(Heap, v5[1], *((unsigned int *)v5 + 5));
  v7 = (_BYTE **)SdbpOpenDatabaseInMemory(Heap, *((unsigned int *)v5 + 5), 0);
  if ( !v7 )
  {
    AslLogCallPrintf(1, "SdbpCompressExistingDatabase", 643, "Failed to open copy of SDB in memory");
    goto LABEL_18;
  }
  SdbCloseDatabaseRead(v5);
  FileW = CreateFileW(a2, 0xC0100080, 0, 0, 2u, 0x80u, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    AslLogCallPrintf(1, "SdbpCompressExistingDatabase", 665, "Failed to create file");
  }
  else
  {
    v10 = AslFileMappingCreate(v7, a2, (__int64)FileW);
    if ( v10 >= 0 )
    {
      *((_DWORD *)v7 + 6) |= 0xCu;
      Heap = 0;
      v2 = SdbpWriteDatabase(v7);
    }
    else
    {
      AslLogCallPrintf(1, "SdbpCompressExistingDatabase", 676, "Failed to create file mapping [%x]", v10);
    }
  }
  if ( *v7 )
  {
    AslFileMappingDelete(*v7);
    *v7 = 0;
  }
  if ( v9 != (void *)-1LL )
    NtClose(v9);
  SdbCloseDatabaseRead(v7);
  if ( Heap )
  {
    v5 = 0;
LABEL_18:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( !v5 )
      return v2;
LABEL_19:
    SdbCloseDatabaseRead(v5);
  }
  return v2;
}

```

## disassembly

```asm
0x140018e34  push    rbx
0x140018e36  push    rbp
0x140018e37  push    rsi
0x140018e38  push    rdi
0x140018e39  push    r14
0x140018e3b  push    r15
0x140018e3d  sub     rsp, 48h
0x140018e41  xor     ebp, ebp
0x140018e43  mov     r14, rdx
0x140018e46  lea     r15d, [rbp+1]
0x140018e4a  mov     r8d, r15d
0x140018e4d  call    SdbOpenDatabaseEx
0x140018e52  mov     rbx, rax
0x140018e55  test    rax, rax
0x140018e58  jnz     short loc_140018E7B
0x140018e5a  lea     r9, aFailedToOpenOr; "Failed to open original DB"
0x140018e61  mov     r8d, 275h
0x140018e67  lea     rdx, aSdbpcompressex; "SdbpCompressExistingDatabase"
0x140018e6e  mov     ecx, r15d
0x140018e71  call    AslLogCallPrintf
0x140018e76  jmp     loc_140019000
0x140018e7b  mov     rcx, gs:60h
0x140018e84  mov     edx, 8; Flags
0x140018e89  mov     r8d, [rax+14h]; Size
0x140018e8d  mov     rcx, [rcx+30h]; HeapHandle
0x140018e91  call    cs:__imp_RtlAllocateHeap
0x140018e97  mov     rsi, rax
0x140018e9a  mov     eax, [rbx+14h]
0x140018e9d  test    rsi, rsi
0x140018ea0  jnz     short loc_140018EC7
0x140018ea2  lea     r9, aFailedToAlloca_7; "Failed to allocate %d bytes: Out of mem"...
0x140018ea9  mov     [rsp+78h+dwCreationDisposition], eax
0x140018ead  mov     r8d, 27Bh
0x140018eb3  lea     rdx, aSdbpcompressex; "SdbpCompressExistingDatabase"
0x140018eba  mov     ecx, r15d
0x140018ebd  call    AslLogCallPrintf
0x140018ec2  jmp     loc_140018FF8
0x140018ec7  mov     rdx, [rbx+8]; Src
0x140018ecb  mov     r8, rax; Size
0x140018ece  mov     rcx, rsi; void *
0x140018ed1  call    memcpy_0
0x140018ed6  mov     edx, [rbx+14h]
0x140018ed9  xor     r8d, r8d
0x140018edc  mov     rcx, rsi
0x140018edf  call    SdbpOpenDatabaseInMemory
0x140018ee4  mov     rdi, rax
0x140018ee7  test    rax, rax
0x140018eea  jnz     short loc_140018F0D
0x140018eec  lea     r9, aFailedToOpenCo; "Failed to open copy of SDB in memory"
0x140018ef3  mov     r8d, 283h
0x140018ef9  lea     rdx, aSdbpcompressex; "SdbpCompressExistingDatabase"
0x140018f00  mov     ecx, r15d
0x140018f03  call    AslLogCallPrintf
0x140018f08  jmp     loc_140018FDB
0x140018f0d  mov     rcx, rbx
0x140018f10  call    SdbCloseDatabaseRead
0x140018f15  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x140018f1a  xor     r9d, r9d; lpSecurityAttributes
0x140018f1d  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140018f25  xor     r8d, r8d; dwShareMode
0x140018f28  mov     edx, 0C0100080h; dwDesiredAccess
0x140018f2d  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x140018f35  mov     rcx, r14; lpFileName
0x140018f38  call    cs:__imp_CreateFileW
0x140018f3e  mov     rbx, rax
0x140018f41  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140018f45  jnz     short loc_140018F65
0x140018f47  lea     r9, aFailedToCreate_8; "Failed to create file"
0x140018f4e  mov     r8d, 299h
0x140018f54  lea     rdx, aSdbpcompressex; "SdbpCompressExistingDatabase"
0x140018f5b  mov     ecx, r15d
0x140018f5e  call    AslLogCallPrintf
0x140018f63  jmp     short loc_140018FA9
0x140018f65  mov     r8, rbx
0x140018f68  mov     rdx, r14
0x140018f6b  mov     rcx, rdi
0x140018f6e  call    AslFileMappingCreate
0x140018f73  test    eax, eax
0x140018f75  jns     short loc_140018F99
0x140018f77  lea     r9, aFailedToCreate_2; "Failed to create file mapping [%x]"
0x140018f7e  mov     [rsp+78h+dwCreationDisposition], eax
0x140018f82  mov     r8d, 2A4h
0x140018f88  lea     rdx, aSdbpcompressex; "SdbpCompressExistingDatabase"
0x140018f8f  mov     ecx, r15d
0x140018f92  call    AslLogCallPrintf
0x140018f97  jmp     short loc_140018FA9
0x140018f99  or      dword ptr [rdi+18h], 0Ch
0x140018f9d  xor     esi, esi
0x140018f9f  mov     rcx, rdi
0x140018fa2  call    SdbpWriteDatabase
0x140018fa7  mov     ebp, eax
0x140018fa9  mov     rcx, [rdi]; P
0x140018fac  test    rcx, rcx
0x140018faf  jz      short loc_140018FBD
0x140018fb1  call    AslFileMappingDelete
0x140018fb6  mov     qword ptr [rdi], 0
0x140018fbd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140018fc1  jz      short loc_140018FCC
0x140018fc3  mov     rcx, rbx; Handle
0x140018fc6  call    cs:__imp_NtClose
0x140018fcc  mov     rcx, rdi
0x140018fcf  call    SdbCloseDatabaseRead
0x140018fd4  test    rsi, rsi
0x140018fd7  jz      short loc_140019000
0x140018fd9  xor     ebx, ebx
0x140018fdb  mov     rcx, gs:60h
0x140018fe4  mov     r8, rsi; P
0x140018fe7  xor     edx, edx; Flags
0x140018fe9  mov     rcx, [rcx+30h]; HeapHandle
0x140018fed  call    cs:__imp_RtlFreeHeap
0x140018ff3  test    rbx, rbx
0x140018ff6  jz      short loc_140019000
0x140018ff8  mov     rcx, rbx
0x140018ffb  call    SdbCloseDatabaseRead
0x140019000  mov     eax, ebp
0x140019002  add     rsp, 48h
0x140019006  pop     r15
0x140019008  pop     r14
0x14001900a  pop     rdi
0x14001900b  pop     rsi
0x14001900c  pop     rbp
0x14001900d  pop     rbx
0x14001900e  retn
```
