# WcInsertDirectoryTableEntry

- ea: `0x14001e94c`
- end: `0x14001ea71`
- name: `WcInsertDirectoryTableEntry`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001ea78`

## callees

- `0x14001e94c`
- `0x14002ee10`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x14001ea15`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14001ea15`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001e9e6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001e9e6`
- `ntoskrnl!RtlHashUnicodeString` at `0x14001e977`
- `ntoskrnl!RtlHashUnicodeString` at `0x14001e977`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ea41`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ea55`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ea41`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ea55`
- `ntoskrnl!ExAllocatePool2` at `0x14001e99d`
- `ntoskrnl!ExAllocatePool2` at `0x14001e99d`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001e9fa`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001e9fa`
- `FLTMGR!FltReleaseResource` at `0x14001ea25`
- `FLTMGR!FltReleaseResource` at `0x14001ea25`

## pseudocode

```c
__int64 __fastcall WcInsertDirectoryTableEntry(__int64 a1, const UNICODE_STRING *a2, __int64 a3)
{
  NTSTATUS UnicodeString; // edi
  __int64 Pool2; // rbx
  void *v8; // rcx
  ULONG HashValue; // [rsp+78h] [rbp+20h] BYREF

  HashValue = 0;
  UnicodeString = RtlHashUnicodeString(a2, 0, 0, &HashValue);
  if ( UnicodeString >= 0 )
  {
    Pool2 = ExAllocatePool2(256, 48, 1952727895);
    if ( Pool2 )
    {
      *(_WORD *)(Pool2 + 26) = a2->MaximumLength;
      *(_QWORD *)(Pool2 + 32) = 0;
      UnicodeString = WcAllocateUnicodeString(1852195671, Pool2 + 24);
      if ( UnicodeString < 0 )
      {
        v8 = *(void **)(Pool2 + 32);
        if ( v8 )
          ExFreePoolWithTag(v8, 0x6E664357u);
        ExFreePoolWithTag((PVOID)Pool2, 0x74644357u);
      }
      else
      {
        RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 24), a2);
        *(_QWORD *)(Pool2 + 40) = a3;
        FltAcquireResourceExclusive(*(PERESOURCE *)(a1 + 64));
        RtlInsertEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 72), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)Pool2, HashValue, 0);
        FltReleaseResource(*(PERESOURCE *)(a1 + 64));
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)UnicodeString;
}

```

## disassembly

```asm
0x14001e94c  push    rbx
0x14001e94e  push    rbp
0x14001e94f  push    rsi
0x14001e950  push    rdi
0x14001e951  push    r14
0x14001e953  push    r15
0x14001e955  sub     rsp, 28h
0x14001e959  mov     rsi, rdx
0x14001e95c  mov     [rsp+58h+HashValue], 0
0x14001e964  mov     r15, r8
0x14001e967  lea     r9, [rsp+58h+HashValue]; HashValue
0x14001e96c  mov     r14, rcx
0x14001e96f  xor     r8d, r8d; HashAlgorithm
0x14001e972  mov     rcx, rsi; String
0x14001e975  xor     edx, edx; CaseInSensitive
0x14001e977  call    cs:__imp_RtlHashUnicodeString
0x14001e97e  nop     dword ptr [rax+rax+00h]
0x14001e983  mov     edi, eax
0x14001e985  test    eax, eax
0x14001e987  js      loc_14001EA61
0x14001e98d  mov     edx, 30h ; '0'
0x14001e992  mov     ecx, 100h
0x14001e997  mov     r8d, 74644357h
0x14001e99d  call    cs:__imp_ExAllocatePool2
0x14001e9a4  nop     dword ptr [rax+rax+00h]
0x14001e9a9  mov     rbx, rax
0x14001e9ac  test    rax, rax
0x14001e9af  jnz     short loc_14001E9BB
0x14001e9b1  mov     edi, 0C000009Ah
0x14001e9b6  jmp     loc_14001EA61
0x14001e9bb  movzx   eax, word ptr [rsi+2]
0x14001e9bf  lea     rdx, [rbx+18h]
0x14001e9c3  mov     ecx, 6E664357h
0x14001e9c8  mov     [rbx+1Ah], ax
0x14001e9cc  mov     qword ptr [rbx+20h], 0
0x14001e9d4  call    WcAllocateUnicodeString
0x14001e9d9  mov     edi, eax
0x14001e9db  test    eax, eax
0x14001e9dd  js      short loc_14001EA33
0x14001e9df  mov     rdx, rsi; SourceString
0x14001e9e2  lea     rcx, [rbx+18h]; DestinationString
0x14001e9e6  call    cs:__imp_RtlCopyUnicodeString
0x14001e9ed  nop     dword ptr [rax+rax+00h]
0x14001e9f2  mov     [rbx+28h], r15
0x14001e9f6  mov     rcx, [r14+40h]; Resource
0x14001e9fa  call    cs:__imp_FltAcquireResourceExclusive
0x14001ea01  nop     dword ptr [rax+rax+00h]
0x14001ea06  mov     r8d, [rsp+58h+HashValue]; Signature
0x14001ea0b  lea     rcx, [r14+48h]; HashTable
0x14001ea0f  xor     r9d, r9d; Context
0x14001ea12  mov     rdx, rbx; Entry
0x14001ea15  call    cs:__imp_RtlInsertEntryHashTable
0x14001ea1c  nop     dword ptr [rax+rax+00h]
0x14001ea21  mov     rcx, [r14+40h]; Resource
0x14001ea25  call    cs:__imp_FltReleaseResource
0x14001ea2c  nop     dword ptr [rax+rax+00h]
0x14001ea31  jmp     short loc_14001EA61
0x14001ea33  mov     rcx, [rbx+20h]; P
0x14001ea37  test    rcx, rcx
0x14001ea3a  jz      short loc_14001EA4D
0x14001ea3c  mov     edx, 6E664357h; Tag
0x14001ea41  call    cs:__imp_ExFreePoolWithTag
0x14001ea48  nop     dword ptr [rax+rax+00h]
0x14001ea4d  mov     edx, 74644357h; Tag
0x14001ea52  mov     rcx, rbx; P
0x14001ea55  call    cs:__imp_ExFreePoolWithTag
0x14001ea5c  nop     dword ptr [rax+rax+00h]
0x14001ea61  mov     eax, edi
0x14001ea63  add     rsp, 28h
0x14001ea67  pop     r15
0x14001ea69  pop     r14
0x14001ea6b  pop     rdi
0x14001ea6c  pop     rsi
0x14001ea6d  pop     rbp
0x14001ea6e  pop     rbx
0x14001ea6f  retn
```
