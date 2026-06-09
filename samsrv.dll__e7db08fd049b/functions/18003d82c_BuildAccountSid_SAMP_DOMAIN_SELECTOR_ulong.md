# BuildAccountSid(_SAMP_DOMAIN_SELECTOR,ulong)

- ea: `0x18003d82c`
- end: `0x18003d8a8`
- name: `?BuildAccountSid@@YAPEAXW4_SAMP_DOMAIN_SELECTOR@@K@Z`
- size: `124`
- prototype: `void *__fastcall(__int64, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003dd78`

## callees

- `0x18003d82c`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18003d87b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d886`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d87b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d886`
- `ntdll!RtlSubAuthoritySid` at `0x18003d894`
- `ntdll!RtlSubAuthoritySid` at `0x18003d894`
- `ntdll!RtlAllocateHeap` at `0x18003d85c`
- `ntdll!RtlAllocateHeap` at `0x18003d85c`
- `ntdll!RtlCopySid` at `0x18003d872`
- `ntdll!RtlCopySid` at `0x18003d872`
- `ntdll!RtlLengthSid` at `0x18003d841`
- `ntdll!RtlLengthSid` at `0x18003d841`

## pseudocode

```c
void *__fastcall BuildAccountSid(__int64 a1, ULONG a2)
{
  PSID v2; // rdi
  ULONG v4; // esi
  PVOID Heap; // rax
  void *v6; // rbx
  PUCHAR v7; // rax
  PUCHAR v8; // rax

  v2 = SampAccountDomainSid;
  v4 = RtlLengthSid(SampAccountDomainSid) + 4;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  v6 = Heap;
  if ( Heap )
  {
    RtlCopySid(v4, Heap, v2);
    v7 = RtlSubAuthorityCountSid(v6);
    ++*v7;
    v8 = RtlSubAuthorityCountSid(v6);
    *RtlSubAuthoritySid(v6, (unsigned int)*v8 - 1) = a2;
  }
  return v6;
}

```

## disassembly

```asm
0x18003d82c  push    rbx
0x18003d82e  push    rbp
0x18003d82f  push    rsi
0x18003d830  push    rdi
0x18003d831  sub     rsp, 28h
0x18003d835  mov     rdi, cs:SampAccountDomainSid
0x18003d83c  mov     ebp, edx
0x18003d83e  mov     rcx, rdi; Sid
0x18003d841  call    cs:__imp_RtlLengthSid
0x18003d847  mov     rcx, gs:60h
0x18003d850  xor     edx, edx; Flags
0x18003d852  lea     esi, [rax+4]
0x18003d855  mov     rcx, [rcx+30h]; HeapHandle
0x18003d859  mov     r8d, esi; Size
0x18003d85c  call    cs:__imp_RtlAllocateHeap
0x18003d862  mov     rbx, rax
0x18003d865  test    rax, rax
0x18003d868  jz      short loc_18003D89C
0x18003d86a  mov     r8, rdi; SourceSid
0x18003d86d  mov     rdx, rax; DestinationSid
0x18003d870  mov     ecx, esi; DestinationSidLength
0x18003d872  call    cs:__imp_RtlCopySid
0x18003d878  mov     rcx, rbx; Sid
0x18003d87b  call    cs:__imp_RtlSubAuthorityCountSid
0x18003d881  mov     rcx, rbx; Sid
0x18003d884  inc     byte ptr [rax]
0x18003d886  call    cs:__imp_RtlSubAuthorityCountSid
0x18003d88c  mov     rcx, rbx; Sid
0x18003d88f  movzx   edx, byte ptr [rax]
0x18003d892  dec     edx; SubAuthority
0x18003d894  call    cs:__imp_RtlSubAuthoritySid
0x18003d89a  mov     [rax], ebp
0x18003d89c  mov     rax, rbx
0x18003d89f  add     rsp, 28h
0x18003d8a3  pop     rdi
0x18003d8a4  pop     rsi
0x18003d8a5  pop     rbp
0x18003d8a6  pop     rbx
0x18003d8a7  retn
```
