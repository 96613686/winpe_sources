# SmpSaveRegistryValue_U

- ea: `0x140007e50`
- end: `0x1400080b7`
- name: `SmpSaveRegistryValue_U`
- size: `615`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140007cb0`
- `0x1400182cc`

## callees

- `0x140007e50`
- `0x14000d494`
- `0x14001cc11`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000806e`
- `ntdll!RtlInitUnicodeString` at `0x14000806e`
- `ntdll!RtlAllocateHeap` at `0x140007f45`
- `ntdll!RtlAllocateHeap` at `0x140007fb4`
- `ntdll!RtlAllocateHeap` at `0x140008010`
- `ntdll!RtlAllocateHeap` at `0x140007f45`
- `ntdll!RtlAllocateHeap` at `0x140007fb4`
- `ntdll!RtlAllocateHeap` at `0x140008010`
- `ntdll!RtlFreeHeap` at `0x140007eff`
- `ntdll!RtlFreeHeap` at `0x140007f21`
- `ntdll!RtlFreeHeap` at `0x140007eff`
- `ntdll!RtlFreeHeap` at `0x140007f21`
- `ntdll!RtlCompareUnicodeString` at `0x140007e93`
- `ntdll!RtlCompareUnicodeString` at `0x140007ebf`
- `ntdll!RtlCompareUnicodeString` at `0x140007e93`
- `ntdll!RtlCompareUnicodeString` at `0x140007ebf`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x140008044`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x140008044`

## pseudocode

```c
__int64 __fastcall SmpSaveRegistryValue_U(
        struct _UNICODE_STRING **a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        char a4,
        struct _UNICODE_STRING **a5)
{
  struct _UNICODE_STRING *i; // rbx
  PWSTR Buffer; // r8
  int v12; // ebp
  void *v13; // r8
  struct _UNICODE_STRING *Heap; // rax
  WCHAR *v15; // rax
  CHAR *v16; // rax
  USHORT v17; // ax
  struct _UNICODE_STRING *v18; // rax
  struct _STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF

  DestinationString = 0;
  if ( (a4 & 1) != 0 )
  {
    for ( i = *a1; ; i = *(struct _UNICODE_STRING **)&i->Length )
    {
      if ( i == (struct _UNICODE_STRING *)a1 )
        goto LABEL_15;
      if ( !RtlCompareUnicodeString(i + 1, a2, 1u) )
        break;
    }
    if ( i[2].Buffer )
    {
      if ( !a3 )
      {
LABEL_12:
        Buffer = i[2].Buffer;
        v12 = 0;
        if ( Buffer )
        {
          RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Buffer);
          v13 = *(void **)&i[3].Length;
          if ( v13 )
            RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v13);
        }
        goto LABEL_17;
      }
    }
    else if ( !a3 )
    {
      return 0x40000000;
    }
    if ( !RtlCompareUnicodeString(i + 2, a3, 1u) )
      return 0x40000000;
    goto LABEL_12;
  }
LABEL_15:
  Heap = (struct _UNICODE_STRING *)RtlAllocateHeap(
                                     *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                                     SmBaseTag,
                                     a2->MaximumLength + 56LL);
  i = Heap;
  if ( !Heap )
    return 3221225495LL;
  Heap->Buffer = &Heap->Length;
  *(_QWORD *)&Heap->Length = Heap;
  Heap[1].Buffer = (PWSTR)&Heap[3].Buffer;
  v12 = 1;
  Heap[1].Length = a2->Length;
  Heap[1].MaximumLength = a2->MaximumLength;
  *(_QWORD *)&Heap[3].Length = 0;
  memcpy_0(&Heap[3].Buffer, a2->Buffer, a2->MaximumLength);
  i[2].Buffer = 0;
LABEL_17:
  if ( !a3 )
  {
    RtlInitUnicodeString(i + 2, 0);
    goto LABEL_25;
  }
  v15 = (WCHAR *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag, a3->MaximumLength);
  i[2].Buffer = v15;
  if ( !v15 )
  {
LABEL_22:
    SmpFreeSavedRegistryEntry(i);
    return 3221225495LL;
  }
  i[2].Length = a3->Length;
  i[2].MaximumLength = a3->MaximumLength;
  memcpy_0(v15, a3->Buffer, a3->MaximumLength);
  if ( (a4 & 2) != 0 )
  {
    v16 = (CHAR *)RtlAllocateHeap(
                    *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                    SmBaseTag,
                    ((unsigned __int64)a3->Length >> 1) + 1);
    *(_QWORD *)&i[3].Length = v16;
    if ( v16 )
    {
      DestinationString.Buffer = v16;
      v17 = (a3->Length >> 1) + 1;
      DestinationString.Length = 0;
      DestinationString.MaximumLength = v17;
      RtlUnicodeStringToAnsiString(&DestinationString, a3, 0);
      goto LABEL_25;
    }
    goto LABEL_22;
  }
LABEL_25:
  if ( v12 )
  {
    v18 = a1[1];
    if ( *(struct _UNICODE_STRING ***)&v18->Length != a1 )
      __fastfail(3u);
    *(_QWORD *)&i->Length = a1;
    i->Buffer = &v18->Length;
    *(_QWORD *)&v18->Length = i;
    a1[1] = i;
  }
  if ( a5 )
    *a5 = i;
  return 0;
}

```

## disassembly

```asm
0x140007e50  push    rbx
0x140007e52  push    rbp
0x140007e53  push    rsi
0x140007e54  push    rdi
0x140007e55  push    r12
0x140007e57  push    r14
0x140007e59  push    r15
0x140007e5b  sub     rsp, 30h
0x140007e5f  xorps   xmm0, xmm0
0x140007e62  mov     r12d, r9d
0x140007e65  mov     r14, r8
0x140007e68  mov     rsi, rdx
0x140007e6b  mov     rdi, rcx
0x140007e6e  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140007e73  test    r9b, 1
0x140007e77  jz      loc_140007F29
0x140007e7d  mov     rbx, [rcx]
0x140007e80  cmp     rbx, rdi
0x140007e83  jz      loc_140007F29
0x140007e89  lea     rcx, [rbx+10h]; String1
0x140007e8d  mov     r8b, 1; CaseInSensitive
0x140007e90  mov     rdx, rsi; String2
0x140007e93  call    cs:__imp_RtlCompareUnicodeString
0x140007e99  test    eax, eax
0x140007e9b  jz      short loc_140007EA2
0x140007e9d  mov     rbx, [rbx]
0x140007ea0  jmp     short loc_140007E80
0x140007ea2  cmp     qword ptr [rbx+28h], 0
0x140007ea7  jnz     short loc_140007EB0
0x140007ea9  test    r14, r14
0x140007eac  jnz     short loc_140007EB5
0x140007eae  jmp     short loc_140007EC9
0x140007eb0  test    r14, r14
0x140007eb3  jz      short loc_140007EDD
0x140007eb5  lea     rcx, [rbx+20h]; String1
0x140007eb9  mov     r8b, 1; CaseInSensitive
0x140007ebc  mov     rdx, r14; String2
0x140007ebf  call    cs:__imp_RtlCompareUnicodeString
0x140007ec5  test    eax, eax
0x140007ec7  jnz     short loc_140007EDD
0x140007ec9  mov     eax, 40000000h
0x140007ece  add     rsp, 30h
0x140007ed2  pop     r15
0x140007ed4  pop     r14
0x140007ed6  pop     r12
0x140007ed8  pop     rdi
0x140007ed9  pop     rsi
0x140007eda  pop     rbp
0x140007edb  pop     rbx
0x140007edc  retn
0x140007edd  mov     r8, [rbx+28h]; BaseAddress
0x140007ee1  xor     r15d, r15d
0x140007ee4  mov     ebp, r15d
0x140007ee7  test    r8, r8
0x140007eea  jz      loc_140007F93
0x140007ef0  mov     rcx, gs:60h
0x140007ef9  xor     edx, edx; Flags
0x140007efb  mov     rcx, [rcx+30h]; HeapHandle
0x140007eff  call    cs:__imp_RtlFreeHeap
0x140007f05  mov     r8, [rbx+30h]; BaseAddress
0x140007f09  test    r8, r8
0x140007f0c  jz      loc_140007F93
0x140007f12  mov     rcx, gs:60h
0x140007f1b  xor     edx, edx; Flags
0x140007f1d  mov     rcx, [rcx+30h]; HeapHandle
0x140007f21  call    cs:__imp_RtlFreeHeap
0x140007f27  jmp     short loc_140007F93
0x140007f29  mov     rcx, gs:60h
0x140007f32  movzx   r8d, word ptr [rsi+2]
0x140007f37  mov     edx, cs:SmBaseTag; Flags
0x140007f3d  add     r8, 38h ; '8'; Size
0x140007f41  mov     rcx, [rcx+30h]; HeapHandle
0x140007f45  call    cs:__imp_RtlAllocateHeap
0x140007f4b  mov     rbx, rax
0x140007f4e  test    rax, rax
0x140007f51  jz      loc_140008054
0x140007f57  mov     [rax+8], rax
0x140007f5b  lea     rcx, [rax+38h]; void *
0x140007f5f  mov     [rax], rax
0x140007f62  xor     r15d, r15d
0x140007f65  mov     [rax+18h], rcx
0x140007f69  mov     ebp, 1
0x140007f6e  movzx   eax, word ptr [rsi]
0x140007f71  mov     [rbx+10h], ax
0x140007f75  movzx   eax, word ptr [rsi+2]
0x140007f79  mov     [rbx+12h], ax
0x140007f7d  mov     [rbx+30h], r15
0x140007f81  movzx   r8d, word ptr [rsi+2]; MaxCount
0x140007f86  mov     rdx, [rsi+8]; Src
0x140007f8a  call    memcpy_0
0x140007f8f  mov     [rbx+28h], r15
0x140007f93  test    r14, r14
0x140007f96  jz      loc_140008068
0x140007f9c  mov     rcx, gs:60h
0x140007fa5  mov     edx, cs:SmBaseTag; Flags
0x140007fab  movzx   r8d, word ptr [r14+2]; Size
0x140007fb0  mov     rcx, [rcx+30h]; HeapHandle
0x140007fb4  call    cs:__imp_RtlAllocateHeap
0x140007fba  mov     [rbx+28h], rax
0x140007fbe  test    rax, rax
0x140007fc1  jz      loc_14000804C
0x140007fc7  movzx   ecx, word ptr [r14]
0x140007fcb  mov     [rbx+20h], cx
0x140007fcf  movzx   ecx, word ptr [r14+2]
0x140007fd4  mov     [rbx+22h], cx
0x140007fd8  mov     rcx, rax; void *
0x140007fdb  movzx   r8d, word ptr [r14+2]; MaxCount
0x140007fe0  mov     rdx, [r14+8]; Src
0x140007fe4  call    memcpy_0
0x140007fe9  test    r12b, 2
0x140007fed  jz      loc_140008074
0x140007ff3  mov     rcx, gs:60h
0x140007ffc  movzx   r8d, word ptr [r14]
0x140008000  mov     edx, cs:SmBaseTag; Flags
0x140008006  shr     r8, 1
0x140008009  mov     rcx, [rcx+30h]; HeapHandle
0x14000800d  inc     r8; Size
0x140008010  call    cs:__imp_RtlAllocateHeap
0x140008016  mov     [rbx+30h], rax
0x14000801a  test    rax, rax
0x14000801d  jz      short loc_14000804C
0x14000801f  mov     [rsp+68h+DestinationString.Buffer], rax
0x140008024  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140008029  movzx   eax, word ptr [r14]
0x14000802d  xor     r8d, r8d; AllocateDestinationString
0x140008030  shr     ax, 1
0x140008033  mov     rdx, r14; SourceString
0x140008036  inc     ax
0x140008039  mov     [rsp+68h+DestinationString.Length], r15w
0x14000803f  mov     [rsp+68h+DestinationString.MaximumLength], ax
0x140008044  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14000804a  jmp     short loc_140008074
0x14000804c  mov     rcx, rbx
0x14000804f  call    SmpFreeSavedRegistryEntry
0x140008054  mov     eax, 0C0000017h
0x140008059  add     rsp, 30h
0x14000805d  pop     r15
0x14000805f  pop     r14
0x140008061  pop     r12
0x140008063  pop     rdi
0x140008064  pop     rsi
0x140008065  pop     rbp
0x140008066  pop     rbx
0x140008067  retn
0x140008068  lea     rcx, [rbx+20h]; DestinationString
0x14000806c  xor     edx, edx; SourceString
0x14000806e  call    cs:__imp_RtlInitUnicodeString
0x140008074  test    ebp, ebp
0x140008076  jz      short loc_140008096
0x140008078  mov     rax, [rdi+8]
0x14000807c  cmp     [rax], rdi
0x14000807f  jz      short loc_140008088
0x140008081  mov     ecx, 3
0x140008086  int     29h; Win8: RtlFailFast(ecx)
0x140008088  mov     [rbx], rdi
0x14000808b  mov     [rbx+8], rax
0x14000808f  mov     [rax], rbx
0x140008092  mov     [rdi+8], rbx
0x140008096  mov     rax, [rsp+68h+arg_20]
0x14000809e  test    rax, rax
0x1400080a1  jz      short loc_1400080A6
0x1400080a3  mov     [rax], rbx
0x1400080a6  xor     eax, eax
0x1400080a8  add     rsp, 30h
0x1400080ac  pop     r15
0x1400080ae  pop     r14
0x1400080b0  pop     r12
0x1400080b2  pop     rdi
0x1400080b3  pop     rsi
0x1400080b4  pop     rbp
0x1400080b5  pop     rbx
0x1400080b6  retn
```
