# Smb2GetNegotiateSecurityInfo

- ea: `0x14008ef4c`
- end: `0x14008f108`
- name: `Smb2GetNegotiateSecurityInfo`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140090240`

## callees

- `0x140024260`
- `0x140038490`
- `0x14008ef4c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14008efee`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14008efee`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008f063`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008f063`
- `srvnet!SrvLibQueryCredentialHandle` at `0x14008f004`
- `srvnet!SrvLibQueryCredentialHandle` at `0x14008f004`
- `ksecdd!MapSecurityError` at `0x14008f0e7`
- `ksecdd!MapSecurityError` at `0x14008f0e7`
- `ksecdd!DeleteSecurityContext` at `0x14008f090`
- `ksecdd!DeleteSecurityContext` at `0x14008f090`
- `ksecdd!AcceptSecurityContext` at `0x14008f04a`
- `ksecdd!AcceptSecurityContext` at `0x14008f04a`

## pseudocode

```c
NTSTATUS __fastcall Smb2GetNegotiateSecurityInfo(_QWORD *a1, _DWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rsi
  struct _SecHandle *CredentialHandle; // rax
  SECURITY_STATUS v7; // eax
  __int64 v8; // rdi
  SECURITY_STATUS v9; // r14d
  int v10; // ecx
  __int64 v11; // rsi
  __int64 v12; // rdi
  NTSTATUS result; // eax
  unsigned int pfContextAttr; // [rsp+50h] [rbp-19h] BYREF
  __int128 v15; // [rsp+58h] [rbp-11h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+68h] [rbp-1h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+78h] [rbp+Fh] BYREF
  struct _SecHandle phContext; // [rsp+80h] [rbp+17h] BYREF

  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  phContext = 0;
  v4 = MEMORY[0xFFFFF78000000014];
  *a1 = 0;
  *a2 = 0;
  pOutput.cBuffers = 1;
  pOutput.pBuffers = (PSecBuffer)&v15;
  pOutput.ulVersion = 0;
  v15 = 0x200000000uLL;
  ExAcquireResourceSharedLite(&Smb2ExtensibleCredHandleLock, 1u);
  v5 = MEMORY[0xFFFFF78000000014];
  CredentialHandle = (struct _SecHandle *)SrvLibQueryCredentialHandle(Smb2ExtensibleCredentialHandle);
  v7 = AcceptSecurityContext(CredentialHandle, 0, 0, 0x120111u, 0x10u, &phContext, &pOutput, &pfContextAttr, &ptsExpiry);
  v8 = MEMORY[0xFFFFF78000000014];
  v9 = v7;
  ExReleaseResourceLite(&Smb2ExtensibleCredHandleLock);
  if ( v9 < 0 )
  {
    result = MapSecurityError(v9);
    if ( result == -1073741816 || result == -1073741570 )
      return -1073741623;
  }
  else
  {
    v10 = v15;
    v11 = v5 - v4;
    v12 = v8 - v4;
    if ( (_DWORD)v15 )
    {
      *a1 = *((_QWORD *)&v15 + 1);
      *a2 = v10;
    }
    DeleteSecurityContext(&phContext);
    if ( MEMORY[0xFFFFF78000000014] - v4 > 50000000 && (byte_14004C339 & 0x10) != 0 )
      McTemplateK0hxxxx_EtwWriteTransfer(
        (unsigned __int64)(v12 + ((unsigned __int128)(v12 * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64)) >> 63,
        v11 / 10000000,
        v12 / 10000000,
        0,
        v11 / 10000000,
        v12 / 10000000,
        (MEMORY[0xFFFFF78000000014] - v4) / 10000000);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14008ef4c  mov     [rsp-8+arg_10], rbx
0x14008ef51  mov     [rsp-8+arg_18], rsi
0x14008ef56  push    rbp
0x14008ef57  push    rdi
0x14008ef58  push    r12
0x14008ef5a  push    r14
0x14008ef5c  push    r15
0x14008ef5e  lea     rbp, [rsp-37h]
0x14008ef63  sub     rsp, 0A0h
0x14008ef6a  mov     rax, cs:__security_cookie
0x14008ef71  xor     rax, rsp
0x14008ef74  mov     [rbp+57h+var_30], rax
0x14008ef78  xorps   xmm0, xmm0
0x14008ef7b  mov     [rbp+57h+var_70], 0
0x14008ef82  movups  xmmword ptr [rbp+57h+var_58.ulVersion], xmm0
0x14008ef86  mov     qword ptr [rbp+57h+var_48], 0
0x14008ef8e  mov     r12, rdx
0x14008ef91  xorps   xmm1, xmm1
0x14008ef94  lea     rax, [rbp+57h+var_68]
0x14008ef98  movups  [rbp+57h+var_68], xmm1
0x14008ef9c  mov     r15, rcx
0x14008ef9f  mov     rdi, 0FFFFF78000000014h
0x14008efa9  movups  xmmword ptr [rbp+57h+phContext.dwLower], xmm0
0x14008efad  mov     rbx, [rdi]
0x14008efb0  mov     qword ptr [rcx], 0
0x14008efb7  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x14008efbe  mov     dword ptr [rdx], 0
0x14008efc4  mov     dl, 1; Wait
0x14008efc6  mov     [rbp+57h+var_58.cBuffers], 1
0x14008efcd  mov     [rbp+57h+var_58.pBuffers], rax
0x14008efd1  mov     [rbp+57h+var_58.ulVersion], 0
0x14008efd8  mov     qword ptr [rbp+57h+var_68+8], 0
0x14008efe0  mov     dword ptr [rbp+57h+var_68], 0
0x14008efe7  mov     dword ptr [rbp+57h+var_68+4], 2
0x14008efee  call    cs:__imp_ExAcquireResourceSharedLite
0x14008eff5  nop     dword ptr [rax+rax+00h]
0x14008effa  mov     rsi, [rdi]
0x14008effd  mov     rcx, cs:Smb2ExtensibleCredentialHandle
0x14008f004  call    cs:__imp_SrvLibQueryCredentialHandle
0x14008f00b  nop     dword ptr [rax+rax+00h]
0x14008f010  mov     r9d, 120111h; fContextReq
0x14008f016  xor     r8d, r8d; pInput
0x14008f019  mov     rcx, rax; phCredential
0x14008f01c  xor     edx, edx; phContext
0x14008f01e  lea     rax, [rbp+57h+var_48]
0x14008f022  mov     [rsp+0C0h+ptsExpiry], rax; ptsExpiry
0x14008f027  lea     rax, [rbp+57h+var_70]
0x14008f02b  mov     [rsp+0C0h+pfContextAttr], rax; pfContextAttr
0x14008f030  lea     rax, [rbp+57h+var_58]
0x14008f034  mov     [rsp+0C0h+pOutput], rax; pOutput
0x14008f039  lea     rax, [rbp+57h+phContext]
0x14008f03d  mov     [rsp+0C0h+phNewContext], rax; phNewContext
0x14008f042  mov     [rsp+0C0h+TargetDataRep], 10h; TargetDataRep
0x14008f04a  call    cs:__imp_AcceptSecurityContext
0x14008f051  nop     dword ptr [rax+rax+00h]
0x14008f056  mov     rdi, [rdi]
0x14008f059  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x14008f060  mov     r14d, eax
0x14008f063  call    cs:__imp_ExReleaseResourceLite
0x14008f06a  nop     dword ptr [rax+rax+00h]
0x14008f06f  test    r14d, r14d
0x14008f072  js      short loc_14008F0E4
0x14008f074  mov     ecx, dword ptr [rbp+57h+var_68]
0x14008f077  sub     rsi, rbx
0x14008f07a  sub     rdi, rbx
0x14008f07d  test    ecx, ecx
0x14008f07f  jz      short loc_14008F08C
0x14008f081  mov     rax, qword ptr [rbp+57h+var_68+8]
0x14008f085  mov     [r15], rax
0x14008f088  mov     [r12], ecx
0x14008f08c  lea     rcx, [rbp+57h+phContext]; phContext
0x14008f090  call    cs:__imp_DeleteSecurityContext
0x14008f097  nop     dword ptr [rax+rax+00h]
0x14008f09c  mov     rcx, 0FFFFF78000000014h
0x14008f0a6  mov     rcx, [rcx]
0x14008f0a9  sub     rcx, rbx
0x14008f0ac  cmp     rcx, 2FAF080h
0x14008f0b3  jg      loc_14009BB04
0x14008f0b9  xor     eax, eax
0x14008f0bb  mov     rcx, [rbp+57h+var_30]
0x14008f0bf  xor     rcx, rsp; StackCookie
0x14008f0c2  call    __security_check_cookie
0x14008f0c7  lea     r11, [rsp+0C0h+var_20]
0x14008f0cf  mov     rbx, [r11+40h]
0x14008f0d3  mov     rsi, [r11+48h]
0x14008f0d7  mov     rsp, r11
0x14008f0da  pop     r15
0x14008f0dc  pop     r14
0x14008f0de  pop     r12
0x14008f0e0  pop     rdi
0x14008f0e1  pop     rbp
0x14008f0e2  retn
0x14008f0e4  mov     ecx, r14d; SecStatus
0x14008f0e7  call    cs:__imp_MapSecurityError
0x14008f0ee  nop     dword ptr [rax+rax+00h]
0x14008f0f3  cmp     eax, 0C0000008h
0x14008f0f8  jz      short loc_14008F101
0x14008f0fa  cmp     eax, 0C00000FEh
0x14008f0ff  jnz     short loc_14008F0BB
0x14008f101  mov     eax, 0C00000C9h
0x14008f106  jmp     short loc_14008F0BB
0x14009bb04  test    cs:byte_14004C339, 10h
0x14009bb0b  jz      loc_14008F0B9
0x14009bb11  mov     r9, 0D6BF94D5E57A42BDh
0x14009bb1b  mov     rax, r9
0x14009bb1e  imul    rcx
0x14009bb21  mov     rax, r9
0x14009bb24  lea     r10, [rcx+rdx]
0x14009bb28  imul    rdi
0x14009bb2b  mov     rax, r9
0x14009bb2e  sar     r10, 17h
0x14009bb32  mov     rcx, r10
0x14009bb35  xor     r9d, r9d
0x14009bb38  shr     rcx, 3Fh
0x14009bb3c  add     r10, rcx
0x14009bb3f  lea     r8, [rdi+rdx]
0x14009bb43  mov     [rsp+0C0h+pOutput], r10
0x14009bb48  imul    rsi
0x14009bb4b  sar     r8, 17h
0x14009bb4f  add     rdx, rsi
0x14009bb52  mov     rcx, r8
0x14009bb55  sar     rdx, 17h
0x14009bb59  mov     rax, rdx
0x14009bb5c  shr     rcx, 3Fh
0x14009bb60  shr     rax, 3Fh
0x14009bb64  add     r8, rcx
0x14009bb67  add     rdx, rax
0x14009bb6a  mov     [rsp+0C0h+phNewContext], r8
0x14009bb6f  mov     qword ptr [rsp+0C0h+TargetDataRep], rdx
0x14009bb74  call    McTemplateK0hxxxx_EtwWriteTransfer
0x14009bb79  nop
0x14009bb7a  jmp     loc_14008F0B9
```
