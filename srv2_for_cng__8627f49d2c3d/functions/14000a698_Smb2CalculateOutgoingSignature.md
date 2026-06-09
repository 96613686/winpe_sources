# Smb2CalculateOutgoingSignature

- ea: `0x14000a698`
- end: `0x14000a9e2`
- name: `Smb2CalculateOutgoingSignature`
- size: `842`
- prototype: `__int64 __fastcall(PMDL MemoryDescriptorList, ULONG, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a5a0`

## callees

- `0x14000a698`
- `0x14000a9e8`
- `0x14000aab4`
- `0x1400222ec`
- `0x140022958`
- `0x140038490`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a914`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a914`
- `srvnet!SmbCryptoSigningAlgRequireIV` at `0x14000a794`
- `srvnet!SmbCryptoSigningAlgRequireIV` at `0x14000a794`
- `srvnet!SmbCryptoCalculateAndSetIV` at `0x14000a877`
- `srvnet!SmbCryptoCalculateAndSetIV` at `0x14000a877`
- `ksecdd!BCryptDuplicateHash` at `0x14000a721`
- `ksecdd!BCryptDuplicateHash` at `0x14000a721`
- `ksecdd!BCryptHashData` at `0x14000a7dc`
- `ksecdd!BCryptHashData` at `0x14000a7dc`
- `ksecdd!BCryptFinishHash` at `0x14000a808`
- `ksecdd!BCryptFinishHash` at `0x14000a808`
- `ksecdd!BCryptDestroyHash` at `0x14000a754`
- `ksecdd!BCryptDestroyHash` at `0x14000a754`

## pseudocode

```c
__int64 __fastcall Smb2CalculateOutgoingSignature(PMDL MemoryDescriptorList, ULONG a2, __int64 a3, _OWORD *a4)
{
  __int64 v4; // r13
  __int64 v9; // rbp
  __int64 v10; // rcx
  UCHAR *SigningHashObject; // rax
  UCHAR *v12; // r15
  NTSTATUS v13; // ebx
  __int64 v15; // r8
  UCHAR *MappedSystemVa; // rax
  ULONG ByteCount; // ebp
  PDEVICE_OBJECT v18; // r10
  PDEVICE_OBJECT v19; // r10
  __int64 v20; // rdx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v22; // rdx
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+30h] [rbp-78h] BYREF
  UCHAR pbOutput[16]; // [rsp+38h] [rbp-70h] BYREF
  __int128 v25; // [rsp+48h] [rbp-60h]

  v4 = *(_QWORD *)(a3 + 560);
  v9 = *(_QWORD *)(*(_QWORD *)(a3 + 96) + 496LL);
  *(_OWORD *)pbOutput = 0;
  phNewHash = 0;
  v25 = 0;
  v10 = *(unsigned int *)(v4 + 120);
  if ( !(_DWORD)v10 )
    __int2c();
  SigningHashObject = (UCHAR *)Smb2AllocateSigningHashObject(v10);
  v12 = SigningHashObject;
  if ( !SigningHashObject )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v20 = 10;
LABEL_51:
      WPP_SF_q(v18->AttachedDevice, v20, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a3);
    }
LABEL_22:
    v13 = -1073741670;
    goto LABEL_6;
  }
  v13 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(v4 + 112), &phNewHash, SigningHashObject, *(_DWORD *)(v4 + 120), 0);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v22 = 11;
LABEL_50:
      WPP_SF_qD(AttachedDevice, v22, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a3, v13);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  if ( !(unsigned __int8)SmbCryptoSigningAlgRequireIV(*(unsigned int *)(v9 + 140))
    || (LOBYTE(v15) = 1,
        v13 = SmbCryptoCalculateAndSetIV(*(unsigned int *)(v9 + 140), *(_QWORD *)(v4 + 176), v15, 0, phNewHash),
        v13 >= 0) )
  {
    while ( 1 )
    {
      if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
        MappedSystemVa = (UCHAR *)MemoryDescriptorList->MappedSystemVa;
      else
        MappedSystemVa = (UCHAR *)MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u);
      ByteCount = a2;
      if ( a2 >= MemoryDescriptorList->ByteCount )
        ByteCount = MemoryDescriptorList->ByteCount;
      if ( !MappedSystemVa )
        break;
      MemoryDescriptorList = MemoryDescriptorList->Next;
      v13 = BCryptHashData(phNewHash, MappedSystemVa, ByteCount, 0);
      if ( v13 < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v22 = 14;
          goto LABEL_49;
        }
        goto LABEL_6;
      }
      if ( MemoryDescriptorList )
      {
        a2 -= ByteCount;
        if ( a2 )
          continue;
      }
      v13 = BCryptFinishHash(phNewHash, pbOutput, *(_DWORD *)(v4 + 124), 0);
      if ( v13 >= 0 )
      {
        *a4 = *(_OWORD *)pbOutput;
        goto LABEL_6;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v22 = 15;
        goto LABEL_49;
      }
      goto LABEL_6;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v20 = 13;
      goto LABEL_51;
    }
    goto LABEL_22;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v22 = 12;
LABEL_49:
    AttachedDevice = v19->AttachedDevice;
    goto LABEL_50;
  }
LABEL_6:
  if ( phNewHash )
    BCryptDestroyHash(phNewHash);
  if ( v12 )
    Smb2DeallocateSigningHashObject(v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000a698  push    rbx
0x14000a69a  push    rbp
0x14000a69b  push    rsi
0x14000a69c  push    rdi
0x14000a69d  push    r12
0x14000a69f  push    r13
0x14000a6a1  push    r14
0x14000a6a3  push    r15
0x14000a6a5  sub     rsp, 68h
0x14000a6a9  mov     rax, cs:__security_cookie
0x14000a6b0  xor     rax, rsp
0x14000a6b3  mov     [rsp+0A8h+var_50], rax
0x14000a6b8  mov     rax, [r8+60h]
0x14000a6bc  xorps   xmm0, xmm0
0x14000a6bf  mov     r13, [r8+230h]
0x14000a6c6  mov     rdi, rcx
0x14000a6c9  mov     r12, r9
0x14000a6cc  mov     rsi, r8
0x14000a6cf  mov     r14d, edx
0x14000a6d2  mov     rbp, [rax+1F0h]
0x14000a6d9  movups  xmmword ptr [rsp+0A8h+pbOutput], xmm0
0x14000a6de  mov     [rsp+0A8h+phNewHash], 0
0x14000a6e7  movups  [rsp+0A8h+var_60], xmm0
0x14000a6ec  mov     ecx, [r13+78h]
0x14000a6f0  test    ecx, ecx
0x14000a6f2  jz      loc_14000A925
0x14000a6f8  call    Smb2AllocateSigningHashObject
0x14000a6fd  mov     r15, rax
0x14000a700  test    rax, rax
0x14000a703  jz      loc_14000A82E
0x14000a709  mov     r9d, [r13+78h]; cbHashObject
0x14000a70d  lea     rdx, [rsp+0A8h+phNewHash]; phNewHash
0x14000a712  mov     rcx, [r13+70h]; hHash
0x14000a716  mov     r8, rax; pbHashObject
0x14000a719  mov     [rsp+0A8h+dwFlags], 0; dwFlags
0x14000a721  call    cs:__imp_BCryptDuplicateHash
0x14000a728  nop     dword ptr [rax+rax+00h]
0x14000a72d  mov     ebx, eax
0x14000a72f  test    eax, eax
0x14000a731  jns     short loc_14000A78E
0x14000a733  mov     rax, cs:WPP_GLOBAL_Control
0x14000a73a  lea     rcx, WPP_GLOBAL_Control
0x14000a741  cmp     rax, rcx
0x14000a744  jnz     loc_14000A94E
0x14000a74a  mov     rcx, [rsp+0A8h+phNewHash]; hHash
0x14000a74f  test    rcx, rcx
0x14000a752  jz      short loc_14000A760
0x14000a754  call    cs:__imp_BCryptDestroyHash
0x14000a75b  nop     dword ptr [rax+rax+00h]
0x14000a760  test    r15, r15
0x14000a763  jz      short loc_14000A76D
0x14000a765  mov     rcx, r15
0x14000a768  call    Smb2DeallocateSigningHashObject
0x14000a76d  mov     eax, ebx
0x14000a76f  mov     rcx, [rsp+0A8h+var_50]
0x14000a774  xor     rcx, rsp; StackCookie
0x14000a777  call    __security_check_cookie
0x14000a77c  add     rsp, 68h
0x14000a780  pop     r15
0x14000a782  pop     r14
0x14000a784  pop     r13
0x14000a786  pop     r12
0x14000a788  pop     rdi
0x14000a789  pop     rsi
0x14000a78a  pop     rbp
0x14000a78b  pop     rbx
0x14000a78c  retn
0x14000a78e  mov     ecx, [rbp+8Ch]
0x14000a794  call    cs:__imp_SmbCryptoSigningAlgRequireIV
0x14000a79b  nop     dword ptr [rax+rax+00h]
0x14000a7a0  test    al, al
0x14000a7a2  jnz     loc_14000A85A
0x14000a7a8  test    byte ptr [rdi+0Ah], 5
0x14000a7ac  jz      loc_14000A8F8
0x14000a7b2  mov     rax, [rdi+18h]
0x14000a7b6  mov     ecx, [rdi+28h]
0x14000a7b9  mov     ebp, r14d
0x14000a7bc  cmp     r14d, ecx
0x14000a7bf  cmovnb  ebp, ecx
0x14000a7c2  test    rax, rax
0x14000a7c5  jz      loc_14000A9AA
0x14000a7cb  mov     rcx, [rsp+0A8h+phNewHash]; hHash
0x14000a7d0  xor     r9d, r9d; dwFlags
0x14000a7d3  mov     rdi, [rdi]
0x14000a7d6  mov     r8d, ebp; cbInput
0x14000a7d9  mov     rdx, rax; pbInput
0x14000a7dc  call    cs:__imp_BCryptHashData
0x14000a7e3  nop     dword ptr [rax+rax+00h]
0x14000a7e8  mov     ebx, eax
0x14000a7ea  test    eax, eax
0x14000a7ec  js      loc_14000A8C0
0x14000a7f2  test    rdi, rdi
0x14000a7f5  jnz     short loc_14000A84F
0x14000a7f7  mov     r8d, [r13+7Ch]; cbOutput
0x14000a7fb  lea     rdx, [rsp+0A8h+pbOutput]; pbOutput
0x14000a800  mov     rcx, [rsp+0A8h+phNewHash]; hHash
0x14000a805  xor     r9d, r9d; dwFlags
0x14000a808  call    cs:__imp_BCryptFinishHash
0x14000a80f  nop     dword ptr [rax+rax+00h]
0x14000a814  mov     ebx, eax
0x14000a816  test    eax, eax
0x14000a818  js      loc_14000A972
0x14000a81e  movups  xmm0, xmmword ptr [rsp+0A8h+pbOutput]
0x14000a823  movdqu  xmmword ptr [r12], xmm0
0x14000a829  jmp     loc_14000A74A
0x14000a82e  mov     r10, cs:WPP_GLOBAL_Control
0x14000a835  lea     rcx, WPP_GLOBAL_Control
0x14000a83c  cmp     r10, rcx
0x14000a83f  jnz     loc_14000A92C
0x14000a845  mov     ebx, 0C000009Ah
0x14000a84a  jmp     loc_14000A74A
0x14000a84f  sub     r14d, ebp
0x14000a852  jnz     loc_14000A7A8
0x14000a858  jmp     short loc_14000A7F7
0x14000a85a  mov     rax, [rsp+0A8h+phNewHash]
0x14000a85f  xor     r9d, r9d
0x14000a862  mov     rdx, [r13+0B0h]
0x14000a869  mov     r8b, 1
0x14000a86c  mov     ecx, [rbp+8Ch]
0x14000a872  mov     qword ptr [rsp+0A8h+dwFlags], rax
0x14000a877  call    cs:__imp_SmbCryptoCalculateAndSetIV
0x14000a87e  nop     dword ptr [rax+rax+00h]
0x14000a883  mov     ebx, eax
0x14000a885  test    eax, eax
0x14000a887  jns     loc_14000A7A8
0x14000a88d  mov     r10, cs:WPP_GLOBAL_Control
0x14000a894  lea     rcx, WPP_GLOBAL_Control
0x14000a89b  cmp     r10, rcx
0x14000a89e  jz      loc_14000A74A
0x14000a8a4  mov     eax, [r10+2Ch]
0x14000a8a8  test    al, 1
0x14000a8aa  jz      loc_14000A74A
0x14000a8b0  cmp     byte ptr [r10+29h], 1
0x14000a8b5  jb      loc_14000A74A
0x14000a8bb  jmp     loc_14003AC52
0x14000a8c0  mov     r10, cs:WPP_GLOBAL_Control
0x14000a8c7  lea     rcx, WPP_GLOBAL_Control
0x14000a8ce  cmp     r10, rcx
0x14000a8d1  jz      loc_14000A74A
0x14000a8d7  mov     eax, [r10+2Ch]
0x14000a8db  test    al, 1
0x14000a8dd  jz      loc_14000A74A
0x14000a8e3  cmp     byte ptr [r10+29h], 1
0x14000a8e8  jb      loc_14000A74A
0x14000a8ee  mov     edx, 0Eh
0x14000a8f3  jmp     loc_14003AC57
0x14000a8f8  xor     r9d, r9d; RequestedAddress
0x14000a8fb  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x14000a903  xor     edx, edx; AccessMode
0x14000a905  mov     [rsp+0A8h+dwFlags], 0; BugCheckOnFailure
0x14000a90d  mov     rcx, rdi; MemoryDescriptorList
0x14000a910  lea     r8d, [r9+1]; CacheType
0x14000a914  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a91b  nop     dword ptr [rax+rax+00h]
0x14000a920  jmp     loc_14000A7B6
0x14000a925  int     2Ch; Windows NT - assertion failure
0x14000a927  jmp     loc_14000A6F8
0x14000a92c  mov     edx, [r10+2Ch]
0x14000a930  test    dl, 1
0x14000a933  jz      loc_14000A845
0x14000a939  cmp     byte ptr [r10+29h], 1
0x14000a93e  jb      loc_14000A845
0x14000a944  mov     edx, 0Ah
0x14000a949  jmp     loc_14003AC74
0x14000a94e  mov     edx, [rax+2Ch]
0x14000a951  test    dl, 1
0x14000a954  jz      loc_14000A74A
0x14000a95a  cmp     byte ptr [rax+29h], 1
0x14000a95e  jb      loc_14000A74A
0x14000a964  mov     rcx, [rax+18h]
0x14000a968  mov     edx, 0Bh
0x14000a96d  jmp     loc_14003AC5B
0x14000a972  mov     r10, cs:WPP_GLOBAL_Control
0x14000a979  lea     rcx, WPP_GLOBAL_Control
0x14000a980  cmp     r10, rcx
0x14000a983  jz      loc_14000A74A
0x14000a989  mov     eax, [r10+2Ch]
0x14000a98d  test    al, 1
0x14000a98f  jz      loc_14000A74A
0x14000a995  cmp     byte ptr [r10+29h], 1
0x14000a99a  jb      loc_14000A74A
0x14000a9a0  mov     edx, 0Fh
0x14000a9a5  jmp     loc_14003AC57
0x14000a9aa  mov     r10, cs:WPP_GLOBAL_Control
0x14000a9b1  lea     rcx, WPP_GLOBAL_Control
0x14000a9b8  cmp     r10, rcx
0x14000a9bb  jz      loc_14000A845
0x14000a9c1  mov     eax, [r10+2Ch]
0x14000a9c5  test    al, 1
0x14000a9c7  jz      loc_14000A845
0x14000a9cd  cmp     byte ptr [r10+29h], 1
0x14000a9d2  jb      loc_14000A845
0x14000a9d8  mov     edx, 0Dh
0x14000a9dd  jmp     loc_14003AC74
0x14003ac52  mov     edx, 0Ch
0x14003ac57  mov     rcx, [r10+18h]
0x14003ac5b  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x14003ac62  mov     [rsp+0A8h+dwFlags], ebx
0x14003ac66  mov     r9, rsi
0x14003ac69  call    WPP_SF_qD
0x14003ac6e  nop
0x14003ac6f  jmp     loc_14000A74A
0x14003ac74  mov     rcx, [r10+18h]
0x14003ac78  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x14003ac7f  mov     r9, rsi
0x14003ac82  call    WPP_SF_q
0x14003ac87  nop
0x14003ac88  jmp     loc_14000A845
```
