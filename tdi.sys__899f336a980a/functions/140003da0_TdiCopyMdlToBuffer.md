# TdiCopyMdlToBuffer

- ea: `0x140003da0`
- end: `0x140003fea`
- name: `TdiCopyMdlToBuffer`
- size: `586`
- prototype: `NTSTATUS __stdcall(PMDL SourceMdlChain, ULONG SourceOffset, PVOID DestinationBuffer, ULONG DestinationOffset, ULONG DestinationBufferSize, PULONG BytesCopied)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003da0`
- `0x1400054e0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003dec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003e64`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003eb8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003f3a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003dec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003e64`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003eb8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003f3a`

## pseudocode

```c
NTSTATUS __stdcall TdiCopyMdlToBuffer(
        PMDL SourceMdlChain,
        ULONG SourceOffset,
        PVOID DestinationBuffer,
        ULONG DestinationOffset,
        ULONG DestinationBufferSize,
        PULONG BytesCopied)
{
  __int64 v8; // r14
  PMDL v10; // rbx
  char *MappedSystemVa; // r15
  ULONG i; // edi
  unsigned int ByteCount; // ecx
  __int64 v14; // rax
  char *v15; // rax
  char *v16; // rbp
  unsigned int v17; // esi
  __int64 v18; // rdi
  unsigned int BytesCopieda; // [rsp+88h] [rbp+30h]

  v8 = DestinationOffset;
  v10 = SourceMdlChain;
  *BytesCopied = 0;
  if ( (SourceMdlChain->MdlFlags & 5) != 0 )
    MappedSystemVa = (char *)SourceMdlChain->MappedSystemVa;
  else
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(SourceMdlChain, 0, MmCached, 0, 0, 0x40000010u);
  if ( MappedSystemVa )
  {
    for ( i = 0; ; i += ByteCount )
    {
      ByteCount = v10->ByteCount;
      BytesCopieda = ByteCount;
      if ( i >= SourceOffset )
        goto LABEL_23;
      v14 = SourceOffset - i;
      if ( ByteCount > (unsigned int)v14 )
      {
        ByteCount += i - SourceOffset;
        MappedSystemVa += v14;
        goto LABEL_22;
      }
      v10 = v10->Next;
      if ( ByteCount == (_DWORD)v14 )
        break;
      if ( !v10 )
        return 0;
      if ( (v10->MdlFlags & 5) != 0 )
      {
        MappedSystemVa = (char *)v10->MappedSystemVa;
      }
      else
      {
        v15 = (char *)MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u);
        ByteCount = BytesCopieda;
        MappedSystemVa = v15;
      }
      if ( !MappedSystemVa )
        return -1073741670;
    }
    if ( !v10 )
      return 0;
    if ( (v10->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v10->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u);
    if ( MappedSystemVa )
    {
      ByteCount = v10->ByteCount;
LABEL_22:
      BytesCopieda = ByteCount;
LABEL_23:
      v16 = (char *)DestinationBuffer + v8;
      v17 = DestinationBufferSize - v8;
      while ( v17 && v10 )
      {
        if ( ByteCount )
        {
          if ( v17 == ByteCount )
          {
            RtlCopyVolatileMemory(v16, MappedSystemVa, v17);
            *BytesCopied += v17;
            return 0;
          }
          if ( v17 < ByteCount )
          {
            RtlCopyVolatileMemory(v16, MappedSystemVa, v17);
            *BytesCopied += v17;
            return -2147483643;
          }
          v18 = ByteCount;
          RtlCopyVolatileMemory(v16, MappedSystemVa, ByteCount);
          v16 += v18;
          *BytesCopied += BytesCopieda;
          v17 -= BytesCopieda;
          ByteCount = 0;
          BytesCopieda = 0;
        }
        else
        {
          v10 = v10->Next;
          if ( !v10 )
            return 0;
          if ( (v10->MdlFlags & 5) != 0 )
            MappedSystemVa = (char *)v10->MappedSystemVa;
          else
            MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u);
          if ( !MappedSystemVa )
            return -1073741670;
          ByteCount = v10->ByteCount;
          BytesCopieda = ByteCount;
        }
      }
      return v10 != 0 ? 0x80000005 : 0;
    }
  }
  return -1073741670;
}

```

## disassembly

```asm
0x140003da0  mov     [rsp+arg_10], rbx
0x140003da5  push    rsi
0x140003da6  push    r12
0x140003da8  push    r13
0x140003daa  push    r14
0x140003dac  push    r15
0x140003dae  sub     rsp, 30h
0x140003db2  mov     r13, [rsp+58h+BytesCopied]
0x140003dba  mov     esi, edx
0x140003dbc  xor     edx, edx; AccessMode
0x140003dbe  mov     r14d, r9d
0x140003dc1  mov     r12, r8
0x140003dc4  mov     rbx, rcx
0x140003dc7  mov     [r13+0], edx
0x140003dcb  test    byte ptr [rcx+0Ah], 5
0x140003dcf  jz      short loc_140003DD7
0x140003dd1  mov     r15, [rcx+18h]
0x140003dd5  jmp     short loc_140003DFD
0x140003dd7  mov     [rsp+58h+Priority], 40000010h; Priority
0x140003ddf  xor     r9d, r9d; RequestedAddress
0x140003de2  mov     r8d, 1; CacheType
0x140003de8  mov     [rsp+58h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140003dec  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003df3  nop     dword ptr [rax+rax+00h]
0x140003df8  mov     r15, rax
0x140003dfb  xor     edx, edx
0x140003dfd  mov     [rsp+58h+arg_0], rbp
0x140003e02  mov     [rsp+58h+arg_8], rdi
0x140003e07  test    r15, r15
0x140003e0a  jz      loc_140003FC7
0x140003e10  mov     edi, edx
0x140003e12  mov     ecx, [rbx+28h]
0x140003e15  mov     dword ptr [rsp+58h+BytesCopied], ecx
0x140003e1c  cmp     edi, esi
0x140003e1e  jnb     loc_140003EE5
0x140003e24  mov     eax, esi
0x140003e26  sub     eax, edi
0x140003e28  cmp     ecx, eax
0x140003e2a  ja      loc_140003ED7
0x140003e30  mov     rbx, [rbx]
0x140003e33  jz      short loc_140003E89
0x140003e35  test    rbx, rbx
0x140003e38  jz      loc_140003FB7
0x140003e3e  test    byte ptr [rbx+0Ah], 5
0x140003e42  jz      short loc_140003E4A
0x140003e44  mov     r15, [rbx+18h]
0x140003e48  jmp     short loc_140003E7C
0x140003e4a  mov     [rsp+58h+Priority], 40000010h; Priority
0x140003e52  xor     r9d, r9d; RequestedAddress
0x140003e55  mov     [rsp+58h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140003e59  mov     r8d, 1; CacheType
0x140003e5f  xor     edx, edx; AccessMode
0x140003e61  mov     rcx, rbx; MemoryDescriptorList
0x140003e64  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003e6b  nop     dword ptr [rax+rax+00h]
0x140003e70  mov     ecx, dword ptr [rsp+58h+BytesCopied]
0x140003e77  xor     edx, edx
0x140003e79  mov     r15, rax
0x140003e7c  test    r15, r15
0x140003e7f  jz      loc_140003FC7
0x140003e85  add     edi, ecx
0x140003e87  jmp     short loc_140003E12
0x140003e89  test    rbx, rbx
0x140003e8c  jz      loc_140003FB7
0x140003e92  test    byte ptr [rbx+0Ah], 5
0x140003e96  jz      short loc_140003E9E
0x140003e98  mov     r15, [rbx+18h]
0x140003e9c  jmp     short loc_140003EC9
0x140003e9e  mov     [rsp+58h+Priority], 40000010h; Priority
0x140003ea6  xor     r9d, r9d; RequestedAddress
0x140003ea9  mov     [rsp+58h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140003ead  mov     r8d, 1; CacheType
0x140003eb3  xor     edx, edx; AccessMode
0x140003eb5  mov     rcx, rbx; MemoryDescriptorList
0x140003eb8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003ebf  nop     dword ptr [rax+rax+00h]
0x140003ec4  mov     r15, rax
0x140003ec7  xor     edx, edx
0x140003ec9  test    r15, r15
0x140003ecc  jz      loc_140003FC7
0x140003ed2  mov     ecx, [rbx+28h]
0x140003ed5  jmp     short loc_140003EDE
0x140003ed7  sub     edi, esi
0x140003ed9  add     ecx, edi
0x140003edb  add     r15, rax
0x140003ede  mov     dword ptr [rsp+58h+BytesCopied], ecx
0x140003ee5  mov     esi, [rsp+58h+DestinationBufferSize]
0x140003eec  lea     rbp, [r12+r14]
0x140003ef0  sub     esi, r14d
0x140003ef3  test    esi, esi
0x140003ef5  jz      loc_140003FBB
0x140003efb  test    rbx, rbx
0x140003efe  jz      loc_140003FBB
0x140003f04  test    ecx, ecx
0x140003f06  jnz     short loc_140003F5C
0x140003f08  mov     rbx, [rbx]
0x140003f0b  test    rbx, rbx
0x140003f0e  jz      loc_140003FB7
0x140003f14  test    byte ptr [rbx+0Ah], 5
0x140003f18  jz      short loc_140003F20
0x140003f1a  mov     r15, [rbx+18h]
0x140003f1e  jmp     short loc_140003F49
0x140003f20  mov     [rsp+58h+Priority], 40000010h; Priority
0x140003f28  xor     r9d, r9d; RequestedAddress
0x140003f2b  mov     [rsp+58h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140003f2f  mov     r8d, 1; CacheType
0x140003f35  xor     edx, edx; AccessMode
0x140003f37  mov     rcx, rbx; MemoryDescriptorList
0x140003f3a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003f41  nop     dword ptr [rax+rax+00h]
0x140003f46  mov     r15, rax
0x140003f49  test    r15, r15
0x140003f4c  jz      short loc_140003FC7
0x140003f4e  mov     ecx, [rbx+28h]
0x140003f51  xor     edx, edx
0x140003f53  mov     dword ptr [rsp+58h+BytesCopied], ecx
0x140003f5a  jmp     short loc_140003EF3
0x140003f5c  mov     rdx, r15; Src
0x140003f5f  cmp     esi, ecx
0x140003f61  jz      short loc_140003FA8
0x140003f63  jb      short loc_140003F92
0x140003f65  mov     edi, ecx
0x140003f67  mov     r8d, ecx; Size
0x140003f6a  mov     rcx, rbp; void *
0x140003f6d  call    RtlCopyVolatileMemory
0x140003f72  mov     eax, dword ptr [rsp+58h+BytesCopied]
0x140003f79  add     rbp, rdi
0x140003f7c  add     [r13+0], eax
0x140003f80  sub     esi, eax
0x140003f82  xor     edx, edx
0x140003f84  mov     ecx, edx
0x140003f86  mov     dword ptr [rsp+58h+BytesCopied], edx
0x140003f8d  jmp     loc_140003EF3
0x140003f92  mov     r8d, esi; Size
0x140003f95  mov     rcx, rbp; void *
0x140003f98  call    RtlCopyVolatileMemory
0x140003f9d  add     [r13+0], esi
0x140003fa1  mov     eax, 80000005h
0x140003fa6  jmp     short loc_140003FCC
0x140003fa8  mov     r8d, esi; Size
0x140003fab  mov     rcx, rbp; void *
0x140003fae  call    RtlCopyVolatileMemory
0x140003fb3  add     [r13+0], esi
0x140003fb7  xor     eax, eax
0x140003fb9  jmp     short loc_140003FCC
0x140003fbb  neg     rbx
0x140003fbe  sbb     eax, eax
0x140003fc0  and     eax, 80000005h
0x140003fc5  jmp     short loc_140003FCC
0x140003fc7  mov     eax, 0C000009Ah
0x140003fcc  mov     rdi, [rsp+58h+arg_8]
0x140003fd1  mov     rbp, [rsp+58h+arg_0]
0x140003fd6  mov     rbx, [rsp+58h+arg_10]
0x140003fdb  add     rsp, 30h
0x140003fdf  pop     r15
0x140003fe1  pop     r14
0x140003fe3  pop     r13
0x140003fe5  pop     r12
0x140003fe7  pop     rsi
0x140003fe8  retn
```
