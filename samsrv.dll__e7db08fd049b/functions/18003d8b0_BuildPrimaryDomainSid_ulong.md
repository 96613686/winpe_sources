# BuildPrimaryDomainSid(ulong)

- ea: `0x18003d8b0`
- end: `0x18003d930`
- name: `?BuildPrimaryDomainSid@@YAPEAXK@Z`
- size: `128`
- prototype: `void *__fastcall(ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003dd78`

## callees

- `0x18003d8b0`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18003d903`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d90e`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d903`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d90e`
- `ntdll!RtlSubAuthoritySid` at `0x18003d91c`
- `ntdll!RtlSubAuthoritySid` at `0x18003d91c`
- `ntdll!RtlAllocateHeap` at `0x18003d8e4`
- `ntdll!RtlAllocateHeap` at `0x18003d8e4`
- `ntdll!RtlCopySid` at `0x18003d8fa`
- `ntdll!RtlCopySid` at `0x18003d8fa`
- `ntdll!RtlLengthSid` at `0x18003d8c9`
- `ntdll!RtlLengthSid` at `0x18003d8c9`

## pseudocode

```c
void *__fastcall BuildPrimaryDomainSid(ULONG a1)
{
  void *v2; // rdi
  ULONG v3; // esi
  PVOID Heap; // rax
  void *v5; // rbx
  PUCHAR v6; // rax
  PUCHAR v7; // rax

  v2 = *(void **)(qword_1800F0960 + 16);
  v3 = RtlLengthSid(v2) + 4;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  v5 = Heap;
  if ( Heap )
  {
    RtlCopySid(v3, Heap, v2);
    v6 = RtlSubAuthorityCountSid(v5);
    ++*v6;
    v7 = RtlSubAuthorityCountSid(v5);
    *RtlSubAuthoritySid(v5, (unsigned int)*v7 - 1) = a1;
  }
  return v5;
}

```

## disassembly

```asm
0x18003d8b0  push    rbx
0x18003d8b2  push    rbp
0x18003d8b3  push    rsi
0x18003d8b4  push    rdi
0x18003d8b5  sub     rsp, 28h
0x18003d8b9  mov     rax, cs:qword_1800F0960
0x18003d8c0  mov     ebp, ecx
0x18003d8c2  mov     rdi, [rax+10h]
0x18003d8c6  mov     rcx, rdi; Sid
0x18003d8c9  call    cs:__imp_RtlLengthSid
0x18003d8cf  mov     rcx, gs:60h
0x18003d8d8  xor     edx, edx; Flags
0x18003d8da  lea     esi, [rax+4]
0x18003d8dd  mov     rcx, [rcx+30h]; HeapHandle
0x18003d8e1  mov     r8d, esi; Size
0x18003d8e4  call    cs:__imp_RtlAllocateHeap
0x18003d8ea  mov     rbx, rax
0x18003d8ed  test    rax, rax
0x18003d8f0  jz      short loc_18003D924
0x18003d8f2  mov     r8, rdi; SourceSid
0x18003d8f5  mov     rdx, rax; DestinationSid
0x18003d8f8  mov     ecx, esi; DestinationSidLength
0x18003d8fa  call    cs:__imp_RtlCopySid
0x18003d900  mov     rcx, rbx; Sid
0x18003d903  call    cs:__imp_RtlSubAuthorityCountSid
0x18003d909  mov     rcx, rbx; Sid
0x18003d90c  inc     byte ptr [rax]
0x18003d90e  call    cs:__imp_RtlSubAuthorityCountSid
0x18003d914  mov     rcx, rbx; Sid
0x18003d917  movzx   edx, byte ptr [rax]
0x18003d91a  dec     edx; SubAuthority
0x18003d91c  call    cs:__imp_RtlSubAuthoritySid
0x18003d922  mov     [rax], ebp
0x18003d924  mov     rax, rbx
0x18003d927  add     rsp, 28h
0x18003d92b  pop     rdi
0x18003d92c  pop     rsi
0x18003d92d  pop     rbp
0x18003d92e  pop     rbx
0x18003d92f  retn
```
