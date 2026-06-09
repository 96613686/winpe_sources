# WcAddInMemoryTombstone

- ea: `0x14001bcec`
- end: `0x14001bf1e`
- name: `WcAddInMemoryTombstone`
- size: `562`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001c244`
- `0x14001c688`
- `0x140027f24`
- `0x1400343c0`

## callees

- `0x1400016f0`
- `0x14001bcec`
- `0x140029608`
- `0x14002ee54`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14001bef3`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001bef3`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14001be7b`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14001be7b`
- `ntoskrnl!RtlCreateHashTable` at `0x14001be43`
- `ntoskrnl!RtlCreateHashTable` at `0x14001be43`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x14001bdd9`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x14001bdd9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001be24`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001be24`
- `ntoskrnl!KeSetEvent` at `0x14001be8f`
- `ntoskrnl!KeSetEvent` at `0x14001be8f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001bdc4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001bdc4`
- `ntoskrnl!RtlHashUnicodeString` at `0x14001bdfb`
- `ntoskrnl!RtlHashUnicodeString` at `0x14001bdfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bede`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bede`
- `ntoskrnl!ExAllocatePool2` at `0x14001bd8a`
- `ntoskrnl!ExAllocatePool2` at `0x14001bd8a`
- `FLTMGR!FltReleaseContext` at `0x14001beb1`
- `FLTMGR!FltReleaseContext` at `0x14001bec5`
- `FLTMGR!FltReleaseContext` at `0x14001beb1`
- `FLTMGR!FltReleaseContext` at `0x14001bec5`

## pseudocode

```c
__int64 __fastcall WcAddInMemoryTombstone(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        UNICODE_STRING *a3,
        char a4,
        struct _FILE_OBJECT *FileObject)
{
  NTSTATUS v5; // ebx
  __int64 UnionContext; // r14
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v10; // rdi
  int SetContextFileObject; // eax
  char *v12; // rsi
  __int64 Pool2; // rax
  int Timeout; // [rsp+20h] [rbp-40h]
  ULONG HashValue; // [rsp+40h] [rbp-20h] BYREF
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+48h] [rbp-18h] BYREF
  PFLT_CONTEXT v18; // [rsp+50h] [rbp-10h] BYREF
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-8h] BYREF

  v5 = 0;
  Context = 0;
  v18 = 0;
  HashValue = 0;
  HashTable = 0;
  UnionContext = WcGetUnionContext(a1, a2, FileObject);
  if ( !UnionContext )
    goto LABEL_20;
  v10 = 0;
  SetContextFileObject = WcGetSetContextFileObject(a2, FileObject, Timeout, (__int64)&Context, (__int64)&v18);
  v12 = (char *)v18;
  v5 = SetContextFileObject;
  if ( SetContextFileObject < 0 )
  {
    if ( SetContextFileObject != -1073741195 )
      goto LABEL_14;
LABEL_13:
    v5 = 0;
    goto LABEL_14;
  }
  if ( SetContextFileObject == 260 )
    goto LABEL_13;
  if ( v18 )
  {
    Pool2 = ExAllocatePool2(256, a3->MaximumLength + 48LL, 1952990039);
    v10 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)Pool2;
    if ( !Pool2 )
    {
LABEL_6:
      v5 = -1073741670;
      goto LABEL_14;
    }
    *(_BYTE *)(Pool2 + 24) = a4;
    *(_QWORD *)(Pool2 + 40) = Pool2 + 48;
    *(_WORD *)(Pool2 + 34) = a3->MaximumLength;
    RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 32), a3);
    v5 = RtlDowncaseUnicodeString(a3, a3, 0);
    if ( v5 < 0 )
      goto LABEL_14;
    v5 = RtlHashUnicodeString(a3, 1u, 0, &HashValue);
    KeWaitForSingleObject(v12 + 232, Executive, 0, 0, 0);
    if ( !*((_QWORD *)v12 + 32) )
    {
      if ( !RtlCreateHashTable(&HashTable, 0, 0) )
        goto LABEL_6;
      *((_QWORD *)v12 + 32) = HashTable;
      HashTable = 0;
    }
    RtlInsertEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)v12 + 32), v10, HashValue, 0);
    KeSetEvent((PRKEVENT)(v12 + 232), 0, 0);
    v10 = 0;
  }
LABEL_14:
  if ( Context )
    FltReleaseContext(Context);
  if ( v12 )
    FltReleaseContext(v12);
  if ( v10 )
    ExFreePoolWithTag(v10, 0x74684357u);
LABEL_20:
  if ( HashTable )
    RtlDeleteHashTable(HashTable);
  if ( UnionContext )
    WcReleaseUnionContext(UnionContext);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001bcec  push    rbp
0x14001bcee  push    rbx
0x14001bcef  push    rsi
0x14001bcf0  push    rdi
0x14001bcf1  push    r12
0x14001bcf3  push    r14
0x14001bcf5  push    r15
0x14001bcf7  mov     rbp, rsp
0x14001bcfa  sub     rsp, 60h
0x14001bcfe  xor     ebx, ebx
0x14001bd00  mov     r15, r8
0x14001bd03  mov     r8, [rbp+FileObject]
0x14001bd07  mov     r12b, r9b
0x14001bd0a  mov     [rbp+Context], rbx
0x14001bd0e  mov     rsi, rdx
0x14001bd11  mov     [rbp+var_10], rbx
0x14001bd15  mov     [rbp+HashValue], ebx
0x14001bd18  mov     [rbp+HashTable], rbx
0x14001bd1c  call    WcGetUnionContext
0x14001bd21  mov     r14, rax
0x14001bd24  test    rax, rax
0x14001bd27  jz      loc_14001BEEA
0x14001bd2d  mov     rdx, [rbp+FileObject]; FileObject
0x14001bd31  lea     rax, [rbp+var_10]
0x14001bd35  mov     [rsp+60h+var_30], rax; __int64
0x14001bd3a  lea     r9d, [rbx+1]
0x14001bd3e  lea     rax, [rbp+Context]
0x14001bd42  mov     r8, r14
0x14001bd45  mov     rcx, rsi; Instance
0x14001bd48  mov     [rsp+60h+var_38], rax; __int64
0x14001bd4d  xor     edi, edi
0x14001bd4f  call    WcGetSetContextFileObject
0x14001bd54  mov     rsi, [rbp+var_10]
0x14001bd58  mov     ebx, eax
0x14001bd5a  test    eax, eax
0x14001bd5c  js      loc_14001BE9F
0x14001bd62  cmp     eax, 104h
0x14001bd67  jz      loc_14001BEA6
0x14001bd6d  test    rsi, rsi
0x14001bd70  jz      loc_14001BEA8
0x14001bd76  movzx   edx, word ptr [r15+2]
0x14001bd7b  mov     ecx, 100h
0x14001bd80  add     rdx, 30h ; '0'
0x14001bd84  mov     r8d, 74684357h
0x14001bd8a  call    cs:__imp_ExAllocatePool2
0x14001bd91  nop     dword ptr [rax+rax+00h]
0x14001bd96  mov     rdi, rax
0x14001bd99  test    rax, rax
0x14001bd9c  jnz     short loc_14001BDA8
0x14001bd9e  mov     ebx, 0C000009Ah
0x14001bda3  jmp     loc_14001BEA8
0x14001bda8  mov     [rax+18h], r12b
0x14001bdac  lea     rcx, [rdi+20h]; DestinationString
0x14001bdb0  add     rax, 30h ; '0'
0x14001bdb4  mov     rdx, r15; SourceString
0x14001bdb7  mov     [rdi+28h], rax
0x14001bdbb  movzx   eax, word ptr [r15+2]
0x14001bdc0  mov     [rdi+22h], ax
0x14001bdc4  call    cs:__imp_RtlCopyUnicodeString
0x14001bdcb  nop     dword ptr [rax+rax+00h]
0x14001bdd0  xor     r8d, r8d; AllocateDestinationString
0x14001bdd3  mov     rdx, r15; SourceString
0x14001bdd6  mov     rcx, r15; DestinationString
0x14001bdd9  call    cs:__imp_RtlDowncaseUnicodeString
0x14001bde0  nop     dword ptr [rax+rax+00h]
0x14001bde5  mov     ebx, eax
0x14001bde7  test    eax, eax
0x14001bde9  js      loc_14001BEA8
0x14001bdef  lea     r9, [rbp+HashValue]; HashValue
0x14001bdf3  xor     r8d, r8d; HashAlgorithm
0x14001bdf6  mov     dl, 1; CaseInSensitive
0x14001bdf8  mov     rcx, r15; String
0x14001bdfb  call    cs:__imp_RtlHashUnicodeString
0x14001be02  nop     dword ptr [rax+rax+00h]
0x14001be07  lea     r15, [rsi+0E8h]
0x14001be0e  mov     [rsp+60h+Timeout], 0; Timeout
0x14001be17  mov     rcx, r15; Object
0x14001be1a  xor     r9d, r9d; Alertable
0x14001be1d  xor     r8d, r8d; WaitMode
0x14001be20  xor     edx, edx; WaitReason
0x14001be22  mov     ebx, eax
0x14001be24  call    cs:__imp_KeWaitForSingleObject
0x14001be2b  nop     dword ptr [rax+rax+00h]
0x14001be30  cmp     qword ptr [rsi+100h], 0
0x14001be38  jnz     short loc_14001BE6A
0x14001be3a  xor     r8d, r8d; Flags
0x14001be3d  lea     rcx, [rbp+HashTable]; HashTable
0x14001be41  xor     edx, edx; Shift
0x14001be43  call    cs:__imp_RtlCreateHashTable
0x14001be4a  nop     dword ptr [rax+rax+00h]
0x14001be4f  test    al, al
0x14001be51  jz      loc_14001BD9E
0x14001be57  mov     rax, [rbp+HashTable]
0x14001be5b  mov     [rsi+100h], rax
0x14001be62  mov     [rbp+HashTable], 0
0x14001be6a  mov     r8d, [rbp+HashValue]; Signature
0x14001be6e  xor     r9d, r9d; Context
0x14001be71  mov     rcx, [rsi+100h]; HashTable
0x14001be78  mov     rdx, rdi; Entry
0x14001be7b  call    cs:__imp_RtlInsertEntryHashTable
0x14001be82  nop     dword ptr [rax+rax+00h]
0x14001be87  xor     r8d, r8d; Wait
0x14001be8a  xor     edx, edx; Increment
0x14001be8c  mov     rcx, r15; Event
0x14001be8f  call    cs:__imp_KeSetEvent
0x14001be96  nop     dword ptr [rax+rax+00h]
0x14001be9b  xor     edi, edi
0x14001be9d  jmp     short loc_14001BEA8
0x14001be9f  cmp     eax, 0C0000275h
0x14001bea4  jnz     short loc_14001BEA8
0x14001bea6  xor     ebx, ebx
0x14001bea8  mov     rcx, [rbp+Context]; Context
0x14001beac  test    rcx, rcx
0x14001beaf  jz      short loc_14001BEBD
0x14001beb1  call    cs:__imp_FltReleaseContext
0x14001beb8  nop     dword ptr [rax+rax+00h]
0x14001bebd  test    rsi, rsi
0x14001bec0  jz      short loc_14001BED1
0x14001bec2  mov     rcx, rsi; Context
0x14001bec5  call    cs:__imp_FltReleaseContext
0x14001becc  nop     dword ptr [rax+rax+00h]
0x14001bed1  test    rdi, rdi
0x14001bed4  jz      short loc_14001BEEA
0x14001bed6  mov     edx, 74684357h; Tag
0x14001bedb  mov     rcx, rdi; P
0x14001bede  call    cs:__imp_ExFreePoolWithTag
0x14001bee5  nop     dword ptr [rax+rax+00h]
0x14001beea  mov     rcx, [rbp+HashTable]; HashTable
0x14001beee  test    rcx, rcx
0x14001bef1  jz      short loc_14001BEFF
0x14001bef3  call    cs:__imp_RtlDeleteHashTable
0x14001befa  nop     dword ptr [rax+rax+00h]
0x14001beff  test    r14, r14
0x14001bf02  jz      short loc_14001BF0C
0x14001bf04  mov     rcx, r14
0x14001bf07  call    WcReleaseUnionContext
0x14001bf0c  mov     eax, ebx
0x14001bf0e  add     rsp, 60h
0x14001bf12  pop     r15
0x14001bf14  pop     r14
0x14001bf16  pop     r12
0x14001bf18  pop     rdi
0x14001bf19  pop     rsi
0x14001bf1a  pop     rbx
0x14001bf1b  pop     rbp
0x14001bf1c  retn
```
