# SmpCreateEmergencyPagingFile

- ea: `0x14000f5b0`
- end: `0x14000f6ed`
- name: `SmpCreateEmergencyPagingFile`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000fcf8`

## callees

- `0x14000b464`
- `0x14000f5b0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000f636`
- `ntdll!RtlInitUnicodeString` at `0x14000f636`
- `ntdll!RtlAllocateHeap` at `0x14000f5d5`
- `ntdll!RtlAllocateHeap` at `0x14000f607`
- `ntdll!RtlAllocateHeap` at `0x14000f5d5`
- `ntdll!RtlAllocateHeap` at `0x14000f607`
- `ntdll!RtlFreeHeap` at `0x14000f628`
- `ntdll!RtlFreeHeap` at `0x14000f6a4`
- `ntdll!RtlFreeHeap` at `0x14000f628`
- `ntdll!RtlFreeHeap` at `0x14000f6a4`
- `ntdll!RtlFreeUnicodeString` at `0x14000f68c`
- `ntdll!RtlFreeUnicodeString` at `0x14000f68c`
- `ntdll!RtlAppendUnicodeToString` at `0x14000f647`
- `ntdll!RtlAppendUnicodeToString` at `0x14000f647`

## pseudocode

```c
__int64 SmpCreateEmergencyPagingFile()
{
  struct _UNICODE_STRING *Heap; // rax
  struct _UNICODE_STRING *v1; // rbx
  WCHAR *v3; // rax
  struct _UNICODE_STRING *v4; // rdi
  __int64 v5; // rax

  Heap = (struct _UNICODE_STRING *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 8u, 0x60u);
  v1 = Heap;
  if ( !Heap )
    return 3221225495LL;
  Heap[1].MaximumLength = 40;
  v3 = (WCHAR *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, 0x28u);
  v1[1].Buffer = v3;
  if ( !v3 )
  {
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v1);
    return 3221225495LL;
  }
  RtlInitUnicodeString(v1 + 2, 0);
  RtlAppendUnicodeToString(v1 + 1, L"\\??\\?:\\pagefile.sys");
  v1[1].Buffer[4] = 63;
  HIDWORD(v1[5].Buffer) |= 6u;
  while ( 1 )
  {
    v4 = (struct _UNICODE_STRING *)SmpPagingFileDescriptorList;
    if ( SmpPagingFileDescriptorList == &SmpPagingFileDescriptorList )
      break;
    if ( *((PVOID **)SmpPagingFileDescriptorList + 1) != &SmpPagingFileDescriptorList )
      goto LABEL_11;
    v5 = *(_QWORD *)SmpPagingFileDescriptorList;
    if ( *(PVOID *)(*(_QWORD *)SmpPagingFileDescriptorList + 8LL) != SmpPagingFileDescriptorList )
      goto LABEL_11;
    SmpPagingFileDescriptorList = *(PVOID *)SmpPagingFileDescriptorList;
    *(_QWORD *)(v5 + 8) = &SmpPagingFileDescriptorList;
    RtlFreeUnicodeString(v4 + 1);
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v4);
  }
  SmpNumberOfPagefileDescriptors = 1;
  if ( *((PVOID **)SmpPagingFileDescriptorList + 1) != &SmpPagingFileDescriptorList )
LABEL_11:
    __fastfail(3u);
  *(_QWORD *)&v1->Length = SmpPagingFileDescriptorList;
  v1->Buffer = (PWSTR)&SmpPagingFileDescriptorList;
  v4->Buffer = &v1->Length;
  SmpPagingFileDescriptorList = v1;
  return SmpProcessPagefileDescriptor((__int64)v1);
}

```

## disassembly

```asm
0x14000f5b0  mov     [rsp+arg_0], rbx
0x14000f5b5  mov     [rsp+arg_8], rsi
0x14000f5ba  push    rdi
0x14000f5bb  sub     rsp, 20h
0x14000f5bf  mov     rcx, gs:60h
0x14000f5c8  mov     edx, 8; Flags
0x14000f5cd  mov     rcx, [rcx+30h]; HeapHandle
0x14000f5d1  lea     r8d, [rdx+58h]; Size
0x14000f5d5  call    cs:__imp_RtlAllocateHeap
0x14000f5db  mov     rbx, rax
0x14000f5de  test    rax, rax
0x14000f5e1  jnz     short loc_14000F5ED
0x14000f5e3  mov     eax, 0C0000017h
0x14000f5e8  jmp     loc_14000F6DD
0x14000f5ed  mov     r8d, 28h ; '('; Size
0x14000f5f3  xor     edx, edx; Flags
0x14000f5f5  mov     [rax+12h], r8w
0x14000f5fa  mov     rcx, gs:60h
0x14000f603  mov     rcx, [rcx+30h]; HeapHandle
0x14000f607  call    cs:__imp_RtlAllocateHeap
0x14000f60d  mov     [rbx+18h], rax
0x14000f611  test    rax, rax
0x14000f614  jnz     short loc_14000F630
0x14000f616  mov     rcx, gs:60h
0x14000f61f  mov     r8, rbx; BaseAddress
0x14000f622  xor     edx, edx; Flags
0x14000f624  mov     rcx, [rcx+30h]; HeapHandle
0x14000f628  call    cs:__imp_RtlFreeHeap
0x14000f62e  jmp     short loc_14000F5E3
0x14000f630  lea     rcx, [rbx+20h]; DestinationString
0x14000f634  xor     edx, edx; SourceString
0x14000f636  call    cs:__imp_RtlInitUnicodeString
0x14000f63c  lea     rcx, [rbx+10h]; Destination
0x14000f640  lea     rdx, aPagefileSys; "\\??\\?:\\pagefile.sys"
0x14000f647  call    cs:__imp_RtlAppendUnicodeToString
0x14000f64d  mov     rax, [rbx+18h]
0x14000f651  lea     rsi, SmpPagingFileDescriptorList
0x14000f658  mov     word ptr [rax+8], 3Fh ; '?'
0x14000f65e  or      dword ptr [rbx+5Ch], 6
0x14000f662  mov     rdi, cs:SmpPagingFileDescriptorList
0x14000f669  cmp     rdi, rsi
0x14000f66c  jz      short loc_14000F6AC
0x14000f66e  cmp     [rdi+8], rsi
0x14000f672  jnz     short loc_14000F6BC
0x14000f674  mov     rax, [rdi]
0x14000f677  cmp     [rax+8], rdi
0x14000f67b  jnz     short loc_14000F6BC
0x14000f67d  mov     cs:SmpPagingFileDescriptorList, rax
0x14000f684  lea     rcx, [rdi+10h]; UnicodeString
0x14000f688  mov     [rax+8], rsi
0x14000f68c  call    cs:__imp_RtlFreeUnicodeString
0x14000f692  mov     rcx, gs:60h
0x14000f69b  mov     r8, rdi; BaseAddress
0x14000f69e  xor     edx, edx; Flags
0x14000f6a0  mov     rcx, [rcx+30h]; HeapHandle
0x14000f6a4  call    cs:__imp_RtlFreeHeap
0x14000f6aa  jmp     short loc_14000F662
0x14000f6ac  mov     cs:SmpNumberOfPagefileDescriptors, 1
0x14000f6b6  cmp     [rdi+8], rsi
0x14000f6ba  jz      short loc_14000F6C3
0x14000f6bc  mov     ecx, 3
0x14000f6c1  int     29h; Win8: RtlFailFast(ecx)
0x14000f6c3  mov     [rbx], rdi
0x14000f6c6  mov     rcx, rbx
0x14000f6c9  mov     [rbx+8], rsi
0x14000f6cd  mov     [rdi+8], rbx
0x14000f6d1  mov     cs:SmpPagingFileDescriptorList, rbx
0x14000f6d8  call    SmpProcessPagefileDescriptor
0x14000f6dd  mov     rbx, [rsp+28h+arg_0]
0x14000f6e2  mov     rsi, [rsp+28h+arg_8]
0x14000f6e7  add     rsp, 20h
0x14000f6eb  pop     rdi
0x14000f6ec  retn
```
