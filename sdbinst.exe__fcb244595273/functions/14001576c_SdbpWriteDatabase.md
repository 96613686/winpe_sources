# SdbpWriteDatabase

- ea: `0x14001576c`
- end: `0x140015832`
- name: `SdbpWriteDatabase`
- size: `198`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140014574`
- `0x140018e34`

## callees

- `0x14001008c`
- `0x14001576c`
- `0x1400191a8`

## import_xrefs

- `ntdll!NtWriteFile` at `0x1400157f7`
- `ntdll!NtWriteFile` at `0x1400157f7`

## string_xrefs

- `0x14001578f`: `Failed to write compressed sdb.`
- `0x14001579c`: `SdbpWriteDatabase`
- `0x140015812`: `SdbpWriteDatabase`
- `0x140015801`: `Failed to write the sdb [%x]`

## pseudocode

```c
__int64 __fastcall SdbpWriteDatabase(__int64 a1)
{
  unsigned int v1; // ebx
  bool v2; // zf
  __int64 v3; // rax
  void *v4; // r10
  NTSTATUS v5; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp+8h] BYREF

  v1 = 0;
  v2 = (*(_BYTE *)(a1 + 24) & 4) == 0;
  IoStatusBlock = 0;
  if ( v2 )
  {
    v3 = *(_QWORD *)a1;
    ByteOffset.QuadPart = 0;
    if ( *(_DWORD *)(v3 + 72) )
      v4 = 0;
    else
      v4 = *(void **)(v3 + 8);
    v5 = NtWriteFile(v4, 0, 0, 0, &IoStatusBlock, *(PVOID *)(a1 + 8), *(_DWORD *)(a1 + 20), &ByteOffset, 0);
    if ( v5 < 0 )
    {
      AslLogCallPrintf(1, "SdbpWriteDatabase", 1716, "Failed to write the sdb [%x]", v5);
      return v1;
    }
    return 1;
  }
  if ( (unsigned int)SdbpWriteCompressedDatabase((__int64 *)a1) )
    return 1;
  AslLogCallPrintf(1, "SdbpWriteDatabase", 1695, "Failed to write compressed sdb.");
  return v1;
}

```

## disassembly

```asm
0x14001576c  push    rbx
0x14001576e  sub     rsp, 60h
0x140015772  xor     ebx, ebx
0x140015774  xorps   xmm0, xmm0
0x140015777  test    byte ptr [rcx+18h], 4
0x14001577b  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x140015780  jz      short loc_1400157AD
0x140015782  call    SdbpWriteCompressedDatabase
0x140015787  test    eax, eax
0x140015789  jnz     loc_140015825
0x14001578f  lea     r9, aFailedToWriteC; "Failed to write compressed sdb."
0x140015796  mov     r8d, 69Fh
0x14001579c  lea     rdx, aSdbpwritedatab; "SdbpWriteDatabase"
0x1400157a3  lea     ecx, [rbx+1]
0x1400157a6  call    AslLogCallPrintf
0x1400157ab  jmp     short loc_14001582A
0x1400157ad  mov     rax, [rcx]
0x1400157b0  mov     qword ptr [rsp+68h+arg_0], rbx
0x1400157b5  cmp     [rax+48h], ebx
0x1400157b8  jz      short loc_1400157BF
0x1400157ba  xor     r10d, r10d
0x1400157bd  jmp     short loc_1400157C3
0x1400157bf  mov     r10, [rax+8]
0x1400157c3  mov     [rsp+68h+Key], rbx; Key
0x1400157c8  lea     rax, [rsp+68h+arg_0]
0x1400157cd  mov     [rsp+68h+ByteOffset], rax; ByteOffset
0x1400157d2  xor     r9d, r9d; ApcContext
0x1400157d5  mov     eax, [rcx+14h]
0x1400157d8  xor     r8d, r8d; ApcRoutine
0x1400157db  mov     [rsp+68h+Length], eax; Length
0x1400157df  xor     edx, edx; Event
0x1400157e1  mov     rax, [rcx+8]
0x1400157e5  mov     rcx, r10; FileHandle
0x1400157e8  mov     [rsp+68h+Buffer], rax; Buffer
0x1400157ed  lea     rax, [rsp+68h+var_18]
0x1400157f2  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1400157f7  call    cs:__imp_NtWriteFile
0x1400157fd  test    eax, eax
0x1400157ff  jns     short loc_140015825
0x140015801  lea     r9, aFailedToWriteT_6; "Failed to write the sdb [%x]"
0x140015808  mov     dword ptr [rsp+68h+IoStatusBlock], eax
0x14001580c  mov     r8d, 6B4h
0x140015812  lea     rdx, aSdbpwritedatab; "SdbpWriteDatabase"
0x140015819  mov     ecx, 1
0x14001581e  call    AslLogCallPrintf
0x140015823  jmp     short loc_14001582A
0x140015825  mov     ebx, 1
0x14001582a  mov     eax, ebx
0x14001582c  add     rsp, 60h
0x140015830  pop     rbx
0x140015831  retn
```
