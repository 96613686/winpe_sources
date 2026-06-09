# ScDomainIdToSid

- ea: `0x140086794`
- end: `0x14008683f`
- name: `ScDomainIdToSid`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14003e068`

## callees

- `0x140086794`

## import_xrefs

- `ntdll!RtlLengthRequiredSid` at `0x1400867ca`
- `ntdll!RtlLengthRequiredSid` at `0x1400867ca`
- `ntdll!RtlCopySid` at `0x1400867f9`
- `ntdll!RtlCopySid` at `0x1400867f9`
- `ntdll!RtlFreeHeap` at `0x14008680d`
- `ntdll!RtlFreeHeap` at `0x14008680d`
- `ntdll!RtlSubAuthoritySid` at `0x140086827`
- `ntdll!RtlSubAuthoritySid` at `0x140086827`
- `ntdll!RtlSubAuthorityCountSid` at `0x1400867be`
- `ntdll!RtlSubAuthorityCountSid` at `0x14008681a`
- `ntdll!RtlSubAuthorityCountSid` at `0x1400867be`
- `ntdll!RtlSubAuthorityCountSid` at `0x14008681a`
- `ntdll!RtlAllocateHeap` at `0x1400867db`
- `ntdll!RtlAllocateHeap` at `0x1400867db`

## pseudocode

```c
__int64 __fastcall ScDomainIdToSid(__int64 a1, ULONG a2, PSID *a3)
{
  PSID v4; // rbx
  PVOID ProcessHeap; // rsi
  ULONG v7; // ebp
  ULONG v8; // r14d
  PVOID Heap; // rax
  NTSTATUS v11; // ebx
  PUCHAR v12; // rax

  v4 = BuiltinDomainSid;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v7 = *RtlSubAuthorityCountSid(BuiltinDomainSid);
  v8 = RtlLengthRequiredSid(v7 + 1);
  Heap = RtlAllocateHeap(ProcessHeap, 0, v8);
  *a3 = Heap;
  if ( !Heap )
    return 3221225495LL;
  v11 = RtlCopySid(v8, Heap, v4);
  if ( v11 >= 0 )
  {
    v12 = RtlSubAuthorityCountSid(*a3);
    ++*v12;
    *RtlSubAuthoritySid(*a3, v7) = a2;
    return 0;
  }
  else
  {
    RtlFreeHeap(ProcessHeap, 0, *a3);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x140086794  push    rbx
0x140086796  push    rbp
0x140086797  push    rsi
0x140086798  push    rdi
0x140086799  push    r14
0x14008679b  push    r15
0x14008679d  sub     rsp, 28h
0x1400867a1  mov     rax, gs:60h
0x1400867aa  mov     rdi, r8
0x1400867ad  mov     rbx, cs:BuiltinDomainSid
0x1400867b4  mov     r15d, edx
0x1400867b7  mov     rcx, rbx; Sid
0x1400867ba  mov     rsi, [rax+30h]
0x1400867be  call    cs:__imp_RtlSubAuthorityCountSid
0x1400867c4  movzx   ebp, byte ptr [rax]
0x1400867c7  lea     ecx, [rbp+1]; SubAuthorityCount
0x1400867ca  call    cs:__imp_RtlLengthRequiredSid
0x1400867d0  mov     r8d, eax; Size
0x1400867d3  xor     edx, edx; Flags
0x1400867d5  mov     rcx, rsi; HeapHandle
0x1400867d8  mov     r14d, eax
0x1400867db  call    cs:__imp_RtlAllocateHeap
0x1400867e1  mov     [rdi], rax
0x1400867e4  test    rax, rax
0x1400867e7  jnz     short loc_1400867F0
0x1400867e9  mov     eax, 0C0000017h
0x1400867ee  jmp     short loc_140086832
0x1400867f0  mov     r8, rbx; SourceSid
0x1400867f3  mov     rdx, rax; DestinationSid
0x1400867f6  mov     ecx, r14d; DestinationSidLength
0x1400867f9  call    cs:__imp_RtlCopySid
0x1400867ff  mov     ebx, eax
0x140086801  test    eax, eax
0x140086803  jns     short loc_140086817
0x140086805  mov     r8, [rdi]; P
0x140086808  xor     edx, edx; Flags
0x14008680a  mov     rcx, rsi; HeapHandle
0x14008680d  call    cs:__imp_RtlFreeHeap
0x140086813  mov     eax, ebx
0x140086815  jmp     short loc_140086832
0x140086817  mov     rcx, [rdi]; Sid
0x14008681a  call    cs:__imp_RtlSubAuthorityCountSid
0x140086820  mov     edx, ebp; SubAuthority
0x140086822  inc     byte ptr [rax]
0x140086824  mov     rcx, [rdi]; Sid
0x140086827  call    cs:__imp_RtlSubAuthoritySid
0x14008682d  mov     [rax], r15d
0x140086830  xor     eax, eax
0x140086832  add     rsp, 28h
0x140086836  pop     r15
0x140086838  pop     r14
0x14008683a  pop     rdi
0x14008683b  pop     rsi
0x14008683c  pop     rbp
0x14008683d  pop     rbx
0x14008683e  retn
```
