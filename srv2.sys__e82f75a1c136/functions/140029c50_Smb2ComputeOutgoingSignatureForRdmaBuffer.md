# Smb2ComputeOutgoingSignatureForRdmaBuffer

- ea: `0x140029c50`
- end: `0x140029ecf`
- name: `Smb2ComputeOutgoingSignatureForRdmaBuffer`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a100`

## callees

- `0x14000a9e8`
- `0x14000aab4`
- `0x140022958`
- `0x140029c50`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029db8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029db8`
- `srvnet!SmbCryptoSigningAlgRequireIV` at `0x140029d12`
- `srvnet!SmbCryptoSigningAlgRequireIV` at `0x140029d12`
- `srvnet!SmbCryptoCalculateAndSetIVForRdmaBuffer` at `0x140029d37`
- `srvnet!SmbCryptoCalculateAndSetIVForRdmaBuffer` at `0x140029d37`
- `ksecdd!BCryptDuplicateHash` at `0x140029cc6`
- `ksecdd!BCryptDuplicateHash` at `0x140029cc6`
- `ksecdd!BCryptHashData` at `0x140029de6`
- `ksecdd!BCryptHashData` at `0x140029de6`
- `ksecdd!BCryptFinishHash` at `0x140029e3b`
- `ksecdd!BCryptFinishHash` at `0x140029e3b`
- `ksecdd!BCryptDestroyHash` at `0x140029e93`
- `ksecdd!BCryptDestroyHash` at `0x140029e93`

## pseudocode

```c
__int64 __fastcall Smb2ComputeOutgoingSignatureForRdmaBuffer(__int64 a1, __int64 a2, struct _MDL *a3, ULONG a4)
{
  __int64 v5; // rbx
  unsigned int v9; // r15d
  UCHAR *SigningHashObject; // rax
  UCHAR *v11; // r12
  NTSTATUS v12; // ebx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  UCHAR *MappedSystemVa; // rax
  ULONG ByteCount; // r15d
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+60h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 560);
  v9 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 140LL);
  phNewHash = 0;
  SigningHashObject = (UCHAR *)Smb2AllocateSigningHashObject(*(unsigned int *)(v5 + 120));
  v11 = SigningHashObject;
  if ( !SigningHashObject )
  {
LABEL_2:
    v12 = -1073741670;
    goto LABEL_34;
  }
  v12 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(v5 + 112), &phNewHash, SigningHashObject, *(_DWORD *)(v5 + 120), 0);
  if ( v12 >= 0 )
  {
    if ( (unsigned __int8)SmbCryptoSigningAlgRequireIV(v9)
      && (v12 = SmbCryptoCalculateAndSetIVForRdmaBuffer(
                  phNewHash,
                  a2 + *(unsigned __int16 *)(a2 + 2) + 8LL,
                  *(unsigned __int16 *)(a2 + 4)),
          v12 < 0) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v14 = 23;
        goto LABEL_33;
      }
    }
    else
    {
      while ( a3 && a4 )
      {
        if ( (a3->MdlFlags & 5) != 0 )
          MappedSystemVa = (UCHAR *)a3->MappedSystemVa;
        else
          MappedSystemVa = (UCHAR *)MmMapLockedPagesSpecifyCache(a3, 0, MmCached, 0, 0, 0x40000010u);
        if ( !MappedSystemVa )
          goto LABEL_2;
        ByteCount = a3->ByteCount;
        if ( ByteCount >= a4 )
          ByteCount = a4;
        v12 = BCryptHashData(phNewHash, MappedSystemVa, ByteCount, 0);
        if ( v12 < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v14 = 24;
            goto LABEL_33;
          }
          goto LABEL_34;
        }
        a3 = a3->Next;
        a4 -= ByteCount;
      }
      v12 = BCryptFinishHash(phNewHash, (PUCHAR)(a2 + 8), *(unsigned __int16 *)(a2 + 2), 0);
      if ( v12 < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v14 = 25;
          goto LABEL_33;
        }
      }
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v14 = 22;
LABEL_33:
      WPP_SF_qD(v13->AttachedDevice, v14, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a1, v12);
    }
  }
LABEL_34:
  if ( phNewHash )
  {
    BCryptDestroyHash(phNewHash);
    phNewHash = 0;
  }
  if ( v11 )
    Smb2DeallocateSigningHashObject(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140029c50  mov     [rsp+arg_8], rbx
0x140029c55  mov     [rsp+arg_10], rbp
0x140029c5a  push    rsi
0x140029c5b  push    rdi
0x140029c5c  push    r12
0x140029c5e  push    r14
0x140029c60  push    r15
0x140029c62  sub     rsp, 30h
0x140029c66  mov     rax, [rcx+60h]
0x140029c6a  mov     r14, rcx
0x140029c6d  mov     rbx, [rcx+230h]
0x140029c74  mov     esi, r9d
0x140029c77  mov     rdi, r8
0x140029c7a  mov     rbp, rdx
0x140029c7d  mov     r10, [rax+1F0h]
0x140029c84  mov     r15d, [r10+8Ch]
0x140029c8b  mov     [rsp+58h+phNewHash], 0
0x140029c94  mov     ecx, [rbx+78h]
0x140029c97  call    Smb2AllocateSigningHashObject
0x140029c9c  mov     r12, rax
0x140029c9f  test    rax, rax
0x140029ca2  jnz     short loc_140029CAE
0x140029ca4  mov     ebx, 0C000009Ah
0x140029ca9  jmp     loc_140029E89
0x140029cae  mov     r9d, [rbx+78h]; cbHashObject
0x140029cb2  lea     rdx, [rsp+58h+phNewHash]; phNewHash
0x140029cb7  mov     rcx, [rbx+70h]; hHash
0x140029cbb  mov     r8, r12; pbHashObject
0x140029cbe  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140029cc6  call    cs:__imp_BCryptDuplicateHash
0x140029ccd  nop     dword ptr [rax+rax+00h]
0x140029cd2  mov     ebx, eax
0x140029cd4  test    eax, eax
0x140029cd6  jns     short loc_140029D0F
0x140029cd8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029cdf  lea     rax, WPP_GLOBAL_Control
0x140029ce6  cmp     rcx, rax
0x140029ce9  jz      loc_140029E89
0x140029cef  mov     edx, [rcx+2Ch]
0x140029cf2  test    dl, 1
0x140029cf5  jz      loc_140029E89
0x140029cfb  cmp     byte ptr [rcx+29h], 1
0x140029cff  jb      loc_140029E89
0x140029d05  mov     edx, 16h
0x140029d0a  jmp     loc_140029E72
0x140029d0f  mov     ecx, r15d
0x140029d12  call    cs:__imp_SmbCryptoSigningAlgRequireIV
0x140029d19  nop     dword ptr [rax+rax+00h]
0x140029d1e  test    al, al
0x140029d20  jz      short loc_140029D7F
0x140029d22  movzx   edx, word ptr [rbp+2]
0x140029d26  movzx   r8d, word ptr [rbp+4]
0x140029d2b  add     rdx, 8
0x140029d2f  mov     rcx, [rsp+58h+phNewHash]
0x140029d34  add     rdx, rbp
0x140029d37  call    cs:__imp_SmbCryptoCalculateAndSetIVForRdmaBuffer
0x140029d3e  nop     dword ptr [rax+rax+00h]
0x140029d43  mov     ebx, eax
0x140029d45  test    eax, eax
0x140029d47  jns     short loc_140029D7F
0x140029d49  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029d50  lea     rax, WPP_GLOBAL_Control
0x140029d57  cmp     rcx, rax
0x140029d5a  jz      loc_140029E89
0x140029d60  mov     eax, [rcx+2Ch]
0x140029d63  test    al, 1
0x140029d65  jz      loc_140029E89
0x140029d6b  cmp     byte ptr [rcx+29h], 1
0x140029d6f  jb      loc_140029E89
0x140029d75  mov     edx, 17h
0x140029d7a  jmp     loc_140029E72
0x140029d7f  test    rdi, rdi
0x140029d82  jz      loc_140029E2A
0x140029d88  test    esi, esi
0x140029d8a  jz      loc_140029E2A
0x140029d90  test    byte ptr [rdi+0Ah], 5
0x140029d94  jz      short loc_140029D9C
0x140029d96  mov     rax, [rdi+18h]
0x140029d9a  jmp     short loc_140029DC4
0x140029d9c  xor     r9d, r9d; RequestedAddress
0x140029d9f  mov     [rsp+58h+Priority], 40000010h; Priority
0x140029da7  xor     edx, edx; AccessMode
0x140029da9  mov     [rsp+58h+dwFlags], 0; BugCheckOnFailure
0x140029db1  mov     rcx, rdi; MemoryDescriptorList
0x140029db4  lea     r8d, [r9+1]; CacheType
0x140029db8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140029dbf  nop     dword ptr [rax+rax+00h]
0x140029dc4  test    rax, rax
0x140029dc7  jz      loc_140029CA4
0x140029dcd  mov     r15d, [rdi+28h]
0x140029dd1  mov     rdx, rax; pbInput
0x140029dd4  mov     rcx, [rsp+58h+phNewHash]; hHash
0x140029dd9  cmp     r15d, esi
0x140029ddc  cmovnb  r15d, esi
0x140029de0  xor     r9d, r9d; dwFlags
0x140029de3  mov     r8d, r15d; cbInput
0x140029de6  call    cs:__imp_BCryptHashData
0x140029ded  nop     dword ptr [rax+rax+00h]
0x140029df2  mov     ebx, eax
0x140029df4  test    eax, eax
0x140029df6  js      short loc_140029E03
0x140029df8  mov     rdi, [rdi]
0x140029dfb  sub     esi, r15d
0x140029dfe  jmp     loc_140029D7F
0x140029e03  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029e0a  lea     rax, WPP_GLOBAL_Control
0x140029e11  cmp     rcx, rax
0x140029e14  jz      short loc_140029E89
0x140029e16  mov     eax, [rcx+2Ch]
0x140029e19  test    al, 1
0x140029e1b  jz      short loc_140029E89
0x140029e1d  cmp     byte ptr [rcx+29h], 1
0x140029e21  jb      short loc_140029E89
0x140029e23  mov     edx, 18h
0x140029e28  jmp     short loc_140029E72
0x140029e2a  movzx   r8d, word ptr [rbp+2]; cbOutput
0x140029e2f  lea     rdx, [rbp+8]; pbOutput
0x140029e33  mov     rcx, [rsp+58h+phNewHash]; hHash
0x140029e38  xor     r9d, r9d; dwFlags
0x140029e3b  call    cs:__imp_BCryptFinishHash
0x140029e42  nop     dword ptr [rax+rax+00h]
0x140029e47  mov     ebx, eax
0x140029e49  test    eax, eax
0x140029e4b  jns     short loc_140029E89
0x140029e4d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029e54  lea     rax, WPP_GLOBAL_Control
0x140029e5b  cmp     rcx, rax
0x140029e5e  jz      short loc_140029E89
0x140029e60  mov     eax, [rcx+2Ch]
0x140029e63  test    al, 1
0x140029e65  jz      short loc_140029E89
0x140029e67  cmp     byte ptr [rcx+29h], 1
0x140029e6b  jb      short loc_140029E89
0x140029e6d  mov     edx, 19h
0x140029e72  mov     rcx, [rcx+18h]
0x140029e76  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x140029e7d  mov     r9, r14
0x140029e80  mov     [rsp+58h+dwFlags], ebx
0x140029e84  call    WPP_SF_qD
0x140029e89  mov     rcx, [rsp+58h+phNewHash]; hHash
0x140029e8e  test    rcx, rcx
0x140029e91  jz      short loc_140029EA8
0x140029e93  call    cs:__imp_BCryptDestroyHash
0x140029e9a  nop     dword ptr [rax+rax+00h]
0x140029e9f  mov     [rsp+58h+phNewHash], 0
0x140029ea8  test    r12, r12
0x140029eab  jz      short loc_140029EB5
0x140029ead  mov     rcx, r12
0x140029eb0  call    Smb2DeallocateSigningHashObject
0x140029eb5  mov     rbp, [rsp+58h+arg_10]
0x140029eba  mov     eax, ebx
0x140029ebc  mov     rbx, [rsp+58h+arg_8]
0x140029ec1  add     rsp, 30h
0x140029ec5  pop     r15
0x140029ec7  pop     r14
0x140029ec9  pop     r12
0x140029ecb  pop     rdi
0x140029ecc  pop     rsi
0x140029ecd  retn
```
