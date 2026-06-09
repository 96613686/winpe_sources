# WcLookupDirectoryTableEntry

- ea: `0x14002f670`
- end: `0x14002f758`
- name: `WcLookupDirectoryTableEntry`
- size: `232`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, ULONG_PTR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002a664`
- `0x1400302cc`

## callees

- `0x14002f670`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002f721`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002f721`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002f6ea`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002f6ea`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002f708`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002f708`
- `ntoskrnl!RtlHashUnicodeString` at `0x14002f6a6`
- `ntoskrnl!RtlHashUnicodeString` at `0x14002f6a6`
- `FLTMGR!FltAcquireResourceShared` at `0x14002f6ce`
- `FLTMGR!FltAcquireResourceShared` at `0x14002f6ce`
- `FLTMGR!FltReleaseResource` at `0x14002f73c`
- `FLTMGR!FltReleaseResource` at `0x14002f73c`

## pseudocode

```c
__int64 __fastcall WcLookupDirectoryTableEntry(__int64 a1, const UNICODE_STRING *a2, ULONG_PTR *a3)
{
  NTSTATUS v6; // edi
  struct _ERESOURCE *v7; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v9; // rbx
  _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-58h] BYREF
  ULONG_PTR Signature; // [rsp+98h] [rbp+20h] BYREF

  LODWORD(Signature) = 0;
  memset(&Context, 0, sizeof(Context));
  v6 = RtlHashUnicodeString(a2, 0, 0, (PULONG)&Signature);
  if ( v6 >= 0 )
  {
    v7 = *(struct _ERESOURCE **)(a1 + 64);
    *(_OWORD *)&Context.ChainHead = 0;
    v6 = -1073741766;
    FltAcquireResourceShared(v7);
    for ( i = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 72), (unsigned int)Signature, &Context);
          ;
          i = RtlGetNextEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 72), &Context) )
    {
      v9 = i;
      if ( !i )
        break;
      if ( RtlEqualUnicodeString(a2, (PCUNICODE_STRING)&i[1], 0) )
      {
        v6 = 0;
        *a3 = v9[1].Signature;
        break;
      }
    }
    FltReleaseResource(*(PERESOURCE *)(a1 + 64));
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002f670  mov     r11, rsp
0x14002f673  push    rbx
0x14002f674  push    rbp
0x14002f675  push    rsi
0x14002f676  push    rdi
0x14002f677  push    r14
0x14002f679  push    r15
0x14002f67b  sub     rsp, 48h
0x14002f67f  mov     r14, rdx
0x14002f682  lea     r9, [r11+20h]; HashValue
0x14002f686  xor     eax, eax
0x14002f688  xorps   xmm0, xmm0
0x14002f68b  mov     r15, r8
0x14002f68e  mov     [r11+20h], eax
0x14002f692  mov     rsi, rcx
0x14002f695  xor     r8d, r8d; HashAlgorithm
0x14002f698  movups  xmmword ptr [rsp+78h+Context.ChainHead], xmm0
0x14002f69d  mov     rcx, r14; String
0x14002f6a0  mov     [r11-48h], rax
0x14002f6a4  xor     edx, edx; CaseInSensitive
0x14002f6a6  call    cs:__imp_RtlHashUnicodeString
0x14002f6ad  nop     dword ptr [rax+rax+00h]
0x14002f6b2  mov     edi, eax
0x14002f6b4  test    eax, eax
0x14002f6b6  js      loc_14002F748
0x14002f6bc  mov     rcx, [rsi+40h]; Resource
0x14002f6c0  xorps   xmm0, xmm0
0x14002f6c3  movdqu  xmmword ptr [rsp+78h+Context.ChainHead], xmm0
0x14002f6c9  mov     edi, 0C000003Ah
0x14002f6ce  call    cs:__imp_FltAcquireResourceShared
0x14002f6d5  nop     dword ptr [rax+rax+00h]
0x14002f6da  mov     edx, dword ptr [rsp+78h+Signature]; Signature
0x14002f6e1  lea     r8, [rsp+78h+Context]; Context
0x14002f6e6  lea     rcx, [rsi+48h]; HashTable
0x14002f6ea  call    cs:__imp_RtlLookupEntryHashTable
0x14002f6f1  nop     dword ptr [rax+rax+00h]
0x14002f6f6  mov     rbx, rax
0x14002f6f9  test    rax, rax
0x14002f6fc  jz      short loc_14002F738
0x14002f6fe  lea     rdx, [rax+18h]; String2
0x14002f702  xor     r8d, r8d; CaseInSensitive
0x14002f705  mov     rcx, r14; String1
0x14002f708  call    cs:__imp_RtlEqualUnicodeString
0x14002f70f  nop     dword ptr [rax+rax+00h]
0x14002f714  test    al, al
0x14002f716  jnz     short loc_14002F72F
0x14002f718  lea     rdx, [rsp+78h+Context]; Context
0x14002f71d  lea     rcx, [rsi+48h]; HashTable
0x14002f721  call    cs:__imp_RtlGetNextEntryHashTable
0x14002f728  nop     dword ptr [rax+rax+00h]
0x14002f72d  jmp     short loc_14002F6F6
0x14002f72f  mov     rax, [rbx+28h]
0x14002f733  xor     edi, edi
0x14002f735  mov     [r15], rax
0x14002f738  mov     rcx, [rsi+40h]; Resource
0x14002f73c  call    cs:__imp_FltReleaseResource
0x14002f743  nop     dword ptr [rax+rax+00h]
0x14002f748  mov     eax, edi
0x14002f74a  add     rsp, 48h
0x14002f74e  pop     r15
0x14002f750  pop     r14
0x14002f752  pop     rdi
0x14002f753  pop     rsi
0x14002f754  pop     rbp
0x14002f755  pop     rbx
0x14002f756  retn
```
