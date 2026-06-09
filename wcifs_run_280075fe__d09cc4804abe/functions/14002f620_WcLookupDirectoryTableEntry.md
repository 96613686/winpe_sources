# WcLookupDirectoryTableEntry

- ea: `0x14002f620`
- end: `0x14002f708`
- name: `WcLookupDirectoryTableEntry`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002a614`
- `0x14003027c`

## callees

- `0x14002f620`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002f6d1`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002f6d1`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002f69a`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002f69a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002f6b8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002f6b8`
- `ntoskrnl!RtlHashUnicodeString` at `0x14002f656`
- `ntoskrnl!RtlHashUnicodeString` at `0x14002f656`
- `FLTMGR!FltAcquireResourceShared` at `0x14002f67e`
- `FLTMGR!FltAcquireResourceShared` at `0x14002f67e`
- `FLTMGR!FltReleaseResource` at `0x14002f6ec`
- `FLTMGR!FltReleaseResource` at `0x14002f6ec`

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
0x14002f620  mov     r11, rsp
0x14002f623  push    rbx
0x14002f624  push    rbp
0x14002f625  push    rsi
0x14002f626  push    rdi
0x14002f627  push    r14
0x14002f629  push    r15
0x14002f62b  sub     rsp, 48h
0x14002f62f  mov     r14, rdx
0x14002f632  lea     r9, [r11+20h]; HashValue
0x14002f636  xor     eax, eax
0x14002f638  xorps   xmm0, xmm0
0x14002f63b  mov     r15, r8
0x14002f63e  mov     [r11+20h], eax
0x14002f642  mov     rsi, rcx
0x14002f645  xor     r8d, r8d; HashAlgorithm
0x14002f648  movups  xmmword ptr [rsp+78h+Context.ChainHead], xmm0
0x14002f64d  mov     rcx, r14; String
0x14002f650  mov     [r11-48h], rax
0x14002f654  xor     edx, edx; CaseInSensitive
0x14002f656  call    cs:__imp_RtlHashUnicodeString
0x14002f65d  nop     dword ptr [rax+rax+00h]
0x14002f662  mov     edi, eax
0x14002f664  test    eax, eax
0x14002f666  js      loc_14002F6F8
0x14002f66c  mov     rcx, [rsi+40h]; Resource
0x14002f670  xorps   xmm0, xmm0
0x14002f673  movdqu  xmmword ptr [rsp+78h+Context.ChainHead], xmm0
0x14002f679  mov     edi, 0C000003Ah
0x14002f67e  call    cs:__imp_FltAcquireResourceShared
0x14002f685  nop     dword ptr [rax+rax+00h]
0x14002f68a  mov     edx, dword ptr [rsp+78h+Signature]; Signature
0x14002f691  lea     r8, [rsp+78h+Context]; Context
0x14002f696  lea     rcx, [rsi+48h]; HashTable
0x14002f69a  call    cs:__imp_RtlLookupEntryHashTable
0x14002f6a1  nop     dword ptr [rax+rax+00h]
0x14002f6a6  mov     rbx, rax
0x14002f6a9  test    rax, rax
0x14002f6ac  jz      short loc_14002F6E8
0x14002f6ae  lea     rdx, [rax+18h]; String2
0x14002f6b2  xor     r8d, r8d; CaseInSensitive
0x14002f6b5  mov     rcx, r14; String1
0x14002f6b8  call    cs:__imp_RtlEqualUnicodeString
0x14002f6bf  nop     dword ptr [rax+rax+00h]
0x14002f6c4  test    al, al
0x14002f6c6  jnz     short loc_14002F6DF
0x14002f6c8  lea     rdx, [rsp+78h+Context]; Context
0x14002f6cd  lea     rcx, [rsi+48h]; HashTable
0x14002f6d1  call    cs:__imp_RtlGetNextEntryHashTable
0x14002f6d8  nop     dword ptr [rax+rax+00h]
0x14002f6dd  jmp     short loc_14002F6A6
0x14002f6df  mov     rax, [rbx+28h]
0x14002f6e3  xor     edi, edi
0x14002f6e5  mov     [r15], rax
0x14002f6e8  mov     rcx, [rsi+40h]; Resource
0x14002f6ec  call    cs:__imp_FltReleaseResource
0x14002f6f3  nop     dword ptr [rax+rax+00h]
0x14002f6f8  mov     eax, edi
0x14002f6fa  add     rsp, 48h
0x14002f6fe  pop     r15
0x14002f700  pop     r14
0x14002f702  pop     rdi
0x14002f703  pop     rsi
0x14002f704  pop     rbp
0x14002f705  pop     rbx
0x14002f706  retn
```
