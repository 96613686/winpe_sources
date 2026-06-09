# TdiCopyMdlChainToMdlChain

- ea: `0x140004c20`
- end: `0x140004eb4`
- name: `TdiCopyMdlChainToMdlChain`
- size: `660`
- prototype: `NTSTATUS __stdcall(PMDL SourceMdlChain, ULONG SourceOffset, PMDL DestinationMdlChain, ULONG DestinationOffset, PULONG BytesCopied)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140004c20`
- `0x140005600`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004c7d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004cdc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004d29`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004d8a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004de9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004e40`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004c7d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004cdc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004d29`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004d8a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004de9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004e40`

## pseudocode

```c
NTSTATUS __stdcall TdiCopyMdlChainToMdlChain(
        PMDL SourceMdlChain,
        ULONG SourceOffset,
        PMDL DestinationMdlChain,
        ULONG DestinationOffset,
        PULONG BytesCopied)
{
  PMDL v6; // rdi
  char *MappedSystemVa; // r14
  ULONG i; // ebx
  unsigned int ByteCount; // r12d
  __int64 v12; // rax
  char *v13; // rbp
  ULONG j; // ebx
  ULONG v15; // r15d
  __int64 v16; // rax
  ULONG v17; // eax
  __int64 v18; // rbx

  v6 = DestinationMdlChain;
  *BytesCopied = 0;
  if ( !DestinationMdlChain )
    return -2147483643;
  if ( (DestinationMdlChain->MdlFlags & 5) != 0 )
    MappedSystemVa = (char *)DestinationMdlChain->MappedSystemVa;
  else
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(DestinationMdlChain, 0, MmCached, 0, 0, 0x40000010u);
  if ( !MappedSystemVa )
    return -1073741670;
  for ( i = 0; ; i += ByteCount )
  {
    ByteCount = v6->ByteCount;
    if ( i >= DestinationOffset )
      break;
    v12 = DestinationOffset - i;
    if ( ByteCount > (unsigned int)v12 )
    {
      MappedSystemVa += v12;
      ByteCount += i - DestinationOffset;
      break;
    }
    v6 = v6->Next;
    if ( !v6 )
      return -2147483643;
    if ( (v6->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v6->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u);
    if ( !MappedSystemVa )
      return -1073741670;
  }
  v13 = (char *)((SourceMdlChain->MdlFlags & 5) != 0
               ? SourceMdlChain->MappedSystemVa
               : MmMapLockedPagesSpecifyCache(SourceMdlChain, 0, MmCached, 0, 0, 0x40000010u));
  if ( !v13 )
    return -1073741670;
  for ( j = 0; ; j += v15 )
  {
    v15 = SourceMdlChain->ByteCount;
    if ( j >= SourceOffset )
      goto LABEL_30;
    v16 = SourceOffset - j;
    if ( v15 > (unsigned int)v16 )
      break;
    SourceMdlChain = SourceMdlChain->Next;
    if ( !SourceMdlChain )
      return -2147483643;
    if ( (SourceMdlChain->MdlFlags & 5) != 0 )
      v13 = (char *)SourceMdlChain->MappedSystemVa;
    else
      v13 = (char *)MmMapLockedPagesSpecifyCache(SourceMdlChain, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v13 )
      return -1073741670;
  }
  v13 += v16;
  for ( v15 += j - SourceOffset; ; v15 = SourceMdlChain->ByteCount )
  {
LABEL_30:
    while ( v15 )
    {
      if ( ByteCount )
      {
        v17 = v15;
        if ( ByteCount <= v15 )
          v17 = ByteCount;
        v18 = v17;
        memmove(MappedSystemVa, v13, v17);
        v15 -= v18;
        v13 += v18;
        ByteCount -= v18;
        MappedSystemVa += v18;
        *BytesCopied += v18;
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
    SourceMdlChain = SourceMdlChain->Next;
    if ( !SourceMdlChain )
      break;
    if ( (SourceMdlChain->MdlFlags & 5) != 0 )
      v13 = (char *)SourceMdlChain->MappedSystemVa;
    else
      v13 = (char *)MmMapLockedPagesSpecifyCache(SourceMdlChain, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v13 )
      return -1073741670;
  }
  return 0;
}

```

## disassembly

```asm
0x140004c20  push    rbx
0x140004c22  push    rbp
0x140004c23  push    rsi
0x140004c24  push    rdi
0x140004c25  push    r12
0x140004c27  push    r13
0x140004c29  push    r14
0x140004c2b  push    r15
0x140004c2d  sub     rsp, 38h
0x140004c31  mov     rax, [rsp+78h+BytesCopied]
0x140004c39  mov     ebp, r9d
0x140004c3c  mov     rdi, r8
0x140004c3f  mov     r13d, edx
0x140004c42  mov     rsi, rcx
0x140004c45  mov     dword ptr [rax], 0
0x140004c4b  test    r8, r8
0x140004c4e  jz      loc_140004E9D
0x140004c54  test    byte ptr [r8+0Ah], 5
0x140004c59  jz      short loc_140004C61
0x140004c5b  mov     r14, [r8+18h]
0x140004c5f  jmp     short loc_140004C8C
0x140004c61  xor     r9d, r9d; RequestedAddress
0x140004c64  mov     [rsp+78h+Priority], 40000010h; Priority
0x140004c6c  xor     edx, edx; AccessMode
0x140004c6e  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140004c76  mov     rcx, rdi; MemoryDescriptorList
0x140004c79  lea     r8d, [r9+1]; CacheType
0x140004c7d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140004c84  nop     dword ptr [rax+rax+00h]
0x140004c89  mov     r14, rax
0x140004c8c  test    r14, r14
0x140004c8f  jz      loc_140004E96
0x140004c95  xor     ebx, ebx
0x140004c97  mov     r12d, [rdi+28h]
0x140004c9b  cmp     ebx, ebp
0x140004c9d  jnb     short loc_140004D01
0x140004c9f  mov     eax, ebp
0x140004ca1  sub     eax, ebx
0x140004ca3  cmp     r12d, eax
0x140004ca6  ja      short loc_140004CF9
0x140004ca8  mov     rdi, [rdi]
0x140004cab  test    rdi, rdi
0x140004cae  jz      loc_140004E9D
0x140004cb4  test    byte ptr [rdi+0Ah], 5
0x140004cb8  jz      short loc_140004CC0
0x140004cba  mov     r14, [rdi+18h]
0x140004cbe  jmp     short loc_140004CEB
0x140004cc0  xor     r9d, r9d; RequestedAddress
0x140004cc3  mov     [rsp+78h+Priority], 40000010h; Priority
0x140004ccb  xor     edx, edx; AccessMode
0x140004ccd  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140004cd5  mov     rcx, rdi; MemoryDescriptorList
0x140004cd8  lea     r8d, [r9+1]; CacheType
0x140004cdc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140004ce3  nop     dword ptr [rax+rax+00h]
0x140004ce8  mov     r14, rax
0x140004ceb  test    r14, r14
0x140004cee  jz      loc_140004E96
0x140004cf4  add     ebx, r12d
0x140004cf7  jmp     short loc_140004C97
0x140004cf9  add     r14, rax
0x140004cfc  sub     ebx, ebp
0x140004cfe  add     r12d, ebx
0x140004d01  test    byte ptr [rsi+0Ah], 5
0x140004d05  jz      short loc_140004D0D
0x140004d07  mov     rbp, [rsi+18h]
0x140004d0b  jmp     short loc_140004D38
0x140004d0d  xor     r9d, r9d; RequestedAddress
0x140004d10  mov     [rsp+78h+Priority], 40000010h; Priority
0x140004d18  xor     edx, edx; AccessMode
0x140004d1a  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140004d22  mov     rcx, rsi; MemoryDescriptorList
0x140004d25  lea     r8d, [r9+1]; CacheType
0x140004d29  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140004d30  nop     dword ptr [rax+rax+00h]
0x140004d35  mov     rbp, rax
0x140004d38  test    rbp, rbp
0x140004d3b  jz      loc_140004E96
0x140004d41  xor     ebx, ebx
0x140004d43  mov     r15d, [rsi+28h]
0x140004d47  cmp     ebx, r13d
0x140004d4a  jnb     short loc_140004DB0
0x140004d4c  mov     eax, r13d
0x140004d4f  sub     eax, ebx
0x140004d51  cmp     r15d, eax
0x140004d54  ja      short loc_140004DA7
0x140004d56  mov     rsi, [rsi]
0x140004d59  test    rsi, rsi
0x140004d5c  jz      loc_140004E9D
0x140004d62  test    byte ptr [rsi+0Ah], 5
0x140004d66  jz      short loc_140004D6E
0x140004d68  mov     rbp, [rsi+18h]
0x140004d6c  jmp     short loc_140004D99
0x140004d6e  xor     r9d, r9d; RequestedAddress
0x140004d71  mov     [rsp+78h+Priority], 40000010h; Priority
0x140004d79  xor     edx, edx; AccessMode
0x140004d7b  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140004d83  mov     rcx, rsi; MemoryDescriptorList
0x140004d86  lea     r8d, [r9+1]; CacheType
0x140004d8a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140004d91  nop     dword ptr [rax+rax+00h]
0x140004d96  mov     rbp, rax
0x140004d99  test    rbp, rbp
0x140004d9c  jz      loc_140004E96
0x140004da2  add     ebx, r15d
0x140004da5  jmp     short loc_140004D43
0x140004da7  add     rbp, rax
0x140004daa  sub     ebx, r13d
0x140004dad  add     r15d, ebx
0x140004db0  test    r15d, r15d
0x140004db3  jnz     short loc_140004E07
0x140004db5  mov     rsi, [rsi]
0x140004db8  test    rsi, rsi
0x140004dbb  jz      loc_140004E92
0x140004dc1  test    byte ptr [rsi+0Ah], 5
0x140004dc5  jz      short loc_140004DCD
0x140004dc7  mov     rbp, [rsi+18h]
0x140004dcb  jmp     short loc_140004DF8
0x140004dcd  xor     r9d, r9d; RequestedAddress
0x140004dd0  mov     [rsp+78h+Priority], 40000010h; Priority
0x140004dd8  xor     edx, edx; AccessMode
0x140004dda  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140004de2  mov     rcx, rsi; MemoryDescriptorList
0x140004de5  lea     r8d, [r9+1]; CacheType
0x140004de9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140004df0  nop     dword ptr [rax+rax+00h]
0x140004df5  mov     rbp, rax
0x140004df8  test    rbp, rbp
0x140004dfb  jz      loc_140004E96
0x140004e01  mov     r15d, [rsi+28h]
0x140004e05  jmp     short loc_140004DB0
0x140004e07  test    r12d, r12d
0x140004e0a  jnz     short loc_140004E5D
0x140004e0c  mov     rdi, [rdi]
0x140004e0f  test    rdi, rdi
0x140004e12  jz      loc_140004E9D
0x140004e18  test    byte ptr [rdi+0Ah], 5
0x140004e1c  jz      short loc_140004E24
0x140004e1e  mov     r14, [rdi+18h]
0x140004e22  jmp     short loc_140004E4F
0x140004e24  xor     r9d, r9d; RequestedAddress
0x140004e27  mov     [rsp+78h+Priority], 40000010h; Priority
0x140004e2f  xor     edx, edx; AccessMode
0x140004e31  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140004e39  mov     rcx, rdi; MemoryDescriptorList
0x140004e3c  lea     r8d, [r9+1]; CacheType
0x140004e40  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140004e47  nop     dword ptr [rax+rax+00h]
0x140004e4c  mov     r14, rax
0x140004e4f  test    r14, r14
0x140004e52  jz      short loc_140004E9D
0x140004e54  mov     r12d, [rdi+28h]
0x140004e58  jmp     loc_140004DB0
0x140004e5d  mov     eax, r15d
0x140004e60  cmp     r12d, r15d
0x140004e63  mov     rdx, rbp; Src
0x140004e66  mov     rcx, r14; void *
0x140004e69  cmovbe  eax, r12d
0x140004e6d  mov     r8d, eax; Size
0x140004e70  mov     ebx, eax
0x140004e72  call    memmove
0x140004e77  mov     rax, [rsp+78h+BytesCopied]
0x140004e7f  sub     r15d, ebx
0x140004e82  add     rbp, rbx
0x140004e85  sub     r12d, ebx
0x140004e88  add     r14, rbx
0x140004e8b  add     [rax], ebx
0x140004e8d  jmp     loc_140004DB0
0x140004e92  xor     eax, eax
0x140004e94  jmp     short loc_140004EA2
0x140004e96  mov     eax, 0C000009Ah
0x140004e9b  jmp     short loc_140004EA2
0x140004e9d  mov     eax, 80000005h
0x140004ea2  add     rsp, 38h
0x140004ea6  pop     r15
0x140004ea8  pop     r14
0x140004eaa  pop     r13
0x140004eac  pop     r12
0x140004eae  pop     rdi
0x140004eaf  pop     rsi
0x140004eb0  pop     rbp
0x140004eb1  pop     rbx
0x140004eb2  retn
```
