# TdiCopyBufferToMdl

- ea: `0x1400039d0`
- end: `0x140003c2a`
- name: `TdiCopyBufferToMdl`
- size: `602`
- prototype: `NTSTATUS __stdcall(PVOID SourceBuffer, ULONG SourceOffset, ULONG SourceBytesToCopy, PMDL DestinationMdlChain, ULONG DestinationOffset, PULONG BytesCopied)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400039d0`
- `0x1400054e0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003abc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003b08`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003b52`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003b9a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003abc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003b08`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003b52`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003b9a`

## pseudocode

```c
NTSTATUS __stdcall TdiCopyBufferToMdl(
        PVOID SourceBuffer,
        ULONG SourceOffset,
        ULONG SourceBytesToCopy,
        PMDL DestinationMdlChain,
        ULONG DestinationOffset,
        PULONG BytesCopied)
{
  PMDL v6; // r14
  __int64 v7; // rdi
  ULONG v8; // ebx
  char *MappedSystemVa; // r12
  ULONG i; // r15d
  ULONG ByteCount; // r13d
  char *v13; // r15
  ULONG v15; // ecx

  v6 = DestinationMdlChain;
  v7 = SourceOffset;
  v8 = SourceBytesToCopy;
  *BytesCopied = 0;
  if ( !SourceBytesToCopy )
    return 0;
  if ( !DestinationMdlChain )
    return -2147483643;
  if ( (DestinationMdlChain->MdlFlags & 5) != 0 )
    MappedSystemVa = (char *)DestinationMdlChain->MappedSystemVa;
  else
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(DestinationMdlChain, 0, MmCached, 0, 0, 0x40000010u);
  if ( MappedSystemVa )
  {
    for ( i = 0; ; i += ByteCount )
    {
      ByteCount = v6->ByteCount;
      if ( i >= DestinationOffset )
        goto LABEL_8;
      v15 = DestinationOffset - i;
      if ( ByteCount > DestinationOffset - i )
      {
        ByteCount += i - DestinationOffset;
        MappedSystemVa += v15;
LABEL_8:
        v13 = (char *)SourceBuffer + v7;
        while ( v8 && v6 )
        {
          if ( ByteCount )
          {
            if ( ByteCount >= v8 )
            {
              RtlCopyVolatileMemory(MappedSystemVa, v13, v8);
              *BytesCopied += v8;
              return 0;
            }
            RtlCopyVolatileMemory(MappedSystemVa, v13, ByteCount);
            *BytesCopied += ByteCount;
            v8 -= ByteCount;
            v13 += ByteCount;
            ByteCount = 0;
          }
          else
          {
            v6 = v6->Next;
            if ( !v6 )
              return -2147483643;
            MappedSystemVa = (char *)((v6->MdlFlags & 5) != 0
                                    ? v6->MappedSystemVa
                                    : MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u));
            if ( !MappedSystemVa )
              return -2147483643;
            ByteCount = v6->ByteCount;
          }
        }
        return v8 != 0 ? 0x80000005 : 0;
      }
      v6 = v6->Next;
      if ( ByteCount == v15 )
        break;
      if ( !v6 )
        return -2147483643;
      if ( (v6->MdlFlags & 5) != 0 )
        MappedSystemVa = (char *)v6->MappedSystemVa;
      else
        MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u);
      if ( !MappedSystemVa )
        return -1073741670;
    }
    if ( !v6 )
      return -2147483643;
    if ( (v6->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v6->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u);
    if ( MappedSystemVa )
    {
      ByteCount = v6->ByteCount;
      goto LABEL_8;
    }
  }
  return -1073741670;
}

```

## disassembly

```asm
0x1400039d0  push    rbx
0x1400039d2  push    rbp
0x1400039d3  push    rsi
0x1400039d4  push    rdi
0x1400039d5  push    r14
0x1400039d7  sub     rsp, 30h
0x1400039db  mov     rsi, [rsp+58h+BytesCopied]
0x1400039e3  mov     r14, r9
0x1400039e6  mov     edi, edx
0x1400039e8  mov     ebx, r8d
0x1400039eb  xor     edx, edx; AccessMode
0x1400039ed  mov     rbp, rcx
0x1400039f0  mov     [rsi], edx
0x1400039f2  test    r8d, r8d
0x1400039f5  jz      loc_140003A96
0x1400039fb  mov     [rsp+58h+arg_0], r12
0x140003a00  mov     [rsp+58h+arg_8], r13
0x140003a05  mov     [rsp+58h+arg_10], r15
0x140003a0a  test    r9, r9
0x140003a0d  jz      loc_140003BC3
0x140003a13  test    byte ptr [r9+0Ah], 5
0x140003a18  jz      loc_140003AA4
0x140003a1e  mov     r12, [r9+18h]
0x140003a22  test    r12, r12
0x140003a25  jz      loc_140003C20
0x140003a2b  mov     r15d, edx
0x140003a2e  mov     eax, [rsp+58h+DestinationOffset]
0x140003a35  mov     r13d, [r14+28h]
0x140003a39  cmp     r15d, eax
0x140003a3c  jb      loc_140003BAB
0x140003a42  lea     r15, [rdi+rbp]
0x140003a46  test    ebx, ebx
0x140003a48  jz      loc_140003C12
0x140003a4e  test    r14, r14
0x140003a51  jz      loc_140003C12
0x140003a57  test    r13d, r13d
0x140003a5a  jz      loc_140003BE7
0x140003a60  mov     rdx, r15; Src
0x140003a63  mov     rcx, r12; void *
0x140003a66  cmp     r13d, ebx
0x140003a69  jb      loc_140003BF4
0x140003a6f  mov     r8d, ebx; Size
0x140003a72  call    RtlCopyVolatileMemory
0x140003a77  add     [rsi], ebx
0x140003a79  xor     eax, eax
0x140003a7b  mov     r13, [rsp+58h+arg_8]
0x140003a80  mov     r12, [rsp+58h+arg_0]
0x140003a85  mov     r15, [rsp+58h+arg_10]
0x140003a8a  add     rsp, 30h
0x140003a8e  pop     r14
0x140003a90  pop     rdi
0x140003a91  pop     rsi
0x140003a92  pop     rbp
0x140003a93  pop     rbx
0x140003a94  retn
0x140003a96  xor     eax, eax
0x140003a98  add     rsp, 30h
0x140003a9c  pop     r14
0x140003a9e  pop     rdi
0x140003a9f  pop     rsi
0x140003aa0  pop     rbp
0x140003aa1  pop     rbx
0x140003aa2  retn
0x140003aa4  mov     [rsp+58h+Priority], 40000010h; Priority
0x140003aac  xor     r9d, r9d; RequestedAddress
0x140003aaf  mov     r8d, 1; CacheType
0x140003ab5  mov     [rsp+58h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140003ab9  mov     rcx, r14; MemoryDescriptorList
0x140003abc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003ac3  nop     dword ptr [rax+rax+00h]
0x140003ac8  mov     r12, rax
0x140003acb  xor     edx, edx
0x140003acd  jmp     loc_140003A22
0x140003ad2  test    byte ptr [r14+0Ah], 5
0x140003ad7  jz      short loc_140003AEE
0x140003ad9  mov     r12, [r14+18h]
0x140003add  test    r12, r12
0x140003ae0  jz      loc_140003C20
0x140003ae6  add     r15d, r13d
0x140003ae9  jmp     loc_140003A2E
0x140003aee  mov     [rsp+58h+Priority], 40000010h; Priority
0x140003af6  xor     r9d, r9d; RequestedAddress
0x140003af9  mov     [rsp+58h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140003afd  mov     r8d, 1; CacheType
0x140003b03  xor     edx, edx; AccessMode
0x140003b05  mov     rcx, r14; MemoryDescriptorList
0x140003b08  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003b0f  nop     dword ptr [rax+rax+00h]
0x140003b14  mov     r12, rax
0x140003b17  xor     edx, edx
0x140003b19  jmp     short loc_140003ADD
0x140003b1b  test    byte ptr [r14+0Ah], 5
0x140003b20  jz      short loc_140003B38
0x140003b22  mov     r12, [r14+18h]
0x140003b26  test    r12, r12
0x140003b29  jz      loc_140003C20
0x140003b2f  mov     r13d, [r14+28h]
0x140003b33  jmp     loc_140003A42
0x140003b38  mov     [rsp+58h+Priority], 40000010h; Priority
0x140003b40  xor     r9d, r9d; RequestedAddress
0x140003b43  mov     [rsp+58h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140003b47  mov     r8d, 1; CacheType
0x140003b4d  xor     edx, edx; AccessMode
0x140003b4f  mov     rcx, r14; MemoryDescriptorList
0x140003b52  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003b59  nop     dword ptr [rax+rax+00h]
0x140003b5e  mov     r12, rax
0x140003b61  xor     edx, edx
0x140003b63  jmp     short loc_140003B26
0x140003b65  test    byte ptr [r14+0Ah], 5
0x140003b6a  jz      short loc_140003B80
0x140003b6c  mov     r12, [r14+18h]
0x140003b70  test    r12, r12
0x140003b73  jz      short loc_140003BC3
0x140003b75  mov     r13d, [r14+28h]
0x140003b79  xor     edx, edx
0x140003b7b  jmp     loc_140003A46
0x140003b80  mov     [rsp+58h+Priority], 40000010h; Priority
0x140003b88  xor     r9d, r9d; RequestedAddress
0x140003b8b  mov     [rsp+58h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140003b8f  mov     r8d, 1; CacheType
0x140003b95  xor     edx, edx; AccessMode
0x140003b97  mov     rcx, r14; MemoryDescriptorList
0x140003b9a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003ba1  nop     dword ptr [rax+rax+00h]
0x140003ba6  mov     r12, rax
0x140003ba9  jmp     short loc_140003B70
0x140003bab  mov     ecx, eax
0x140003bad  sub     ecx, r15d
0x140003bb0  cmp     r13d, ecx
0x140003bb3  ja      short loc_140003BD7
0x140003bb5  mov     r14, [r14]
0x140003bb8  jz      short loc_140003BCD
0x140003bba  test    r14, r14
0x140003bbd  jnz     loc_140003AD2
0x140003bc3  mov     eax, 80000005h
0x140003bc8  jmp     loc_140003A7B
0x140003bcd  test    r14, r14
0x140003bd0  jz      short loc_140003BC3
0x140003bd2  jmp     loc_140003B1B
0x140003bd7  sub     r15d, eax
0x140003bda  mov     eax, ecx
0x140003bdc  add     r13d, r15d
0x140003bdf  add     r12, rax
0x140003be2  jmp     loc_140003A42
0x140003be7  mov     r14, [r14]
0x140003bea  test    r14, r14
0x140003bed  jz      short loc_140003BC3
0x140003bef  jmp     loc_140003B65
0x140003bf4  mov     r8d, r13d; Size
0x140003bf7  mov     edi, r13d
0x140003bfa  call    RtlCopyVolatileMemory
0x140003bff  add     [rsi], r13d
0x140003c02  sub     ebx, r13d
0x140003c05  add     r15, rdi
0x140003c08  xor     edx, edx
0x140003c0a  mov     r13d, edx
0x140003c0d  jmp     loc_140003A46
0x140003c12  neg     ebx
0x140003c14  sbb     eax, eax
0x140003c16  and     eax, 80000005h
0x140003c1b  jmp     loc_140003A7B
0x140003c20  mov     eax, 0C000009Ah
0x140003c25  jmp     loc_140003A7B
```
