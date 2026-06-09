# UmpoInternalCacheDefaultSecurityDescriptor

- ea: `0x180012748`
- end: `0x1800127c6`
- name: `UmpoInternalCacheDefaultSecurityDescriptor`
- size: `126`
- prototype: `void __fastcall(STRSAFE_LPCWSTR pszSrc, size_t cbDest)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003a00`
- `0x180014440`

## callees

- `0x1800010f0`
- `0x180012748`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001278e`
- `ntdll!RtlAllocateHeap` at `0x18001278e`
- `ntdll!RtlFreeHeap` at `0x180012779`
- `ntdll!RtlFreeHeap` at `0x180012779`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800127bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001275e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001275e`

## pseudocode

```c
void __fastcall UmpoInternalCacheDefaultSecurityDescriptor(STRSAFE_LPCWSTR pszSrc, size_t cbDest)
{
  SIZE_T v3; // rbx
  wchar_t *Heap; // rax

  v3 = (unsigned int)cbDest;
  AcquireSRWLockExclusive(&UmpoDefaultSecurityDescriptorLock);
  if ( UmpoDefaultSecurityDescriptor )
    RtlFreeHeap(UmpoHeapHandle, 0, (PVOID)UmpoDefaultSecurityDescriptor);
  Heap = (wchar_t *)RtlAllocateHeap(UmpoHeapHandle, 8u, v3);
  UmpoDefaultSecurityDescriptor = Heap;
  if ( Heap )
    StringCbCopyW(Heap, v3, pszSrc);
  ReleaseSRWLockExclusive(&UmpoDefaultSecurityDescriptorLock);
}

```

## disassembly

```asm
0x180012748  mov     [rsp+arg_0], rbx
0x18001274d  push    rdi
0x18001274e  sub     rsp, 20h
0x180012752  mov     rdi, rcx
0x180012755  mov     ebx, edx
0x180012757  lea     rcx, UmpoDefaultSecurityDescriptorLock; SRWLock
0x18001275e  call    cs:__imp_AcquireSRWLockExclusive
0x180012764  mov     r8, cs:UmpoDefaultSecurityDescriptor; P
0x18001276b  test    r8, r8
0x18001276e  jz      short loc_18001277F
0x180012770  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180012777  xor     edx, edx; Flags
0x180012779  call    cs:__imp_RtlFreeHeap
0x18001277f  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180012786  mov     r8, rbx; Size
0x180012789  mov     edx, 8; Flags
0x18001278e  call    cs:__imp_RtlAllocateHeap
0x180012794  mov     cs:UmpoDefaultSecurityDescriptor, rax
0x18001279b  test    rax, rax
0x18001279e  jz      short loc_1800127AE
0x1800127a0  mov     r8, rdi; pszSrc
0x1800127a3  mov     rdx, rbx; cbDest
0x1800127a6  mov     rcx, rax; pszDest
0x1800127a9  call    StringCbCopyW
0x1800127ae  lea     rcx, UmpoDefaultSecurityDescriptorLock
0x1800127b5  mov     rbx, [rsp+28h+arg_0]
0x1800127ba  add     rsp, 20h
0x1800127be  pop     rdi
0x1800127bf  jmp     cs:__imp_ReleaseSRWLockExclusive
```
