# TdiCopyBufferToMdlWithReservedMappingAtDpcLevel

- ea: `0x140004ac0`
- end: `0x140004c0b`
- name: `TdiCopyBufferToMdlWithReservedMappingAtDpcLevel`
- size: `331`
- prototype: `void __stdcall(PVOID SourceBuffer, PMDL DestinationMdl, ULONG DestinationOffset, ULONG BytesToCopy)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140004ac0`
- `0x1400054b0`
- `0x140005600`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140004b5b`
- `ntoskrnl!IoBuildPartialMdl` at `0x140004b5b`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140004b7d`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140004b7d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004b0c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004b0c`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140004ba7`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140004ba7`
- `ntoskrnl!MmUnmapLockedPages` at `0x140004bc1`
- `ntoskrnl!MmUnmapLockedPages` at `0x140004bc1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004be3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004be3`

## pseudocode

```c
void __stdcall TdiCopyBufferToMdlWithReservedMappingAtDpcLevel(
        PVOID SourceBuffer,
        PMDL DestinationMdl,
        ULONG DestinationOffset,
        ULONG BytesToCopy)
{
  ULONG v8; // ebx
  __int64 ByteOffset; // r8
  ULONG v10; // r14d
  __int64 v11; // r15
  PVOID v12; // rax
  _MDL TargetMdl; // [rsp+20h] [rbp-50h] BYREF

  *(_DWORD *)&TargetMdl.Size = 56;
  *(_QWORD *)&TargetMdl.ByteCount = 4096;
  TargetMdl.Next = 0;
  TargetMdl.StartVa = 0;
  KeAcquireSpinLockAtDpcLevel(&TdiMappingAddressLock);
  v8 = DestinationOffset + BytesToCopy;
  if ( DestinationOffset < v8 )
  {
    do
    {
      ByteOffset = DestinationMdl->ByteOffset;
      v10 = v8;
      if ( ((DestinationOffset + (_DWORD)ByteOffset + 4096) & 0xFFFFF000) - (unsigned int)ByteOffset <= v8 )
        v10 = ((DestinationOffset + ByteOffset + 4096) & 0xFFFFF000) - ByteOffset;
      v11 = v10 - DestinationOffset;
      IoBuildPartialMdl(
        DestinationMdl,
        &TargetMdl,
        (char *)DestinationMdl->StartVa + DestinationOffset + ByteOffset,
        v10 - DestinationOffset);
      v12 = MmMapLockedPagesWithReservedMapping(TdiMappingAddress, 0x6D494454u, &TargetMdl, MmCached);
      memmove(v12, SourceBuffer, (unsigned int)v11);
      MmUnmapReservedMapping(TdiMappingAddress, 0x6D494454u, &TargetMdl);
      if ( (TargetMdl.MdlFlags & 0x20) != 0 )
        MmUnmapLockedPages(TargetMdl.MappedSystemVa, &TargetMdl);
      SourceBuffer = (char *)SourceBuffer + v11;
      DestinationOffset = v10;
    }
    while ( v10 < v8 );
  }
  KeReleaseSpinLockFromDpcLevel(&TdiMappingAddressLock);
}

```

## disassembly

```asm
0x140004ac0  push    rbp
0x140004ac2  push    rbx
0x140004ac3  push    rsi
0x140004ac4  push    rdi
0x140004ac5  push    r12
0x140004ac7  push    r14
0x140004ac9  push    r15
0x140004acb  mov     rbp, rsp
0x140004ace  sub     rsp, 70h
0x140004ad2  mov     rax, cs:__security_cookie
0x140004ad9  xor     rax, rsp
0x140004adc  mov     [rbp+var_10], rax
0x140004ae0  mov     rsi, rcx
0x140004ae3  mov     dword ptr [rbp+TargetMdl.Size], 38h ; '8'
0x140004aea  xor     ecx, ecx
0x140004aec  mov     qword ptr [rbp+TargetMdl.ByteCount], 1000h
0x140004af4  mov     [rbp+TargetMdl.Next], rcx
0x140004af8  mov     ebx, r9d
0x140004afb  mov     [rbp+TargetMdl.StartVa], rcx
0x140004aff  mov     edi, r8d
0x140004b02  lea     rcx, TdiMappingAddressLock; SpinLock
0x140004b09  mov     r12, rdx
0x140004b0c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140004b13  nop     dword ptr [rax+rax+00h]
0x140004b18  add     ebx, edi
0x140004b1a  cmp     edi, ebx
0x140004b1c  jnb     loc_140004BDC
0x140004b22  mov     r8d, [r12+2Ch]
0x140004b27  lea     rdx, [rbp+TargetMdl]; TargetMdl
0x140004b2b  mov     r14d, ebx
0x140004b2e  mov     rcx, r12; SourceMdl
0x140004b31  lea     eax, [r8+1000h]
0x140004b38  add     eax, edi
0x140004b3a  and     eax, 0FFFFF000h
0x140004b3f  sub     eax, r8d
0x140004b42  cmp     eax, ebx
0x140004b44  cmovbe  r14d, eax
0x140004b48  mov     eax, edi
0x140004b4a  add     r8, rax
0x140004b4d  mov     r15d, r14d
0x140004b50  add     r8, [r12+20h]; VirtualAddress
0x140004b55  sub     r15d, edi
0x140004b58  mov     r9d, r15d; Length
0x140004b5b  call    cs:__imp_IoBuildPartialMdl
0x140004b62  nop     dword ptr [rax+rax+00h]
0x140004b67  mov     rcx, cs:TdiMappingAddress; MappingAddress
0x140004b6e  lea     r8, [rbp+TargetMdl]; MemoryDescriptorList
0x140004b72  mov     r9d, 1; CacheType
0x140004b78  mov     edx, 6D494454h; PoolTag
0x140004b7d  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140004b84  nop     dword ptr [rax+rax+00h]
0x140004b89  mov     r8d, r15d; Size
0x140004b8c  mov     rdx, rsi; Src
0x140004b8f  mov     rcx, rax; void *
0x140004b92  call    memmove
0x140004b97  mov     rcx, cs:TdiMappingAddress; BaseAddress
0x140004b9e  lea     r8, [rbp+TargetMdl]; MemoryDescriptorList
0x140004ba2  mov     edx, 6D494454h; PoolTag
0x140004ba7  call    cs:__imp_MmUnmapReservedMapping
0x140004bae  nop     dword ptr [rax+rax+00h]
0x140004bb3  test    byte ptr [rbp+TargetMdl.MdlFlags], 20h
0x140004bb7  jz      short loc_140004BCD
0x140004bb9  mov     rcx, [rbp+TargetMdl.MappedSystemVa]; BaseAddress
0x140004bbd  lea     rdx, [rbp+TargetMdl]; MemoryDescriptorList
0x140004bc1  call    cs:__imp_MmUnmapLockedPages
0x140004bc8  nop     dword ptr [rax+rax+00h]
0x140004bcd  add     rsi, r15
0x140004bd0  mov     edi, r14d
0x140004bd3  cmp     r14d, ebx
0x140004bd6  jb      loc_140004B22
0x140004bdc  lea     rcx, TdiMappingAddressLock; SpinLock
0x140004be3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140004bea  nop     dword ptr [rax+rax+00h]
0x140004bef  mov     rcx, [rbp+var_10]
0x140004bf3  xor     rcx, rsp; StackCookie
0x140004bf6  call    __security_check_cookie
0x140004bfb  add     rsp, 70h
0x140004bff  pop     r15
0x140004c01  pop     r14
0x140004c03  pop     r12
0x140004c05  pop     rdi
0x140004c06  pop     rsi
0x140004c07  pop     rbx
0x140004c08  pop     rbp
0x140004c09  retn
```
